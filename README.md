# HelloDocker
Start Docker with Linux

---
##도커 설치하기

자동 설치 스크립트

    curl -fsSL https://get.docker.com/ | sudo sh

만약 아래와 같은 오류가 뜬다면

    [sudo] password for sungtak: 
    # Executing docker install script, commit: 26ff363bcf3b3f5a00498ac43694bf1c7d9ce16c
    + sh -c apt-get update -qq >/dev/null
    + sh -c DEBIAN_FRONTEND=noninteractive apt-get install -y -qq apt-transport-https ca-certificates curl >/dev/null
    E: Could not get lock /var/lib/dpkg/lock-frontend - open (11: Resource temporarily unavailable)
    E: Unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend), is another process using it?

우선 터미널을 열고 모든 프로세스를 죽여본다.

    sudo killall apt apt-get

만일 아래처럼 진행 중인 프로세스가 없다라고 뜨면

    apt: no process found
    apt-get: no process found

 아래와 같이 하나씩 디렉토리를 삭제한다.

    sudo rm /var/lib/apt/lists/lock 
    sudo rm /var/cache/apt/archives/lock 
    sudo rm /var/lib/dpkg/lock*

모두 삭제하였다면

    sudo dpkg --configure -a
    sudo apt update

로 마무리하면 된다.