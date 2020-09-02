# MainActivity::class.java란 무엇인가



안드로이드 공부를 하면서 자꾸 저 표현때메 막히곤 했다.

처음 MainActivity는 그냥 액티비티 이름이다. 저것은 뭐 어렵지 않다.

뒤의` ::class.java`를 코틀린 기초를 배울 땐 배우지 않았고, 안드로이드는 자바 자료만 잔뜩있어서 저런게 잘 언급되지 않아 힘들었다.

class와 java라는 아주 특별한 단어들이 들어있고 `::`라는 낯선 연산자와 `.`라는 매우 익숙한 연산자가 합쳐져서 더욱 혼란스럽다.

오늘은 이것을 정리한다.

> `::`은 내가 알기로는 메소드 리퍼런스이다 .System.out의 println이란 함수를 참조하고 싶을 때 System.out::println이라고 하는 것이다. 코틀린에서도 함수를 넘겨줄 때 쓰곤 했었다. 다만 여기서도 같은의미인지는 앞으로 알게될것이다(class라는 함수가 있나?)



단도 직입적으로 이것은 Kotlin의 [Reflect](https://kotlinlang.org/docs/reference/reflection.html)를 알면 된다.

# Reflection

리플렉션은 언어와 라이브러리에서 런타임에 프로그램의 구조를 파악할 수 있게 지원해주는 것이다. 코틀린은 함수와 변수들이 일급시민이기 떄문에 이것들을 런타임에 검사 하는것은 함수형스타일과 비슷하다.

> 자바 플랫폼에서 리플렉션을 쓰려면 따로 설정을 해줘야한다

## Class References

가장 기본적인 이플렉션은 런타임에 코틀린의 클래스를 참조하는 것이다. 코틀린 클래스를 참조하려면 다음문법을 쓰라:

```
val c = MyClass::class
```

이  변수의 타입은  [KClass](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.reflect/-k-class/index.html).이다. 

코틀린 클래스 리퍼런스와 자바클래스리퍼런스는 다르다. 자바클래스리퍼런스를 얻으려면 `.java` 를 통해 `KClass` 의 java프로퍼티를 얻으라
즉 MainActivity::class.java라는 것은 클래스를 넘겨주는 것이었다.



검색중에 훌륭한 문서가 있었다.[링크](https://medium.com/harrythegreat/%EC%BD%94%ED%8B%80%EB%A6%B0%EC%9D%98-%EB%8D%94%EB%B8%94%EC%BD%9C%EB%A1%A0-%EC%B0%B8%EC%A1%B0-73ff25484586)

