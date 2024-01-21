## ▶ Main_03

* static 메소드에 대해서 알아본다.
  
```java
package my.day02;

import my.util.MyUtil;
// import my.util.MyUtil;

public class Main_03 {

	public static void main(String[] args) {
		
		System.out.println(">> 여기는 Main_03 클래스 입니다. <<");

// 현재시각을 출력해본다.
		MyUtil.current_time_print();
// static 으로 고정시켰을 경우 클래스명.찍으면 됨
		
  // MyUtil util = new MyUtil();
  // util.current_time_print();
		
		/*
		  >> 여기는 Main_03 클래스 입니다. <<
		  == 현재시각 : 2024-01-17 12:15:05
		*/

	}

}
