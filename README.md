1.Vấn đề là gì?
Nam gõ nhầm grenlog.vn thay vì greenlog.vn.  Trình duyệt chưa tìm được IP nên chưa gửi yêu cầu HTTP tới máy chủ công ty. Vì vậy, lỗi này không chứng minh máy chủ bị sập
2.Yêu cầu đề bài
Giải thích cách DNS đổi tên miền thành địa chỉ IP và phân biệt lỗi DNS với lỗi HTTP 500, nêu cách kiểm tra yêu cầu đã tới máy chủ chưa và giải thích trường hợp nhận HTTP 404
3.cách làm
Trước tiên, Nam sửa địa chỉ từ phong-dieu-phoi.grenlog.vn thành phong-dieu-phoi.greenlog.vn. Sau đó kiểm tra theo thứ tự:
1. Kiểm tra DNS: Dùng nslookup tra tên miền. Nếu nhận được IP, DNS đã tìm thấy máy chủ; nếu vẫn báo NXDOMAIN, cần kiểm tra lại tên miền hoặc bản ghi DNS
2. Kiểm tra HTTP: Mở trang và xem mã phản hồi trong tab Network của trình duyệt. Nếu có mã HTTP, yêu cầu đã tới máy chủ
3. Đọc mã lỗi: 500 nghĩa là máy chủ xử lý bị lỗi. Nếu sửa đúng tên miền mà nhận 404, máy chủ vẫn hoạt động nhưng không tìm thấy trang hoặc đường dẫn Nam yêu cầu
