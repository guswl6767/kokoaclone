## kokoka clone 코딩 7일차

### Find Screen Part Three

\- HTML 코드에선 대문자를 나타내려고 해도, 우선 소문자로만 작성한다. 대문자는 디자인적인 요소이기 때문에, CSS 파일에서 작성해줘야 한다.
\- text-transform: uppercase; 대문자로 만들기.



### Find Screen Part Four

1. 중요한 부분
   display: flex;
   justify-content : space-between;
   align-items: center; 는 자주 같이 쓰이는 조합임.

2. 사진 위에 span 올리기 등, 상대적 위치 정해주고 싶을 때는, relative father and absolute child 기억하기



### Chat Screen part Two



z-index : div 위치가 맨 앞에서부터 몇 번째인지를 나타낸다. (layer 순서)
절대적인 위치나 고정적인 위치에서 수정할 수 있다.



### Chat Screen part Three

display :flex 하면 div크기가 줄어드는 이유

: 원래 div는 양 옆으로 긴데 display:flex;를 하면 div가 글자 크기에 맞춰서 줄어든다. 그리고 flex-direction에 column을 주면 다시 block이 가진 특성에 맞게 양 옆의 공간을 차지하게 된다.

그런데 또 align-items를 할 경우 다시 inline-block으로서 inline의 속성을 지니게 되어 블록 사이즈가 맞춰지게 된다.



### Chat Screen part Four

width가 100% 이어야 왼쪽으로 정렬이 되는이유

: width를 주지않으면 컨텐츠 크기만큼만 적용되서 flex박스에 끌려다니는데 width를 100%주면 화면 폭만큼의 크기를갖고 message-row자체는 flex박스의 영향을 받지만 내부컨텐츠인 img나 message-row 내부 자식들은 직접적인 영향을 받지않아서 디폴트로 좌측에 정렬된다.



### Chat Screen part Five

같은 요소가 반복될 때, 간단한 수정만으로 추가하기 위해서는
class를 하나 더 추가해서 css에 적어준다.
flex children에는 order 기능이 있다.
display방식을 바꿀 수 있음.
하나는 order : 0, 1, 2 ... 와 같이 순서를 정해주는 방식이다.
하지만, flex children이 많아지면 코드를 많이 써야한다.
두 번째 방식은 flex-direction : row-reverse를 이용해 반전시키는 방법이다.





-.reply .reply__column:first-child {
  width: 10%;
}

.reply .reply__column:last-child {
  width: 90%;
}

첫번째 컬럼은 10%만 주고 나머지 컬럼에 90%줌




### Write Message Input

하위 요소에 width를 주기 위해선 먼저, 부모 요소가 width를 가져야 한다.



### Splash Screen part On

height : 100vh 화면 높이의 100%
width : 100vw 화면 넓이의 100%



### Splash Screen part Two

CSS로는 element를 페이지로부터 완전히 없앨 수는 없다.
이유는 사라졌다가 다시 원래 상태로 돌아오기 때문
애니메이션 마지막에 forwards를 추가하면, 애니메이션의 마지막 속성을 유지하기 때문에 투명 상태를 유지한다.
하지만, 항상 존재하고 있기 때문에 화면을 덮고 있어서 클릭이 되지 않는다.
이럴 경우엔 visibility: hidden; 속성을 애니메이션의 to에 추가한다.
visibility: hidden = 마우스에 걸리지 않게 빠지는 옵션
animation-delay = 애니메이션을 딜레이 시간 이후에 실행시킴.



