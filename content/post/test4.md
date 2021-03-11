---
title: "React를 사용한 포트폴리오 연습"
date: 2021-02-27T15:21:01+09:00
Description: ""
Tags: []
Categories: []
DisableComments: false
---



### REACT를 또 배워요?



갑자기 왜 리액트에 꽂힌건지.. 리액트를 배우기 시작했다. 



gh-pages 사용하기

npm install --save gh-pages

이후 package.json 수정

> "homepage": "https://xxx.github.com",
>
> //scripts
>
> "predeploy": "npm run build",
>
> "deploy": "gh-pages -d build" 



마지막으로 

> $ npm run deploy

해주면 끝! 