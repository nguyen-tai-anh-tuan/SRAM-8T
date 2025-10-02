# SRAM-8T
# Thiết Kế Ô Nhớ SRAM 8T 8x8 💾  
# Giới Thiệu 📖 

Dự án tập trung vào việc thiết kế và mô phỏng ô nhớ SRAM 8T kích thước 8x8,
nhằm cải thiện độ ổn định và giảm tiêu thụ năng lượng so với cấu trúc SRAM 6T truyền thống.
Hệ thống sử dụng công nghệ CMOS 90nm trên môi trường Cadence,
tối ưu hóa cho các ứng dụng yêu cầu tốc độ cao, độ tin cậy và tiết kiệm điện năng.  
Video hướng dẫn chi tiết có tại: [YouTube Playlist SRAM 8T](https://www.youtube.com/playlist?list=PLexf6rL6kgqxwV7ZoVQh2SbtBmpuDXHkf).  

# Cấu Trúc Chính ⚙️

**Mảng SRAM 8T:** Bao gồm 64 ô nhớ, mỗi ô sử dụng 8 transistor để lưu trữ và truy xuất dữ liệu,
tách biệt đường đọc/ghi để giảm xung đột và tăng ổn định.  
**Mạch nạp trước (Precharge):** Đưa các đường bitline (BL, BLB) về mức điện áp cao trước khi đọc/ghi,
sử dụng transistor với tỷ lệ W/L = 260n/100n để đảm bảo dòng nạp đủ lớn.  
**Mạch ghi (Write Driver):** Ghi dữ liệu vào ô nhớ qua các đường WBL, WBLB và WWL,
sử dụng bộ nghịch đảo để tạo chênh lệch điện áp.  
**Mạch khuếch đại cảm nhận (Sense Amplifier):** Khuếch đại chênh lệch điện áp nhỏ từ bitline,
sử dụng cấu trúc latch để xác định dữ liệu nhanh chóng và chính xác.  
**Mạch giải mã 3 sang 8:** Chọn hàng ô nhớ dựa trên địa chỉ đầu vào,
sử dụng kết hợp giải mã 2 sang 4 với chân enable để tối ưu diện tích.  

# Công Nghệ Sử Dụng 🔧

**Công nghệ bán dẫn:** CMOS 90nm với tỷ lệ W/L pMOS gấp 2 lần nMOS (ví dụ: pMOS W=260nm, L=100nm).  
**Phần mềm mô phỏng:** Cadence Virtuoso cho thiết kế schematic và layout,
Cadence Spectre cho mô phỏng dạng sóng và phân tích.  
**Thông số chính:** Điện áp nguồn Vdd = 0.8V đến 1.2V,
nhiệt độ hoạt động từ -10°C đến 80°C.  

# Thiết Kế Và Kết Quả 🛠️

**Thiết kế phần cứng:** Sơ đồ khối hệ thống bao gồm mảng ô nhớ và các mạch ngoại vi,
layout clean với kích thước tối ưu, không lỗi DRC/LVS.  
**Mô phỏng:** Kiểm tra tại các mức điện áp (1.2V, 1.0V, 0.8V) và nhiệt độ (-10°C, 27°C, 80°C).  
**Ví dụ:** Tại 1.2V/27°C, độ trễ trung bình ~19.89ps, công suất ~58.32μW;
hoạt động ổn định, dạng sóng rõ ràng, không lỗi chức năng.  
**Kết quả:** SRAM 8T cho thấy độ ổn định cao hơn 6T, thời gian truy cập ngắn,
tiêu thụ năng lượng thấp, phù hợp cho hệ thống nhúng và vi mạch mật độ cao.  
**Ưu điểm:** Giảm nhiễu đọc/ghi, hoạt động tốt ở điện áp thấp, dễ tích hợp.  
**Hạn chế:** Diện tích lớn hơn 6T, thiết kế phức tạp hơn.  

# Hướng Phát Triển 🚀

- So sánh và tích hợp với cấu trúc tiên tiến như SRAM 10T hoặc 12T.
- Áp dụng công nghệ mới như 65nm hoặc FinFET để giảm năng lượng và tăng mật độ.
- Mở rộng quy mô mảng nhớ và tích hợp vào các ứng dụng thực tế như IoT hoặc AI.
