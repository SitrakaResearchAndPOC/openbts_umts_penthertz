docker pull ubuntu:22.04

docker rm -f  openbts-umts 2> /dev/null ; \
docker run -tid --privileged \
  --cgroupns=host \
  --net=host \
  -v /sys/fs/cgroup:/sys/fs/cgroup:rw \
  -v /dev:/dev \
  -v /dev/bus/usb:/dev/bus/usb \
  -v /tmp/.X11-unix:/tmp/.X11-unix:ro \
  -v /home/user/.Xauthority:/home/user/.Xauthority:ro \
  --tmpfs /run \
  --tmpfs /run/lock \
  --env="DISPLAY=$DISPLAY" \
  --env="LC_ALL=C.UTF-8" \
  --env="LANG=C.UTF-8" \
  --env="NAME_PLUTO=pluto" \
  --cap-add=sys_nice \
  --cap-add=ipc_lock \
  --ulimit rtprio=99 \
  --ulimit memlock=-1 \
  --volume /run/dbus/system_bus_socket:/run/dbus/system_bus_socket \
  --volume /run/avahi-daemon/socket:/run/avahi-daemon/socket \
  --name openbts-umts \
  --hostname openbts-umts \
  ubuntu:22.04
  

docker exec -it   openbts-umts  bash 

apt update

apt install -y uhd-host libuhd-dev 

uhd_images_downloader

apt install -y git nano wget sqlite3  autoconf automake libtool pkg-config debhelper build-essential devscripts fakeroot dpkg-dev 
apt install -y build-essential debhelper pkg-config autoconf libtool libtool-bin libortp-dev libsqlite3-dev libusb-1.0-0-dev libreadline-dev libzmq3-dev libosip2-dev sqlite3 libusb-1.0-0 libortp-dev libc6 pkg-config libreadline* libosip2-11 git net-cat
apt install -y python3 python3-pip python-is-python3

git clone https://github.com/SitrakaResearchAndPOC/fork_OpenBTS-UMTS

mv fork_OpenBTS-UMTS OpenBTS-UMTS
cd fork_OpenBTS-UMTS/

git checkout 1.1

# git log

# Enlever sudo au debut de ligne avec sed
sed -i 's/^sudo[[:space:]]\+//' install_dependences.sh
sed -i 's/^sudo[[:space:]]\+//' autogen.sh

./install_dependences.sh 

mkdir -p  /etc/OpenBTS-UMTS

# ls -ld /etc/OpenBTS-UMTS

./autogen.sh
  
./configure
  
make -j$(nproc --ignore 1)

make install

# ls -ld /etc/OpenBTS-UMTS



git clone https://github.com/SitrakaResearchAndPOC/fork_libcoredumper
mv fork_libcoredumper libcoredumper
cd fork_libcoredumper
# comment last line to build it by makefile 
sed -i '/^[[:space:]]*#/! s/^\([[:space:]]*\)sayAndDo dpkg-buildpackage -us -uc/\1# sayAndDo dpkg-buildpackage -us -uc/' build.sh

# use my save libcoredumper
sed -i -e '/^[[:space:]]*#/! s|^\([[:space:]]*\)sayAndDo wget https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/google-coredumper/coredumper-\$VERSION\.tar\.gz|\1# sayAndDo wget https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/google-coredumper/coredumper-$VERSION.tar.gz|' -e '/# sayAndDo wget https:\/\/storage\.googleapis\.com\/google-code-archive-downloads\/v2\/code\.google\.com\/google-coredumper\/coredumper-\$VERSION\.tar\.gz/a\
        sayAndDo wget https://raw.githubusercontent.com/SitrakaResearchAndPOC/openbts_umts_penthertz/refs/heads/main/files/coredumper/coredumper-$VERSION.tar.gz' build.sh


./build.sh
cd coredumper-1.2.1
autoreconf -fi
automake --add-missing --force-missing
automake --add-missing --copy
./configure
make -j$(nproc --ignore 1) && make install && ldconfig
cp TransceiverUHD/transceiver apps
cd /OpenBTS-UMTS


git clone https://github.com/SitrakaResearchAndPOC/fork_subscriberRegistry
mv fork_subscriberRegistry subscriberRegistry
cp -rf CommonLibs/ subscriberRegistry/
cp -rf NodeManager/ subscriberRegistry/

cd subscriberRegistry/
# git submodule init
# git submodule update
./autogen.sh
./configure
make -j$(nproc --ignore 1) && make install && ldconfig
cp /usr/local/sbin/* /OpenBTS
cp apps/hexmapper /OpenBTS
cp apps/syslogextractor /OpenBTS
cp apps/checkdb.sh /OpenBTS
cd /OpenBTS-UMTS

sed -i 's/socket.send(request)/socket.send_string(request)/g' /OpenBTS-UMTS/subscriberRegistry/NodeManager/nmcli.py
sed -i 's/print ("raw response: " + response)/print("raw response: " + response.decode())/g' /OpenBTS-UMTS/subscriberRegistry/NodeManager/nmcli.py


sed -i 's/socket.send(request)/socket.send_string(request)/g' /OpenBTS-UMTS/NodeManager/nmcli.py
sed -i 's/print ("raw response: " + response)/print("raw response: " + response.decode())/g' /OpenBTS-UMTS/NodeManager/nmcli.py

cp -rf /OpenBTS-UMTS/NodeManager/nmcli.py /OpenBTS

# all example conf in /etc/OpenBTS
# all binairies in /OpenBTS

mkdir -p /var/log/OpenBTS-UMTS
mkdir -p /var/lib/asterisk/sqlite3dir
mkdir -p /var/lib/asterisk/ 
cd /OpenBTS
sqlite3 /etc/OpenBTS/OpenBTS-UMTS.db ".read /etc/OpenBTS/OpenBTS-UMTS.example.sql"

#verifying sipauthserve
docker exec -it   openbts-umts  bash  -c 'ss -lntp | grep 45064'
docker exec -it   openbts-umts  bash -c 'nc -zv 127.0.0.1 45064'


# Launching
# Terminal 1 : 
docker exec -it   openbts-umts  bash  -c 'cd /OpenBTS && ./OpenBTS-UMTS'

# Terminal 2 :
docker exec -it   openbts-umts  bash  -c 'sipauthserve'

# Terminal 3 :
docker exec -it   openbts-umts  bash  -c 'cd /OpenBTS-UMTS/NodeManager && python nmcli.py sipauthserve subscribers read'

docker exec -it   openbts-umts  bash  -c 'cd /OpenBTS-UMTS/NodeManager && python nmcli.py sipauthserve subscribers create "iPhone 4" IMSI21405771529963 6055551234'


In real host
iptables -t nat -A POSTROUTING -j MASQUERADE -o eth0
sysctl -w net.ipv4.ip_forward=1 
ufw disable 




Probleme database sqlite : 
pkill sipauthserve
rm -rf /var/lib/asterisk/sqlite3dir
mkdir -p /var/lib/asterisk/sqlite3dir
rm -f /var/lib/asterisk/sqlite3dir/sqlite3.db

cd /OpenBTS-UMTS/subscriberRegistry/apps/
sqlite3 sqlite3.db < sipauthserve.example.sql
sipauthserve
