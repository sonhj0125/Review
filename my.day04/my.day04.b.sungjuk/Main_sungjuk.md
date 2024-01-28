## ▶ Main_sungjuk

```java
package my.day04.b.sungjuk;

import java.util.Scanner;

public class Main_sungjuk {

  public static void main(String[] args) {

    Scanner sc = new Scanner(System.in);
    Sungjuk sj = new Sungjuk();            // 기본생성자

    System.out.print("1. 학번 : ");
    sj.hakbun = sc.nextLine();              // "091234"

    System.out.print("2. 성명 : ");
    sj.name = sc.nextLine();                // "이순신"

    String input_str = "";
    int status = 0;                         // 점수를 입력해주는 상태 : 1,
                                            // 나이를 입력해주는 상태 : 2

    try {
        status = 1;
        System.out.print("3. 국어 : ");

        // === *** 유효성 검사하기(올바른 데이터인지 틀린 데이터인지 검사하는 것) *** === //

        input_str = sc.nextLine();
        byte kor = Byte.parseByte(input_str);

        if( !sj.check_jumsu(kor) ) {
            sc.close();
            return;
        }
        else {
            sj.kor = kor;
        }

        System.out.print("4. 영어 : ");
        input_str = sc.nextLine();
        byte eng = Byte.parseByte(input_str);

        if( !sj.check_jumsu(eng) ) {
            sc.close();
            return;
        }
        else {
            sj.eng = eng;
        }

        System.out.print("5. 수학 : ");
        input_str = sc.nextLine();
        byte math = Byte.parseByte(input_str);

        if( !sj.check_jumsu(math) ) {
            sc.close();
            return;
        }
        else {
            sj.math = math;
        }

        status = 2;
        System.out.print("6. 나이 = ");
        input_str = sc.nextLine();

        short age = Short.parseShort(input_str);

        if( !sj.check_age(age) ) {
              sc.close();
              return;
        }
        else {
              sj.age = age;
        }

// 성적 출력하기

			sj.sungjuk_print();
			
/*
   === 이순신님의 성적결과 ===
  1. 학번 : 091234
  2. 성명 : 이순신
  3. 국어 : 90
  4. 영어 : 80
  5. 수학 : 78
  6. 총점 : 248
  7. 평균 : 82.66666666666667
  8. 학점 : B
  9. 나이 : 27
*/

    } catch (NumberFormatException e) {
        // e.printStackTrace();
        // System.out.println(e.getMessage());

        System.out.println("\n>> 입력하신 "+input_str+"은(는) 올바른 데이터가 아닙니다.<<");
					
		if(status == 1) { // 점수를 입력해주는 상태이라면
		System.out.println("[점수에 대한 경고] 점수는 0 ~ 100 까지의 정수만 입력하세요!");
		}
		else { // 나이를 입력해주는 상태이라면
		System.out.println("[나이에 대한 경고] 나이는 20 ~ 50 까지의 정수만 입력하세요!");
		}

        sc.close();

    } // end of try_catch----------------------------------------------------

  } // end of main()-------------------------------------------------------------------------

}
