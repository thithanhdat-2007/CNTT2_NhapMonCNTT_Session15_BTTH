# Bài tập tổng hợp Session 15 - SmartCampus

Họ và tên: Thi Thành Đạt  
MSSV: N26DTCN041  
Lớp: CNTT2  
Email: thithanhdat111@gmail.com

## Phần 1. Thiết lập Hybrid Workflow

**1. Laptop hỏng ổ cứng có làm mất slide không?**

Nếu từ đầu bạn đó lưu `Slide_BaoCao.pptx` trong thư mục dự án được tự động đồng bộ lên Drive, và lần chỉnh sửa mới nhất đã đồng bộ xong trước khi ổ cứng hỏng, nhóm vẫn lấy được bản mới trên Cloud. Đây là cách làm kết hợp bản trên máy và bản trên Cloud. Tuy nhiên, nếu bạn vừa sửa khi mất mạng hoặc quá trình đồng bộ chưa hoàn tất thì phần sửa mới nhất vẫn có thể mất. Vì vậy phải kiểm tra trạng thái đồng bộ, không chỉ đặt file vào thư mục rồi nghĩ rằng file đã an toàn.

**2. Ba bước bật Auto Sync cho nhóm**

1. Mỗi thành viên cài Google Drive for desktop, đăng nhập tài khoản dùng cho dự án; trong **Preferences → Folders from your computer**, chọn thư mục làm việc trên máy và bật **Sync with Google Drive**.
2. Trưởng nhóm tạo thư mục `SmartCampus` trên Drive nhưng không cấp quyền sửa cho cả thư mục. Chia sẻ từng file theo bảng ở Phần 2; riêng slide chỉ cấp Editor cho đúng 5 thành viên. Mỗi người thêm lối tắt file được chia sẻ vào Drive của mình để dễ mở từ máy.
3. Mọi người lưu bản làm việc vào Drive for desktop và mở Drive trên web để kiểm tra file đã xuất hiện, mở được. Trước khi tắt máy, kiểm tra ứng dụng báo đã đồng bộ xong, nhất là sau khi sửa slide hoặc báo cáo.

**3. Khôi phục hai trang vừa xóa nhầm**

Mở `BaoCao_CuoiKy_SmartCampus.docx` từ Drive bằng Google Docs, chọn **File → Version history → See version history**, tìm bản trước lúc xóa hai trang (khoảng 10 phút trước), xem lại rồi chọn **Restore this version**. Nếu file đang được quản lý như file tải lên và không mở chỉnh sửa bằng Google Docs, vào Drive → chọn file → **File information → Manage versions**, lấy bản trước đó để phục hồi. Trước khi khôi phục, nên báo nhóm tạm dừng sửa file để không ghi đè phần việc mới của người khác.

**4. Hai sai lầm khi đồng bộ toàn bộ thư mục**

- Đồng bộ `node_modules` là đồng bộ cả thư mục có rất nhiều file nhỏ được tạo tự động. Việc này tốn thời gian, dung lượng và dễ phát sinh xung đột. Chỉ lưu mã nguồn cùng danh sách thư viện cần cài; khi cần, chạy lệnh cài lại thư viện để tạo `node_modules` trên máy.
- Đồng bộ file phim 4K xem giải trí là đưa dữ liệu không liên quan vào dự án. File lớn chiếm dung lượng và làm chậm đồng bộ tài liệu quan trọng. Chuyển chúng ra khỏi thư mục `SmartCampus` và chỉ đồng bộ file phục vụ đồ án.

## Phần 2. Phân quyền chia sẻ an toàn

**1. Bảng quyền cho bốn file**

| File | Mức quyền | Phạm vi chia sẻ | Giải thích |
|---|---|---|---|
| `BaoCao_CuoiKy_SmartCampus.docx` | Viewer | Restricted | Chỉ thêm đúng tài khoản giảng viên để thầy/cô xem chấm điểm, không sửa đè báo cáo. |
| `Slide_BaoCao.pptx` | Editor | Restricted | Chỉ thêm đúng 5 thành viên để cả nhóm cùng sửa slide trong hai ngày còn lại. |
| `GopY_BanNhap.docx` | Commenter | Restricted | Chỉ thêm đúng tài khoản anh khóa trên để anh ấy ghi nhận xét mà không sửa trực tiếp nội dung. |
| `ThongTin_CaNhan_NhomVien.xlsx` | Viewer | Restricted | Chỉ người phụ trách thủ tục được xem; không cấp quyền sửa hoặc mở link cho người ngoài. Chủ file vẫn có thể cập nhật khi cần. |

**2. Quy tắc Cờ Đỏ Bảo mật**

Khi file có thông tin nhạy cảm như CCCD và số điện thoại, em coi đó là “cờ đỏ”: đặt **Restricted**, chỉ thêm đúng người cần dùng và cấp mức quyền thấp nhất. Nếu chọn **Anyone with the link + Editor**, bất cứ ai có link đều có thể mở, sửa hoặc xóa thông tin. Link cũng có thể bị chuyển tiếp ra ngoài, gây rò rỉ dữ liệu của cả nhóm.

**3. Hai thiết lập bổ sung cho `Slide_BaoCao.pptx`**

Trong cửa sổ **Share → Settings** của file, em thực hiện:

1. **Tắt** “Editors can change permissions and share” để thành viên có quyền sửa không tự mời thêm người lạ vào file.
2. **Tắt** quyền tải xuống, sao chép và in đối với người được cấp quyền xem/nhận xét nếu sau này có chia sẻ slide cho người ngoài nhóm. Thiết lập này không thay thế việc quản lý 5 Editor; chủ file vẫn phải kiểm tra danh sách người được chia sẻ.

Em cũng giữ thư mục chứa slide ở chế độ Restricted và không cấp quyền Editor cho người lạ ở thư mục cha, vì quyền từ thư mục cha có thể được kế thừa xuống file.

## Phần 3. Tổ chức giao tiếp nhóm

**1. Ba vấn đề trong đoạn chat Zalo**

1. Lan nhắn “có ai rảnh không” rồi mới nói cần giúp: đây là kiểu **No-Hello**, thiếu việc cụ thể nên người đọc phải hỏi lại.
2. Trưởng nhóm dùng **@all** lúc 23:47: thông báo làm phiền cả nhóm vào giờ muộn, kể cả người đã xong phần việc.
3. Tin công việc và ảnh mèo nằm trong cùng một luồng: thông tin bị trôi, chưa tách **Channel/Topic** và chưa gom câu trả lời theo **Thread**.

**2. Các kênh nên tạo**

- `#thong-bao`: hạn nộp và quyết định quan trọng; hạn chế tán gẫu.
- `#bao-cao-slide`: thảo luận nội dung báo cáo, slide; trả lời theo thread của từng việc.
- `#tro-chuyen`: trao đổi ngoài công việc để không đẩy trôi thông báo.

**3. Viết lại tin đầu tiên của Lan**

Đề không nói Lan cần giúp việc gì, nên tin dưới đây là **ví dụ giả định** Lan cần rà lỗi slide:

> Mọi người ơi, mình cần một bạn rà lỗi chính tả trong `Slide_BaoCao.pptx` trước 18:00 hôm nay. Ai nhận được việc này hãy trả lời ngay trong thread này; mình sẽ kiểm tra lại các chỗ bạn đánh dấu. Cảm ơn mọi người.

Tin này nêu rõ file, việc cần làm, hạn phản hồi và nơi trả lời; người đọc có thể nhận việc ngay mà không phải hỏi “có chuyện gì?”.

**4. Viết lại tin nhắc deadline**

Đặt **Schedule Send lúc 08:00 sáng hôm sau** trên kênh `#thong-bao`. Trong hội thoại, chỉ Lan xác nhận phần mình vẫn “sắp xong”, nên em chỉ tag Lan; không tự đoán Nam, Hoa hoặc Tuấn còn thiếu việc.

> Hôm nay là hạn nộp báo cáo SmartCampus. @Lan, phần em đang làm đã hoàn tất chưa? Nếu chưa, vui lòng trả lời trong thread này phần còn lại và thời điểm dự kiến xong để nhóm kịp ghép vào báo cáo. Những bạn đã hoàn tất không cần phản hồi.

## Phần 4. Thông báo tổng hợp

Đây là **mẫu tin nhắn để đăng sau khi các thao tác được hoàn tất**; đề bài không cung cấp tài khoản Drive hoặc email giảng viên để em thực hiện thật.

> Đăng tại `#thong-bao`: Thư mục dự án `SmartCampus` đã được bật Auto Sync; mọi người hãy lưu file vào thư mục chung và kiểm tra trạng thái đồng bộ trước khi tắt máy. `BaoCao_CuoiKy_SmartCampus.docx` đã được chia sẻ riêng cho giảng viên với quyền Viewer, phạm vi Restricted để thầy/cô xem mà không sửa được. @Lan, phần em đang làm vẫn chưa được xác nhận hoàn tất; vui lòng cập nhật phần còn lại và thời điểm xong trong thread của tin nhắn này để nhóm ghép báo cáo kịp hạn nộp. Cảm ơn mọi người.

