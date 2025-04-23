# BTVN5
BÀI TẬP VỀ NHÀ 05, Môn Hệ quản trị csdl.

SUBJECT: Trigger on mssql

A. Trình bày lại đầu bài của đồ án PT&TKHT:

Mô tả bài toán của đồ án PT&TKHT, đưa ra yêu cầu của bài toán đó
Cơ sở dữ liệu của Đồ án PT&TKHT : Có database với các bảng dữ liệu cần thiết (3nf), Các bảng này đã có PK, FK, CK cần thiết
B. Nội dung Bài tập 05:

Dựa trên cơ sở là csdl của Đồ án
Tìm cách bổ xung thêm 1 (hoặc vài) trường phi chuẩn (là trường tính toán đc, nhưng thêm vào thì ok hơn, ok hơn theo 1 logic nào đó, vd ok hơn về speed) => Nêu rõ logic này!
Viết trigger cho 1 bảng nào đó, mà có sử dụng trường phi chuẩn này, nhằm đạt được 1 vài mục tiêu nào đó. => Nêu rõ các mục tiêu
Nhập dữ liệu có kiểm soát, nhằm để test sự hiệu quả của việc trigger auto run.
Kết luận về Trigger đã giúp gì cho đồ án của em.
HƯỚNG DẪN CÁCH LÀM:

Hướng dẫn làm phần A:

Chỉ cần nêu ra y/c của đồ án.
Không cần chụp quá trình làm ra db, tables.
Chỉ cần đưa ra db gồm các bảng nào, mỗi bảng có các trường nào, kiểu dữ liệu nào, và pk, fk, ck của các bảng.
Hướng dẫn làm phần B:

Sv tạo repo mới trên github, cho phép truy cập public.
Tạo file Readme.md, đầu file để thông tin cá nhân sv.
Tiếp theo đưa phần A vào file Reame.md .
Các thao tác làm trên csdl bằng phần mềm ssms.
Chụp ảnh màn hình quá trình làm.
Paste ngay vào Readme.md, rồi gõ mô tả ảnh này làm gì, nhập gì, hay đạt được điều gì...
Có thể thêm những nhận xét hoặc kết luận cho việc bản thân đã hiểu rõ thêm về 1 vấn đề gì đó.
Lặp lại các step 4 5 6 cho đến khi hoàn thành yêu cầu của phần B.
Xuất các file sql chứa cấu trúc và data, up lên cùng repo.
Link đến repo cần mở được trực tiếp nội dung, Paste link này vào file excel online ghim trên nhóm. Thầy sẽ dùng tool để check các link này.
DEADLINE: 23H59:59 NGÀY 23/04/2025

p/s:

Sv được phép tham khảo mọi nguồn, nhưng phải tự làm lại.
Đọc thêm nội quy học tập để biết các chế tài.
Đã đến lúc khẳng định bản thân và toả sáng!
Chỗ nào vướng mắc cứ share lên nhóm để cùng tháo gỡ.

# Tạo cơ sở dữ liệu gồm các bảng như:
+ KhachHang  
![{DB9DE248-7E07-401E-A485-62D07D200824}](https://github.com/user-attachments/assets/7482e293-7f20-4915-914a-a7771c2704a0)  
+ TheLoaiSach  
![{9144CD5E-DD47-443D-B11F-B0F00B6D0EAE}](https://github.com/user-attachments/assets/cea04786-ab34-4814-a4b9-9c11036305d0)  
+ Sach  
![{442A9341-C1AF-4F6A-9C82-8E639BB91987}](https://github.com/user-attachments/assets/2e69cfae-cbb3-495e-a466-c23cb5e7b7ee)  
+ DonHang  
![{AAFB48C3-0941-4916-AC30-4305C9343B74}](https://github.com/user-attachments/assets/23b7b4c7-10a7-4a1c-b925-5eb1e7b9f773)  
+ ChiTietDonHang  
![{7A2218BC-929C-4CCD-AEF7-862B95FBA093}](https://github.com/user-attachments/assets/7f3e9ad0-5d8a-4d0b-8747-0be86b40ff24)  
+ NhanVien  
 ![{C93E94E3-6985-4E9D-87D1-404074E9902B}](https://github.com/user-attachments/assets/cbcc1ff6-a980-4dab-ae6b-be2cfb100289)  
+ GiaoDich  
![{47CB2AE8-28FA-45A3-8C67-1E9A1C06B55B}](https://github.com/user-attachments/assets/a8af1457-cadc-475d-bb6a-04183642448f)  
# Đi kèm với mỗi bảng là những khóa ngoại liên kết giữa các bảng  
![{7E4C5B52-4724-49F5-918B-80ADA8EA5F19}](https://github.com/user-attachments/assets/c714b11a-d02c-44c8-a3c1-119410001412)  
![{7AE9E29D-5249-4ED7-A9C3-3B65F239BF4B}](https://github.com/user-attachments/assets/abc8cd1f-2225-4585-8f0b-00f13806cd8d)  
![{FCDE1BA3-1BFB-41C9-AE96-C647789F7761}](https://github.com/user-attachments/assets/70f1aca6-a8bb-4cfe-b412-3c059ea67256)  
![{E99B131D-8FFF-4990-9655-F2D2CF905220}](https://github.com/user-attachments/assets/d5936810-ca77-4cd1-93ce-e90d49f2a1d7)  
## Sau khi đã liên kết các khóa ngoại ta được sơ đồ liên kết thực thể như sau:  
![{8393E79A-85E3-4D56-BAF1-C5CEC21148F4}](https://github.com/user-attachments/assets/95e6e925-868b-43d7-8e5b-57af897c5cb5)  
# Tạo 1 trigger cho bảng ChiTietDonHang để tính tổng tiền khi thêm hoặc cập nhật chi tiết đơn hàng:  
![{184CED3A-18A0-469D-9D32-7E516B525EDB}](https://github.com/user-attachments/assets/8cb37934-c3f8-4e5a-b196-7dd426622ae7)
