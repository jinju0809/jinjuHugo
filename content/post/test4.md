---
title: "React를 사용한 포트폴리오 연습"
date: 2021-02-27T15:21:01+09:00
Description: ""
Tags: []
Categories: []
DisableComments: false
---



### REACT 공부? 무턱대고 해보기



갑자기 왜 리액트에 꽂힌건지.. 리액트를 배우기 시작했다. 

배운다기 보다는 직접 해보면서 경험하는 것에 가깝다. 강의를 찾아서 들었으나 우선적인 목표는 포트폴리오 페이지를 작성하는 것으로 state니 component니 하는 아이들은 뒤로 미루었다. 페이지의 구성을 대충 완성하고 난 뒤에 수정하도록 하자. 지금은 그냥 html과 다름이 없다. 



리액트는 UI를 만들기 위한 자바스크립트 라이브러리 중 하나라고 한다.

JQUERY의 형제자매급인듯..



gh-pages 사용하기

내가 쓰려는 레포와 연결을 위해 gh-pages 패키지를 설치한다.

> $ npm install --save gh-pages



이후 package.json 수정

> "homepage": "https://xxx.github.io/xxx",
>
> //scripts
>
> "predeploy": "npm run build",
>
> "deploy": "gh-pages -d build" 



마지막으로 

> $ npm run deploy

해주면 끝! 



그런데 이렇게 하고 나니 localhost로 실행을 하면 경로에 레포이름이 붙어버려서 이미지를 불러올 수 없는 상황이 생겼다.

> 기존 로컬호스트 경로: localhost:3000/
>
> 깃헙 연결 후 경로: localhost:3000/xxx
>
> 기존에 이미지를 불러온 경로: localhost:3000/images/test.jpg
>
> 깃헙 연결 후 이미지 경로: localhost:3000/xxx/images/test.jpg



상대경로?로 바꿔주어야겠다 싶어 바꿔주었다.

> 기존 이미지 태그 : < img src="images/test.jpg"/ >
>
> 상대경로로 바꿔준 이미지 태그: < img src={process.env.PUBLIC_URL + "/images/test.jpg" />