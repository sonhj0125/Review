## ▶ Main_Gujikja

* Main 메소드는 실행을 해준다.
  
```java
package my.day11.c.abstraction;

import java.util.Scanner;

pubilc class Main_Gujikja {

	public static void main(String[] args) {

	Gujikja[] gu_arr = new Gujikja[5];

///////////////////////////////////////////////////

	Gujikja gu1 = new Gujikja();
	gu1.userid = "eomjh";
	gu1.passwd = "qWer1234$";
	gu1.name = "엄정화";
	gu1.jubun = "8610202";
	gu_arr[Gujikja.count++] = gu1;
	
	Gujikja gu2 = new Gujikja();
	gu2.userid = "leess";
	gu2.passwd = "abCd12345$";
	gu2.name = "이순신";
	gu2.jubun = "9209201";
	gu_arr[Gujikja.count++] = gu2;
	
	Gujikja gu3 = new Gujikja();
	gu3.userid = "chaew";
	gu3.passwd = "aSdf1234$";
	gu3.name = "차은우";
	gu3.jubun = "0106203";
	gu_arr[Gujikja.count++] = gu3;
	    		
///////////////////////////////////////////////////

	Scanner sc = new Scanner(System.in);
	Ctrl_gujikja ctrl = new Ctrl_gujikja();

	String str_menuno = "";

	ctrl.main_menu();
	str_menuno = sc.nextLine();

	switch (str_menuno) {
		case "1" : // 구직자 회원가입







	} // end of switch (str_menuno)------------------------------------














  } // end of public static void main(String[] args)-----------------------------------------------------------

}
