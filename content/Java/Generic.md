[[꼬리물기 질문 - Generic]]
# 자바의 Generic과 컬렉션 프레임워크
일반적으로 클래스를 만들 때 아래와 같은 형식으로 만듭니다.
```Java
class Box {
    private Object item;
    
    public void setItem(Object item) {
        this.item = item;
    }
    
    public Object getItem() {
        return item;
    }
}
```

여기서 Generic을 쓴다면 이렇게 쓸 수 있습니다.
```Java
class Box<T> {
    private T item;
    
    public void setItem(T item) {
        this.item = item;
    }
    
    public T getItem() {
        return item;
    }
}
```

이렇게 했을 때 장점
1. 코드를 재사용하기 쉬워집니다. item으로 String을 담고 싶으면 `Box<String>`으로, Integer를 담고 싶다면 `Box<Integer>`로 쓸 수 있습니다.
2. 컴파일할 때 타입을 체크해주기 때문에 실수로 다른 타입의 데이터를 넣으려고 하면 바로 에러가 발생합니다. (타입 안정성)

실제로 자바의 ArrayList나 HashMap같은 컬렉션 프레임워크들도 전부 이 제네릭을 사용해서 만들어져 있습니다. 
그래서 우리가 `ArrayList<String>`이나 `HashMap<String, Integer>` 이런 식으로 쓸 수 있는 거죠.