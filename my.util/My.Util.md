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














}

