#유닉스 


# 리눅스
- 유닉스를 기반으로 만들어진 운영 체제

 Ubuntu, Red hat, CentOS, Debian 이런 운영 체제들이 다 Linux를 변형해서 만들어진 OS들이다.


# WSL VS Ubuntu 
WSL: windows 내에서 동작하는 Ubuntu CLI (Ubuntu CLI running within Windows)

------------------------------------

pwd (print working directory)
cd(change directory) 
ls(list files) 
----------------------------------------

yuna@yunajoe:~$ pwd  # 현재 디렉토리 경로 
/home/yuna
yuna@yunajoe:~$ cd /  # root 디렉토리로 이동
yuna@yunajoe:/$ pwd
/
yuna@yunajoe:/$ cd  # home 디렉토리로 이동
yuna@yunajoe:~$ pwd
/home/yuna
yuna@yunajoe:~$ cd - # root 디렉토리로 이동
/
yuna@yunajoe:/$ ls  # root 디렉토리 안에 있는 flie들 보기
bin  boot  dev  etc  home  init  lib  lib64  media  mnt  opt  proc  root  run  sbin  snap  srv  sys  tmp  usr  var
yuna@yunajoe:/$ ls home  # home 디렉토리 안에 있는 flie들 보기
yuna
yuna@yunajoe:/$ ls lib  # lib 디렉토리 안에 있는 flie들 보기
apparmor       hdparm                                lsb             open-iscsi     ufw
console-setup  init                                  modprobe.d      recovery-mode  x86_64-linux-gnu
cpp            klibc-IYXwqr0atR70aQDgNUuRThfwUwA.so  modules         systemd
cryptsetup     libhandle.so.1                        modules-load.d  terminfo
ebtables       libhandle.so.1.0.3                    netplan         udev

-----------------------------------------------------------------------------------
# 절대경로 
- root 디렉토리를 기준으로 어떤 파일이나 디렉토리의 고유한 경로를 표시하는 것 

# 상대경로 
- 현재 자신 위치를 기준으로 경로를 나타내기 
-  . 현재 디렉토리  .. 상위디렉토리 


yuna@yunajoe:~$ cd django/project
yuna@yunajoe:~/django/project$ ls
django_env  myproject
yuna@yunajoe:~/django/project$ cd ..
yuna@yunajoe:~/django$ ls
project
yuna@yunajoe:~/django$ cd project
yuna@yunajoe:~/django/project$ ls
django_env  myproject
yuna@yunajoe:~/django/project$ cd myproject
yuna@yunajoe:~/django/project/myproject$ ls
db.sqlite3  manage.py  mindnote  myproject  users
yuna@yunajoe:~/django/project/myproject$ cd ../../  # 상위 디렉토리로 두번가기 
yuna@yunajoe:~/django$ cd project/myproject
yuna@yunajoe:~/django/project/myproject$ cd ~/django   #  ' ~ ' 은 홈디렉토리 
yuna@yunajoe:~/django$ pwd
/home/yuna/django
yuna@yunajoe:~/django$
-----------------------------------------------------

# 파일이나 디렉토리 이름에 공백이 있을 경우

'' 나 "" 나 역슬래시(\) 를 사용한다 

yuna@yunajoe:~$ cd Hello world
-bash: cd: too many arguments
yuna@yunajoe:~$ cd 'Hello world'
yuna@yunajoe:~/Hello world$ cd
yuna@yunajoe:~$ cd "Hello world"
yuna@yunajoe:~/Hello world$
yuna@yunajoe:~$ cd Hello\ world
yuna@yunajoe:~/Hello world$


-----------------------------------------------------------------

# bin 
- bin은 'binaries'의 약자인데요. binary는 간단히 말해서 컴퓨터가 실행할 수 있는 프로그램을 뜻합니다
yuna@yunajoe:/$ ls bin

# sbin
- sbin은 bin과 비슷한데, 관리자 전용 프로그램

# etc
-  컴퓨터 설정 파일들이 있는데요. 각종 프로그램의 설정 파일, 관리자 권한 설정 파일 

# users
- usr은 사용자(user)에게 필요한 파일들을 저장

-  /bin에는 컴퓨터가 시작하거나 자신을 수리하기 위해서 꼭 필요한 커맨드
- /usr/bin에는 컴퓨터가 필요하기보다는 사용자가 필요한 커맨드

--------------------------------------------------------------------------

. 디렉토리와 파일 만들기: mkdir, touch

yuna@yunajoe:~$ mkdir linux_practice  # 폴더 만들기 
yuna@yunajoe:~$ ls
'Hello world'   June   django   linux_practice   python_env

yuna@yunajoe:~$ cd linux_practice
yuna@yunajoe:~/linux_practice$ mkdir May June  # 한번에 2가지 폴더 만들기
yuna@yunajoe:~/linux_practice$ ls
June  May

yuna@yunajoe:~/linux_practice$ cd May
yuna@yunajoe:~/linux_practice/May$ touch ex1.txt ex2.txt
yuna@yunajoe:~/linux_practice/May$ ls
ex1.txt  ex2.txt

yuna@yunajoe:~/linux_practice/May$ cd ..
yuna@yunajoe:~/linux_practice$ ls
June  May
yuna@yunajoe:~/linux_practice$ touch June/ex1.txt June/ex2.txt
yuna@yunajoe:~/linux_practice$ cd June
yuna@yunajoe:~/linux_practice/June$ ls
ex1.txt  ex2.txt

----------------------------------------------------------------

