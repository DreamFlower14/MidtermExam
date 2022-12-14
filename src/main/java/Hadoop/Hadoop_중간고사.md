|    Date    |  Time   |
|:----------:|:-------:|
| 2022-10-06 | 오전 9:13 |

---

# 하둡 중간고사 예상 문제

**1. 하둡의 필수 구성요소 3가지를 작성하시오.**
```java
        1. 하둡 분산 파일 시스템 :
        2. 맵리듀스 : 
        3. 얀 :
 
        // 1장 60p
```

2. 호스트네임을 master로 변경하기 위한 명령어를 작성하시오.
```java
        hostnamectl set-hostname  호스트이름

        // hostname : 현재 호스트 이름 알려주는 명령어
        // 2장 38p
```

3. 하둡과 같이 자바를 기반으로 실행되는 프로세스들을 확인하는 명령어를 작성하시오.
```java
        Jps

        // 5장 9p
```

4. ifconfig 명령어를 사용하기 위한 데몬 설치 명령어를 작성하시오.
```java
        yum install -y net-tools

        // 2장 43p
```

5. SSH 프로토콜의 기본 포트는 몇 번인가?
```java
        22번 포트

        // 3장 7p
```

---
6. 현재 열린 포트를 확인하기 위한 명령어는 무엇인가?
```java
        netstat -ntlp | grep java

        // 4장 97p
```
![img_1.png](img/img_1.png)

7. CentOS 7의 8088번 포트의 외부 접속을 혀용하기 위한 방화벽 설정, 방화벽 재부팅, 방화벽 내용 확인 명령어를 작성하시오.
```java
        - 방화벽 설정 명령어 : firewall-cmd --permanent --zone=public --add-port=8088/tcp
        - 방화벽 재부팅 명령어 : firewall-cmd --reload
        - 방화벽 전체 내용 확인 명령어 : firewall-cmd --list-all

        // 4장 87p
```

**8. 생성된 SSH 키의 권한 설정 명령어를 작성하시오.**
```java
        chmod : 권한 설정 명령어 
        
        chmod 0600 ~/.ssh/authorized_keys : 나만 쓸 수 있게 권한 주기 chmod 숫자 옵션 좀 더 보자

        // 4장 29p
```


9. hadoop 계정의 sudo 권한을 부여하기 위해 수정하는 파일은 무엇인가?
```java
        /etc/sudoers

        // vi /etc/sudoers : 파일 수정 명령어
        // 4장 26p
```

10. 설치한 자바의 환경 설정하는 파일은 무엇이며, 설정 후 적용하기 위한 명령어는 무엇인가?
```java
        - 환경 설정 파일 :  /etc/profile
        - 적용 명령어 : source /etc/profile

        // 4장 41P
```
---
**11. 다음과 같은 폴더의 링크를 생성하기 위한 명령어를 작성하시오.**
 > - 현재 위치 : /
 > - 생성할 링크 위치 : /usr/local
 > - 링크명 : java
 > - 대상 폴더명 : /usr/local/jdk1.8
```java
        ln -s /usr/local/jdk1.8/ /usr/local/java

        // 4장 40P
```

12. jdk1.8.tar.gz 파일의 압축을 해제하는 명령어를 작성하시오.  
```java
        tar -zxvf jdk1.8.tar.gz

        // 4장 39P
```

13. 하둡의 네임노드를 포멧하기 위한 명령어를 작성하시오.
```java
        hdfs namenode -format

        // 4장 83p
```

**14. 하둡의 실행 관련 파일들이 존재하는 폴더는 무엇인가?**
 > - 하둡 설치 경로 : /usr/local/hadoop
```java
        /usr/local/hadoop/sbin

        // 4장 60p
```

**15. 하둡의 환경 설정 관련 파일들이 존재하는 폴더는 무엇인가?**
> - 하둡 설치 경로 : /usr/local/hadoop
```java
        /usr/local/hadoop/etc

        // 4장 59p
```

---
**16. hadoop 계정이 root 계정을 권한을 빌려와서 권한이 없는 파일을 실행, 수정하기 위한 명령어는 무엇인가?**
```java
       sudo 
```

17. hadoop 계정으로 접속된 상태에서 root 계정으로 접속하기 위한 명령어는 무엇인가?
```java
        su - root

        // 4장 83p 
```
![img.png](img/img.png)

**18. DHCP 에 대해 자세히 설명하시오.**
```java
        DHCP  : (동적 호스트 구성 프로토콜)
                IP 주소와 게이트웨이 또는 네임서버의 주소 등 다양한 네트워크 정보를 
                DHCP 서버가 pc와 같은 이용자 단말에게 자동으로 할당(임대)해주는 프로토콜
                **※ 영구적으로 주는 것이 아니라 임대하는 형태이다!!!!!!!!!!!!!!!!!!!!!!!**
        
        구조   : 3가지  
                임대 : 빌리고 빌린다. 
                갱신 : 호스트가 임대기간 더 늘려달라고 부탁한다.
                반환 : 다 쓰고 돌려준다.
        
        장단점 : 네트워크 관리를 클라이언트가 할 필요가 없어서 편하다는 장점이 있지만 
                서버에 의존하기 때문에 서버가 다운되면 IP 할당이 제대로 이루어지지 않는다.
        
        과정  : 4단계 
                1. DHCP Discover : 호스트가 DHCP 서버를 찾기위한 통신 - "거기 DHCP서버 있나요~~"
        
                2. DHCP Offer : DHCP 서버가 자신의 존재를 알리고 호스트에게 할당할 IP주소 정보를 포함한 네트워크 정보를 같이 알리는 통신
                - "네 저 여기 있어요  제 IP 주소는 0.0.0.0이구요 제가 호스트님께 0.0.0.1 아이피 주소를 임대해 드릴 수 있어요~"
        
                3. DHCP request : 호스트가 DHCP 서버에 호스트가 사용할 네트워크 정보 요청 하는 통신
                - "그럼 IP 주소 할당해주실래요? "
        
                4. DHCP Ack : DHCP가 호스트에게 네트워크 정보를 전달해주는 통신
                - "네 여기 IP 주소 있습니다 1시간동안 임대해드릴게요~"
                
```
![img_2.png](img/img_2.png)

19. vi 편집기에서 맨 마지막 줄로 이동하는 단축키는 무엇인가?
```java
        shift + g
```


20. 하둡을 실행과 종료하는 명령어는 무엇인가?
```java
        - 실행 명령어 : ./start-all.sh
        - 종료 명령어 : ./stop-all.sh

        // cd /usr/local/hadoop/sbin : 하둡 실행 관련 명령어가 모인 폴더, 여기서 명령어를 쳐야한다.
        // 4장 93p
```


---
21. 하둡 마스터 서버에 네임노드와 데이터노드의 역할을 부여했다고 가정했을 때, 하둡이 샐행될 때 실행되는 데몬을 모두 작성하시오.
```java
        Jps
        NameNode
        DataNode
        NodeManager
        SecondaryNamenode
        ResourceManager

        // 4장 94p
```

22. 하둡 슬레이브 서버에 데이터노드의 역할을 부여했다고 가정했을 때, 하둡이 샐행될 때 실행되는 데몬을 모두 작성하시오.
```java
        Jps
        DataNode
        NodeManager

        // 4장 95p
```

**23. 파일 업로드 및 다운로드를 쉽게 하기위한 데몬의 설치 명령어를 작성하시오.**
```java
        yum install -y lrzsz

        // 파일 전송을 위한 기능으로 ZMODEM 프로토콜을 사용
        // 4장 16p
```


###빅데이터플랫폼 #예상문제