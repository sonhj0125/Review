## ▶ Main_scanner_1

* System.in 은 입력장치(키보드)
  
* System.out 은 출력장치(모니터)
  
* Scanner sc 는 키보드에서 입력된 문자열을 읽어들이는 객체
  
* sc.nextLine (); 은 키보드로부터 입력받은 문장을 읽어들이는 것인데,   
  엔터(종결신호)까지 모두 읽어들인 후 스캐너 버퍼(sc)에 아무것도 남기지 않는다.

* sc.nextInt(); 는 정수(int)를 읽어들이는 것인데, 종결자가 공백 또는 엔터이다.   
  종결자(공백 또는 엔터) 앞까지의 입력해준 **정수**를 읽어온다.   
  sc.nextInt(); 를 사용하면 스캐너(sc) 버퍼에는 종결자(공백 또는 엔터)가 삭제 되는 것이 아니라
  그대로 남아 있게 된다.

* sc.nextDouble; 는 실수(Double)를 읽어들이는 것인데, 종결자가 공백 또는 엔터이다.   
  종결자(공백 또는 엔터) 앞까지의 입력해준 **실수**를 읽어온다.   
  sc.nextDouble(); 를 사용하면 스캐너(sc)버퍼에는 종결자(공백 또는 엔터)가 삭제되는 것이 아니라
  그대로 남아 있게 된다.

 * sc.next(); 은 단어를 읽어들이는 것인데, 종결자가 공백 또는 엔터이다.   
   종결자(공백 또는 엔터) 앞까지의 입력해준 **문자열**을 읽어온다.   
   sc.nextDouble(); 를 사용하면 스캐너(sc)버퍼에는 종결자(공백 또는 엔터)가 삭제되는 것이 아니라 그
   대로 남아 있게 된다.

```java

package my.day03.c.scanner;

import java.util.Scanner;

public class Main_scanner_1 {

  public static void main(String[] args) {

  Scanner sc = new Scanner(System.in);        // 파라미터가 들어있는 생성자

  System.out.print("1. 문장을 입력하세요 => ");
  String inputStr = sc.nextLine();

  System.out.println("입력한 문장 => " + inputStr);
// 1. 문장을 입력하세요 => 다시 만나는 날
// 입력한 문장 => 다시 만나는 날


  System.out.println("\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n");

  System.out.print("2. 정수를 입력하세요 => ");
  int inputNum = sc.nextInt();

  System.out.println("입력한 정수 => " + inputNum);
// 2. 정수를 입력하세요 => 2326
// 입력한 정수 => 2326

// byte inputNum1 = sc.nextByte();
// short inputNum2 = sc.nextShort();
// int inputNum3 = sc.nextInt();
// long inputNum4 = sc.nextLong();

  sc.nextLine();
// 스캐너(sc) 버퍼에 남아있는걸 비우는(제거하는) 효과
// 공백이 종결자, 정수를 234 567 적으면, 567 라는 쓰레기가 남아서
// '다음 실수를 입력하시오'에 자동적으로 입력


  System.out.println("\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n");

  System.out.print("3. 실수를 입력하세요 => ");

  double inputDb1 = sc.nextDouble();
// float inputft1 = sc.nextFloat();

  System.out.println("입력한 실수 => " + inputDb1);
// 3. 실수를 입력하세요 => 21.484564
// 입력한 실수 => 21.484564

  sc.nextLine();


  System.out.println("\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n");

  System.out.print("4. 단어를 입력하세요 => ");
  String input_word = sc.next();

  System.out.println("입력한 단어 => " + input_word);
// 4. 단어를 입력하세요 => 저의 이름은 이순신입니다.
// 입력한 단어 => 저의

  sc.nextLine();


  System.out.println("\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n");

  System.out.print("5. 새로운 문장을 입력하세요 => ");
  String input_str2 = sc.nextLine();

  System.out.println("입력한 문장 => " + input_str2);

  sc.close();

  } // end of main()-----------------------------------------------------------------------

}
