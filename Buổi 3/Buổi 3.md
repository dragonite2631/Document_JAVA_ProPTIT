# MỌI THỨ ĐỀU LÀ ĐỐI TƯỢNG


# Tính Đóng Gói trong Java

## 1. Tính Đóng Gói là gì?
- **Tính đóng gói** là một trong những nguyên tắc cơ bản của Lập trình Hướng đối tượng (OOP).
- Nó đề cập đến việc đóng gói dữ liệu (các thuộc tính) và các phương thức (hàm) thao tác trên dữ liệu vào trong một đơn vị duy nhất, thường là một lớp (class).
- Tính đóng gói hạn chế truy cập trực tiếp đến các thành phần của đối tượng, giúp bảo vệ dữ liệu và kiểm soát cách thức truy cập vào nó.

## 2. Mục Đích của Tính Đóng Gói
- **Bảo vệ Dữ liệu**: Tính đóng gói giúp bảo vệ dữ liệu khỏi việc thay đổi không mong muốn hoặc độc hại.
- **Kiểm soát**: Nó cho phép định nghĩa ai có thể đọc và ghi dữ liệu.
- **Dễ Duy trì**: Bằng cách hạn chế truy cập trực tiếp, tính đóng gói giúp dễ dàng bảo trì và sửa đổi mã mà không ảnh hưởng đến các phần khác của chương trình.
- **Linh hoạt**: Cho phép thay đổi một phần mã mà không làm ảnh hưởng đến toàn bộ hệ thống bằng cách kiểm soát cách thức truy cập và thay đổi dữ liệu.

## 3. Cách Thực Hiện Tính Đóng Gói trong Java
- Tính đóng gói trong Java được thực hiện bằng cách:
  - Khai báo các trường (thuộc tính) của lớp là **private**.
  - Cung cấp các phương thức **getter và setter công khai (public)** để truy cập và cập nhật giá trị của các trường private.

## 4. Các Từ Khóa Điều Chỉnh Truy Cập trong Java
- Java cung cấp **các từ khóa điều chỉnh truy cập** để kiểm soát khả năng truy cập:
  - `public`: Thành phần có thể được truy cập từ bất kỳ lớp nào khác.
  - `private`: Thành phần chỉ có thể được truy cập trong lớp của nó.
  - `protected`: Thành phần có thể được truy cập trong cùng package và các lớp con.
  - **Mặc định (Package-private)**: Chỉ có thể truy cập trong cùng package.

## 5. Ví Dụ về Tính Đóng Gói

```java
public class Student {
    // Trường private để hạn chế truy cập trực tiếp
    private String name;
    private int age;

    // Constructor để khởi tạo đối tượng Student
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Getter cho 'name' - phương thức công khai để lấy giá trị của 'name'
    public String getName() {
        return name;
    }

    // Setter cho 'name' - phương thức công khai để đặt giá trị cho 'name'
    public void setName(String name) {
        this.name = name;
    }

    // Getter cho 'age' - phương thức công khai để lấy giá trị của 'age'
    public int getAge() {
        return age;
    }

    // Setter cho 'age' - phương thức công khai để đặt giá trị cho 'age'
    public void setAge(int age) {
        if (age > 0) { // Kiểm tra hợp lệ
            this.age = age;
        } else {
            System.out.println("Tuổi không hợp lệ");
        }
    }
}
```



# Tính Kế Thừa trong Java

Tính kế thừa (Inheritance) là một trong bốn đặc trưng chính của lập trình hướng đối tượng trong Java. Nó cho phép một lớp con (subclass) kế thừa các thuộc tính và phương thức từ một lớp cha (superclass).

## 1. Đặc điểm của Tính Kế Thừa
- **Kế thừa thuộc tính và phương thức**: Lớp con tự động có các thuộc tính và phương thức của lớp cha mà không cần khai báo lại.
- **Dễ bảo trì và mở rộng**: Các thay đổi ở lớp cha sẽ tự động áp dụng cho lớp con, giúp mã dễ bảo trì và mở rộng.
- **Khả năng tái sử dụng**: Tính kế thừa giúp tái sử dụng các đoạn mã đã có, giảm thiểu việc viết lại mã.

## 2. Constructor trong Kế Thừa
- **Constructor không được kế thừa**: Constructor của lớp cha không được kế thừa bởi lớp con. Tuy nhiên, lớp con có thể gọi constructor của lớp cha bằng từ khóa `super`.
- **Sử dụng từ khóa `super`**: Từ khóa `super` được sử dụng để gọi constructor của lớp cha trong lớp con, thường dùng để khởi tạo các thuộc tính mà lớp con không định nghĩa lại.

### Ví dụ về Constructor và `super`
```java
class Parent {
    Parent() {
        System.out.println("Constructor của lớp cha");
    }
}

class Child extends Parent {
    Child() {
        super(); // Gọi constructor của lớp cha
        System.out.println("Constructor của lớp con");
    }
}
```

## 3. Variable Hiding
- **Variable hiding (ẩn biến)** xảy ra khi lớp con khai báo biến có cùng tên với biến trong lớp cha.
- Khi gọi biến trong lớp con, biến của lớp con sẽ được ưu tiên, làm biến lớp cha bị ẩn đi.
- Để truy cập biến của lớp cha, có thể sử dụng từ khóa `super`.

### Ví dụ về Variable Hiding
```java
class Parent {
    int x = 10;
}

class Child extends Parent {
    int x = 20; // Biến x trong lớp con che khuất biến x trong lớp cha
    void printX() {
        System.out.println("x của lớp con: " + x);
        System.out.println("x của lớp cha: " + super.x);
    }
}
```

## 4. Đa Kế Thừa
- Java không hỗ trợ đa kế thừa trực tiếp (một lớp không thể kế thừa từ nhiều lớp).
- Thay vào đó, Java hỗ trợ đa kế thừa qua **Interface**, cho phép một lớp implement nhiều interface.

### Ví dụ về Đa Kế Thừa qua Interface
```java
interface A {
    void methodA();
}

interface B {
    void methodB();
}

class C implements A, B {
    public void methodA() {
        System.out.println("Method A");
    }
    public void methodB() {
        System.out.println("Method B");
    }
}
```

# Upcasting và Downcasting trong Java

## 1. Upcasting là gì?
**Upcasting** là quá trình chuyển đổi một đối tượng của lớp con (subclass) thành một đối tượng của lớp cha (superclass). Trong Java, upcasting thường được thực hiện tự động. Đây là một tính năng quan trọng của tính kế thừa trong Java, cho phép các đối tượng của lớp con có thể được xử lý như các đối tượng của lớp cha.

### Ví dụ về Upcasting
```java
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Woof Woof");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal = new Dog(); // Upcasting Dog lên Animal
        animal.sound(); // Output: Woof Woof
    }
}
```

Trong ví dụ trên, `Dog` là lớp con của `Animal`, và biến `animal` được upcast từ `Dog` sang `Animal`. Phương thức `sound()` của `Dog` vẫn được gọi do tính đa hình.

## 2. Downcasting là gì?
**Downcasting** là quá trình chuyển đổi ngược lại từ lớp cha (superclass) về lớp con (subclass). Downcasting không được thực hiện tự động trong Java và phải được thực hiện một cách tường minh (explicitly). Việc downcasting có thể gây lỗi `ClassCastException` nếu không cẩn thận.

### Ví dụ về Downcasting
```java
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Woof Woof");
    }
    
    void fetch() {
        System.out.println("Fetching...");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal = new Dog(); // Upcasting
        Dog dog = (Dog) animal;    // Downcasting
        
        dog.sound();  // Output: Woof Woof
        dog.fetch();  // Output: Fetching...
    }
}
```

Trong ví dụ trên, biến `animal` được downcast từ `Animal` về `Dog`. Khi downcast thành công, chúng ta có thể truy cập các phương thức của lớp `Dog` như `fetch()`.

## 3. Lưu ý khi sử dụng Upcasting và Downcasting
- Upcasting thường được sử dụng để tận dụng tính đa hình (polymorphism), giúp cho code linh hoạt và dễ mở rộng.
- Downcasting có thể gây lỗi tại thời điểm runtime (`ClassCastException`) nếu biến được cast không phải là instance của lớp con mong muốn.
- Để đảm bảo an toàn, nên sử dụng từ khóa `instanceof` để kiểm tra trước khi thực hiện downcast.

### Ví dụ sử dụng `instanceof`
```java
if (animal instanceof Dog) {
    Dog dog = (Dog) animal;
    dog.fetch();
} else {
    System.out.println("Không thể downcast thành Dog.");
}
```
# Class Object trong Java

Trong Java, **Object** là lớp gốc (superclass) của tất cả các lớp. Điều này có nghĩa là mọi lớp đều kế thừa trực tiếp hoặc gián tiếp từ lớp Object. Đây là một phần quan trọng của ngôn ngữ Java, vì nó cung cấp một tập hợp các phương thức cơ bản mà mọi đối tượng đều có thể sử dụng.

## Các phương thức chính trong lớp Object

Lớp Object cung cấp một số phương thức mà các lớp con có thể sử dụng và ghi đè lại để phù hợp với nhu cầu của mình. Dưới đây là các phương thức quan trọng nhất:

1. **toString()**
   - Mô tả: Phương thức này trả về chuỗi biểu diễn của đối tượng. Mặc định, nó trả về tên lớp và mã hash của đối tượng.
   - Ví dụ:
     ```java
     public class MyClass {
         @Override
         public String toString() {
             return "MyClass object";
         }
     }
     ```

2. **equals(Object obj)**
   - Mô tả: Phương thức này so sánh hai đối tượng với nhau. Theo mặc định, nó kiểm tra xem hai đối tượng có cùng tham chiếu bộ nhớ hay không.
   - Ví dụ:
     ```java
     public class MyClass {
         private int id;
         public MyClass(int id) {
             this.id = id;
         }
         
         @Override
         public boolean equals(Object obj) {
             if (this == obj) return true;
             if (obj == null || getClass() != obj.getClass()) return false;
             MyClass myClass = (MyClass) obj;
             return id == myClass.id;
         }
     }
     ```

3. **hashCode()**
   - Mô tả: Phương thức này trả về mã băm (hash code) của đối tượng. Mã băm này được sử dụng trong các cấu trúc dữ liệu như HashMap, HashSet.
   - Ví dụ:
     ```java
     public class MyClass {
         private int id;
         public MyClass(int id) {
             this.id = id;
         }
         
         @Override
         public int hashCode() {
             return Integer.hashCode(id);
         }
     }
     ```

4. **getClass()**
   - Mô tả: Phương thức này trả về lớp đối tượng tại runtime. Đây là phương thức rất hữu ích khi cần phản ánh thông tin lớp của đối tượng.
   - Ví dụ:
     ```java
     MyClass obj = new MyClass(1);
     System.out.println(obj.getClass().getName()); // Kết quả: MyClass
     ```

5. **clone()**
   - Mô tả: Phương thức này tạo một bản sao của đối tượng. Để sử dụng, lớp cần phải thực hiện giao diện `Cloneable`.
   - Ví dụ:
     ```java
     public class MyClass implements Cloneable {
         private int id;
         public MyClass(int id) {
             this.id = id;
         }
         
         @Override
         protected Object clone() throws CloneNotSupportedException {
             return super.clone();
         }
     }
     ```

6. **finalize()**
   - Mô tả: Phương thức này được gọi trước khi bộ dọn rác (garbage collector) thu hồi bộ nhớ của đối tượng. Phương thức này hiếm khi được sử dụng trong thực tế.
   - Ví dụ:
     ```java
     public class MyClass {
         @Override
         protected void finalize() throws Throwable {
             System.out.println("Object is being garbage collected");
         }
     }
     ```

## Ý nghĩa của lớp Object

Lớp Object trong Java giúp tạo nên một hệ thống phân cấp lớp thống nhất và cung cấp các phương thức cơ bản cho mọi đối tượng. Nhờ kế thừa từ lớp Object, mọi đối tượng trong Java đều có các phương thức cơ bản giúp xử lý và quản lý đối tượng dễ dàng hơn.

# Tính Đa Hình (Polymorphism) trong Java

## Định nghĩa
**Tính đa hình** là một khái niệm quan trọng trong lập trình hướng đối tượng, cho phép một hành động có thể có nhiều cách thực hiện khác nhau. Trong Java, tính đa hình cho phép một phương thức có thể hoạt động trên nhiều kiểu đối tượng khác nhau.

## Các Loại Đa Hình trong Java
Trong Java, tính đa hình có hai loại chính:
1. **Đa hình lúc biên dịch (Compile-time Polymorphism)**: Hay còn gọi là **Method Overloading** (Nạp chồng phương thức).
2. **Đa hình lúc chạy (Runtime Polymorphism)**: Hay còn gọi là **Method Overriding** (Ghi đè phương thức).

---

## 1. Đa Hình Lúc Biên Dịch (Compile-time Polymorphism)

### Method Overloading (Nạp chồng phương thức)
Method Overloading là khi nhiều phương thức trong cùng một lớp có cùng tên nhưng khác nhau về số lượng hoặc kiểu tham số. Việc này cho phép sử dụng cùng một tên phương thức để thực hiện các tác vụ khác nhau dựa trên tham số truyền vào.

**Ví dụ:**

```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) {
        return a + b;
    }
}
```
## 2. Đa Hình Lúc Chạy (Runtime Polymorphism)
### Method Overriding (Ghi đè phương thức)
Method Overriding xảy ra khi một lớp con (subclass) cung cấp triển khai cụ thể cho một phương thức đã có trong lớp cha (superclass). Đây là một ví dụ tiêu biểu của tính đa hình động, cho phép Java chọn phương thức chính xác trong thời gian chạy.

**ví dụ:**
```java
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Woof Woof");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        myDog.sound(); // Output: Woof Woof
    }
}
```

## Lợi ích của tính đa hình
- Tính mở rộng: Cho phép thêm các tính năng mới mà không ảnh hưởng đến mã nguồn cũ.
- Dễ bảo trì: Giúp mã nguồn rõ ràng, dễ đọc, và dễ bảo trì.
Tái sử dụng mã: Tăng cường khả năng tái sử dụng mã, giảm thiểu mã lặp.

## Sự Khác Biệt giữa Overloading và Overriding

| Đặc điểm  | Overloading | Overriding                                             |
|---------------|------------------|------------------------------------------------------------|
| Lúc thực hiện     |Biên dịch          | 	Chạy thời gian thực                               |
| Phương thức trong    | 	Cùng một lớp        | 	Lớp con và lớp cha                     |
| Thay đổi tham số        | 	Bắt buộc (khác số lượng hoặc kiểu)       | Không bắt buộc|
| Từ khóa **@Override**      | Không cần thiết        |       Bắt buộc (để đảm bảo ghi đè)                                                      |

