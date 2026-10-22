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
│   ├── BaiGiang.tex/                   # Mã nguồn LaTeX Beamer của các chương (bản cô đọng gốc)
│   │   └── Chuong1/                    # Chương 1: Logic Mệnh đề và Suy luận
│   │       ├── Chuong1.tex             # Mã nguồn Beamer chuẩn tỉ lệ 16:9 (35 slide hoàn chỉnh)
│   │       └── Chuong1.pdf             # File PDF đầu ra đã biên dịch
│   │
│   └── HocHanh/                        # Tài liệu học tập trực quan, sư phạm chuyên sâu
│       └── Chuong1/                    # Chương 1: Logic Mệnh Đề & Suy Luận Toán Học
│           ├── Chuong1.tex             # Slide Beamer 16:9 dải màu Cozy, hệ thống 5 khối tcolorbox (42 slide)
│           └── Chuong1.pdf             # File PDF đầu ra hoàn thiện (42 trang chuẩn xác)
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

### Chương 1 (Bản Trực quan Sư phạm -- `Hoc/HocHanh/Chuong1`): Logic Mệnh Đề & Suy Luận
Tài liệu học tập trực quan Beamer 16:9 phối màu **Cozy**, tích hợp **hệ thống 5 khối nhận thức `tcolorbox`** cô đọng thành **42 slide hoàn chỉnh**:
- **Khái niệm & Định nghĩa cơ bản (`cozyDef` - Xanh Slate):** Nhận diện mệnh đề nhị phân, 6 toán tử logic cơ bản, hệ thống 11 luật tương đương, 8 quy tắc suy luận kinh điển.
- **Trực giác & Mô hình hóa (`cozyInsight` - Xanh Forest):** Mô hình lời hứa giải mã bản chất phép kéo theo ($p \to q$), nguyên lý đối ngẫu (Duality), phân tích ngữ nghĩa thực tế chuỗi suy luận.
- **Phương pháp & Thuật toán (`cozyMethod` - Cam Đất / Amber):** Mẹo nhị phân lập bảng chân trị $2^n$ dòng (Binary Trick), quy trình 3 bước biến đổi đại số mệnh đề không kẻ bảng.
- **Cảnh báo & Cạm bẫy thi cử (`cozyTrap` - Đỏ Gạch / Crimson Red):** Phân biệt điều kiện cần vs đủ, bẫy phân phối số học vs logic Boole, nhận diện 2 ngụy biện diễn dịch phổ biến (Khẳng định kết luận & Phủ định tiền đề).
- **Ví dụ mẫu & Thực hành chi tiết (`cozyExample` - Xám Tro / Muted):** Lập bảng chân lý 8 dòng cho 3 biến, chứng minh tương đương và hằng đúng 2 cột, giải toán ông Minh và bài toán dã ngoại 8 bước.

### Chương 1 (Bản Cô đọng Gốc -- `Hoc/BaiGiang.tex/Chuong1`): Logic Mệnh đề và Suy luận
Chuyển đổi từ slide bài giảng gốc sang [Chuong1.tex](file:///home/fullstuck_developer/Workspace/CITD/HocHanh/CauTrucRoiRac/Hoc/BaiGiang.tex/Chuong1/Chuong1.tex), cô đọng thành **35 slide chuẩn tỉ lệ 16:9**:
1. **Khái niệm Mệnh đề và Phân loại (Slide 1 -- 2):** Định nghĩa mệnh đề, chân trị ($1/0$), mệnh đề sơ cấp vs phức hợp.
2. **Các toán tử Logic cơ bản (Slide 3 -- 9):** $\neg, \lor, \land, \oplus, \to, \leftrightarrow$, phân tích lời hứa, trắc nghiệm nhanh.
3. **Biểu thức phức hợp & Tương đương Logic (Slide 10 -- 23):** Bảng chân lý 2 biến và 3 biến, hệ thống các luật tương đương, chứng minh đại số.
4. **Suy luận, Chứng minh & Bài toán thực tế (Slide 24 -- 35):** 8 quy tắc suy luận, bài tập hợp lệ, bài toán dã ngoại.

---

## 🛠️ Hướng dẫn Biên dịch LaTeX

### Yêu cầu môi trường
- Hệ thống TeX Live (hoặc MiKTeX) hỗ trợ:
  - `pdflatex`
  - Gói tài liệu trình chiếu `beamer`
  - Bảng mã và font Tiếng Việt `vntex` (`\usepackage[T5]{fontenc}`, `\usepackage[vietnamese]{babel}`)
  - Gói đồ họa và khối màu: `tcolorbox`, `tikz`
  - Các gói toán học và bảng biểu: `amsmath`, `amssymb`, `amsfonts`, `booktabs`, `array`, `tabularx`

### Lệnh biên dịch

#### 1. Biên dịch Tài liệu học tập trực quan (`Hoc/HocHanh/Chuong1`)

Biên dịch trực tiếp từ thư mục gốc:
```bash
pdflatex -interaction=nonstopmode -output-directory=Hoc/HocHanh/Chuong1 Hoc/HocHanh/Chuong1/Chuong1.tex
pdflatex -interaction=nonstopmode -output-directory=Hoc/HocHanh/Chuong1 Hoc/HocHanh/Chuong1/Chuong1.tex
```

Hoặc di chuyển vào thư mục chương để biên dịch:
```bash
cd Hoc/HocHanh/Chuong1
pdflatex -interaction=nonstopmode Chuong1.tex && pdflatex -interaction=nonstopmode Chuong1.tex
```
*(Chạy lệnh 2 lần để cập nhật chuẩn xác số trang footline `X / 42` và liên kết mục lục).*

#### 2. Biên dịch Bản cô đọng gốc (`Hoc/BaiGiang.tex/Chuong1`)

Biên dịch trực tiếp từ thư mục gốc:
```bash
pdflatex -interaction=nonstopmode -output-directory=Hoc/BaiGiang.tex/Chuong1 Hoc/BaiGiang.tex/Chuong1/Chuong1.tex
```

Hoặc di chuyển vào thư mục chương để biên dịch:
```bash
cd Hoc/BaiGiang.tex/Chuong1
pdflatex -interaction=nonstopmode Chuong1.tex
```

