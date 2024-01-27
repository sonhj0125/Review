## ▶ Main_wrapper

### wrapper 클래스

| 기본자료형(원시형, primitive) | wrapper 클래스 |
| :--: | :--: |
 byte | Byte 
 short |Short
 int | Integer  
 long | Long
 char | Character
 float | Float
 double | Double
 boolean | Boolean 
 
 
* 기본자료형(원시형)은 데이터 저장 및 4칙연산 에서만 사용하는 것
  
* wrapper 클래스는 데이터 저장 및 4칙연산 뿐만 아니라 아주 다양한 기능의 메소드가 제공되므로 다방면으로 사용되어진다.
---
### Boxing(박싱, 포장을 하는것)
* 기본자료형(boolean, byte, short, int, long, char, float, double)으로 되어진 변수를
* 객체타입인 Wrapper 클래스(Boolean, Byte, Short, Integer, Long, Character, Float, Double) 타입의 객체로 만들어주는 것
		

 ### UnBoxing(언박싱, 포장을 푸는것)
* Wrapper 클래스(Boolean, Byte, Short, Integer, Long, Character, Float, Double)로 되어져 있는 객체를
* 기본자료형(boolean, byte, short, int, long, char, float, double)으로 만들어주는 것을 말한다.

```java
package my.day04.a.wrapper;

import java.util.Scanner;

public class Main_wrapper {

  public static void main(String[] args) {

    char ch = 'a';
    System.out.println("ch => " + ch);    // ch => a
    System.out.println( (ch+1) );         // (int)ch+1 => 97+1 => 98
    System.out.println( (char)(ch-32) );  // (int)ch-32 => 65 => (char) => A

// Character chr = new Character('a');  => jdk 1.8에서 사용
// 생성자 Character(char) 는 더이상 사용되지 않으며, 제거 대상으로 표시되었습니다.

    Character chr = Character.valueOf('a');  // jdk 11에서 사용
    System.out.println("chr => " + chr);     // chr => a


    System.out.println("\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n");

    System.out.println((char)('a' - 32));              // 65 => A

    System.out.println(Character.toUpperCase('a'));    // A
    System.out.println(Character.toLowerCase('A'));    // a
    System.out.println(Character.toUpperCase(97));     // 97 = a, a => A, 65
    System.out.println(Character.toLowerCase(65));     // 65 = A, A => a, 97

    System.out.println("\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n");

	char ch2 = 'c'; // 99
		
		if('A' <= ch2 && ch2 <= 'Z') {       // ch2가 대문자인지 알아보기, A는 65
			System.out.println(ch2+"는 대문자 입니다.");
		}
		else if('a' <= ch2 && ch2 <= 'z') {   // ch2가 소문자인지 알아보기, a는 97
			System.out.println(ch2+"는 소문자 입니다.");
		}
		else if('0' <= ch2 && ch2 <= '9') {   // ch2가 숫자인지 알아보기, 0은 48
			System.out.println(ch2+"는 숫자 입니다.");
		}
		else {  			      // ch2가 특수문자인지 알아보기
			System.out.println(ch2+"는 특수문자 입니다.");
		}


	char ch3 = '5';
		
		if(Character.isUpperCase(ch3)) {      // 대문자인지 알아보기
			System.out.println(ch3+"는 대문자 입니다.");
		}
		else if(Character.isLowerCase(ch3)) {  // 소문자인지 알아보기
			System.out.println(ch3+"는 소문자 입니다.");
		}
		else if(Character.isDigit(ch3)) {      // 숫자인지 알아보기
			System.out.println(ch3+"는 숫자 입니다.");
		}
		else {   			       // ch2가 특수문자인지 알아보기
			System.out.println(ch3+"는 특수문자 입니다.");
		}



	System.out.println("\n==============================\n");
		
		String str = "Baby";

//  ★★★ 암기 ★★★
// index  (Baby) = (0123) , 위치값을 나타낼때, 0부터 시작
		
	char ch1 = str.charAt(0);  // 'B'가 리턴
		System.out.println(ch1);   // B
		
		ch1 = str.charAt(3);       // 'y'
		System.out.println(ch1);   // y
				
		
		Scanner sc = new Scanner(System.in);
		System.out.print(">> [퀴즈] 한글을 포함한 문장을 입력하세요. => ");

		String input_str = sc.nextLine();		
// I am a boy             => 첫글자 I 은(는) 대문자입니다.
// superman               => 첫글자 s 은(는) 소문자입니다.
// 8080 tomcat            => 첫글자 8 은(는) 숫자입니다.
// 안녕하세요 goodmoring  => 첫글자 안 은(는) 한글입니다.
//  좋은하루 되세요       => 첫글자  은(는) 공백입니다.
// @gmail.com             => 첫글자 @ 은(는) 특수문자입니다.


	char c = input_str.charAt(0);
		
		if(Character.isUpperCase(c)) {   	// 대문자인지 알아보기
			System.out.println("첫글자 "+c+"은(는) 대문자 입니다.");
		}
		else if(Character.isLowerCase(c)) {   	// 소문자인지 알아보기
			System.out.println("첫글자 "+c+"은(는) 소문자 입니다.");
		}
		else if(Character.isDigit(c)) {   	// 숫자인지 알아보기
			System.out.println("첫글자 "+c+"은(는) 숫자 입니다.");
		}
		else if('가' <= c && c <= '힣') {  	// 한글인지 알아보기
			System.out.println("첫글자 "+c+"은(는) 한글 입니다.");
		}
		else if( c == ' ') {   			// 공백인지 알아보기
			System.out.println("첫글자 "+c+"은(는) 공백 입니다.");
		}						
		else {  				 // ch2가 특수문자인지 알아보기
			System.out.println("첫글자 "+c+"은(는) 특수문자 입니다.");
		}


	System.out.println("\n======================================\n");

	System.out.println("== 오토박싱, 오토언박싱에 대해 알아보기 ==");

	int a1 = 10;

	Integer a2 = Integer.valueOf(a1);	// jdk 11 방식
// 	Integer a2 = new Integer(a1); jdk 1.8 방식  // Boxing(박싱)

	System.out.println("a2 => " + a2);	// a2 => 10

	int b1 = 10;
	Integer b2 = b1;			// Auto Boxing(박싱)
	System.out.println("b2 => " + b2); 	// b2 => 10

	System.out.println("\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n");

	Integer a3 = Integer.valueOf(20);
	int a4 = a3.intValue();			// UnBoxing(언박싱)
	System.out.println("a4 => " + a4);	// a4 => 20

	int a5 = Integer.valueOf(20);		// Auto UnBoxing(언박싱)
	System.out.println("a5 => " + a5);	// a5 => 20

	sc.close();

  } // end of main()------------------------------------------------------------------------

}






 
