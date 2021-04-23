## kokoka clone 코딩 6일차

##### Navigation Bar part One

\- navigation 안의 ul 안에 많은 li들로 구성되는데, 검색엔진 구글도 navigation을 찾아서 ul의 li 안에 있는 link를 가져오게끔 설정되어 있다.
\- VSC의 단축키로 navigation에서 하위메뉴까지 한번에 자동 완성 시킬 수 있다.
→ nav>il>li*(필요한 갯수)>a
→ 그 후 #과 tab만으로 간편하게 작성이 가능하다.(수정하다보면 다음 tab이 옳게 먹히지 않는다.)
\- 점 3개는 ellipsis라고 한다.
\- 속성과 class 이름이 똑같아도 상관없다.
\- 메인 styles.css에 다른 요소의 css를 import 할 때, 순서를 지키는 것이 정말 중요하다.



### Navigation Bar part Two

위치를 고정 시키기
position : fixed
배열이 깨지는 경우 width : 100% 설정
고정할 위치 (아래 인 경우 bottoom : 0;)과 같이 설정
box-sizing:border-box를 사용해 아이콘들이 한 줄로 보이게 함



### Border Box

\- CSS에게 200px의 box를 원한다고 하면, CSS는 내가 원한대로 box를 만든다.근데 그 box에 padding을 추가하게 되면 CSS는 기본적으로 내가 원했던 200px을 유지하려고 할 것이다. 따라서, padding을 50px 줬다고 생각한다면 CSS는 box가 150px이 되었다고 생각할 것이다. 하지만 CSS는 이렇게 둘 수 없기 때문에 200px을 유지하기 위해서 box를 더 크게 만들 것이고 오히려 결과적으로 250px이 되는 것이다.
\- box-sizing: border-box; → CSS에게 "내가 padding을 줘도 신경쓰지마. 내 box 사이즈를 늘리지 말아줘"라고 말하는 격이다.



### Navigation Bar part Three

\- border을 사각형으로 만들고 싶다면, radius를 width의 절반값을 주면된다.
\- position: absolute;는 정중앙. absolute는 해당 element의 가장 가까운 relative를 가진 부모 기준으로 움직인다. 기본적으로 body가 그에 해당되며, 따로 원하는 기준이 있다면 그 container에 position: relative;를 준다.

\- ellipsis 옆 notification 만들기
.nav__notification__2 {
background-color: tomato;
width: 6px;
height: 6px;
border-radius: 3px;
display: flex;
justify-content: center;
align-items: center;
position: absolute;
left: 30px;
bottom: 28px;
}

### User Component part One

.user-component*2 입력할경우 클래스가 user-component인 div가 2개 만들어짐.
반복되는 것들은 component로 만들어서 반복해서 사용할 수 있도록 만든다

### Finishing Friends Screen

CSS 파일 분리해서 입력할 때, 각각의 파일 위치에 맞게 작성
BEM 사용시 class 이름이 길어지는데, 헷갈리지 않도록 주의
div안에 div 안에 div 안에 span... 과 같이 HTML이 복잡해질 수 있는데, 들여쓰기 실수하거나, 위치 잘못 입력으로 오류 발생하지 않게 조심.

### Chats Screen part Two 

원래 span은 inline element여서 margin이 적용이 안된다.
그런데 부모요소에 display:flex를 하면 자식요소는 flex item이 됩니다. 이럴경우 inline element가 아니라 flex element여서 span에 margin이 적용된다.



### Find Screen Part One

icon 위에 빨간점 component로 만들기

\1. components 파일에 point.css 생성

2.point.css에 red point에 대한 코드 작성
.point {
background-color: tomato;
width: 5px;
height: 5px;
border-radius: 2.5px;
position: absolute;
right: -6px;
top: -7px;
}

3.styles.css 에 import
@import "components/point.css";

4.find.html 에 해당코드 작성 ( div class=“point” )
점 찍고 싶은 span 사이에 넣어주기

5.screen-header.css에서 relative 관계 설정해주기
.screen-header__icons span{} 에 position: relative 설정



