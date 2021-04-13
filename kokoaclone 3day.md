# kokoa clone 코딩 3일차

### **inline block**

inline : width, height 가질 수 없다.

block: width, height 가질 수 있다.

->block 속성을 inline로 바꾸고, width와 height를 가지게 하고 싶을 때는 inline-block을 사용한다.
하지만 많은 문제가 있고, 오래됐기 때문에 잘 사용하지 않음.
(반응형 디자인을 지원하지 않는다.)



### Flexbox Part One

inline block의 문제점을 해결하기 위해 flexblock를 생각해냈다.
flexbox 사용 규칙

1. 자식 엘리먼트에는 어떤 것도 적지 말아야 함.
   자식 엘리먼트를 움직이게 하려면 부모 엘리먼트를 flex container로 만들어야 한다.
2. align-items : cross axis에서 작용 (세로)
3. justify-content : main axis에서 작용 (가로) (디폴트)
   flex-container가 height를 가지고 있지 않으면 align-items를 사용하더라도 위치가 바뀌지 않음.
   vh = viewport height (스크린에 따라 다름)



### Flexbox Part Two

1. justify-content나 align-items의 default를 변경하기 위해선, 'flex-direction'을 수정하면 된다.
2.  flex-direction에는 두 가지 속성, column과 row가 있다.
3.  display를 flex로 했을 때 default는 row이다. 따라서 flex-direction: column;을 주면 주축과 교차축이 반전된다.
4.  원하는만큼 flex 부모-자식 엘리먼트를 만들어낼 수 있다.
5.  flex-wrap: nowrap;을 통해 wrapping이 일어나지 않게 할 수 있다.
6.  flexbox는 width값을 초기 사이즈로만 여기고, 모든 엘리먼트를 같은 줄에 있게 하기 위해 width를 바꾸기도 한다.
7.  flex-direction: column-reverse; 밑에서 시작해서 위로 올라가게 한다.(마찬가지로 row-reverse도 있다.)
8.  flex-wrap: wrap-reverse; 또한 있는데, 브라우저를 줄일 때, 엘리먼트가 겹쳐지는 위치가 역전된다.

### Fixed

position: fixed
초기 레이아웃에 자리한 위치에 고정시킴(기본적으로는 맨 위)
동시에 해당 element가 다른 레이어에 위치하도록 함
position: fixed만 사용했을때는 같은 레이어인 것처럼 보이나,
top, left, right, bottom의 프로퍼티 중 하나라도 이용해 해당 element의
위치를 임의로 변경시킨다면 원래 위치가 무시되는 것을 확인할 수 있음.



### Relative Absolute

1. position: static (default) - 박스를 처음 위치한 곳에 두는 것
2. position: fixed - 처음에 위치한 자리에서 화면의 스크롤에 상관없이 고정되는 것, top,bottom, left, right 속성을 줘서 고정된 위치 이동시킬 수 있음. 단 이동이 되면 가장 위의 새 레이어에 놓이게됨
3.  position : relative - 박스가 처음 위치한 곳을 기준으로 이동,
   top,bottom, left, right 속성을 주면 첫 위치를 기준으로 이동됨
4.  position : absolute - 가장 가까운 부모 엘리먼트에 position:relative를 추가한다면, 그 부모 기준으로 top,bottom,left,right이동하고/ 아닐시엔 body 기준으로 이동된다.



###  Pseudo Selectors part One

좀더 세부적으로 엘리먼트를 선택해 주는 것!
(기존 방법 : 태그, id w/#, class w/.)

선택의 복잡한 과정을 pseudo selector로 가능함
ex>
div:first-child {
background-color: tomato;
}

/* pseudo selector */
div:last-child {
background-color: teal;
}
id나 class를 따로 만드는것보다 이렇게 지정하는게 훨씬 좋은 방법이다.
css에서만 선택을 하면 되니까! html코드를 고칠 필요가 없기 때문이다

n번째 태그 수정하기 nth-child(n) 
span:nth-child(2) {
background-color: teal;
}
span:nth-child(even) { //or odd ( 홀수 )
background-color: teal;
}

even은 짝수! 짝수번째를 모두 바꿀 수있다.


span:nth-child(5n + 1) {
background-color: silver;
}
n을 사용하면 매우 편하다.



### Combinators

div의 바로 밑 자식에서 span을 찾아서 그것만 효과를 주는 방법
1)
div span {
text-decoration : underline;
}
이렇게하면 div밑에 있는 모든 span이 효과를 가진다
직접적인 부모가 아니어도 밑에있는 것들을 모두 css가 찾는다.

2) div > span {
text-decoration : underline;
}
이렇게하면 바로 밑!!! 을 찾게 되므로 바로 밑의 자식만 건들일수있게된다.

형제에게 효과를 주는방법

p + span {
color: black;

}
\+ 를 사용하면 형제에게 영향을 끼칠 수 있다. cool


※ > 를 사용하면 direct child를 찾고, + 를 사용하면 바로 코드상 밑에 있는 sibling을 찾게된다.



###  Pseudo Selectors part Two

\- "~"는 span이 p의 형제인데, 바로 뒤에 오지 않을 때 쓸 수 있다.
\- Attribute selectors 특성 선택자
\- 그냥 input과 required input이 있다면, input:required{}를 통해서, required input에만 속성을 적용시킬 수 있다.
\- input{} 을 통해, [input 이름]에 해당하는 input 속성을 따로 줄 수 있다.
\- 여기서, input[placeholder="First name"]은 First name에만 속성을 주지만, input[placeholder~="name"]은 name이 들어가는 모든 input에 속성을 부여할 수 있다.
\- "~="은 name을 포함하고 있다는 의미가 되는 것이다.
\- a[href$=".org"] → "$="는 ".org"로 끝나는 모든 anchor를 선택할 수 있다.
\- attribute selectors를 이용하면, class를 지정할 필요 없이 CSS만으로 각각의 속성을 부여해줄 수 있다.

(**덧붙이기**)

*= "hello" 라고 하면 ㅁㄴㅇㄹㄴㅇㄹhelloㅁㄴㅇㄹㄴㅇㄹ 라고 줘도 선택되고요.
~= "hello" 라고 하면 앞뒤에 공백이 있는 상태에서 hello 인 경우만 선택되요.

###  States

1.Active, hover, focus, focus-within, visited

2.active 해당 요소를 마우스로 클릭했을 때 효과를 적용

3.hover 마우스가 해당 요소 위를 지나갈 때 효과를 적용

4.focus 키보드로 선택되었을 때 효과를 적용

5.focus-within 부모 요소에게 적용. 자신의 자식 요소 중 하나가 focused되었을 때 효과를 적용

6.visited 방문한 사이트일 경우에 효과를 적용

7.조건을 나열해 여러 상황을 설정할 수 있음.
예 high-tag:hover low-tag:focus{

}
인 경우, 상위 요소위에 마우스 커서가 있고, 하위 요소가 focused되었을 때 효과를 적용하게 된다.



###  pseudo element

1) :: placeholder (0:46)
: placeholder의 특성만 바꾸고 싶을 때 사용한다.

2) :: selection (1:31)
: 클릭해서 긁을 때(1:58) 발생한다.

3) :: first-letter
: 첫 글자에만 적용된다.

4) ::first-line
: 첫 줄에만 작용한다.

### Colors and Variables

Color
color는 정말 css 에서중요하다
css에서 알아야할 color system
1) hexadecimal color (16진수 컬러)
\#000000 <
2)RGB 방식
-> 이건 디자이너들이 많이 사용
rgb(252,206,0); 이런식
rgba (205,23,0, 0.5);
4번째 숫자는 투명도를 말한다.
a 즉 알파는 투명도를 말하는 것이다

Variable (custom properties )

variable도 정말 중요하다.
이게 css를 프로그래밍언어처럼 보여준다
프로그래밍언어는아니지만 그 장점을 보여주는것이다.

:root 라는 엘리먼트에 변수를 추가하는 것이다
:root은 기본적으로 모든 document의 뿌리가 되는 것이다
출발점이 되는 것이다
여기에 변수이름을 쓰고
--main-color라고 변수이름을 주고
이것을 document의 root에 저장하는것이다

--를 써주고 변수이름을 써줘야한다.
변수는 -- 2개 그리고 변수이름
빈공간이 있다면 -로 채워야한다.
물론 컬러만 저장할 수 있는게 아니다
--default-border: 1px solde var(--main-color);


그 다음 이 변수를 사용할 곳에
p {
background-color: var(--main-color);
}
a {
background-color: var(--main-color);
}
이렇게 써주면 된다.