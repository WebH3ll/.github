# 🔥 WebHell 🔥
중앙대학교 보안동아리 CAUTION 여름방학 웹 해킹 스터디 [2022.07.01 ~ 08.30]

노션 - https://myoungseok.notion.site/Web-Hacking-WebH3ll-48a96a349fec4ddebb4cb01efc1a44cd

## 🐳 스터디 목적 

- 웹 해킹 및 모의 해킹 전반적인 지식 습득
- 워게임이나 CTF 에서 PHP + Mysql 기반으로 만들어진 문제 多  → 개발을 통해 PHP언어에 대한 이해를 높이며, 취약점이 발생하는 로직을 이해한다.
- 웹 취약점 점검에서 가장 많이 사용되는 OWASP Top 10, 주요정보통신기반시설 취약점 분석 가이드를 실제 개발된 사이트에 적용
- 깃허브, 클라우드, 문서 작성 능력, 리눅스, 가상머신 등 IT 기본 지식 습득

## 🐤 스터디 운영 방식
- 기본 2인 1조로 서로 모르는 거 물어보면서 진행( 사이트 및 보고서는 각자 개발 )
- 2일에 한 번 진행 상황 공유

## 🐢 스터디 진행 일정
- [7.01 ~ 7.17 ] - [PHP 웹사이트 제작]()
- [7.21 ~ 7.03 ] - 취약점 분석 평가 및 보고서 작성
- [8.01 ~ 8.25 ] - OWASP Top 10 취약점과 관련된 CTF 문제 풀이
- [8.21 ~ 8.30 ] - Web Advanced 

# 🌀 PHP 웹사이트 제작
## PHP 기본 다지기

- 유튜브 강의를 통한 PHP 기본 문법 학습 [[링크](https://www.youtube.com/watch?v=_P68ImcE6VU&list=PLLtzrE3hP5SQQGi8R_SFe-_JpqJ-bAbBY&index=1)]
- 유튜브 강의를 통한 Bootstrap 기본 문법 학습[ [링크](https://www.youtube.com/watch?v=5ETqQWvwXV4) ]

## 웹사이트 요구사항

- system(),exec()함수를 이용한 서비스
    - ex) 사용자로부터 ip를 입력받으면 서버에서 ping을 날려주는 서비스
    - ex) 사용자로부터 url을 입력받으면 서버에서 dnslookup을 해주는 서비스
- 회원가입, 로그인, 로그아웃 기능 구현
    - 세션 혹은 쿠키를 이용하여 사용자 로그인 유무 검증
- Admin(관리자) 계정
    - 다른 사용자들의 모든 정보를 볼 수 있는 admin
    - 그 외에 자신의 사이트에서 제한된 정보를 볼 수 있는 관리자 권한 구현
- 게시판 기능
    - 게시글 작성
    - 게시글 읽기
    - 게시글 삭제 및 수정
    - 비밀 게시글
- 파일 업로드 및 다운로드 기능
- 비밀번호 변경, 계정 삭제 기능

## 웹사이트 배포

- 명석 [http://54.144.125.125](http://54.144.125.125/)
- 하람 [http://13.125.207.167](http://13.125.207.167)
- 지우
- 여진 [http://54.183.97.213](http://54.183.97.213/)
- 교현 [http://52.53.166.24](http://52.53.166.24/)
- 진우
- 필중 [http://3.38.168.17](http://3.38.168.17/PhilJoong/main.php)

# ⚡ 취약점 분석 평가 및 보고서 작성

## 취약점 분석 평가

**[체크리스트]**
**한국 인터넷 진흥원** - [**[주요정보통신기반시설 기술적 취약점 분석ㆍ평가 방법 상세가이드 2021](https://www.krcert.or.kr/data/guideView.do?bulletin_writing_sequence=35988)]**

**[진단 항목]**

- **운영체제 명령 실행**
- **SQL 인젝션**
- SSI 인젝션
- XPath 인젝션
- **디렉터리 인덱싱**
- **정보 누출**
- 악성 콘텐츠
- **XSS**
- **불충분한 인증**
- 취약한 패스워드 복구
- **CSRF**
- 세션 예측
- **불충분한 인가**
- 불충분한 세션 만료
- 세션 고정
- 자동화 공격
- **프로세스 검증 누락**
- **파일 업로드**
- **파일 다운로드**
- **관리자 페이지 노출**
- 경로 추적
- 위치 공개
- **데이터 평문 전송**
- **쿠키 변조**

## 취약점 분석 평가 방식
- 평가 방식 : WhiteBox 방식의 취약점 분석 평가
- 사용한 툴 : BurpSuite
- 기능이 완성된 하람, 여진, 필중, 교현의 웹사이트를 대상으로 점검 수행


# 🌟 OWASP Juice Shop CTF
## OWASP Top 10이란?
[OWASP Top 10:2021](https://owasp.org/Top10/)

## OWASP Juice Shop
- OWASP 재단에서 OWASP Top 10 취약점에 대한 교육을 위해 제작한 취약한 웹사이트
- 특정 취약점을 유도하면 FLAG 획득 가능

## 환경 설치
1. docker 설치
    
    ```bash
    $sudo apt-get install -y docker.io
    ```
    
2. owasp-juice 설치
    
    ```bash
    $sudo docker run -d -e "NODE_ENV=ctf" -p 3000:3000 bkimminich/juice-shop
    ```
    

3. AWS 포트 열기
    1. EC2 인스턴스 찾기
    2. 인스턴스 ID 클릭       
    3. 보안 > 보안 그룹 클릭
    4. 인바운드 규칙 편집 > 다음과 같이 인바운드 규칙 추가

[http://54.144.125.125:4000/](http://54.144.125.125:4000/)
![image](https://user-images.githubusercontent.com/33647663/185735629-769e8706-1bbd-42bb-ad71-eb4dcf44d96b.png)

## FLAG 제출 사이트
[http://54.144.125.125:8000](http://54.144.125.125:8000/)

![image](https://user-images.githubusercontent.com/33647663/185735676-8aa04901-b509-48d9-88a7-24e96855ba17.png)

# 🏆 Web - Advanced
## 1. Vulnerable Web ( 필중 여진 하람 지우 )

- 예시 - xxe 취약점이 가능하도록 기능을 넣어보기, HTTP Header XSS 가 가능하도록 기능을 넣어보기, Upload 기능에서 필터링을 구현했지만 우회가 가능하도록 구현해보기 등등
- 요구사항
    - 관련된 취약점이 무엇인지
    - 취약점이 발생하는 이유(코드상에서 어떠한 로직, 함수, 변수 때문)
    - 해당 취약점으로 가능한 공격(쉘 획득, 데이터 유출, dos 등..) → 시연도 하기
    - 2 ~ 3개 정도

## 2. CTF WriteUp ( 진우 교현 )

- OWASP Juice All Clear
- 요구사항
    - 풀이과정이 포함된 Write Up

## 3. Create CTF ( 필중 하람 )

- 웹 해킹 관련 CTF 문제 제작하기
- 요구사항
    - Docker ( 너무 쉬운거면 안해도 되긴 함 ) ~~그래도 해 그냥~~
    - FLAG 출력

