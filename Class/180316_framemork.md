# Framework 정리
> 2018.03.16 업데이트

## Framework
Homebrew 를 설치한다.
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

gem update를 한다.
```
sudo gem update; gem cleanup;
```


## Cocoapad
cocoapod 의 repository 를 업데이트 해준다.
```
pod repo update;
```

cocoapod framework 설치가 필요한 폴더로 이동하여
```
pod init
```
을 입력한다.


```
target 'CocoapodTest' do
  use_frameworks!

  pod 'frameworkName'
end
```

```
pod install
```

## Carthage
```
brew install carthage
```

Cartfile
```
github "GitCategory/GitName"
```

`Xcode` > `Preferences` > `Locations`
`Command Line Tools:` 에서 Xcode의 버전을 선택해야 된다.

```
carthage update
```

`TARGETS` > `Build Phases` > `Link Binary With Libraries` 에서
add(+) 를 눌러 `Add Others`에서 frameworkName.framework 를 open해준다.

`Run Script` 에 
```
/usr/local/bin/carthage copy-frameworks
```
를 입력한다.

Input Files에
```
$(SRCROOT)/Carthage/Build/iOS/frameworkName.framework
```
를 입력한다.