## ▶ Main_02

* static 메소드에 대해서 알아본다.
* my.util 파일 참조
  
```java
package my.day02;

import my.util.MyUtil;
// import my.util.MyUtil;

public class Main_02 {

  public static void main(String[] args) {
		
		System.out.println(">> 여기는 Main_02 클래스 입니다. <<");
		
// 현재시각을 출력
		MyUtil.current_time_print();
// static 으로 고정시켰을 경우 클래스명.찍으면 됨
		
// MyUtil util = new MyUtil();
// instance 인 경우, 제어할 수 있게 만들어주고, 주소 찾아서 불러와야함.
// util.current_time_print();

		/*
		   >> 여기는 Main_02 클래스 입니다. <<
           == 현재시각 : 2024-01-17 12:16:03
		*/

	}

}
