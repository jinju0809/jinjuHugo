---
title: "Hugo + Github pages 로 블로그 만들기"
date: 2021-02-25T16:43:01+09:00
Description: ""
Tags: ["Hugo", "git", "blog"]
Categories: ["basic"]
DisableComments: false

---

---
### 뉴비의 휴고, 깃헙 페이지를 이용한 블로그 만들기

#### 서론

이 글은 typora를 이용해서 쓰고 있는데, typora 역시 아직 모르는 기능이 많아서 앞으로도 글이 계속 수정될 예정..

먼저 휴고의 배경에 대해서는 https://ialy1595.github.io/post/blog-construct-1/ 이 블로그에 굉장히 많이 설명이 되어 있었다. 휴고는 정적 사이트 만들기를 도와주는 프로그램이라고 생각하면 된다. 또 다른 프로그램으로는 jekyll과 hexo 등 여러 프로그램이 있다. 휴고로 만들자고 생각한 이유는 크게 없다. 

##### 제킬도 헥소도 휴고도 모르니 그냥 이름이 마음에 드는 프로그램을 쓰자!

중간에 포기하고 싶은 적이 여럿 있었지만 오기로 해냈다.



사실 블로그를 만드는 법은 굉장히 간단하다. (기본적인 지식과 영어실력을 갖추고 있다면)

휴고를 깔고

깃을 깔고

깃 repo 두 개를 만들고

휴고 프로젝트를 만든 다음

테마와 연결해서

repo에 올리면 끝! *(근데 왜 며칠이 걸렸을까?)*



나처럼 고생하는 사람들이 있을 수도 있고 미래에 또 까먹을 나에게도 알려주기 위해서 글을 작성한다!



#### 지금부터 시작

먼저 휴고를 설치한다. 나는 쓰려는 테마에서 extend 버전을 깔라고 하여 extend 버전을 설치했다. 

위에 링크된 블로그에서 초기 단계를 잘 알려주고 있으니까 따라하면 된다!

휴고 설치 후 환경변수 설정이 끝났다면 깃에서 repo 두 개를 먼저 만들어 두자

첫 번째 이름은 프로젝트 이름 (ex: blog)

두 번째 이름은 페이지 주소가 될 이름 (ex: 깃헙아이디.github.io)

이렇게 만들어 두고 나는 master 브랜치를 추가했다. 



이후 cmd나 git bash 등을 열어두고 프로젝트를 만들 폴더로 이동한다. 이건 개인의 자유. 

나는 c:users:내이름 아래에 폴더를 만들었다

> $ hugo new site project

입력하면 와우!! 프로젝트를 만드셨네요! 축하합니다~! 하는 식의 문구가 나오게 된다.

해당 경로를 확인해보면 content라느니, layouts라느니 하는 기본 구성이 들어가 있다. 

![image-20210227161327939](C:\Users\jjyou\AppData\Roaming\Typora\typora-user-images\image-20210227161327939.png)

![image-20210227161419340](C:\Users\jjyou\AppData\Roaming\Typora\typora-user-images\image-20210227161419340.png)

이제부터 모든 작업은 c:users:내이름:project 에서 진행된다.

그럼 이제 테마를 가져올 차례 -> https://themes.gohugo.io/

테마를 골라 깃헙주소를 복사한다. 테마의 readme에 설명이 들어 있으니 참고하는게 좋다.

맞다! git init 작업을 해주자

> $ git init 이 뭐죠? 

git 을 쓰기 위한 뼈대를 만들어주는 작업이라고 볼 수 있다. 깃 저장소를 생성하는 명령어라고 한다.

이걸 안하고 있었다가 수많은 오류와 만났던 지난날의 나..ㅠㅠ



> $ git submodule add 테마의주소  public

이렇게 하면 열심히 테마를 가져와준다. 테마주소는 보통 readme에 써있는대로 적으면 된다.

project 폴더 themes에 테마이름으로 된 폴더가 나타나면 성공!

안나타나는 경우 나타나는 에러를 열심히 살펴보고.. 다시 찾아보고.. 갈아엎고..

나의 경우는 git init을 안하고 막 가져오려고 했다가 실패했었다 (왕초보ㅠㅠ 야 너두?)



암튼 가져온 다음에는 config.toml이라는 파일을 수정하면 된다.

나는 이것도 내가 사용한 테마의 readme를 참고했는데, 통째로 가져다 써도 된다고 해서 가져다 썼음

내가 사용한 anatole 테마: https://github.com/lxndrblz/anatole



자 이제 

> $ hugo new post/test.md 

를 작성해보자. contents 폴더 내에 post/test.md가 작성되었을 것이다. 

> $hugo server -D

를 하면 localhost:1313에서 페이지 초안을 확인할 수 있다. -D를 붙이면 draft인 파일들도 보여주게 되는데, 이 파일들은 draft라서 실제로 내가 쓰게될 블로그에서는 보이지 않으니 빌드하기 전에 draft: true 라고 적힌 설정을 지워주자

![image-20210227170618859](C:\Users\jjyou\AppData\Roaming\Typora\typora-user-images\image-20210227170618859.png)

나중의 얘기지만 나는 git에 연결하고 난 뒤에 계속 **hugo server -D**로 보는 화면과 실제 화면이 달라서 원인을 찾느라 또 헤매는데 archetypes의 default 폴더가 draft 상태여서 그랬다. 그 뒤로는 hugo server로만 확인을 했음... 

![image-20210227170831720](C:\Users\jjyou\AppData\Roaming\Typora\typora-user-images\image-20210227170831720.png)

**hugo server -D**를 하고 난 뒤에 위에 보이는 이 localhost:1313 링크로 가면 내용을 볼 수 있다는 뜻이다.  (진짜 왕초보.. 야 나두!)



암튼 이제 나 혼자 보지말고 다른 사람들도 볼 수 있게 만들어보자!

위에서 이미 repo는 두 개 만들었으니 연결만 하면 된다! 다들 순서가 여기서 레포를 만들라고 했는데 나는 그게 더 헷갈려 미리 레포를 만들어두었다.

순서대로 blog와 깃아이디.github.io 를 추가한다.

> $ git remote add origin blog의깃주소(첫번째 repo)
>
> $ git submodule add -b master 깃아이디.github.io의깃주소 public

둘 다 무사하게 연결이 되면 이제 빌드를 한다. 만약 무사히 연결이 안된다면 무엇때문인지 자세히 확인해보자! (나는 init 때문이었지)

이제 연결이 되었으니 빌드를 해야한다. draft : "true" 를 찾아 지워주자.

> $ hugo -t 테마이름(나의 경우 anatole)

테마를 넣기 위해서 -t를 뒤에 붙이는 것이고 이후에 내용 수정하거나 할 때는 hugo만 써도 된다

요렇게 빌드 하고난 뒤 원격에 푸시해주면 끝!

> $ cd public
>
> $ git add .
>
> $ git commit -m "커밋 메시지 입력"
>
> $ git push origin master
>
> $ cd ..
>
> $ git add .
>
> $ git commit -m "커밋 메시지 입력"
>
> $ git push origin master



끝났다! 이제 내아이디.github.io 를 입력하면 블로그를 확인할 수 있다!



그동안 열심히 찾아본 사이트들을 아래 공유한다.

https://medium.com/@bjs1616/hugo%EC%99%80-github-page%EB%A5%BC-%EC%9D%B4%EC%9A%A9%ED%95%9C-%EB%B8%94%EB%A1%9C%EA%B7%B8-%EB%A7%8C%EB%93%A4%EA%B8%B0-9eb1a5b50d91

https://blog.billo.io/devposts/blog_github_page/

https://blog.lulab.net/infra/install-hugo-and-configure-for-your-blog/

https://naraewool.gitbook.io/techwriter/today-i-learned/hugo

https://github.com/Integerous/Integerous.github.io



모아둔 링크들을 확인하다가 내가 이것도 했었지!!! 한 링크들

https://stackoverflow.com/questions/39837559/why-isnt-my-page-loading-up-on-github

https://mygumi.tistory.com/285

github의 settings에서 아래로 쭉 내리면 github pages가 나타난다. 

여기서 branch가 master가 아니었기 때문에 또 오류가 나서 열심히 찾아서 master로 바꿔주었다.



결론적으로는 어떤 오류든 해결 못 할 오류는 절대 없다. 내가 그 정도 레벨의 오류를 낼 수 없는 뉴비이기 때문이다. 조잡한 포스팅이지만 도움이 되었다면 좋겠다☺ 뉴비개발자 화댜!