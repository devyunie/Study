
![[Nn38tvd5-wallha.com.jpg]]
### Study Group:  리눅스 (Bash) 관련 명령어 및 리눅스 자료 & 제작자 하명윤
---
# Linux란 무엇인가?

- Linux는 1991년 Linus Torvals가 개발한 운영체제이다. Linux는 Unix 운영체제를 기반으로 만들어진 운영체제로 유닉스 클론 운영체제라 할 수 있다.Unix와 마찬가지로 다중 사용자, 다중작업 다중 스레드를 지원하는 네트워크 운영체제를 의미한다.  

- Unix가 애초부터 통신 네트워크를 지향해 설계된 것 처럼 Linux 역시 서버로 작동하는데 최적화 되어있다. 또한 Linux는 자유 소프트 라이센스로 누구나 소스코드를 활용, 수정 및 재 배포가 가능해서 지속적인 업그레이드가 이루어진다.
---
# Bash란 무엇인가
## 리눅스의 구조

![[Pasted image 20241118024215.png]]

> **Bourne-agin shell** 을 줄여서 Bash라고 부른다.
> **Unix 계열 운영체제에서 사용되는 명령 줄 인터페이스(Command Line Interface, CLI)를 위한 쉘**
## 커널(Kernal)이란?

- 운영체제의 핵심이 시스템 프로그램이다. 
- 각종 프로그램이 실행될 때, 모든 단계를 통제하고 중요한 처리를 하는 프로그램이다. 
- 우리는 이 부분을 코어, 리눅스라고도 부른다. 
- 사람이 쉽게 알 수 있는 구조로 되어있지 않기 때문에 쉽게 접근할 수 없다. 
- 사용자가 커널에 접근할 수 있도록 놓여진 다리의 역할을 shell이 수행하게 된다.
---
##  shell이란?

-  쉘은 운영 체제 상에서 다양한 운영 체제 기능과 서비스를 구현하는 인터페이스를 제공하는 프로그램
- 커널과 사용자를 이어주는 다리의 역할을 한다.
- 사용자는 커널에 직접 접근할 수 없기 때문에 쉘의 도움을 받아서 리눅스에서 제공하는 다양한 기능을 활용한다. 
- 사용자로부터 명령어를 입력받으면 그 명령어를 커널에 전달하여 처리해준다. 
- 쉘은 일반적으로 CLI형(명령줄 인터페이스) 과 GUI형(그래픽 인터페이스)으로 나뉜다.
---
# 리눅스의 계열 및 종류

1.  레드햇 계열: 레드햇 계열은 주로 기업 및 상용 시장을 대상으로 설계되었습니다. 이 계열은 기업 환경에서의 안정성과 신뢰성을 강조하며, 높은 수준의 기업 지원 및 서비스를 제공합니다. 또한, 상용 소프트웨어에 대한 통합과 호환성에 중점을 둡니다. 가장 유명한 레드햇 계열 배포판은 Red Hat Enterprise Linux (RHEL)입니다.  
   - 레드햇 계열: Fedora, RHEL (Red Hat Enterprise Linux), CentOS 등

2. 데비안 계열: 데비안 계열은 커뮤니티 중심의 개방형 프로젝트로서 설계되었습니다. 이 계열은 자유 소프트웨어 및 개방형 소스 개발 원칙을 중시하며, 커뮤니티 기반의 개발과 관리를 강조합니다. 데비안은 사용자의 자율성과 선택의 폭을 중요시하며, 소프트웨어 패키지의 안정성과 보안에도 주의를 기울입니다. 가장 유명한 데비안 계열 배포판은 Debian GNU/Linux입니다.
   - 데비안 계열: Debian GNU/Linux, Ubuntu, Linux Mint 등
---
#  기초 명령어
## 1.  ls

> List => Abbreviation : ls
> Windows 명령 프롬프트에서 dir과 같은 역할
> 즉 해당 디렉터리(폴더)에 있는 파일의 목록을 나열 하는 명령어
##### `ls [옵션][경로명]`
```bash
# ls -> 현대 디렉터리리의 파일 목록을 표시
Applications (Parallels) Downloads                Music                Public
Desktop                  IdeaProjects             Parallels            dump.rdb
Dev                      Library                  Pictures
Documents                Movies                   Postman
```

```bash
# ls /etc/ssh -> 디렉터리의 목록을 표시
crypto        crypto.conf   moduli        ssh_config    ssh_config.d  sshd_config   sshd_config.d
```

```bash
# ls -a -> 현재 디렉토리의 목록(숨긴 파일 포함)을 표시
.      ..     .test1 .test2 test3  test4
```

```bash
# ls -l -> 현재 디렉터리의 목록을 자세히 표시
total 0
-rw-r--r--@ 1 devyunie  staff  0 11 17 22:06 test3
-rw-r--r--@ 1 devyunie  staff  0 11 17 22:06 test4
```

```bash
# ls -al -> 현재 디렉토리의 목록(숨긴 파일 포함)을 자세히 표시
total 0
drwxr-xr-x@  6 devyunie  staff   192 11 17 22:06 .
drwx------+ 50 devyunie  staff  1600 11 17 22:05 ..
-rw-r--r--@  1 devyunie  staff     0 11 17 22:05 .test1
-rw-r--r--@  1 devyunie  staff     0 11 17 22:06 .test2
-rw-r--r--@  1 devyunie  staff     0 11 17 22:06 test3
-rw-r--r--@  1 devyunie  staff     0 11 17 22:06 test4
drwxr-xr-x@  2 devyunie  staff    64 11 17 22:14 testdirectory
--------------------------------------------------------------
total : 사용하고 있는 블럭의 크기 -> 1블럭당 1024 Byte
rwx : 파일 권한 r: 읽기 w: 쓰기 x: 실행
1, 2, 50 : 안에 있는 파일 갯수
devyunie : 사용자
staff : 사용그룹
1600, 64 : 파일 크기 -> byte단위
11 17 22:06 : 날짜
test3 : 파일명

.[파일명] => 숨긴 파일이라는 뜻
```
---
## 2.  cd

> Change Directory => Abbreviation : cd
> 디렉터리를 이동하는 명령입니다.
##### `cd [상대경로|절대경로][경로명]`

```bash
# cd / -> 루트 디렉토리로 이동
```

```bash
# cd ~ -> 현재 사용자의 홈디렉토리로 이동
```

```bash
# cd .. -> 바로 상위 디렉토리로 이동 '..'은 현재 디렉토리의 부모 디렉토리 의미
```

```bash
# cd /etc/ssh -> /etc/ssh 디렉토리로 이동 [절대경로]
```

```bash
# cd ../etc/ssh -> 상대 경로 이동
```
---
## 3. pwd

> Print Working Directory => Abbreviation : pwd
> 현재 디렉터리의 전체 경로를 화면에 표시 [절대경로]
##### `pwd`
```bash
# pwd
/Users/devyunie/Downloads/test
```
---
## 4. rm

> Remove => Abbreviation : rm
> 파일이나 디렉터리를 삭제합니다. 
> 파일이나 디렉터리를 삭제할 권한이 있어야 해당 명령을 실행할 수 있습니다
> root 사용자는 모든 권한이 있으므로 rm 명령 사용에 제약이 없습니다. (Administrator)
##### `rm [옵션] 파일명|디렉토리명`
```bash
# rm test -> 해당 파일을 삭제
```

```bash
# rm -i test -> 삭제 시 정말 삭제할 지 확인하는 메시지를 표시
remove test4? yes | no
```

```bash
# rm -f test -> 삭제 시 확인하지 않고 바로 삭제 (f는 force의 약자)
```

```bash
# rm -r test ->해당 디렉토리를 삭제 (r은 Recursive의 약자
```

```bash
#rm -rf test -> r옵션과 f옵션을 합친 것으로 test 디렉터리의 그 아래에 있는 하위 디렉터리를 강제로 전부 삭제
```
---
## 5. cp

> copy => Abbreviation : cp
>  파일이나 디렉터리를 복사합니다.
>  새로 복사한 파일은 복사한 사용자의 소유가 됩니다.
>  명령을 실행하는 사용자는 해당 파일의 읽기 권한이 필요합니다.
##### `cp [옵션] 원본대상 [파일명|경로]`
```bash
# cp test1.txt test2.txt -> test1.txt를 test2.txt라는 이름으로 변경하여 복사
```

```bash
# cp -r testD1 testD2 -> 디렉토리 복사
```
---
## 6. touch

> 크기가 0인 새 파일을 생성하거나 생성된 파일이 존재한다면 파일의 최종 수정 시간을 변경합니다.
##### `touch [옵션] 파일명`
```bash
# touch abc.txt -> 파일이 없는 경우 abc.txt라는 빈 파일을 생성 abc.txt파일이 있는 경우 최종 수정 시간을 현재 시간으로 변경
```
----
## 7. mv

> Move => Abbreviation : mv
> 파일이나 디렉터리의 이름을 변경하거나 다른 디렉터리로 옮길 때 사용합니다.
#####  `mv [옵션] 원본대상 [파일명|경로]`
```bash
# mv test.txt /etc -> test.txt을 /etc 디렉터리로 이동
```

```bash
# mv aaa bbb ccc /etc -> aaa, bbb, ccc 파일을 /etc 디렉터리 이동
```

```bash
# mv test.txt ests.txt -> test.txt이름을 ests.txt로 이름을 변경해서 이동
```
---
## 8. mkdir

> Make Directory => Abbreviation : mkdir
> 새로운 디렉터리를 생성합니다.
> 생성된 디렉터리는 명령을 실행한 사용자의 소유가 됩니다.
#####  `mkdir [옵션] 디렉터리명`
```bash
# mkdir abc -> 현재 디렉터리 아래에 /abc이름의 디렉토리 생성
```

```bash
# mkdir -p /def/fgh -> /def/fgh 디렉토리 생성 /def디렉토리가 없다면 자동 생성
```
---
## 9. rmdir

> Remove Directory => Abbreviation : rmdir
> 디렉터리를 삭제합니다. 
> 해당 디렉터리의 삭제 권한이 있어야 하며 디렉터리는 비어 있어야 합니다.
> 파일이 있는 디렉터리를 삭제하려면 rm -r 명령을 실행해야 합니다.
#####  `rmdir [옵션] 디렉터리명`
```bash
# rmdir abc -> /abc이름의 디렉토리 삭제
```
---
## 10.  cat

> Concatenate => Abbreviation : cat
> 파일 내용을 화면에 출력합니다.
> 여러 파일을 나열하면 파일을 연결해서 출력합니다.
##### `cat [옵션] 파일명`
```bash
# cat a.txt    → a.txt 파일의 내용을 화면에 출력
1
2
3
4
5
...
```

```bash
# cat -n a.txt -> 비어있는 행 포함 해서 파일의 내용을 출력
1	1
2	2
3	3
4	4
5	5
6	6
7	7
8	8
9	9
10	10
```
---
## 11.  head , tall

>텍스트 형식으로 작성된 파일의 앞 10행 또는 마지막 10행만 화면에 출력합니다.
##### `head|tail [옵션] 파일명`
```bash
# head a.txt -> 해당 파일의 앞 10행을 화면에 출력
1	1
2	2
3	3
4	4
5	5
6	6
7	7
8	8
9	9
10	10
```

```bash
# head -3 a.txt
1
2
3
```

```bash
# tail -5 a.txt      → 마지막 5행만 화면에 출력
16
17
18
19
20
```

```bash
# tail -f -> 실시간 입력되는 결과 보기
```

---
## 12. more

>텍스트 형식으로 작성된 파일을 페이지 단위로 화면에 출력합니다. 
>[Space]를 누르면 다음 페이지로 이동하며, 
>[B]를 누르면 앞 페이지로 이동합니다. 
>[Q]를 누르면 명령을 종료합니다.
##### `more [옵션] 파일명`
```bash
# more a.txt
```

```bash
# more +30 a.txt    → 30행부터 출력
```
---
## 13. clear

>현재 사용 중인 터미널 화면을 깨끗하게 지웁니다.
```bash
# clear
```
---
## 14. who

> 현재 시스템에 접속해 있는 사용자들을 조회하는 명령어
> 사용자 계정명 터미널 정보 접속시간, 접속한 서버 등 조회 가능
> 명령어 who am i || whoami 는 자신의 정보를 조회 가능

```bash
#who -> 시스템에 접속해 있는 사용자들의 조회
devyunie         console      11 13 12:33
devyunie         ttys000      11 18 09:36
```

```bash
#whoami -> 자신의 정보
devyunie
```

```bash
#who am i-> 자신의 정보 자세히 보기
devyunie         ttys000      11 18 09:36
```

>/etc/passwd : 계정 정보가 모여있는 파일

```bash
# cat /etc/passwd
parallels:x:1000:1000:parallels:/home/parallels:/bin/bash
----------------------------------------------------------
parallels : 계정명 | 로그인 이름
x : 사용자 패스워드 -> 암호화로 인해 /etc/shadow에 저장
1000 : 사용자 ID로 특정 사용자를 나타내는 숫자로된 ID (UID : User Id)
1000 : 기본 그룹 ID로 사용자가 소속된 그룹을 나타내는 숫자로 된 ID(GID : Group ID)
parallels : 사용자 기타 정보
/home/parallels : 로그인에 성공한 후에 사용자가 위치할 홈 디렉토리 명
/bin/bash : 명령어를 처리하는 쉘의 종류
```

---
## 15. w

> 현재 접속 중인 사용자들의 정보를 나타내는 명령어
> 서버의 현재 시간 정보
> 서버 부팅후 시스템 작동 시간
> 서버 접속자의 총 수
> 접속자별 서버 평균 부하율
> 접속자별 서버 접속 계정명
> tty명
> 로그인 시간 정보 등

```bash
# w -> 현재 접속중인 사용자들의 정보 조회
 9:44  up 4 days, 21:14, 4 users, load averages: 3.14 2.70 2.91
USER       TTY      FROM           LOGIN@  IDLE WHAT
devyunie   console  -             수12%.*s 4days -
devyunie   s000     -              9:36       - w
devyunie   s001     192.168.7.47   9:43       - ssh 192.168.7.47
devyunie   s002     192.168.7.47   9:44       - -zsh
```
---
## 16. passwd

>생성된 계정자의 패스워드를 입력 및 변경하는 명령어
##### `passwd [계정명]`
```bash
# passwd parallels -> parallels 계정의 비밀번호를 변경
New password:[비밀번호 같은 경우는 보안을 위해 안 보이게 되어있다 입력하면 입력이 된다.]
BAD PASSWORD: The password is shorter than 8 characters
Retype new password:
passwd: password updated successfully
```

> /etc/shadow : 사용자 계정에 따른 비밀번호 암호화 문서

```bash
# cat /etc/shadow -> root관리자 권한일때만 열람 가능
parallels:$y$j9T$LKKe.8vz5xcTsQjiF6fi70$IosLlK0.4wERMs8nT..sJJ3CyvEVggT6frZwZIglGH0:20039:0:99999:7:::
root:$y$j9T$EG4WoZaQJO074p44RptP81$W86CmFBo/D3QkaOtdqbUMKpWIpLtgYxEfQU2U8zF001:20040:0:99999:7:::
```
---
## 16. su

>  Switch user => Abbreviation : su
>  현재의 사용자 계정에서 로그아웃하지 않고 다른 사용자 계정으로 로그인하여 해당 사용자의 권한을 획득하는 명령어
##### `su [옵션] [사용자] [셀변수]`
```bash
# su root -> root 계정으로 변경
Password:
root@ubuntu-linux-2404:/home/parallels#
```
---
## 17. sudo

> substitute user do => Abbreviation : su 
> superuser do => Abbreviation : su 
> 유닉스 리눅스 계열 OS에서 관리자 권한으로 실행 할수 있게 하는 명령어
##### `sudo [명령어]`
```bash
# sudo systemctl start openssh -> 관리자 권한으로 ssh 서버 실행
```
---
## 18. alias

>명령어를 간소화하여 다른 이름으로 사용할 수 있도록 해주는 쉘내부 명령어
>별칭
##### `alias [단축 명령어]=['원래 명령어']`
```bash
#alias -> 현재 등록되어 있는 모든 alias 출력
alias egrep='egrep --color=auto'
alias fgrep='fgrep --color=auto'
alias grep='grep --color=auto'
alias l='ls -CF'
alias la='ls -A'
alias ll='ls -alF'
alias ls='ls --color=auto'
```

```bash
# alias ll='ls -l' ->ls -l을 ll로만 쳐도 실행될 수 있게 별칠 설정

⚠️ alias 같은 경우 ll = 'ls -l'이런식으로 입력할 경우 오류가 발행
alias같은 경우 따로 셋팅을 해주지 않는 경우 컴퓨터 종료 또는 재시작시 셋팅하지 않은 alias는 삭제됨
```

```bash
#unalias ll -> 별칭 삭제
```
### 18-1 alias 셋팅

> ~/.bashrc -> [.bashrc는 bash관련 쉘 설정파일 , zsh 같은 경우는 .zshrc]

```bash
# sudo vi ~/.bashrc
 80 # some more ls aliases
 81 alias ll='ls -alF'
 82 alias la='ls -A'
 83 alias l='ls -CF'
 84 alias lsl='ls -l' -> 해당 부분 처럼 작성 해주시면 됩니다.
```
---
## 19. Pipe

> 터미널은 하나의 프로세스 이고 ,명령어 실행은 해당 터미널의 정보를 기준으로 백그라운드에 자식 프로세스가 fork되어 명령어를 실행하게 됩니다
> 즉 터미널에서 'ls'라는 명령어를 입력하면, 자식 프로세스 1개가 fork 되어 백그라운드에서 부모프로세스의 정보를 기준으로 명령어 즉, stdin을 통해 정보를 입력받고 stdout을 통해 ls 명령어를 호출한 터미널로 정보를 반환하는 식으로 동작 합니다

- fork : 현재 프로세스에 대해 자식 프로세스를 생성하는 함수

리눅스 쉘은 항상 아래와 같이 표준 입출력을 파일 형태로 열고 있다.
- 표준 입력 (stdin: 키보드) -> 파일 디스크립터 0
- 표준 출련 (stdout: 모니터) -> 파일 디스크립터 1
- 표준 에러 (stderr: 모니터) -> 파일 디스크립터 2

pipe의 재지향
- 프로그램은 연산 결과를 출력 장치(파일, 모니터, 프린터 등)로 내보내는데 이 출력되는 데이터를 임의로 다른 장치로 보내는 것을 재지향

pipe의 구조
첫 번째 명령어 파이프의 결과를 화면으로 출력하는 대신 다른 파이프로 흘러가도록 연결한다고 생각
![[12.png]]

2가지 명령어가 흐르는 명령어 파이프가 있다고 가정
 - 필터링 하는 명령어 파이프에 | 를 통해서 연결하면 화면에 출력되는 최종 결과는 필터링을 걸친 결과가 출력
![[1222.png]]
```bash
#ls -l -> 디렉터리안에 해당 파일이 있다고 가정
-rw-r--r-- 1 root root 0 Nov 18 14:06 test1
-rw-r--r-- 1 root root 0 Nov 18 14:06 test2
-rw-r--r-- 1 root root 0 Nov 18 14:06 test3
-rw-r--r-- 1 root root 0 Nov 18 14:06 test4
-rw-r--r-- 1 root root 0 Nov 18 14:07 touch1
-rw-r--r-- 1 root root 0 Nov 18 14:07 touch2
# ls -l | grep touch -> grep을 통해 touch가 들어가는 파일의 목록만 필터링 하여 출력
-rw-r--r-- 1 root root 0 Nov 18 14:07 touch1
-rw-r--r-- 1 root root 0 Nov 18 14:07 touch2
```
---
## 20. grap

>특정 파일에서 지정한 문자열이나 정규표현식을 포함한 행을 출력해주는 명령어입니다.
> tail이나 ls 등 다양한 명령어와 조합하여 응용
##### `grep [옵션][패턴][파일명]`
```bash
# grep error 파일명 -> 특정 파일에서 'error' 문자열 찾기
# grep error -> 해당 문자열이 들어간 파일 찾기
```

---
# 권한 명령어
## 1. chmod

>파일이나 디렉터리의 접근 허가권을 변경하는 명령어
##### `chmod [옵션] 파일명]
```
chmod 777 a -> a 디렉토리에 모든 권한을 부여
```

숫자별 권한 부여 표

| 기호  | 숫자 (2진수) | 숫자() |    의미    |
| :-: | :------: | :--: | :------: |
| rwx |   111    |  7   | 읽기 쓰기 실행 |
| rw- |   110    |  6   |  읽기 쓰기   |
| r-x |   101    |  5   |  읽기 실행   |
| r-- |   100    |  4   |    읽기    |
| -wx |   011    |  3   |  쓰기 실행   |
| -w- |   010    |  2   |    쓰기    |
| --x |   001    |  1   |    실행    |
| --- |   000    |  0   | 아무 권한 없음 |

## 2. umask

>새로 생성되는 파일이나 디렉토리의 기본 허가권 값을 지정
>파일의 기본 권한 : 666
>디렉터리의 기본 권한 : 777 
>umask의 기본 권한 : 022

파일이나 디렉토리 생성시 디폴트 권한 값에서 설정한 umask 값을 뺀 값을 기본 허가권(권한)으로 지정
**umask: 022 -> 파일 같은 경우 (666-022)를 한 644 -rw- r-- r-- 부여 
umask: 022 -> 디렉터리 같은 경우 (777-022)를 한 755 drwx r-x r-x 부여 

---
# Network
## 1. ping

> ICMP 프로토콜에서 제공하는 명령인 ECHO_REQUEST 데이터그램을 클라이언트에 전송하고 응답을 기다리고, 그 응답시간을 측정한다.
> 간단히 네트워크가 잘 연결되었는지 확인할 때 이용

```bash
# ping 127.0.0.1
PING 127.0.0.1 (127.0.0.1): 56 data bytes
64 bytes from 127.0.0.1: icmp_seq=0 ttl=64 time=0.167 ms
64 bytes from 127.0.0.1: icmp_seq=1 ttl=64 time=0.130 ms
64 bytes from 127.0.0.1: icmp_seq=2 ttl=64 time=0.127 ms
64 bytes from 127.0.0.1: icmp_seq=3 ttl=64 time=0.254 ms
64 bytes from 127.0.0.1: icmp_seq=4 ttl=64 time=0.181 ms
64 bytes from 127.0.0.1: icmp_seq=5 ttl=64 time=0.176 ms
^C
--- 127.0.0.1 ping statistics ---
6 packets transmitted, 6 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 0.127/0.172/0.254/0.042 ms

127.0.0.1은 자신 네트워크 즉 localhost를 의미

만약 응답이 없을 경우 해당 요청 처럼 Request timeout이 발생
PING 192.168.0.158 (192.168.0.158): 56 data bytes
Request timeout for icmp_seq 0
Request timeout for icmp_seq 1
Request timeout for icmp_seq 2
Request timeout for icmp_seq 3
Request timeout for icmp_seq 4
Request timeout for icmp_seq 5
^C
--- 192.168.0.158 ping statistics ---
7 packets transmitted, 0 packets received, 100.0% packet loss
```
---
## 2. losf

>시스템에서 열려있는 파일에 대한 정보를 출력해주는 명령어
>일반파일, 디렉토리 ,소켓, 파이프, 블록 디바이스, 캐릭터 디바이스에 대한 관리를 파일 파일 시스템을 통해서 모니터링 가능

```bash
# lsof -PiTCP -sTCP:LISTEN  -> 현재 열린 포트 목록
COMMAND     PID     USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
mongod      979 devyunie    9u  IPv4 0x56857d90061ed1cc      0t0  TCP localhost:27017 (LISTEN)
mongod      979 devyunie   10u  IPv6 0x98dc60c45437b808      0t0  TCP localhost:27017 (LISTEN)
com.docke  1900 devyunie   13u  IPv6 0x4e7ca656f12f3359      0t0  TCP *:6379 (LISTEN)
mysqld     5352 devyunie   19u  IPv4 0x83e1913e5f3e2846      0t0  TCP localhost:33060 (LISTEN)
mysqld     5352 devyunie   21u  IPv4  0x49dc7a4629aad6a      0t0  TCP localhost:3306 (LISTEN)
Cursor    33026 devyunie   38u  IPv4 0xb16b518d2ef2c466      0t0  TCP localhost:8831 (LISTEN)
Cursor    69376 devyunie   33u  IPv4 0xa57f37576079d20f      0t0  TCP localhost:8829 (LISTEN)
Cursor    71586 devyunie   51u  IPv4 0x3bee93ba353639c2      0t0  TCP localhost:8828 (LISTEN)
java      71650 devyunie   86u  IPv6 0x26967814a8f2145c      0t0  TCP *:55770 (LISTEN)
java      71821 devyunie   22u  IPv6 0xaca919e9395c5817      0t0  TCP hamyeong-yun-ui-macbookpro.local:55773 (LISTEN)
java      71821 devyunie  239u  IPv6 0x85d49b2e30683853      0t0  TCP localhost:55788 (LISTEN)
java      71821 devyunie  495u  IPv6 0x7018a83390c96cef      0t0  TCP localhost:55790 (LISTEN)
```

```bash
# lsof -i :5352 -> 특정 포트를 찾아 포트를 닫고 싶으면 다음과 같이 쳐서 PID를 알아낸다.
COMMAND     PID     USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
mysqld     5352 devyunie   21u  IPv4  0x49dc7a4629aad6a      0t0  TCP localhost:mysql (LISTEN)

PID : 프로세스 아이디
```

```bash
# kill -9 5352 -> PID를 입력하면 해당 포드가 닫힌다
```
---
## 4. Systemctl

> 서비스 시작 및 중지 관련 리눅스 명령어 (system control)
##### `systemctl [옵션] [서비스명]`
```bash
# systemctl start docker -> 해당 서비스 실행
start: 실행
stop: 종료
reload: 재실행
enable:자동 실행
```

```bash
# systemctl status ssh ->  상태 및 정보 보여주기
 ssh.service - OpenBSD Secure Shell server
     Loaded: loaded (/usr/lib/systemd/system/ssh.service; disabled; preset: ena>
     Active: active (running) since Wed 2024-11-13 12:05:52 KST; 4 days ago
TriggeredBy: ● ssh.socket
       Docs: man:sshd(8)
             man:sshd_config(5)
   Main PID: 31023 (sshd)
      Tasks: 1 (limit: 2206)
     Memory: 2.6M (peak: 19.2M)
        CPU: 275ms
     CGroup: /system.slice/ssh.service
             └─31023 "sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 start

Active: running : 실행중 | dead :종료
```
---
## 5. ifconfig

>네트워크 인터페이스 및 아이피 보여주는 명령어
>Windows에서는 ipconfig와 동일

```bash
# ifconfig
enp0s5: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.211.55.3  netmask 255.255.255.0  broadcast 10.211.55.255
        inet6 fdb2:2c26:f4e4:0:24d2:dcec:f537:358b  prefixlen 64  scopeid 0x0<gl

enp0s5 : 네트워크 인터페이스 이름
inet : 할당된 아이피 주소
netmask : 할당된 넷마스크 주소
```
---
## 6. ssh

>ssh란 Secure Shell Protocol, 즉 네트워크 프로토콜 중 하나
> 컴퓨터와 컴퓨터가 인터넷과 같은 Public Network를 통해 서로 통신을 할 때 보안적으로 안전하게 통신을 하기 위해 사용하는 프로토콜입니다
> SSH를 사용하기 위해서는 해당 접속하고자 하는 컴퓨터에 SSH가 설치되어있고 서비스가 실행되어있어야한다
> 리눅스 같은경우는 root권한으로 접속하고자 할 경우 /etc/ssh/sshd_config 파일을 수정 해주어야 한다.

```bash
# ssh [계정명]@[아이피 주소]
# ssh root@192.168.0.156
```

### 6-1 /etc/ssh/sshd_config

**PermitRootLogin** : root 사용자의 로그인 허용 여부. (yes, prohibit-password, forced-commands-only, no) 중에서 설정해야 합니다. 설정하지 않으면 prohibit-password 가 됩니다.  yes 로 설정하세요.
-  방법
1. root password 설정
```bash
# sudo passwd root
```
2. sshd_config 창을 수정
```bash
# vi /etc/ssh/sshd_config
 32 #LoginGraceTime 2m
 33 PermitRootLogin yes -> 해당 설정을 yes로 설정
 34 #StrictModes yes
 35 #MaxAuthTries 6
 36 #MaxSessions 10
```
3. ssh service 재실행
```bash
# sudo systemctl restart ssh
```
---
# 패키지 설치

  - 레드햇 계열: 레드햇 계열은 RPM (Red Hat Package Manager)을 주로 사용합니다. RPM은 소프트웨어 패키지의 설치, 업그레이드, 제거 등을 관리하는 도구입니다. 가장 유명한 레드햇 계열 배포판인 RHEL은 yum (Yellowdog Updater, Modified)이나 dnf (Dandified Yum)과 같은 패키지 관리 도구를 사용합니다.  
  
  - 데비안 계열: 데비안 계열은 dpkg (Debian Package)를 주로 사용합니다. dpkg는 소프트웨어 패키지의 설치, 업그레이드, 제거 등을 관리하는 도구입니다. 데비안 계열 배포은 apt (Advanced Package Tool)를 사용하여 패키지 관리를 쉽게 할 수 있도록 지원합니다.
#### Red Hat 계력 Yum 사용법
```bash
# yum insall [package] -> 시스템으로 패키지의 install을 실시
# yum install [package-name1] [package-name2] -> package1 , package2번을 샅이 설치
# yum reinstall [package] -> 패키지 재인스톨
# yum remove [package] -> 패키지 삭제
# yum list -> 서버에 있는 그룹 및 패키지의 리스트를 보여줌
# yum upgrade [package] -> 해당 패키지 업데이트
# yum update [package] -> 패키지 업데이트
```
#### Debian 계력 apt 사용법  [apt-get 의 최신 버전이 apt]
```bash
# apt insall [package] -> 시스템으로 패키지의 install을 실시
# apt install [package-name1] [package-name2] -> package1 , package2번을 샅이 설치
# apt reinstall [package] -> 패키지 재인스톨
# apt remove [package] -> 패키지 삭제
# apt list -> 서버에 있는 그룹 및 패키지의 리스트를 보여줌
# apt upgrade -> 전체 패키지를 업그레이드한다. [package]를 붙일 경우 해당 패키지 업그레이드
# apt update -> 패키지를 다운로드할 수 있는 저장소의 최신 정보를 업데이트한다. [package]를 붙일 경우 해당 패키지 업데이트
```
---
# vi 편집기 사용 방법

> vi editor 기본 구조
![[제목 없는 다이어그램.drawio.png]]
## 1. 명령 모드에서 편집 모드로 전환

|         | 키(Key) |       기능       |
| :-----: | :----: | :------------: |
| 입력모드 전환 |   a    |   커서 뒤에서 입력    |
| 입력모드 전환 |   A    |   줄의 마지막에 입력   |
| 입력모드 전환 |   i    |  현재 문자 앞에 입력   |
| 입력모드 전환 |   I    |  줄의 시작부분에 입력   |
| 입력모드 전환 |   o    | 현재 줄 다음 줄에 입력  |
| 입력모드 전환 |   p    | 커서가 있는 줄 위에 입력 |

## 2. EX명령 모드에서 저장 및 종료 ,  환경 설정

|             |  키(Key)   |      기능       |
| :---------: | :-------: | :-----------: |
|   저장 및 종료   |    :wq    |    저장하고 종료    |
| 저장 및 종료<br> |    :q!    | 저장하지 않고 바로 종료 |
|   저장 및 종료   |    :q     |      종료       |
|    환경 설정    |  :set nu  |    줄 번호 표시    |
|    환경 설정    | :set nonu | 줄 번호 표시 설정 해제 |

## 3.명령모드에서 삭제, 복사 ,붙여넣기

|      | 키(Key) |         기능          |
| :--: | :----: | :-----------------: |
|  삭제  |   x    | 커서가 위치한 곳의 한 문자 삭제  |
|  삭제  |   dd   |       한 라인 삭제       |
|  삭제  |   dw   | 커서 위치에서 오른쪽 한 단어 삭제 |
|  삭제  |   db   | 커서 위치에서 왼쪽 한 단어 삭제  |
|  복사  |   yy   |       한 라인 복사       |
|  복사  |   yw   | 커서 위치에서 오른쪽 한 단어 복사 |
|  복사  |   yb   | 커서 위치에서 왼쪽 한 단어 복사  |
| 붙여넣기 |   P    |  커서 위치에서 윗줄에 붙여넣기   |
| 붙여넣기 |   p    |  커서 위치에서 아랫줄에 붙여넣기  |

## 4.  vi 오류로 인한 강제 종료될 경우 SWAP파일 처리 방법

>해당 파일 수정 중 비 정상 종료 후 수정 할때 복구 및 처리 방법

해당 파일을 열 경우 아래와 같은 창이 떠오른다
- O : 읽기 전용으로 열기
- E : 그냥 고치기
- R : 복구
- Q : 끝내기
- D : 삭제
- A : 버리기

```
E325: ATTENTION
Found a swap file by the name ".1234.swp"
          owned by: root   dated: Mon Nov 18 11:50:40 2024
         file name: ~root/test/1234
          modified: YES
         user name: root   host name: ubuntu-linux-2404
        process ID: 83471
While opening file "1234"
      CANNOT BE FOUND
(1) Another program may be editing the same file.  If this is the case,
    be careful not to end up with two different instances of the same
    file when making changes.  Quit, or continue with caution.
(2) An edit session for this file crashed.
    If this is the case, use ":recover" or "vim -r 1234"
    to recover the changes (see ":help recovery").
    If you did this already, delete the swap file ".1234.swp"
    to avoid this message.

Swap file ".1234.swp" already exists!
[O]pen Read-Only, (E)dit anyway, (R)ecover, (D)elete it, (Q)uit, (A)bort:
```
1. R을 눌러 파일을 복구 한다
2. Enter을 눌러 복구를 실행한다
3. 저장하고 종료 :wq를 입력한다
4. ls -al을 입력한다
```bash
# ls -al 
-rw-r--r-- 1 root root    77 Nov 18 12:07 1234
-rw------- 1 root root 12288 Nov 18 11:50 .1234.swp
```
5. .1234.swp이라는 파일이 있는데 해당 파일이 swap파일이다 
    해당파일을 지워야만 위와 같은 swp이 생성되었을때 문구가 뜨지가 않는다.
6. rm -rf .1234.swp를 입력하여 해당 스왓파일을 삭제한다
```bash
# rm -rf .1234.swp
```

