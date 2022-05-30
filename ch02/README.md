## 인트로

- MySQL 서버는 여러 형태로 설치할 수 있지만 리눅스의 RPM이나 운영체제별
  인스톨러를 이용하는 것이 좋다. - _.tar 또는 _.zip으로 압축된 버전 - 리눅스 RPM 설치버전 - 소스코드 빌드

## 버전과 에디션

- MySQL 서버 버전을 선택할때는 다른 제약사항이 없다면, 가능한 최신버전으로
  설치를 권장한다.
- 최신 버전중에서도 15~20번정도 릴리즈된 버전을 설치하는 것이 바람직하다.
- MySQL 8.0버전이라면 8.015 ~ 8.020버전 사이를 설치를 권장한다.
- 그리고 가장 최신 메이저 버전은 조심해야한다. 갓 탄생된 만큼 수많은 버그들이
  기다리고 있을수도 있기 때문이다.
- 초기에는 MySQL 커뮤니티 버전과 엔터프라이즈 버전은 기술적 지원만 차이가 있었을 뿐
  다른 차이는 없었다.
- 하지만, 5.5버전 이후로 소스코드도 달라졌고 엔터프라이즈 버전은 소스코드가 비공개로 돌려졌다.
  하지만, 상용화 전략은 어느 버전을 쓰든간에 똑같다. 단지, 특정 부가기능들만 엔터프라이즈 버전에
  포함되는 방식이다. 이러한 상용화 방식을 오픈 코어 모델이라고 한다.
- 그럼 엔터프라이즈에 속한 부가기능들은 무엇일까? 바로 아래와 같다.
  - Tread Pool
  - Enterprise Audit
  - Enterprise TDE (Master Key 관리)
  - Enterprise Authentication
  - Enterprise Firewall
  - Enterprise Monitor
  - Enterprise Backup
  - MySQL 기술 지원
- 경험상, Percona에서 출시하는 Percona Server를 이용하여 백업 및 모니터링 도구등등
  각종 플러그인을 이용하면 MySQL 커뮤니티 버전에 부족한 부분을 메꿀수 있다.

## MySQL 설치

- 필자는 현재 Mac OS를 사용하고 있으므로 Mac에 관련된 설치방법만 소개하겠다.
  그외에 설치방법을 알고 싶으면, 다른 필자가 작성한 글들을 참고 바란다.

  [MySQL 설치 사이트](https://dev.mysql.com/downloads/mysql/)

- 위의 링크를 타고 들어가서 해당되는 버전에 dmg 파일을 설치하면 된다.
- 설치를 진행하고 마지막에, MySQL Configuration 부분에서 Use String Password Encryption을
  이용하고 비밀번호를 설정하면 된다.

> ⚠️주의 : 설정한 비밀번호는 절대 까먹으면 안된다!

- 그럼 설치가 완료되었으면 제대로 설치가 되었는지 확인해보자. 아래와 같이 터미널에 명령어를 입력한다.

```bash
ps -ef | grep mysqld
```

- 위와 같이 입력하면 아래와 같은 결과가 나오면 설치가 된것이다.
  - bin: MySQL 서버와 클라이언트 프로그램, 유틸리티를 위한 디렉터리
  - data: 로그 파일과 데이터 파일들이 저장되는 디렉터리
  - include: C/C++헤더 파일들이 저장된 디렉터리
  - lib: 라이브러리 파일들이 저장된 디렉터리
  - share: 다양한 지원 파일들이 저장되어 있으며, 에러 메세지나 샘플 설정파일이 있는 디렉터리

![](https://velog.velcdn.com/images/roberts/post/58b1321a-e157-4def-9326-f5946ac54e5e/image.png)

- 그래도 못믿으면 시스템 환경설정에 mysql 돌고래 아이콘이 있으면 정말로 설치가 된것이다.

![](https://velog.velcdn.com/images/roberts/post/12b4318f-2fb1-4ded-aad9-3ea4d1f4e493/image.png)

- 돌고래 아이콘을 클릭해보면 MySQL 서버 설정을 변경할수 있다.

![](https://velog.velcdn.com/images/roberts/post/45b76c7d-4df3-49a2-b09f-7a4a0cda19bd/image.png)

![](https://velog.velcdn.com/images/roberts/post/40791016-e4b6-4c8a-8530-a8769f2188ca/image.png)
