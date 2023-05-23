# 스왑 파일을 사용하여 Amazon EC2 인스턴스에서 스왑 공간으로 사용할 메모리를 할당하는 방법

[참고자료 - 공식 블로그](https://repost.aws/ko/knowledge-center/ec2-memory-swap-file)

`스프링 부트와 AWS로 혼자 구현하는 웹 서비스` 책을 따라하던 도중 AWS 환경에서 SpringBoot 프로젝트를 Build 하다가 발생한 에러입니다.

> AWS EC2 free tier... > 램이 1GB정도 밖에 되지 않음. <br>
> 프로젝트 빌드 명령어 `./gradlew clean build -x test` 를 작성했을 때 무한 로딩 발생.

## 해결 과정
### 0. 현재 메모리 확인하기
```bash
$ free -h
```
![image](https://github.com/5jisoo/TIL/assets/96935231/4c5f5470-4910-4ede-8137-8265cfe2465d)

### 1. dd 명령어를 사용하여 루트 파일 시스템에 스왑 파일 생성하기
``` bash
$ sudo dd if=/dev/zero of=/swapfile bs=128M count=32
```

### 2. 스왑 파일의 읽기 및 쓰기 권한 업데이트
```bash
$ sudo chmod 600 /swapfile
```

### 3. Linux 스왑 영역 설정
```bash
$ sudo mkswap /swapfile
```

### 4. 스왑 공간에 스왑 파일을 추가하여 스왑 파일을 즉시 사용할 수 있도록 하기
```bash
$ sudo swapon /swapfile
```

### 5. 프로시저가 성공적인지 확인하기
```bash
$ sudo swapon -s
```

### 6. `/etc/fstab` 파일을 편집하여 부팅 시 스왑 파일을 시작하기
```bash
$ sudo vi /etc/fstab
```
파일 끝에 다음 줄 새로 추가하기
```
/swapfile swap swap defaults 0 0
```

## 결과
* 메모리 할당량 증가 <br>
![image](https://github.com/5jisoo/TIL/assets/96935231/d7ea3096-62fd-4646-befe-2ecc7a02fbd4)

* Build 성공! <br>
![image](https://github.com/5jisoo/TIL/assets/96935231/dd56db46-d014-47d0-9d18-517a7381a929)
