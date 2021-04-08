react가 javascript에 대한 지식이 많이 필요하기 때문에 이번엔 vue를 공부하기로 함.

===========

1일차

component ?

- 웹을 구성하는 로고, 메뉴바, 버튼 등 요소
- 재사용 가능하도록 구조화한것

spa(single page application)

- 단일 페이지 어플리케이션
- 하나의 페이지 않에서 필요한 영역 부분만 로딩
- 빠른 페이지 변환
- 적은 트래픽 양

설치하고 환경설정하는데 오늘 공부시간을 다씀

설치를 했는데 localhost 페이지가 안나오던건 npm i로 해결

https://youtu.be/sqH0u8wN4Rs?t=593

===========

2일차

readme를 사용해서 코딩 일지를 작성하는게 좋겠다는 판단을 했음.

vue router

    웹 페이지를 이동하는것
    서버에 요청해서 새로운 페이지를 받는다
    하지만 라우터는 미리 해당하는 모든 component 페이지를 받고   라우팅을 통해서 그 부분만 전환함.

    이것은 3대장 모두에게 동일하게 적용됨

    npm install vue-router --save로 설치할 있음

BootstrapVue

    상단에 있는 메뉴바는 굳이 다시 로딩할 필요가 없으므로 Header로 따로 만듬

    npm install vue bootstrap-vue bootstrap

vue에는 template과 script부분으로 나눌 수 있음
template는 디자인
script는 디자인에 데이터를 바인딩, 이벤트 캐치, 서버와 통신 등등

App.vue를 통해서 우리한테 보여짐

template에 있는 <Header/>는 components를 참조한뒤 import를 참조하여 해당 위치에 있는 값을 가져옴

https://youtu.be/sqH0u8wN4Rs?t=1232
