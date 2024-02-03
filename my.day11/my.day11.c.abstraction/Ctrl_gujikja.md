## ▶ Ctrl_gujikja

* Main 메소드를 실행하기 위한 방식

```java

package my.day11.c.abstraction;

import java.util.Scanner;

import my.util.MyUtil;

public class Ctrl_gujikja {

  // == 메인 메뉴를 보여주는 메소드 생성하기 == //

  void main_menu() {
    System.out.println("\n === 메인메뉴 ===\n"
                        + "1. 구직자 회원가입   2. 구직자 모두보기   3. 검색하기   4. 프로그램 종료\n");
    System.out.print("▶ 메뉴번호 선택 : ");	

} // end of void main_menu()---------------------------------------------------

  // == 구직자(Gujikja) 신규 회원가입시
  // Gujikja 클래스의 field 의 요구사항에 모두 맞으면,
  // Gujikja[] gu_arr 에 저장시켜주는 메소드 생성하기 == //

  void register(Scanner sc, Gujikja[] gu_arr) {

    if(Gujikja.count < gu_arr.length) {

        String userid;
        String passwd;
        String name;
        String jubun;

        boolean isUse_userid;

            do {
              isUse_userid = true;  // 초기화
              System.out.print("1. 아이디 : ");
              userid = sc.nextLine();

              // == 가입된 회원들에 대해 중복아이디 검사하기 == //

              // if( userid.trim().isEmpty() ) {} => jdk 1.8
              if( userid.isBlank() ) { // jdk 11
                System.out.println(">> 아이디는 필수 입력사항 입니다. <<\n");
                isUse_userid = false;
              }
              else {
                for(int i=0; i<Gujikja.count; i++) {
                  if( userid.equals(gu_arr[i].userid) ) {
                    System.out.println(">> 이미 사용중인 아이디 입니다. <<\n");
                    isUse_userid = false;
                  }
                } // end of for----------------------------------
              }
            } while ();
            // end of do_while------------------------------------------------

            // 비밀번호는 필수 입력사항이면서 비밀번호 조건에 맞을 때 까지 반복
            boolean isUse_passwd;

            do {
              isUse_passwd = true;
              System.out.print("2. 비밀번호 : ");
              passwd = sc.nextLine();

              if ( !MyUtil.isCheckPasswd(passwd) ) {
                System.out.println("[경고] 비밀번호는 8글자 이상 15글자 이하의 대, 소문자, 숫자, 특수기호가 혼합되어야만 합니다.\n");

              }

            } while();
            // end of do_while-----------------------------------------------------

    } // end of if(Gujikja.count < gu_arr.length)------------------------------------



  } // end of void register(Scanner sc, Gujikja[] gu_arr)-----------------------------






}
