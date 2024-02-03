## ▶ My.Util

* static 메소드를 생성한다.

```java
package my.util;

import java.text.SimpleDateFormat;
import java.util.Date;

public class MyUtil {


// === 현재시각을 출력해주는 static 메소드를 생성한다. === //

// public void current_time_print()   -> instance
public static void current_time_print() {
		
	Date now = new Date(); // 현재시각
		
	SimpleDateFormat sdfmt = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");  // 연월일, 시분초 String 타입으로 나오게 함.
		
	System.out.println("== 현재시각 : " + sdfmt.format(now));
		
} // end of public static void current_time_print()------------------------------------------------------------------------


// === certification key 를 만들어주는 static 메소드를 생성한다. === //

public static String certification_key() {

	Random rnd = new Random();	// 랜덤한 정수

	String certification_key = "";

	for(int i=0; i<7; i++) {
		if(i<3) {
			char ch = (char)(rnd.nextInt('z'-'a'+1) + 'a');
			certification_key += ch;
		}
		else {
			int n = (int)(rnd.nextInt (9-0+1) + 0);
			certification_key += n;
		} // end of if_else---------------------------

		return certification_key;

	} // end of for--------------------------------------------------------

} // end of public static String certification_key()---------------------------------------------------------------------------------


// === 입력받은 문자열에서 공백을 제거해주는 메소드를 생성한다. === //

public static String space_delete(String input_str) {

	String result = null;

	if(input_str != null) {
		result = "";	// null 이 없게 초기화시킨 후 진행
		for(int i=0; i<input_str.length(); i++) {
			char ch = input_str.charAt(i);
			if(ch != ' ') {
				result += ch;
			}
		} // end of for---------------------------
	}
	
	return result;

} // end of public static String space_delete(String input_str)-----------------------------------------------------------------------


// === 비밀번호가 규칙에 맞는지 틀리는지 알려주는 static 메소드 생성하기 === //

/*
  비밀번호 규칙
  1. 길이는 8글자 이상 15글자 이하
  2. 비밀번호는 영문 대문자, 영문 소문자, 숫자, 특수기호가 혼합	
  3. 규칙에 맞으면 true 리턴, 아니면 false 리턴
*/

public static boolean isCheckPasswd(String passwd) {

	if(passwd == null)
		return false;

	int length = passwd.length();
	if(length < 8 || length > 15) {
		return false;
	}
	
	boolean flag_upper = false;   // 영문 대문자 표식을 위한 용도
	boolean flag_lower = false;   // 영문 소문자 표식을 위한 용도
	boolean flag_number = false;  // 숫자 표식을 위한 용도
	boolean flag_special = false; // 특수문자 표식을 위한 용도

	for(int i=0; i<length; i++) {
		char ch = passwd.charAt(i);
		if('가' <= ch && ch <= '힣') {
			return false;
		}

		if(Character.isUpperCase(ch))
			flag_upper = true;
		else if(Character.isLowerCase(ch))
			flag_lower = true;
		else if(Character.isDigit(ch))
			flag_number = true;
		else
			flag_special = true;

	} // end of for--------------------------------------

	return flag_upper && flag_lower && flag_number && flag_special;

} // end of public static boolean isCheckPasswd(String passwd)-----------------------------------------------------------------------









}

