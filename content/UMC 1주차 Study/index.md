---
emoji: 📔
title: UMC 1주차 워크북
date: '2023-03-27 00:00:00'
author: dydals3440
tags: UMC UMC1주차 UMC-4기
categories: UMC
---

# Chapter 1. HTML + CSS + JS (1)

## 📝 학습 목표

---

1. Web이 무엇인지 인지하고, Web에 대해 이해한다.
2. 자신이 왜 Web을 공부해야 할 지 고민해본다.
3. HTML, CSS, JavaScript가 뭔지 역할을 이해한다.

## 📸잠깐 ! 스터디 인증샷은 찍으셨나요?📸

---

- 스터디리더께서 대표로 매 주차마다 한 장 남겨주시면 좋겠습니다!🙆💗
  (사진을 저장해서 이미지 임베드를 하셔도 좋고, 복사+붙여넣기해서 넣어주셔도 좋습니다!)

[https://www.notion.so](https://www.notion.so)

## 🎯 핵심 키워드

---

<aside>
💡 주요 내용들에 대해 조사해보고, 자신만의 생각을 통해 정리해보세요!
레퍼런스를 참고하여 정의, 속성, 장단점 등을 적어주셔도 됩니다.
조사는 공식 홈페이지 **Best**, 블로그(최신 날짜) **Not Bad**

</aside>

- Web

  - URL/URI/둘의 차이점

    # URL

    `URL(Uniform Resource Locators)`
    웹 주소이다, 컴퓨터 네트워크 상에서 리소스가 어디에 위치해있는지 알려주기 위한 규약이다.
    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled.png>)

    ### 프로토콜

    브라우저가 리소스를 요청하기 위해 사용해야 하는 `프로토콜`을 나타낸다.
    `프로토콜`은 중앙 컴퓨터와 단말기 사이에서 데이터 통신을 원활하게 하기 위해 필요한 통신 규약으로, 웹에서는 브라우저와 서버 간에 데이터를 주고 받기 위한 방식으로 `HTTPS`/`HTTP` 프로토콜이 가장 많이 사용되고 있다. `HTTPS`/`HTTP` 외에도 `mailto:`(이메일 주소를 지정하는 프로토콜), `ftp:`(파일을 주고 받는 프로토콜) 등 다양한 프로토콜이 존재한다.

    - `HTTP`(Hyper Text Transfer Protocol): 웹 브라우저와 웹 서버가 서로 데이터를 주고받기 위해 만든 통신규약
    - `HTTPS`(Hyper Text Transter Protocol Secure): `HTTP에서 보안이 강화`된 버전
      > `http`://www.naver.com > `https`://www.google.co.kr > `ftp`://192.23.56.189

    ### 호스트 주소(Domain Name)

    도메인은 아래와 같이 구성됩니다.
      <aside>
      💡 호스트명(차상위 도메인/서브 도메인) - 도메인명 - 최상위 도메인
      
      </aside>
      
      1. 최상위 도메인 (TLD, Top-Level Domain)
          
          : 도메인 레벨 중 가장 높은 단계에 있는 도메인, 도메인의 목적, 종류, 국가등을 나타낸다.
          
          (`.com`, `.net` 등)
          
      2. 차상위 도메인 (SLD, Second-Level Domain)
          
          : 호스트, 서브 도메인으로 불리기도 한다. 보조 도메인으로써 URL로 전송하거나 계정 내의 IP주소나 디렉토리로 포워딩되는 도메인 이름의 확장자이다.
          
          (`www.`, `m.`등)
          
      3. 도메인 이름 (Domain Name)
          
          : 임의로 지정할 수 있는 사이트의 이름이다. 익히 알고 있는 google, naver 등 사용자에게 쉽게 기억될 수 있도록 보통 서비스명으로 도메인 명을 지정해 사용합니다.
          
          (`google`, `naver` 등)
          
      
      제목 그대로 도메인 주소이다.
      
      도메인 주소 대신, IP주소가 사용되기도 합니다.
      
      ### Port
      
      포트 번호를 통해 `어떤 서버를 이용할지 결정`하며, `: (콜론)` 뒤에 나온다.
      
      - 포트 번호
      - 표준 HTTP 포트를 사용한다면 포트 번호가 생략 됨 (HTTP의 경우 80 생략, HTTPS의 경우 443 생략)
      - URL에는 기본적으로 표준 포트번호가 생략되어 있음.
      
      > https://www.google.co.kr:`443`
      http://www.google.co.kr:`80`
      > 
      
      ### Parameter(Query String
      
      파라미터는 쿼리 스트링이라고 부르며, key(파라미터 이름) = value(파라미터 값)의 형태로 이루어집니다. ? 뒤에 나열되고, & 기호로 구분되어 여러개가 존재할 수 있습니다.
      
      광고 분석시 많이 사용되는 UTM(Urchin Tracking Module)이 query parameter를 이용한 사용자 추적 서비스이다.
      
      > [https://www.youtube.com/watch?`v=7YZ1isZmdqw`](https://www.youtube.com/watch?v=7YZ1isZmdqw)
      > 
      - directoryNo=0
      - currentPage=1
      - groupId=0
      
      ### Anchor(=Fragment)
      
      HashTag라고도 불립니다. 해시태그로 이동을 원하는 요소의 id를 링크로 연결하여 스크롤 이동 없이 바로 해당 위치로 이동할 수 있습니다. 파일 디렉토리 및 파일 이름과 유사한 역할로 쓰이는 경우가 많습니다.
      
      > https://www.naver.com/`#wrap`
      > 
      
      ---
      
      # URI
      
      URI(Uniform Resource Identifier) 
      
      URI는 특정 리소스를 식별하는 **통합 자원 식별자(Uniform Resource Identifier)**를 의미한다. 웹 기술에서 사용하는 논리적 또는 물리적 리소스를 식별하는 고유한 문자열 시퀀스다.
      
      일반 URI는 다음과 같은 구조를 보여준다.
      
      ```
      scheme:[//[user[:password]@]host[:port]][/path][?query][#fragment]
      
      ```
      
      1. `scheme` : 사용할 프로토콜을 뜻하며 웹에서는 http 또는 https를 사용
      2. `user`와 `password` : (서버에 있는) 데이터에 접근하기 위한 사용자의 이름과 비밀번호
      3. `host`와 `port` : 접근할 대상(서버)의 호스트명과 포트번호
      4. `path` : 접근할 대상(서버)의 경로에 대한 상세 정보
      5. `query` : 접근할 대상에 전달하는 추가적인 정보 (파라미터)
      6. `fragment` : 메인 리소스 내에 존재하는 서브 리소스에 접근할 때 이를 식별하기 위한 정보
      
      ---
      
      # URL과 URI 그래서 차이는 뭔데?
      
      URI 그리고 URL을 혼용해서 사용하는 경우가 있다. 대부분의 경우 문제가 없지만 정확하게 이 둘의 차이점이 존재한다. 
      
      ![Untitled](Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%201.png)
      
      비록 URL은 URI의 서브셋이지만 URI와 URL의 가장 큰 차이점은 바로 아래와 같다
      
      > URI는 식별하고, URL은 위치를 가르킨다.
      > 
      
      실세계에 빗대어 예시를 들어보자면 다음과 같다.
      
      **“Charles”** 는 내 이름이며 **식별자(Identifier)**다. 이는 URI와 비슷하지만 내 위치나 연락처에 대한 정보가 없으므로 URL은 될 수 없다.
      
      **“경기도 성남시 분당구 정자동 불정로 6”**는 주소다. **주소는 특정 위치를 가르킨다**. URL 및 URI와 비슷하며 간접적으로 내가 있는 장소로 식별한다.
      
      실제 네트워크상에서 URI와 URL을 예시는 다음과 같다.
      
      ![Untitled](Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%202.png)
      
      두 주소는 모두 index.html을 가리키고 있다.
      
      첫번째 주소는 웹서버의 실제 파일 위치를 나타내는 주소이므로 URI이면서 URL이다.두번째 주소는 실제로 index라는 파일이 웹서버에 존재하지 않으므로 URL은 아니다. 하지만 서버 내부에서 이를 처리하여 결국 index.html을 가리키기 때문에 URI라고 볼 수 있다.
      
      ---
      
      ## ✅ 참고자료
      
      wikipedia [URL](https://ko.wikipedia.org/wiki/URL)
      
      MDN [What is a URL?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL)
      
      [https://velog.io/@liankim/URL의-구조](https://velog.io/@liankim/URL%EC%9D%98-%EA%B5%AC%EC%A1%B0)
      
      [https://velog.io/@h220101/URI-URL-구조-차이점](https://velog.io/@h220101/URI-URL-%EA%B5%AC%EC%A1%B0-%EC%B0%A8%EC%9D%B4%EC%A0%90)
      
      [https://www.charlezz.com/?p=44767](https://www.charlezz.com/?p=44767)

  - www
    # www
    ‘World Wide Web’의 약자로 인터넷에 연결된 컴퓨터를 이용하여 사람들과 정보를 공유할 수 있는 공간을 의미합니다.
    HTTP를 기반으로 HTML로 작성된 하이퍼 텍스트를 웹브라우저를 통해 읽을 수 있게 되었습니다.
    보통은 인터넷과 동일하게 보는 경우가 있지만, 정확하게 말하자면 인터넷보다 작은 개념이라고 할 수 있습니다.
  - http/https
    # HTTP?
    ‘Hyper Text Transfer Protocol’의 약자로 하이퍼 텍스트를 교환, 전송을 위한 통신 규약입니다.
    쉽게 말하자면 ‘HTTP’는 다양한 환경에서 여러 기기가 서로 통신을 주고 받을 수 있도록 만든 일종의 규칙이라고 생각하면 됩니다. 내가 A데이터를 요청하면 너는 그에 해당하는 데이터를 반환해줘! 라는 통신규약입니다. 이런 규칙을 따름으로서 서로 다른 회사에서 기기나 서비스를 만들어도 서로 데이터를 주고받을 수 있게됩니다.
    ### HTTP의 구조
    ‘HTTP’는 클라이언트와 서버 사이에 이루어지는 Request와 Response로 이루어져있습니다.
    특정 링크를 클릭하여 홈페이지를 접속한다고 가정했을떄, 사용자는 링크를 클릭하는 행위를 통해 서버에 해당하는 홈페이지의 정보를 Request하며, 서버는 사용자의 요청에 따라 홈페이지의 정보를 Response하고 통신을 종료합니다.
    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%203.png>)
    위의 과정을 통하여 홈페이지 정보를 전달받은 사용자의 브라우저는 홈페이지 정보를 화면에 출력하게 됩니다.
    우리가 사용하는 인터넷은 위의 과정을 거친 무수한 Request와 Response로 이루어져있습니다.
    우리가 홈페이지 주소를 입력할 때 사용하는 ‘http’는 ‘http’프로토콜을 이용하여 정보를 교환한다는 의미를 갖고있다고 생각하면 됩니다.
    ### HTTP의 get/post
    위의 구조에서 설명했듯이, 클라이언트가 http를 통하여 서버 측에 Request시 사용하는 방식이 크게 2가지 입니다. 하나는 ‘`get`’ , 다른 하나는 ‘`post`’ 방식입니다. 둘의 차이는 무엇인지 아래에서 설명해보겠습니다.
    > `get`: url에 데이터를 붙여서 서버로 데이터를 보내고 정보가 겉으로 표현됨, url의 크기가 제한적이여서 보낼 수 있는 정보량의 한계가 있다는 단점이 있다.
    >
    > `post`: 데이터가 body안에 숨겨져서 발송이되어 보안성에 뛰어나다.
    > **위의 설명만 보면 왜 `get`을 쓰냐 이렇게 생각할 수 있습니다.**
    > 하지만 실제로 둘의 용도에는 차이점이 있습니다.
    > 일반적으로 `get`은 DB에서 자료를 가져와서 읽을 떄 주로 사용합니다.
    > `post`은 서버의 DB값이나 상태를 바꾸는 쓰기, 수정 기능을 사용할 때 사용합니다.
    > `get` 방식은 동영상, 이미지, 텍스트를 읽어오는 등 서버에 저장된 데이터를 가져올 떄 사용합니다.
    > `post` 방식은 게시판에 글을 쓴다든지, 회원가입을 한다든지 하는 DB에 영향을 줄 떄 사용합니다.
    > 링크를 전달할때 `post` 방식을 사용할 경우 자료를 읽어올때 자료의 링크가 전부 숨겨질 것이다. 타인에게 자료를 전달할려고 할떄 모든 정보가 숨겨지기 떄문에 전달이 불가능하기에 이러한 상황일떄는 `get` 방식을 사용한다.
    ### HTTP의 응답(response) 코드
    `HTTP는 클라이언트가 Request 하면, Response 합니다.`
    `Response`시 클라이언트가 요청한 것 외에도 코드를 반환합니다. 이 코드를 통해 정보가 제대로 전달이 되었는지, 에러가 발생했는지를 확인할 수 있습니다.
    - 200 OK: 클라이언트의 성공적으로 처리됐을 때를 의미함.
    - **302 Found**: 요청된 리소스의 URI가 일시적으로 변경됐음을 의미함.
    - 400 Bad Request: 요청이 잘못되었을 때를 나타냄.
    - 401 Unauthorized: 인증이 필요한 리소스에 인증없이 접근할 때 발생.
    - **403 Forbidden:** 서버까지 클라이언트 요청이 도착했으나 접근 권한이 없음.
    - **404 Not Found**: 서버가 요청된 리소스를 찾을 수 없음. 가장 흔한 오류.
    - 408 Request Timeout: 요청 중 시간이 초과되었을 때 사용.
    - 500 Internal Server Error: 서버 문제로 인한 오류. 보통은 서버측 오류임.
    - **502 Bad Gateway**: 게이트웨이가 연결된 서버에서 잘못된 응답을 받았을 때. 보통 서버 폭주시 발생.
      [HTTP response status codes - HTTP | MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
    ***
    # HTTPS란?
    최근에는 많은 사이트들이 앞에 ‘HTTP’가 아닌 ‘HTTPS’라는 글자를 앞에 부팅기 시작했다.
    이는 **HyperText Transfer Protocol over Secure Socket Layer** 의 약자다.
    앞서 설명했듯이 보안이 강화된 ‘HTTP’라고 생각하는게 이해하기 편할 것이다.
    SSL, TSL 프로토콜을 사용하여 데이터를 암호화한다. 흔히 쇼핑몰이나 은행 등 보안이 필요한 사이트에서 원래는 주료 이용했으나, 현재 대부분 디폴트 수준으로 많이 지원한다.
    # ✅ 참고자료
    [HTTP란? WWW란?](https://sgcomputer.tistory.com/221)
    [What is a web server? - Learn web development | MDN](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Web_mechanics/What_is_a_web_server)
    [HTTP response status codes - HTTP | MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)

- 인터넷
  ### 인터넷(Internet)의 개념
  인터넷(Internet)이란 여러 통신망을 하나로 연결한다는 의미의 ‘인터 네트워크(inter-network)’라는 말에서 시작되었으며, 이제는 전 세계 컴퓨터들을 하나로 연결하는 거대한 컴퓨터 통신망을 의미합니다.
  이러한 인터넷은 클라이언트와 서버로 구성되며, TCP/IP라는 기본 프로토콜을 통해 제공되고 있습니다.
  ### 인터넷의 구성
  여러 컴퓨터가 각각 클라이언트와 서버로써 서로 연결되어 구성된 망을 컴퓨터 네트워크(computer network)라고 합니다.
  인터넷은 이러한 컴퓨터 네트워크가 전 세계적인 규모로 수없이 많이 모여서 이루어진 일종의 컴퓨터 네트워크 시스템입니다. 즉, 인터넷이란 수많은 클라이언트 컴퓨터와 서버 컴퓨터, 그리고 이들로 구성된 네트워크들의 집합체인 것입니다.
  # ✅ 참고자료
  [코딩교육 티씨피스쿨](http://www.tcpschool.com/webbasic/intro)
- 웹 1.0 / 2.0 / 3.0
  # WEB 1.0
  Web 1.0의 시대는 이런 검색 서비스의 탄생들이 해당되겠습니다. 대표 예시가 1990년대 인기를 끈 웹사이트인 Yahoo 입니다.
  Web 1.0의 구성요소는
  1. 정적 페이지
  2. 프레임셋의 이용
  3. HTML 확장
  4. 온라인 방명록
  5. GIF 단축
     등이 있습니다. Web 1.0은 전화접속을 기반으로, 한국에는 천리안, 나우누리, 하이텔 등의 시절이며 평균 50k 정도의 대역 수준입니다.
     대표 사례: 인터넷 익스플로러, 다음, 네이버, 구글과 같은 검색 포털
     핵심 기술: HTML, Active X
  ***
  # WEB 2.0
  검색을 통해 자료를 열람하는 시대가 지나 개방, 참여, 공유 소통의 시대로 넘어오게 됩니다. 양방향 소통 기술이 접목된 것이 Web 2.0의 시대입니다.
  Web 2.0의 대표 컨텐츠는 아래와 같습니다.
  1. 게시판
  2. 블로그
  3. 댓글
  4. UCC
  5. 지식백과
     단순한 웹의 집합체의 모임을 분류한게 Web 1.0 이라면, 이를 더 발전시켜서 하나의 플랫폼으로 만들고, 이 플랫폼을 개방하여 다양한 사람들의 참여를 유도하고 소통하는 것이 Web 2.0의 시대라고 생각하시면 됩니다.
     Web 2.0을 한마디로 요약하자면 “프로그램 처럼 사용할 수 있는 웹사이트” 입니다. 위에서 말한 블로그 이외에도 나무위키 같은 것도 Web 2.0의 표본이라고 생각하시면 됩니다. 누구나 인증만 거치면 내용 및 수정에 기여할 수 있습니다.
     대표 사례: 크롬, 파이어폭스 같은 확장브라우저, 위키피디아, 블로그, 싸이월드, 페이스북, 트위터, 링크드인 등과 같은 웹사이트
     핵심 기술: AJAX, XML, RSS Tagging
  ***
  # Web 3.0
  `**Web 3.0 이란?**`
  컴퓨터가 시멘틱 웹 기술을 활용하여 웹페이지에 담긴 내용을 이해하고, 개인 맞춤형 정보를 제공할 수 있는 지능형 웹 기술을 말합니다. 지능화, 개인화된 맞춤형 웹입니다.
  `Web 3.0`은 기본적으로 `Web 2.0`의 핵심인 읽기와 쓰기를 넘어 `‘소유’의 개념이 더해진 것`이다.
  세계 곳곳에 흩어진 네트워크 참여자들의 컴퓨터 자원을 활용하는 블록체인 기술 덕분에 자료가 분산 저장되고 이더리움 같은 가상화폐에 내재된 자동화 프로그래밍 기술(스마트 콘트랙트)로써 관리자의 개입 없는 웹 이용이 가능하다. 암호화 기술을 활용한 대체 불가능 토큰으로 데이터의 온전한 소유권 또한 주장할 수 있다.
  즉, 데이터의 저장과 사용, 소유가 네티즌에게 주어지는 완전히 개인화된 인터넷 환경을 만들 수 있다는 개념이다.
  ***
  # ✅ 참고 자료
  [Web 1.0 Web 2.0 Web 3.0, 웹 1.0, 웹 2.0, 웹3.0 차이와 세대 정리](https://kasper1030.tistory.com/790)
  [WEB 3.0 - web3가 뭐죠?](https://story.pxd.co.kr/1648)
- 브라우저

  # Browser?

    <aside>
    💡 인터넷에서 웹 서버의 모든 정보를 볼 수 있도록 하고, 문서 검색을 도와주는 응용 프로그램이다.
    
    </aside>
    
    우리가 일상 생활에서 인터넷을 통해 검색을 할 떄 주로 구글 네이버 같은 사이트에 접속하여 필요한 정보를 검색합니다. 이 떄 사이트에 접속할 수 있는 도구를 바로 ‘브라우저’ 혹은 ‘웹 브라우저’라고 부른다.
    
    한마디로 브라우저는 제어판과 같이 컴퓨터에 설치되어 있는 하나의 프로그램으로, 이 프로그램을 다운받고 실행하게 되면 주소창을 입력할 수 있는 도구가 나타내게 되는 것이다.
    
    ### 최근 브라우저 시장 점유율 (크롬이 압도적이다)
    
    ![Untitled](Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%204.png)
    
    ### ✅ 참고자료
    
    [브라우저(browser)란 무엇일까?](https://velog.io/@hahan/브라우저browser란-무엇일까)

- HTML

  - DOM

    # DOM?

    DOM(Document Object Mode)은 웹 페이지에 대한 인터페이스이다. 기본적으로 여러 프로그램들이 페이지의 콘텐츠 및 구조, 그리고 스타일을 읽고 조작할 수 있도록 API를 제공합니다. 먼저 DOM을 이해하기 전에 웹 페이지가 어떻게 빌드 되는지 살펴보겠다.

    ***

    ### 웹 페이지는 어떻게 만들어지나?

    웹 브라우저가 원본 HTML 문서를 읽어드린 후, 스타일을 입히고 대화형 페이지로 만들어 뷰 포트에 표시하기까지의 과정을 “`Critical Rendering Path”`라고 한다.
    두 단계로 나누어져 있습니다.

    1. 첫번쨰 단계에서 브라우저는 읽어들인 문서를 `파싱`하여 최종적으로 `어떤 내용을 페이지에 렌더링할지 결정`합니다.
    2. 두번쨰 단계에서 브라우저는 해당 렌더링을 수행합니다.
       ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%205.png>)
       1번 과정을 거치면 `“Render Tree”`가 생성됩니다.
       `Render Tree`는 웹 페이지에 표시될 HTML 요소들과 이와 관련된 스타일 요소들로 구성됩니다. 브라우저는 렌더 트리를 생성하기 위해 다음과 같이 두 모델이 필요합니다.

    - `DOM(Document Object Model)` → HTML 요소들의 구조화된 표현
    - `CSSOM(Cascading Style Sheets Object Model)` → 요소들과 연관된 스타일 정보의 구조화된 표현

    ### DOM은 어떻게 생성될까? 어떻게 보여질까?

    DOM은 원본 HTML 문서의 객체 기반 표현 방식입니다. 둘은 서로 비슷하지만, DOM이 갖고 있는 근본적인 차이는 단순 텍스트로 구성된 HTML문서의 내용과 구조가 객체 모델로 변환되어 다양한 프로그램에서 사용될 수 있다는 점이다.
    DOM의 개체 구조는 “Node Tree”로 표현된다. 하나의 부모 줄기가 여러 개의 자식 나뭇가지를 가지고 있습니다. 각각의 나뭇가지는 잎을 갖고있습니다.

    ```html
    <!doctype html>
    	<head>
    		<title>My first web page</title>
    	</head>
    	<body>
    			<h1>Hello, World!</h1>
    			<p>How are you?</p>
    	</body>
    </html>
    ```

    아래와 같은 Node Tree로 표현된다!
    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%206.png>)

    ### DOM과 HTML의 차이점?

    위의 토글에서 본 결과 DOM은 마치 HTML 문서와 1대1 매핑이 되는 것으로 보입니다. 그러나 둘 간에는 몇가지 차이점이 있다.

    1. **작성된 HTML 문서가 유효하지 않을 떄**

       DOM은 유효한 HTML 문서의 인터페이스 입니다. DOM을 생성하는 동안, 브라우저는 유효하지 않은 HTML 코드를 올바르게 교정합니다.

       ```html
       <!doctype html>
       	<html>
       		Hello , world
       	</html>
       </html>
       ```

       문서에 유효한 HTML 규칙의 필수 사항인 head 태그, body 태그의 요소가 빠져있습니다. 그렇지만 `생성된 DOM 트리에는 올바르게 교정되어 나타납니다.`

       ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%207.png>)

    2. **자바스크립트에 의해 DOM이 수정될 떄**

       DOM은 HTML 문서의 내용을 볼 수 있는 인터페이스 역할을 하는 동시에 동적 자원이 되어 수정될 수 있습니다. 예를 들어, 자바스크립트를 사용해 DOM에 새로운 노드를 추가할 수 있습니다.

       ```jsx
       let newElement = document.createElement('p');
       let newElementContent = document.createTextNode("I'm new!");
       newElement.appendChild(newElementContent);
       document.body.appenChild(newElement);
       ```

       이 코드는 DOM을 업데이트하나, HTML 문서의 내용을 변경하지는 않습니다.

    3. **DOM은 브라우저에서 보이는 것이 아니다.**

       브라우저 뷰 포트에 보이는 것은 `Render Tree`로 `DOM과 CSSOM의 조합`입니다. `Render Tree`는 오직 스크린에 그려지는 것으로 구성되어 있어 `DOM`과 다릅니다. 달리 말하면, `Render Tree는 렌더링 되는 요소만이 관련 있기 떄문에 시각적으로 보이지 않는 요소는 제외됩니다.`

       예를들어 html의 태그에 직접적으로 inline에 css속성을 주어 보겠습니다.

       ```jsx
       <!doctype html>
       <html lang="en">
       	<head></head>
       	<body>
       		<h1>Hello, world</h1>
       		<p style="display: none;">How are You?</p>
       	</body>
       </html>
       ```

       `DOM`은 `<p> 요소를 포함`합니다.

       ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%208.png>)

       하지만 `Render Tree`에 해당하는 `View Port에 표시되는 내용은 display: none 속성이므로 <p> 요소를 포함하지 않습니다.`

       ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%209.png>)

    4. **DOM은 개발도구에서 보이는 것이 아니다.**
       `개발도구의 요소 검사기`는 `DOM과 가장 가까운 근사치를 제공`합니다. 그러나 개발도구의 요소 검사기는 DOM에 없는 추가적인 정보를 포함합니다.
       `가장 좋은 예는 CSS의 가상 요소`입니다. `::before`, `::after` 선택자를 사용하여 생성된 가상 요소는 `CSSOM과 Render Tree의 일부를 구성`합니다.
       하지만, 기술적으로 `DOM`의 일부는 아니다. `DOM`은 오직 원본 HTML 문서로 부터 빌드 되고, 요소에 적용되는 스타일을 포함하지 않기 떄문입니다.
       가상 요소가 DOM의 일부가 아님에도 불구하고, 요소 검사기에서는 아래와 같이 확인된다.
       ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2010.png>)
       이러한 이유로 `가상 요소는 DOM의 일부가 아니기 떄문에 자바스크립트에 의해 수정될 수 없습니다.`

    ***

    ### 요약 정리

    DOM은 HTML 문서에 대한 인터페이스이다. 첫째로 뷰 포트에 무엇을 렌더링 할지 결정하기 위해 사용되며, 둘쨰로는 페이지의 콘텐츠 및 구조, 그리고 스타일이 자바스크립트 프로그램에 의해 수정되기 위해 사용됩니다. DOM은 원본 HTML 문서 형태와 비슷하지만 몇 가지 차이점이 있습니다.

    - 항상 유효한 HTML 형식입니다.
    - 자바스크립트에 수정될 수 있는 동적 모델이어야 합니다.
    - 가상 요소를 포함하지 않습니다.(`ex. ::after`)
    - 보이지 않는 요소를 포함합니다. (`ex. display:none`)

    ***

    # ✅ 참고 자료

    [DOM - MDN Web Docs 용어 사전: 웹 용어 정의 | MDN](https://developer.mozilla.org/ko/docs/Glossary/DOM)
    [브라우저는 어떻게 동작하는가?](https://d2.naver.com/helloworld/59361)
    [DOM은 정확히 무엇일까? | WIT블로그](https://wit.nts-corp.com/2019/02/14/5522)

  - <div> 태그
      
      # <div> 태그
      
      HTML 요소들을 하나로 묶는데 자주 사용되는 대표적인 `block 요소`입니다.
      
      여기서 block이란 요소가 한 줄을 가득 채운다고 생각하면 됩니다.
      
      ```jsx
      <style>
          div {
              background-color: orange;
              font-style: italic;
          }
      </style>
      
      <p>HTML의 모든 요소는 해당 요소가 웹 브라우저에 어떻게 보이는가를 결정짓는 display 속성을 가집니다.</p>
      <div><p>div 요소는 다른 HTML 요소들을 하나로 묶는 데 자주 사용되는 대표적인 블록(block) 요소입니다.</p></div>
      <p>span 요소는 텍스트(text)의 특정 부분을 묶는 데 자주 사용되는 인라인(inline) 요소입니다.</p>
      ```
      
      ![스크린샷 2023-03-24 오후 6.27.10.png](Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_6.27.10.png)

  - <img> 태그
    # <img> 태그
    ```jsx
    <img class="fit-picture"
         src="/media/cc0-images/grapefruit-slice-332-332.jpg"
         alt="Grapefruit slice atop a pile of other slices">
    ```
    위의 예제를 통해 `<img>` 요소의 사용법을 알 수 있습니다.
    - `src` 특성은 **필수**이며, 포함하고자 하는 `이미지의 경로를 지정`합니다.
    - `alt` 특성은 이미지의 텍스트 설명이며 필수는 아니지만, 스크린 리더가 `alt`의 값을 읽어 사용자에게 이미지를 설명하므로, 접근성 차원에서 **매우 유용**합니다. 또한 네트워크 오류, 콘텐츠 차단, `죽은 링크 등 이미지를 표시할 수 없는 경우에도 이 속성의 값을 대신 보여줍니다`.
      ![스크린샷 2023-03-24 오후 6.30.33.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_6.30.33.png>)
      [<img>: 이미지 삽입 요소 - HTML: Hypertext Markup Language | MDN](https://developer.mozilla.org/ko/docs/Web/HTML/Element/img)
  - <input> 태그

    # <input> 태그

    **HTML `<input>` 요소**는 웹 기반 양식에서 사용자의 데이터를 받을 수 있는 대화형 컨트롤을 생성합니다. [사용자 에이전트](https://developer.mozilla.org/ko/docs/Glossary/User_agent)에 따라서 다양한 종류의 입력 데이터 유형과 컨트롤 위젯이 존재합니다. 입력 유형과 특성의 다양한 조합 가능성으로 인해, `<input>` 요소는 HTML에서 제일 강력하고 복잡한 요소 중 하나입니다.

    ```jsx
    <label for="name">Name (4 to 8 characters):</label>

    <input type="text" id="name" name="name" required
           minlength="4" maxlength="8" size="10">
    ```

    위와 같은 방식으로, 원하는 크기만큼 값을 입력받을 수도 있습니다.
    ![스크린샷 2023-03-24 오후 6.36.31.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_6.36.31.png>)
    `<input>` 요소의 동작 방식은 type에 따라 현저히 달라집니다. 기본 값은 `text` 입니다.
    [<input>: 입력 요소 - HTML: Hypertext Markup Language | MDN](https://developer.mozilla.org/ko/docs/Web/HTML/Element/input)
    [HTML <form> 태그 총정리 + <input>, <button>](https://365kim.tistory.com/64)
    `위의 링크에서 type과 option을 확인할 수 있습니다.`

    ### label으로 input 의미 정의하기

    `<label>` : 폼의 양식에 이름을 붙이는 태그, 주요 속성은 `for`이다. `label`의 `for`의 값과 양식의 `id`의 값이 같으면 연결이 된다.

    ```html
    <form>
      <label for="username">Username:</label>
      <input id="username" type="text" placeholder="username" name="username" />
    </form>
    ```

    `<label>` 안에 `<input>` 을 중첩시킬 수 있다. 이 경우 연관이 암시적이므로 `for` 및 `id` 속성이 필요없다.

    ```html
    <form>
      <label for="password"
        >Password:
        <input id="password" type="password" placeholder="password" name="password" />
      </label>
    </form>
    ```

    ### form태그에 입력값 전달하기 button

    `<button>`을 통해 `<input>`을 이용하지 않고 버튼을 생성할 수 있다.`<button>` 요소 안에서는 텍스트나 이미지 같은 내용을 넣을 수 있다.`type` 값을 지정하지 않으면 form의 내용이 제출(submit)된다.

    ```
    <form>
       <button>Submit!</button>
       <input type="submit" value="Submit!">
    </form>
    ```

    `type` 값을 button으로 지정하면 제출되지 않는다.

    ```
    <form>
       <button type="button">This is a button(won't submit)</button>
    </form>
    ```

    ### action과 name 속성을 활용하여 구글 검색하기

    `action`에 구글 검색 URL, `name` 값에 q 입력`action` 값과 `name` 값은 사이트마다 다름

    ```
    <form action="https://www.google.com/search">
        <input type="text" name="q">
        <button>Search Google</button>
    </form>
    ```

  - <a> 태그

    # <a> 태그

    하이퍼링크를 걸어주는 `anchor` 태그입니다.
    `target: blank`를 쓰면 새 탭으로 홈페이지를 열어줍니다.

    ### **속성**

    - **href**: 클릭시 이동 할 링크
    - **target**: 링크를 여는 방법
      - `_self`: 현재 페이지 (기본값)
      - `_blank`: 새 탭
      - `_parent`: 부모 페이지로, `iframe` 등이 사용된 환경에서 쓰입니다.
      - `_top`: 최상위 페이지로, `iframe` 등이 사용된 환경에서 쓰입니다.
      - _`프레임이름`_: 직접 프레임이름을 명시해서 사용할 수도 있습니다.

    # **사용법**

    ```
    <a href="http://www.naver.com">Go NAVER</a>
    ```

    # **예제**

    ```
    <html>
    	<body>
    		<a href="http://www.naver.com">Go Naver</a><br>
    		<a href="http://google.co.kr" target="_blank">Go Google (new window)</a>
    	</body>
    </html>

    ```

    _출력 결과_
    [Go Naver](http://www.naver.com/)
    [Go Google (new window)](http://google.co.kr/)

  - <span> 태그

    # **개요**

    `<span></span>` 태그는 `<div></div>` 태그처럼 특별한 기능을 갖고있지 않고, CSS와 함께 쓰입니다.
    `<div>` 태그와의 차이점은 `display`속성이 `block`이 아닌, `inline`이라는 점인데, 이는 [CSS display](https://ofcourse.kr/css-course/display-%EC%86%8D%EC%84%B1) 항목에서 세부 정보를 알 수 있습니다.이 둘의 차이를 쉽게 설명하자면, `<div>`는 줄 바꿈이 되지만, `<span>`은 줄 바꿈이 되지 않다는 점입니다. 또한 텍스트의 특정 부분을 묶는데 자주 사용되어집니다.

    # **사용법**

    ```
    <span>내용</span>

    ```

    # **예제**

    ```
    <html>
    <body>
    	<span style="background-color:red">span1</span>
    	<span style="background-color:blue">span2</span>
    	<span style="background-color:green">span3</span>
    </body>
    </html>

    ```

    **_출력 결과_**
    span1 span2 span3

  - id, class

    # **개요**

    태그에서 설정한 `id`나 `class` 속성에 따라 스타일을 지정합니다.참고: [HTML 태그의 속성](https://ofcourse.kr/html-course/%ED%83%9C%EA%B7%B8%EC%9D%98-%EC%86%8D%EC%84%B1#id-class-%EC%86%8D%EC%84%B1)
    id 에 줄 경우 아래처럼 `#`을 맨 앞에 붙여 사용하며, 원칙적으로 하나의 객체에만 적용할 수 있습니다.

    ```
    #아이디{ 속성1:속성값; 속성2:속성값; }

    ```

    class에 줄 경우 아래처럼 `.`을 맨 앞에 붙여 사용하며, 여러 객체에 적용할 수 있습니다.

    ```
    .클래스명{ 속성1:속성값; 속성2:속성값 }

    ```

    # **사용법**

    ```
    #m_box{ width:500px; height:300px; }
    .box{ background-color:blue; }

    ```

    # **예제**

    ```
    <html>
    <head>
    <style>
    	#m_box{ background-color: #09C; width: 150px; height: 40px; }
    	.box{ width: 100px; height: 50px; border: 1px solid green }
    </style>
    </head>
    <body>
    	<div class="box">box 클래스</div>
    	<div class="box">box 클래스</div>
    	<div id="m_box">m_box 아이디</div>
    </body>
    </html>

    ```

    ![스크린샷 2023-03-24 오후 6.51.10.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_6.51.10.png>)

  - Markup Language
    # **마크업 언어(Markup Language)란**
    마크업 언어는 태그 등을 이용하여 문서 혹은 데이터의 구조를 기록하는 언어로, `대부분 '기록'의 용도로 사용되기 때문에 프로그래밍 언어로 취급하지는 않는다고 한다.`
    조금 더 풀어서 살펴보기 위해 예를 들어보자면 클라이언트가 잡지를 읽는다고 가정해보자, 이때 1-10페이지 까지는 의류, 11-20 페이지 까지는 액세서리의 내용이 들어있다고 한다면, 이 페이지들은 하나하나 마크업으로 작성이 되어서 존재하는 것이다(인터넷에서는 웹페이지) 이것을 프로그래밍 언어로 각 페이지를 요청에 맞게 방문할 수 있게 하면 그것이 바로 서비스가 된다. 즉 클라이언트가 사용하는 웹서비스는 마크업언어를 기반으로 쌓아 올린 페이지들의 묶음인 것이다.
    가장 대표적인 마크업의 사용 예는 아래의 예시처럼 단순하게 문장 혹은 글자 앞에 태그(여는 태그) 그리고 뒤에 태그(닫는 태그) 등을 사용하여 문서의 문서의 구조를 표현한다.
    ```xml
    <p>TEST TEXT 1</p>
    <span>TEST TEXT 2</span>
    ```
    `여는 태그와 닫는 태그 그리고 그 안의 내용을 합쳐서 Element`라고 하는데 위의 예시에서 `<p> 태그로 감싸져 있는 요소 같은 경우는 p element라고 한다.`
    마크업 언어도 여러 가지가 있는데 일반적으로 세 가지로 종류로 분류가 된다
    **∙ 표현적 마크업 (Presentational Markup)**
    전통적인 워드 처리 시스템이 사용하는 마크업, 즉 문서의 형태를 표현하기 위한 마크업이다. 대표적인 예는 HTML의 style태그를 생각하면 된다, 이 외에도 메모장이나 워드의 제목 앞에 몇 칸의 공백을 넣는 등의 행위도 표현적 마크업의 일종이라고 볼 수 있다.
    **∙ 절차적 마크업 (Procedural Markup)**
    프로그램이 문서를 처리하는 방법을 서술 마크업
    **∙ 기술적 마크업 (Descriptive Markup)**
    가장 많이 사용되는 마크업 언어의 종류이며 문서가 표현하는 내용을 기술한다, 대표적으로는 HTML과 마크업이 있다.
    # **MarkDown Language**
    반대로 MarkDown 언어도 존재한다 간략하게 알아보자면, 흔히 사용하는 .md 확장자 파일이 바로 대표적인 마크다운 언어인데, 주로 SNS의 태그 기능에 사용한다고 한다.
    # **핵심정리**
    웹브라우저가 해독할 수 있도록 문서를 구조화하는 언어가 바로 마크업 언어이다. 이렇게 만들어진 웹페이지가 모여 웹사이트가 되고 클라이언트에게 제공되는 서비스가 된다.
    ### ✅ 참고 자료
    [https://ko.wikipedia.org/wiki/%EB%A7%88%ED%81%AC%EC%97%85\_%EC%96%B8%EC%96%B4](https://ko.wikipedia.org/wiki/%EB%A7%88%ED%81%AC%EC%97%85_%EC%96%B8%EC%96%B4)
    [https://blog.cordelia273.space/15](https://blog.cordelia273.space/15)
    [https://developerjio.tistory.com/entry/%EB%A7%88%ED%81%AC%EC%97%85-%EC%96%B8%EC%96%B4Markup-Language%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94](https://developerjio.tistory.com/entry/%EB%A7%88%ED%81%AC%EC%97%85-%EC%96%B8%EC%96%B4Markup-Language%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94)
    [https://titus94.tistory.com/2](https://titus94.tistory.com/2)
    [https://maenco.tistory.com/entry/WEB-마크업-언어Markup-Language](https://maenco.tistory.com/entry/WEB-%EB%A7%88%ED%81%AC%EC%97%85-%EC%96%B8%EC%96%B4Markup-Language)

- CSS

  - 선택자 (전체 선택자, 그룹 선택자, 가상 클래스 선택자)

    # 기본 선택자

    우리는 지난 시간에 CSS에서는 `선택자`를 통해서 `속성을 줄 대상`을 지정한다고 배웠습니다. 그리고 몇가지 기본적인 선택자(태그, .클래스, #아이디)에대해 알아보았습니다.
    오늘은 지난시간에 배운 기본 선택자 이외에 `전체 선택자`, `그룹선택자`, `가상 클래스 선택자`에 대해 알아보도록 하겠습니다.

    ## 전체 선택자

    전체 선택자는 HTML의 **모든 요소를 선택**합니다.

    ```css
    * {
      property: property value;
    }
    ```

    ## 그룹 선택자

    그룹 선택자는 `여러 선택자를 그룹으로 묶는 기능`입니다.
    보통 그룹 선택자는 중복된 속성을 여러번 반복해서 줄 경우, 선택자를 묶어서 한번에 처리함으로써 코드를 줄여주는 역할을 합니다.

    ```css
    /* 동일한 속성을 반복적으로 사용 */
    h2 {
      color: blue;
    }
    p {
      color: blue;
    }
    div {
      color: blue;
    }
    ```

    ```
    /* 그룹 선택자를 이용해서 한번에 처리 */
    h2, p, div {
    	color : blue
    }

    ```

    코드를 비교해서 보면 아래가 훨씬 깔끔하고 가독성이 좋지 않나요? 여러분도 그룹 선택자를 활용해서 최대한 코드의 중복을 제거하는 연습을 하면 좋다.

    ## 가상 클래스 선택자

  - flex

    - **flex 레이아웃 (flex-direction, justify-content, align-items, 기타 주의점)**

      # flex 레이아웃

      ```c
      display: flex;
      ```

      ## flex-container (display: flex가 적용된 요소)

      ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2011.png>)

      ## flex-direction

      ```css
      flex-direction: row | column;
      ```

      flex-direction 을 이해하려면 flexbox의 중심축 부터 이해해야한다.
      ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2012.png>)
      flexible box가 되면 중심축이 생긴다. 이 중심축은 item 정렬의 기준이되고 flex-direction을 이용하여 방향을 바꿔줄 수 있다. 이것이 지금은 가로방향인데 나중에는 세로 방향으로 변경할 수 있다.

      1. flex-direction : row (기본 값)
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2013.png>)
      1. flex-direction : column
         중심축이 세로로 변경이 된다.
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2014.png>)

      ## justify-content : 중심축 방향 정렬

      ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2015.png>)
      flex-direciton : row 이면 가로방향의 정렬을 결정
      flex-direction : column 이면 세로방향의 정렬을 결정
      우리는 flex-direction의 value 값을 기본값인 row라고 생각하고 justify-content의 여러가지 속성을 실행해보겠다.

      1. justify-content : flex-start (기본 값)
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2016.png>)
         기본값이 flex-start다 컨테이너의 시작점을 기준으로 아이템이 정렬된 것이다.
      1. justify-content: flex-end
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2017.png>)
         flex-end 는 컨테이너의 끝 부분을 기준으로 item 들이 정렬된다.
      1. justify-content: center
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2018.png>)
         말그대로 중앙 정렬이다 해당 중심축을 기준으로해서 center 지점을 기준으로 정렬이 된다.
      1. justify-content : space-between
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2019.png>)
         컨테이너 안에있는 아이템들이 균일한 여백을 두고 배치가 된다는 것을 알 수 있다.
      1. justify-content : space-around
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2020.png>)
         space로 시작하는 속성들 같은 경우에는 item 사이에 적절한 여백을 주면서 컨테이너 안의 아이템들이 균일한 여백을 갖고 배치가 된다.
         space-between 은 startline과 endline에 붙어 있다
         space-around 은 startline과 endline에도 약간의 여백이 들어간다.
      1. justify-content: space-evenly
         space-around는 startline과 endline의 여백과 아이템들 사이의 여백의 크기가 다르다는 것을 알 수 있다. space-evenly를 적용한 이미지를 봐보자
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2021.png>)
         이와 같이 모든 여백이 균일하게 적용되었다. 이러한 것은 카드형 레이아웃을 만들떄 space 계열 속성들이 주로 사용된다.

      ## align-items: 중심축 반대 방향 정렬

      ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2022.png>)
      예시와 같은 경우에는 flex-direction이 row이기에 중심축은 가로방향이다.
      align-items는 그럼 세로방향을 결정한다.

      1. align-item: stretch (기본 값)
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2023.png>)
         stretch 는 쭉 뻗는다는 의미이다. 말그대로 item의 실제 세로사이즈가 어떻든 간에 아이템들을 위로 늘려서 컨테이너 영역을 꽉 채운다.
      1. align-item: flex-start
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2024.png>)
         아까와 마찬가지로 컨테이너의 시작점 기준으로 정렬한다.
      1. align-item: flex-end
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2025.png>)
         컨테이너의 끝 지점을 기준으로 정렬한다.

      ## flex 레이아웃 사용시 주의할 점!

        <aside>
        💡 주의!
        align-items는 flex-item이 한 줄일 떄 우선 적용!
        두 줄 이상일 떄에는 align-content라는 다른 속성을 써주어야 한다.
        
        </aside>
        
        <aside>
        💡 주의 2!
        flex-direction이 바뀌면 중심축의 방향이 바뀐다!
        중심축의 방향이 바뀌면, justify-content와 align-item의 정렬 방향도 함께 바뀌게 된다!
        
        </aside>
        
        즉 주의 2!를 쉽게 이해하자면 아래 이미지를 보자
        
        ![Untitled](Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2026.png)
        
        ![Untitled](Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2027.png)

    - **flex 레이아웃 (flex-wrap, align-content, flex-flow|order, flex-basis, flex shrink 등)**

      # flex 레이아웃 2

      **flex-container에 적용하는 속성(flex-wrap, align-content, flex-flow )**

      ***

      ## flex-wrap

      flex-item이 여러개일 때, item들의 줄바꿈을 허용할 것인지 말 것인지 결정한다.

      ## flex-wrap : nowrap (기본 값)

      ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2028.png>)
      flex-item 의 가로사이즈가 아무리 커도 무조건 한줄안에 들어가도록 강제하는 코드입니다.
      컨테이너가 400px 아이템 하나가 200px 이라하고 8개의 아이템이 들어간다해도 1줄안에 구겨져서라도 컨테이너 안에 들어간다.

      ## flex-wrap: wrap

      ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2029.png>)
      자연스럽게 다음줄로 넘어가게 하는 속성이다.

      ## align-content

      여러 줄이 된 Flex-item의 중심 반대 축 정렬을 어떻게 할 지 결정한다.
      즉, 1줄일떄는 align-item을 사용하고 여러 줄이 된 item들을 정렬할떄는 align-content를 사용한다고 생각하면 된다.

      ## 주의 사항!

      ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2030.png>)

      1. align-content: flex-start

         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2031.png>)

      2. align-content: flex-end
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2032.png>)
      3. align-content: center;
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2033.png>)
      4. align-content: space-between
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2034.png>)
         star 라인과 end 라인에 각각 딱 붙게 됩니다.
      5. align-content: space-around
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2035.png>)
         이 경우에는 축을 따라 아이템을 고르게 배치하는 것은 동일하나 여백의 사이즈가 다르다. 아이템 사이의 여백, 양끝(위,아래)의 여백의 2배 사이즈가 된다.
      6. align-content: space-evenly
         ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2036.png>)
         축을 따라 아이템을 균등하게 배치하고 모든 여백을 균등하게 맞춰준다.

      ## flex-flow(flex-direction +flex-wrap 단축속성)

      `flex-direction`과 `flex-wrap`을 합쳐놓은 `단축 속성`이다.
      아래의 두가지 속성을 한방에 쓸려면 어떻게 해야할까?

      ```css
      flex-direction: row;
      flex-wrap: wrap

      ----------------------------
      // 두가지 속성을 한방에 쓰는 방법
      flex-flow: column wrap
      ```

      `flex-flow: flex-direction 속성, flex-wrap 속성` 이렇게 두가지를 한방에 선언해주면된다.
      지금까지는 flex-container에 적용하는 속성들이다.
      **flex-item에 적용하는 속성(order, flex-basis, flex-shrink, flex-grow 등)**

      ***

      ## order

      item의 순서를 지정하는 속성이다.

      ## flex-basis

      item의 기본 사이즈를 지정해주는 속성이다.

      ## flex-shrink

      두 속성은 "flex-basis" 속성으로 정한 플렉스박스 아이템의 기본 너비를 자동으로 줄어들도록(flex-shrink) 해서 행 안에 적절한 너비로 배치되도록 맞추는 기능을 합니다.

      ## flex-grow

      두 속성은 "flex-basis" 속성으로 정한 플렉스박스 아이템의 기본 너비를 자동으로 늘어나게(flex-grow) 행 안에 적절한 너비로 배치되도록 맞추는 기능을 합니다.

  - grid ‼
    위에서 우리는 flex에 대해서 공부를 했다.
    먼저, 우리는 Flex와 Grid의 가장 큰 차이점을 이해해야 합니다.

    - Flex : 한 방향 레이아웃 시스템 (1차원)
    - Grid : 두 방향(가로-세로) 레이아웃 시스템 (2차원)
      즉, 위와 같은 의미로 더 복잡한 레이아웃 표현이 가능합니다.
      ![스크린샷 2023-03-24 오후 7.19.03.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.19.03.png>)
      Internet Explorer에서는 Grid를 지원하지 않습니다…
      어떻게 쓸 수 있는 방법은 있다고 합니다…
      Fire Fox의 개발자 도구에 > 검사기 에서는 Grid의 구조를 정확히 볼 수 있습니다.
      ![스크린샷 2023-03-24 오후 7.23.30.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.23.30.png>)
      Grid 레이아웃을 만들기 위한 기본적인 HTML 구조는 아래와 같습니다.
      Flex와 마찬가지로, 컨테이너와 아이템이 있으면 Grid를 사용할 수 있습니다.

    ```css
    <div class="container">
    	<div class="item">A</div>
    	<div class="item">B</div>
    	<div class="item">C</div>
    	<div class="item">D</div>
    	<div class="item">E</div>
    	<div class="item">F</div>
    	<div class="item">G</div>
    	<div class="item">H</div>
    	<div class="item">I</div>
    </div>
    ```

    부모 요소인 div.container를 Grid Container(그리드 컨테이너)라고 부른다.
    자식 요소인 div.item을 Grid Item이라고 부른다.
    Container가 Grid의 영향을 받는 전체 공간이고, 설정된 속성에 따라 각각의 아이템들이 어떤 형태로 배치되는 것이라고 생각하면 된다.
    CSS에서 아래와 같이 선언하면 Grid를 사용할 수 있다.

    ```css
    .container {
      display: grid;
    }
    ```

    ### 용어 정리

    ![스크린샷 2023-03-24 오후 7.27.30.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.27.30.png>)

    - 그리드 컨테이너 (Grid Container)
      `display: grid`를 적용하는, Grid의 전체 영역 `.container` 부분 입니다.
      `.container` 안의 `.item`들이 `grid`의 규칙의 영향을 받아 정렬된다고 생각하면 됩니다.
    - 그리드 아이템 (Grid Item)
      `.item` 이 그리드 아이템입니다.
    - 그리드 트랙 (Grid Track)
      Grid의 행(Row), 열(Column)
    - 그리드 셀 (Grid Cell)
      Grid 한 칸을 가리킵니다. <div>같은 실제 html 요소는 그리드 아이템이고, 이런 Grid 아이템 하나가 들어가는 “가상의 칸(틀)”이라고 생각하면 됩니다.
    - 그리드 라인 (Grid Line)
      Grid 셀을 구분하는 선입니다.
    - 그리드 번호 (Grid Number)
      Grid 라인의 각 번호입니다.
    - 그리드 갭 (Grid Gap)
      Grid 셀 사이의 간격.
    - 그리드 영역 (Grid Area)
      Grid 라인으로 둘러싸인 사각형 영역으로, Grid 셀의 집합.
      Grid의 속성은 Flex와 마찬가지로,
    - 컨테이너에 적용하는 속성
    - 아이템에 적용하는 속성
      두가지로 나뉩니다.
      ![스크린샷 2023-03-24 오후 7.32.31.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.32.31.png>)

    ## display: grid;

    Grid Container에 `display: grid;`를 적용하는게 시작이에요.아이템들이 block 요소라면 이 한 줄 만으로는 딱히 변화는 없습니다.

    ```
    .container {
    	display: grid;
    	/* display: inline-grid; */
    }
    /* 그리고 아무 일도 일어나지 않았다 */
    ```

    **inline-grid**도 있는데, 이건 block과 inline-block의 관계를 생각하시면 돼요.아이템의 배치와 관련이 있다기 보다는, 컨테이너가 주변 요소들과 어떻게 어우러질지 결정하는 값입니다. inline-grid는 inline-block처럼 동작해요. 이것 역시 Flex랑 비슷하죠?

    ## 그리드 형태 정의

    grid-template-rowsgrid-template-columnsms-grid-rowsms-grid-columns
    컨테이너에 Grid 트랙의 크기들을 지정해주는 속성입니다.여러가지 단위를 사용할 수 있고 섞어서 쓸 수도 있어요.

    ```
    .container {
    	grid-template-columns: 200px 200px 500px;
    	/* grid-template-columns: 1fr 1fr 1fr */
    	/* grid-template-columns: repeat(3, 1fr) */
    	/* grid-template-columns: 200px 1fr */
    	/* grid-template-columns: 100px 200px auto */

    	grid-template-rows: 200px 200px 500px;
    	/* grid-template-rows: 1fr 1fr 1fr */
    	/* grid-template-rows: repeat(3, 1fr) */
    	/* grid-template-rows: 200px 1fr */
    	/* grid-template-rows: 100px 200px auto */
    }
    ```

    - grid-template-rows는 행(row)의 배치
    - grid-template-columns는 열(column)의 배치를 결정합니다.
      예를 들어

    ```
    grid-template-columns: 200px 200px 500px;
    ```

    는 column을 200px, 200px, 500px로 만들겠다는 의미예요.

    ```
    grid-template-columns: 1fr 1fr 1fr;
    ```

    fr은 fraction인데요, 숫자 비율대로 트랙의 크기를 나눕니다.즉 위의 1fr 1fr 1fr은 균일하게 1:1:1 비율인 3개의 column을 만들겠다는 의미예요.이렇게요↓
    ![스크린샷 2023-03-24 오후 7.35.13.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.35.13.png>)
    고정 크기와 가변 크기를 섞어 쓸 수도 있고요.아래처럼 하면 왼쪽의 첫번째 column은 100px로 고정되고, 나머지 두번째 세번째 column은 2:1의 비율로 유연하게 움직이게 됩니다.

    ```
    grid-template-columns: 100px 2fr 1fr;

    // 첫번쨰 columndms 100x, 나머지 2:1비율로 2개의 columns 생성
    ```

    ![스크린샷 2023-03-24 오후 7.36.36.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.36.36.png>)

    ```css
    grid-template-columns: 1fr 3fr;
    ```

    이렇게 작성하면 어떻게 될까요?
    당연히 속성 값이 2개밖에 없으니 2열이 생성되겠죠?
    ![스크린샷 2023-03-24 오후 7.38.02.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.38.02.png>)

    ### repeat 함수 이용!

    repeat은 반복되는 값을 자동으로 처리할 수 있는 함수입니다.

    ```css
    .container {
      grid-template-columns: repeat(5, 1fr);
      /* grid-template-columns: 1fr 1fr 1fr 1fr 1fr */
    }
    ```

    1fr의 비율로 5열을 만든다고 생각해봅시다.
    `grid-template-columns: 1fr 1fr 1fr 1fr 1fr`
    그럼 이렇게 작성해야하는데, 코딩하는 사람들은 이렇게 길게 작성하는 것을 좋아하지 않습니다.
    이럴떄 활용하는 것이 `repeat function` 입니다.
    `repeat(반복 횟수, 반복 값)`
    위의 양식으로 사용하시면 됩니다. `즉, repeat(5, 1fr)` 이렇게 사용하면 위의 코드와 동일합니다.

    ### **minmax 함수**

    최솟값과 최댓값을 지정할 수 있는 함수입니다.**minmax(100px, auto)**의 의미는 **최소한 100px**, **최대는 자동으로(auto) 늘어나게**.. 입니다. 즉 아무리 내용의 양이 적더라도 `최소한 높이 100px은 확보`하고, 내용이 많아 100px이 넘어가면 알아서 늘어나도록 처리해 준 예시입니다.

    ```css
    .container {
      grid-template-columns: repeat(3, 1fr);
      grid-template-rows: repeat(3, minmax(100px, auto));
    }
    ```

    ![스크린샷 2023-03-24 오후 7.42.15.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.42.15.png>)

    ### **auto-fill과 auto-fit**

    `auto-fill`과 `auto-fit`은 column의 `개수를 미리 정하지 않고 설정된 너비가 허용하는 한 최대한 셀을 채웁니다.`
    auto-fill 먼저 살펴 볼게요.

    ```
    .container {
    	grid-template-columns: repeat(auto-fill, minmax(20%, auto));
    }
    ```

    auto-fill의 크기를 20%로 설정했으므로, 1개의 row에는 5개의 셀이 들어갑니다.
    즉, 위의 코드에서는 크기를 20%로 설정했으므로, 1개의 row에는 5개의 셀이 들어갑니다.
    ![스크린샷 2023-03-24 오후 7.44.16.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.44.16.png>)
    만약에 A부터 D까지 밖에 item이 없다면 어떻게 될까요???
    ![스크린샷 2023-03-24 오후 7.44.44.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.44.44.png>)
    위와 같이 공백 공간이 하나 남게 됩니다.

    ### auto-fit이 뭔데????

    위의 auto-fill과 같은 속성일 경우 공간이 하나 남는다!!!! 그럼 auto-fit인 경우에는 남은 공간을 채워줍니다.
    ![스크린샷 2023-03-24 오후 7.45.52.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.45.52.png>)

    ***

    # 간격 만들기 (row-gap, column-gap, gap)

    그리드와 셀 사이의 간격을 설정합니다.

    ```
    .container {
    	row-gap: 10px;
    	/* row의 간격을 10px로 */
    	column-gap: 20px;
    	/* column의 간격을 20px로 */
    }
    ```

    ```
    .container {
    	gap: 10px 20px;
    	/* row-gap: 10px; column-gap: 20px; */
    }
    ```

    ```
    .container {
    	gap: 20px;
    	/* row-gap: 20px; column-gap: 20px; */
    }
    ```

    1. gap: 0px;

       ![스크린샷 2023-03-24 오후 7.48.56.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.48.56.png>)

    2. gap: 10px;

       ![스크린샷 2023-03-24 오후 7.49.12.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.49.12.png>)

    3. gap: 2rem;

       ![스크린샷 2023-03-24 오후 7.49.23.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.49.23.png>)
       초기에는 앞에 `grid-`를 붙여서 `grid-gap`, `grid-row-gap`, `grid-column-gap`이었는데, 브라우저 호환 범위를 넓히기 위해 아래처럼 이전 버전의 이름과 현재 버전의 이름을 둘 다 쓰기도 해요.

    ```css
    .container {
      grid-gap: 20px;
      gap: 20px;
    }
    ```

    IE에서는 `gap`의 대체 속성이 없기 때문에, IE와 구조를 통일하고 싶으면 아예 처음부터 `gap`을 사용하지 않고 구조를 설계하는게 편해요.

    ## 그리드 형태를 자동으로 정의

    grid-auto-columns, grid-auto-rows
    `grid-template-columns`(또는 `grid-template-rows`)의 통제를 벗어난 위치에 있는 트랙의 크기를 지정하는 속성이에요.속성 이름이 헷갈린다면 -template- 자리에 – auto-가 들어간다고 생각하세요
    “통제를 벗어난”이 무슨 의미일까요? 아까 이 코드 기억 나시나요?

    ```css
    .container {
      grid-template-rows: repeat(3, minmax(100px, auto));
    }
    ```

    각 셀마다 최소 100px의 높이를 확보하고, 컨텐츠가 높이 100px을 넘어가면 알아서 자동으로 늘어나도록(auto) 하려고 저 코드를 썼는데, 우리가 만든 예시가 row가 3개였기 때문에 repeat 회수를 3으로 지정해 줬었지요? 그런데 `row 개수를 미리 알 수 없는 경우면 어떻게 할까요? 바로 이 grid-auto-rows가 그 해결책입니다.`

    ```css
    .container {
      grid-auto-rows: minmax(100px, auto);
    }
    ```

    ![스크린샷 2023-03-24 오후 7.52.06.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.52.06.png>)
    ![스크린샷 2023-03-24 오후 7.52.19.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.52.19.png>)
    이렇게 `grid-auto-rows`를 써주면, 굳이 횟수를 지정해서 반복할 필요 없이 “알아서” 처리됩니다. 즉, `grid-template-rows`로 미리 세팅해 둔 것이 없이 때문에 여기있는 모든 row들은 `grid-template-rows`의 통제를 벗어난 row가 되는 것이고, 바로 `grid-auto-rows`가 처리를 하는 거지요! “통제를 벗어난”의 의미는 바로 이겁니다.

    ## 각 셀의 영역 지정

    grid-column-start, grid-column-end, grid-column
    grid-row-start, grid-row-end, grid-row,
    ms-grid-row, ms-grid-column,
    ms-grid-row-span, ms-grid-column-span
    이 속성들은 Grid **아이템**에 적용하는 속성으로, 각 셀의 영역을 지정합니다.아래 그림을 보면,
    ![https://studiomeal.com/wp-content/uploads/2020/01/07-2.jpg](https://studiomeal.com/wp-content/uploads/2020/01/07-2.jpg)
    1부터 4까지의 Grid 라인 번호가 매겨져 있는데요, 바로 그 번호를 이용해서 column과 row의 범위를 결정하는 겁니다.
    column으로 살펴보면, grid-column-start가 시작 번호, grid-column-end가 끝 번호입니다. grid-column은 start와 end 속성을 한번에 쓰는 축약형입니다.
    위의 빨간색 영역을 코드로 쓰면 아래와 같아요. 이 두 코드↓는 같은 영역을 지정합니다.

    ```css
    .item:nth-child(1) {
      grid-column-start: 1;
      grid-column-end: 3;
      grid-row-start: 1;
      grid-row-end: 2;
    }
    ```

    ```css
    .item:nth-child(1) {
      grid-column: 1 / 3;
      grid-row: 1 / 2;
    }
    ```

    이렇게 설정하면 영역은 이렇게↓ 됩니다.
    ![스크린샷 2023-03-24 오후 7.55.53.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.55.53.png>)
    시작번호 / 끝번호를 지정하는 방법 외에, **몇 개의 셀을 차지하게 할 것인지**를 지정해줄 수도 있어요.

    ```css
    .item:nth-child(1) {
      /* 1번 라인에서 2칸 */
      grid-column: 1 / span 2;
      /* 1번 라인에서 3칸 */
      grid-row: 1 / span 3;
    }
    ```

    ![스크린샷 2023-03-24 오후 7.57.10.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.57.10.png>)
    여기서 잠깐 위에서 공부했던 grid-auto-columns를 다시 볼게요.
    grid-auto-columns는 grid-template-columns의 통제를 받지 않는 column들의 배치를 결정하는 규칙이라고 했는데요, 이 grid-column을 이용해 ‘통제받지 않는’ column들을 만들 수 있어요.

    ```css
    .container {
      grid-template-columns: 50px;
      grid-auto-columns: 1fr 2fr;
    }
    .item:nth-child(1) {
      grid-column: 2;
    }
    .item:nth-child(2) {
      grid-column: 3;
    }
    .item:nth-child(3) {
      grid-column: 4;
    }
    .item:nth-child(4) {
      grid-column: 5;
    }
    .item:nth-child(5) {
      grid-column: 6;
    }
    .item:nth-child(6) {
      grid-column: 7;
    }
    /* end를 생략하면 그냥 한 칸임 */
    ```

    이렇게 하면, 첫번째 column(G)만 grid-template-columns의 통제를 받아 50px로 되고, 나머지 column들은 grid-auto-columns의 규칙에 따라 1:2의 비율이 반복됩니다.이렇게요↓
    ![스크린샷 2023-03-24 오후 7.57.54.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.57.54.png>)

    ## 영역 이름으로 그리드 정의 grid-template-areas

    각 영역(Grid Area)에 이름을 붙이고, 그 이름을 이용해서 배치하는 방법입니다.정말 직관적인 방법이에요.아래의 그림↓에서 각 셀에 매칭되는 이름을 어떤 식으로 썼는지 살펴 보세요.
    ![https://studiomeal.com/wp-content/uploads/2020/01/08-2.jpg](https://studiomeal.com/wp-content/uploads/2020/01/08-2.jpg)

    ```
    .container {
    	grid-template-areas:
    		"header header header"
    		"   a    main    b   "
    		"   .     .      .   "
    		"footer footer footer";
    }
    ```

    위의 형태로 각자 차지하는 셀의 개수만큼 해당 위치에 이름을 써주면 됩니다.각 셀마다 공백을 하나씩 넣어서 구분해주시면 되고요.header는 첫번째 row에서 3개의 column을 차지하니 맨 위에 3번 쓴 것, 이해 되시죠?빈칸은 마침표 또는 “none”을 사용하면 되고, 마침표의 개수는 여러개를 써도 상관 없습니다.
    그럼 각 영역의 이름은 어떻게 매칭할까요? **해당 아이템** 요소에 **grid-area** 속성으로 이름을 지정해주면 됩니다!예를 들면 이런↓ 식이 되겠지요.

    ```
    .header { grid-area: header; }
    .sidebar-a { grid-area: a; }
    .main-content { grid-area: main; }
    .sidebar-b { grid-area: b; }
    .footer { grid-area: footer; }
    /* 이름 값에 따옴표가 없는 것에 주의하세요 */
    ```

    ## 자동 배치grid-auto-flow

    아이템이 자동 배치되는 흐름을 결정하는 속성입니다.

    ```
    .container {
    	display: grid;
    	grid-template-columns: repeat(auto-fill, minmax(25%, auto));
    	grid-template-rows: repeat(5, minmax(50px,auto));
    	grid-auto-flow: dense;
    }
    item:nth-child(2) { grid-column: auto / span 3; }
    item:nth-child(5) { grid-column: auto / span 3; }
    item:nth-child(7) { grid-column: auto / span 2; }
    ```

    B, E, G는 각각 셀을 3개 또는 2개를 점유하도록 설정했는데요, 그 때문에 셀에 들어갈 자리가 없어서 빈 셀들이 생겼습니다. Grid 배치의 기본 설정은 아이템이 **row**를 기준으로 순서대로 배치가 되다가 들어갈 자리가 없으면 그 칸은 비워두고 아래로 배치가 됩니다.dense는 기본적으로 빈 셀을 채우는 알고리즘이며, row와 column에 따라 기준이 달라집니다.
    ![스크린샷 2023-03-24 오후 7.58.47.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.58.47.png>)
    ![스크린샷 2023-03-24 오후 7.58.55.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.58.55.png>)
    ![스크린샷 2023-03-24 오후 7.59.02.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.59.02.png>)
    ![스크린샷 2023-03-24 오후 7.59.35.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.59.35.png>)
    ![스크린샷 2023-03-24 오후 7.59.40.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.59.40.png>)
    자, 이제 정렬입니다.

    ## 세로 방향 정렬align-items

    아이템들을 세로(column축) 방향으로 정렬합니다. 컨테이너에 적용합니다.

    ```
    .container {
    	align-items: stretch;
    	/* align-items: start; */
    	/* align-items: center; */
    	/* align-items: end; */
    }
    ```

    ![스크린샷 2023-03-24 오후 8.00.24.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_8.00.24.png>)
    ![스크린샷 2023-03-24 오후 8.00.31.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_8.00.31.png>)
    ![스크린샷 2023-03-24 오후 8.01.37.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_8.01.37.png>)
    ![스크린샷 2023-03-24 오후 8.01.59.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_8.01.59.png>)

    ## 가로 방향 정렬justify-items

    아이템들을 가로(row축) 방향으로 정렬합니다. 컨테이너에 적용합니다.

    ```
    .container {
    	justify-items: stretch;
    	/* justify-items: start; */
    	/* justify-items: center; */
    	/* justify-items: end; */
    }
    ```

    ![스크린샷 2023-03-24 오후 8.03.10.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_8.03.10.png>)
    ![스크린샷 2023-03-24 오후 8.03.18.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_8.03.18.png>)
    ![스크린샷 2023-03-24 오후 8.03.26.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_8.03.26.png>)
    ![스크린샷 2023-03-24 오후 8.03.32.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_8.03.32.png>)

    ## place-items

    align-items와 justify-items를 같이 쓸 수 있는 단축 속성이에요.align-items, justify-items의 순서로 작성하고, 하나의 값만 쓰면 두 속성 모두에 적용됩니다.

    ```
    .container {
    	place-items: center start;
    }
    ```

    ***

    content는 이제 그룹으로 정렬한다고 생각하면됩니다. 따로 이미지는 첨부하지 않을 거지만,
    ![스크린샷 2023-03-24 오후 8.04.44.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_8.04.44.png>)
    이런 느낌으로 이제 다같이 움직인다고 생각하면 됩니다.

    ## 아이템 그룹 세로 정렬align-content

    Grid 아이템들의 높이를 모두 합한 값이 Grid 컨테이너의 높이보다 작을 때 Grid 아이템들을 통째로 정렬합니다.

    ```
    .container {
    	align-content: stretch;
    	/* align-content: start; */
    	/* align-content: center; */
    	/* align-content: end; */
    	/* align-content: space-between; */
    	/* align-content: space-around; */
    	/* align-content: space-evenly; */
    }
    ```

    ## 아이템 그룹 가로 정렬justify-content

    Grid 아이템들의 너비를 모두 합한 값이 Grid 컨테이너의 너비보다 작을 때 Grid 아이템들을 통째로 정렬합니다.

    ```
    .container {
    	justify-content: stretch;
    	/* justify-content: start; */
    	/* justify-content: center; */
    	/* justify-content: end; */
    	/* justify-content: space-between; */
    	/* justify-content: space-around; */
    	/* justify-content: space-evenly; */
    }
    ```

    ## place-content

    align-content와 justify-content를 같이 쓸 수 있는 단축 속성이에요.align-content, justify-content의 순서로 작성하고, 하나의 값만 쓰면 두 속성 모두에 적용됩니다.

    ```
    .container {
    	place-content: space-between center;
    }
    ```

    ## 개별 아이템 세로 정렬align-self ms-grid-row-align

    해당 아이템을 세로(column축) 방향으로 정렬합니다. 아이템에 적용합니다.

    ```
    .item {
    	align-self: stretch;
    	/* align-self: start; */
    	/* align-self: center; */
    	/* align-self: end; */
    }
    ```

    ![스크린샷 2023-03-24 오후 8.05.29.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_8.05.29.png>)

    ## 개별 아이템 가로 정렬justify-selfms-grid-column-align

    해당 아이템을 가로(row축) 방향으로 정렬합니다. 아이템에 적용합니다.

    ```
    .item {
    	justify-self: stretch;
    	/* justify-self: start; */
    	/* justify-self: center; */
    	/* justify-self: end; */
    }
    ```

    ![스크린샷 2023-03-24 오후 8.05.48.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_8.05.48.png>)

    ## place-self

    align-self와 justify-self를 같이 쓸 수 있는 단축 속성이에요.align-self, justify-self의 순서로 작성하고, 하나의 값만 쓰면 두 속성 모두에 적용됩니다.

    ```
    .item {
    	place-self: start center;
    }
    ```

    ## 배치 순서order

    각 아이템들의 시각적 나열 순서를 결정하는 속성이에요.숫자값이 들어가며, 작은 숫자일 수록 먼저 배치됩니다. "시각적" 순서일 뿐, HTML 자체의 구조를 바꾸는 것은 아니므로 접근성 측면에서 사용에 주의하셔야 합니다. 시각 장애인분들이 사용하는 스크린 리더로 화면을 읽을 때, order를 이용해 순서를 바꾼 것은 의미가 없다는 것을 기억해 주세요.

    ```
    .item:nth-child(1) { order: 3; } /* A */
    .item:nth-child(2) { order: 1; } /* B */
    .item:nth-child(3) { order: 2; } /* C */
    ```

    ![스크린샷 2023-03-24 오후 8.06.12.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_8.06.12.png>)

    ## z-index

    z-index로 Z축 정렬을 할 수 있어요. 숫자가 클 수록 위로 올라옵니다.(position에서의 z-index랑 똑같이 생각하시면 됩니다.)

    ```
    .item:nth-child(5) {
    	z-index: 1;
    	transform: scale(2);
    }
    /* z-index를 설정 안하면 0이므로, 1만 설정해도 나머지 아이템을 보다 위로 올라온다 */
    ```

    ![스크린샷 2023-03-24 오후 8.06.32.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_8.06.32.png>)

    # ✅ 참고 자료

    [이번에야말로 CSS Grid를 익혀보자](https://studiomeal.com/archives/533)
    끝으로, IE(인터넷 익스플로러) 10, 11에서 사용할 수 있는 Grid 속성을 알려드릴게요.한계는 있지만, 적절히 사용하면 충분히 상용 서비스에도 적용할 수 있습니다![IE에서 지원하는 고인물 스펙 참고](https://www.w3.org/TR/2011/WD-css3-grid-layout-20110407/)
    [제목 없음](https://www.notion.so/db394860d387465097c7918e019dde8e)

  - font-size (폰트에 관한 기타 속성들…추가)

    ### font-size

    텍스트의 크기를 지정한다.

    ```css
    font-size: 18px;
    ```

    ### font-weight

    텍스트의 두께를 지정한다.
    bold, regular 처럼 키워드를 이용해도 되고
    600, 700, 800등 숫자를 이용해도 된다.

    ```css
    font-weight: 600;
    ```

    ### text-decoration

    텍스트에 장식용 선을 추가한다.

    ```css
    text-decoration: underline;
    ```

    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2037.png>)
    다음은 자주 사용되는 속성 3가지이다. 더 많은 속성이 있으므로 궁금하면 MDN에 들어가보자.
    text-decoration: none; 도 자주 사용하니 알아두자.

    ### line-height

    텍스트의 행간을 설정한다.

    ```css
    line-height: 1.8;
    ```

    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2038.png>)

    ### letter-spacing

    텍스트의 자간을 설정한다.

    ```css
    letter-spacing: 0.1rem;
    ```

    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2039.png>)
    기본 값은 normal 이다. 속성 값에 양수를 넣으면 normal + 양수 값이다.
    속성 값에 음수를 넣으면 normal - 음수값이다.

    ### word-spacing

    텍스트의 단어(한 어절과 어절) 간 간격을 지정한다.

    ```css
    word-spacing: 2px;
    ```

    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2040.png>)

    ### text-align

    블록요소나 표 안에서 텍스트의 가로 정렬 방식을 지정한다.

    ```css
    text-align: center;
    ```

    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2041.png>)
    이 속성 외에도 justify 라는 속성이다. 양측 정렬을 의미한다.
    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2042.png>)
    left의 경우에는 텍스트의 우측 부분이 ‘쌍떡’ 이부분이나 오른쪽 부분이 울퉁불퉁하다.
    justify 같은 경우에는 각각의 라인에 있는 좌측, 우측 라인을 올바르게 정리해주었다.
    보기에는 깔끔하다. 하지만 띄어쓰기의 규격이 서로 다르기 떄문에 장문일 경우 시각적인 입장에서 별로이다.
    실무에서는 디자이너들과 상의가 필요한 부분이다.

    ### vertical-align

    인라인 요소나 표 안에서 텍스트의 세로 정렬 방식을 지정한다.

    ```css
    vertical-align: middle;
    ```

    text-align은 가로방향의 정렬이였다면 vertical-align은 세로 방향이다. text-align은 block 요소나 표 요소 안에서만 적용이 가능했다면, vertical align은 inline 요소 표 안에서만 적용이 가능합니다.
    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2043.png>)

    ### text-indent

    텍스트의 들여쓰기를 설정한다.

    ```css
    text-indent: 10%;
    ```

    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2044.png>)
    양수, 음수 값 둘다 가능하다.

    ### text-transform

    영문 텍스트의 대/소문자를 바꿀 수 있습니다.

    ```css
    text-transform: capitalize;
    ```

    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2045.png>)

    ### word-break

    텍스트가 콘텐츠 박스 영역 밖으로 넘쳤을 때, 어떻게 줄을 바꿀지 설정합ㄴ디ㅏ.

    ```css
    word-break: keep-all | break-all |;
    ```

    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2046.png>)
    `keep-all`인 경우에는 어절을 기준으로 줄바꿈을 합니다 즉, 띄어쓰기를 기준으로 enter를 친다고 생각.
    `break-all`인 경우에는 음절(한 단어, 한 단어)을 기준으로 줄바꿈을 합니다. 한 단어를 기준으로 줄바꿈을 해준다고 생각하면 됩니다.

    ### overflow-wrap

    단어가 콘텐츠 박스 영역 밖으로 넘쳤을 떄, 줄바꿈 여부를 설정합니다.

    ```css
    overflow-wrap: normal | break-word;
    ```

    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2047.png>)
    normal의 경우 watarmelon 을 보면 keep-all 은 박스에 글씨가 넘어도 이 단어를 끊지를 못한다.
    break-word의 경우에는 박스에 글씨가 넘어도 이 단어를 끊을 수 있다.

    ### overflow-wrap vs word-break

    둘의 차이는 그럼 무엇일까?
    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2048.png>)
    break-all의 경우에는 모든 단어를 음절단위로 쪼개게 됩니다. 그래서 예시와 같은 문장의 경우 오히려 문단을 읽기 불편해진다. W랑 A가 뚝 끊겼기 떄문이다. 가독하기가 나쁘다.
    break-word는 기본적으로 keep-all과 비슷한 느낌이다. 단 한가지 단어가 길어서 지정된 영역을 벗어나는 경우에만 그 단어를 쪼개서 다음줄로 내리게 됩니다. 이것이 가독성을 챙기면서 동시에 레이아웃도 깔끔하게 만들기 때문에 장문의 글을 다루는 웹페이지/블로그 플랫폼에서 많이 사용한다.

    ### overflow

    콘텐츠가 커서 요소 안에서 내용을 다 보여주기 힘들 떄, 어떤 방식으로 보여줄지 설정합니다.

    ```css
    overflow: visible | hidden | scroll | auto;
    ```

    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2049.png>)
    visible인 경우 콘텐츠가 영역에 벗어나도 그냥 자르지 않고 다 보이도록 내버려 둔다.
    hidden의 경우 넘쳐나는 영역은 잘라서 안보이도록 한다.
    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2050.png>)
    scroll 은 스크롤을 통해 글을 볼 수 있게 해준다. (해당 요소안에 강제로 스크롤 바를 넣어준다 세로, 가로 둘다, 규격이 적어도 스크롤 바를 무조건 노출한다.)
    auto의 경우 내용의 규격이 적을떄는 스크롤바를 안보여주고, 내용의 규격이 클때에는 스크롤바를 보여준다.

    ### text-overflow

    줄바꿈을 하지 않을 떄, 요소 밖으로 넘치는 text를 어떻게 표기할 것인지 설정합니다.

    ```css
    text-overflow: clip | ellipsis;
    ```

    주의!
    text-overflow를 적용하고 싶은 요소에는 반드시 다음 선언들도 함께 적용되어야 합니다.

    ### text-overflow 선행 조건

    ```css
    /* text가 박스 밖을 넘칠 경우 자동으로 줄바꿈을 해줬는데 nowrap을 해줄경우 줄바꿈 x */
    white-space: nowrap;

    overflow: hidden;
    ```

    ![Untitled](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/Untitled%2051.png>)
    위와 같이 작동된다.
    `clip`이라는 속성을 주게되면 그냥 텍스트가 길어지면 뚝 끊어버린다.
    `ellipsis`라는 속성을 주게되면 … 이라는 말줄임표를 사용해서 텍스트가 자연스럽게 생략되는 것처럼 표현할 수 있다.

  - color
    ### color
    텍스트의 색을 지정한다. 3가지 사용방법이 있다.
    ```css
    /* 첫번쨰 방법: 색깔명 */
    color: red
    /* 두번쨰 방법: 헥스코드 */
    color: #5145d8;
    /* 세번쨰 방법: rgb값 사용 */
    color: rgb(213,229,37)
    ```
  - margin, padding
    # margin, padding
    # **개요**
    `margin`과 `padding` 속성은 각각 **바깥쪽 여백**, **안쪽 여백**을 의미합니다.`width`, `height` 속성과 마찬가지로 숫자 뒤에 단위를 표시하여 적습니다.
    `margin`과 `padding`는 `[border](https://ofcourse.kr/css-course/border-%EC%86%8D%EC%84%B1)` 을 경계로 나뉩니다.
    ![스크린샷 2023-03-24 오후 7.12.28.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-24_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_7.12.28.png>)
    # **방향**
    방향마다 여백을 다르게 설정할 수 있습니다.
    - `margin: 20px` 같은 표현은 상하좌우 모두 20px을 의미합니다
    - `margin: 30px 10px`은 상하 30px, 좌우 10px을 의미합니다.
    - `margin: 30px 10px 20px 50px`은 위 30px, 오른쪽 10px, 아래 20px, 왼쪽 50px을 의미합니다.
    - `margin: 30px 10px 40px`은 위 30px, 좌우 10px, 아래 40px을 의미합니다.
      즉 방향의 위부터 시계방향으로 회전하여 `위 오른쪽 아래 왼쪽` 순서로 설정합니다.
    ### **✅ 참고자료**
    [CSS margin,padding 속성 - ofcourse](https://ofcourse.kr/css-course/margin-padding-속성)
  - position
    HTML 요소가 배치되는 방식을 결정하는 속성
    postion을 배우기에 앞서서 우리는 top / left / bottom / right 에 대해 이해하고 있어야 한다.

    ### top/left/bottom/right

    해당 방향 기준으로 요소의 좌표값을 변경한다.

    ### static (기본값)

    요소를 문서상 원래 있어야 하는 위치에 배치한다.
    top/left/bottom/right 적용이 불가하다.
    ![스크린샷 2023-01-11 오후 5.37.08.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-01-11_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_5.37.08.png>)
    코드 안에는 top과 left가 실행되어 있지만 실행되지 않는다.

    ### relative

    원래 있던 자리를 기준으로 요소의 위치를 조정할 수 있다.
    top/left/bottom/right 적용이 가능하다.
    ![스크린샷 2023-01-11 오후 5.38.29.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-01-11_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_5.38.29.png>)
    기존에 있던 자리에서 위쪽에서 30px , 왼쪽에서 30px 이렇게 이동한 것을 확인할 수 있다. 다른 static 요소들과 겹쳐질 수 도 있다.

    ### absolute

    절대 좌표를 기준으로 요소의 위치를 조정할 수 있다.
    top/left/bottom/right 적용 가능
    ![스크린샷 2023-01-11 오후 5.40.21.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-01-11_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_5.40.21.png>)
    절대좌표가 기준이 된다. 절대 좌표가 측정되는 기준은

    1. absolute 가 적용된 요소의 부모 요소 중 relative 가 적용된 요소를 찾아서 그 요소를 절대 좌표의 기준으로 삼는다.

    1. 상위의 relative한 속성을 가진 요소가 없다면, 부모의 요소는 html의 body 전체이다.
       아래에서 한번 absolute를 실습해보면 조금 더 이해가 쉬울 것이다.

    ### absolute 실습

    ```html
    <body>
      <div class="container">
        여기는 컨테이너 입니다.
        <div class="wrapper">
          여기는 컨테이너 안 입니다.
          <div class="item">여기는 가장 안쪽의 아이템 박스 입니다.</div>
        </div>
      </div>
    </body>
    ```

    ```css
    * {
      box-sizing: border-box;
    }

    .container {
      border: 3px solid red;
      padding: 10px;
    }

    .wrapper {
      border: 3px solid blue;
      padding: 10px;
    }

    /* 실질적으로 absolute 적용할 곳 */
    .item {
      background-color: orange;
      width: 200px;
      height: 100px;
    }
    ```

    위와 같이 코드를 적용 시켰을때
    ![스크린샷 2023-01-11 오후 5.54.42.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-01-11_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_5.54.42.png>)
    이러한 예시가 나온다.

    1. item의 부모 요소가 relative가 없는 경우(즉, body를 기준)

    ```css
    .item {
      background-color: orange;
      width: 200px;
      height: 100px;
      position: absolute;
      top: 0;
      left: 0;
    }
    ```

    body를 기준으로 위로부터 0px, 왼쪽으로부터 0px이기에 왼쪽 모서리에 딱 붙어있는 오랜지색 상자가 화면에 출력될 것이다.
    ![스크린샷 2023-01-11 오후 6.00.13.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-01-11_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_6.00.13.png>)

    1. container에 relative 속성을 주었을떄.

    ```css
    .container {
      border: 3px solid red;
      padding: 10px;
      position: relative;
    }
    ```

    컨테이너를 기준으로 하므로, 컨테이너 상자에 딱 달라 붙을 것이다.
    ![스크린샷 2023-01-11 오후 5.59.47.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-01-11_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_5.59.47.png>)

    1. container, wrapper 에다 모두 position: relative를 설정한 경우

    ```css
    .container {
      border: 3px solid red;
      padding: 10px;
      position: relative;
    }

    .wrapper {
      border: 3px solid blue;
      padding: 10px;
      position: relative;
    }

    /* 실질적으로 absolute 적용할 곳 */
    .item {
      background-color: orange;
      width: 200px;
      height: 100px;
      position: absolute;
      top: 0;
      left: 0;
    }
    ```

    ![스크린샷 2023-01-11 오후 6.01.37.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-01-11_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_6.01.37.png>)
    파란색 상자 (wrapper)를 기준으로 한다.
    여러 개의 relative 가 설정되있을떄 가까운 조상을 찾아서 그 것을 절대적인 기준으로 좌표를 측정한다.

    ### fixed (스크롤 내려도 고정)

    스크롤과 무관하게 뷰포트를 기준으로 요소의 위치를 설정할 수 있다. `(기준 : viewport)`
    ![스크린샷 2023-01-11 오후 6.04.47.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-01-11_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_6.04.47.png>)
    스크롤을 내려도 저 빨간색 박스의 position은 해당하는 위치에 고정시켜 놓을 수 있다.

    ### sticky

    요소의 원래 위치에 있다가 스크롤이 내려가면 지정한 좌표에 고정됩니다.
    `기준: 부모 요소의 좌표`
    ![스크린샷 2023-01-11 오후 6.06.35.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-01-11_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_6.06.35.png>)
    스크롤이 내려가기 전 즉, 현재와 같은 상태일떄 static과 같은 위치 상태를 같고 있다가, 스크롤할시에 이제
    ![스크린샷 2023-01-11 오후 6.04.47.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-01-11_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_6.04.47%201.png>)
    위와 같이 sticky되었던 빨간 상자가 올라간 것을 확인할 수 있다.

    ***

    ### z-index

## 📢 학습 후기

---

- 이번 주차 워크북을 해결해보면서 어땠는지 회고해봅시다.
- 핵심 키워드에 대해 완벽하게 이해했는지? 혹시 이해가 안 되는 부분은 뭐였는지?

<aside>
📢 CSS Grid (flex만 사용해서, Grid를 사용해볼려니까 어렵다.)

</aside>

## ⚠️ 스터디 진행 방법

---

1. 스터디를 진행하기 전, 워크북 내용들을 모두 채우고 스터디에서는 서로 모르는 내용들을 공유해주세요.
2. 미션은 워크북 내용들을 모두 완료하고 나서 스터디 전/후로 진행해보세요.
3. 다음주 스터디를 진행하기 전, 지난주 미션을 서로 공유해서 상호 피드백을 진행하시면 됩니다.

## ✅ 실습 체크리스트

---

- [x] Web에 대한 본인만의 문서 정리를 해보세요.
- [x] vscode를 사용하는 것 부터 시작해서 파일 만들고 실행하고 확인하는 법 등 본격적인 코딩을 시작하기전 환경 설정을 완료하세요.
- [x] html, css, javascript의 전체적인 구조를 직접 만들어가며 프로젝트 구조를 익혀보세요.

## ☑️ 실습 인증 파트

---

- Web에 대한 본인만의 문서 정리를 해보세요.
  ✅ 핵심 키워드 부분에 정리했습니다.
- vscode를 사용하는 것 부터 시작해서 파일 만들고 실행하고 확인하는 법 등 본격적인 코딩을 시작하기전 환경 설정을 완료하세요.
  ✅
- html, css, javascript의 전체적인 구조를 직접 만들어가며 프로젝트 구조를 익혀보세요.
  ✅

## 🔥 미션

---

1. 학습한 HTML, CSS의 개념을 모두 사용하여 **서비스를 하나 클론코딩** 해오기
   - ✅ [넷플릭스](https://www.netflix.com/kr/) 홈 화면 구현!
     [https://github.com/dydals3440/UMC/tree/main/UMC 1주차](https://github.com/dydals3440/UMC/tree/main/UMC%201%EC%A3%BC%EC%B0%A8)
   - [번개장터](https://m.bunjang.co.kr/)
   - [마켓컬리](https://www.kurly.com/shop/main/index.php)
   - [에어비엔비](https://www.airbnb.co.kr/)
   - [원티드](https://www.wanted.co.kr/)
   - [인프런](https://www.inflearn.com/)

<aside>
👨🏻‍💻 [ 클론코딩 미션 팁 ]

- **먼저 화면 리스트를 나열하고, 중요해 보이는 화면 순으로 작업을 시작합니다.** 유튜브를 예시로 들면 맨 처음 나오는 홈 화면, 동영상 상세 보기화면, 좋아요 표시한 화면 등이 있고, '나는 홈화면 → 상세보기 화면 → 좋아요 표시한 화면 순으로 작업해야지 !' 라고 본인만의 기준으로 순서를 정한 후 작업 합니다.

- **한 화면을 만들 때 html,css 80% javascript 20%로 작업을 합니다.** 즉, 자바스크립트의 기능에 신경을 많이 쓰기보다 웹의 화면(html, css)을 보다 더 실제 서비스처럼 만드는 것에 집중합니다.

- **실제 이미지, 아이콘등을 보고싶다면 크롬 개발자도구 > 네트워크 탭에 접속하신 후 웹 페이지를 새로고침 해보시면 확인할 수 있습니다.** 해당 데이터들을 사용한다면 더욱 더 실제 웹사이트 같아지겠죠 ~?

- 웹을 만들 때 큰 숲을 먼저 보고 그 후 나무를 본다는 느낌으로, **웹 사이트의 구조를 네모난 상자들의 집합들 이라 생각 하고, 큰 상자들 안에 작은 상자들이 어떻게 배치되어 있는 가를 먼저 파악을 하고 코드 작성을 시작합니다.** (div에 border를 줘서 눈으로 직접 레이아웃을 확인해가며 작업 하면 좋아요 :D)

- 반응형 코딩까지 다루면 물론 좋지만, 기본 PC 화면 퍼블리싱 하는것에도 시간이 많이 부족할 것 이므로 반응형 코딩은 **최소 화면을 3개 이상** 만드신 후 시간이 남는다면 도전해보는 것을 추천합니다:)

</aside>

## ⚡ 트러블 슈팅

---

<aside>
💡 실습하면서 생긴 문제들에 대해서, **이슈 - 문제 - 해결** 순서로 작성해주세요.

</aside>

<aside>
💡 스스로 해결하기 어렵다면? 스터디원들에게 도움을 요청하거나 **너디너리의 지식IN 채널에 질문**해보세요!

</aside>

- ⚡이슈 No.1 (예시, 서식만 복사하시고 지워주세요.)
  **`이슈`**
  👉 Grid 학습
  **`문제`**
  👉 Grid의 여러가지 속성들을 정확하게 이해하기 어렵다.
  **`해결`**
  👉 인터넷 검색을 통해 재정리하는 시간을 갖었다, flex말고도 grid로 구조를 짜보는 연습을 더 해봐야겠다.
  **`참고레퍼런스`**
  👉
  [이번에야말로 CSS Grid를 익혀보자](https://studiomeal.com/archives/533)

## 🤔 이것도 한 번 생각해봐요!

---

- 프로젝트를 만들어가면서 불편한 점은 없었나요?
  **`이슈`**
  👉 Netflix accordion을 순수 HTML CSS 만으로 제작해보기
  [화면 기록 2023-03-22 오후 1.43.37.mov](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2592%25E1%2585%25AA%25E1%2584%2586%25E1%2585%25A7%25E1%2586%25AB_%25E1%2584%2580%25E1%2585%25B5%25E1%2584%2585%25E1%2585%25A9%25E1%2586%25A8_2023-03-22_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_1.43.37.mov>)
  **`문제`**
  👉 Bootstrap 없이 어떻게 만들어야 할지 감이 안잡혔다.
  **`해결`**
  👉 `input type = “radio”`을 활용하여 만들었다.

  ```html
  <ul class="accordion">
    <li>
      <input type="radio" name="accordion" id="first" />
      <label for="first">넷플릭스에서 어떤 콘텐츠를 시청할 수 있나요? </label>
      <div class="content">
        <p>
          넷플릭스는 장편 영화, 다큐멘터리, 시리즈, 애니메이션, 각종 상을 수상한 넷플릭스 오리지널
          등 수많은 콘텐츠를 확보하고 있습니다. 마음에 드는 콘텐츠를 원하는 시간에 원하는 만큼
          시청하실 수 있습니다.<br /><br />
          넷플릭스 콘텐츠를 한번 살펴보세요.
        </p>
      </div>
    </li>
    <li>
      <input type="radio" name="accordion" id="second" />
      <label for="second">넷플릭스란 무엇인가요?</label>
      <div class="content">
        <p>
          넷플릭스는 각종 수상 경력에 빛나는 시리즈, 영화, 애니메이션, 다큐멘터리 등 다양한 콘텐츠를
          인터넷 연결이 가능한 수천 종의 디바이스에서 시청할 수 있는 스트리밍 서비스입니다.<br /><br />
          저렴한 월 요금으로 원하는 시간에 원하는 만큼 즐길 수 있습니다. 무궁무진한 콘텐츠가
          준비되어 있으며 매주 새로운 시리즈와 영화가 제공됩니다.
        </p>
      </div>
    </li>
    <li>
      <input type="radio" name="accordion" id="third" />
      <label for="third">넷플릭스 요금은 얼마인가요?</label>
      <div class="content">
        <p>
          스마트폰, 태블릿, 스마트 TV, 노트북, 스트리밍 디바이스 등 다양한 디바이스에서 월정액 요금
          하나로 넷플릭스를 시청하세요. 멤버십 요금은 월 5,500원부터 17,000원까지 다양합니다. 추가
          비용이나 약정이 없습니다.
        </p>
      </div>
    </li>
    <li>
      <input type="radio" name="accordion" id="fourth" />
      <label for="fourth">광고형 멤버십은 뭐가 다른가요?</label>
      <div class="content">
        <p>
          광고형 멤버십은 저렴한 요금으로 영화와 시리즈를 즐길 수 있는 방법입니다. 제한된 수의 중간
          광고와 함께 좋아하는 콘텐츠를 스트리밍할 수 있습니다(일부 위치 및 디바이스 제한 적용).
          저장 기능은 지원되지 않으며, 라이선스 제한으로 인해 일부 영화와 시리즈를 이용할 수
          없습니다. 자세히 알아보기.
        </p>
      </div>
    </li>
    <li>
      <input type="radio" name="accordion" id="fifth" />
      <label for="fifth">어디에서 시청할 수 있나요?</label>
      <div class="content">
        <p>
          언제 어디서나 시청할 수 있습니다. 넷플릭스 계정으로 로그인하면 PC에서 netflix.com을 통해
          바로 시청할 수 있으며, 인터넷이 연결되어 있고 넷플릭스 앱을 지원하는 디바이스(스마트 TV,
          스마트폰, 태블릿, 스트리밍 미디어 플레이어, 게임 콘솔 등)에서도 언제든지 시청할 수
          있습니다.<br />
          <br />iOS, Android, Windows 10용 앱에서는 좋아하는 시리즈를 저장할 수도 있습니다. 저장
          기능을 이용해 이동 중이나 인터넷에 연결할 수 없는 곳에서도 시청하세요. 넷플릭스는 어디서든
          함께니까요.
        </p>
      </div>
    </li>
    <li>
      <input type="radio" name="accordion" id="sixth" />
      <label for="sixth">멤버십을 해지하려면 어떻게 하나요?</label>
      <div class="content">
        <p>
          넷플릭스는 부담 없이 간편합니다. 성가신 계약도, 약정도 없으니까요. 멤버십 해지도
          온라인에서 클릭 두 번이면 완료할 수 있습니다. 해지 수수료도 없으니 원할 때 언제든 계정을
          시작하거나 종료하세요.
        </p>
      </div>
    </li>
    <li>
      <input type="radio" name="accordion" id="seventh" />
      <label for="seventh">아이들이 넷플릭스를 봐도 좋을까요?</label>
      <div class="content">
        <p>
          멤버십에 넷플릭스 키즈 환경이 포함되어 있어 자녀가 자기만의 공간에서 가족용 시리즈와
          영화를 즐기는 동안 부모가 이를 관리할 수 있습니다.<br /><br />
          키즈 프로필과 더불어 PIN 번호를 이용한 자녀 보호 기능도 있어, 자녀가 시청할 수 있는
          콘텐츠의 관람등급을 제한하고 자녀의 시청을 원치 않는 특정 작품을 차단할 수도 있습니다.
        </p>
      </div>
    </li>
  </ul>
  ```

  ![스크린샷 2023-03-22 오후 1.47.40.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-22_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_1.47.40.png>)
  위의 파란 점을 즉, radio를 안보이게 하고 싶으면 직접 input의 type에 접근해서 `display: none`해주면 된다. `🚨list-style: none 이 아님을 주의!!`

  ```css
  input[type='radio'] {
    display: none;
  }
  ```

  전체 CSS 코드다

  ```css
  /* faq section */
  .faq {
    padding: 10px 12%;
    text-align: center;
    font-size: 18px;
  }

  .faq h2 {
    font-weight: 700;
    font-size: 50px;
  }

  /* accordion */
  .accordion {
    margin: 30px auto;
    width: 100%;
    max-width: 750px;
  }

  .accordion li {
    list-style: none;
    width: 100%;
    padding: 5px;
  }

  .accordion li label {
    display: flex;
    align-items: center;
    padding: 20px;
    background: var(--color--gray);
    font-size: 26px;
    font-weight: 500;
    margin-bottom: 2px;
    cursor: pointer;
    position: relative;
  }

  /* label 이후에 + 아이콘을 추가 label에 relative를 해주어야지
  absolute시 부모요소 기준으로 +가 그려짐!!! 매우 중요 */
  label::after {
    content: '+';
    font-size: 40px;
    position: absolute;
    right: 20px;
    transition: transform 0.5s;
  }

  /* 동그라미 선택점을 없애줌. */
  input[type='radio'] {
    display: none;
  }

  .accordion .content {
    background-color: var(--color--gray);
    text-align: left;
    padding: 0 20px;
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.5s, padding 0.5s;
  }

  /* input이 체크가 되면 헤딩하는 라벨의 콘텐트를 보여줌.  */
  .accordion input[type='radio']:checked + label + .content {
    max-height: 600px;
    padding: 30px 20px;
  }

  .accordion input[type='radio']:checked + label::after {
    transform: rotate(135deg);
  }

  .faq .email__form {
    max-width: 600px;
    margin: 20px auto 60px;
  }

  .faq small {
    font-size: 18px;
  }
  ```

  핵심!

  ```css
  label::after {
    content: '+';
    font-size: 40px;
    position: absolute;
    right: 20px;
    transition: transform 0.5s;
  }

  .accordion .content {
    background-color: var(--color--gray);
    text-align: left;
    padding: 0 20px;
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.5s, padding 0.5s;
  }

  /* input이 체크가 되면 헤딩하는 라벨의 콘텐트를 보여줌.  */
  .accordion input[type='radio']:checked + label + .content {
    max-height: 600px;
    padding: 30px 20px;
  }

  .accordion input[type='radio']:checked + label::after {
    transform: rotate(135deg);
  }
  ```

  overflow: hidden 속성을 통해 아래 이미지와 같이, 전체 박스보다, 글씨의 양이 더많을떄 컨텐츠가 보여지는 것을 방지했다.
  ![스크린샷 2023-03-28 오후 10.40.43.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-28_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_10.40.43.png>)
  ::after 연산자를 통해 + 를 표기해주었다. label에 relative를 해주어야지
  absolute시 부모요소 기준으로 +가 그려진다는 점을 주의해야한다.
  Netflix Accordion의 가장 중요한 메커니즘은, 제목을 보여주는 라벨과, 안의 내용을 보여주는 컨텐츠를 만든 후, 컨텐츠의 높이를 초기에는 max-width:0으로 설정해주어서, 보이지 않게 해준다음에, 라벨을 클릭하면, max-width의 높이를 지정해주어서, 보이게 설정해주어야한다!!!
  **`참고레퍼런스`**
  [https://www.youtube.com/watch?v=Tgat3-prVv4](https://www.youtube.com/watch?v=Tgat3-prVv4)
  **`문제`**
  3열로 HTML 구조를 작성했는데 제대로, 원하는대로 정렬이 되지않았다.
  ![스크린샷 2023-03-22 오후 1.33.54.png](<Chapter%201%20HTML%20+%20CSS%20+%20JS%20(1)%209b876961e14542488a06b04d9d3b5c66/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-22_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_1.33.54.png>)
  세로 3줄 정렬, `display: block`을 통해 해결하였다.

## 🤔 참고 자료

---

---

**UMC 활동에 대해 궁금하신 점이 있다면 아래 `댓글`로 남겨주세요!👇**
