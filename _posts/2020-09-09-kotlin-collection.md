---
title: "Kotlin Collection 유형과 Mutable/Immutable"
header:
  overlay_image: /assets/images/overlay.jpg
date: 2020-09-09 02:00:00 -0000
categories:Kotlin,Android
classes: wide
published: true
---

컬렉션에는 일반적으로 동일한 유형의 여러 개체 (이 숫자는 0 일 수도 있음)가 포함됩니다. 컬렉션의 개체를 elements 또는 items 이라고 합니다 

**List:** index로 elements에 접근가능한 정렬 된 컬렉션 입니다. 순서가 중요하며 elements은 중복이 허용됩니다.

**Set:** elements 중복 허용이 안되는 모음입니다. 순서는 중요하지 않습니다.

**Map:** key-value에 집합입니다. 키는 고유하며 각 키는 정확히 하나의 값에 매핑됩니다. 값은 중복 될 수 있습니다.


# Collection 유형

 **Immutable:** 컬렉션 요소에 액세스하기위한 작업을 제공 하는 읽기 전용 인터페이스입니다.
 
 **Mutable:** 쓰기 작업(elements 추가, 삭제 및 변경)으로 해당 읽기 외에 확장 및 변경 가능한 인터페이스입니다


Mutable 컬렉션을 변경한다고해서 반드시 변경되는 것은 아닙니다 `val`에 컬렉션 을 재 할당하려고 하면 컴파일 오류가 발생합니다.

```kotlin
val numbers = mutableListOf("one", "two", "three", "four")
numbers.add("five")   // this is OK    
//numbers = mutableListOf("six", "seven")      // compilation error
```


다음은 Kotlin 컬렉션 인터페이스의 다이어그램입니다.
 <figure class="align-center">
   <img src="{{ site.url }}{{ site.baseurl }}/assets/images/collections-diagram.png" alt="">
 </figure> 



# 인터페이스 구현

## List
목록 elements(null 포함)는 중복 될 수 있습니다. 목록에는 동일한 개체 또는 단일 개체의 항목이 얼마든지 포함될 수 있습니다. 두 목록의 크기가 같고 동일한 위치에 구조적으로 동일한 요소 가 있으면 동일한 것으로 간주됩니다 .

**Immutable:** Kotlin의 List는 기본적으로 Immutable방식이며 get만 가능합니다.
```kotlin
val numbers = listOf("one", "two", "three", "four")
numbers[3]
 ```

**Mutable:** mutableListOf(), arrayListOf()가 있으며 추가, 삭제 및 변경이 가능합니다.
```kotlin
val numbers = mutableListOf(1, 2, 3, 4)
numbers.add(5)
numbers.removeAt(1)
numbers[0] = 0
numbers.shuffle()
 ```

## Set
고유 한 요소를 저장합니다. 그들의 순서는 일반적으로 정의되지 않습니다. null요소도 고유합니다.

**Immutable:** 
```kotlin
val numbers = setOf<Int>(1, 2, 3, 4, 5, 6)
numbers.size
numbers.contains(1)
numbers.isEmpty()
 ```

**Mutable:** mutableSetOf, hashSetOf, linkedSetOf, sortedSetOf 등의 함수가 있습니다.
```kotlin
val numbers = mutableSetOf<Int>(1, 2, 3, 4, 5, 6)
numbers.add(10)
numbers.remove(4)
numbers.removeIf({ it < 3 })
 ```

## Map
Collection인터페이스의 상속자가 아닙니다. 그러나 Kotlin Collection 유형 이기도합니다. Map는 키-값 (또는 elements)을 저장 합니다. 키는 고유하지만 다른 키 들은 동일한 값으로 쌍을 이룰 수 있습니다.

**Immutable:** 
```kotlin
val numbersMap = mapOf("key1" to 1, "key2" to 2, "key3" to 3, "key4" to 1)
if ("key2" in numbersMap)
if (1 in numbersMap.values)
numbersMap.containsValue(1)
 ```

**Mutable:** mutableMapOf, hashMapOf, linkedMapOf, sortedMapOf 등의 함수가 있습니다.
```kotlin
val numbersMap = mutableMapOf("one" to 1, "two" to 2)
numbersMap.put("three", 3)
numbersMap["one"] = 11
 ```


