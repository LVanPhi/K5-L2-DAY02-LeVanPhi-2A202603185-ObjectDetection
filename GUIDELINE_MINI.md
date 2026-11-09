# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` | Xe con chở người: sedan, SUV, taxi, xe bán tải | Thân thấp, có nắp capo và thường có cốp riêng; taxi vẫn là `car`. Không gán cho xe buýt, xe tải, mô tô |
| `truck` | Xe tải chở hàng, xe đầu kéo, xe chuyên dụng có cabin tách rời phần thùng/thiết bị phía sau | Cabin riêng + thùng hàng hoặc cẩu phía sau (ví dụ xe cứu hộ ở `drive_014`). Xe bán tải/cabin nhỏ thuộc `car` |
| `bus` | Xe buýt, minibus chở khách | Thân dài, nhiều cửa sổ dọc thân, cửa lên xuống khách; xe buýt nối toa vẫn là một xe |
| `van` | Xe van, minivan chở hàng hoặc chở người | Thân hộp liền khối, cao hơn sedan, không có cốp riêng, thường có cửa trượt; ngắn hơn hẳn `bus` |

## Quy tắc chung

- Box bám sát vật thể nghĩa là: bốn cạnh box chạm sát mép phần thân xe nhìn thấy được, không lấy thêm mặt đường, trời, bóng đổ hay xe bên cạnh; mỗi xe một box riêng.
- Vật thể bị che khuất: vẫn vẽ box quanh phần nhìn thấy được nếu nhận diện được lớp; hai xe chồng nhau thì vẽ hai box riêng.
- Vật thể bị cắt bởi rìa ảnh: box chạm đúng rìa ảnh, không đoán phần nằm ngoài khung.
- Vật thể rất nhỏ/mơ hồ: xe ở xa vẫn gán nếu nhận ra lớp (phóng to để vẽ sát); nếu chỉ còn mảnh nhỏ không xác định chắc lớp thì không tự đoán, ghi vào bảng dưới và hỏi giảng viên.

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_014` | Xe cứu hộ có cần cẩu phía sau (giữa ảnh) | `truck` (1) | Cabin riêng + cẩu/thùng chở phía sau, là xe chuyên dụng chở/kéo như xe tải, không phải xe chở khách |
| `drive_024` | Xe ba bánh chở người có mái che, bị nhòe (phía dưới ảnh) | Không gán | Xe ba bánh/xe máy không thuộc bốn lớp của schema (GUIDE §1) |
| `drive_024` | Xe màu bạc thân hộp, cao, cửa trượt (giữa và bên phải ảnh) | `van` (3) | Thân hộp, cao hơn sedan, không có cốp riêng, ngắn hơn xe buýt |
| `dataset/labels/eval` | Nhãn gold eval có vẻ gán một số xe buýt là class 3 (`van`), khác README | Theo đúng schema README: `car`=0, `truck`=1, `bus`=2, `van`=3; không sửa nhãn eval | Làm theo định nghĩa trong tài liệu `.md` |
