# RECOMMENDER-SYSTEM
## CHƯƠNG 1: GIỚI THIỆU VỀ RECOMMENDER SYSTEM
### 1 Giới thiệu hệ thống
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp; Hệ thống tư vấn (Recommender Systems) - là một thành phần trong hệ thống thông tin. Mục đích của nó là hỗ trợ người dùng tìm kiếm được đúng thông tin cần thiết.
  
### 2 Các phương pháp thường dùng
#### 2.1 Phương pháp lọc dựa trên nội dung (Content-based filter)
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Phương pháp lọc dựa trên nội dung là một giải thuật nghiên cứu về lọc thông tin, phương pháp lọc dựa trên nội dung ước lượng hàm đánh giá R(u,i) của item i với user u được thiết lập dựa trên cơ sở đánh giá R(u,i’) của cùng user u cho item i’ mà trong đó i và i’ là tương tự nhau về mặt nội dung.
  
  
#### 2.2 Phương pháp lọc cộng tác (Collaboration filter)
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Phương pháp lọc cộng tác là phương pháp tập hợp các đánh giá hoặc các quan điểm của khách hàng, nhận dạng sự tương đồng giữa các khách hàng trên cơ sở các đánh giá hoặc quan điểm của họ và phát sinh ra những tư vấn mới cho khách hàng.
Bản chất của phương pháp này chính là hình thức tư vấn truyền miệng tự động. Trong phương pháp này, hệ thống sẽ so sánh, tính toán độ tương tự nhau giữa những người dùng hay sản phẩm, từ đó người dùng sẽ được tư vấn những thông tin, sản phẩm được ưa chuộng nhất bởi những người dùng có cùng thị hiếu. Trong phương pháp này, hệ thống thường xây dựng các ma trận đánh giá bởi người dùng lên các sản phẩm, bản tin, từ đó tính toán độ tương tự giữa họ.
Các hệ tư vấn dựa trên lọc cộng tác không yêu cầu quá nặng vào việc tính toán, do đó nó có thể đưa ra những tư vấn có độ chính xác cao và nhanh chóng cho một số lượng lớn người dùng. Hơn nữa, hệ tư vấn này không yêu cầu mô tả nội dung tưởng mình mà chỉ sử dụng đánh giá của người dùng để ước lượng, do đó những hệ này có khả năng tư vấn phong phú và thường tạo ra những tư vấn bất ngờ cho người dùng.
Phương pháp lọc cộng tác có các vấn đề như:
•	Sự thưa thớt
•	Vấn đề sản phẩm mới
•	Vấn đề khách hàng mới

  
  
## CHƯƠNG 2: CÁC THÀNH PHẦN CỦA MỘT HỆ GỢI Ý
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Hệ gợi ý rất quen thuộc và gần gũi, vậy để xây dựng được một hệ gợi ý, chúng ta cần có:
    
### 1 Dữ liệu
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Đầu tiên chúng ta cần có dữ liệu về users, items, feedback
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Trong đó
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	users là danh sách người dùng
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	items là danh sách sản phẩm, đối tượng của hệ thống. Ví dụ như các bài viết trên trang viblo, các video trên youtube,… Và mỗi item có thể kèm theo thông tin mô tả.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	feedback là lịch sử tương tác của user với mỗi item, có thể là đánh giá của mỗi user với một item, số ratings, hoặc comment, việc user click, view hoặc mua sản phẩm,…

### 2 Ma trận user-item: Utility matrix
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/106374874-92ec6e80-63b9-11eb-92eb-405234070018.png" width="50%"/>
  
### 3 Phương pháp 

#### 3.1 Content-based Filtering: 

#### 3.2 Collaborative Filtering: 

## CHƯƠNG 3: PHƯƠNG PHÁP GỢI Ý DỰA THEO NỘI DUNG (CONTENT-BASED FILTERING)
### 1 Ý tưởng 

### 2 Xây dựng Items Profile

### 3 Học mô hình biểu diễn của user

## TÀI LIỆU THAM KHẢO
