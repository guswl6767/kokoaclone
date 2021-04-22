## kokoa clone 코딩 5일차



#### BEM(Block Element Modifier) —추천 규칙

BEM은 기본적으로 ID를 사용하지 않으며, class만을 사용한다. 또, '어떻게 보이는가'가 아니라 '어떤 목적인가'에 따라 이름을 짓는다. 예를 들어, 에러 메시지를 띄우는 P 태그에게는 .red가 아닌, .error라는 이름을 줘야한다.
이름을 연결할 때는 block-name과 같이 하이픈 하나만 써서 연결한다.



#### Font Awesome-아이콘 추가하기

\- 아이콘을 추가하는 데에는 두 가지 옵션이 있다.
\1. 직접 아이콘을 구하는 방법(직접 이미지를 만들고 추출하거나 svg파일을 이용. svg는 픽셀이 없는 이미지 파일형식. 수학으로만 구성된 형식)
\2. Heroicons, FontAwesome에서 가져오기
\- FontAwesome에서 가져온 kit code 스크립트는 항상 마지막에 있어야한다. body 태그를 닫기 직전.
\- 'i'는 icon의 줄임말.



#### sign up screen part two-헤더작성

마찬가지로 어떤 페이지든 공통적으로 헤더를 가지고 있으므로 구분 가능하게 클래스를 만들어줘야한다.



#### status bar css

ink:css + enter : css링크 단축키

web font
\- link 보다 import를 추천한다.
\- import위치는 제일 상단
\- body에 font-family 추가
\- 모든 폰트를 추가하면 웹사이트 무거워진다.
[Google Fonts](https://fonts.google.com/)

css hack(justify-content대신사용가능)
\- 레시피 같이 어디든 쓸 수 있다. 이상하지만 작동한다.
\- 1 상위 박스 : justify-content: center; -중앙으로 몰림
\- 2 내부 박스 범위 : width: 33%; -왼쪽으로 몰려서 범위 벌어짐, 왼쪽 위치할 박스는 왼쪽에 붙어서 정렬됨
\- 3 중앙에 위치할 박스 : display: flex; justify-content: center; -중앙에 위치할 박스만 중앙에 위치함
\- 4 오른쪽에 정렬할 박스 : *display*: flex; *justify-content*: flex-end; *align-items*: center; -오른쪽에 붙어서 정렬됨



#### sign up screen part three

\- 리셋 CSS는 CSS 파일이다. 브라우저에 기본적으로 적용되어 있는 스타일을 초기화 해준다.
\- 먼저 브라우저 스타일을 없애고, 직접 디자인 하는게 더 좋은 방법이다.
\- styles.css에서 작성한 한 부분도 따로 css파일을 만들어 분리해주는 것이 깔끔하게 작업할 수 있는 방법이다. → CSS 코드를 여러 파일로 분할했다가 다시 합친다.



#### Log in form part one

\- 모든 input에 focus를 없앨 것이기 때문에, reset.css에 input:focus{ outline: none; }을 적용한다.
\- 어떤 css파일이건 styles.css에 적용시키고 싶다면, 반드시 import를 해줘야 한다.



#### Log in form part two

\- 가상 클래스 선택자(pseudo element)
\- :not()→ 뭔가가 적용되는 걸 원하지 않을 때 사용한다.
\- [ ] 사이에 쓰인 것들은 특성 선택자(attribute selector)이다.
\- cursor: pointer;로 버튼 위의 커서를 변경할 수 있다.
\- color:inherit;는 부모로부터 색을 상속받는 것이다.



#### Recap and Form

CSS 작성법(class 사용, id 사용) 어떤 것이 더 나은지 선택
style.css에는 font-family와 같이 모든 스크린에 적용될 수 있는 스타일을 써놓는다 (방식 중 하나)
form 의 중요한 2가지 속성(attribute) = action, method
action = 어떤 페이지로 data를 보낼 것인지 지정
method = post(백엔드 서버에 정보를 전송하는 방식), get(보안에 취약(URL에 포함 되어도 상관 없는 정보들)) 중 선택 가능