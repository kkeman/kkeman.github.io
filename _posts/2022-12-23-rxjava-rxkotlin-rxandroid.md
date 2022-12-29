---
title: "Reactive Programming RxKotlin 란?"
header:
  overlay_image: /assets/images/overlay.jpg
date: 2022-12-23 11:53:00 -0000
categories: Kotlin,Android

classes: wide
published: true
---

Reactive Programming 옵져버 패턴을 이용하여 구독자에게 변경사항을 알려주는 programming 기법 입니다.

여기서 RxKotlin에 대해 알아 보겠습니다.

## Reactive Programming 란?
* 사용하는 이유?
  * 메인 쓰레드가 아닌 별도 쓰레드를 생성하여 서버 통신이나 DB 데이터를 가져올때 사용하며,
AsyncTask는 공식적으로 deprecated 됨


* 명령형 프로그래밍과 차이점?
  * 명령형은 순서대로 실행
  * 반응형은 데이터의 흐름을 먼저 정의하고 데이터가 변경 되었을때 연관되는 함수나 메소드가 업데이트 되는 방식 


* RxJava, RxAndroid, RxKotlin 차이점?
  * RxJava는 Java기반이지만 Kotlin에서도 사용 가능
  * RxKotlin은 RxJava기반이며 Kotlin만 지원
  * RxAndroid는 RxJava기반이며 쉽고 빠르게 구현가능한 구성요소를 지원

## RxKotlin 구축
* 종속성 설정
```kotlin
implementation("io.reactivex.rxjava2:rxkotlin:3.0.1")
 ```
 * 최신버전 확인 https://mvnrepository.com/artifact/io.reactivex.rxjava2
 
## 코드

 * 코드 구성

간단한 앱을 만들어 봤습니다.
```kotlin
button.setOnClickListener {
  button.isClickable = false

  Observable
          .interval(0, 1, TimeUnit.SECONDS) // 1초에 1씩 증가
          .subscribe {
            runOnUiThread {
              button.text = it.toString()
            }
          }
}
 ```



