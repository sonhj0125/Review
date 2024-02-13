## ▶ ArrayList_main_1

=== Array(배열) 와 Collection(자료구조)의 차이점 ===     

1. Array(배열)은 크기가 한정 되어져 있지만,  Collection(구조체)은 크기가 무한정이다.
    
2. Array(배열)은 배열에 선언되어진 동일한 타입의 데이터만 입력가능하지만, Collection(구조체)은 입력되어지는 데이터가 객체(Object)이기만 하면 어떤것이든지 입력가능하다. 


=== 배열(Array)과 자료구조(Collection)의 차이점 ===

1. 배열(Array)은 오로지 동일한 데이터 타입만 들어가는 저장소. 배열(Array)은 그 크기가 한번 정해지면 크기를 변경할 수 없다.
  
2. 자료구조(Collection)은 동일한 타입의 객체가 아니더라도 객체타입이기만 하면 모두 들어가는 저장소. 자료구조(Collection)은 저장되는 크기가 자동적으로 늘어난다.
 
* 웹에서 가장 많이 사용하는 대표적인 Collection 타입은 List 계열과 Map 계열

```
--------------------------------------------------------------------------------
              Web에서 주로 사용하는 클래스    게임프로그램밍에서 주로 사용하는 클래스
Interface       (Single Thread 방식)              (Multi Thread 방식)
--------------------------------------------------------------------------------         
List 계열    --      ArrayList      ,                 Vector
Map  계열    --      HashMap        ,               Hashtable 
```

 * ArrayList 및 HashMap 은 Multi Thread를 지원안해주므로 가볍다.
   
 * Vector 및 Hashtable 이 Multi Thread를 지원해주므로 무겁다.

 * Multi Thread를 지원해주는냐 안해주느냐만 차이가 있을 뿐 그 나머지 기능은 동일

```java
package my.day18.a.collection;

import java.util.ArrayList;
import java.util.List;

public class ArrayList_main_1 {

	public static void main(String[] args) {
		
		List my_list = new ArrayList();
		System.out.println("my_list 의 크기 : " + my_list.size());		// .length == .size
		// my_list 의 크기 : 0
		
		my_list.add(new String("이순신"));
		my_list.add("엄정화");				// AutoBoxing
		
		System.out.println("my_list 의 크기 : " + my_list.size());		// .length == .size
		// my_list 의 크기 : 2
		
		my_list.add(new Integer(98));
		my_list.add(Integer.valueOf(100));
		my_list.add(80);					// AutoBoxing, int ---> Integer 로 autoboxing 해준다.
		// my_list 의 크기 : 4
		
		
		my_list.add(new Double(1234.5));
		my_list.add(Double.valueOf(2345.6));
		my_list.add(4345.7);				// double --> Double 로 autoboxing 해준다.
		
		
//		my_list.add(new Member());
        // my_list 의 크기 : 9
		
		for(int i=0; i<91; i++) {
//		my_list.add(new Member());
		} // end of for----------------------------------------------------
		
		System.out.println("my_list 의 크기 : " + my_list.size());		// .length == .size
		// my_list 의 크기 : 100
		
		
		System.out.println("\n===========================================================\n");
		
		for(int i=0; i<9; i++) {
			System.out.println(my_list.get(i));
		} // end of for-----------------------------------------------------
		/*
		   이순신
		   엄정화
		   98
		   100
		   80
		   1234.5
		   2345.6
		   4345.7
		   my.day18.a.collection.Member@5f5a92bb		  
		*/
		
		
		my_list.add(999);
		
		System.out.println("\n=== my_list 에 저장되어진 데이터 중 정수데이터만 출력하기 ===\n");
		
		for(int i=0; i<my_list.size(); i++) {
			if(my_list.get(i) instanceof Integer) {
				System.out.println(my_list.get(i));
			}
		} // end of for-----------------------------------------------------
		
		/*
		   98 
		   100 
		   80 
		   999  
		*/
