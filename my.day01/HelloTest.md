## Hello_Test

* 어떤 프로그램(예 : 쇼핑몰 프로그램)을 생성하려면, 설게 도면이 필요
* 자바(Java)라는 개발언어로 만드는 설계도면을 **"클래스"** 라고 부른다.

### === CLASS(클래스)의 구조 ===

#### 1. 패키지 선언문
   
   * 패키지란, 클래스가 저장되어진 디렉토리(폴더) 경로이다.

   * package 패키지명;  ==> 이때, 패키지명은 반드시 소문자로 시작

   * 예> package my.day01;


#### 2. import 문   

   * import java.lang.--;  ==>  '--'의 뜻은 모든 것을 의미
   
   * 즉, java.lang 패키지 속에 있는 모든 클래스를 사용. 기본적으로 import java.lang.*; 은 생략


#### 3. 클래스 선언문

   * 클래스란, 설계도면을 뜻함. 클래스 명의 첫글자는 대문자
   
   * 저장 시, 파일명은 클래스명과 동일해야 하며, 확장자는 .java   
   
   * class body(클래스 본체)는 { 로 시작해 }로 끝남.
  

#### 4. compile(컴파일) 하기

  * 고급언어를 저급언어로 바꾸는 과정
  
  * 고급언어란? 사람(개발자)이 알아볼 수 있는 언어
  * 저급언어란? 기계(컴퓨터)가 알아 들을 수 있는 언어
  * Binary Digit(== Bit, 2진수 0,1)
  
  * javac 를 사용하여 컴파일을 하면 .java 파일이 .class 로 생성됨
  * .java 파일은 고급언어로 구성된 자바소스 파일
  * .class 파일은 기계(컴퓨터)가 알아 들을 수 있는 저급언어이며,
    실행되어지는 파일.
*/   
      
// 1줄 주석문   
   
/*   
   여러줄   
   주석문   
*/

/**   
   문서화 주석   
   ==> 어떤 클래스나 메소드 생성 시, javadoc 를 이용해서 API 문서를 만들 때 사용.   
*/

.java
package my.day01.copy;

import java.util.Date;

public class HelloTest {

   public static void main(String[] args) {
      
      System.out.println("Hello, world");
      
// System.out 은 모니터
      
/*
   System.out.println("출력하고자 하는 문자열"); 은
   모니터에 "출력하고자 하는 문자열" 을 출력      
*/
      
      System.out.print("안녕하세요.\n");
      
// System.out.println("\n"); 은 줄바꿈. Enter 의 역할      
      
      System.out.println("반갑습니다");
      
// println = \n
      
      System.out.println("자바 첫날 입니다.\n");

// println 과 \n 은 줄바꾸기 2번(\n\n 과 동일)
      
      System.out.println("조금 뒤 자기소개를 할 예정입니다.");
      
      Date today_now = new Date();
      System.out.println("컴퓨터에서 알려주는 현재시각 : " + today_now);
      
// 생성자, import 필요. new Date();은 컴퓨터의 현재시각을 알아오는 것.      
   }

}
