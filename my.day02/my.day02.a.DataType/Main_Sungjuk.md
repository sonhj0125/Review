## ▶ Main_Sungjuk

```java
package my.day02.a.dataType;

public class Main_Sungjuk {

	public static void main(String[] args) {
		
		float ft1 = 12.345f;
		float ft2 = 12.345678901234f;
		          // 12.345679 반올림됨
		
		System.out.println("ft1 : " + ft1);
		System.out.println("ft2 : " + ft2);
		
		Sungjuk lss_sungjuk = new Sungjuk();
		lss_sungjuk.hakbun = "091234";
		lss_sungjuk.name = "이순신";
		lss_sungjuk.kor = 70;
		lss_sungjuk.eng = 96;
		lss_sungjuk.math = 100;
		
		Sungjuk eom_sungjuk = new Sungjuk();
		eom_sungjuk.hakbun = "109876";
		eom_sungjuk.name = "엄정화";
		eom_sungjuk.kor = 79;
		eom_sungjuk.eng = 58;
		eom_sungjuk.math = 95;
		
		lss_sungjuk.sungjuk_print();

/*
		   === 이순신 님의 성적 결과 ===
1. 학번 : 091234
2. 성명 : 이순신
3. 국어 : 70
4. 영어 : 96
5. 수학 : 100
6. 총점 : 266
7. 평균1 : 88
8. 평균2 : 88.66666666666667
9. 평균3 : 88.666664
10. 평균4 : 88.66666666666667
11. 평균5 : 88.666664
12. 장학금 : 3000000000
13. 학점 : B
*/
		
		eom_sungjuk.sungjuk_print();

/*
		  === 엄정화 님의 성적 결과 ===
1. 학번 : 109876
2. 성명 : 엄정화
3. 국어 : 79
4. 영어 : 58
5. 수학 : 95
6. 총점 : 232
7. 평균1 : 77
8. 평균2 : 77.33333333333333
9. 평균3 : 77.333336
10. 평균4 : 77.33333333333333
11. 평균5 : 77.333336
12. 장학금 : 3000000000
13. 학점 : C 
*/
		
		System.out.println("\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n");
		Sungjuk.boolean_print();

		System.out.println("\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n");
		Sungjuk.char_print();
								
	}

}
```
