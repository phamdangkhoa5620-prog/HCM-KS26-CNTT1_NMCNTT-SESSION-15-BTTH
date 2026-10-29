## 1\. Hybrid Workflow: Local + Auto Sync + Version History

### 1.1. Khi laptop bị hỏng

Nếu đã bật Auto Sync và tệp được đồng bộ hoàn tất lên Cloud, nhóm có thể đăng nhập trên thiết bị khác để tiếp tục làm việc. Những thay đổi chưa kịp đồng bộ có thể bị mất.

### 1.2. Ba bước thiết lập Auto Sync

1. Cài Google Drive for Desktop và đăng nhập tài khoản.
2. Chọn thư mục dự án SmartCampus cần đồng bộ và thiết lập chế độ đồng bộ phù hợp.
3. Kiểm tra trạng thái đồng bộ hoàn tất, sau đó thử mở tệp trên Google Drive bằng trình duyệt.

### 1.3. Khôi phục hai trang bị xóa

Mở tài liệu trên Google Drive → **File** → **Version history** → **See version history**. Chọn phiên bản trước khi xóa hai trang, kiểm tra nội dung rồi chọn **Restore this version**.

### 1.4. Những lỗi khi đồng bộ

* **`node\_modules`:** Chứa nhiều tệp được tạo tự động, có thể rất nặng và làm quá trình đồng bộ chậm. Nên lưu `package.json` cùng tệp khóa phiên bản để cài đặt và tạo lại thư mục khi cần.
* **Phim 4K:** Không liên quan trực tiếp đến dự án, dung lượng lớn và làm tốn bộ nhớ Cloud. Không nên lưu trong thư mục dự án; chỉ đồng bộ tệp thật sự cần thiết.

## 2\. Phân quyền và bảo mật

### 2.1. Chọn quyền cho từng tệp

|Tệp|Quyền|Phạm vi chia sẻ|Giải thích|
|-|-|-|-|
|`BaoCao\_CuoiKy\_SmartCampus.docx`|Viewer|Restricted|Giảng viên chỉ cần xem và chấm bài, tránh sửa nhầm nội dung. Cần thêm đúng tài khoản giảng viên.|
|`Slide\_BaoCao.pptx`|Editor|Restricted|Cả 5 thành viên cần chỉnh sửa, nhưng chỉ người được mời mới có quyền truy cập.|
|`GopY\_BanNhap.docx`|Commenter|Restricted|Người góp ý có thể nhận xét mà không trực tiếp sửa nội dung chính.|
|`ThongTin\_CaNhan\_NhomVien.xlsx`|Editor chỉ cấp cho người phụ trách cần xử lý dữ liệu|Restricted|Tệp có CCCD và số điện thoại nên chỉ chia sẻ với người thật sự cần thiết. Không cấp quyền rộng cho cả nhóm nếu không cần.|

### 2.2. Red Flag Security Rule

Với dữ liệu nhạy cảm như CCCD và số điện thoại, luôn chọn **Restricted** và chỉ cấp quyền tối thiểu cho đúng người cần truy cập. Tuyệt đối không chọn **Anyone with the link + Editor**, vì người có đường dẫn có thể truy cập và chỉnh sửa dữ liệu, làm tăng nguy cơ rò rỉ hoặc phá hoại.

### 2.3. Hai thiết lập giảm rủi ro khi có 5 Editors

1. Tắt tùy chọn cho phép **Editors thay đổi quyền và chia sẻ** nếu nền tảng có hỗ trợ.
2. Với người chỉ cần xem hoặc nhận xét, cân nhắc tắt quyền tải xuống, in và sao chép nếu có tùy chọn phù hợp. Lưu ý: thiết lập này thường không ngăn được Editor tải xuống hoặc sao chép; cần chính sách quản trị riêng nếu muốn hạn chế Editor.

## 3\. Văn hóa giao tiếp nhóm

### 3.1. Ba vấn đề trong nhóm Zalo

* **No-Hello:** Tin nhắn thiếu lời chào và ngữ cảnh, khiến người nhận khó hiểu yêu cầu.
* **Spam `@all`:** Gây phiền, đặc biệt khi gửi vào đêm muộn.
* **Không phân chia kênh/chủ đề:** Thông báo, trao đổi công việc và trò chuyện bị trộn lẫn, khó tìm lại thông tin.

### 3.2. Đề xuất các kênh

* `#thong-bao`: Thông báo chính thức và hạn chót.
* `#bao-cao-do-an`: Trao đổi nội dung báo cáo.
* `#task-tien-do`: Giao việc và cập nhật tiến độ.
* `#tro-chuyen`: Trao đổi không chính thức.

### 3.3. Viết lại tin nhắn của Lan theo cách giao tiếp bất đồng bộ

> Chào mọi người, mình đang hoàn thiện phần giao diện cho báo cáo SmartCampus và cần một bạn kiểm tra lại hình minh họa ở trang 5–7. Bạn nào có thể hỗ trợ thì phản hồi trong nhóm trước 16h hôm nay nhé. Nếu bận, mọi người có thể xem và phản hồi khi thuận tiện; mình sẽ tổng hợp góp ý trước 20h.

### 3.4. Viết lại tin nhắn nhắc việc lúc 23:47

Nên lên lịch gửi lúc 8:00 sáng và chỉ tag đúng người còn thiếu phần việc, không dùng `@all`.

> Chào buổi sáng Nam và Hoa, nhờ hai bạn cập nhật phần việc còn thiếu trước 10h sáng nay nhé. @Nam: hoàn thiện phần cơ sở dữ liệu. @Hoa: kiểm tra hình minh họa và bố cục slide. Sau khi hoàn thành, hai bạn cập nhật tiến độ trong `#task-tien-do` để nhóm tổng hợp bản cuối. Cảm ơn hai bạn!

*Chỉ tag Nam và Hoa nếu đã xác nhận hai bạn là người đang thiếu phần việc.*

## 4\. Tin nhắn thông báo chung trong `#thong-bao`

**\[CẬP NHẬT TIẾN ĐỘ SMARTCAMPUS]**

Chào mọi người, mình đã bật **Auto Sync** cho thư mục dự án và kiểm tra trạng thái đồng bộ. File `BaoCao\_CuoiKy\_SmartCampus.docx` đã được chia sẻ cho giảng viên với quyền **Viewer**, phạm vi **Restricted** để bảo đảm giảng viên chỉ xem và chấm bài.

@Nam, bạn vui lòng hoàn thiện phần cơ sở dữ liệu trước 10h sáng. @Hoa, bạn kiểm tra hình minh họa và bố cục slide trước cùng thời hạn. Sau khi xong, hai bạn cập nhật tiến độ trong `#task-tien-do` để nhóm tổng hợp bản cuối.

Mọi người tiếp tục làm việc trên file Cloud để tránh thất lạc phiên bản. Cảm ơn cả nhóm!

\---

## 

