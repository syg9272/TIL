Generic

-   Object의 장점인 여러가지 타입을 하나의 클래스로 적용이 가능하다는 장점을 가져오고
-   런타임시에 원하지 않는 타입이 들어온걸 체크해야 하고 값을 추출시에 형변환을 해야만 했던 단점을 보완
-   Generic Type : 클래스<타입파라미터>
-   타입파라미터 이름으로 권장
-   T : Type
-   E : Element (ex) ArrayList)
-   K : Key
-   V : Value (ex) Map)
-   N : Number

타입 파라미터 제한

-   필요에 따라서 구체적인 타입으로 제한이 필요한 경우
-   Generic Type 선언시 특정한 타입만 받을 수 있도록 제한
-   <T extends Drink> ----> T 타입 파라미터에는 Drink포함 Drink의 자손 타입으로 제한
-   <T super Drink> ----> T 타입 파라미터에는 Drink포함 Drink의 조상 타입으로 제한

```
Fruit f = new Apple();	// 객체 형변환에서는 가능했지만
Box06<Fruit> box01 = new Box06<Apple>();	// 컴파일에러
// 타입 파라미터 제한을 통해 다형성개념으로 접근가능
Box06<? extends Fruit> box01 = new Box06<Apple>(); 	
```

class 클래스명<타입파라미터> \*

-   제너릭메서드
-   선언
-   접근 제한자 <타입파라미터> 반환타입 메서드명(매개변수...)
-   호출
-   변수명.<타입파라미터>메서드명(매개변수...)
