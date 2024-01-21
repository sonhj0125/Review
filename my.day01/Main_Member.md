## ▶ Main_Member

* 콘솔프로그램의 실행은 main() 메소드에서 실행한다.
  
```java
package my.day01;

public class Member_main {
	
	public static void main(String[] args) {
		
		System.out.println("1. : " + new Member());
		
		System.out.println("2. : " + new Member());
		
// 1명의 새로운 회원이 필요

		Member lssMbr = new Member();

// Member 클래스파일을 읽어다가 메모리에 로딩
// Member 클래스 인스턴스(== 객체)화		
// Memer_main 클래스와 Member 클래스는 동일한 패키지에 저장된 클래스이므로 import 를 하지 않더라도 사용 가능하다.
		
// 단어와 단어 사이를 연결지을 때, 대소문자로 구분짓는 것을 "카멜기법" 이라고 부른다.
// 단어와 단어 사이를 연결지을 때, _로 구분짓는 것을 "스네이크기법" 이라고 부른다.

		System.out.println(lssMbr);

// my.day01.Member@73a28541
// 패키지명.클래스명@메모리(RAM)상에 올라온 주소값
// lssMbr 를 사용하여 my.day01.Member@73a28541 을 제어
// 그래서 lssMbr 은 메모리 참조변수
		
// 또, 1명의 새로운 회원이 필요하다.

		Member eom_mbr = new Member();
		
		System.out.println(eom_mbr);

// my.day01.Member@6f75e721
// 패키지명.클래스명@메모리(RAM)상에 올라온 주소값
// eom_mbr 를 사용하여 my.day01.Member@6f75e721 을 제어
// 그래서 eom_mbr 은 메모리 참조변수
		
		System.out.println("\n-------------------------------------\n");
		
		lssMbr.id = "leess";
// = 은 같다가 아니라 대입해준다라는 말이다.
		lssMbr.pwd = "abcd";
		lssMbr.name = "이순신";
		lssMbr.email = "leess@naver.com";
// lssMbr.school = "대졸"; -- school 은 Member 클래스에서 존재하지 않는 필드이므로 불가함.
		
// lssMbr.address = "서울시 강남구"; 이렇게 사용해도 되지만, static 변수는 아래와 같이 클래스명.변수명으로 사용할 것을 권장함.

		Member.address = "서울시 강남구";

// Member 클래스에 주어진 모든 인스턴스는 공유한다.
		
		System.out.println("== lssMbr 이라는 인스턴스(객체)에 저장된 필드 값 출력하기 1번째 ==");
		System.out.println("1. 아이디 : " + lssMbr.id + "\n" + 
		                   "2. 비밀번호 : " + lssMbr.pwd + "\n" +  
				   "3. 성명 : " + lssMbr.name + "\n" +
		                   "4. 이메일 : " + lssMbr.email + "\n" +
//				   "5. 주소(비추) : " + lssMbr.address + "\n" +
		                   "5. 주소(권장) : " + Member.address + "\n");
		
		
        System.out.println("\n-------------------------------------\n");
		
        eom_mbr.id = "eomjh";
        eom_mbr.pwd = "qwer1234";
        eom_mbr.name = "엄정화";
        eom_mbr.email = "eomjh@gmail.com";
	 //   eom_mbr.school = "대학원졸"; -- school 은 Member 클래스에서 존재하지 않는 필드이므로 불가함.
		
		System.out.println("== eom_mbr 이라는 인스턴스(객체)에 저장된 필드 값 출력하기 1번째 ==");
		System.out.println("1. 아이디 : " + eom_mbr.id + "\n" + 
		                   "2. 비밀번호 : " + eom_mbr.pwd + "\n" +  
				   "3. 성명 : " + eom_mbr.name + "\n" +
		                   "4. 이메일 : " + eom_mbr.email + "\n" +
//			           "5. 주소(비추) : " + eom_mbr.address + "\n" +
				   "5. 주소(권장) : " + Member.address + "\n");
		
		System.out.println("\n============================================\n");
		
		System.out.println(">> lssMbr 이라는 인스턴스(객체)에 저장된 필드 값 출력하기 2번째 <<");
		lssMbr.print_info();
		
		
		System.out.println(">> eom_mbr 이라는 인스턴스(객체)에 저장된 필드 값 출력하기 2번째 <<");
		eom_mbr.print_info();

	}

}
