## ▶ Main_calculator

* 사칙연산 계산

* 나누기 할 때 0으로 나눌 수 없고, 실수가 나오게 함
  
```java
package my.day04.d.calculator;

import java.util.Scanner;

public class Main_calculator {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		
		String input_str = "";
		
		try {			
			System.out.print("◈ 첫 번째 정수 입력 => ");
			input_str = sc.nextLine();
			int num1 = Integer.parseInt(input_str);      // 문자열을 정수로 형변환 시킨다.
														 // 10
														 // 3000000000
														 // 튤립
				
			System.out.print("◈ 두 번째 정수 입력 => ");
			input_str = sc.nextLine();
			int num2 = Integer.parseInt(input_str);      // 문자열을 정수로 형변환 시킨다.
			 											 // 4
														 // 5000000000
														 // 해바라기
			
			System.out.print("◈ 사칙연산을 선택하세요(+ - * /) => ");   // + - * /
																 // 안녕, #, 숫자 등..			
			String operator = sc.nextLine();	
			String result = "";
			double calc_result = 0;
			
			if("+".equals(operator)) {
				 calc_result = num1 + num2;
			}
			else if("-".equals(operator)) {
				 calc_result = num1 - num2;
			}
			else if("*".equals(operator)) {
				 calc_result = num1 * num2;
			}	
			else if("/".equals(operator)) {
				 calc_result = (double)num1 / num2;
			}
			else {
				// 사칙연산 선택 시 + - * / 를 제외한 다른것을 입력한 경우
				System.out.println("[경고] 사칙연산 선택은 + - * / 만 입력하세요.");
				sc.close();
				return; // 종료
			}
			
			if("/".equals(operator)) {
				
				if(num1%num2 == 0) {
					result = num1 + operator + num2 + " = " + (int)calc_result;
					 // 10 / 5 = 2
				}
				else {
				result = num1 + operator + num2 + " = " + calc_result;
				// 10/4 = 2.5
				}		
			}
			else { // + - * 인 경우
				result = num1 + operator + num2 + " = " + (int)calc_result;
			}
			
						
			System.out.println(result);
			/*
			   10 + 4 = 14
			   10 - 4 = 6
			   10 * 4 = 40
			   10 / 4 = 2.5  --> 실수가 나오게 하고 싶음.
			*/
				
			
		} catch(NumberFormatException e) {
			System.out.println("\n>> 입력하신 "+input_str+"은(는) 올바른 데이터가 아닙니다. <<");
			
		} catch(ArithmeticException e) {
			System.out.println(">>> 0 으로 나눌 수 없습니다. <<<");	
		}
	
		sc.close();
		
	} // end of public static void main(String[] args)-----------------

}

