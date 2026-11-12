# Nhặt — kho sticker cá nhân ngay trên bàn phím Android

> Thấy thích. Nhặt lại. Gửi ngay.

Tên **Nhặt** là tên tạm trong lúc lên ý tưởng; repository hiện tên `stiker`.
Tài liệu lưu lại ý tưởng và câu chuyện sản phẩm ngày 12/11/2026 để triển khai sau. Đây là bản định hướng, chưa phải ứng dụng chạy được hay cam kết tính năng.

## Câu chuyện bắt đầu

Muốn tự làm sticker từ tranh vẽ, ảnh đẹp, meme hoặc khung hình trong phim. Trải nghiệm bộ sticker của Zalo khá tiện, nhưng bộ đó chủ yếu dùng trong Zalo. Nếu tự cắt từng hình rồi lưu như ảnh bình thường, mỗi lần chat lại phải mò thư viện, tìm đúng hình; tìm xong có khi đã qua mất câu chuyện.

Mong muốn thật sự: có một kho biểu cảm của riêng mình, đang chat là lấy ra dùng được ngay từ bàn phím. Việc lưu dạng ảnh bên dưới không phải vấn đề; vấn đề là cách thu thập, sắp xếp và gọi ảnh ra.

Ý tưởng phát triển từ “app cắt sticker” thành:
**Thấy ảnh thích → chia sẻ vào Nhặt → giữ nguyên hoặc cắt nền → lưu vào bộ → mở sticker từ bàn phím khi chat.**

## Hướng sản phẩm

Một ứng dụng Android, cài bằng một APK, gồm hai phần:

- **App quản lý và tạo sticker:** nhận ảnh, chỉnh sửa, đặt tên/tag, chia bộ.
- **Bàn phím sticker (IME):** hiển thị kho ngay dưới ô nhập tin nhắn để chọn ảnh trong lúc trò chuyện.

Thêm sticker mới chỉ lưu dữ liệu vào máy, không phải đóng lại APK.

“Kéo ảnh vào” là cách hình dung ban đầu. Luồng thực tế ưu tiên **menu Chia sẻ của Android → Nhặt**, vì kéo thả không dùng được nhất quán giữa các app. Vẫn có nút chọn ảnh từ máy.

## Luồng sử dụng chính

### 1. Gặp ảnh thích

Trong thư viện hoặc app hỗ trợ chia sẻ ảnh: bấm **Chia sẻ → Nhặt**.
Với nội dung chỉ chia sẻ được đường link, không giả định luôn lấy được ảnh: hướng dẫn lưu ảnh hoặc chụp màn hình rồi nhập.

Nguồn đầu vào: ảnh trong máy, tranh tự vẽ, meme, ảnh chụp màn hình/khung hình phim. Trích khung hình trực tiếp từ video để sau.

### 2. Tạo sticker

Hiện bản xem trước với lựa chọn:

- **Giữ nguyên:** phù hợp meme có chữ hoặc hình cần cả bối cảnh.
- **Xóa nền:** tách nhân vật/chủ thể.
- Cắt khung, tẩy/khôi phục thủ công; viền trắng và thêm chữ có thể bổ sung sau.

Chọn bộ, thêm tên/tag nếu muốn, bấm **Lưu sticker**. Không bắt buộc thao tác dài chỉ để lưu một ảnh.

### 3. Kho cá nhân

Lưới sticker, các bộ như “Mèo”, “Meme”, “Tranh của tui”.
Tìm theo tên/tag/cảm xúc như “cạn lời”, “bất lực”, “đồng ý”.
Có **Vừa thêm**, **Gần đây**, **Yêu thích**; sticker vừa lưu xuất hiện ngay để dùng.

### 4. Dùng khi chat

Mở bàn phím Nhặt → chọn bộ hoặc tìm → chạm sticker để chuyển ảnh vào app chat hỗ trợ.
Tùy app, có thể mở màn xem trước và cần bấm gửi thêm.

Bản thử là bàn phím tập trung vào sticker, có nút chuyển về bàn phím gõ chữ đang dùng. Android cần người dùng tự bật/chọn IME trong cài đặt; app không tự bật bàn phím.
Nếu việc đổi bàn phím quá phiền, đánh giá tiếp bàn phím chữ với tiếng Việt. Chưa mặc định xây một bộ gõ tiếng Việt hoàn chỉnh ngay từ đầu.

## Phác thảo giao diện

Bản hình dung đã trao đổi có bốn màn hình, tông tím nhạt, nền trắng, sticker nổi bật:

1. **Gặp ảnh thích:** ảnh đang xem và menu Chia sẻ với biểu tượng Nhặt.
2. **Lưu thành sticker:** xem trước, Giữ nguyên / Xóa nền, Viền, Thêm chữ, chọn bộ, Lưu sticker.
3. **Kho của tui:** ô tìm kiếm, các bộ, lưới ảnh và nhãn Mới thêm.
4. **Lấy ngay lúc chat:** cuộc trò chuyện phía trên, vùng sticker thay vị trí phím chữ phía dưới; tab Gần đây / Yêu thích / Bộ sưu tập, tìm kiếm và nút đổi bàn phím.

Ví dụ: bạn nhắn “Deadline tới đâu rồi?” → mở Nhặt → chọn mèo nằm bẹp → đưa vào cuộc chat.

Ảnh mockup trong cuộc trò chuyện là minh họa thiết kế, chưa chứng minh việc gửi sticker thực tế. Tài liệu này mô tả lại bố cục để không phụ thuộc ảnh đính kèm trong chat.

## Giới hạn kỹ thuật cần hiểu đúng

- Android không có chuẩn sticker gốc chung cho mọi ứng dụng chat.
- Không thể tùy ý chèn một tab của mình vào Gboard. IME riêng là hướng chủ động; tích hợp bàn phím khác cần cơ chế họ hỗ trợ.
- Hướng thử: IME gửi ảnh bằng cơ chế rich content của Android, ví dụ `InputConnection.commitContent` / `InputConnectionCompat`, kiểm tra MIME type app nhận và cấp quyền đọc URI đúng cách.
- App nhận quyết định hỗ trợ hay không, hiển thị dạng ảnh hay sticker, giữ nền trong hay không, có xem trước hay không. API báo nhận nội dung chưa đủ để kết luận gửi thành công; cần kiểm tra phía cuộc chat.
- Telegram/WhatsApp có cơ chế bộ sticker riêng, có thể nghiên cứu tích hợp sau. Không mặc định bộ sticker sẽ xuất hiện trong tab sticker gốc của Zalo hoặc mọi app.
- Nếu không hỗ trợ gửi từ IME, có thể cung cấp luồng Chia sẻ ảnh từ app quản lý. Đây là phương án dự phòng, không đảm bảo giữ nguyên trải nghiệm bàn phím.

Mục tiêu là truy cập bộ ảnh cá nhân nhanh ở nhiều app, không hứa hoạt động y hệt sticker Zalo trên mọi nền tảng.

## Xóa nền và chi phí

Có hai hướng:

| Hướng | Điểm cần tính |
| --- | --- |
| Xử lý trên thiết bị | Không cần trả API theo lượt; tốc độ, dung lượng model và chất lượng phụ thuộc máy/model. Kiểm tra giấy phép và yêu cầu tải model. |
| API trên mạng | Có thể có hạn mức miễn phí rồi tính phí, cần mạng và tải ảnh lên dịch vụ. Không phải hướng mặc định. |

Ứng viên cần đánh giá: ML Kit Subject Segmentation hoặc model segmentation chạy bằng LiteRT/ONNX Runtime Mobile. Chưa chốt công nghệ/model; cần kiểm tra API, thiết bị hỗ trợ, điều khoản và chất lượng thực tế lúc triển khai.

Tranh vẽ, anime, cảnh phim nhiều chi tiết có thể bị cắt lẹm. Cần giữ bản gốc và cho tẩy/khôi phục thủ công.
Viền trắng là xử lý ảnh thông thường, không cần AI hay API trả phí.

Ưu tiên xử lý tại máy, không bắt buộc tài khoản/server. Không hứa model AI hoạt động offline ngay lần đầu nếu còn cần tải tài nguyên.

## Công nghệ đề xuất để bắt đầu

Đây là đề xuất để thử, chưa phải quyết định đã triển khai:

- Android native: **Kotlin**, **Jetpack Compose** cho phần app; IME dựa trên **InputMethodService**.
- Nhận ảnh qua Android Sharesheet (`ACTION_SEND`, MIME ảnh) và Photo Picker.
- **Room** lưu metadata; file PNG/WebP có alpha cho sticker tĩnh; thumbnail riêng.
- **ContentProvider/FileProvider** chia sẻ nội dung bằng URI và quyền đọc tạm thời theo yêu cầu API nhận.
- Lưu nội bộ làm mặc định, không yêu cầu quyền đọc toàn bộ thư viện nếu Photo Picker/URI được cấp đã đủ.
- Không thu thập nội dung gõ; phân biệt rõ dữ liệu sticker với dữ liệu cuộc trò chuyện.

Dữ liệu gợi ý: Sticker (id, tên, đường dẫn ảnh gốc/ảnh xử lý/thumbnail, bộ, tags, yêu thích, thời điểm tạo và dùng gần nhất), Collection (id, tên, thứ tự).
Tìm kiếm tên/tag trước; chưa cần AI hiểu cảm xúc ảnh.

## Bản đầu cần làm

Ưu tiên kiểm chứng **đưa sticker từ bàn phím vào cuộc chat có tiện và hoạt động không**, trước khi đầu tư AI.

### Mốc 0 — thử đường gửi

- [ ] IME tối giản có khoảng 10 PNG nền trong cố định.
- [ ] Có nút chuyển về bàn phím chữ.
- [ ] Thử trên thiết bị Android thật với các app người dùng hay chat: Messenger, Zalo, Telegram, WhatsApp tùy nhu cầu.
- [ ] Ghi phiên bản Android/app, MIME hỗ trợ, có nhận ảnh không, cách hiển thị, giữ nền trong, có cần bấm gửi, lỗi quyền đọc URI.
- [ ] Đánh giá bất tiện khi chuyển bàn phím.

### Mốc 1 — kho dùng được

- [ ] Nhập ảnh từ Photo Picker và menu Chia sẻ.
- [ ] Nhận PNG đã cắt sẵn, hoặc giữ nguyên ảnh.
- [ ] Tạo/xóa bộ, thêm/xóa sticker.
- [ ] Bàn phím đọc kho, sticker vừa thêm hiện ngay.
- [ ] Gần đây, yêu thích, tìm theo tên/tag.
- [ ] Luồng Chia sẻ ảnh dự phòng khi app nhận không hỗ trợ IME.

### Mốc 2 — tạo sticker tốt hơn

- [ ] Cắt khung, tẩy/khôi phục; thêm viền và chữ.
- [ ] Thử model xóa nền với ảnh chụp, tranh và khung phim.
- [ ] Đo tốc độ, bộ nhớ, dung lượng app trên máy thật.
- [ ] Chọn model/công cụ sau khi kiểm tra chất lượng và giấy phép.

### Để sau

Sticker động, lấy khung hình từ video, xuất bộ cho nền tảng riêng, sao lưu/xuất nhập kho, đồng bộ và bàn phím gõ tiếng Việt đầy đủ. Chưa cần cộng đồng, cửa hàng sticker hay server ở bản đầu.

## Tiêu chí để biết ý tưởng có ích

- Nhận một ảnh qua Chia sẻ, lưu xong là thấy trong kho và bàn phím.
- Không phải mò thư viện ảnh khi đang chat.
- Tìm một hình quen bằng bộ, gần đây hoặc vài từ tag trong vài giây.
- Dữ liệu còn sau khi đóng/mở app.
- Với mỗi app chat đã thử, biết rõ gửi được theo cách nào và giới hạn gì.
- Không làm thao tác gõ chữ bất tiện đến mức người dùng bỏ kho sticker.

## Các quyết định còn mở

- App chat nào cần ưu tiên và phiên bản Android tối thiểu?
- Đổi qua lại giữa IME sticker và bàn phím chữ có đủ tiện không?
- Model xóa nền nào phù hợp ảnh vẽ, chi phí và dung lượng?
- Có cần sao lưu/xuất kho ngay sớm để tránh mất sticker khi gỡ app?

**Nguyên tắc giữ lại:** nhét hình vào dễ, lúc chat lấy ra nhanh. Phần cắt nền cầu kỳ đến sau khi đường dùng chính đã ổn.
