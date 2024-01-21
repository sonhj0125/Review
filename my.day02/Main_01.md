## ▶ Main_01

* 멤버변수와 local(지역)변수의 차이점

* 멤버변수 : instance 변수와 static 변수를 합친 것을 멤버변수라고 부른다.
  
* 클래스는 필요한 부품의 설계도. 클래스는 필드(속성값)와 메소드(행위)로 이루어져 있다.
  
  -> 필요한 속성 및 기능만 뽑아내는 것 : 추상화   


### << ★★★ 필수 암기 ★★★ >>

```	   
멤버변수 ==> instance 변수와 static 변수를 합친 것

즉, instance 변수와 static 변수는 초기화를 하지 않더라도 자동적으로 초기화됨.

정수형인 데이터타입(byte, short, int, long) : 0

실수형인 데이터타입(float, double) : 0.0

문자형인 데이터타입(char) : ' '(공백)

String 을 포함한 클래스 타입은 null 로 초기화 된다.

※ 초기화란? 변수에 어떤 값을 부여하는 것
```

```java
package my.day02;

   public class Main_01 {
	

// instance 변수

	 String id;
// String 은 문자열 타입

	 String pwd;
	 String name;

// String email = "몰라"; 초기화한 것.
// 변수에 값을 넣어준 것 = 초기화
  	 String email;

// int age = 25;                   // int 는 정수타입
	 int age;

// double height = 186.7;          // double 은 실수타입
	 double height;

// char grade = 'A';               // char 은 문자형 타입(글자 1개)
	 char grade;
	
    	 void info_print() {
		
// 지역변수(local variable)는 반드시 초기화(== 변수에 어떤 값을 부여하는 것)를 꼭 해주어야 한다.***
// 지역변수는 { } 내에서만 사용되는 것으로 { } 을 벗어나는 순간, 지역변수는 자동적으로 메모리(RAM)에서 삭제되어진다.***
		
		int hope_money = 5000;
// int hope_money;  : 초기화 하지 않을 경우, 오류
		
		String address = "서울시 마포구";
// 지역변수는 반드시 초기화!
// String address = null; 이거는 초기화가 되어진 것! 값이 없어서 null 뜨는 것과 다른 것
		
		System.out.println("=== 회원정보 1 ===\n" +
	                       "1. 아이디 : " + id + "\n" +
			       "2. 비밀번호 : " + pwd + "\n" +
	                       "3. 성명 : " + name + "\n" +
			       "4. 이메일 : " + email + "\n" +
	                       "5. 나이 : " + age + "\n" +
			       "6. 신장 : " + height +"\n" + 
	                       "7. 등급 : " + grade + "\n" +
			       "8. 희망급여 : " + hope_money + "\n" +
	                       "9. 주소 : " + address + "\n");
		
		/* 
		   문자열과 문자열 사이의 + 는 문자열 결합을 뜻하는 것이고,
		   숫자와 숫자 사이의 + 는 숫자 더하기(+)를 뜻하는 것이고,
		   문자열과 숫자 사이의 + 는 문자열 결합을 뜻함.
		*/
		
	}

	void info_view() {
		
		int hope_money = 8000;		
		String address = "경기도 군포시";
		
		System.out.println("=== 회원정보 2 ===\n" +
	                       "1. 아이디 : " + id + "\n" +
			       "2. 비밀번호 : " + pwd + "\n" +
	                       "3. 성명 : " + name + "\n" +
			       "4. 이메일 : " + email + "\n" +
	                       "5. 나이 : " + age + "\n" +
			       "6. 신장 : " + height +"\n" + 
	                       "7. 등급 : " + grade + "\n" +
			       "8. 희망급여 : " + hope_money + "\n" +
	                       "9. 주소 : " + address + "\n");
		
	}
	

	public static void main(String[] args) {
		
		Main_01 ma1 = new Main_01(); // 인스턴스화(== 객체생성)
		
		ma1.id = "leess";
		ma1.pwd = "qwer1234";
		ma1.name = "이순신";
		
		ma1.info_print();
		ma1.info_view();
		
		/*
		    === 회원정보 ===
		    1. 아이디 : leess
		    2. 비밀번호 : qwer1234
		    3. 성명 : 이순신
		*/

	}

}
