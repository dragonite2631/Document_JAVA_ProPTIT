# Buổi 7
## Cấu trúc dữ liệu là gì, sử dụng khi nào?

Cấu trúc dữ liệu (Data Structure) là cách tổ chức, lưu trữ và quản lý dữ liệu trong máy tính để dữ liệu có thể được truy cập và sử dụng một cách hiệu quả. Trong Java, cấu trúc dữ liệu được sử dụng để giải quyết các bài toán cụ thể, tối ưu hóa hiệu suất và quản lý dữ liệu một cách có hệ thống.

## **Phân loại cấu trúc dữ liệu**

### a. **Cấu trúc dữ liệu tuyến tính (Linear Data Structures)**
- **Đặc điểm**: Các phần tử được sắp xếp **theo một trình tự tuần tự**.
- **Truy cập**: Mỗi phần tử chỉ có **một phần tử liền trước và một phần tử liền sau** (trừ phần tử đầu và cuối).
- **Ví dụ**:
  | Cấu trúc         | Mô tả                              | Ứng dụng                          |
  |------------------|------------------------------------|-----------------------------------|
  | **Mảng (Array)** | Các phần tử liên tiếp trong bộ nhớ | Lưu trữ dữ liệu có kích thước cố định |
  | **Danh sách liên kết (Linked List)** | Các nút liên kết qua con trỏ | Quản lý bộ nhớ động, undo/redo chức năng |
  | **Ngăn xếp (Stack)** | Nguyên tắc LIFO (Last In First Out) | Xử lý lời gọi hàm, backtracking |
  | **Hàng đợi (Queue)** | Nguyên tắc FIFO (First In First Out) | Lập lịch tác vụ, xử lý yêu cầu |

### b. **Cấu trúc dữ liệu phi tuyến tính (Non-linear Data Structures)**
- **Đặc điểm**: Các phần tử **không sắp xếp tuần tự**, có thể có nhiều mối quan hệ phức tạp.
- **Truy cập**: Phần tử có thể liên kết với nhiều phần tử khác.
- **Ví dụ**:
  | Cấu trúc         | Mô tả                              | Ứng dụng                          |
  |------------------|------------------------------------|-----------------------------------|
  | **Cây (Tree)**   | Cấu trúc phân cấp (ví dụ: cây nhị phân) | Cơ sở dữ liệu, hệ thống file |
  | **Đồ thị (Graph)** | Các nút (đỉnh) và cạnh kết nối    | Mạng xã hội, GPS navigation |
  | **Bảng băm (Hash Table)** | Lưu trữ key-value dùng hàm băm | Từ điển, cache hệ thống |

---

### **So sánh Tuyến tính vs Phi tuyến tính**

| Tiêu chí          | Tuyến tính                          | Phi tuyến tính                    |
|--------------------|-------------------------------------|-----------------------------------|
| **Thứ tự**         | Tuần tự, một chiều                 | Đa chiều, phân nhánh              |
| **Độ phức tạp**    | Dễ triển khai, truy cập nhanh      | Phức tạp, linh hoạt hơn           |
| **Bộ nhớ**         | Tiết kiệm (liên tục)               | Tốn bộ nhớ (liên kết động)        |
| **Ví dụ**          | Array, Stack, Queue                | Tree, Graph, Hash Table           |

---


### Khi nào sử dụng cấu trúc dữ liệu?
Cấu trúc dữ liệu được sử dụng trong các tình huống sau:
- **Lưu trữ dữ liệu**: Khi cần lưu trữ một tập hợp dữ liệu (ví dụ: danh - sách, mảng, tập hợp).
- **Truy cập và tìm kiếm**: Khi cần truy cập hoặc tìm kiếm dữ liệu một cách nhanh chóng (ví dụ: sử dụng bảng băm hoặc cây nhị phân).
- **Sắp xếp dữ liệu**: Khi cần sắp xếp dữ liệu theo một thứ tự cụ thể (ví dụ: sử dụng danh sách liên kết hoặc cấu trúc heap).
- **Quản lý dữ liệu động**: Khi cần thêm, xóa hoặc cập nhật dữ liệu thường xuyên (ví dụ: sử dụng danh sách liên kết hoặc hàng đợi).

### Các cấu trúc dữ liệu phổ biến trong Java
1. **Mảng (Array)**: Lưu trữ dữ liệu trong một khối bộ nhớ liên tục.
2. **Danh sách liên kết (LinkedList)**: Lưu trữ dữ liệu trong các nút riêng biệt, mỗi nút chứa dữ liệu và tham chiếu đến nút tiếp theo.
3. **Ngăn xếp (Stack)**: Cấu trúc dữ liệu hoạt động theo nguyên tắc "Last In, First Out" (LIFO).
4. **Hàng đợi (Queue)**: Cấu trúc dữ liệu hoạt động theo nguyên tắc "First In, First Out" (FIFO).
5. **Bảng băm (HashMap)**: Lưu trữ dữ liệu dưới dạng cặp khóa-giá trị, cho phép truy cập nhanh chóng.
6. **Cây (Tree)**: Cấu trúc dữ liệu phân cấp, thường được sử dụng để tìm kiếm và sắp xếp dữ liệu.


```java
import java.util.*;

public class ViDuCauTrucDuLieu {
    public static void main(String[] args) {
        // Sử dụng ArrayList (một loại danh sách)
        List<String> danhSach = new ArrayList<>();
        danhSach.add("Java");
        danhSach.add("Python");
        danhSach.add("C++");
        System.out.println("Danh sách: " + danhSach);

        // Sử dụng HashMap (bảng băm)
        Map<String, Integer> bangBam = new HashMap<>();
        bangBam.put("Java", 1);
        bangBam.put("Python", 2);
        bangBam.put("C++", 3);
        System.out.println("Bảng băm: " + bangBam);
    }
}
```
```java
Danh sách: [Java, Python, C++]
Bảng băm: {Java=1, Python=2, C++=3}
```
## Các Interface trong Java: Iterable, Collection, List, Set, Queue


Trong Java, **Collections Framework** là một phần quan trọng của thư viện chuẩn, cung cấp các cấu trúc dữ liệu và thuật toán để quản lý và thao tác với các tập hợp dữ liệu. Các interface như `Iterable`, `Collection`, `List`, `Set`, và `Queue` là nền tảng của framework này.

---

## 1. Interface `Iterable`

### Mục đích
- `Iterable` là interface cơ bản nhất, cung cấp khả năng duyệt qua các phần tử của một tập hợp bằng vòng lặp `for-each`.
- Mọi lớp triển khai `Iterable` đều có thể sử dụng trong vòng lặp `for-each`.

### Phương thức chính
- **`iterator()`**: Trả về một đối tượng `Iterator` để duyệt qua các phần tử.
  ```java
  Iterator<T> iterator();
  ```

### 2. Interface `Collection`
- **Mục đích**: Là interface cha của hầu hết các cấu trúc dữ liệu tập hợp trong Java.
- **Kế thừa từ**: `Iterable`.
- **Phương thức chính**:
  - `add(E e)`: Thêm một phần tử vào tập hợp.
  - `remove(Object o)`: Xóa một phần tử khỏi tập hợp.
  - `size()`: Trả về số lượng phần tử trong tập hợp.
  - `isEmpty()`: Kiểm tra xem tập hợp có rỗng không.
  - `contains(Object o)`: Kiểm tra xem tập hợp có chứa phần tử nào không.

### 3. Các Interface con của `Collection`

#### a. `List`
- **Mục đích**: Đại diện cho một danh sách các phần tử có thứ tự, cho phép trùng lặp.
- **Các lớp triển khai phổ biến**: `ArrayList`, `LinkedList`.
- **Phương thức chính**:
  - `get(int index)`: Lấy phần tử tại vị trí chỉ định.
  - `set(int index, E element)`: Thay thế phần tử tại vị trí chỉ định.
  - `indexOf(Object o)`: Trả về chỉ số của phần tử đầu tiên được tìm thấy.

#### b. `Set`
- **Mục đích**: Đại diện cho một tập hợp các phần tử không có thứ tự và không cho phép trùng lặp.
- **Các lớp triển khai phổ biến**: `HashSet`, `TreeSet`.
- **Phương thức chính**:
  - `add(E e)`: Thêm một phần tử vào tập hợp (nếu chưa tồn tại).
  - `contains(Object o)`: Kiểm tra xem tập hợp có chứa phần tử nào không.

#### c. `Queue`
- **Mục đích**: Đại diện cho một hàng đợi, thường tuân theo nguyên tắc **FIFO** (First In, First Out).
- **Các lớp triển khai phổ biến**: `LinkedList`, `PriorityQueue`.
- **Phương thức chính**:
  - `offer(E e)`: Thêm một phần tử vào hàng đợi.
  - `poll()`: Lấy và xóa phần tử đầu tiên trong hàng đợi.
  - `peek()`: Lấy phần tử đầu tiên trong hàng đợi mà không xóa.


## Ví dụ
```java
import java.util.*;

public class InterfaceExample {
    public static void main(String[] args) {
        // Ví dụ về List
        List<String> danhSach = new ArrayList<>();
        danhSach.add("Java");
        danhSach.add("Python");
        danhSach.add("C++");
        System.out.println("Danh sách: " + danhSach);

        // Ví dụ về Set
        Set<String> tapHop = new HashSet<>();
        tapHop.add("Java");
        tapHop.add("Python");
        tapHop.add("Java"); // Phần tử trùng lặp sẽ không được thêm
        System.out.println("Tập hợp: " + tapHop);

        // Ví dụ về Queue
        Queue<String> hangDoi = new LinkedList<>();
        hangDoi.offer("Java");
        hangDoi.offer("Python");
        hangDoi.offer("C++");
        System.out.println("Hàng đợi: " + hangDoi);
        System.out.println("Phần tử đầu tiên: " + hangDoi.peek());
        System.out.println("Lấy và xóa phần tử đầu tiên: " + hangDoi.poll());
        System.out.println("Hàng đợi sau khi poll: " + hangDoi);
    }
}
```
```java
ArrayList: [Java, Python]
HashSet: [Java, Python]
PriorityQueue: [Java, Python]
ArrayDeque: [Java, Python]
```
## Cấu trúc dữ liệu trong Java: Set và Map

### Set

- **Set** là một cấu trúc dữ liệu đại diện cho một tập hợp các phần tử **không có thứ tự** và **không cho phép trùng lặp**.
- Set thường được sử dụng khi cần lưu trữ các phần tử duy nhất và không quan tâm đến thứ tự của chúng.

### Đặc điểm
- **Không cho phép trùng lặp**: Mỗi phần tử trong Set là duy nhất.
- **Không có thứ tự**: Các phần tử không được sắp xếp theo bất kỳ thứ tự cụ thể nào (trừ một số triển khai như `TreeSet`).
- **Cho phép phần tử `null`**: Một số triển khai của Set cho phép chứa phần tử `null`.

### Các lớp triển khai phổ biến
- **`HashSet`**:
  - Dựa trên bảng băm (hash table).
  - Truy cập và thêm phần tử với độ phức tạp trung bình là O(1).
  - Không đảm bảo thứ tự các phần tử.
- **`TreeSet`**:
  - Dựa trên cây đỏ-đen (Red-Black Tree).
  - Các phần tử được sắp xếp theo thứ tự tự nhiên hoặc theo một bộ so sánh (Comparator).
  - Truy cập và thêm phần tử với độ phức tạp O(log n).
- **`LinkedHashSet`**:
  - Kết hợp giữa `HashSet` và `LinkedList`.
  - Duy trì thứ tự chèn của các phần tử.

### Ví dụ 
```java
import java.util.*;

public class SetExample {
    public static void main(String[] args) {
        // Sử dụng HashSet
        Set<String> hashSet = new HashSet<>();
        hashSet.add("Java");
        hashSet.add("Python");
        hashSet.add("C++");
        hashSet.add("Java"); // Phần tử trùng lặp sẽ không được thêm
        System.out.println("HashSet: " + hashSet);

        // Sử dụng TreeSet
        Set<String> treeSet = new TreeSet<>();
        treeSet.add("Java");
        treeSet.add("Python");
        treeSet.add("C++");
        System.out.println("TreeSet: " + treeSet);

        // Sử dụng LinkedHashSet
        Set<String> linkedHashSet = new LinkedHashSet<>();
        linkedHashSet.add("Java");
        linkedHashSet.add("Python");
        linkedHashSet.add("C++");
        System.out.println("LinkedHashSet: " + linkedHashSet);
    }
}
```
```java
HashSet: [Java, Python, C++]
TreeSet: [C++, Java, Python]
LinkedHashSet: [Java, Python, C++]
```
# Cấu trúc dữ liệu trong Java: Map

## Định nghĩa
- **Map** là một cấu trúc dữ liệu lưu trữ các cặp **khóa-giá trị** (key-value pairs).
- Mỗi khóa trong Map là duy nhất, và mỗi khóa ánh xạ đến một giá trị tương ứng.
- Map thường được sử dụng khi cần truy cập dữ liệu thông qua khóa một cách nhanh chóng.

## Đặc điểm
- **Khóa là duy nhất**: Mỗi khóa trong Map chỉ xuất hiện một lần.
- **Cho phép giá trị `null`**: Một số triển khai của Map cho phép khóa hoặc giá trị là `null`.
- **Không có thứ tự**: Các cặp khóa-giá trị không được sắp xếp theo bất kỳ thứ tự cụ thể nào (trừ một số triển khai như `TreeMap`).

## Các lớp triển khai phổ biến
- **`HashMap`**:
  - Dựa trên bảng băm (hash table).
  - Truy cập và thêm phần tử với độ phức tạp trung bình là O(1).
  - Không đảm bảo thứ tự các cặp khóa-giá trị.
- **`TreeMap`**:
  - Dựa trên cây đỏ-đen (Red-Black Tree).
  - Các cặp khóa-giá trị được sắp xếp theo thứ tự tự nhiên của khóa hoặc theo một bộ so sánh (Comparator).
  - Truy cập và thêm phần tử với độ phức tạp O(log n).
- **`LinkedHashMap`**:
  - Kết hợp giữa `HashMap` và `LinkedList`.
  - Duy trì thứ tự chèn của các cặp khóa-giá trị.

## Ví dụ mã
```java
import java.util.*;

public class MapExample {
    public static void main(String[] args) {
        // Sử dụng HashMap
        Map<String, Integer> hashMap = new HashMap<>();
        hashMap.put("Java", 1);
        hashMap.put("Python", 2);
        hashMap.put("C++", 3);
        System.out.println("HashMap: " + hashMap);

        // Sử dụng TreeMap
        Map<String, Integer> treeMap = new TreeMap<>();
        treeMap.put("Java", 1);
        treeMap.put("Python", 2);
        treeMap.put("C++", 3);
        System.out.println("TreeMap: " + treeMap);

        // Sử dụng LinkedHashMap
        Map<String, Integer> linkedHashMap = new LinkedHashMap<>();
        linkedHashMap.put("Java", 1);
        linkedHashMap.put("Python", 2);
        linkedHashMap.put("C++", 3);
        System.out.println("LinkedHashMap: " + linkedHashMap);
    }
}
```
```java
HashMap: {Java=1, Python=2, C++=3}
TreeMap: {C++=3, Java=1, Python=2}
LinkedHashMap: {Java=1, Python=2, C++=3}
```
### So sánh các triển khai của Map

| Đặc điểm               | HashMap                            | TreeMap                            | LinkedHashMap                      |
|------------------------|------------------------------------|------------------------------------|------------------------------------|
| **Thứ tự**             | Không có thứ tự                   | Sắp xếp theo khóa                 | Duy trì thứ tự chèn               |
| **Độ phức tạp truy cập**| O(1) (trung bình)                 | O(log n)                          | O(1) (trung bình)                 |
| **Cho phép `null`**    | Khóa và giá trị đều có thể là `null` | Khóa không thể là `null`, giá trị có thể là `null` | Khóa và giá trị đều có thể là `null` |
## Sơ đồ kế thừa của các cấu trúc dữ liệu trong Java

![alt](java-collection-hierarchy.png)


## Tại sao Java có nhiều lớp Collection? Cách chọn lớp phù hợp

### 1. **Đa dạng nhu cầu sử dụng**
- Java Collections Framework được thiết kế để đáp ứng các yêu cầu khác nhau:
  - **Thứ tự dữ liệu**: Danh sách có thứ tự (`List`) vs. tập hợp không thứ tự (`Set`).
  - **Tính duy nhất**: Cho phép trùng lặp (`List`) vs. không trùng lặp (`Set`).
  - **Cấu trúc dữ liệu đặc biệt**: Hàng đợi (`Queue`), ngăn xếp (`Stack`), ánh xạ (`Map`).

### 2. **Tối ưu hiệu suất**
- Mỗi lớp Collection được tối ưu cho các thao tác cụ thể:
  - **Truy cập ngẫu nhiên**: `ArrayList` (O(1)) tốt hơn `LinkedList` (O(n)).
  - **Chèn/Xóa**: `LinkedList` (O(1)) tốt hơn `ArrayList` (O(n)).
  - **Tìm kiếm**: `HashSet`/`HashMap` (O(1)) nhanh hơn `TreeSet`/`TreeMap` (O(log n)).

### 3. **Linh hoạt trong triển khai**
- Các lớp triển khai khác nhau phù hợp với các **kịch bản khác nhau**:
  - `Vector` vs. `ArrayList`: `Vector` đồng bộ hóa (thread-safe), `ArrayList` không đồng bộ.
  - `HashMap` vs. `LinkedHashMap`: `LinkedHashMap` duy trì thứ tự chèn.

---

## Cách chọn lớp Collection phù hợp

### 1. **Xác định yêu cầu cơ bản**
| Yêu cầu                     | Lựa chọn phù hợp               |
|-----------------------------|---------------------------------|
| **Cần thứ tự**              | `List` (`ArrayList`, `LinkedList`) |
| **Không trùng lặp**         | `Set` (`HashSet`, `TreeSet`)    |
| **Cặp khóa-giá trị**        | `Map` (`HashMap`, `TreeMap`)    |
| **Hàng đợi/Stack**          | `Queue`/`Deque` (`LinkedList`, `PriorityQueue`) |

### 2. **Phân tích hiệu suất**
| Thao tác               | Lớp hiệu quả                  | Độ phức tạp       |
|------------------------|-------------------------------|-------------------|
| **Truy cập ngẫu nhiên**| `ArrayList`                   | O(1)             |
| **Chèn/Xóa thường xuyên** | `LinkedList`                | O(1)             |
| **Tìm kiếm nhanh**     | `HashSet`/`HashMap`           | O(1)             |
| **Duyệt có thứ tự**    | `LinkedHashSet`/`LinkedHashMap` | O(1)             |

### 3. **Xử lý đa luồng (Multi-threading)**
| Yêu cầu                     | Lựa chọn phù hợp               |
|-----------------------------|---------------------------------|
| **Thread-safe**             | `ConcurrentHashMap`, `CopyOnWriteArrayList`, `Vector` |
| **Không cần thread-safe**   | `ArrayList`, `HashSet`, `HashMap` |

### 4. **Các trường hợp đặc biệt**
| Yêu cầu                  | Lựa chọn tối ưu               |
|----------------------------|-------------------------------|
| **Cần sắp xếp tự nhiên**   | `TreeSet`/`TreeMap`           |
| **Duy trì thứ tự chèn**    | `LinkedHashSet`/`LinkedHashMap` |
| **Hàng đợi ưu tiên**       | `PriorityQueue`               |
| **Lưu trữ key-value lịch sử** | `LinkedHashMap` với `accessOrder=true` |

## Comparable và Comparator trong Java: Cách sử dụng để sắp xếp

### 1. **Comparable**
- **Comparable** là một interface được sử dụng để định nghĩa **thứ tự tự nhiên** (natural ordering) của các đối tượng.
- Lớp triển khai `Comparable` phải override phương thức `compareTo()`.

### Cách sử dụng
- **Bước 1**: Implement `Comparable` trong lớp cần sắp xếp.
- **Bước 2**: Override phương thức `compareTo()` để định nghĩa logic so sánh.

### Ví dụ
```java
public class Student implements Comparable<Student> {
    private String name;
    private int grade;

    public Student(String name, int grade) {
        this.name = name;
        this.grade = grade;
    }

    @Override
    public int compareTo(Student other) {
        // Sắp xếp theo tên (thứ tự từ điển)
        return this.name.compareTo(other.name);
    }

    @Override
    public String toString() {
        return name + " (" + grade + ")";
    }
}

// Sử dụng
List<Student> students = new ArrayList<>();
students.add(new Student("Alice", 90));
students.add(new Student("Bob", 85));
Collections.sort(students); // Sắp xếp tự động dùng compareTo()
System.out.println(students); // [Alice (90), Bob (85)]
```
# Comparator trong Java: Cách sử dụng để sắp xếp

## 1. **Định nghĩa**
- **Comparator** là một interface thuộc gói `java.util`, dùng để định nghĩa **thứ tự tùy chỉnh** (custom ordering) cho các đối tượng.
- Cho phép sắp xếp dữ liệu theo nhiều tiêu chí khác nhau mà không cần thay đổi lớp gốc.

## 2. **Cách sử dụng**
### a. Triển khai Comparator
Có 2 cách phổ biến:
1. **Tạo lớp riêng triển khai Comparator**.
2. **Sử dụng anonymous class hoặc lambda (Java 8+)**.

### b. Phương thức chính
- **`compare(T o1, T o2)`**: So sánh hai đối tượng.
  - Trả về **số âm** nếu `o1 < o2`.
  - Trả về **0** nếu `o1 = o2`.
  - Trả về **số dương** nếu `o1 > o2`.

---

## 3. **Ví dụ chi tiết**

### Ví dụ 1: Sắp xếp theo tuổi (dùng anonymous class)
```java
import java.util.*;

class Person {
    String name;
    int age;
    
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    public int getAge() { return age; }
}

public class ComparatorExample {
    public static void main(String[] args) {
        List<Person> people = Arrays.asList(
            new Person("Alice", 30),
            new Person("Bob", 25)
        );

        // Sử dụng anonymous class
        Comparator<Person> ageComparator = new Comparator<Person>() {
            @Override
            public int compare(Person p1, Person p2) {
                return p1.getAge() - p2.getAge();
            }
        };

        Collections.sort(people, ageComparator);
        System.out.println(people); 
        // Output: [Bob (25), Alice (30)]
    }
    
}
```

### Ví dụ 2: Sắp xếp theo tên (dùng lambda - Java 8+)
```java
// Sử dụng lambda
Comparator<Person> nameComparator = (p1, p2) -> 
    p1.name.compareTo(p2.name);

Collections.sort(people, nameComparator);
System.out.println(people); 
// Output: [Alice (30), Bob (25)]
```
### Comparator với phương thức tham chiếu
```java
// Sắp xếp theo tuổi
Comparator<Person> ageComp = Comparator.comparing(Person::getAge);

// Sắp xếp theo tên giảm dần
Comparator<Person> nameComp = Comparator.comparing(Person::getName).reversed();
```
## So sánh Comparator và Comparable

| Tiêu chí          | Comparator                          | Comparable                          |
|--------------------|-------------------------------------|-------------------------------------|
| **Gói**            | `java.util.Comparator`              | `java.lang.Comparable`              |
| **Phương thức**    | `compare(T o1, T o2)`               | `compareTo(T o)`                    |
| **Thay đổi lớp**   | Không cần                           | Cần implement trong lớp             |
| **Số cách sắp xếp**| Nhiều (tạo nhiều Comparator)        | Một (thứ tự mặc định)               |
| **Ưu điểm**        | Linh hoạt, không ảnh hưởng lớp gốc  | Định nghĩa thứ tự mặc định          |