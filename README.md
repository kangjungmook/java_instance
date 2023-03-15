<h2> 자바 객체지향 프로그래밍 - 인스턴스화 </h1>

<h3>클래스란</h3>

* 객체를 만들기 위한 설계도
* 변수와 메서드의 집합
* class명과 파일명이 반드시 같아야 함

<h3>인스턴스란</h3>

* 객체에 포함된 개념 
* 실체화된 인스턴스는 메모리가 할당됨
* 인스턴스화는 객체의 특성/속성을 정의하여 실체로 만들어주는 것.

<h3>1단계</h3>

```java
class Accounting{
    public static double valueOfSuppyl;
    public static double vatRate = 0.1;
    public static double getVAT(){
        return valueOfSuppyl * vatRate;
    }
    public static double getTotal(){
        return valueOfSuppyl  + getVAT();
    }
}
public class AccountingApp {
    public static void main(String[] args) {
        Accounting.valueOfSuppyl = 10000.0;
        System.out.println("Value of supply :" + Accounting.valueOfSuppyl);
        Accounting.valueOfSuppyl = 20000.0;
        System.out.println("Value of supply :" + Accounting.valueOfSuppyl);

        Accounting.valueOfSuppyl = 10000.0;
        System.out.println("VAR  :" + Accounting.getVAT());
        Accounting.valueOfSuppyl = 20000.0;
        System.out.println("VAR  :" + Accounting.getVAT());

        Accounting.valueOfSuppyl = 10000.0;
        System.out.println("Total  :" + Accounting.getTotal());
        Accounting.valueOfSuppyl = 20000.0;
        System.out.println("Total  :" + Accounting.getTotal());
    }
}

```
<h3>2단계</h3>

```java
class Accounting2 {
    public double valueOfSuppyl;
    public static double vatRate = 0.1;
    public double getVAT(){
        return valueOfSuppyl * vatRate;
    }
    public double getTotal(){
        return valueOfSuppyl + getVAT();
    }
}
public class AccountingApp2 {
    public static void main(String[] args) {
        Accounting2 a1 = new Accounting2();
        a1.valueOfSuppyl = 10000.0;

        Accounting2 a2 = new Accounting2();
        a2.valueOfSuppyl = 10000.0;
        System.out.println("Value of supply :" + a1.valueOfSuppyl);
        System.out.println("Value of supply :" + a2.valueOfSuppyl);

        System.out.println("VAR  :" + a1.getVAT());
        System.out.println("VAR  :" + a2.getVAT());

        System.out.println("Total  :" + a1.getTotal());
        System.out.println("Total  :" + a2.getTotal());
    }
}
```
<h3>3단계</h3>

```java
class Accounting3 {
    public double valueOfSuppyl;
    public static double vatRate = 0.1;
    public Accounting3(double valueOfSuppyl){
        this.valueOfSuppyl = valueOfSuppyl;
    }
    public double getVAT() {
        return valueOfSuppyl * vatRate;
    }
    public double getTotal() {
        return valueOfSuppyl + getVAT();
    }
}

public class AccountingApp3 {
    public static void main(String[] args) {
        Accounting3 a1 = new Accounting3(10000.0);

        Accounting3 a2 = new Accounting3(20000.0);

        System.out.println("Value of supply :" + a1.valueOfSuppyl);
        System.out.println("Value of supply :" + a2.valueOfSuppyl);

        System.out.println("VAR  :" + a1.getVAT());
        System.out.println("VAR  :" + a2.getVAT());

        System.out.println("Total  :" + a1.getTotal());
        System.out.println("Total  :" + a2.getTotal());
    }
}
```
