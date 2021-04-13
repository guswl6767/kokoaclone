# kokoa clone 코딩 4일차

### Transitions

transition
어떤 상태에서 다른 상태로의 변화를 보내주는 애니매이션이다

1. transtion은 state가 없는 요소에 붙어야한다
   처음 생긴곳에 있어야한다/
   state에 transition을 준다면 변화를 준것(예를들면 hover라면 마우스를 갖다 댄것)을 그만할경우(마우스를 뗄경우)
   원래상태로 바로 돌아간다
2. transtion 에 변화를 준것들은 state에 들어있는것들이 기준이 되어 바뀌는것이다
   바뀌는 것들에 한정하여 transition 이 일어날 수 있다.



### Transitions part Two

1."ease-in function"은 브라우저에게 애니메이션이 어떻게 변할지 말해주는 기능이다.
 → default로 갖고 있는 것은 linear, ease-in, ease-in-out, ease-out, ease 이다.

2.cubic-bezier(0, 0, 0, 0)을 이용해서 자신만의 커브를 만들 수 있다.

3. transition은 state에 따라 바뀌는 property를 갖고 있으면 사용된다.
\- 다른 transtion을 더 쓰고 싶다면 "콤마(,)"를 잊어선 안된다.

### Transformations

한 요소를 말 그대로 변형시킬수 있다. css로 3D까지 가능하다.
transform 안에 많은 기능들이 있다. transformation은 box element를 변형시키지 않는다.즉, 옆에 sibling들에게 영향을 끼치지 않는다.
margin, padding이 적용되지 않는다. 일종의 3D transformation이기 때문이다.
margin이나 padding을 주기위해서 tarnslateX, trnasLateY 를 사용하는것이 아니다!
다른 요소의 box를 변형시키지 않고 원하는 요소를 이동시키기 위해서 사용하는 것이다.
trransformation 은 페이지의 픽셀의 다른 부분에서 일어난다.
transformatino은 box차원에서 일어나지 않는다.
tronsformation 을 결합 가능하다!
CSS의 3D는 GPU로 돌아간다 즉 3D작업을 할 수 있다
transformation 은 이것 역시 엄청나게 많은 document가 있다 확인해서 combine할 수 있다
transition 과 transformation 을 합친다면 아름다운 애니매이션을 만들 수 있다.



### Animations part One

애니메이션 만들기
@keyframes 애니메이션 이름 {
from{
}
to {
}
}
사용하기
img {
animation : 애니메이션 이름 재생시간 옵션
}
무한으로 반복되게 하려면 뒤에 infinite를 붙여준다.

### Animations part Two

\- from to 말고, 1,2,3,4,5...10 혹은 0% 25% 50% 75% 100% 같이 여러 단계로 나뉘어 애니매이션을 만들 수 있다.
\- 다른 property들도 애니매이션으로 만들 수 있다. 꼭 transform만 써야하는 건 아니지만, transform을 쓰는걸 권한다. 일부 property는 애니매이션이 잘 안되기 때문이다.



### Media Queries

media Queries
@media screen and (max-width: 400px){ // 스크린 넓이가 400px 보다 작으면
background-color: tomato
}

(orientation : portrait) - 세로모드
ㄴlandscape - 가로모드



### Media Queries Recap

Media Queries 주요기능
\- min-device-width
\- max-device-width
\- orientation: landscape
\- orientation: portrait
\- aspect-ration - 레티나디스플레이 감지가능
\- display-mode
\- inverted-colors
\- lightlevel
\- prefers-contrast
\- resolution
\- monochrome

Media type
\- @media screen{}
\- @media print{}