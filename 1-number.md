# 패캠 알고리즘

## Number

### 문제 1

두 수를 입력받아 큰 수를 반환하는 함수를 작성하세요.

```js
1번방법
function larger(x,y){
  if(x>y){
    return x;// 만약 x가 크면 x를 반환
  }else{
    return y;// 아니면 y를 반환
}
}

2번방법
function larger(x,y){
  return Math.max(x,y);
}

3번방법
function larger(x,y){
  return x > y ? x : y;
}

내가 한 방법
const x = prompt("첫번째수를 입력하시오");
const y = prompt("두번째수를 입력하시오");

const a = parseInt(x);
const b = parseInt(y);

Math.max(a,b);

```

### 문제 2

세 수를 입력받아 그 곱이 양수이면 `true`, 0 혹은 음수이면 `false`, 둘 다 아니면 에러를 발생시키는 함수를 작성하세요.

에러를 발생시키는 코드는 다음과 같습니다.

```js
throw new Error('입력값이 잘못되었습니다.');
```

```js
function isPositive(x, y, z){
  const result = x * y * z;
  if (result > 0){
    return true;
  }
  else if(result <= 0){
    return false;
  }
  else{
    throw new Error('입력값이 잘못되었습니다.');
  }
}

** 내가 해보고 싶었던 방법 **

const x = prompt('첫번째 숫자를 입력하시오');
const y = prompt('두번째 숫자를 입력하시오');
const z = prompt('세번째 숫자를 입력하시오');
const a = parseInt(x);
const b = parseInt(y);
const c = parseInt(z);

console.log(isPositive(a,b,c))

function isPositive(a,b,c){
    const result = a * b * c;
  if (result > 0){
    return true;
  }
  else if(result <= 0){
    return false;
  }
  else{
    throw new Error('입력값이 잘못되었습니다.');
  }
}

```

### 문제 3

세 수 `min`, `max`, `input`을 입력받아, 다음과 같이 동작하는 함수를 작성하세요.

- `min`보다 `input`이 작으면, `min`을 반환합니다.
- `max`보다 `input`이 크면, `max`를 반환합니다.
- 아니면 `input`을 반환합니다.

예:

```js
limit(3, 7, 5); -> 5
limit(3, 7, 11); -> 7
limit(3, 7, 0); -> 3
```

```js
function counter(min, max, input){
  if(min > input){
    return min;
  }
  else if(input > max){
    return max;
  }
  else{
    return input;
  }
}
```

### 문제 4

어떤 정수가 짝수인지 홀수인지 출력하는 함수를 작성하세요. 이를 이용해서, 1부터 20까지의 수가 각각 짝수인지 홀수인지 출력하는 프로그램을 작성하세요.

```js
function printEvenOrOdd(x){
  if (x%2=== 0){
    console.log(x + "는 짝수");
  }
  else{
    console.log(`${x}는 홀수`);
  }
}

let i = 0;
while(i<20){
  printEvenOrOdd(i+1);
  i++;
}
```

### 문제 5

100 이하의 자연수 중 3과 5의 공배수를 모두 출력하는 프로그램을 작성하세요.

```js
내답
function commonMultiple(x){
  if(x % 5 === 0 && x % 3 === 0){
      console.log(x);
    }
  }

let i = 0;
while(i<100){
  commonMultiple(i+1);
  i++;
}

for문 풀이
for (let i=0; i < 100; i++){
  if((i+1)%3===0 && (i+1)%5===0){
  console.log(i+1);}
}
```

### 문제 6

자연수를 입력받아, 그 수의 모든 약수를 출력하는 함수를 작성하세요.

```js
let a,b=1;
function aliquot(a){
  while(b<=a){
  if(a%b===0){
  console.log(b);
  b++;
  }else{
    b++;
  }
  }
}
```

### 문제 7

2 이상의 자연수를 입력받아, 그 수가 소수인지 아닌지를 판별하는 함수를 작성하세요.

```js
function primeNumber(x){
  let y=2;
  while(y<=x){
  if(x % y === 0){
    if(y===1 && y === x){
      console.log(y);
    }
    }y++;
  }
}
```

### 문제 8

1부터 100까지의 수를 차례대로 출력하되, 자릿수에 3, 6, 9중 하나라도 포함되어 있으면 '짝!'을 대신 출력하는 프로그램을 작성하세요.

```js
for(i=1; i<100; i++){
  const str = i.toString();
  if (str.includes('3')||str.includes('6')||str.includes('9')){
    console.log("짝");}
    else{
      console.log(i);}
  }
```

### 문제 9

양의 정수를 입력받아, 다음과 같은 패턴의 출력을 하는 함수를 작성하세요.

1을 입력받은 경우:

```js
*
```

3을 입력받은 경우:

```js
*
* *
* * *
```

5를 입력받은 경우:

```js
*
* *
* * *
* * * *
* * * * *
```

```js
function stair(n){
    for(let i=0; i<n; i++){
      let str='';                   // 이 부분에서 망함 계속 초기화 해주는게 포인트!!!
      for(let j=0; j<=i; j++){
        str+='*';
      }
      console.log(str);
    }
  }

 해설 연습해라 인터프리터기가 되라
    // function stair(n){
  //   for (let i=0; i<n; i++){
  //     console.log('안쪽루프시작');
  //     for (let j = 0; j<i;j++){
  //       console.log(`ì: ${i}, j:${j}`);
  //     }
  //     console.log("안쪽루프끝");
  //   }
  // }
  메소드 이용
  function stair(n){
  for (let i=0; i<n; i++){
    const str = '*'.repeat(i+1);
    console.log(str);
  }
}
```

### 문제 10

양의 정수를 입력받아, 다음과 같은 패턴의 출력을 하는 함수를 작성하세요.

1를 입력받은 경우:

```js
*
```

3를 입력받은 경우:

```js
  *
 * *
* * *
 * *
  *
```

5를 입력받은 경우:

```js
    *
   * *
  * * *
 * * * *
* * * * *
 * * * *
  * * *
   * *
    *
```

```js
function diamond(n){
  for (let i =0; i<n; i++){
      line(n,i);
  }// 공백 포함 피라미드 별표
      for(let i =n-2 ; i>=0; i--){
      line(n,i);
      }
  }
function line(n,i){
   const str = ' '.repeat(n-i-1) + '* '.repeat(i+1);
      console.log(str);
}

line(n, n-i-2);
```

### 문제 11

두 수를 입력받아서, 두 수의 최대공약수를 반환하는 함수를 작성하세요. ([유클리드 호제법](https://ko.wikipedia.org/wiki/%EC%9C%A0%ED%81%B4%EB%A6%AC%EB%93%9C_%ED%98%B8%EC%A0%9C%EB%B2%95)을 참고하세요.)

### 문제 12

세 수를 입력받아 큰 것부터 차례대로 출력하는 함수를 작성하세요.

```js
# 선택정렬 알고리즘
function sort (x,y,z){
  let larger = x > y ? x : y;
  let smaller1 = x > y ? y:x;
  let max = larger > z ? larger : z;
  let smaller2 = larger > z ? z: larger;
  console.log(max);
  if(smaller1>smaller2){
    console.log(smaller1);
  }else{
    console.log(smaller2);
    console.log(smaller1);
  }
}
```

### 문제 13

자연수 `n`을 입력받아, `n`번째 피보나치 수를 반환하는 함수를 작성하세요.
