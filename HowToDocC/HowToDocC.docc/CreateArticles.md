# CreateArticles

우리가 평소에 보는 문서를 마크다운과 함께 Article 형태로 표현할 수도 있습니다

## Overview

DocC에서 문서는 3가지 종류로 만들어 볼 수 있어요
![문서 종류 3가지](3types.jpeg)

- 작성한 코드에 대한 설명을 만드는 Reference (<doc:CreateDocumentation>에서 만들어 본 내용이에요)

- 지금 만들어볼 종류인 Articles 종류

- 그리고 Tutorials 종류도 있어요 (애플 튜토리얼 중 Scrumdinger 생각하면 됩니다)  

> 지금 해볼 건 깃헙 ReadMe 같은 종류인 Articles 에요!

### 한 번 만들어볼까요!

![카탈로그 만들기](create-catalog.jpeg)

먼저 문서에 대한 카탈로그를 만들어야 합니다
![카탈로그 이름 설정](hierarchy-catalog.jpeg)

이후에 md 파일을 작성해주면 Article 형태의 문서 추가 완료!
![아티클 추가](add-readme.jpeg)

이미지를 추가하고 싶을 땐  

카탈로그의 Resources 폴더에 넣고 싶은 이미지를 드래그 하고  

md파일에서 `![이미지에 대한 설명](파일 이름.jpg)`  

와 같은 형태로 추가해주면 작성할 수 있어요  

네모 괄호 안은 검색할 때 인덱싱하는 용도로 쓰게 됩니다.

```
### 한 번 만들어볼까요!

![카탈로그 만들기](create-catalog.jpeg)

먼저 문서에 대한 카탈로그를 만들어야 합니다
![카탈로그 이름 설정](hierarchy-catalog.jpeg)

이후에 md 파일을 작성해주면 Article 형태의 문서 추가 완료!
![아티클 추가](add-readme.jpeg)
```

## 문서 구조화

문서의 계층을 구조화해두면 나중에 읽기 편하겠죠?


![문서 구조화](organize-document.jpeg)


마크 다운을 작성하다 다른 Article 파일을 참조하고 싶을 경우  

`<doc:문서이름>`으로 참조링크를 걸 수 있어요

![문서 링크 걸기](linking-document.jpeg)

![문서 링크 걸기](linking-sample.jpeg)


## Extensions

작성한 코드마다 주석표현이 달려 있으면  

작업할 때 보기 불편하겠죠?


![문서 나누기](separate-doc.jpeg)

해당 swift 파일에 대한 md 파일을 따로 구성해줄 수 있습니다

### 한 번 분리해보죠!

![extension 파일 만들기](create-extension.jpeg)

Extension 파일을 문서 카탈로그 쪽에 새로운 md파일로 만들어주고


![extension md파일](extension-md.jpeg)

헤더에 참조 링크 표현인 백틱 두개와 함께 경로를 표현해주면 됩니다!

## 마무리
현재 작성한 문서 페이지를 누구든 확인 가능한 웹으로 퍼블리쉬도 가능해요  

자세한 건 <doc:PublishDocC>에서 확인해 보시죠
