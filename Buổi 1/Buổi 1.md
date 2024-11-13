
# BUỔI 1 - WELCOME TO JAVA

# Nội dung

- **Ngôn ngữ Java là gì:**
  Java là một ngôn ngữ lập trình hướng đối tượng được thiết kế để chạy trên nhiều nền tảng khác nhau mà không cần phải chỉnh sửa mã nguồn. Nó được phát triển bởi Sun Microsystems và hiện tại thuộc về Oracle.

- **Lí do ra đời của Java:**
  Java ra đời nhằm giải quyết vấn đề tương thích đa nền tảng và cung cấp một môi trường phát triển đơn giản, bảo mật, và mạnh mẽ cho các ứng dụng mạng.

- **Cách Java hoạt động và điều gì xảy ra khi chạy code Java (.java):**
  Khi một file `.java` được biên dịch, nó sẽ tạo ra bytecode (.class) có thể chạy trên bất kỳ nền tảng nào có máy ảo Java (JVM). JVM thực thi bytecode này mà không cần quan tâm tới hệ điều hành của máy tính.

# Cấu trúc chương trình Java

Một chương trình Java cơ bản bao gồm các thành phần sau:

```java
// Khai báo package (nếu có)
package mypackage;

// Import các thư viện cần thiết
import java.util.Scanner; // ví dụ: nhập dữ liệu từ bàn phím

// Khai báo class
public class MyProgram {

    // Phương thức main: điểm bắt đầu của chương trình
    public static void main(String[] args) {
        // Câu lệnh trong phương thức main
        System.out.println("Hello, Java!");
    }
}
```


# Package là gì
Package trong Java là một không gian tên (namespace) được sử dụng để tổ chức các lớp (classes) và giao diện (interfaces). Các package giúp nhóm các lớp có liên quan lại với nhau, giúp quản lý mã nguồn dễ dàng hơn và tránh xung đột tên giữa các lớp có cùng tên nhưng khác package
```java
package mypackage; // Khai báo package

public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}

```
Trong ví dụ trên, mypackage là tên của package, và lớp HelloWorld thuộc về package này. Tất cả các lớp trong cùng một package có thể truy cập trực tiếp các lớp khác trong cùng package mà không cần khai báo import.

# Khai báo biến nguyên thủy:

| Kiểu dữ liệu  | Kích thước (bit) | Phạm vi giá trị                                            | Ví dụ khai báo          |
|---------------|------------------|------------------------------------------------------------|-------------------------|
| `byte`        | 8                | -128 đến 127                                                | `byte age = 25;`         |
| `short`       | 16               | -32,768 đến 32,767                                          | `short year = 2024;`     |
| `int`         | 32               | -2^31 đến 2^31 - 1 (khoảng -2,147,483,648 đến 2,147,483,647)| `int salary = 50000;`    |
| `long`        | 64               | -2^63 đến 2^63 - 1 (khoảng -9,223,372,036,854,775,808 đến 9,223,372,036,854,775,807) | `long distance = 100000L;` |
| `float`       | 32               | Giá trị số thực có dấu, khoảng 1.4e-45 đến 3.4e+38          | `float price = 19.99f;`  |
| `double`      | 64               | Giá trị số thực có dấu, khoảng 4.9e-324 đến 1.7e+308        | `double pi = 3.14159;`   |
| `char`        | 16               | Một ký tự Unicode, từ '\u0000' đến '\uffff' (0 đến 65,535)  | `char letter = 'A';`     |
| `boolean`     | 1                | Chỉ có 2 giá trị: `true` hoặc `false`                      | `boolean isJavaFun = true;` |


# Vòng lặp trong Java

Trong Java, có ba loại vòng lặp chính được sử dụng để lặp qua các phần tử hoặc thực hiện một đoạn mã nhiều lần dựa trên điều kiện:

-  **Vòng lặp `for`**
-  **Vòng lặp `while`**
-  **Vòng lặp `do-while`**

**1. Vòng lặp `for`**

Vòng lặp `for` được sử dụng khi biết trước số lần lặp. Cấu trúc cơ bản của vòng lặp `for` như sau:

```java
for (khởi tạo; điều kiện; bước lặp) {
    // Khối lệnh được thực thi
}
```
**2. Vòng lặp `While`**

Vòng lặp while tiếp tục thực hiện lặp chừng nào điều kiện đúng. Cấu trúc của vòng lặp while như sau:
```java
while (điều kiện) {
    // Khối lệnh được thực thi
}

```
**3. Vòng lặp `do-while`**

Vòng lặp do-while luôn thực hiện ít nhất một lần, bởi vì điều kiện được kiểm tra sau khi thực hiện khối lệnh. Cấu trúc của vòng lặp do-while như sau:
```java
do {
    // Khối lệnh được thực thi
} while (điều kiện);

```
# Câu lệnh rẽ nhánh

Câu lệnh rẽ nhánh trong Java được sử dụng để điều khiển luồng của chương trình dựa trên các điều kiện cụ thể. Có ba loại chính của câu lệnh rẽ nhánh:

- **Câu lệnh `if`**
- **Câu lệnh `if-else`**
- **Câu lệnh `else-if`**
- **Câu lệnh `switch`**

**1. Câu lệnh `if`**

Câu lệnh `if` kiểm tra một điều kiện. Nếu điều kiện là `true`, khối lệnh trong câu lệnh `if` sẽ được thực thi.

- Cấu trúc:
```java
if (điều kiện) {
    // Khối lệnh được thực thi nếu điều kiện là true
}
```
**2. Câu lệnh `if-else`**

Câu lệnh if-else cung cấp một lựa chọn thay thế nếu điều kiện không thỏa mãn (false).
- Cấu trúc:
```java
if (điều kiện) {
    // Khối lệnh được thực thi nếu điều kiện là true
} else {
    // Khối lệnh được thực thi nếu điều kiện là false
}

```
**3. Câu lệnh `else-if`**

Câu lệnh else-if cho phép kiểm tra nhiều điều kiện trong cùng một khối lệnh.
- Cấu trúc:
```java
if (điều kiện1) {
    // Khối lệnh được thực thi nếu điều kiện1 là true
} else if (điều kiện2) {
    // Khối lệnh được thực thi nếu điều kiện2 là true
} else {
    // Khối lệnh được thực thi nếu tất cả các điều kiện đều là false
}

```
# Mảng trong Java

Mảng (Array) trong Java là một cấu trúc dữ liệu giúp lưu trữ nhiều phần tử có cùng kiểu dữ liệu. Mảng có một kích thước cố định và các phần tử trong mảng được đánh chỉ số bắt đầu từ `0`.

### 1. Khai báo và khởi tạo mảng

### Khai báo mảng:
Trong Java, để khai báo một mảng, chúng ta sử dụng cú pháp:

```java
type[] arrayName;
```
- type: Kiểu dữ liệu của các phần tử trong mảng (ví dụ: int, float, String).
- arrayName: Tên của mảng.
### Khởi tạo mảng:
Có thể khởi tạo mảng với một kích thước xác định:
```java
arrayName = new type[size];
```
Hoặc có thể khởi tạo mảng với giá trị cụ thể:
```java
int[] arr = {1, 2, 3, 4, 5};  // Mảng được khởi tạo với các giá trị cụ thể
```
### 2. Truy cập các phần tử trong mảng
Có thể truy cập các phần tử của mảng thông qua chỉ số (index). Chỉ số của mảng bắt đầu từ 0.
```java
arrayName[index];
```
### 3. Duyệt mảng
Để duyệt qua các phần tử của mảng, có thể sử dụng các vòng lặp như for, while, hoặc for-each.
 - Ví dụ sử dụng vòng lặp for:
```java
int[] arr = {10, 20, 30, 40, 50};

for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```
- Ví dụ sử dụng vòng lặp for-each:
```java
int[] arr = {10, 20, 30, 40, 50};

for (int element : arr) {
    System.out.println(element);
}
```
### 4. Độ dài của mảng
Trong Java, có thể sử dụng thuộc tính length để biết kích thước của mảng.
```java
int[] arr = {10, 20, 30, 40, 50};
System.out.println("Độ dài của mảng: " + arr.length);  // Kết quả: 5
```
### 5. Mảng nhiều chiều
Java cũng hỗ trợ mảng nhiều chiều, phổ biến nhất là mảng 2 chiều (ma trận).
```java
type[][] arrayName = new type[rows][columns];
```
# Tổng quan về Class và Object

## Từ khóa `this` trong Java

- Từ khóa `this` trong Java là một biến tham chiếu đặc biệt, được sử dụng trong các phương thức không tĩnh của một lớp để tham chiếu đến đối tượng hiện tại (đối tượng mà phương thức hiện tại đang hoạt động trên đó).
- Nó chủ yếu được sử dụng để tránh sự nhầm lẫn giữa các biến thành viên và tham số của phương thức khi chúng có cùng tên.

## Sử dụng từ khóa `this`

### 1. Tham chiếu đến biến instance (biến thành viên)
Khi biến thành viên của lớp có cùng tên với tham số của phương thức, từ khóa `this` giúp phân biệt chúng.

**Ví dụ**:
```java
class SinhVien {
    private String ten;

    // Constructor có tham số trùng tên với biến instance
    public SinhVien(String ten) {
        this.ten = ten; // Sử dụng this để tham chiếu đến biến thành viên
    }

    public void hienThiTen() {
        System.out.println("Tên sinh viên: " + this.ten);
    }
}

public class Main {
    public static void main(String[] args) {
        SinhVien sv = new SinhVien("An");
        sv.hienThiTen(); // Kết quả: Tên sinh viên: An
    }
}
```
### 2. Gọi constructor khác trong cùng một lớp
Từ khóa this cũng có thể được sử dụng để gọi một constructor khác trong cùng lớp, giúp tái sử dụng mã lệnh.
```java
class SinhVien {
    private String ten;
    private int tuoi;

    // Constructor đầu tiên
    public SinhVien(String ten) {
        this(ten, 18); // Gọi constructor khác trong cùng lớp
    }

    // Constructor thứ hai
    public SinhVien(String ten, int tuoi) {
        this.ten = ten;
        this.tuoi = tuoi;
    }

    public void hienThiThongTin() {
        System.out.println("Tên: " + this.ten + ", Tuổi: " + this.tuoi);
    }
}

public class Main {
    public static void main(String[] args) {
        SinhVien sv = new SinhVien("Minh");
        sv.hienThiThongTin(); // Kết quả: Tên: Minh, Tuổi: 18
    }
}
```
### 3. Truyền đối tượng hiện tại làm tham số
`this` có thể được sử dụng để truyền đối tượng hiện tại làm tham số cho một phương thức hoặc constructor khác.

```java
class A {
    public void methodA(B obj) {
        obj.methodB(this); // Truyền đối tượng hiện tại làm tham số
    }
}

class B {
    public void methodB(A obj) {
        System.out.println("Đối tượng của A được truyền thành công!");
    }
}

public class Main {
    public static void main(String[] args) {
        A objA = new A();
        B objB = new B();
        objA.methodA(objB);
    }
}
```
### 4. Trả về đối tượng hiện tại
`this` cũng có thể được sử dụng để trả về đối tượng hiện tại từ phương thức.
```java
class A {
    public A getA() {
        return this; // Trả về đối tượng hiện tại
    }

    public void hienThiThongTin() {
        System.out.println("Đây là đối tượng hiện tại");
    }
}

public class Main {
    public static void main(String[] args) {
        A obj = new A();
        obj.getA().hienThiThongTin(); // Kết quả: Đây là đối tượng hiện tại
    }
}
```
# Constructor trong Java

## Đặc điểm của Constructor
1. **Tên trùng với tên lớp**: Constructor phải có cùng tên với lớp.
2. **Không có kiểu trả về**: Constructor không có kiểu trả về, không được khai báo với từ khóa `void` hoặc bất kỳ kiểu dữ liệu nào khác.
3. **Tự động gọi khi đối tượng được tạo**: Constructor được gọi tự động ngay khi đối tượng được tạo thông qua từ khóa `new`.
4. **Constructor mặc định**: Nếu không khai báo constructor, Java sẽ cung cấp một constructor mặc định không tham số cho mỗi lớp.

## Phân loại Constructor

### 1. Constructor không tham số (Default Constructor)
- Đây là constructor mặc định, không nhận bất kỳ tham số nào.
- Nếu không khai báo constructor trong lớp, Java tự động cung cấp một constructor không tham số.

**Ví dụ**:
```java
class SinhVien {
    private String ten;

    // Constructor không tham số
    public SinhVien() {
        ten = "Chưa rõ";
    }

    public void hienThiTen() {
        System.out.println("Tên sinh viên: " + ten);
    }
}

public class Main {
    public static void main(String[] args) {
        SinhVien sv = new SinhVien(); // Gọi constructor không tham số
        sv.hienThiTen(); // Kết quả: Tên sinh viên: Chưa rõ
    }
}
```
### 2. Constructor có tham số (Parameterized Constructor)
Constructor có tham số nhận các giá trị khi khởi tạo đối tượng và gán chúng cho các biến instance.
```java
class SinhVien {
    private String ten;

    // Constructor có tham số
    public SinhVien(String ten) {
        this.ten = ten;
    }

    public void hienThiTen() {
        System.out.println("Tên sinh viên: " + ten);
    }
}

public class Main {
    public static void main(String[] args) {
        SinhVien sv = new SinhVien("Minh"); // Gọi constructor có tham số
        sv.hienThiTen(); // Kết quả: Tên sinh viên: Minh
    }
}
```
### 3. Constructor sao chép (Copy Constructor)
Constructor sao chép được sử dụng để tạo một đối tượng mới là bản sao của đối tượng đã có.
```java
class SinhVien {
    private String ten;

    // Constructor có tham số
    public SinhVien(String ten) {
        this.ten = ten;
    }

    // Constructor sao chép
    public SinhVien(SinhVien sv) {
        this.ten = sv.ten;
    }

    public void hienThiTen() {
        System.out.println("Tên sinh viên: " + ten);
    }
}

public class Main {
    public static void main(String[] args) {
        SinhVien sv1 = new SinhVien("Minh");
        SinhVien sv2 = new SinhVien(sv1); // Sử dụng constructor sao chép
        sv2.hienThiTen(); // Kết quả: Tên sinh viên: Minh
    }
}
```
# Access Modifier trong Java

- **Access modifier** (bộ định danh truy cập) trong Java xác định phạm vi truy cập của các lớp, phương thức, biến và constructor. Nó kiểm soát mức độ truy cập của các thành viên trong một lớp từ các lớp khác.
- Java cung cấp bốn loại access modifier chính: `private`, `default` (không có từ khóa), `protected` và `public`.

## Các access modifier chính

| Modifier     | Mức độ truy cập trong cùng lớp | Mức độ truy cập trong cùng package | Mức độ truy cập từ subclass khác package | Mức độ truy cập từ lớp khác package |
|--------------|--------------------------------|-------------------------------------|------------------------------------------|--------------------------------------|
| `private`    | ✅ Có thể truy cập              | ❌ Không thể truy cập               | ❌ Không thể truy cập                    | ❌ Không thể truy cập                |
| `default`    | ✅ Có thể truy cập              | ✅ Có thể truy cập                  | ❌ Không thể truy cập                    | ❌ Không thể truy cập                |
| `protected`  | ✅ Có thể truy cập              | ✅ Có thể truy cập                  | ✅ Có thể truy cập                       | ❌ Không thể truy cập                |
| `public`     | ✅ Có thể truy cập              | ✅ Có thể truy cập                  | ✅ Có thể truy cập                       | ✅ Có thể truy cập                   |

---

# Getter và Setter trong Java

- **Getter** và **Setter** là các phương thức trong Java được sử dụng để truy cập và cập nhật giá trị của các thuộc tính (biến thành viên) trong một lớp.
- Trong lập trình hướng đối tượng, các biến thành viên thường được khai báo là `private` để bảo vệ dữ liệu, và các phương thức getter và setter sẽ cung cấp cơ chế truy cập và thay đổi dữ liệu từ bên ngoài lớp theo cách kiểm soát.

## Cấu trúc Getter và Setter

### 1. **Getter**:
- **Getter** là một phương thức dùng để lấy (get) giá trị của một biến thành viên.
- **Cú pháp**: Tên của phương thức getter thường bắt đầu bằng từ khóa `get` và theo sau là tên biến với chữ cái đầu viết hoa.

```java
public class Person {
    private String name;  // Biến private

    // Getter
    public String getName() {
        return name;
    }
}
```
### 2. **Setter**:
- **Setter** là một phương thức dùng để đặt (set) giá trị cho một biến thành viên.
- **Cú pháp:** Tên của phương thức setter thường bắt đầu bằng từ khóa set và theo sau là tên biến với chữ cái đầu viết hoa. Nó thường nhận một tham số để cập nhật giá trị của biến.
```java
public class Person {
    private String name;  // Biến private

    // Setter
    public void setName(String name) {
        this.name = name;
    }
}
```
### 3. Lợi ích của Getter và Setter
- **Bảo vệ dữ liệu:** Các biến thành viên thường được khai báo là private để không bị truy cập trực tiếp từ bên ngoài. Getter và setter cung cấp cách thức an toàn để truy cập và thay đổi dữ liệu.
- **Kiểm soát dữ liệu:** Với setter, ta có thể thêm logic kiểm tra dữ liệu trước khi thay đổi, đảm bảo rằng chỉ những giá trị hợp lệ mới được gán cho biến.
- **Tính linh hoạt:** Ta có thể thay đổi cách mà các biến được truy cập hoặc cập nhật mà không ảnh hưởng đến các đoạn mã sử dụng các biến đó.

# Từ khóa `static` trong Java

- Từ khóa **`static`** trong Java được sử dụng để khai báo các thành viên (biến, phương thức, khối lệnh, hoặc lớp lồng nhau) thuộc về **lớp** thay vì thuộc về **đối tượng** của lớp.
- Các thành viên `static` có thể được truy cập mà không cần tạo đối tượng của lớp, chúng tồn tại ở cấp độ lớp (class-level) thay vì đối tượng (instance-level).

---

## **1. Biến `static` (Static Variables)**
- **Biến `static`** là biến dùng chung cho tất cả các đối tượng của lớp. Mỗi đối tượng sẽ không có bản sao riêng của biến này, thay vào đó chúng chia sẻ cùng một biến.
- **Biến `static`** được khởi tạo một lần khi lớp được tải vào bộ nhớ và tồn tại cho đến khi chương trình kết thúc.
### Cú pháp khai báo biến `static`:
```java
class Person {
    static String species = "Homo sapiens";  // Biến static
}
public class Main {
    public static void main(String[] args) {
        // Không cần tạo đối tượng vẫn có thể truy cập biến static
        System.out.println("Loài người: " + Person.species);
    }
}
```
## **2. Phương thức `static` (Static Methods)**
- **Phương thức `static`** có thể được gọi mà không cần tạo đối tượng của lớp.
- **Phương thức `static`** chỉ có thể truy cập các thành viên `static` khác (biến `static` và phương thức `static`) trong lớp và không thể truy cập các thành viên không phải là `static`.
```java
class MathUtils {
    // Phương thức static
    static int add(int a, int b) {
        return a + b;
    }
}
public class Main {
    public static void main(String[] args) {
        // Gọi phương thức static mà không cần tạo đối tượng
        int result = MathUtils.add(5, 3);
        System.out.println("Kết quả: " + result);
    }
}
```
## **3. Khối lệnh static (Static Block)**
- **Khối lệnh `static`** được sử dụng để khởi tạo các thành viên static. Nó được thực thi một lần khi lớp được nạp vào bộ nhớ, trước khi bất kỳ phương thức hoặc khối lệnh nào của lớp được gọi.
```java
class Test {
    static String message;

    // Static block
    static {
        message = "Hello from static block!";
        System.out.println("Static block executed.");
    }
}
public class Main {
    public static void main(String[] args) {
        // Khối lệnh static sẽ được thực thi khi lớp Test được tải vào bộ nhớ
        System.out.println(Test.message);
    }
}
```
## **4. Lớp lồng nhau static (Static Nested Class)**
- **Lớp lồng nhau `static`** là một lớp bên trong lớp khác và được khai báo với từ khóa static. Nó không phụ thuộc vào đối tượng của lớp bên ngoài và có thể được truy cập mà không cần tạo đối tượng của lớp ngoài.
```java
class OuterClass {
    static class NestedStaticClass {
        void display() {
            System.out.println("Đây là lớp lồng nhau static.");
        }
    }
}
```