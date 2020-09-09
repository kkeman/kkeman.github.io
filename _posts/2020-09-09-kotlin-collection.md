---
title: "Kotlin Collection 유형과 Mutable/Immutable"
header:
  overlay_image: /assets/images/overlay.jpg
date: 2020-09-09 02:00:00 -0000
categories:
  - Kotlin
  - Android
classes: wide
published: true
---

컬렉션에는 일반적으로 동일한 유형의 여러 개체 (이 숫자는 0 일 수도 있음)가 포함됩니다. 컬렉션의 개체를 elements 또는 items 이라고 합니다 

 **List**. index로 elements에 접근가능한 정렬 된 컬렉션 입니다. 순서가 중요하며 elements은 중복이 허용됩니다.
 **Set**. elements 중복 허용이 안되는 모음입니다. 순서는 중요하지 않습니다.
 **Map**. key-value에 집합입니다. 키는 고유하며 각 키는 정확히 하나의 값에 매핑됩니다. 값은 중복 될 수 있습니다.


## Collection 유형

 **Immutable:** 컬렉션 요소에 액세스하기위한 작업을 제공 하는 읽기 전용 인터페이스입니다.
 **Mutable:** 쓰기 작업 (elements 추가, 삭제 및 변경)으로 해당 읽기 전용 인터페이스를 확장 하는 변경 가능한 인터페이스입니다


변경 가능한 컬렉션을 변경한다고해서 반드시 변경되는 것은 아닙니다 `val`컬렉션 을 재 할당하려고 하면 컴파일 오류가 발생합니다.

```kotlin
val numbers = mutableListOf("one", "two", "three", "four")
numbers.add("five")   // this is OK    
//numbers = mutableListOf("six", "seven")      // compilation error
 ```


다음은 Kotlin 컬렉션 인터페이스의 다이어그램입니다.
 <figure class="align-center">
   <img src="{{ site.url }}{{ site.baseurl }}/assets/images/collections-diagram.png" alt="">
 </figure> 



## 인터페이스 구현

 * List 
**Immutable:** Kotlin의 List는 기본적으로 Immutable방식이며 get만 가능합니다.
```kotlin
val numbers = listOf("one", "two", "three", "four")
numbers[3]
 ```

**Mutable:** 추가, 삭제 및 변경이 가능하며 
```kotlin
val numbers = mutableListOf(1, 2, 3, 4)
numbers.add(5)
numbers.removeAt(1)
numbers[0] = 0
numbers.shuffle()
 ```








