

# 1. Version Control là gì?
Version Control (Hệ thống quản lý phiên bản) là một hệ thống giúp theo dõi và quản lý các thay đổi đối với mã nguồn, tài liệu, hoặc bất kỳ loại tệp nào trong suốt quá trình phát triển. Nó cho phép người dùng lưu lại lịch sử thay đổi của từng phiên bản, giúp dễ dàng kiểm tra và khôi phục lại những phiên bản trước nếu cần.

Trong quá trình phát triển phần mềm, việc thay đổi và cập nhật mã nguồn là điều không thể tránh khỏi. Hệ thống Version Control giúp lưu trữ thông tin về các thay đổi, như ai đã thay đổi gì, thay đổi khi nào, và nội dung thay đổi ra sao.

Version Control mang lại nhiều lợi ích cho quá trình phát triển phần mềm, bao gồm:

### Theo dõi thay đổi
- Với Version Control, mỗi thay đổi của mã nguồn được ghi lại cùng với thông tin về người thực hiện, thời gian, và lý do thay đổi.
- Điều này giúp các lập trình viên dễ dàng xem lại lịch sử thay đổi, giúp trong việc hiểu mã nguồn và phát hiện lỗi.

### Khả năng làm việc nhóm hiệu quả
- Version Control cho phép nhiều người làm việc trên cùng một dự án mà không gây xung đột.
- Mỗi thành viên có thể làm việc trên các tính năng riêng biệt, và sau đó hợp nhất chúng lại với nhau.

### Khôi phục mã nguồn
- Trong trường hợp xảy ra lỗi hoặc cần quay lại phiên bản trước, Version Control giúp khôi phục lại các phiên bản trước một cách dễ dàng.
- Điều này đặc biệt hữu ích khi gặp các lỗi nghiêm trọng hoặc phát hiện vấn đề sau khi đã cập nhật mã.

### Hỗ trợ phân nhánh và phát triển song song
- Hầu hết các hệ thống Version Control hiện đại như Git hỗ trợ tạo nhánh (branch), giúp lập trình viên phát triển các tính năng hoặc sửa lỗi độc lập trước khi hợp nhất vào phiên bản chính.
- Điều này làm tăng tính linh hoạt và giúp duy trì mã nguồn ổn định.

### Một số hệ thống Version Control phổ biến
Các hệ thống Version Control phổ biến bao gồm:
- **Git**: Một trong những hệ thống Version Control phân tán nổi tiếng nhất, thường được sử dụng với GitHub, GitLab.
- **SVN (Subversion)**: Hệ thống Version Control tập trung, phù hợp cho các dự án đơn giản.
- **Mercurial**: Hệ thống quản lý phiên bản phân tán tương tự như Git, nhưng có giao diện và cách thức hoạt động khác.

![alt](git.webp)
# 2. Các khái niệm về Git

**Repository** (hay repo) là một thư mục chứa toàn bộ mã nguồn và lịch sử thay đổi của một dự án. Một repository có thể tồn tại trên máy tính cá nhân hoặc trên một dịch vụ lưu trữ như GitHub, GitLab.

 ```bash
  # Khởi tạo repository mới
  git init

  # Sao chép một repository từ xa về máy tính
  git clone <repository-url>
```

**Branch** là nhánh trong repository. Branch giúp tạo ra một dòng phát triển mới mà không ảnh hưởng đến dòng chính (thường là nhánh `main` hoặc `master`). Mỗi branch có thể được sử dụng cho các tính năng hoặc bản sửa lỗi riêng biệt.

```bash
# Tạo một nhánh mới
git branch <branch-name>

# Chuyển sang một nhánh khác
git checkout <branch-name>

# Tạo và chuyển sang nhánh mới
git checkout -b <branch-name>
```

**Commit** là hành động lưu lại thay đổi trong repository. Mỗi commit được coi là một phiên bản của mã nguồn tại thời điểm commit. Mỗi commit có một mã định danh duy nhất và chứa thông tin về thay đổi cũng như tác giả.

```bash
# Thêm các thay đổi vào staging area
git add <file-name>

# Tạo một commit với thông điệp
git commit -m "Thông điệp miêu tả thay đổi"
```

**Merge** là quá trình hợp nhất các thay đổi từ một nhánh vào nhánh khác. Khi merge, các thay đổi trên nhánh phụ sẽ được gộp vào nhánh chính hoặc một nhánh khác.

```bash
# Gộp nhánh vào nhánh hiện tại
git merge <branch-name>
```

**Rebase** là quá trình chuyển các commit từ nhánh này sang một nhánh khác để tạo ra lịch sử commit gọn gàng hơn. Rebase thường được sử dụng để "làm sạch" lịch sử commit khi hợp nhất các nhánh.

```bash
# Rebase nhánh hiện tại vào nhánh khác
git rebase <branch-name>
```

**Gộp commit** là quá trình kết hợp nhiều commit lại thành một commit duy nhất. Điều này giúp lịch sử commit rõ ràng và ngắn gọn hơn.

```bash
# Thực hiện squash commit khi rebase
git rebase -i HEAD~<number-of-commits>
```

**Pull** là quá trình lấy các thay đổi từ repository từ xa (remote) về repository cục bộ (local) và hợp nhất chúng. Pull bao gồm cả hai bước fetch (lấy về) và merge.

```bash
git pull <remote> <branch>
```

**Push** là quá trình đưa các commit từ repository cục bộ lên repository từ xa. Đây là bước cuối cùng sau khi thực hiện các thay đổi cục bộ.

```bash
git push <remote> <branch>
```

**Clone** là quá trình sao chép một repository từ xa về máy tính cá nhân. Clone giúp có một bản sao đầy đủ của repository để làm việc trên máy cục bộ.

```bash
git clone <repository-url>
```

**Fork** là quá trình sao chép một repository từ xa sang tài khoản cá nhân trên nền tảng như GitHub. Fork thường được dùng khi muốn đóng góp vào dự án mã nguồn mở.

**Pull Request** (PR) là một yêu cầu hợp nhất các thay đổi từ nhánh của người phát triển vào nhánh chính của dự án. Pull Request thường được dùng trong môi trường cộng tác để xem xét mã nguồn trước khi hợp nhất.

**Gitignore** là một tệp trong repository để chỉ định các tệp hoặc thư mục mà  muốn Git bỏ qua, không theo dõi. Thông thường, các tệp cấu hình cá nhân hoặc tệp biên dịch sẽ được liệt kê trong `.gitignore`.

# 3. Khi nào cần Pull Request? Cách tạo Pull Request

Pull Request (PR) thường được sử dụng trong các dự án phát triển phần mềm để quản lý các thay đổi mã nguồn một cách hiệu quả. Nên tạo Pull Request trong các trường hợp sau:

- **Khi hoàn thành một tính năng mới**: Sau khi  đã hoàn thành một tính năng mới,  nên tạo một Pull Request để các thành viên khác có thể xem xét mã và tích hợp vào nhánh chính (main branch) của dự án.
- **Khi sửa lỗi**: Khi sửa lỗi trong mã nguồn, việc tạo một Pull Request cho phép các thành viên khác xem xét và đảm bảo rằng việc sửa lỗi không ảnh hưởng đến các phần khác của mã.
- **Khi cần sự đánh giá từ nhóm**: Pull Request cung cấp một cơ chế để các thành viên trong nhóm đánh giá mã, đưa ra góp ý, hoặc chỉ ra các lỗi có thể gặp phải.
- **Khi tích hợp mã từ nhánh phụ**: Để đưa mã từ nhánh phụ (feature branch) vào nhánh chính, Pull Request giúp theo dõi và kiểm soát quá trình tích hợp này, đảm bảo sự nhất quán và không phá vỡ các tính năng hiện có.

### Cách tạo pull request

#### Bước 1: Đẩy mã lên Remote Repository
Đầu tiên cần đẩy các thay đổi từ nhánh local lên repository trên GitHub
#### Bước 2: Truy cập Repository trên GitHub
- Mở trình duyệt và truy cập vào repository của bạn trên GitHub.
- Chọn nhánh mà bạn vừa đẩy mã lên.
#### Bước 3: Tạo Pull Request
- Ở phần "Pull Requests" trên GitHub, chọn New Pull Request.
- Chọn nhánh mà bạn muốn merge mã vào (thường là main hoặc develop) và nhánh chứa các thay đổi của bạn.
- Viết tiêu đề và mô tả cho Pull Request, nêu rõ những thay đổi bạn đã thực hiện.
#### Bước 4: Gửi Pull Request
- Nhấn Create Pull Request để gửi Pull Request cho nhóm.
- Sau khi tạo, bạn có thể thêm các Reviewer, Assignee hoặc Labels để giúp nhóm quản lý Pull Request dễ dàng hơn.
#### Bước 5: Đánh giá và Merge Pull Request
- Thành viên trong nhóm sẽ kiểm tra Pull Request, đưa ra nhận xét nếu có, và xác nhận rằng mã có thể được tích hợp.
- Sau khi mã đã được đánh giá, bạn hoặc người có quyền sẽ nhấn Merge để tích hợp các thay đổi vào nhánh chính.
# 4. Resolve Conflict khi merge pull request
## Tại sao lại xảy ra Conflict khi Merge Pull Request?
Conflict (xung đột) xảy ra khi Git không thể tự động hợp nhất các thay đổi từ một nhánh vào nhánh khác do các thay đổi xung đột với nhau. Điều này thường xảy ra trong các trường hợp sau:

- **Chỉnh sửa cùng một dòng hoặc cùng một đoạn mã**: Khi hai nhánh có các thay đổi trên cùng một dòng hoặc cùng một đoạn mã, Git không thể xác định được thay đổi nào cần được giữ lại.
- **Xóa hoặc sửa đổi các tệp giống nhau**: Khi một nhánh xoá hoặc sửa một tệp mà nhánh khác cũng thực hiện hành động tương tự, xung đột có thể xảy ra.
- **Cấu trúc thư mục bị thay đổi**: Khi hai nhánh có thay đổi về cấu trúc thư mục hoặc tên tệp giống nhau, Git cũng có thể gặp khó khăn trong việc xử lý.

## Các bước Resolve Conflict khi Merge Pull Request
Khi xảy ra conflict, bạn cần giải quyết nó trước khi Pull Request có thể được hợp nhất. Các bước dưới đây hướng dẫn cách xử lý conflict:

### Bước 1: Xem các file bị conflict
- Khi có conflict, Git sẽ thông báo các file bị ảnh hưởng. Bạn có thể xem danh sách các file này bằng lệnh:

```bash
git status
```
### Bước 2: Mở file để giải quyết conflict
Mở các file bị conflict trong editor. Git sẽ đánh dấu các vùng bị conflict bằng ký hiệu <<<<<<<, =======, và >>>>>>>.
```java
public void exampleMethod() {
<<<<<<< HEAD
    System.out.println("This is from the main branch");
=======
    System.out.println("This is from the feature branch");
>>>>>>> feature-branch
}
```
### Bước 3: Giải quyết conflict
Chọn phần mã bạn muốn giữ lại hoặc chỉnh sửa lại mã sao cho phù hợp. Sau đó, xóa các ký hiệu <<<<<<<, =======, và >>>>>>>.
```java
public void exampleMethod() {
    System.out.println("This is the resolved code");
}
```
### Bước 4: Đánh dấu conflict đã được giải quyết
Sau khi chỉnh sửa, bạn cần đánh dấu các file đã được giải quyết conflict bằng lệnh:
```bash
git add <ten-file>
```
### Bước 5: Commit thay đổi
Tạo một commit để lưu lại quá trình giải quyết conflict
```bash
git commit -m "Resolve merge conflict in <ten-file>"
```
### Bước 6: Đẩy thay đổi lên Remote Repository
Đẩy các thay đổi đã giải quyết lên repository từ nhánh chứa Pull Request
```bash
git push
```
## Các công cụ hỗ trợ Resolve Conflict

- Visual Studio Code: VS Code sẽ đánh dấu các conflict trong mã và cung cấp các nút để chọn một trong các thay đổi hoặc giữ cả hai.
- GitHub Web Interface: GitHub cũng cho phép bạn giải quyết conflict trực tiếp trên giao diện web khi bạn mở Pull Request.
- Sourcetree hoặc GitKraken: Đây là các công cụ giao diện đồ họa giúp bạn dễ dàng xem và giải quyết các conflict.

# UML là gì?

## 1. Khái niệm về UML
UML (Unified Modeling Language) là ngôn ngữ mô hình hóa chuẩn trong phát triển phần mềm, được sử dụng để trực quan hóa, đặc tả, xây dựng, và lập tài liệu các hệ thống phần mềm phức tạp. UML hỗ trợ nhiều loại biểu đồ khác nhau, giúp mô tả các khía cạnh khác nhau của một hệ thống, từ cấu trúc cho đến hành vi.

- **Ngôn ngữ chuẩn**: UML là một ngôn ngữ tiêu chuẩn, được tổ chức OMG (Object Management Group) phát triển và duy trì.
- **Trực quan hóa hệ thống**: UML cung cấp các công cụ để các lập trình viên, kiến trúc sư và các nhà phân tích phần mềm hình dung được cấu trúc và hành vi của hệ thống trước khi bắt tay vào phát triển.


![alt](UML.webp)


## 2. Mô hình Class Diagram

### Khái niệm
Class Diagram (biểu đồ lớp) là một trong những loại biểu đồ cấu trúc phổ biến nhất trong UML. Class Diagram mô tả các lớp, thuộc tính, phương thức và mối quan hệ giữa các lớp trong hệ thống, giúp hiểu rõ hơn về cấu trúc của hệ thống phần mềm.

### Các thành phần chính
- **Class (Lớp)**: Được biểu diễn dưới dạng hình chữ nhật, chứa tên lớp, thuộc tính, và phương thức của lớp đó.
- **Attributes (Thuộc tính)**: Đặc điểm của một lớp, tương ứng với biến trong lớp.
- **Methods (Phương thức)**: Các hành vi của một lớp, tương ứng với các hàm trong lớp.
- **Relationships (Quan hệ)**: Biểu diễn mối quan hệ giữa các lớp, bao gồm:
  - **Association**: Quan hệ kết hợp giữa các lớp.
  - **Inheritance**: Quan hệ kế thừa giữa các lớp.
  - **Aggregation** và **Composition**: Quan hệ giữa toàn bộ và các thành phần.

![alt](class_diagram.webp)
## 3. Mô hình Activity Diagram

### Khái niệm
Activity Diagram (biểu đồ hoạt động) là loại biểu đồ dùng để mô tả dòng công việc hoặc các hành động của hệ thống. Nó thể hiện các bước cần thực hiện để hoàn thành một nhiệm vụ hoặc một quá trình trong hệ thống, giúp hình dung rõ hơn về dòng chảy của các hoạt động.

### Các thành phần chính
- **Start Node (Nút bắt đầu)**: Điểm khởi đầu của biểu đồ hoạt động.
- **Action (Hành động)**: Biểu diễn một hành động hoặc một bước trong quá trình.
- **Decision Node (Nút quyết định)**: Biểu diễn các nhánh hoặc điều kiện dẫn đến các hành động khác nhau.
- **Merge Node (Nút gộp)**: Kết hợp lại các luồng hành động sau một nút quyết định.
- **End Node (Nút kết thúc)**: Điểm kết thúc của biểu đồ.

![alt](class_diagram.webp)

## 4. Lí do cần vẽ UML

Vẽ UML giúp ích rất nhiều trong việc phát triển và duy trì phần mềm:

- **Giúp truyền tải ý tưởng**: UML giúp các thành viên trong nhóm hiểu rõ về cấu trúc và luồng hoạt động của hệ thống, giúp cho việc truyền tải ý tưởng và yêu cầu dễ dàng hơn.
- **Hỗ trợ thiết kế hệ thống**: UML cung cấp công cụ để mô hình hóa hệ thống một cách chi tiết, giúp cho việc thiết kế hệ thống trở nên rõ ràng và nhất quán.
- **Hỗ trợ bảo trì và mở rộng**: Khi hệ thống phức tạp dần lên, UML giúp dễ dàng theo dõi cấu trúc và hành vi của hệ thống, từ đó hỗ trợ tốt cho công việc bảo trì và mở rộng.
- **Tiêu chuẩn hóa**: UML là ngôn ngữ tiêu chuẩn quốc tế, giúp đảm bảo rằng các mô hình có thể được hiểu và sử dụng trên toàn cầu, bất kể vị trí địa lý hay ngôn ngữ.