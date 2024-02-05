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
                isUse_passwd = false;
              }

            } while(!isUse_passwd);
            // end of do_while-----------------------------------------------------


// 성명은 필수 입력사항이므로 그냥 엔터나 공백만으로 된 것이 아닐때 까지 반복해야 한다.
// 성명은 2글자 이상 6글자 이하의 한글로만 되어져야 한다.

        boolean isUse_name;
        do {
          isUse_name = true;
          System.out.print("3. 성명 : ");
          name = sc.nextLine();

          if(name.isBlank()) {
            isUse_name = false;
          }
          else {
            char[] ch_arr = name.toCharArray();

            if(2 <= ch_arr.length && ch_arr.length <= 6) {
              isUse_name = false;
            }
            else {
              char[] ch_arr = name.toCharArray();

              if(2 <= ch_arr.length && ch_arr.length <= 6) {

                for(int i=0; i<ch_arr.length; i++) {
                  if( !('가' <= ch_arr[i] && ch_arr[i] <= '힣') ) {
                    isUse_name = false;
                    break;
                  }
                } // end of for-------------------------------------------------
              }
              else {
                isUse_name = false;
              }
            }

            if(!isUse_name) {
              System.out.println("[경고] 성명은 공백 없이 한글로만 2글자 이상 6글자 이하이어야 합니다.");
            }

        } while(!isUse_name);
        // end of do_while----------------------------------------------------------

// 주민번호는 필수 입력사항이면서 주민번호 조건에 맞을때까지 반복

        boolean isUse_jubun;
        do {
          isUse_jubun = true;
          System.out.print("4. 주민번호 : ");
          jubun = sc.nextLine();

          if( !Myutil.isCheckJubun(jubun) ) {
            System.out.println("[경고] 올바른 주민번호를 입력해주세요. \n");
            isUse_jubun = false;
          }

        } while(!isUse_jubun);
        // end of do_while-----------------------------------------------------------
        Gujikja gu = new Gujikja();
        gu.userid = userid;
        gu.passwd = passwd;
        gu.name = name;
        gu.jubun = jubun;

        gu_arr[Gujikja.count++] = gu;

        System.out.println(">> 구직자 회원가입 성공 <<\n");

    } // end of if(Gujikja.count < gu_arr.length)-----------------------------------
    else {
// 지금까지 생성된 구직자 회원수가 gu_arr.length(==>정원) 와 같거나 큰 경우에는 신규회원을 받아들이면 안된다.

      System.out.println(">> 정원 "+ gu_arr.length + "명이 꽉차서 구직자 회원가입이 불가합니다. <<\n");

    }
  } // end of void register(Scanner sc, Gujikja[] gu_arr)----------------------------------------------------------------


// == 구직자 모두보기 메소드 == //
void view_all_info(Gujikja[] gu_arr) {
/*
  ------------------------------------------------------------------------------
  아이디	    비밀번호       성명      생년월일      성별    현재나이(만)        가입일자
  ------------------------------------------------------------------------------
  eomjh   qWe******		엄정화	961020		여성		 27	     2024-01-31 10:30:40
  leess   abC*******	이순신	960120		남성		 28		 2024-01-31 10:30:40
  chaew	  aSd******		차은우	010620		남성		 22		 2024-01-31 10:30:40	
  ------------------------------------------------------------------------------
*/
		
  if(Gujikja.count == 0) {
   	 System.out.println(">> 구직자로 가입된 회원이 존재하지 않습니다. <<\n");
  }
  else {
    	title();
    	StringBuilder sb = new StringBuilder();

	for(int i=0; i<Gujikja.count; i++) {
		sb.append(gu_arr[i].getinfo()+"\n");
	} // end of for-------------------------------------------------

	System.out.println(sb.toString());
  }

} end of void view_all_info(Gujikja[] gu_arr)----------------------------------------------------------------

void title() {
	System.out.println("-".repeat(75) + "\n"
			+ "아이디\t비밀번호\t\t성명\t생년월일\t성별\t현재나이(만\t)가입일자 \n"
			+ "-".repeat(75));
} // end of void title()-------------------------------------------------


// == 검색하기 메뉴를 보여주는 메소드 생성 == //

void search_menu(Scanner sc, Gujikja[] gu_arr) {

	String str_menuno = "";
	do {


	} while(!"4".equals(str_menuno));

} // end of void search_menu(Scanner sc, Gujikja[] gu_arr)-------------------------------------------------















}
