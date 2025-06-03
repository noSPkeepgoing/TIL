# Archive Validation 실패 이슈 정리

#react-native

## 📍 문제 상황

React Native VisionOS로 앱 빌드 후 Archive → Validate 단계에서 에러 발생 ⚠️

> **Missing Info.plist value. A value for the key 'MinimumOSVersion' in bundle rnVision.app/Frameworks/hermes.framework is required.**

## 📍 문제 원인

원인은 hermes.framework의 Info.plist에 MinimumOSVersion 항목이 없어서 생기는 문제.  
Callstack에서도 인지한 이슈지만 아직 공식 패치는 없음.

## 📍 해결 방법

1. Archive 완료 후, Xcode Organizer에서 "Open in Finder"
2. `.xcarchive` → 우클릭 → "Show Package Contents"
3. `Products/Applications/YourApp.app` → 우클릭 → "Show Package Contents"
4. `Frameworks/hermes.framework/Info.plist` 열기
5. 아래 내용 추가:

```XML
<key>MinimumOSVersion</key>
<string>1.0</string>
```

다시 Validate하면 정상 통과 🎉

## 🆕 관련 업데이트

이 이슈는 **React Native 0.74.3**에서 공식적으로 해결되었고,  
**0.73.x 버전에도 backport 예정**이라고 함. 관련 PR: [`facebook/hermes#1432`](https://github.com/facebook/hermes/pull/1432)

→ 최신 버전 사용 시 이 문제를 수동으로 처리할 필요가 없음! 🔧
