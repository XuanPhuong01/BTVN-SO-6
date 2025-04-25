# BTVN-SO-6
# Bài tập 6:NGUYỄN THỊ XUÂN PHƯƠNG-K225480106054 - Hệ quản trị CSDL
# Yêu cầu bài toán: 
Cho file sv_tnut.sql (1.6MB)
1. Hãy nêu các bước để import được dữ liệu trong sv_tnut.sql vào sql server của em
2. dữ liệu đầu vào là tên của sv; sđt; ngày, tháng, năm sinh của sinh viên (của sv đang làm bài tập này)
3. nhập sql để tìm xem có những sv nào trùng hoàn toàn ngày/tháng/năm với em?
4. nhập sql để tìm xem có những sv nào trùng ngày và tháng sinh với em?
5. nhập sql để tìm xem có những sv nào trùng tháng và năm sinh với em?
6. nhập sql để tìm xem có những sv nào trùng tên với em?
7. nhập sql để tìm xem có những sv nào trùng họ và tên đệm với em.
8. nhập sql để tìm xem có những sv nào có sđt sai khác chỉ 1 số so với sđt của em.
9. BẢNG SV CÓ HƠN 9000 ROWS, HÃY LIỆT KÊ TẤT CẢ CÁC SV NGÀNH KMT, SẮP XẾP THEO TÊN VÀ HỌ ĐỆM, KIỂU TIẾNG  VIỆT, GIẢI THÍCH.
10. HÃY NHẬP SQL ĐỂ LIỆT KÊ CÁC SV NỮ NGÀNH KMT CÓ TRONG BẢNG SV (TRÌNH BÀY QUÁ TRÌNH SUY NGHĨ VÀ GIẢI NHỮNG VỨNG MẮC)

# 1. Hãy nêu các bước để import được dữ liệu trong sv_tnut.sql vào sql server
để import được dữ liệu trong sv_tnut.sql thì đầu tiên em tải file sv_tnut.sql về máy. Sau đó tạo 1 database mới mang tên sv_tnut rồi em mở file sv_tnut.sql vừa tải về -> execute toàn bộ file sv_tnut.sql 
![Ảnh chụp màn hình (840)](https://github.com/user-attachments/assets/bc0ed309-7367-4a64-9ea8-258f0aa63610)
Sau khi đã chạy em được bảng dữ liệu dbo.SV như hình:
![Ảnh chụp màn hình (841)](https://github.com/user-attachments/assets/7c0fda50-3652-4091-aa09-3f2b8ac19bb4)

# 2. dữ liệu đầu vào là tên của sv; sđt; ngày, tháng, năm sinh của sinh viên (của sv đang làm bài tập này)
Để thêm dữ liệu đầu vào là tên của sv, sdt, ngày, tháng, năm sinh thì em sử dụng câu lệnh sau ví dụ: thông tin của em
![Ảnh chụp màn hình (844)](https://github.com/user-attachments/assets/b5e8a9db-fa95-4bb5-a865-417ca6ec752c)
Nếu sau khi ta chạy câu lệnh ra được thông tin ta vừa thêm thì là đã đã hoàn tất việc thêm dữ liệu mới vào bảng 

# 3. nhập sql để tìm xem có những sv nào trùng hoàn toàn ngày/tháng/năm với em?
Để tìm xem có nhưng sv nào trùng hoàn toàn ngày/tháng/năm hay không em dùng câu lệnh sau để kiểm tra dữ liệu trong bảng:
![Ảnh chụp màn hình (846)](https://github.com/user-attachments/assets/03774e26-bb7d-4fd8-8a03-366aa8383545)

# 4. nhập sql để tìm xem có những sv nào trùng ngày và tháng sinh với em?
Để tìm xem có những sv nào trùng ngày và tháng sinh với em thì em dùng DAY() và MONTH() để so sánh ngày và tháng ( không dùng năm sinh )
![Ảnh chụp màn hình (847)](https://github.com/user-attachments/assets/22ed85ea-12c8-44e9-ab96-5e443db98195)

# 5. nhập sql để tìm xem có những sv nào trùng tháng và năm sinh với em?
Với yêu cầu của câu 5 thì em sử dụng câu lệnh gần giống như câu 4 nhưng ở đâu em không dùng DAY() nữa vì yêu cầu bài toán là tìm tháng, năm lên em sử dụng MONTH() và YEAR() thay vì sử dụng DAY(), MONTH()
![Ảnh chụp màn hình (848)](https://github.com/user-attachments/assets/09b62352-5493-4ffb-9eff-c9608fa65c9e)

# 6. nhập sql để tìm xem có những sv nào trùng tên với em?
Để tìm xem có những sv nào trùng tên với em thì em sử dụng câu lệnh truy vấn sau: 
![Ảnh chụp màn hình (849)](https://github.com/user-attachments/assets/7376d723-b4d2-4925-a285-243ecffc166f)

# 7. nhập sql để tìm xem có những sv nào trùng họ và tên đệm với em.
Để tìm xem có những sv nào trùng họ và tên đệm với em thì em dùng câu lệnh truy vẫn sau:
![Ảnh chụp màn hình (850)](https://github.com/user-attachments/assets/4c24c42f-dc74-42de-ad53-1ef307008264)


# 8. nhập sql để tìm xem có những sv nào có sđt sai khác chỉ 1 số so với sđt của em.
Để tìm xem có những sv nào có sdt sai khác chỉ 1 số với sdt của em thì em dùng câu lệnh sau:
![Ảnh chụp màn hình (852)](https://github.com/user-attachments/assets/f4656cb4-3e61-4caa-9361-580482cf55eb)

Giải thích lênh:
+ SUBSTRING(sdt,i,1) lấy i là số thứ tự trong số điện thoại ở đây em có tổng cộng 10 con số
+ SUBSTRING('0396988607',i,1) là số điện thoại của em muốn so sánh
+ Dùng IIF(..., 1,0) để cộng dồn các ký tự khác nhau nếu có từ 2 hay giống số khác với sdt của em thì nó sẽ bị loại. Ở dòng lệnh này chỉ khi nào sdt khác chỉ 1 số thì mới đúng.

# 9. BẢNG SV CÓ HƠN 9000 ROWS, HÃY LIỆT KÊ TẤT CẢ CÁC SV NGÀNH KMT, SẮP XẾP THEO TÊN VÀ HỌ ĐỆM, KIỂU TIẾNG  VIỆT, GIẢI THÍCH.
Để liệt kê tất cả cac ngành KMT, sắp xếp tên và họ đệm, kiểu tiếng việt thì em dùng câu lệnh truy vấn sau:
![Ảnh chụp màn hình (853)](https://github.com/user-attachments/assets/8c0ff690-ff1e-49e0-8313-2c5a67709835)

Giải thích lệnh:
+ Để lọc các sinh viên có (lop) thuộc KMT và KTP thì em sử dụng LIKE '%KMT%' và LIKR'%KTP%' để lọc dữ liệu
+ Để sắp xếp theo tên và họ đệm thì em dùng lệnh ORDER BY ten COLLATE Vietnamese_CI_AS, hodem COLLATE Vietnamese_CI_AS;
  + Vietnamese là để sắp xếp theo thứ tự bảng chữ cái tiếng việt
  + 'CI'(Case-Insensitive) dùng để không phân biệt chữ hoa/thường
  + 'AS'(Accent-Sensitive) dùng để phân biệt dấu (ví dụ: a khác á)

# 10. HÃY NHẬP SQL ĐỂ LIỆT KÊ CÁC SV NỮ NGÀNH KMT CÓ TRONG BẢNG SV (TRÌNH BÀY QUÁ TRÌNH SUY NGHĨ VÀ GIẢI NHỮNG VỨNG MẮC)
Để liệt kê các sv nữ ngành KMT có trong bảng sv thì em dùng câu lênh sau: 
![Uploading Ảnh chụp màn hình (854).png…]()

Giải thích:
+ vì trong bảng sv không có cột giới tính nên em dựa vào họ đêm. Em lọc những sinh viên có họ đêm là 'Thị' làm 1 điều kiện để lọc sinh viên
+ Tiếp theo em truy vấn 1 số cái tên nữ mà em biết để lọc bước 2 rồi hiển thị ra bảng sv nữ ngành KMT và KTP.

