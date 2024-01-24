## Main_while_1

###  * while문 형식

*  변수의 초기화;

```
while(조건식) {   
조건식이 참(true)이라면 반복해서 실행할 명령문을 실행하고,
조건식이 거짓(false)이라면 while의 { } 이부분을 빠져나간다. 
	         
반복해서 실행할 명령문;
증감식;   
}
```
```java
package my.day07.a.While;

public class Main_while_1 {

	public static void main(String[] args) {

  		int cnt = 5, loop = 0;

  		while(loop < cnt) {
        		System.out.println( (loop+1) + ". 안녕 자바!!");
        		loop++;
 		 } // end of while--------------------------------
  		System.out.println("\n>> 프로그램 종료 <<")

<결과>
1. 안녕 자바!!
2. 안녕 자바!!
3. 안녕 자바!!
4. 안녕 자바!!
5. 안녕 자바!!

// 또는

		cnt = 5; loop = 0;

		while(loop++ < cnt) {
			System.out.println(loop + ". Hello 자바!!);
		} // end of while--------------------------------
		System.out.println("\n>> 프로그램 종료 <<")

<결과>
1. Hello 자바!!
2. Hello 자바!!
3. Hello 자바!!
4. Hello 자바!!
5. Hello 자바!!

// 또는

		cnt = 5; loop = 0;

		while(loop < cnt) {
			System.out.println(++loop + ". Hi Eclipse!!);
		} // end of while--------------------------------
		System.out.println("\n>> 프로그램 종료 <<")

<결과>
1. Hi Eclipse!!
2. Hi Eclipse!!
3. Hi Eclipse!!
4. Hi Eclipse!!
5. Hi Eclipse!!

// 또는

		loop = 0;

		while(true) {
			System.out.println(++loop + ". Hi 이클립스!!);
			if(loop == 5)
				break;
		} // end of while--------------------------------
		System.out.println("\n>> 프로그램 종료 <<")

<결과>
1. Hi 이클립스!!
2. Hi 이클립스!!
3. Hi 이클립스!!
4. Hi 이클립스!!
5. Hi 이클립스!!

// 또는

		loop = 0;

		while( !(++loop > 5) ) {
// (++loop > 5) 가 while 문을 빠져나가는 조건
// 즉, 6이 되면 끝냄. () 안의 문장이 true 가 되면 ! 는 부정

			System.out.println(loop + ". 안녕 오라클!!);
		} // end of while--------------------------------
		System.out.println("\n>> 프로그램 종료 <<")

<결과>
1. 안녕 오라클!!
2. 안녕 오라클!!
3. 안녕 오라클!!
4. 안녕 오라클!!
5. 안녕 오라클!!

		loop = 0;
		while(true) {
			if(++loop > 10)  // 탈출조건
				break;

			if(loop%2==0)
				continue; // continue; 를 만나면 아래로 내려가지 않고 while()의 괄호 속의 조건식으로 이동

			System.out.println(loop + ".Hi Oracle!");
		} // end of while--------------------------------
		System.out.println("\n>> 프로그램 종료 <<")


  } // end of main()--------------------------------------------
}


