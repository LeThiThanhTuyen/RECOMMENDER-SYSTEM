# RECOMMENDER-SYSTEM
## CHƯƠNG 1: BÀI TOÁN
### 1 Bài toán, input, output
#### Bài toán
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp; Hàng năm có vô vàn các bộ phim được phát hành, chính vì vậy mà khách hàng cũng có vô vàn sự lựa chọn khác nhau. Do đó để có thể thu hút được người xem cần có những công cụ đề xuất phim cho người xem.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp; Giữa người xem và phim có sự phụ thuộc chặt chẽ với nhau, ví dụ: một người xem quan tâm đến một bộ phim tài liệu lịch sử có nhiều khả năng quan tâm đến một tài liệu lịch sử khác hoặc một chương trình giáo dục, thay vì trong một bộ phim hành động. Trong nhiều trường hợp, các danh mục phim khác nhau có thể hiển thị các mối tương quan đáng kể, có thể được tận dụng để tạo ra khuyến nghị chính xác hơn. Một hệ thống đề xuất phim quan trọng ở sức mạnh của nó trong việc cung cấp giải trí và trải nghiệm người dùng được cá nhân hóa. Như một hệ thống có thể đề xuất một bộ phim cho người dùng dựa trên sự quan tâm hoặc mức độ phổ biến của các bộ phim.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp; Các công ty đang chi hàng triệu đô để xây dựng mô hình đề xuất chính xác vì đây là một mô hình được cá nhân hóa chiến dịch hướng đến khách hàng mục tiêu. Giải thưởng Netflix, một cuộc thi mở cho thuật toán lọc cộng tác tốt nhất để dự đoán người dùng xếp hạng cho phim, dựa trên xếp hạng trước đó mà không có bất kỳ thông tin nào khác về người dùng hoặc phim. Cuộc thi đã được tổ chức bởi Netflix vào năm 2006 và diễn ra trong gần 3 năm và giải thưởng lớn 1.000.000 đô la Mỹ đã được trao cho đội có thuật toán tốt nhất để dự đoán xếp hạng tăng 10,06%.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp; Các hệ thống khuyến nghị được sử dụng rộng rãi nhất dựa trên Collaborative Filtering(CF) -  Lọc cộng tác và  Content-based Filtering - Lọc dựa trên nội dung. Lọc dựa trên nội dung thúc đẩy sự tương đồng giữa các bộ phim. Nó giả định rằng nếu người dùng thích một bộ phim thì anh ta cũng sẽ thích một bộ phim tương tự.
	
#### Input
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp; Tập dữ liệu MovieLens được thu thập bởi Grou- Dự án nghiên cứu pLens tại Đại học Minnesota. Tập dữ liệu này bao gồm:
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;• 100.000 xếp hạng (1-5) từ 943 người dùng trên 1682 phim
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;• Mỗi người dùng đã xếp hạng ít nhất 20 phim
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Dữ liệu được thu thập thông qua trang web MovieLens (phimmoi.umn.edu)
	
#### Output
### Dữ liệu bài toán
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Dataset gồm 2 file: movies.csv và ratings.csv
File movies.csv chứa những thông tin: mã phim (movieId), tên phim (title), thể loại phim (genres).
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/116339823-5093cb80-a808-11eb-83f6-26f905ab7ef6.png" width="50%"/>
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp; File ratings.csv chứa những thông tin: mã người đánh giá (userId), mã phim (movieId), điểm đánh giá (rating), thời gian đánh giá (timestamp).
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/116339976-95b7fd80-a808-11eb-9ff7-1b0c8a222408.png" width="50%"/>	
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/116340212-fd6e4880-a808-11eb-8c93-bcba1c3f269a.png" width="50%"/>
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/116340219-ffd0a280-a808-11eb-8453-e643736444d5.png" width="50%"/>
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/116340223-019a6600-a809-11eb-8471-a2ed27bff403.png" width="50%"/>
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/116340230-04955680-a809-11eb-8971-332f8d25a2c6.png" width="50%"/>
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/116340234-07904700-a809-11eb-99e3-bb73b48978b6.png" width="50%"/>

## CHƯƠNG 2: GIỚI THIỆU VỀ RECOMMENDER SYSTEM
### 1 Giới thiệu hệ thống
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp; Hệ thống tư vấn (Recommender Systems) - là một thành phần trong hệ thống thông tin. Mục đích của nó là hỗ trợ người dùng tìm kiếm được đúng thông tin cần thiết.
  
### 2 Các phương pháp thường dùng
#### 2.1 Phương pháp lọc dựa trên nội dung (Content-based filter)
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Phương pháp lọc dựa trên nội dung là một giải thuật nghiên cứu về lọc thông tin, phương pháp lọc dựa trên nội dung ước lượng hàm đánh giá R(u,i) của item i với user u được thiết lập dựa trên cơ sở đánh giá R(u,i’) của cùng user u cho item i’ mà trong đó i và i’ là tương tự nhau về mặt nội dung.
  
  
#### 2.2 Phương pháp lọc cộng tác (Collaboration filter)
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Phương pháp lọc cộng tác là phương pháp tập hợp các đánh giá hoặc các quan điểm của khách hàng, nhận dạng sự tương đồng giữa các khách hàng trên cơ sở các đánh giá hoặc quan điểm của họ và phát sinh ra những tư vấn mới cho khách hàng.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Bản chất của phương pháp này chính là hình thức tư vấn truyền miệng tự động. Trong phương pháp này, hệ thống sẽ so sánh, tính toán độ tương tự nhau giữa những người dùng hay sản phẩm, từ đó người dùng sẽ được tư vấn những thông tin, sản phẩm được ưa chuộng nhất bởi những người dùng có cùng thị hiếu. Trong phương pháp này, hệ thống thường xây dựng các ma trận đánh giá bởi người dùng lên các sản phẩm, bản tin, từ đó tính toán độ tương tự giữa họ.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Các hệ tư vấn dựa trên lọc cộng tác không yêu cầu quá nặng vào việc tính toán, do đó nó có thể đưa ra những tư vấn có độ chính xác cao và nhanh chóng cho một số lượng lớn người dùng. Hơn nữa, hệ tư vấn này không yêu cầu mô tả nội dung tưởng mình mà chỉ sử dụng đánh giá của người dùng để ước lượng, do đó những hệ này có khả năng tư vấn phong phú và thường tạo ra những tư vấn bất ngờ cho người dùng.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Phương pháp lọc cộng tác có các vấn đề như:
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	Sự thưa thớt
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	Vấn đề sản phẩm mới
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	Vấn đề khách hàng mới

  
  
## CHƯƠNG 3: CÁC THÀNH PHẦN CỦA MỘT HỆ GỢI Ý
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Hệ gợi ý rất quen thuộc và gần gũi, vậy để xây dựng được một hệ gợi ý, chúng ta cần có:
    
### 1 Dữ liệu
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Đầu tiên chúng ta cần có dữ liệu về users, items, feedback
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Trong đó
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	users là danh sách người dùng
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	items là danh sách sản phẩm, đối tượng của hệ thống. Ví dụ như các bài viết trên trang viblo, các video trên youtube,… Và mỗi item có thể kèm theo thông tin mô tả.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	feedback là lịch sử tương tác của user với mỗi item, có thể là đánh giá của mỗi user với một item, số ratings, hoặc comment, việc user click, view hoặc mua sản phẩm,…

### 2 Ma trận user-item: Utility matrix
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143839-cadb8780-a073-11eb-9678-f22c5408e530.png" width="50%"/>
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp; Đây là ma trận biểu diễn mức độ quan tâm (rating) của user với mỗi item. Ma trận này được xây dựng từ dữ liệu (1). Những ma trận này có rất nhiều các giá trị miss. Nhiệm vụ của Hệ gợi ý chính là dựa vào các ô đã có giá trị trong ma trận trên (dữ liệu thu được từ trong quá khứ), thông qua mô hình đã được xây dựng, dự đoán các ô còn trống (của user hiện hành), sau đó sắp xếp kết quả dự đoán (ví dụ, từ cao xuống thấp) và chọn ra Top-N items theo thứ tự rating giảm dần, từ đó gợi ý chúng cho người dùng.
  
### 3 Phương pháp 
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Có 2 phương pháp gợi ý chính, thường được sử dụng để xây dựng hệ gợi ý, đó là:
  
#### 3.1 Content-based Filtering: 
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Gợi ý các item dựa vào hồ sơ (profiles) của người dùng hoặc dựa vào nội dung/thuộc tính (attributes) của những item tương tự như item mà người dùng đã chọn trong quá khứ.
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143842-ce6f0e80-a073-11eb-98fe-fb7c62da8467.png" width="50%"/>
  
#### 3.2 Collaborative Filtering: 
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Gợi ý các items dựa trên sự tương quan (similarity) giữa các users và/hoặc items. Có thể hiểu rằng đây là cách gợi ý tới một user dựa trên những users có hành vi tương tự.
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143844-cfa03b80-a073-11eb-8f7a-5989b4f16ffb.png" width="50%"/>

## CHƯƠNG 4: PHƯƠNG PHÁP GỢI Ý DỰA THEO NỘI DUNG (CONTENT-BASED FILTERING)
### 1 Ý tưởng 
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Ý tưởng của thuật toán này là, từ thông tin mô tả của item, biểu diễn item dưới dạng vectơ thuộc tính. Sau đó dùng các vectơ này để học mô hình của mỗi user, là ma trận trọng số của user với mỗi item.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Như vậy, thuật toán content-based gồm 2 bước:
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Bước 1: Biểu diễn items dưới dạng vectơ thuộc tính – item profile
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Bước 2: Học mô hình của mỗi user

### 2 Xây dựng Items Profile
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Trong các hệ thống content-based, chúng ta cần xây dựng một bộ hồ sơ (profile) cho mỗi item. Profile này được biểu diễn dưới dạng toán học là một “feature vector” n chiều. Trong những trường hợp đơn giản (ví dụ như item là dữ liệu dạng văn bản), feature vector được trực tiếp trích xuất từ item. Từ đó chúng ta có thể xác định các item có nội dung tương tự bằng cách tính độ tương đồng giữa các feature vector của chúng.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Một số phương pháp thường được sử dụng để xây dựng feature vector là:
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	Sử dụng TF-IDF
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	Sử dụng biểu diễn nhị phân
  
#### Sử dụng TF-IDF:
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;TF(t, d) = ( số lần từ t xuất hiện trong văn bản d) / (tổng số từ trong văn bản d)
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;IDF(t, D) = log_e( Tổng số văn bản trong tập mẫu D/ Số văn bản có chứa từ t )
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Ví dụ: Giả sử chúng ta tìm kiếm về “IoT and analytics” trên Internet và tìm được những bài báo dưới đây:
	
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143846-d169ff00-a073-11eb-8a7c-a1e1052ef6f2.png" width="50%"/>
	
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Trong các bài báo, 5000 chứa analytics, 50.000 chứa data và số lượng tương tự dành cho các từ khác. Chúng ta hãy giả sử rằng tổng số tài liệu là 1 triệu (10 ^ 6).
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	Tính TF: Ta sẽ tính TF cho mỗi từ trong mỗi bài báoVí dụ, TF(analytics) = 1 + lg21 = 2.322
	
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143848-d29b2c00-a073-11eb-9492-dbb868e4186c.png" width="50%"/>
  
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	Tính IDF:
	
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;IDF được tính bằng cách lấy nghịch đảo logarit của tần số tài liệu trong toàn bộ kho tài liệu. Vì vậy, nếu có tổng số 1 triệu tài liệu được trả về bởi truy vấn tìm kiếm của chúng tôi và trong số các tài liệu đó, ví dụ: nếu từ smart xuất hiện trong 0,5 triệu lần trong tài liệu, giá trị IDF của nó sẽ là: Log10 (10 ^ 6/5000000) = 0,30.(thiếu)
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143850-d464ef80-a073-11eb-9fc2-9ad3ee38164d.jpg" width="50%"/>
  
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	Tính trọng số TF-IDF:
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Đầu tiên chúng ta sử dụng công thức sau để tính tf-df:
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143853-d8910d00-a073-11eb-957e-048f66debcec.jpg" width="50%"/>
  
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Sau đó, chuẩn hóa feature vector bằng cách chia vector cho độ dài của chính nó.
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143858-ddee5780-a073-11eb-9089-3cce313e6be7.jpg" width="50%"/>
  
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Như vậy, ta có thể có được các vector đặc trưng cho từng bài báo. Sau đó chúng ta có thể sử dụng độ tương đồng cosin để tính khoảng cách giữa chúng.
#### Sử dụng biểu diễn nhị phân: 
  
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Sử dụng biểu diễn nhị phân:
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143860-de86ee00-a073-11eb-8297-d28b63379357.png" width="50%"/>
  
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Trên đây là danh sách 6 bộ phim. Mỗi giá trị 0/1 thể hiện bộ phim đó không/có thuộc thể loại ở cột tương ứng.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Bên cạnh đó, một hồ sơ người dùng cũng được tạo ra, với 1 là quan tâm, -1 là không, và null là chưa đánh giá. Như trong ví dụ trên, User 1 có quan tâm bộ phim Star Wars IV, còn User 2 thì không.

  
  
### 3 Học mô hình biểu diễn của user
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Trong bài viết này, mình sẽ xét ví dụ với mô hình tuyến tính.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Giả sử ta có:
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	N users
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	M items
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	Y ma trận user-item. Trong đó, y(i,j) là mức độ quan tâm (ở đây là số sao đã rate) của user thứ i với sản phẩm thứ j mà hệ thống đã thu thập được. Ma trận Y bị khuyết rất nhiều thành phần tương ứng với các giá trị mà hệ thống cần dự đoán.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;•	R là ma trận rated or not thể hiện việc một user đã rated một item hay chưa. Cụ thể, rij = 1 nếu item thứ i đã được rated bởi user thứ j, ngược lại rij = 0 nếu item thứ i chưa được rated bởi user thứ j.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Áp dụng mô hình tuyến tính:

<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Giả sử rằng ta có thể tìm được một mô hình có thể tính được mức độ quan tâm của mỗi user với mỗi item bằng một hàm tuyến tính:
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143862-df1f8480-a073-11eb-900f-63d2e782b0f4.png" width="50%"/>
  
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Trong đó, x(m) là vector đặc trưng của item m.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Mục tiêu của chúng ta sẽ là học ra mô hình của user, tức là tìm ra w(n) và b(n).
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Xét một user thứ n bất kỳ, nếu ta coi training set là tập hợp các thành phần đã được điền của yn, ta có thể xây dựng hàm mất mát tương tự như sau:

<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143863-dfb81b00-a073-11eb-9788-a988378ce763.png" width="50%"/>
  
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Trong đó, thành phần thứ hai là regularization term và λ là một tham số dương. Chú ý rằng regularization thường không được áp dụng lên bn. Trong thực hành, trung bình cộng của lỗi thường được dùng, và mất mát nên Ln được viết lại thành:
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143865-e050b180-a073-11eb-8c45-9352cbb370f6.png" width="50%"/>
  
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Trong đó sn là số lượng các items mà user thứ n đã rated. Nói cách khác, sn là tổng các phần tử trên cột thứ n của ma trận rated or not R:
  
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143866-e0e94800-a073-11eb-874c-1d4e46298864.png" width="50%"/>
  
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Vì hàm mục tiêu chỉ phụ thuộc vào các items đã được rated, ta có thể rút gọn nó bằng cách đặt ^yn là sub vector của y được xây dựng bằng cách trích các thành phần khác dấu? ở cột thứ n, tức đã được rated bởi user thứ n trong ma trận Y. Đồng thời, đặt X^n là submatrix của ma trận feature X, được tạo bằng cách trích các hàng tương ứng với các items đã được rated bởi user thứ n. Khi đó, biểu thức hàm mất mát của mô hình cho user thứ n được viết gọn thành công thức (*):
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143867-e181de80-a073-11eb-9ace-29317307f911.png" width="50%"/>
  
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Đây chính là bài toán Ridge Regression, đã có sẵn trong thư viện “sklearn.linear_model.Ridge” của sklearn. Ở bài tiếp theo, chúng ta sẽ sử dụng thư viện này để tìm w(n) và b(n) cho mỗi user. Còn bây giờ chúng ta sẽ xét một ví dụ về cách xây dựng mô hình cho mỗi user.
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Ví dụ:
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Xét bài toán: Ta có 5 items, vector đặc trưng của mỗi item được biểu diễn bởi một hàng:
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143871-e2b30b80-a073-11eb-91da-289621f5d888.png" width="50%"/>
  
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Đồng thời, chúng ta có thông tin về user 5, đã đánh giá các item 1 và 4:  
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143872-e34ba200-a073-11eb-8ad7-b76aa4823eaf.png" width="50%"/>
  
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Đầu tiên, tiền xử lý để thu được sub vector:
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143891-ed6da080-a073-11eb-8b4f-abfc0f57cefc.png" width="50%"/>
  
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Sau đó áp dụng công thức (*), ta sẽ được hàm mất mát:
<p align="center"> <img src ="https://user-images.githubusercontent.com/77925421/115143893-ee9ecd80-a073-11eb-9616-405680b5b4c1.png" width="50%"/>
  
<p align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;Cuối cùng, chúng ta có thể sử dụng Stochastic Gradient Descent (SGD), hoặc Mini-batch GD để tìm ra w(5) và b(5).

## CHƯƠNG 5: CODE DEMO
### Code Pyspark
&nbsp;&nbsp;&nbsp;&nbsp;https://colab.research.google.com/drive/1wkWEL9ETvlWh2BQsPmGHcIcCq_uUdFuy?usp=sharing&fbclid=IwAR3PAb-x85Q628DtfTn8IPLCUcie9-Mr1sU-NxhYfWR0Fd6lKpVNtam_QB0

### Code Tuần tự 
&nbsp;&nbsp;&nbsp;&nbsp;https://colab.research.google.com/drive/1yd_wSb81Myhgu4cKq3vEjd7WQnHNYcPI?usp=sharing 
## TÀI LIỆU THAM KHẢO
&nbsp;&nbsp;&nbsp;&nbsp;1.https://machinelearningcoban.com/2017/05/17/contentbasedrecommendersys/

&nbsp;&nbsp;&nbsp;&nbsp;2.https://tailieu.vn/doc/luan-van-thac-si-ung-dung-he-thong-tu-van-recommender-systems-trong-linh-vuc-thuong-mai-dien-tu-1602259.html

&nbsp;&nbsp;&nbsp;&nbsp;3.https://itzone.com.vn/vi/article/tim-hieu-ve-content-based-filtering-phuong-phap-goi-y-dua-theo-noi-dung-phan-1/

&nbsp;&nbsp;&nbsp;&nbsp;4.https://l.facebook.com/l.php?u=https%3A%2F%2Fviblo.asia%2Fp%2Flam-the-nao-de-xay-dung-mot-recommender-system-rs-phan-1-aWj53V2Gl6m%3Ffbclid%3DIwAR2k-ePOFRDLOPSsG3iAHRqDCaQ6X_GzKpJW8vOi1hpCAiiomYfHD2JWtXg&h=AT19O0pxrq2c6csEXzJ5VnE5c8oIg1ohkBGYHTgkg5ytrg1u3orKqBq3TB5u_3f5m7Kc_L4in4vGm-8Iuy8BMcoaXNdXLsBoJ49KhNTKRw9VCv8JGeZKHCBndCAaMYoMXH_-GA

### Code Pyspark:
&nbsp;&nbsp;&nbsp;&nbsp;5.https://towardsdatascience.com/build-recommendation-system-with-pyspark-using-alternating-least-squares-als-matrix-factorisation-ebe1ad2e7679

&nbsp;&nbsp;&nbsp;&nbsp;6.https://github.com/snehalnair/als-recommender-pyspark 
### Code tuần tự:
&nbsp;&nbsp;&nbsp;&nbsp;7.https://github.com/vivdalal/movie-recommender-system
### Dataset:
&nbsp;&nbsp;&nbsp;&nbsp;8.https://grouplens.org/datasets/movielens/100k/


