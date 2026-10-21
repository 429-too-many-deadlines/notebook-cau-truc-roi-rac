# Cấu Trúc Rời Rạc (Toán Rời Rạc)

Kho lưu trữ tài liệu học tập, slide bài giảng gốc và mã nguồn LaTeX chuyển đổi cho môn học **Cấu Trúc Rời Rạc** (Toán Rời Rạc).

---

## 📁 Cấu trúc thư mục

```text
CauTrucRoiRac/
├── BaiGiang/                           # Slide bài giảng gốc dạng PDF
│   └── Chuong1.pdf                     # Slide gốc Chương 1 (283 trang hiệu ứng / overlays)
│
├── Hoc/
│   └── BaiGiang.tex/                   # Mã nguồn LaTeX Beamer của các chương
│       └── Chuong1/                    # Chương 1: Logic Mệnh đề và Suy luận
│           ├── Chuong1.tex             # Mã nguồn Beamer chuẩn tỉ lệ 16:9 (35 slide hoàn chỉnh)
│           └── Chuong1.pdf             # File PDF đầu ra đã biên dịch
│
├── docs/                               # Tài liệu đặc tả và kế hoạch phát triển
│   └── superpowers/
│       ├── specs/                      # Thiết kế chi tiết (Design Specs)
│       └── plans/                      # Kế hoạch triển khai (Implementation Plans)
│
└── README.md                           # Giới thiệu và hướng dẫn sử dụng
```

---

## 📖 Nội dung các chương

### Chương 1: Logic Mệnh đề và Suy luận
Chuyển đổi hoàn chỉnh từ slide bài giảng gốc sang [Chuong1.tex](file:///home/fullstuck_developer/Workspace/CITD/HocHanh/CauTrucRoiRac/Hoc/BaiGiang.tex/Chuong1/Chuong1.tex), cô đọng thành **35 slide chuẩn tỉ lệ 16:9**:

1. **Khái niệm Mệnh đề và Phân loại (Slide 1 -- 2):** Định nghĩa mệnh đề (khẳng định Đúng/Sai), ví dụ và phản ví dụ thực tế, biến mệnh đề ($p, q, r$), chân trị ($1/0$), mệnh đề sơ cấp vs mệnh đề phức hợp.
2. **Các toán tử Logic cơ bản (Slide 3 -- 9):** Phép phủ định ($\neg p, \bar{p}$), phép tuyển ($\lor$), phép hội ($\land$), phép tuyển loại XOR ($\oplus$), phép kéo theo ($\rightarrow$), phép tương đương ($\leftrightarrow$), phân tích bản chất phép kéo theo qua ví dụ lời hứa, bài tập trắc nghiệm kiểm tra nhanh chân trị.
3. **Biểu thức phức hợp & Tương đương Logic (Slide 10 -- 23):** Lập bảng chân lý biểu thức 2 biến và 3 biến (8 dòng); hệ thống các luật tương đương logic (Đồng nhất, Nuốt, Lũy đẳng, Phủ định kép, Giao hoán, Kết hợp, Phân phối, De Morgan, Hấp thụ, Kéo theo, Tương đương); phương pháp chứng minh tương đương logic và hằng đúng (Tautology) bằng đại số mệnh đề; bài tập & lời giải chi tiết.
4. **Suy luận, Chứng minh & Bài toán thực tế (Slide 24 -- 35):** 8 quy tắc suy luận nền tảng (Modus Ponens, Modus Tollens, Tam đoạn luận giả định, Tam đoạn luận tuyển, Quy tắc cộng, Rút gọn, Hội, Phân giải); 9 bài tập kiểm tra tính hợp lệ của lập luận kèm lời giải chi tiết; bài toán thực tế ông Minh và câu đố logic dã ngoại *"Đi bơi hay đi canô?"* kèm bảng suy luận 8 bước.

---

## 🛠️ Hướng dẫn Biên dịch LaTeX

### Yêu cầu môi trường
- Hệ thống TeX Live (hoặc MiKTeX) hỗ trợ:
  - `pdflatex`
  - Gói tài liệu trình chiếu `beamer`
  - Bảng mã và font Tiếng Việt `vntex` (`\usepackage[T5]{fontenc}`, `\usepackage[vietnamese]{babel}`)
  - Các gói toán học: `amsmath`, `amssymb`, `amsfonts`, `booktabs`, `array`

### Lệnh biên dịch

Biên dịch trực tiếp từ thư mục gốc:
```bash
pdflatex -interaction=nonstopmode -output-directory=Hoc/BaiGiang.tex/Chuong1 Hoc/BaiGiang.tex/Chuong1/Chuong1.tex
```

Hoặc di chuyển vào thư mục chương để biên dịch:
```bash
cd Hoc/BaiGiang.tex/Chuong1
pdflatex -interaction=nonstopmode Chuong1.tex
```
*(Nên chạy lệnh 2 lần để cập nhật số trang `\inserttotalframenumber` và các tham chiếu mục lục).*

