# PublishDocC

작성한 DocC를 웹으로 Publish 해보겠습니다

## Overview

DocC 작성을 완료했다면 작성한 내용을 공유할 수 있다면 좋겠죠?

![docc 내보내기](export-docc.png)

document 창에서 현재의 문서를 Export하면  

doccarchive라는 파일이 생성 됩니다.

![docc 저장 경로](docc-directory.png)

먼저 현재 파일을 원하는 경로에 저장합니다.  

(저는 현재의 프로젝트 파일이 있는 경로로 설정했어요)  

## Github Pages 설정

제일 간단하게 Github Pages로 호스팅을 해볼게요.

![깃헙 레포 생성](github-repo.png)

깃헙 레포를 프로젝트 이름과 똑같이 설정해줬구요 Create Repository를 눌러 줍니다  


![현재 프로젝트 터미널 열기](open-terminal.png)  

그리고 작성하고 있었던 현재 프로젝트를 터미널에서 열어 줍니다

![깃 생성](git-init.png)
git을 init해서 만들어주고! remote origin에 현재의 git을 추가해줍니다.

이제 현재의 프로젝트를 push해주면 되는데  

터미널로 하시는 게 편한 분들은 터미널로 커밋 후에 Push 해주시면 되고  

저는 Github App을 사용하는 게 편해서 existing repo를 통해서 추가했습니다  

![깃헙 앱](github-app.png)  

![경로 설정](github-app-path.png)

![이니셜 커밋](initial-commit.png)

이니셜 커밋 후에 Publish를 해주세요!

![레포 체크](github-repo-check.png)  

다시 웹 깃헙으로 와서 push가 잘 됐는지 확인해 봅니다

이제 Github Pages 설정을 해줘야 해요.  

상단 네비게이션 메뉴 중 Settings 버튼을 누르고 Pages 섹션에서  

main 브랜치, 하위 디렉토리는 /docs가 되게 한 뒤 저장합니다.

![깃헙 페이지 세팅](setting-github-page.png)  

## doccarchive 파일 호스팅 가능한 형태로 변경하기

아까 저장했던 doccarchive를 살짝 변경한 후에 docs라는 폴더를 추가하겠습니다  

터미널을 사용해서 현재의 작업을 해주면 돼요

```
➜  HowToDocC git:(main) ✗ $(xcrun --find docc) process-archive \
transform-for-static-hosting ~/Desktop/FramStudy/HowToDocC/HowToDocC.doccarchive \
> --output-path ~/Desktop/FramStudy/HowToDocC/docs \
> --hosting-base-path HowToDocC
➜  SwiftUIDocCSample git:(main) ✗
```

![터미널로 docc 변환](make-docc-static.png)

- transform-for 라인엔 저장해뒀던 HowToDocC.doccarchive 파일의 경로를  

- output-path 라인엔 저장하고 싶은 docs의 경로를 (레포의 하위에 바로 있게)

- hosting-base-path는 repo 이름으로 설정해주고 엔터하면 끝!

![docs 폴더 생성됨](docs-created.png)

docs 폴더가 생겼구요  

변경 사항들을 커밋 + push 해줍니다


![docs 폴더 커밋](docs-folder-commit.png)

이제 아래 링크처럼

> `https://woozoobro.github.io/HowToDocC/documentation/howtodocc`
  

닉네임.github.io/프로젝트 이름/documentation/프로젝트 이름 소문자  

로 접근하면 documentation 페이지를 확인할 수 있습니다!!
