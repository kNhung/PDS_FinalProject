# ĐỒ ÁN CUỐI KỲ
# MÔN HỌC: LẬP TRÌNH CHO KHOA HỌC DỮ LIỆU
Giảng viên hướng dẫn: ThS. Phạm Trọng Nghĩa
### NHÓM 16 ###
---
## Mục lục
- [A. Tổng quan về nhóm và đồ án](#phan-a)
  - [1. Thông tin các thành viên](#thong-tin)
  - [2. Phân công công việc và đánh giá mức độ hoàn thành](#tu-danh-gia)
  - [3. Kế hoạch đồ án](#ke-hoach)
- [B. Những khó khăn và bài học rút ra được khi thực hiện đồ án](#phan-b)
- [C. Biên bản họp](#phan-c)
  - [1. Biên bản họp lần 1](#hop-lan-1)
  - [2. Biên bản họp lần 2](#hop-lan-2)
---
## A. Tổng quan về nhóm và đồ án: <a id="phan-a"></a>
### 1. Thông tin các thành viên: <a id="thong-tin"></a>
|Họ tên                 |MSSV    |
|-----------------------|--------|
|Nguyễn Trần Gia        |22120083|
|Trần Hoàng Kim Ngân    |22120224|
|Nguyễn Phát Kim Nhung  |22120259|

### 2. Phân công công việc và đánh giá mức độ hoàn thành: <a id="tu-danh-gia"></a>
|Họ tên                 |MSSV    |Phân công công việc                                   |Mức độ hoàn thành|
|-----------------------|--------|------------------------------------------------------|-----------------|
|Nguyễn Trần Gia        |22120083|Thu thập dữ liệu, đặt và trả lời câu hỏi              |100%             |
|Trần Hoàng Kim Ngân    |22120224|Khám phá và tiền xử lý dữ liệu, đặt và trả lời câu hỏi|100%             |
|Nguyễn Phát Kim Nhung  |22120259|Khám phá và tiền xử lý dữ liệu, đặt và trả lời câu hỏi|100%             |

### 3. Kế hoạch đồ án: <a id="ke-hoach"></a>
|Thời gian thực hiện      |Công việc                                         |Người thực hiện                             |Đánh giá tiến độ |
|-------------------------|--------------------------------------------------|--------------------------------------------|-----------------|
|18/11/2024 - 23/11/2024  |Tìm hiểu về cách thực hiện đồ án                  |Tất cả thành viên                           |100%             |
|24/11/2024               |Họp nhóm lần 1                                    |Tất cả thành viên                           |100%             |
|24/11/2024 - 1/12/2024   |Thực hiện thu thập dữ liệu về tập dữ liệu đã chọn |Nguyễn Trần Gia                             |100%             |
|24/11/2024 - 29/11/2024  |Thực hiện khám phá và tiền xử lý dữ liệu          |Trần Hoàng Kim Ngân và Nguyễn Phát Kim Nhung|100%             |
|29/11/2024 - 9/12/2024   |Tìm hiểu, đặt và phân tích những câu hỏi          |Tất cả thành viên                           |100%             |
|9/12/2024 - 10/12/2024   |Duyệt lại tất cả các nội dung đã thực hiện        |Tất cả thành viên                           |100%             |
|11/12/2024               |Họp lần 2                                         |Tất cả thành viên                           |100%             |
|11/12/2024 - 13/12/2024  |Thực hiện chỉnh sửa và hoàn thành đồ án           |Tất cả thành viên                           |100%             |

---
## B. Những khó khăn và cách giải quyết khó khăn khi thực hiện đồ án: <a id="phan-b"></a>
#### 1. Thu thập dữ liệu:
- Có nhiều trang web cung cấp nhiều dữ liệu khác nhau, khó khăn trong tìm kiếm dữ liệu phù hợp để phân tích, tìm hiểu xử lý

-> *Cách xử lý:* Trang kagge có cung cấp đầy đủ thông tin giấy phép uy tín, update dữ liệu mới.

#### 2. Khám phá và tiền xử lý dữ liệu:
- Cột ‘duration’ không nhất quán về giá trị: vừa là số phút của phim, vừa là số phần của chương trình truyền hình.

-> *Cách xử lý:* Tách làm 2 cột: ‘duration’ cho thời lượng phim, ‘season’ cho số mùa của chương trình truyền hình.
- Sau khi tách thì tạo ra giá trị null trong 2 cột  ‘duration’ và ‘season’.

-> *Cách xử lý:* Do giá trị null của mỗi cột là do khác loại, nếu điền 0 sẽ không hợp lí do nó không phải null từ mỗi cột và sẽ làm sai lệch phân bổ của dữ liệu, nên nhóm quyết định giữ null. Vì giữ null nên không ép kiểu int được mà phải ép kiểu float.
- Giá trị null của cột ‘rating’ không thể điền trung bình hay mode do dễ làm sai thông tin liên quan đến thể loại, nội dung.

-> *Cách xử lý:* Vì phần trăm null của cột này không nhiều, có thể tìm và điền vào rating tương ứng. Nhưng mỗi nội dung được gán nhãn khác nhau ở mỗi nước -> Thống nhất chọn rating ở Mỹ.

#### 3. Trả lời câu hỏi:
**Câu 1:** Sự thay đổi về số lượng và thể loại nội dung của Netflix qua các năm là gì?
- Cột ‘listed_in’ bao gồm nhiều thể loại ở mỗi nội dung, không tiện để phân tích từng thể loại

-> *Cách xử lý:* One-hot encoding cho cột ‘listed_in’
- Có quá nhiều thể loại đơn, khó phân tích và trực quan

-> *Cách xử lý:* Dựa vào đặc điểm chung để nhóm vào thành các nhóm thể loại chính

**Câu 2:** Xu hướng về sự đa dạng hóa nội dung quốc tế và nội dung nội địa của Netflix là gì?
- Cột ‘country’ là một cột đa trị, gây khó khăn trong quá trình phân tích đó là nội dung nội địa hay quốc tế

-> Cách xử lý: One-hot encoding cho cột ‘country’’
- Cột ‘country’ có nhiều giá trị UNKNOWN gây khó khăn trong việc phân tích và có thể làm dữ liệu cho quá trình phân tích

-> *Cách xử lý:* Bỏ qua các hàng UNKNOWN do ở đây câu hỏi đặt ra là nội dung nội địa và quốc tế nên các giá trị UNKNOWN không có giá trị để phân tích. Ngoài ra các giá trị UNKNOWN cũng không chiếm số lượng quá nhiều.

**Câu 3:** Netflix có đang thay đổi chiến lược hợp tác với các đạo diễn và diễn viên nổi bật theo thể loại và thời gian không?
- Cột director, cast còn nhiều giá trị UNKNOWN khó khăn hơn trong việc phân tích chi tiết làm bỏ đi nhiều phim.

-> *Cách xử lý:* Bỏ qua các hàng có giá trị UNKNOWN, chọn top nổi bật để phân tích
Có nhiều ô đa giá trị, khi tách giá trị thành hàng riêng biệt đơn giá trị, làm ảnh hưởng khi đếm đạo diễn cho phim nào sẽ bị trùng lại

-> *Cách xử lý:* Kế hợp với title tựa đề phim để gom nhóm tránh bị đếm trùng

---
## C. Biên bản họp: <a id="phan-c"></a>
### 1. Biên bản họp lần 1: <a id="hop-lan-1"></a>
#### Thông tin các thành viên tham gia họp:

|Họ tên                 |MSSV    |
|-----------------------|--------|
|Nguyễn Trần Gia        |22120083|
|Trần Hoàng Kim Ngân    |22120224|
|Nguyễn Phát Kim Nhung  |22120259|

#### Thời gian:
- **Bắt đầu:** 22h ngày 24/11/2024
- **Kết thúc:** 23h ngày 24/11/2024
#### Nội dung:
- **Phân công công việc:** Nhóm trưởng sẽ đọc các yêu cầu được thầy đưa ra và thực hiện chia công việc theo như bảng phân công đã được nêu ở phần trên.
- **Đặt ra hạn chót cho các công việc:**

|Công việc                     |Người thực hiện      |Hạn chót  |
|------------------------------|---------------------|----------|
|Thu thập dữ liệu              |Trần Gia             |1/12/2024 |
|Khám phá dữ liệu và tiền xử lý|Kim Ngân và Kim Nhung|29/11/2024|
|Đặt câu hỏi                   |Tất cả               |9/12/2024 |
|Câu 1                         |Kim Nhung            |9/12/2024 |
|Câu 2                         |Kim Ngân             |9/12/2024 |
|Câu 3                         |Trần Gia             |9/12/2024 |

- **Đặt câu hỏi có ý nghĩa:** Nhóm trưởng sẽ giao việc đặt câu hỏi cho từng thành viên và nêu lên được lợi ích của chúng.
  - Câu 1. Sự thay đổi về số lượng và thể loại nội dung của Netflix qua các năm là gì?
  - Câu 2. Xu hướng về sự đa dạng hóa nội dung quốc tế và nội dung nội địa của Netflix là gì?
  - Câu 3. Netflix có đang thay đổi chiến lược hợp tác với các đạo diễn và diễn viên nổi bật theo thể loại và thời gian không?
### 2. Biên bản họp lần 2: <a id="hop-lan-2"></a>
#### Thông tin các thành viên tham gia họp:

|Họ tên                 |MSSV    |
|-----------------------|--------|
|Nguyễn Trần Gia        |22120083|
|Trần Hoàng Kim Ngân    |22120224|
|Nguyễn Phát Kim Nhung  |22120259|

#### Thời gian:
- **Bắt đầu:** 13h ngày 11/12/2024
- **Kết thúc:** 15h ngày 11/12/2024
#### Nội dung:
- **Kiểm tra các phần đã thực hiện:** Các thành viên trong nhóm cùng xem lại các phần đã thực hiện và xem xét, ghi chú lại các nội dung bị sai sót trong quá trình làm.
