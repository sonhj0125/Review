## ▶ Main_scanner_4

```java
package my.day03.c.scanner;

import java.util.Scanner;

public class Main_scanner_4 {

  public static void main(String[] args) {

    Scanner sc = new Scanner(System.in);

    String str_no = "";
// 지역변수 초기화 필요. 그래서 String 타입의 아무거나 써도 됨.
// 또는 String Str_no = null; 해도 상관 없음
// str_no = sc.nextLine(); 에서 null 대신 내가 입력한 값으로 바꾸겠다는 의미

    try {
      System.out.print("1. 첫 번째 정수 입력 : ");
      Str_no = sc.nextLine();
      int first_no = Integer.parseInt(str_no);

      System.out.print("2. 두 번째 정수 입력 : ");
      str_no = sc.nextLine();
      int second_no = Integer.parseInt(str_no);

      System.out.println(">> " + first_no + " + " + second_no + " = " + (first_no + second_no));

    } catch(NumberFormatException e) {

        System.out.println("[경고] >> " + str_no + "는 정수가 아닙니다. 모두 정수를 입력해주세요! << ");

    } // end of try_catch---------------------------------------------

  sc.close();
  
  } // end of main()---------------------------------------------------------------------

}
