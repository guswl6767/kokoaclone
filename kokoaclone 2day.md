# kokoa clone 코딩 2일차

#### More Tags and Prettier 

순서가 없는 리스트: ul
순서가 있는 리스트: ol
리스트 내의 항목: li

#### Tag Attributes

a: annchor - 다른 웹으로 이동
attributes : 부가적 정보-속성
\- 어떤 속성이든 부여해도 되지만, 웹브라우저는 이해하지 못한다.
img : self-closing tag

#### More Tags and Head

HTML 문서의 구조를 작성하는 법
\- head : 페이지 환경 설정
\- body : 보여지는 컨텐츠

#### Its ALL About the Head

\- meta tag는 웹브라우저에 보이지 않는다.
\- google에서 title과 description을 가져온다.
\- 검색엔진에 도움을 주기 위해, lang 정보를 준다.
\- og:image : 카카오톡체팅 링크에서 보여지는 이미지

#### More Tags

태그들을 전부 외우는 것은 불가능하다 .

mdn = web에 관련된 태그들을 설명하는 사이트를 통해 보는 것이 좋다.

#### Form Tags

HTML에는 여러 개의 tag들이 존재한다.

그 중 form태그는 다양한 input값을 넣어주기 위한 tag이다.

input을 넣어주는 다양한 종류의 type들이 있고 type마다 사용할 수 있는 arrtibute가 각각 존재한다.

ex)  type : button, checkbox, color, date, image, number
       attribute : placeholder, required, accept, disabled, minlength, maxlenth

#### More Tags and IDs

lable은 input과 함께 작동한다. (label이 input을 activate)
lable 태그에 for=""
input 태그에 id="" 에 완전 똑같은 벨류가 들어가야 함.

***핵심은 Id**
id는 body 안에 어떤 태그에든 넣을 수 있는 attribute임
element당 하나의 id 만을 가질 수 있다 (고유식별자임, 중복된 id를 사용하면 안됨)
**Why?***   CSS가 태그를 지정하여 꾸미기 위해서 ID가 필요하기 때문이다



#### Semantic HTML

Semantic HTML(**document와 code를 명확하게 할 수 있도록 짜는게 좋다**)
div tag = division (박스라고 생각해도 됨) 아무런 값이 없는 단순한 box
header tag = div 대체 태그 (head와 헷갈리지 않기. head는 보이지 않지만 header는 보인다)
main tag = 내용을 의미하는 태그
footer tag = 꼬릿말을 의미하는 태그
span tag= 짧은 텍스트를 의미하는 태그



#### 총정리 

\- html은 뼈대이고 수많은 tag들로 이루어져 있다.(tag는 항상 같은 이름으로 시작하고 끝나야한다.)
\- Content는 태그사이에 위치한다.
\- Attribute 값에는 항상 “” 큰따옴표 사용 (Prettier 사용시 ‘’써도 자동으로 “”으로 바꿔줌)
\- src는 image만 사용가능
\- semantic 태그는 의미가 있는 태그다. 좋은 프로그래머가 되기 위해서는 필수
\- 모든 태그는 mdn 또는 구글에서 찾아보자. 암기하지 말자. 그러나 자주쓰는건 암기하면 좋다.

