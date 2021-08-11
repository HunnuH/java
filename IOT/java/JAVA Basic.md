# JAVA Basic

- 환경설정
  - `java _home` : jdk의 설치 포더 경로
  - `path` : jdk의 bin디렉터리 경로
  
- 자바실행
  - 컴파일
    - 자바언어로 작성된 명령어를 컴퓨터에서 실행하기 위해서 컴퓨터가 이해 할수있는 명령어로 변경하는 작업
  - 인터프리터
    - 컴파일러로 번역한 명령어를 한 줄씩 번역하여 자바에서 실행
    - 중간에 오류가 발생하여도 오류가 발생 하기 전까지 실행

- 자바언어로 소스 코드를 작성
  - 자바 명령어로 구성된 
  - 확장자 : `.java`
  - 소스파일은 소스파일 내부에서 선언된 클래스명과 동일한 이름으로 작성
    - 클래스명 >` Hello`
    - 파일명 > `Hello.java`
  
- 자바소스 파일을 컴파일
  - 컴파일러 : `javac.exe`
    - javac 자바소스파일명. java
      - `javac Hello.java`
  - 컴파일의 결과파일이 생성
    - cmd > dir/w 로 확인
    - 확장자 :`.class` (클래스파일, 바이트코드)
      - `Hello.class`
  
- 자바실행
  - 인터프리터 : `java.exe`
    - `java`컴파일 결과로 생성된 클래스 파일의 파일명(확장자x)
    - `java Hello`
  
- 자바플랫폼
  - 자바를 개발하고 실행할 수 있는 환경
  - `JavaSE` (java  standard edition) : 기본, 입출력, DB연동, 네트워크
  - `JavaEE` (java  enterprise edition) : 서블릿JSP(웹)
  - `JavaME` (java  mobile deition)  
  
- 자바로 개발할 수 있는 구성요소

  - `Application`	
    - `java.exe`라는 인터프리터를 이용해서 실행하는 프로그램을 `application`이라고 한다
  - `Servlet`
  - `Applet`

- 자바의 작업 단위 -클래스

  - `class` : 키워드, 자바프로그램에 미리 의미를 부여해서 등록해 놓은 이름

    ​            미리 예약된 명령어

  - 클래스명 : 임의로 정의하는 이름

    ​                   명사적 특징을 갖도록 이름 부여

    ​                   여러단어결합 가능, 단어의 첫글자는 대문자

- 기본문법

  - 기본형리터럴

  - 연산자

    - 증감연산자 : `++` , `--`

      - ```java
        // 증감연산자 test
        public class OprTest01{
        	public static void main(String[] args) {
        		int x;
        		int y;
        
        		x = 5;
        		y = x++;
        		System.out.println("x의 값=>"+x);
        		System.out.println("y의 값=>"+y);
                System.out.println("===============");
          		
        		x = 5;
        		y = ++x;
        		System.out.println("x의 값=>"+x);
        		System.out.println("y의 값=>"+y);
                System.out.println("===============");
          
        		x = 5;
        		y = x--;
        		System.out.println("x의 값=>"+x);
        		System.out.println("y의 값=>"+y);
                System.out.println("===============");
          
                x = 5;
        		y = --x;
        		System.out.println("x의 값=>"+x);
        		System.out.println("y의 값=>"+y);
                System.out.println("===============");
          
        	}
        }
        ```

    - 산술연산자 " `+`, `-`, `*`, `/`, `%`

    - 비교연산자 : `<`, `<=`,  `>`,  `>=` , `==`, `!=`

      - ```java
        // 비교연산자
        public class OprTest02 {
        	public static void main(String[] args) {
        		int num1 = 100;
        		int num2 = 200;
        		int num3 = 200;
                   
        // num의 변수가 +연산자 때문에 문자열로 변환됨 
        // +의 연산자는 더하기의 의미 이외에도 연결연산자의 기능도 수행
        // +연산자 앞에 문자열이 존재하면 뒤에 숫자열이 오더라도 문자열로 변환
        // 비교연산. 사친연산을할 수 없다.
        		System.out.println("더한결과==>"+(num1+num2));
        		System.out.println("num1>num2==>"+ (num1>num2));
        		System.out.println("num1>=num2==>"+ (num1>=num2));
        		System.out.println("num1<num2==>"+ (num1<num2));
        		System.out.println("num1<=num2==>"+ (num1<=num2));
        
        		System.out.println("num1==num3==>"+ (num1==num3));
        		System.out.println("num2==num3==>"+ (num2==num3));
        		System.out.println("num1!=num3==>"+ (num1!=num3));
        	}
        }
        ```

    - 논리연산자 : `&` , `|`, `!`, `&&`, `||`

      - ```java
        //논리연산자
        // and : &
        // or : |
        // not : !
        public class OprTest03 {
        	public static void main(String[] args) {
        		int age = 15;
        		int gender = 1;
        
        		int num1 =100;
        		int num2 = 200;
        		//&연산
        		System.out.println("=======and======");
        		//true & true
        	    System.out.println((num1<num2) & (num1>=100));
        		//true & false
        		System.out.println((num1<num2) & (num1>100));
        		//false & true
        		System.out.println((num1>num2) & (num1>=100));
        		//false & false
        		System.out.println((num1>num2) & (num1>100));
        
        		//|연산
                System.out.println("=======or=======");
        		//true | true
        	    System.out.println((num1<num2) | (num1>=100));
        		//true | false
        		System.out.println((num1<num2) | (num1>100));
        		//false | true
        		System.out.println((num1>num2) | (num1>=100));
        		//false | false
        		System.out.println((num1>num2) | (num1>100));
        
        		System.out.println(); //Enter키를 누른 것과 같은 결과
        
        		//!
        		System.out.println(!true);
                System.out.println(!false);
        	}
        }
        ```

      - ```java
        //논리연산자(short circuit) && , ||
        //        & ,  |    둘의 차이는 조건식을 모두 검사하는지 skip하는지의 차이
        public class OprTest04 {
        	public static void main(String[] args) {
                  int num1 = 120;
                  //int num2 = 
                System.out.println("start");
        		String str = null; // 현재 str에 아무것도 할당되지 않은 변수
        
         	  //System.out.println(num1>100 | str.length()>0); 오류발생
        		System.out.println(num1>100 || str.length()>0);
        // ||연산자는 or연산의 특성을 파악하고 첫 번쨰 항이 true 연산자 뒤의 항은 검사하지 않는다 
        
              //System.out.println(num1<100 & str.length()>0); 오류발생
        	    System.out.println(num1<100 && str.length()>0);
        // &&연산자는 and연산의 특성을 파악하고 첫 번쨰 항이 false이면 뒤의 항은 검사하지 않는다
        	}
        }
        ```

  - 삼황연산자, 대입연산자

    - ```java
      //삼항연산자
      public class OprTest05 {
      	public static void main(String[] args) {
      		int num1 = 90;
      	//조건?조건이 만족하는 경우 할당될 값:조건이 만족하지 않을때 할당될 값
      		System.out.println(num1>=90?"합격" : "불합격");
      		int point = num1 >=90?1000:0;
      		System.out.println(point);
      //대입연산자
      		int i = 0;
      		i = i+20;
      		System.out.println("i="+i);
      		i+=30;
      		System.out.println("i="+i);
      		i-=30;
      		System.out.println("i="+i);
      	    i*=30;
      		System.out.println("i="+i);
      		i/=30;
      		System.out.println("i="+i);
      	}
      }
      ```

- 모든 프로그래밍 언어의 공통된 특징(기본문법)

  - 문장의 종류

    - 순차형

    - 조건형

      - `if` 

        - 
          
          ```java
          [구문]
          if(조건){ 조건이 만족하는 경우 실행할 문장}
          else {조건이 만족하지 않는 경우 실행할 문장}
          ```
          

    - 순환형

  - 변수

    - 프로그램 사용중에 발생하는 데이터를 임시로 저장하기 위한 메모리의 공간

      - 변수선언 : 데이터타입 변수명;
      - 변수에 저장될 값을 설정 : 변수명 = 값;
        - 변수를 사용할때 변수의 선언과 값의 할당을 한 문장으로 처리한다 
        - 데이터타입 변수명 = 값;

    - 데이터타입

      - 기본형 : 값을 저장하는 데이터타입

        - 숫자 :  정수 -`byte(1byte)`,`short(2byte)`,`int(4byte)`,`long(8byte)`

          ​            실수 - `float`,`double`

        - 문자 :  `char`

        - 논리값 : `true/false` - boolean

      - 참조형 :  기본형 타입을 제외한 모든 형태의 타입

        ​                객체의 주소값을 저장하고 있다.

        ​                배열 `array`      클래스`class`

        ​                열거 `enum`         인터페이스`interface`       

  - API사용방법

  - 제어구문

    - 조건제어문
      - if
      - switch
    - 반복제어문
      - for
      - while
      - do~while
  - 배열
    - 일차원배열
    - 이차원배열

- 자바의 특징(oop개요)

- 자에서 제공되는 기능(API)

---

```java
/* 점수를 저장할 수 있는 변수를 선언하고 다음과 같은 추력형태로 출력되도록 작성
 90이상 pass
 90미만 fail
*/

public class IfElseTest {
	public static void main(String[] args) {
		int num = 98;
		if (num>=90) {
          System.out.println(num+"점수는 pass");
		}
         else{
			System.out.println(num+"점수는 fail");
        }
	}
}
```

```java
/*  아래의 변수를 선헌하고 다음과 같은 조건을 만족하도록 작성
   int time = 8000; 초 데이터
   [출력결과]
   시간 분 초
   로 변경하여 출력
 */

public class TimeTest{
    public static void main(String[] args) {
		int time = 8000;
		int h = time/3600;
	    int m = time%3600/60;
		int s = time%3600%60;
	
		System.out.println(h+"시간"+m+"분"+s+"초");
	}
}

```

```java
/* 
1.변수를 3개 선언
2.국어,영어,수학점수를 임의로 저장
3.출력결과를 다음과 같이 작성
[출력결과]
총점:
평균:
*/

public class ScoreExam
{     public static void main(String [] args) {
	    int K = 80;
		int E = 90;
		int M = 70;
        int tot = K + E + M;
		int avg = tot / 3;
         System.out.println("[출력결과]");
		 System.out.println("총점:"+tot);
		 System.out.print("평균:"+avg);
		       
   }
}
```

---

```java
package basic;

public class APITest {
	public static void main(String[] args) {
       System.out.println("문자열");
       int i =10;
//문자열을 처리하기 위한 기능을 사용하기 위해 string 클래스를 jvm이 인식하는  작업공간에 할당
       
/*     [형식]
 *     할당되는 클래스타입 변수명= new heap에 할당해서 사용하고 싶은 클래스명()
 *                         or new heap에 할당해서 사용하고 싶은 클래스명()
 *     java문자열을 처리하기 위해서 string클래스를 heap에 할당
 *     heap할당된 string객체를 APITest.javad의 main블럭에서 사용하기 위해 str변수를 통해 접근할수 있도록 heap의 주소를 설정  */
       String str = new String("java");
       Thread t = new Thread();
       Object o = new Object();
       
       
/*     str이 참조하는 주소를 가지고 heap에 있는 객체를 참조
 *     heap에 할당된 string객체의 length메소드를 참조       */
       str.length();//메소드호출
 	}
}
```

