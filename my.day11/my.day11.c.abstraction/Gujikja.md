## ▶ Gujikja

### 객체지향 프로그래밍(Object Oriented Programming)

1. 객체지향(중심) 프로그래밍(OOP)

  * field(= attribute, property, 속성) 와 method(= operation, function, 기능, 행위) 로 구성된 클래스를 통해 객체(= instance, 인스턴스)를 만들고,
    데이터 처리와 같은 상호작용을 만들어진 객체를 가지고 프로그래밍화 하는 것

  * 예
```
   쇼핑몰 프로그램에 있어서 어떤 회원이 어떤 제품을 주문하는것을 프로그래밍 하려고 한다.

   주문이라는 데이터 처리를 위해서는 어떤 회원이 어떤 제품을 언제 몇 개를 주문했다라는 정보를 담아야 한다.

   이것을 위해서 "주문" 이라는 클래스를 만드는데 이 "주문" 클래스의 field 로 "회원" 클래스와 "제품" 클래스가 들어가게 된다.

   또한 "주문" 클래스의 method 로 주문결과를 화면에 보여주는 기능이 들어가야 할 것이다.

   이와같이 "회원" 클래스, "제품" 클래스, "주문" 클래스를 통해 객체를 만들고 객체들간의 상호작용을 논리적으로 프로그래밍 하는것
```
2. OOP 의 4가지 특징 == ★★★ 필수암기
   
   * 상속성(Inheritance) : 클래스의 재사용과 소스 코드의 중복 제거를 목적으로 하는 기술
   * 추상화(Abstraction) : 프로그램이 필요로 하는 실제 데이터들을 모델링 하는 기술
   * 캡슐화(EnCapsulation == 은닉화) : 객체지향의 가장 중요한 데이터 보호 기술
   * 다형성(Polymorphism) : 상속을 이용하여 여러 클래스 타입을 하나의 클래스 타입으로 다루는 기술
```
 구인구직 어플리케이션 프로그래밍 제작시 
 필요한 요소(부품)가 무엇이 있는지 생각해보자.
 아주 다양하고, 많은 요소들이 필요할 것이다.

 예를 들어,
 구직자, 구인회사, 채용.... 등등등 많이 있다.
 이러한 요소(부품)들이 바로 객체인데 이 객체를 만드는 설계도면이 클래스이다.

 위와(구인구직 어플리케이션 프로그래밍 제작) 같이 현실세계에 존재하는
 다양한 객체들을 각각 하나하나 추상화 시켜서 클래스로 옮기는 것을
 객체지향 프로그래밍(OOP)이라고 한다.
```  

3. 추상화(abstraction)

   * 일반적인 의미의 추상화란 어떤 물체(object)에서 주된 특징을 부각시켜 표현하고, 나머지 부분은 과감하게 생략하는 것
     
   * 추상화의 반대는 아주 세세한 것까지 전부 다 묘사하는 것을 말하는데, 이것을 정밀화라고 말한다.
  
   * 객체지향 프로그래밍(OOP)에서 사용되는 추상화도 이와 유사.
  
   * 어떤 하나의 물체를 대표하는 속성(명사, 멤버변수)과 기능(동사, 메소드)을 추출해내는 것을 OOP에서 "추상화"라고 한다.
  
```
구인구직 어플리케이션 프로그래밍 제작시
필요한 부품(요소)중 하나인 "구직자" 에 대해서 알아보자.
"구직자" 가 가지고 있는 속성(명사, 멤버변수)과 행동양식(기능, 동사, 메소드)을 뽑아보자.
```

1) 속성(property, attribute, field)은 멤버변수
   
2) 행동양식(기능)은 메소드

<Gujikja(클래스)>
* 속성(property, attribute, field) : 아이디, 암호, 성명, 연락처, 이메일, 주소, 학력, 희망구직직종, 희망연봉.....  
* 행동양식(기능, 메소드) : 구직자로 접속(로그인)할수 있는 기능, 구직자정보를 조회해주는 기능, 구직자정보를 변경해주는 기능, .......  

```java

package my.day11.c.abstraction;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class Gujikja {

 // == fleid 생성 == //
String userid; // 아이디
String passwd; // 비밀번호
String name;   // 성명
String jubun;  // 주민번호, 앞자리 6자리 + 성별을 나타내는 1자리

String register_day;  // 가입일자(자동적으로 생성됨)

static int count;    // Gujikja 객체(인스턴스)의 개수를 알아오려는 용도, 다같이 공유


// 기본생성자
public Gujikja() {
   Date now = new Date(); // 현재시각
   SimpleDateFormat df = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");

   register_day = df.format(now);
   // 2024-01-30 15:12:10

} // end of public Gujikja()----------------------------------------------------


// == 구직자의 만나이를 알려주는 메소드 생성하기 == //
int getAge() {
 // == 만나이 구하기 == //
 int age = 0;

// 구직자의 올해 생일이 현재날짜와 같거나 보다 이전(과거)이라면
// 나이 = 현재년도 = 구직자의 태어난년도

// 구직자의 올해 생일이 현재날짜보다 이후(미래)이라면
// 나이 = 현재년도 = 구직자의 태어난년도 - 1

 Date now = new Date();
 SimpleDateFormat sdfmt = new SimpleDateFormat("yyyyMMdd");
 String str_now = sdfmt.format(now);

// 구직자의 올해 생일
 String str_now_birthday = str_now.substring(0, 4) + jubun.substring(2, 6);
// "2024" + "1020" ==> "20241020"

// 현재년도
 int now_year = Integer.parseInt(str_now.substring(0, 4));

// 구직자의 태어난년도
 int centry = ( "1".equals(jubun.substring(jubun.length()-1)) || "2".equals(jubun.substring(jubun.length()-1)) )?1900:2000;
 int birth_year = centry + Integer.parseInt(jubun.substring(0,2));

 try {
  now = sdfmt.parse(str_now);                         // 오늘의 자정, 오늘의 0시 0분 0초
  Date now_birthday = sdfmt.parse(str_now_birthday);  // 올해 생일의 자정, 올해 생일의 0시 0분 0초
  if(now_birthday.compareTo(now) > 0) {  // 구직자의 올해 생일이 현재일 보다 미래인 경우
   age = now_year - birth_year -1;
  }
  else {  // 구직자의 올해 생일이 현재일 이거나 과거인 경우
   age = now_year - birth_year;
  }
 } catch(ParseException e) {

 } // end of try_catch------------------------------------------------

 return age;

} // end of int getAge()--------------------------------------------------------------


// == 성별을 구해주는 메소드 == //
 String getGender() {

  if( "1".equals(jubun.substring(jubun.length() - 1)) ||	"3".equals(jubun.substring(jubun.length() - 1)) ) {
				return "남";	
			}
			else {
				return "여";
			}

 } // end of String getGender()--------------------------------------


// === 구직자의 정보를 한줄로 출력해주는 메소드 생성하기 === //

String getinfo() {

	StringBuilder sb = new StringBuilder();

	sb.append(userid + "\t");

	sb.append(passwd.substring(0, 3) + "*".repeat(passwd.length() - 3) + "\t");

	sb.append(name + "\t");

	sb.append(jubun.substring(0, 6) + "\t");	// (0, 6) 또는 (0, jubun.length() - 1)

	sb.append(getGender() + "\t");

	sb.append(getAgd() + "\t");

	sb.append("\t" + register_day);

	return sb.toString();	// 쌓인 정보들을 String 타입으로 변환

} // end of String getinfo()--------------------------------------

}
