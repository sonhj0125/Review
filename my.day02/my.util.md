## ▶ my.util

* 현재시각을 출력해주는 static 메소드를 생성
  
```java
package my.util;

import java.text.SimpleDateFormat;
import java.util.Date;

public class MyUtil {

// public void current_time_print()   -> instance

	public static void current_time_print() {
		
		Date now = new Date();
// 현재시각
		
		SimpleDateFormat sdfmt = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
// 연월일, 시분초 String 타입으로 나오게 함.
		
		System.out.println("== 현재시각 : " + sdfmt.format(now));
		
	}

}
