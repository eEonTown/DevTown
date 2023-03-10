## JavaScript Prototype
JavaScript는 객체지향 언어라고는 하지만 다른 객체지향 언어에는 있는 Class가 JavaScript에는 없습니다.
<br><br>
그래서 보통 JavaScript에선 객체를 상속기능을 구현하기 위해서 프로토타입을 사용한다고 합니다.
이게 JavaScript가 프로토타입 기반 객체지향 언어라고 불리우는 이유입니다.
<br><br>
ECMA6 표준에서 Class문법이 추가 되었다고는 하지만 Class문법이 나왔다고 해서 JavaScript가 클래스 기반으로 바뀐것은 아니고 개인적인 생각으로는 결국 Class문법도 프로토타입을 사용하고, 기존에 프로토타입을 사용해서 작성했던 구문을 보다 간편하게 사용하기위해 만든 문법이 아닐까라고 생각합니다.
<br><br>

## Prototype객체
함수 객체를 생성하게 되면 그 객체에는 prototype이라는 객체가 생성이되고, 그 프로토타입 객체에는 constructor라는 속성이 존재해서 서로를 참조할 수 있게 됩니다.
<br>
![image](https://user-images.githubusercontent.com/102468071/209544453-e751d811-81ac-4087-8d08-44f695588c2e.png)

[https://www.nextree.co.kr/p7323/](https://www.nextree.co.kr/p7323/)

<br><br>

함수를 생성하고 생성자 함수로 객체를 생성하게 되면 그 객체는 __proto__속성으로인해 상위 프로토타입 객체를 참조할 수 있습니다.
<br><br>
즉, 프로토타입 객체는 생성자 함수를 통해 생성된 모든 객체의 모태가 되며, 생성된 모든 객체는 프로토타입 객체를 참조합니다.
<br>
![image](https://user-images.githubusercontent.com/102468071/209544478-53faa6f1-9b7f-479e-80eb-3ad6b83509f4.png)

[https://www.nextree.co.kr/p7323/](https://www.nextree.co.kr/p7323/)

<br><br>

위에서 언급한 __proto__는 부모 프로토타입 객체를 가리키는 링크를 담고 있다는 특징이 있습니다.
그래서 __proto__의 특징을 이용해서 부모객체의 property나 method를 발견할 때까지 부모의 부모객체를 거슬러 올라가면서 검색하는 것을 Prototype체인이라고 합니다.
<br><br>
그래서 Prototype체인에 대해서 간략하게 정리하자면 어떤 객체의 property나 method에 접근 하고자 할 때 해당 객체의 부모 객체에도 접근해서 사용이 가능하다는 의미입니다.
<br><br>
다만, 찾고자 하는 property나 method가 없다면 마지막에는 Object.prototype에 도달하게 되고, Object.prototype에도 찾고자하는 정보가 없다면 최종적으로 undefined를 반환하게 됩니다.
