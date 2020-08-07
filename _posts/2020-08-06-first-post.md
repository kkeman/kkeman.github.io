---
title: "Kotlin 범위 함수 (let, run, apply, also, with)"
header:
  overlay_image: /assets/images/unsplash-image-1.jpg
date: 2020-08-06 17:00:00 -0400
categories: Kotlin Android
image: assets/images/1_F5fHRUgq67xrbF9924p2_w.png
---

각 범위 함수에 권장되는 사용 사례가 있습니다. 올바른 출력을 반환하고 코드 규칙에 맞는 함수를 선택하십시오.

## [apply]
 * 개체구성
```kotlin
 val foo = Foo().apply {
     this.field1 = 1 
 }
 ```

## [run]
 * 개체 구성 및 결과 계산
```kotlin
 val bar = Foo().run {
     this.field1 = 1
     this.toBar() 
 }
 ```
 * 여러 명령문을 하나의 표현식으로 그룹화 : run비 확장 양식도 있습니다.
```kotlin
val bar = run {
    val foo = Foo()
    foo.field1 = 1
    foo.toBar()
}
 ```

## [also]
 * 개체와 관련된 추가 효과 수행
```kotlin
val foo = Foo().also {
     doSomethingTo(it) 
}
```

## [let]
 * null이 아닌 객체에서 람다 실행
```kotlin
val bar = getFoo()?.let {
     it.toBar() 
}
```

 * 로컬 범위의 변수로 표현식 도입
```kotlin
(...complicated expression...).let {
    doSomethingWith(it)
}
 ```

## [with]
 * 개체에 대한 그룹화 함수 호출. run확장 프로그램과 유사 하지만 아님
```kotlin
val bar = with(Foo()) {
    this.field1 = 1
    this.toBar()
}
```

<figure>
	<a href="/assets/images/1_F5fHRUgq67xrbF9924p2_w.png"> <img src="/assets/images/1_F5fHRUgq67xrbF9924p2_w.png"></a>
	<figcaption><a title="범위 함수 표">범위 함수 표</a>.</figcaption>
</figure>

[apply]: https://kotlinlang.org/docs/reference/scope-functions.html#apply
[run]: https://kotlinlang.org/docs/reference/scope-functions.html#run
[also]: https://kotlinlang.org/docs/reference/scope-functions.html#also
[let]: https://kotlinlang.org/docs/reference/scope-functions.html#let
[with]: https://kotlinlang.org/docs/reference/scope-functions.html#with
