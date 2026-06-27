 1  docker pull ubuntu:22.04 

    apt install uhd-host
    2  apt update
    3  apt install uhd-host
    4  uhd_usrp_probe 
    5  uhd_images_downloader 
    6  uhd_usrp_probe 
    7  clear
    8  git clone https://github.com/PentHertz/OpenBTS-UMTS.git
    9  apt install git
   10  git clone https://github.com/PentHertz/OpenBTS-UMTS.git
   11  cd OpenBTS-UMTS/
   12  git checkout 1.1
   13  git log
   14  ./install_dependences.sh 
   15  nano install_dependences.sh 
   16  apt install nano 
   17  nano install_dependences.sh 
#commande sed pour enlever sudo au debut de chaque ligne
   18  ./install_dependences.sh 
   19  make -j 10
   20  make install
   21  apt install sqlite3
   22  ls
   23  find -name *.sql
   24  cd apps/
   25  ls
   26  ls -ld /etc/OpenBTS-UMTS
   27  mkdir -p  /etc/OpenBTS-UMTS
   28  echo 1 | sudo tee /proc/sys/net/ipv4/ip_forward 1>/dev/null
   29  cd ..
   30  cat build.sh 
   31  ./build.sh
   32  apt install wget
   33  ./build.sh
   34  cd coredumper-1.2.1
   35  ./configure 
   36  make && make install
   37  cd ..
   38  git clone https://github.com/PentHertz/subscriberRegistry
   39  git submodule init
   40  ./autogen.sh
   41  cd subscriberRegistry/
   42  ./autogen.sh
   43  autoreconf fi
   44  autoreconf -fi
   45  cd ..
   46  ./autogen.sh 
   47  ./configure
   48  cd subscriberRegistry/
   49  ls
   50  ./configure
   51  autoreconf -fi
   52  cd ..
   53  ls -ld CommonLibs NodeManager
   54  find CommonLibs -name Makefile.am
   55  find NodeManager -name Makefile.am
   56  find CommonLibs -name Makefile.in
   57  find NodeManager -name Makefile.in
   58  head -100 /OpenBTS-UMTS/subscriberRegistry/configure.ac
   59  cd /OpenBTS-UMTS/subscriberRegistry
   60  ls -ld CommonLibs NodeManager Globals apps config
   61  find . -name Makefile.in
   62  make distclean 2>/dev/null
   63  rm -rf autom4te.cache config.log config.status
   64  autoreconf -fi
   65  apt install -y autoconf automake libtool pkg-config
   66  automake --add-missing --copy
   67  autoreconf -fi
   68  ls
   69  cd ..
   70  ls
   71  cd subscriberRegistry/
   72  cd ..
   73  autoreconf -fi
   74  ./configure
   75  make -j$(nproc)
   76  make install
   77  cd subscriberRegistry/
   78  make
   79  autoreconf -fi
   80  cd ..
   81  cp -rf CommonLibs/ subscriberRegistry/
   82  cp -rf NodeManager/ subscriberRegistry/
   83  cd subscriberRegistry/
   84  autoreconf -fi
   85  ./autogen.sh
   86  ./configure
   87  make -j10
   88  nano SubscriberRegistry.h
#ajouter #include <vector> et #include <string>
   89  make -j10
   90  make -j$(nproc)
   91  ldconfig
   92  history
   93  clear
   94  history



TERMINAL 1
root@openbts-umts:/OpenBTS-UMTS/apps# history
    1  apt install uhd-host
    2  apt update
    3  apt install uhd-host
    4  uhd_usrp_probe 
    5  uhd_images_downloader 
    6  uhd_usrp_probe 
    7  clear
    8  git clone https://github.com/PentHertz/OpenBTS-UMTS.git
    9  apt install git
   10  git clone https://github.com/PentHertz/OpenBTS-UMTS.git
   11  cd OpenBTS-UMTS/
   12  git checkout 1.1
   13  git log
   14  ./install_dependences.sh 
   15  nano install_dependences.sh 
   16  apt install nano 
   17  nano install_dependences.sh 
   18  ./install_dependences.sh 
   19  make -j 10
   20  make install
   21  apt install sqlite3
   22  ls
   23  find -name *.sql
   24  cd apps/
   25  ls
   26  ls -ld /etc/OpenBTS-UMTS
   27  mkdir -p  /etc/OpenBTS-UMTS
   28  echo 1 | sudo tee /proc/sys/net/ipv4/ip_forward 1>/dev/null
   29  cd ..
   30  cat build.sh 
   31  ./build.sh
   32  apt install wget
   33  ./build.sh
   34  cd coredumper-1.2.1
   35  ./configure 
   36  make && make install
   37  cd ..
   38  git clone https://github.com/PentHertz/subscriberRegistry
   39  git submodule init
   40  ./autogen.sh
   41  cd subscriberRegistry/
   42  ./autogen.sh
   43  autoreconf fi
   44  autoreconf -fi
   45  cd ..
   46  ./autogen.sh 
   47  ./configure
   48  cd subscriberRegistry/
   49  ls
   50  ./configure
   51  autoreconf -fi
   52  cd ..
   53  ls -ld CommonLibs NodeManager
   54  find CommonLibs -name Makefile.am
   55  find NodeManager -name Makefile.am
   56  find CommonLibs -name Makefile.in
   57  find NodeManager -name Makefile.in
   58  head -100 /OpenBTS-UMTS/subscriberRegistry/configure.ac
   59  cd /OpenBTS-UMTS/subscriberRegistry
   60  ls -ld CommonLibs NodeManager Globals apps config
   61  find . -name Makefile.in
   62  make distclean 2>/dev/null
   63  rm -rf autom4te.cache config.log config.status
   64  autoreconf -fi
   65  apt install -y autoconf automake libtool pkg-config
   66  automake --add-missing --copy
   67  autoreconf -fi
   68  ls
   69  cd ..
   70  ls
   71  cd subscriberRegistry/
   72  cd ..
   73  autoreconf -fi
   74  ./configure
   75  make -j$(nproc)
   76  make install
   77  cd subscriberRegistry/
   78  make
   79  autoreconf -fi
   80  cd ..
   81  cp -rf CommonLibs/ subscriberRegistry/
   82  cp -rf NodeManager/ subscriberRegistry/
   83  cd subscriberRegistry/
   84  autoreconf -fi
   85  ./autogen.sh
   86  ./configure
   87  make -j10
   88  nano SubscriberRegistry.h
   89  make -j10
   90  make -j$(nproc)
   91  ldconfig
   92  history
   93  clear
   94  history
   95  ls
   96  cd ..
   97  ls
   98  fnd -name comp128
   99  ls
  100  cd subscriberRegistry/
  101  make install
  102  cd /OpenBTS-UMTS/subscriberRegistry/apps/
  103  ls /OpenBTS-UMTS/subscriberRegistry/apps/
  104  cp comp128 /OpenBTS-UMTS/
  105  cd ..
  106  ls
  107  cd apps/
  108  ls
  109  ./OpenBTS-UMTS
  110  ls
  111  cd ..
  112  ls
  113  cd TRXManager/
  114  ls
  115  cd ..
  116  cd Transceiver
  117  cd TransceiverUHD/
  118  ls
  119  cp transceiver /OpenBTS-UMTS/apps/
  120  cd ..
  121  cd apps/
  122  ls
  123  ./OpenBTS-UMTS
  124  clear
  125  ls
  126  cat doppp.sh 
  127  ls
  128  cd ..
  129  ls
  130  cd NodeManager/
  131  ls
  132  cat nmcli.py 
  133  apt install  cp /OpenBTS-UMTS/comp128 /OpenBTS-UMTS/
  134  apt install  libuhd-dev
  135  cd /etc/OpenBTS
  136  ls
  137  sudo sqlite3 /etc/OpenBTS/OpenBTS-UMTS.db “.read OpenBTS-UMTS.example.sql”
  138  sqlite3 /etc/OpenBTS/OpenBTS-UMTS.db “.read OpenBTS-UMTS.example.sql”
  139  cd /OpenBTS-UMTS/
  140  ls
  141  mkdir /var/lib/asterisk/
  142  mkdir /var/lib/asterisk/sqlite3dir/
  143  ls subscriberRegistry/apps/comp128
  144  cd subscriberRegistry/apps/
  145  ls
  146  cd ..
  147  mkdir /var/lib/asterisk/sqlite3dir/
  148  cp subscriberRegistry/apps/comp128 /OpenBTS-UMTS/
  149  cp subscriberRegistry/apps/comp128 /OpenBTS-UMTS/apps/
  150  cp subscriberRegistry/apps/comp128 /OpenBTS
  151  cd NodeManager/
  152  ./nmcli.py sipauthserve subscribers create "iPhone 4" IMSI214057715229963 6055551234
  153  cd ..
  154  exit
  155  cd /OpenBTS
  156  cd ..
  157  cd /OpenBTS-UMTS/
  158  ls
  159  cd apps/
  160  ls
  161  ./OpenBTS-UMTS
  162  history
root@openbts-umts:/OpenBTS-UMTS/apps# 




TERMINAL 2 

root@openbts-umts:/OpenBTS-UMTS/subscriberRegistry/apps# history
    1  apt install uhd-host
    2  apt update
    3  apt install uhd-host
    4  uhd_usrp_probe 
    5  uhd_images_downloader 
    6  uhd_usrp_probe 
    7  clear
    8  git clone https://github.com/PentHertz/OpenBTS-UMTS.git
    9  apt install git
   10  git clone https://github.com/PentHertz/OpenBTS-UMTS.git
   11  cd OpenBTS-UMTS/
   12  git checkout 1.1
   13  git log
   14  ./install_dependences.sh 
   15  nano install_dependences.sh 
   16  apt install nano 
   17  nano install_dependences.sh 
   18  ./install_dependences.sh 
   19  make -j 10
   20  make install
   21  apt install sqlite3
   22  ls
   23  find -name *.sql
   24  cd apps/
   25  ls
   26  ls -ld /etc/OpenBTS-UMTS
   27  mkdir -p  /etc/OpenBTS-UMTS
   28  echo 1 | sudo tee /proc/sys/net/ipv4/ip_forward 1>/dev/null
   29  cd ..
   30  cat build.sh 
   31  ./build.sh
   32  apt install wget
   33  ./build.sh
   34  cd coredumper-1.2.1
   35  ./configure 
   36  make && make install
   37  cd ..
   38  git clone https://github.com/PentHertz/subscriberRegistry
   39  git submodule init
   40  ./autogen.sh
   41  cd subscriberRegistry/
   42  ./autogen.sh
   43  autoreconf fi
   44  autoreconf -fi
   45  cd ..
   46  ./autogen.sh 
   47  ./configure
   48  cd subscriberRegistry/
   49  ls
   50  ./configure
   51  autoreconf -fi
   52  cd ..
   53  ls -ld CommonLibs NodeManager
   54  find CommonLibs -name Makefile.am
   55  find NodeManager -name Makefile.am
   56  find CommonLibs -name Makefile.in
   57  find NodeManager -name Makefile.in
   58  head -100 /OpenBTS-UMTS/subscriberRegistry/configure.ac
   59  cd /OpenBTS-UMTS/subscriberRegistry
   60  ls -ld CommonLibs NodeManager Globals apps config
   61  find . -name Makefile.in
   62  make distclean 2>/dev/null
   63  rm -rf autom4te.cache config.log config.status
   64  autoreconf -fi
   65  apt install -y autoconf automake libtool pkg-config
   66  automake --add-missing --copy
   67  autoreconf -fi
   68  ls
   69  cd ..
   70  ls
   71  cd subscriberRegistry/
   72  cd ..
   73  autoreconf -fi
   74  ./configure
   75  make -j$(nproc)
   76  make install
   77  cd subscriberRegistry/
   78  make
   79  autoreconf -fi
   80  cd ..
   81  cp -rf CommonLibs/ subscriberRegistry/
   82  cp -rf NodeManager/ subscriberRegistry/
   83  cd subscriberRegistry/
   84  autoreconf -fi
   85  ./autogen.sh
   86  ./configure
   87  make -j10
   88  nano SubscriberRegistry.h
   89  make -j10
   90  make -j$(nproc)
   91  ldconfig
   92  history
   93  clear
   94  history
   95  ls
   96  cd ..
   97  ls
   98  fnd -name comp128
   99  ls
  100  cd subscriberRegistry/
  101  make install
  102  cd /OpenBTS-UMTS/subscriberRegistry/apps/
  103  ls /OpenBTS-UMTS/subscriberRegistry/apps/
  104  cp comp128 /OpenBTS-UMTS/
  105  cd ..
  106  ls
  107  cd apps/
  108  ls
  109  ./OpenBTS-UMTS
  110  ls
  111  cd ..
  112  ls
  113  cd TRXManager/
  114  ls
  115  cd ..
  116  cd Transceiver
  117  cd TransceiverUHD/
  118  ls
  119  cp transceiver /OpenBTS-UMTS/apps/
  120  cd ..
  121  cd apps/
  122  ls
  123  ./OpenBTS-UMTS
  124  clear
  125  ls
  126  cat doppp.sh 
  127  ls
  128  cd ..
  129  ls
  130  cd NodeManager/
  131  ls
  132  cat nmcli.py 
  133  apt install  cp /OpenBTS-UMTS/comp128 /OpenBTS-UMTS/
  134  apt install  libuhd-dev
  135  cd /etc/OpenBTS
  136  ls
  137  sudo sqlite3 /etc/OpenBTS/OpenBTS-UMTS.db “.read OpenBTS-UMTS.example.sql”
  138  sqlite3 /etc/OpenBTS/OpenBTS-UMTS.db “.read OpenBTS-UMTS.example.sql”
  139  cd /OpenBTS-UMTS/
  140  ls
  141  mkdir /var/lib/asterisk/
  142  mkdir /var/lib/asterisk/sqlite3dir/
  143  ls subscriberRegistry/apps/comp128
  144  cd subscriberRegistry/apps/
  145  ls
  146  cd ..
  147  mkdir /var/lib/asterisk/sqlite3dir/
  148  cp subscriberRegistry/apps/comp128 /OpenBTS-UMTS/
  149  cp subscriberRegistry/apps/comp128 /OpenBTS-UMTS/apps/
  150  cp subscriberRegistry/apps/comp128 /OpenBTS
  151  cd NodeManager/
  152  ./nmcli.py sipauthserve subscribers create "iPhone 4" IMSI214057715229963 6055551234
  153  cd ..
  154  exit
  155  cd /OpenBTS-UMTS/
  156  cd subscriberRegistry/
  157  cd apps/
  158  ./sipauthserve 
  159  history
root@openbts-umts:/OpenBTS-UMTS/subscriberRegistry/apps# 


TERMINAL 3
root@openbts-umts:/OpenBTS-UMTS/NodeManager# history
    1  apt install uhd-host
    2  apt update
    3  apt install uhd-host
    4  uhd_usrp_probe 
    5  uhd_images_downloader 
    6  uhd_usrp_probe 
    7  clear
    8  git clone https://github.com/PentHertz/OpenBTS-UMTS.git
    9  apt install git
   10  git clone https://github.com/PentHertz/OpenBTS-UMTS.git
   11  cd OpenBTS-UMTS/
   12  git checkout 1.1
   13  git log
   14  ./install_dependences.sh 
   15  nano install_dependences.sh 
   16  apt install nano 
   17  nano install_dependences.sh 
   18  ./install_dependences.sh 
   19  make -j 10
   20  make install
   21  apt install sqlite3
   22  ls
   23  find -name *.sql
   24  cd apps/
   25  ls
   26  ls -ld /etc/OpenBTS-UMTS
   27  mkdir -p  /etc/OpenBTS-UMTS
   28  echo 1 | sudo tee /proc/sys/net/ipv4/ip_forward 1>/dev/null
   29  cd ..
   30  cat build.sh 
   31  ./build.sh
   32  apt install wget
   33  ./build.sh
   34  cd coredumper-1.2.1
   35  ./configure 
   36  make && make install
   37  cd ..
   38  git clone https://github.com/PentHertz/subscriberRegistry
   39  git submodule init
   40  ./autogen.sh
   41  cd subscriberRegistry/
   42  ./autogen.sh
   43  autoreconf fi
   44  autoreconf -fi
   45  cd ..
   46  ./autogen.sh 
   47  ./configure
   48  cd subscriberRegistry/
   49  ls
   50  ./configure
   51  autoreconf -fi
   52  cd ..
   53  ls -ld CommonLibs NodeManager
   54  find CommonLibs -name Makefile.am
   55  find NodeManager -name Makefile.am
   56  find CommonLibs -name Makefile.in
   57  find NodeManager -name Makefile.in
   58  head -100 /OpenBTS-UMTS/subscriberRegistry/configure.ac
   59  cd /OpenBTS-UMTS/subscriberRegistry
   60  ls -ld CommonLibs NodeManager Globals apps config
   61  find . -name Makefile.in
   62  make distclean 2>/dev/null
   63  rm -rf autom4te.cache config.log config.status
   64  autoreconf -fi
   65  apt install -y autoconf automake libtool pkg-config
   66  automake --add-missing --copy
   67  autoreconf -fi
   68  ls
   69  cd ..
   70  ls
   71  cd subscriberRegistry/
   72  cd ..
   73  autoreconf -fi
   74  ./configure
   75  make -j$(nproc)
   76  make install
   77  cd subscriberRegistry/
   78  make
   79  autoreconf -fi
   80  cd ..
   81  cp -rf CommonLibs/ subscriberRegistry/
   82  cp -rf NodeManager/ subscriberRegistry/
   83  cd subscriberRegistry/
   84  autoreconf -fi
   85  ./autogen.sh
   86  ./configure
   87  make -j10
   88  nano SubscriberRegistry.h
   89  make -j10
   90  make -j$(nproc)
   91  ldconfig
   92  history
   93  clear
   94  history
   95  ls
   96  cd ..
   97  ls
   98  fnd -name comp128
   99  ls
  100  cd subscriberRegistry/
  101  make install
  102  cd /OpenBTS-UMTS/subscriberRegistry/apps/
  103  ls /OpenBTS-UMTS/subscriberRegistry/apps/
  104  cp comp128 /OpenBTS-UMTS/
  105  cd ..
  106  ls
  107  cd apps/
  108  ls
  109  ./OpenBTS-UMTS
  110  ls
  111  cd ..
  112  ls
  113  cd TRXManager/
  114  ls
  115  cd ..
  116  cd Transceiver
  117  cd TransceiverUHD/
  118  ls
  119  cp transceiver /OpenBTS-UMTS/apps/
  120  cd ..
  121  cd apps/
  122  ls
  123  ./OpenBTS-UMTS
  124  clear
  125  ls
  126  cat doppp.sh 
  127  ls
  128  cd ..
  129  ls
  130  cd NodeManager/
  131  ls
  132  cat nmcli.py 
  133  apt install  cp /OpenBTS-UMTS/comp128 /OpenBTS-UMTS/
  134  apt install  libuhd-dev
  135  cd /etc/OpenBTS
  136  ls
  137  sudo sqlite3 /etc/OpenBTS/OpenBTS-UMTS.db “.read OpenBTS-UMTS.example.sql”
  138  sqlite3 /etc/OpenBTS/OpenBTS-UMTS.db “.read OpenBTS-UMTS.example.sql”
  139  cd /OpenBTS-UMTS/
  140  ls
  141  mkdir /var/lib/asterisk/
  142  mkdir /var/lib/asterisk/sqlite3dir/
  143  ls subscriberRegistry/apps/comp128
  144  cd subscriberRegistry/apps/
  145  ls
  146  cd ..
  147  mkdir /var/lib/asterisk/sqlite3dir/
  148  cp subscriberRegistry/apps/comp128 /OpenBTS-UMTS/
  149  cp subscriberRegistry/apps/comp128 /OpenBTS-UMTS/apps/
  150  cp subscriberRegistry/apps/comp128 /OpenBTS
  151  cd NodeManager/
  152  ./nmcli.py sipauthserve subscribers create "iPhone 4" IMSI214057715229963 6055551234
  153  cd ..
  154  exit
  155  cd /OpenBTS-UMTS/
  156  cd NodeManager/
  157  ./nmcli.py sipauthserve subscribers create "iPhone 4" IMSI21405771529963 6055551234
  158  apt-get install build-essential debhelper pkg-config autoconf libtool libtool-bin libortp-dev libsqlite3-dev libusb-1.0-0-dev libreadline-dev libzmq3-dev libosip2-dev sqlite3 libusb-1.0-0 libortp-dev libc6 pkg-config libreadline6 libosip2-11 git
  159  apt-get install build-essential debhelper pkg-config autoconf libtool libtool-bin libortp-dev libsqlite3-dev libusb-1.0-0-dev libreadline-dev libzmq3-dev libosip2-dev sqlite3 libusb-1.0-0 libortp-dev libc6 pkg-config  libosip2-11 git
  160  ./nmcli.py sipauthserve subscribers create "iPhone 4" IMSI21405771529963 6055551234
  161  cat nmcli.py 
  162  ss -lntp | grep 45064
  163  apt install -y netcat
  164  nc -zv 127.0.0.1 45064
  165  ./nmcli.py sipauthserve subscribers create "iPhone 4" IMSI21405771529963 6055551234
  166  python2 nmcli.py sipauthserve subscribers create "iPhone 4" IMSI21405771529963 6055551234
  167  ./nmcli.py sipauthserve subscribers create "iPhone 4" IMSI21405771529963 6055551234
  168  cat nmcli.py 
  169  sed -i 's/socket.send(request)/socket.send_string(request)/g' nmcli.py
  170  sed -i 's/print ("raw response: " + response)/print("raw response: " + response.decode())/g' nmcli.py
  171  ./nmcli.py sipauthserve subscribers create "iPhone 4" IMSI21405771529963 6055551234
  172  clear
  173  ./nmcli.py sipauthserve subscribers create "iPhone 4" IMSI21405771529963 6055551234
  174  sqlite3 /etc/OpenBTS-UMTS/OpenBTS-UMTS.db
  175  ./nmcli.py sipauthserve subscribers read
  176  history
root@openbts-umts:/OpenBTS-UMTS/NodeManager# 
