# 주석

주석 작성은 개발보다는 문서 작성에 가까운 일이라 개발자에게는 가장 인기 없고 최대한 미루고 싶어하는 일 입니다. 하지만 전체적인 코드의 유지보수를 위해 주석은 정말 중요합니다. 주석이 없는 파일에 작업할 때는 새로운 모험을 하는 것처럼 흥미진진한 기분을 느낄 수 있지만, 프로젝트 마감일이 코 앞이면 그건 모험이아니라 고문입니다. 적절한 주석이 있으면 코드를 처음 부터 일일이 살펴볼 필요 없이 코드의 작성 이유를 바로 파악하고 작업을 시작할 수 있습니다.

## 2.1 한 줄 주석
한 줄 주석은 두 개의 슬래시를 이용해 작성하고, 그 줄에서 끝납니다.
```javascript
// 한 줄 주석
```
보통 두 개의 슬래시를 입력하고 주석을 입력하기 전에 한 칸을 띄웁니다. 한 줄 주석은 3가지 방법으로 사용합니다.

- **주석을 입력하기 전, 한 줄을 비우고 시작하며 주석은 설명할 코드 바로 윗줄에 작성합니다. 들여쓰기 단계는 설명할 코드에 맞춥니다.**
- **한 줄 주석은 꼬리 주석을 입력할 때 사용합니다. 줄 끝에 입력하는 꼬리 주석은 적어도 한 단계 들여쓰기를 한 후에 입력합니다. 이 때 꼬리 주석도 최대 줄 길이를 넘으면 안됩니다. 주석을 입력하기에 공간이 부족하면 코드 윗줄에 주석을 입력합니다.**
- **한 줄 주석은 코드를 주석처리할 때 사용합니다. 실제로 많은 에디터에서 코드를 주석 처리할 때 자동으로 한 줄 주석으로 처리합니다.**

코드를 주석 처리할 때를 제외하고는, 연속으로 한 줄 주석을 사용하면 안됩니다. 주석이 길어지면 여러 줄 주석을 사용해야 합니다. 예제를 통해 살펴보겠습니다

```javascript
// 좋은 예
if (condition) {

  // 이 문장에 도달한다면, 모든 보안 요소 체크가 통과 한 것임.
  allowed();
}

// 나쁜 예 : 주석 전에 빈 줄이 추가되지 않음
if (condition) {
  // 이 문장에 도달한다면, 모든 보안 요소 체크가 통과 한 것임.
  allowed();
}

// 나쁜 예 : 잘못된 들여쓰기
if (condition) {

// 이 문장에 도달한다면, 모든 보안 요소 체크가 통과된 것임.
  allowed();
}

// 좋은 예
let result = someting + somethingElse;  // somethingElse는 절대 null 값이면 안됨.

// 나쁜 예 : 코드와 주석 사이에 빈 칸을 더 입력해야함.
let result = someting + somethingElse; // somethingElse는 절대 null 값이면 안됨.

// 좋은 예
// if (condition) {
//  doSomething();
//  thenDoSomethingElse();
// }

//나쁜 예 : 주석을 길게 적을 거면 여러줄 주석을 이용해야함
// 이 후에 나오는 코드는 상당히 복잡합니다. 코드에 대해 설명하겠습니다.
// 여기서 확인할 부분은 condition 값이 true 인지 체크하여 허용된 사용자만
// 들어올 수 있도록 하는 것입니다. condition 변수는 여러 함수를 거치는 동안
// 변경 될 수 있고, 세션이 살아있는 동안 언제든지 변할 수 있습니다.
if (condition) {
  
  // 이 문장에 도달한다면, 모든 보안 요소 체크가 통과된 것임.
  allowed();
}
```

## 2.2 여러 줄 주석
여러 줄 주석은 말 그대로 여러 줄에 걸친 주석을 파일에 입력할 때 사용하며 /* 로 시작하여, */로 끝마칩니다. 여러 줄 주석이라고해서 꼭 여러 줄에 걸쳐있지 않아도 됩니다. 여러 줄 주석을 이용해 한 줄만 입력해도 되고, 여러 줄로 입력해도 됩니다. 즉 작성자 마음입니다. 다음은 여러 줄 주석에 대한 예제로 모두 유효한 방법입니다.
```javascript
/* 내가 추가한 주석 */

/* 또 다른 주석.
이 주석은 두 줄에 걸쳐 있습니다. */

/* 
또 다른 주석 한 개 더
이 주석도 두 줄에 걸쳐 있습니다.
 */
 ```
마지막으로 최소 세줄이 필요한 주석이 있습니다. 예제를 보며 확인하겠습니다.
```javascript
/*
 * 또 다른 주석 한 개 더
 * 이 주석도 두 줄에 걸쳐 있습니다.
 */
```
이 주석은 별표를 기준으로 왼쪽 정렬이 되어 있어 더 깔끔하고 읽기에도 좋습니다. 
 
## 2.3 주석 쓰기
주석은 개발자 사이에서 항상 논란이 많은 주제입니다. 일반적으로는 명확하지 않은 것에 대해 주석을 쓰고, 코드 자채로 충분히 설명 가능한 부분에는 주석을 쓰지 않습니다.
```javascript
// 나쁜 예

// count 초기화
let count = 10;
```
예제를 언 뜻 보아도 count가 초기화 되는 것을 알 수 있습니다. 따라서 예제의 주석은 전혀 의미가 없습니다. 하지만 10에 특별한 의미가 있다면 왜 10으로 초기화하는지 코드만으로는 알 수 없으므로 주석으로 10에 대해 설명해야 합니다.
```javascript
// 좋은 예

// 이 값을 수정하면, A가 작동합니다.
let count = 10;
```
count 변수의 값을 변경하면 A가 실행됩니다. 주석이 없었다면 아무도 몰랐을 테니 이 주석은 적절한 주석이다라고 볼 수 있습니다. 

일반적으로 주석은 코드를 명확하게 해야 할 곳에 추가해야 합니다.

### **2.3.1 이해하기 어려운 코드**
이해하기 어려운 코드에는 반드시 주석을 추가해야 합니다. 코드의 역할에 따라 여러 줄 주석을 사용하거나 한 줄 주석을 여러 개 사용하거나 이 둘을 섞어서 사용합니다. 핵심은 코드의 의도를 다른 사람에게 이해시키는 것 입니다. 예제로 YUI 라이브러리의 Y.mix() 메서드 코드를 살펴보겠습니다.
```javascript
// 좋은 예

if (mode) {

  /*
   * mode가 2이면(한 prototype에서 다른 prototype으로, 한 object에서 다른 object로)
   * 반복문을 수행하여 prototype과 prototype을 합치고
   * object 대 object로 합치는 기능은 나중에 수행한다.
   */
   if (mode === 2) {
     Y.mix(receiver.prototype, supplier.prototype, overwrite,
         whitelist, 0, merge);
   }

  /* 
   *입력된 모드에 따라 supplier에서 receiver로 복사하거나 receiver에서 supplier로
   * 프로토타입을 복사한다.
   */
  from = mode === 1 || mode === 3 ? supplier.prototype : supplier;
  to = mode === 1 || mode === 4 ? receiver.prototype : receiver;

  /*
   * supplier나 receiver에 프로토타입 프로퍼티가 없으면
   * from이나 to 변수에 undefined 값이 저장된다.
   * 이런 경우에는 이후 로직을 수행하지 않고 receiver를 반환한다.
   */
  if (!from || !to) {
    return receiver;
  } else {
    from = supplier;
    to   = receiver;
  }
}
```
Y.mix() 메서드는 로직 진행 방식을 결정하는 데 상수를 사용합니다. 인자 mode는 상수 1, 2, 3, 4 중 하나이지만 숫자만으로는 이상수가 무엇을 의미하는지 이해하기 어렵습니다. 그렇지만 이 코드의 주석은 상황별로 어떤 작업이 수행되는지 잘 설명하고 있어 잘 쓰인 주석으로 볼 수 있습니다.
 
### **2.3.2 오해하기 쉬운 코드**
다른 사람이 오해할 수 잇는 코드에는 주석을 써야 합니다. 가끔 코드에 문제가 될 만한 부분을 보면 그냥 넘어가지 못하는 개발자 덕분에 큰 일을 겪기도 합니다. 코드 자체가 문제인 경우를 제외하고는 본인은 '고친다'고 생각했겠지만 실제로는 오히려 문제를 만들어 낼 때가 있습니다. 이런 문제를 방지하려면 다른 개발자가 오해할 만한 코드에는 반드시 주석을 추가해야합니다. YUI에서 가져온 예제를 살펴보겠습니다.
```javascript
while (element &&(element = element[axis])) { // 주의: 대입한게 맞아요.
  if ( (all || element[TAG_NAME]) &&
    (!fn || fn(element)) ) {
      return element;
    }
}
```
이 예제에서는 while 반복문의 조건식에 할당 연산자를 사용했습니다. 물론 일반적으로는 이렇게 코드를 작성하지도 않으며, 린트 툴이 그냥 넘어가지도 않습니다. 하지만 이런 코드가 주석 없이 존재한다면 == 대신 =으로 잘 못 썻구나 라고 오해할 만한 상황이 만들어집니다. 이를 위해 예제에서는 꼬리 주석을 추가해 할당 연산자를 일부러 사용했다고 알리고 있습니다. 이처럼 주석이 있으면 다른 개발자가 보고 마음대로 수정하는 일은 없을 겁니다.

### **2.3.3 특정 브라우저 핵**
자바스크립트 개발을 하다보면 오래된 브라우저를 지원하기 위해 비효율적인데다가 깔끔하지도 않은 코드를 작성해야 할 때가 있습니다. 이런 코드는 일종의 '오해하기 쉬운 코드'로 볼 수 있습니다. 특정 브라우저를 지원하기 위해 작성한 코드라는 것이 명확하지 않으면 다른 개발자가 봤을 때 문제 있는 코드라 생각할 수 있습니다. 아래는 YUI 라이브러리의 Y.DOM.contains() 메서드에서 가져온 예제입니다.
```javascript
let ret = false;

if ( !needle || !element || !needle[NODE_TYPE] || !element[NODE_TYPE]) {
  ret = false;
} else if (element[CONTAINS]) {
  
  // IE와 사파리에서 변수 needle이 ELEMENT_NODE가 아니면 에러가 발생한다.
  if (Y.UA.opera || needle[NODE_TYPE] === 1) {
    ret = element[CONTAINS](needle);
  } else {
    ret = Y_DOM._bruteContains(element. needle);
  }
} else if (element[COMPARE_DOCUMENT_POSITION]) { // gecko
  if (element === needle || !!(element[COMPARE_DOCUMENT_POSITION](needle) & 16)) {
    ret = true;
  }
}
```
6번째 줄에는 굉장히 중요한 주석이 달려 있습니다. IE와 사파리는 기본적으로 contains()메서드를 지원하지만, 변수 needle이 DOM요소가 아니면 에러가 발생합니다. 그렇기 때문에 주석으로 if문이 필요한 이유를 알 수 있습니다.

## 2.4 문서화 주석
문서화 주석은 기술적으로는 자바스크립트에서 지원하는 영역이 아니지만, 굉장히 많이 사용되고 있습니다. 문서화 주석에는 다양한 포맷이 있지만 JavaDoc 문서 포맷이 가장 많이 쓰입니다. 여러 줄 주석과 유사하지만 별표(*)가 하나 더 붙어 /**로 주석을 시작하고 그 다음 줄부터 항목마다 @를 앞에 붙입니다. YUI 예제를 살펴봅시다.
```javascript
/**
인자로 넘어온 객체들의 모든 프로퍼티를 갖는 새로운 객체를 반환합니다.
프로퍼티가 중복될 경우 나중에 들어온 객체의 프로퍼티로 덮어쓰게 됩니다.

인자를 한 개의 객체만 넘길 경우 얕은 복사를 수행합니다.
깊은 복사의 경우, 'clone()'을 사용하십시오.

@method merge
@param {Object} objects* 합치고 싶은 객체들 (1개 이상)
@return {Object} 프로퍼티를 합친 새로운 객체
**/
Y.merge = function () {
  let args = arguments,
    i      = 0,
    len    = args.length,
    result = {};

  for (; i < len; ++i) {
    Y.mix(result, args[i], true);
  }

  return result;
};
```
YUI 라이브러리는 이 주석을 문서화하는데 YUIDoc이란 툴을 사용합니다. 주석을 문서화 하는 툴킷에는 JSDoc도 있습니다. JSDoc은 특정 라이브러리에 구애받지 않고 사용할 수 있는 툴킷으로 YUIDoc과 문서화 주석 포맷이 같습니다. 오픈 소스 프로젝트에 많이 사용되고 있으며 구글에서도 사용하고 있습니다.

문서화 주식을 사용할 때에는 아래 항목을 모두 만족해야 합니다.
- **모든 메서드**  
모든 메서드에 대한 설명이 추가되어야 하며, 인자 값이나 반환 값에 대한 설명도 있어야 한다.

- **모든 생성자**  
생성자에 대한 주석에는 사용자 정의 타입의 목적이 포함되어야 하며, 인자 값에 대한 설명 도 있어야한다.

- **주석을 추가한 메서드를 가진 모든 객체**  
객체의 메소드에 문서화 주석이 추가되었다면, 적절한 문서 생성을 위해 객체에도 주석을 추가해야 한다.

물론, 정확한 주석 포맷과 함께 주석 작성 방법은 사용하는 문서 생성기가 요구하는 방식을 따라야 합니다.