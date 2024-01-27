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







  } // end of main()------------------------------------------------------------------------
}






 
