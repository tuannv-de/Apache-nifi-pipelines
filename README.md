# **Triển Khai Pipeline Bằng Apache Nifi**
Ở trong dự án này cung cấp tài liệu hướng dẫn chi tiết cấu hình, triển khai, quản lý pipeline dạng manual bằng giao diện - Nifi là một công cụ thuộc lớp Ingestion, có thể triển khai dễ dàng bằng giao diện và cũng là một công cụ có thể triển khai CDC cho các database

## **1. real-time pipeline 1:**
**EXTRACT DATA FROM FORDGOBIKE API, TRANSFORM AND STORE IT IN S3 AS CSV**
  -	lấy dữ liệu từ API http://hamilton.socialbicycles.com/opendata/station_status.json chứa thông tin về trạng thái của các trạm xe của Ford GoBike
![Picture15](https://github.com/user-attachments/assets/d010b55d-f422-4ebe-a906-410fcf8a950d)
  - Sau khi các tệp đã được lấy từ thư mục tạm thời, bước tiếp theo là trích xuất thông tin về ID trạm và số lượng xe đạp có sẵn, sau đó chuyển đổi thông tin đó thành tệp CSV và thêm nó vào s3

![Picture10](https://github.com/user-attachments/assets/68d89ab2-e59b-496d-b322-89163468f8f1)

## **2. real-time pipeline 2:**
**REAL TIME DATA PROCESSING WITH KAFKA, NIFI, CLICKHOUSE**
Thu thập dữ liệu từ api bằng nifi, đưa dữ liệu vào kafka topics, phân luồng dữ liệu để xử lí , lưu dữ liệu sau xử lí vào Clickhouse và trực quan hoá bằng Superset
![Picture20](https://github.com/user-attachments/assets/5c4b3531-932b-4cac-8c4d-285830752a43)
![Picture30](https://github.com/user-attachments/assets/628b77f0-09a2-4e80-8733-8d8c7f4fa54c)
![Picture40](https://github.com/user-attachments/assets/682faee8-b648-4bb2-abe8-038905a7683d)


## **3. process with Nifi**
**FETCH FILES FROM STAGING FOLDER, PROCESSING AND PUT PROCESSED FILE IN DESTINATION FOLDER**
  - lấy dữ liệu từ staging (S3)
  - Thực hiện một số xử lý (Apache nifi): Xóa các ký tự đặc biệt khỏi số điện thoại
  - lưu dữ liệu sau xử lý vào destination (S3)

![Pictureb1](https://github.com/user-attachments/assets/bd77a217-7017-4e3d-836b-d558a2777f80)
