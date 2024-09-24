## **Hướng dẫn OCR**

**Mục lục**

1. [Tổng quan về OCR](#tổng-quan-về-ocr)
2. [Tiếp cận bài toán OCR](#tiếp-cận-bài-toán-ocr)
3. [Text Recognition](#text-recognition)
4. [Connectionist Temporal Classification (CTC)](#connectionist-temporal-classification-ctc)
5. [Thực hiện dự án](#thực-hiện-dự-án)

**1. Tổng quan về OCR** <a name="tổng-quan-về-ocr"></a>

* **Định nghĩa:** OCR là quá trình chuyển đổi văn bản trong hình ảnh thành dạng văn bản máy tính có thể đọc được.
* **Ứng dụng:**
    * Tìm kiếm và truy vấn thông tin trong ảnh và video.
    * Nhận dạng biển số xe.
    * Lọc và tóm tắt dữ liệu từ hóa đơn, chứng minh thư, ...
* **Thách thức:**
    * Mật độ chữ dày đặc.
    * Đa dạng về font chữ và kiểu chữ.
    * Sự khác biệt về cấu trúc của từ (ví dụ: chữ viết theo chiều dọc, đường cong).
    * Chất lượng ảnh (độ phân giải, ánh sáng, ...).

**2. Tiếp cận bài toán OCR** <a name="tiếp-cận-bài-toán-ocr"></a>

* **Hai bước chính:**
    * **Text Detection:** Xác định vị trí của các từ trong ảnh.
    * **Text Recognition:** Nhận dạng (dự đoán) các từ tại vị trí đã xác định.
* **Các module hỗ trợ khác:**
    * Tăng cường dữ liệu.
    * Lựa chọn hàm mất mát (loss function).
    * Căn chỉnh bounding box (align bounding box).
    * Chỉnh sửa kết quả dự đoán.

**3. Text Recognition** <a name="text-recognition"></a>

* **Pipeline xử lý:**
    * **Feature Sequence Extraction:** Trích xuất đặc trưng của ảnh.
    * **Sequence Labeling:** Sử dụng RNN (LSTM) để dự đoán nhãn cho từng vùng ảnh.
    * **Transcription:** Sử dụng CTC để chuyển đổi đầu ra của RNN thành chuỗi ký tự cuối cùng.

**4. Connectionist Temporal Classification (CTC)** <a name="connectionist-temporal-classification-ctc"></a>

* **Giới thiệu:** CTC là một phương pháp được sử dụng để giải quyết vấn đề không biết trước sự liên kết (alignment) giữa đầu vào và đầu ra trong các bài toán nhận dạng chuỗi, như nhận dạng giọng nói, nhận dạng chữ viết tay, và OCR.
* **Ưu điểm:**
    * Không yêu cầu alignment giữa đầu vào và đầu ra.
    * Có thể xử lý đầu vào và đầu ra có chiều dài khác nhau.
    * Có thể xử lý các trường hợp đầu ra có ký tự lặp lại.

**5. Thực hiện dự án** <a name="thực-hiện-dự-án"></a>

* **Text Detection:**
    * Có thể sử dụng YOLOv5 để phát hiện văn bản như một đối tượng.
    * Tham khảo các thuật toán Text Detection khác.
* **Text Recognition:**
    * Triển khai pipeline xử lý.
    * Sử dụng CTC loss và CTC decoder.
    * Tham khảo các thuật toán Text Recognition khác.
* **Tools/Frameworks:**
    * Tìm hiểu và sử dụng các công cụ và frameworks phổ biến cho OCR.
