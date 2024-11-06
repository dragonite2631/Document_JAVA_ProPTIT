
# BUỔI 2: TÌM HIỂU SÂU VỀ OBJECT

# 1. Object là gì?

Trong Java, **Object** (đối tượng) là một thực thể có trạng thái và hành vi. Trạng thái của đối tượng được đại diện bởi các thuộc tính (biến), còn hành vi của đối tượng được đại diện bởi các phương thức (hàm). Ví dụ, một đối tượng `Car` có thể có trạng thái là `color` (màu sắc), `brand` (hãng xe), và hành vi như `drive` (lái), `brake` (phanh).

**Cú pháp để tạo một đối tượng trong Java:**
```java
Car myCar = new Car();
```

# 2. Object được lưu thế nào trong Java

Trong Java, các đối tượng (objects) được lưu trữ trong **Heap Memory** (bộ nhớ Heap). Khi một đối tượng được tạo bằng từ khóa `new`, Java cấp phát không gian bộ nhớ trong Heap Memory để lưu trữ đối tượng đó. Bộ nhớ này được quản lý bởi **Garbage Collector**, một cơ chế tự động của Java nhằm thu hồi bộ nhớ của các đối tượng không còn được tham chiếu để tránh lãng phí tài nguyên.

## Cách hoạt động của bộ nhớ trong Java:

- **Stack Memory**: Dùng để lưu trữ các biến cục bộ và tham chiếu (reference) đến các đối tượng trong Heap Memory. Các biến này sẽ bị xóa khi phương thức kết thúc.
- **Heap Memory**: Là nơi lưu trữ tất cả các đối tượng được tạo ra trong Java. Các đối tượng được cấp phát bộ nhớ tại đây sẽ tiếp tục tồn tại cho đến khi không còn bất kỳ tham chiếu nào đến chúng.

## Ví dụ:

```java
public class Main {
    public static void main(String[] args) {
        Car myCar = new Car(); // Đối tượng myCar được lưu trong Heap Memory
    }
}
```

# 3. Wrapper Class

Trong Java, **Wrapper Class** là các lớp bao bọc (wrapper) cung cấp một cách để sử dụng các kiểu dữ liệu nguyên thủy (như `int`, `char`, `boolean`, v.v.) như các đối tượng. Mỗi kiểu nguyên thủy có một lớp wrapper tương ứng trong gói `java.lang`. Các kiểu dữ liệu lưu dạng object này tuân theo cách Java lưu trữ object, tức là không lưu trực tiếp object, mà chỉ lưu địa chỉ tới object đó.


## Mục đích của Wrapper Class

Wrapper Class được sử dụng để:
1. **Tạo đối tượng** từ các kiểu dữ liệu nguyên thủy, cho phép sử dụng chúng trong các tình huống yêu cầu đối tượng, như khi lưu trữ trong các cấu trúc dữ liệu `Collection` (ví dụ: `ArrayList`, `HashMap`, v.v.).
2. **Cung cấp các phương thức tiện ích** để chuyển đổi và xử lý dữ liệu kiểu nguyên thủy, như chuyển đổi từ `String` sang `int` và ngược lại.
3. **Tích hợp với các tính năng của Java như Autoboxing và Unboxing** (tự động chuyển đổi giữa kiểu nguyên thủy và wrapper).

## Các Wrapper Class Tương Ứng Với Kiểu Nguyên Thủy

| Kiểu Nguyên Thủy | Wrapper Class |
|------------------|---------------|
| `byte`           | `Byte`        |
| `short`          | `Short`       |
| `int`            | `Integer`     |
| `long`           | `Long`        |
| `float`          | `Float`       |
| `double`         | `Double`      |
| `char`           | `Character`   |
| `boolean`        | `Boolean`     |

## Ví dụ về Wrapper Class

Dưới đây là một ví dụ về cách sử dụng Wrapper Class trong Java:

```java
public class Main {
    public static void main(String[] args) {
        // Sử dụng Wrapper Class Integer thay cho int
        Integer intObject = Integer.valueOf(10); // Autoboxing
        int primitiveInt = intObject.intValue(); // Unboxing
        
        System.out.println("Giá trị của đối tượng Integer: " + intObject);
        System.out.println("Giá trị kiểu nguyên thủy: " + primitiveInt);
    }
}
```
## Nhược điểm của Wrapper Class
**Hiệu suất**: Đối tượng Wrapper chiếm nhiều bộ nhớ hơn kiểu nguyên thủy và cần xử lý nhiều hơn khi thực hiện autoboxing và unboxing.

**Khả năng xảy ra lỗi NullPointerException**: Nếu đối tượng Wrapper là null và cố gắng chuyển đổi thành kiểu nguyên thủy, sẽ xảy ra lỗi NullPointerException.
# 4. Auto Boxing / Auto Unboxing
- **Auto Boxing**: Tự động chuyển đổi từ kiểu nguyên thủy sang kiểu đối tượng Wrapper Class. Ví dụ: `int` sang `Integer`.
- **Auto Unboxing**: Tự động chuyển đổi từ kiểu đối tượng Wrapper Class sang kiểu nguyên thủy. Ví dụ: `Integer` sang `int`.

# 5. String và StringBuilder trong Java

## String trong Java

Trong Java, **String** là một **immutable class** được sử dụng để lưu trữ chuỗi ký tự. **Immutable class** là là một lớp bất biến, các thuộc tính của nó không bao giờ bị thay đổi và chỉ có thể thiết lập lúc khởi tạo. Biến khai báo theo kiểu String khi được tạo ra sẽ được lưu vào **String Pool**.
**String pool** là một vùng nhớ đặc biệt nằm trong vùng nhớ **Heap**** , dùng để lưu trữ các biến được khai báo theo kiểu **String**.
**String pool** giúp tối ưu hoá việc lưu trữ và sử dụng vùng nhớ khi khai báo biến **String**, giúp hạn chế tình trạng tràn bộ nhớ **Java Heap Space**.
### Khởi tạo String
Có hai cách chính để khởi tạo một đối tượng `String`:
```java
String str1 = "abc"; // Sử dụng literal
String str2 = new String("abc"); // Sử dụng từ khóa new
```
![Alt text](stringpool.png "a title")
## StringBuilder
**StringBuilder** là một lớp được sử dụng để tạo và thay đổi chuỗi ký tự, và nó mutable (có thể thay đổi). Khác với **String**, **StringBuilder** không tạo ra một đối tượng mới khi thay đổi chuỗi, giúp tiết kiệm bộ nhớ và tăng hiệu suất.
```java
StringBuilder sb = new StringBuilder("Hello");
```
### Các phương thức phổ biến của StringBuilder
```java
StringBuilder sb = new StringBuilder("Hello");

// Thêm vào chuỗi
sb.append(" World"); // "Hello World"

// Chèn chuỗi
sb.insert(5, ","); // "Hello, World"

// Xóa ký tự hoặc chuỗi con
sb.delete(5, 6); // "Hello World"

// Đảo ngược chuỗi
sb.reverse(); // "dlroW olleH"

// Chuyển đổi thành String
String result = sb.toString(); // "Hello, World"
```
# 6. equals, hashCode và toán tử == trong Java

## Toán tử `==` trong Java

Toán tử `==` trong Java được sử dụng để so sánh:
- **Đối với kiểu nguyên thủy**: So sánh giá trị của hai biến.
- **Đối với đối tượng (tham chiếu)**: So sánh địa chỉ (vị trí trong bộ nhớ) của hai đối tượng, tức là kiểm tra xem hai biến có tham chiếu đến cùng một đối tượng hay không.

### Ví dụ về `==`:
```java
int a = 10;
int b = 10;
System.out.println(a == b); // true, so sánh giá trị của kiểu nguyên thủy

String s1 = new String("Java");
String s2 = new String("Java");
System.out.println(s1 == s2); // false, s1 và s2 là hai đối tượng khác nhau trong bộ nhớ
```
## Phương thức equals trong Java
Phương thức equals được định nghĩa trong lớp Object và thường được sử dụng để so sánh nội dung của hai đối tượng, thay vì so sánh vị trí trong bộ nhớ như ==. Tuy nhiên, lớp Object mặc định chỉ so sánh vị trí trong bộ nhớ. Các lớp khác như String, Integer, và List đã ghi đè phương thức này để so sánh nội dung.
```java
String s1 = new String("Java");
String s2 = new String("Java");
System.out.println(s1.equals(s2)); // true, nội dung của hai chuỗi giống nhau
```
## Khi nào nên ghi đè equals
Nên ghi đè equals khi muốn so sánh nội dung của các đối tượng tùy chỉnh. Ví dụ, trong một lớp Student với các thuộc tính như id, name, ta có thể ghi đè equals để hai đối tượng Student được coi là bằng nhau nếu có cùng id.
```java
public class Student {
    private int id;
    private String name;

    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true;
        if (obj == null || getClass() != obj.getClass()) return false;
        Student student = (Student) obj;
        return id == student.id;
    }
}
```
## Phương thức hashCode trong Java
**hashCode** là phương thức trả về một số nguyên duy nhất đại diện cho đối tượng. Nó cũng được định nghĩa trong lớp Object và có mối quan hệ chặt chẽ với equals. Phương thức này đặc biệt quan trọng khi sử dụng đối tượng trong các cấu trúc dữ liệu dựa trên hash như HashMap, HashSet, và HashTable.

## Nguyên tắc ghi đè equals và hashCode
Nếu hai đối tượng được coi là bằng nhau (theo equals), chúng phải có cùng mã băm (hashCode).
Nếu hai đối tượng có cùng hashCode, chúng không nhất thiết phải bằng nhau.
```java
Student s1 = new Student(1, "Alice");
Student s2 = new Student(1, "Alice");

System.out.println(s1.equals(s2)); // true, vì id giống nhau
System.out.println(s1.hashCode() == s2.hashCode()); // true, vì cùng id

```
## So sánh `==`, `equals`, và `hashCode`

| Thuộc tính         | Toán tử `==`                    | Phương thức `equals`               | Phương thức `hashCode`          |
|--------------------|---------------------------------|------------------------------------|---------------------------------|
| So sánh            | Địa chỉ bộ nhớ (đối tượng)      | Nội dung (khi được ghi đè)        | Mã băm của đối tượng            |
| Mặc định           | So sánh địa chỉ                 | So sánh địa chỉ                    | Tạo mã băm dựa trên địa chỉ     |
| Có thể ghi đè      | Không                           | Có                                | Có                              |
| Sử dụng trong      | Kiểu nguyên thủy, tham chiếu    | So sánh nội dung của đối tượng     | Cấu trúc dữ liệu Hash           |
# 7. Cách Java truyền tham số, pass by value, tại sao pass by value mà String lại thay đổi được

## Pass by Value trong Java

Trong Java, tất cả các tham số khi truyền vào phương thức đều được truyền **theo kiểu pass by value**. Điều này có nghĩa là Java sẽ **tạo một bản sao của giá trị** được truyền vào, và phương thức chỉ làm việc với bản sao đó. Điều này áp dụng cho cả kiểu dữ liệu nguyên thủy (như `int`, `float`, v.v.) và tham chiếu đối tượng.

### Ví dụ với Kiểu Dữ Liệu Nguyên Thủy:
```java
public class PassByValueExample {
    public static void main(String[] args) {
        int x = 10;
        modifyPrimitive(x);
        System.out.println(x); // Output: 10, giá trị x không bị thay đổi
    }

    public static void modifyPrimitive(int num) {
        num = 20;
    }
}
```

Trong ví dụ trên, giá trị của `x` không thay đổi sau khi gọi phương thức `modifyPrimitive` vì `num` chỉ là một bản sao của `x`.

## Pass by Value với Tham Chiếu Đối Tượng

Với đối tượng, Java vẫn truyền theo kiểu pass by value, nhưng giá trị được truyền là **tham chiếu (reference)** của đối tượng, không phải bản thân đối tượng. Điều này có nghĩa là nếu bạn thay đổi thuộc tính của đối tượng bên trong phương thức, thay đổi sẽ phản ánh trên đối tượng gốc. Tuy nhiên, nếu bạn gán tham chiếu đến một đối tượng mới, tham chiếu ban đầu không bị thay đổi.

### Ví dụ:
```java
public class PassByReferenceExample {
    public static void main(String[] args) {
        Student student = new Student("Alice");
        modifyStudent(student);
        System.out.println(student.getName()); // Output: Bob, thuộc tính name đã bị thay đổi
    }

    public static void modifyStudent(Student s) {
        s.setName("Bob");
    }
}
```

Trong ví dụ này, `student` có thuộc tính `name` bị thay đổi vì phương thức `modifyStudent` thay đổi trạng thái của đối tượng mà `student` tham chiếu đến.

## Vì Sao Pass by Value nhưng `String` Vẫn Có Thể Thay Đổi?

Trong Java, `String` là **immutable** (bất biến), có nghĩa là một khi được tạo, giá trị của chuỗi không thể thay đổi. Khi bạn thực hiện các thao tác như nối chuỗi hoặc thay đổi giá trị chuỗi, Java thực chất tạo ra một đối tượng `String` mới và trả về tham chiếu đến đối tượng đó, thay vì thay đổi đối tượng ban đầu.

### Ví dụ về String:
```java
public class StringExample {
    public static void main(String[] args) {
        String text = "Hello";
        modifyString(text);
        System.out.println(text); // Output: Hello, giá trị không thay đổi
    }

    public static void modifyString(String str) {
        str = str + " World"; // Tạo một đối tượng String mới, không thay đổi text ban đầu
    }
}
```

### Lý do `String` có thể thay đổi cảm giác nhưng vẫn là Pass by Value

- Bất kỳ thao tác nào trên `String` đều tạo ra một đối tượng `String` mới, chứ không phải thay đổi trực tiếp trên đối tượng ban đầu.
- Khi truyền một `String` vào phương thức, chỉ có **tham chiếu đến đối tượng ban đầu được truyền vào**, và mọi thao tác trên chuỗi thực chất là thao tác trên một **bản sao của tham chiếu**.

# 8. Các khái niệm cơ bản về Garbage Collector

## Garbage Collection là gì?

Garbage Collection (GC) trong Java là quá trình tự động quản lý bộ nhớ nhằm **thu hồi và giải phóng bộ nhớ** của các đối tượng không còn được sử dụng (không có tham chiếu đến) nữa. Bộ thu gom rác giúp giảm thiểu tình trạng bộ nhớ bị lãng phí và ngăn ngừa rò rỉ bộ nhớ, cho phép chương trình sử dụng bộ nhớ hiệu quả hơn.

## Cơ chế hoạt động của Garbage Collector

Java sử dụng thuật toán **Mark and Sweep** để xác định các đối tượng nào cần được thu gom:
- **Mark**: Xác định và đánh dấu các đối tượng còn tham chiếu hoặc không còn tham chiếu.
- **Sweep**: Giải phóng bộ nhớ của các đối tượng không còn được tham chiếu.

Ngoài ra, các JVM hiện đại sử dụng nhiều kỹ thuật GC khác nhau, tùy vào nhu cầu và tình trạng bộ nhớ của ứng dụng.

## Bộ nhớ Heap trong Java và GC

Bộ nhớ **Heap** trong Java được chia thành nhiều vùng:
- **Young Generation**: Nơi lưu trữ các đối tượng mới tạo. Khi bộ nhớ trong vùng này đầy, sẽ kích hoạt **Minor GC**.
- **Old Generation**: Lưu trữ các đối tượng sống lâu (đã tồn tại lâu trong Young Generation). **Major GC** sẽ dọn dẹp vùng này khi cần.
- **Permanent Generation (PermGen)** hoặc **Metaspace** (từ Java 8): Chứa các metadata về class, thông tin method.

## Các loại Garbage Collection

Java cung cấp nhiều bộ Garbage Collector khác nhau, tùy thuộc vào hiệu suất yêu cầu:
- **Serial GC**: Dành cho các ứng dụng nhỏ, thực hiện GC trên một luồng đơn.
- **Parallel GC**: Thực hiện GC trên nhiều luồng, tăng tốc độ cho các ứng dụng yêu cầu hiệu suất cao.
- **CMS (Concurrent Mark-Sweep) GC**: Tối ưu cho ứng dụng yêu cầu ít gián đoạn.
- **G1 (Garbage First) GC**: Phù hợp cho ứng dụng lớn, chia vùng Heap thành nhiều vùng nhỏ để quản lý.

## Ví dụ minh họa

```java
public class GarbageCollectorExample {
    public static void main(String[] args) {
        GarbageCollectorExample example = new GarbageCollectorExample();
        example = null; // Đối tượng trở nên không tham chiếu và sẽ bị GC xử lý

        // Gọi hệ thống yêu cầu GC (không đảm bảo sẽ chạy ngay lập tức)
        System.gc();
    }

    @Override
    protected void finalize() {
        System.out.println("Đối tượng đã bị thu gom rác.");
    }
}
```

Trong ví dụ trên, phương thức `System.gc()` gửi yêu cầu đến GC để thu dọn bộ nhớ, tuy nhiên không đảm bảo GC sẽ chạy ngay lập tức. Khi đối tượng `example` bị thu gom, phương thức `finalize` sẽ được gọi trước khi đối tượng bị xóa.

## Những điểm cần lưu ý về GC trong Java

- **Không kiểm soát trực tiếp**: Người lập trình không thể kiểm soát GC trực tiếp mà chỉ có thể yêu cầu.
- **Phương thức `System.gc()`**: Dùng để yêu cầu GC nhưng không đảm bảo nó sẽ thực hiện ngay.
- **Phương thức `finalize()`**: Được gọi trước khi đối tượng bị GC thu dọn, nhưng việc sử dụng nó không được khuyến khích.
- **Hiệu suất**: Lựa chọn loại GC phù hợp có thể cải thiện hiệu suất của ứng dụng đáng kể.
