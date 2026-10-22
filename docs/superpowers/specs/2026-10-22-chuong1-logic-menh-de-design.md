# Đặc tả Thiết kế: Tái cấu trúc Sư phạm & Visual Bài giảng Cấu trúc Rời rạc - Chương 1

- **Tài liệu nguồn:** `Hoc/BaiGiang.tex/Chuong1/Chuong1.tex`
- **Tài liệu đích:** `Hoc/HocHanh/Chuong1/Chuong1.tex`
- **Mục tiêu:** Xây dựng lại nội dung học tập Chương 1 (Logic Mệnh đề và Suy luận) theo định dạng Beamer 16:9 với triết lý sư phạm 3 tầng (Trực giác $\to$ Hình thức toán học $\to$ Ứng dụng & Phòng ngừa cạm bẫy), giao diện Cozy ấm áp, trực quan, hỗ trợ tối đa cho sinh viên tiếp thu và đạt kết quả cao.

---

## 1. Kiến trúc Tổng thể & Hệ thống Giao diện Cozy (Theme & Layout)

### 1.1. Cấu hình Kỹ thuật LaTeX Beamer
- **Documentclass:** `\documentclass[aspectratio=169, 10pt]{beamer}`
- **Bảng mã và font:** `\usepackage[utf8]{inputenc}`, `\usepackage[T5]{fontenc}`, `\usepackage[vietnamese]{babel}`
- **Gói toán học & bảng biểu:** `amsmath`, `amssymb`, `amsfonts`, `booktabs`, `array`, `tabularx`
- **Gói giao diện trực quan:** `xcolor`, `tcolorbox` (với thư viện `skins`, `breakable`), `tikz`
- **Tỉ lệ trình chiếu:** Chuẩn 16:9 hiện đại, tối ưu không gian hiển thị slide 2 cột và các hộp tư duy.

### 1.2. Bảng màu Cozy (Warm, Aesthetic & High-Contrast Palette)
- `cozyBg` (`RGB{250, 248, 245}` / `#FAF8F5`): Màu nền giấy kem ấm áp, dịu mắt khi học tập lâu.
- `cozySlate` (`RGB{44, 62, 80}` / `#2C3E50`): Màu chữ và tiêu đề cấu trúc chính, tương phản trang nhã.
- `cozyWarm` (`RGB{211, 84, 0}` / `#D35400`): Màu cam đất Terracotta nhấn mạnh khái niệm trọng tâm.
- `cozyAmber` (`RGB{230, 126, 34}` / `#E67E22`): Điểm nhấn phụ và tiêu đề hộp mẹo giải.
- `cozyTrue` (`RGB{46, 125, 50}` / `#2E7D32`): Màu xanh lá Forest dịu biểu thị Chân trị Đúng ($1 / \text{Đ}$).
- `cozyFalse` (`RGB{192, 57, 43}` / `#C0392B`): Màu đỏ gạch Brick Red biểu thị Chân trị Sai ($0 / \text{S}$).
- `cozyMuted` (`RGB{127, 140, 141}` / `#7F8C8D`): Màu xám ấm cho ghi chú và đường kẻ phụ.

### 1.3. Hệ thống 5 Hộp `tcolorbox` Chuyên biệt
1. **`cozyDef` (Khung Định nghĩa Chuẩn mực):**
   - Nền trắng/kem nhẹ, viền `cozySlate`, tiêu đề đậm. Dùng cho các định nghĩa toán học hình thức.
2. **`cozyInsight` (Khung Trực giác & Mô hình Tư duy):**
   - Viền xanh sage/ấm, icon bóng đèn 💡. Trả lời câu hỏi: *"Bản chất của khái niệm này là gì trong đời sống & lập trình?"*.
3. **`cozyTrap` (Khung Cạm bẫy / Cảnh báo Lỗi Sai):**
   - Viền đỏ gạch `cozyFalse`, icon cảnh báo ⚠️. Nhấn mạnh lỗi $80\%$ sinh viên hay mắc trong bài thi.
4. **`cozyMethod` (Khung Quy trình & Mẹo Giải nhanh):**
   - Viền cam đất `cozyWarm`, icon cờ lê/công cụ 🛠️. Đánh số bước thao tác cụ thể ($B_1 \to B_2 \to B_3$).
5. **`cozyExample` (Khung Ví dụ & Lời giải mẫu):**
   - Viền xám ấm `cozyMuted`, trình bày đối chiếu 2 cột biểu thức và lý do.

---

## 2. Thiết kế Sư phạm Chi tiết theo 4 Phần Nội dung

### Phần 1: Khái niệm Mệnh đề & Phân loại (Slide 1 -- 5)
- **Slide 1: Trang tiêu đề & Giới thiệu Chương 1:** Thiết kế trang nhã, ấm cúng, nêu rõ mục tiêu và lộ trình học tập.
- **Slide 2: Mệnh đề là gì? (Bản chất nhị phân):**
  - Khái niệm câu khẳng định có giá trị khách quan Đúng ($1$) hoặc Sai ($0$).
  - Đối chiếu song song 2 bảng: *Câu là mệnh đề* vs *Câu không phải mệnh đề* kèm giải thích cặn kẽ (câu cảm thán, đánh giá chủ quan, câu hỏi, vị từ chứa biến, nghịch lý).
- **Slide 3: Ký hiệu, Chân trị & Phân loại:**
  - Biến mệnh đề $p, q, r, \dots$
  - Chân trị trong toán học vs Bit nhị phân trong máy tính ($1/\text{Đ}$ và $0/\text{S}$).
  - Phân loại: Mệnh đề sơ cấp (nguyên tử) vs Mệnh đề phức hợp.

### Phần 2: 6 Toán tử Logic Cơ bản & Phân tích Trực giác (Slide 6 -- 16)
- **Slide 6: Phép Phủ định ($\neg p, \bar{p}$):** Bảng chân lý, cơ chế đảo bit, ví dụ ngôn ngữ tự nhiên.
- **Slide 7: Phép Tuyển thường ($\lor$) vs Phép Tuyển loại ($\oplus$ XOR):**
  - Phân tích sự khác biệt sâu sắc giữa *Inclusive OR* (có ít nhất 1 cái đúng) và *Exclusive OR* (chỉ được chọn 1 trong 2).
  - Ví dụ thực tế: Điều kiện học bổng vs Thực đơn bữa trưa.
- **Slide 8: Phép Hội ($\land$ AND):** Đúng khi và chỉ khi cả hai cùng đúng. Liên hệ phép nhân logic và điều kiện gộp.
- **Slide 9: Phép Kéo theo ($p \to q$) - Bản chất & Giải mã Vacuous Truth:**
  - Định nghĩa hình thức và bảng chân lý.
  - Phân tích cặn kẽ tình huống $p$ Sai $\implies p \to q$ Đúng thông qua Mô hình Lời hứa / Hợp đồng thưởng điểm.
  - Phân tích mối quan hệ: $p$ là điều kiện đủ, $q$ là điều kiện cần.
- **Slide 10: Phép Tương đương ($p \leftrightarrow q$):** Bản chất kéo theo 2 chiều $(p \to q) \land (q \to p)$. Chân trị đúng khi cùng đúng hoặc cùng sai.
- **Slide 11 -- 12: Kiểm tra Phản xạ Chân trị (Quick Quiz):**
  - Hệ thống các câu trắc nghiệm phản xạ từ bài giảng gốc, kèm hộp phân tích lý do chọn đáp án ngay trong slide.

### Phần 3: Biểu thức Phức hợp & Các Luật Tương đương Logic (Slide 13 -- 27)
- **Slide 13 -- 14: Lập Bảng Chân lý & Mẹo Nhị phân (Binary Trick):**
  - Hướng dẫn lập bảng $2^n$ dòng: Mẹo điền xen kẽ bit $1/0$ đảm bảo không sót dòng.
  - Ví dụ lập bảng chân lý 2 biến và 3 biến (8 dòng) cho $(p \lor q) \to (p \land \neg r)$.
- **Slide 15 -- 18: Hệ thống 11 Luật Tương đương theo 3 Cụm Dễ Nhớ (Memory Chunking):**
  - *Cụm 1 (Tương đồng Số học):* Giao hoán, Kết hợp, Đồng nhất, Nuốt, Phủ định kép.
  - *Cụm 2 (Đặc thù Đại số Boole):* Lũy đẳng, Phân phối 2 chiều, Hấp thụ, Phần bù.
  - *Cụm 3 (Chuyển đổi Toán tử Phức tạp):* Luật De Morgan, Luật Kéo theo ($p \to q \equiv \neg p \lor q$), Luật Phản đảo, Luật Tương đương.
  - 💡 *Nguyên lý Đối ngẫu (Principle of Duality):* Mẹo ghi nhớ giảm $50\%$ công sức học thuộc.
- **Slide 19 -- 20: Phương pháp Biến đổi Đại số Mệnh đề (Không cần kẻ bảng):**
  - Khung quy trình 3 bước: Khử mũi tên $\to$ Đưa phủ định vào trong $\to$ Gom nhóm & Rút gọn.
- **Slide 21 -- 26: Lời giải Chi tiết Bài tập Tương đương & Hằng đúng:**
  - Chứng minh $p \to (q \to r) \equiv (p \land q) \to r$.
  - Chứng minh hằng đúng $(p \land q) \to (p \lor q) \equiv \mathbf{T}$.
  - Giải chi tiết Bài 2 và Bài 5 trong bài giảng gốc bằng bảng 2 cột (Biểu thức $\longleftrightarrow$ Tên luật áp dụng).

### Phần 4: Quy tắc Suy luận & Bài toán Thực tế (Slide 28 -- 42)
- **Slide 28 -- 29: Bản chất của Lập luận Hợp lệ (Valid Argument):**
  - Khái niệm: Tiền đề đúng $\implies$ Kết luận bắt buộc phải đúng.
  - Hình thức hóa toán học: $(P_1 \land P_2 \land \dots \land P_k) \to C$ là hằng đúng.
- **Slide 30 -- 32: 8 Quy tắc Suy luận Nền tảng:**
  - Modus Ponens, Modus Tollens, Tam đoạn luận giả định, Tam đoạn luận tuyển, Cộng, Rút gọn, Ghép hội, Phân giải (Resolution).
- **Slide 33 -- 34: ⚠️ Hai Cạm bẫy Ngụy biện Phổ biến nhất (Formal Fallacies):**
  - *Ngụy biện khẳng định kết luận:* $p \to q, q \vdash p$ (SAI!).
  - *Ngụy biện phủ định tiền đề:* $p \to q, \neg p \vdash \neg q$ (SAI!).
  - Đối chiếu ví dụ thực tế và giải mã loạt bài tập trắc nghiệm suy luận ngôn ngữ tự nhiên (d, e, f, g, h, i).
- **Slide 35 -- 37: Lời giải Chi tiết Bài tập Kiểm tra Suy luận Hình thức:**
  - Giải chi tiết bài tập (a), (b), (c) qua bảng suy luận chuẩn mực.
- **Slide 38 -- 41: Chinh phục Bài toán Thực tế (Bài toán Dã ngoại "Đi bơi hay đi canô?"):**
  - Quy trình 4 bước: Nguyên tử hóa biến $\to$ Hình thức hóa giả thiết $\to$ Lập chiến lược suy diễn $\to$ Bảng chứng minh 8 bước.
  - Phân tích rõ nét lý do của từng bước dẫn đến kết luận $t$ ("Chúng ta sẽ về nhà trước khi mặt trời lặn").
- **Slide 42: Slide Tổng kết & Bản đồ Tư duy Chương 1:** Khái quát toàn bộ liên kết logic của chương.

---

## 3. Chiến lược Kiểm thử & Xác thực (Verification Strategy)
1. **Biên dịch sạch với `pdflatex`:**
   - Biên dịch lệnh: `pdflatex -interaction=nonstopmode -output-directory=Hoc/HocHanh/Chuong1 Hoc/HocHanh/Chuong1/Chuong1.tex`
   - Đảm bảo mã thoát lệnh bằng $0$ (exit code 0), không có lỗi cú pháp TeX.
2. **Kiểm soát Tràn dòng và Bố cục trực quan:**
   - Sử dụng `columns` và tỉ lệ `wd` hợp lý để không xảy ra Overfull `\hbox` / `\vbox` nghiêm trọng.
   - Các bảng chân lý và bảng chứng minh sử dụng `booktabs`, căn lề cân đối và nổi bật các dòng/cột kết quả.
3. **Độ chính xác Toán học:**
   - Từng ký hiệu, dấu tương đương ($\equiv$), kéo theo ($\to$), quy tắc suy luận ($\vdash$ / $\therefore$) phải chuẩn xác tuyệt đối theo chuẩn quốc tế và giáo trình đại học.
