## Main_Operator

* 산술연산자 : +, -, *, /

* 증감연산자 : ++, --

```
★★★ 암기 ★★★

1. 후위증감연산자(a++; b--;)는 다른 연산을 다 마친 이후에 1씩 증감
   
2. 전위증감연산자(++a; --b;)는 먼저 1씩 증감을 한 후 다른 연산을 함
```

* 논리 부정 연산자 : !

* 논리 연산자 : &, |, &&, ||

```
T ∧(AND) T ∧ F ==> F 
T ∧(AND) T ∧ T ==> T

T ∨(OR) T ∨ F ==> T
T ∨(OR) T ∨ T ==> T
F ∨(OR) F ∨ F ==> F
```

*  if(조건) {   
              실행해야할 명령;         
    }   
    ==> 조건이 참일때만 실행해야할 명령; 을 구동한다.    
    ==> 조건이 거짓이라면 실행해야할 명령; 을 구동안한다.

* 비교 연산자
```
 == 같다, != 같지않다
 > 크다, < 작다, >= 같거나 크다, <= 같거나 작다
```

* 할당 연산자(연산 후 대입연산자) : +=, -=, *=, /=, %=

* 삼항 연산자

```
변수선언 = (조건식)?값1:값2

=> 변수를 선언하고 나서 값을 부여하고자 할 때 사용

=> 조건식이 '참' 이라면 변수에 ? 다음에 나오는 '값1'을 대입

=> 조건식이 '거짓'이라면 변수에 : 다음에 나오는 '값2'을 대입
```

```java
package my.day03.b.operator;

public class Main_operator {

   public static void main(String[] args) {

      System.out.println(" ==== 1. 산술연산자 + - * / %(나머지) ====");

      int n = 10;
      System.out.println("n+3 = " + n + 3); // n+3 = 103
      // n+3 = 10 문자열에 3을 합침. = 103
      System.out.println("n+3 = " + (n+3)); // n+3 = 13
   
      System.out.println("n+3 = "+ (n+3));            // n+3 = 13
		System.out.println("n+3 = "+ (n-3));            // n-3 = 7
		System.out.println("n+3 = "+ (n*3));            // n*3 = 30
		System.out.println("n+3 = "+ (n/3));            // n/3 = 3. 정수/정수 = 정수(몫)
		System.out.println("n+3 = "+ ((double)n/3));    // n+3 = 3.3333333333333335
		System.out.println("n%3 = "+ (n%3));            // n%3 = 1  10을 3으로 나눌 때의 나머지

=====================================================================

      System.out.println("\n==== 2. 증감연산자 ++ -- ====");

/*
   int a = 7;
   int b = 3;
*/
// 또는
	int a = 7; b = 3;
	System.out.println("a => " + a);   // a => 7

// a = a + 1;
// 또는
	a++;
	System.out.println("a => " + a);   // a => 8

	++a;
	System.out.println("a => " + a);   // a => 9


	System.out.println("b + > " + b);  // b => 3

// b = b - 1;
// 또는

	b--;
	System.out.println("b => " + b);   // b => 2

	--b;
	System.out.println("b => " + b);   // b => 1

    
	int x = 10, y = 10;
	int z = ++x;
	System.out.println("z => " + z);   // z => 11
	System.out.println("x => " + x);   // x => 11

	z = y++;
	System.out.println("z => " + z);   // z => 10
	System.out.println("y => " + y);   // y => 11

	System.out.println("x => " + x++); // x => 11
	System.out.println("x => " + x);   // x => 12

	System.out.println("y => " + ++y); // y => 12
	System.out.println("y => " + y);   // y => 12

=====================================================================

	System.out.println("\n==== 3. 논리 부정 연산자 ! ====");

	boolean bool = false;
	System.out.println("bool => " + bool);       // bool => false
	System.out.println("!bool => " + !bool);     // !bool => true

=====================================================================

	System.out.println("\n==== 4. 논리 연산자 & | && || ====");

	int c = 50, d = 60, e = 70;

	bool = (c > d) && ( d < e) && (c == e);      // false
// &&(그리고) 뒤는 **스킵**. &&는 그리고인데, 하나라도 false 가 나오면 false => 처리 속도 빠름
	System.out.println("bool => " + bool);	     // bool => false

	bool = (c > d) & (d < e) & (c == e);
// false & true & false 를 보여줌, & 하나는 일단 전부 수행 후 판단
	System.out.println("bool => " + bool);       // bool => false

	bool = (c > d) || (d < e) || (c == e);
// false  || true || **스킵** 
	System.out.println("bool => " + bool);       // bool => true
		
	bool = (c > d) | (d < e) | (c == e);
// false  | true | false, | 하나는 일단 전부 수행 후 판
	System.out.println("bool => " + bool);    // bool => true

=====================================================================

	int n1 = 10;

	if(n1 < 20) {
	// true
		System.out.println(">> n1은 20보다 작습니다.");
	}

=====================================================================

	System.out.println("\n------ 퀴즈1 ------\n");
	int i = 1;
	int j = i++;    // int j = i, i = i + 1
// i = 2; j = 1;

	if( (i > ++j) & (i++ ==j) ) {
/*
   j = j + 1; j => 2가 되고 이후, i > j? => 2 > 2? => false
   i == j; 이후, i = i + 1; => 2 == 2, i = 3 => true
   ----------------
   false  i ==> 3
*/

		i = i + j;
	} // false 이므로 수행하지 않음

	System.out.println("i = " + i);
// i = 3

	j = 1;
	j = i++;
// j = 1; i = i+1;
// j ==> 1, i ==> 2

	if( (i > ++j) && (i++ == j)) {
/*
   j = j+1; j==>2 이후 2 > 2? => false
   false 이므로 나머지 스킵
   ------------------------
   false   i==>2
*/
	i = i + j;
// false 이므로 수행하지 않음
	}
	System.out.println("i = " + i);
// i = 2

=====================================================================

	System.out.println("\n~~~~~~~~ 퀴즈2 ~~~~~~~~~~\n");

	int m1=0;
	n1=1;
		
	if( (m1++ == 0) | (n1++ == 2) ) {
/*
   m1 == 0, m1 = m1+1 => 1  => true
   n1 == 2 => false => n1 = n1+1 = 2
*/
	m1=42;  // 실행함
		}
	System.out.println("m1 => " + m1 + ", n1 => " + n1);  
// m1 => 42, n1 => 2

	m1 = 0;
	n1 = 1;
	if( (m1++ == 0) || (n1++ == 2) ) {
/*
   m1 == 0, m1 = m1+1 => 1 => true
   앞이 true 이므로 뒤는 스킵함
*/
	m1=42;  // 실행함
	}
	System.out.println("m1 => " + m1 + ", n1 => " + n1);
// m1 => 42, n1 => 1

=====================================================================

	System.out.println("\n==== 6. 할당 연산자(연산후 대입 연산자) ====");
		
	int no = 1;
	no += 3;
// no = no + 3; 와 같은 것이다.
	System.out.println("no = " + no);    // no = 4
	no -= 2;
// no = no - 2; 와 같은 것이다.
	System.out.println("no = " + no);    // no = 2
		
	no *= 5;
// no = no * 5; 와 같은 것이다.
	System.out.println("no = " + no);    // no = 10
		
	no /= 4;
// no = no / 4; 와 같은 것이다.
	System.out.println("no = " + no);    // no = 2
		
	no %= 3;
// no = no % 3; 와 같은 것이다.
	System.out.println("no = " + no);    // no = 2

=====================================================================

	System.out.println("\n==== 7. 삼항 연산자 ====");
		
	int num1 = 50, num2 = 60;
	int num3 = (num1 > num2)?num1:num2;
	System.out.println("num = " + num3);
// num => 60

   } // end of main()-------------------------------------------------------------------

}
