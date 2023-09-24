# CreateDocumentation

문서를 구성하는 방법은 간단합니다!

## Overview

먼저 문서가 어떤 식으로 추가 되는 지 알아봐야겠네요  

현재 Xcode로 만든 프로젝트가 있다면 현재 프로젝트에 대한 문서를 빌드할 수 있어요

![빌드 다큐멘테이션 이미지](build-documentation.jpeg)

평소에 보던 Documentation 창이 잘 뜨고 있죠?
![다큐멘테이션 창](open-documentation.jpeg)

우리가 작성한 코드들에 어떤 dependency가 연관되어 있는지 개별적으로 모두 확인도 가능합니다
![디펜던시 계층 이미지](documentation-hierarchy.jpeg)

자, 어떤 표현으로 문서가 추가 되느냐?

```swift
/// 현재처럼 코드에 대한 설명을 작성하면 됩니다
/// 슬래시 3개로 설명을 추가할 수 있어요
public struct ContentView: View {
    // ...
}
```

여러 줄 작성하는 표현에 별표를 하나 더 붙여서 설명을 추가하는 것도 가능합니다.
```swift
/** 
별표를 하나더 추가해서
현재처럼 코드에 대한 설명을 작성하면 됩니다
*/
public struct ContentView: View {
    // ...
}
```

마크다운 표현을 지원하기 때문에 백틱(`)으로 코드 블록도 만들어 줄 수 있구요.  

백틱이 나오지 않는다면 한영 전환을 한 번 해봐요!

```swift
/// 코드 블록 설명도 추가하고 싶다면
/// ```swift
/// print("Swift is Awesome")
/// ```
public struct ContentView: View {
    // ...
}
```

지금처럼 작성한 내용은 프로젝트를 진행하는 동안에도 언제든 확인할 수 있죠?  

옵션키를 누른 채로 클릭을 하면 돼요!

![옵션으로 설명 확인](option-click.jpeg)

메소드의 특정 파라미터에 대한 설명이 필요한 경우에는 아래 코드처럼 표현 하면 되고  

return에 대한 설명이 필요할 경우도 마찬가지에요

```swift
/// Something이라는 구조체입니다
public struct Something {
    /// Something이 어떤 건지 궁금하지 않나요?
    ///
    /// - Parameter habitat: Something이 잠을 자는 걸 표현 합니다.
    /// - Returns: Something이 자는 동안의 energy level 입니다.
    mutating public func sleep(in habitat: Habitat) -> Int {
        energyLevel += habitat.comfortLevel
        return energyLevel
    }
}
```

근데 만약에 파라미터가 여러 개라면?
```swift
/// Something이라는 구조체입니다
public struct Something {
    /// Something이 어떤 건지 궁금하지 않나요?
    ///
    /// - Parameter: 
    ///     - habitat: Something이 잠을 자는 걸 표현 합니다.
    ///     - numberOfHours: Something이 잠자는 시간 입니다.
    /// - Returns: Something이 자는 동안의 energy level 입니다.
    mutating public func sleep(in habitat: Habitat, for numberOfHours: Int = 12) -> Int {
        energyLevel += habitat.comfortLevel * numberOfHours
        return energyLevel
    }
}
```

근데 이러면 매번 전부 타이핑을 해줘야 하잖아요?  

더 쉽게 해볼 수도 있어요  

Documentation을 작성하고 싶은 곳에서 커맨드키를 누른 채로 클릭을 하게 되면 추가할 수 있어요  

![쉽게 추가하는 방법 이미지](easy-add.jpeg)

참조 형태의 링크를 걸고 싶을 때는 백틱 두개(``)로 표현하면 됩니다.
```swift
/// Something이라는 구조체입니다
public struct Something {
    /// Something이 어떤 건지 궁금하지 않나요?
    /// ``ContentView`` 백틱 두개로 감싸면 참조 링크가 생성되고
    /// ``Habitat/comfortLevel`` 
    /// 지금처럼 다른 파일에 있는 그 하위의 경로를 작성해줄 수도 있습니다
}
```
