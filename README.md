# Notebook Cấu Trúc Rời Rạc

Kho lưu trữ slide bài giảng và tài liệu ghi chú (notebook) môn **Cấu Trúc Rời Rạc** (Trường Đại học Công nghệ Thông tin – UIT, giảng viên: **TS. Nguyễn Văn Hợi**), được hệ thống hóa và trình bày lại bằng LaTeX để phục vụ học tập và ôn tập.

## Cấu trúc thư mục

```text
notebook-cau-truc-roi-rac/
├── BaiGiang/                  # Slide bài giảng gốc (PDF)
│   ├── Chương 1.pdf
│   ├── Chương 2.pdf
│   ├── Chương 3.pdf
│   ├── Chương 4.pdf
│   ├── Chương 5.pdf
│   └── Chương 6.pdf
├── BaiGiang.tex/              # Ghi chú bài giảng viết bằng LaTeX (.tex & .pdf)
│   ├── Chuong1/
│   │   ├── Chuong1.tex
│   │   └── Chuong1.pdf
│   └── Chuong2/
│       ├── Chuong2.tex
│       └── Chuong2.pdf
├── .gitignore
└── README.md
```

## Nội dung các chương

| Chương | Chủ đề | Slide gốc | Ghi chú LaTeX | Bản PDF biên dịch | Trạng thái |
| :---: | :--- | :---: | :---: | :---: | :---: |
| 1 | Logic mệnh đề, suy luận và logic vị từ | [Chương 1.pdf](BaiGiang/Ch%C6%B0%C6%A1ng%201.pdf) | [Chuong1.tex](BaiGiang.tex/Chuong1/Chuong1.tex) | [Chuong1.pdf](BaiGiang.tex/Chuong1/Chuong1.pdf) | Đã soạn |
| 2 | Tập hợp, các nguyên lý đếm và tổ hợp | [Chương 2.pdf](BaiGiang/Ch%C6%B0%C6%A1ng%202.pdf) | [Chuong2.tex](BaiGiang.tex/Chuong2/Chuong2.tex) | [Chuong2.pdf](BaiGiang.tex/Chuong2/Chuong2.pdf) | Đã soạn |
| 3 | Quan hệ | [Chương 3.pdf](BaiGiang/Ch%C6%B0%C6%A1ng%203.pdf) | — | — | Chưa soạn |
| 4 | Đại số Bool | [Chương 4.pdf](BaiGiang/Ch%C6%B0%C6%A1ng%204.pdf) | — | — | Chưa soạn |
| 5 | Các khái niệm cơ bản của lý thuyết đồ thị | [Chương 5.pdf](BaiGiang/Ch%C6%B0%C6%A1ng%205.pdf) | — | — | Chưa soạn |
| 6 | Cây | [Chương 6.pdf](BaiGiang/Ch%C6%B0%C6%A1ng%206.pdf) | — | — | Chưa soạn |

### Chi tiết các phần đã soạn trong `BaiGiang.tex/`

- **Chương 1 (`Chuong1.tex`)**: Mệnh đề, Các toán tử Logic, Biểu thức phức hợp, Các tương đương Logic, Suy luận và Chứng minh, Vị từ và lượng từ, Phủ định lượng từ, Suy luận với lượng từ.
- **Chương 2 (`Chuong2.tex`)**: Tập hợp và các phép toán, Các nguyên lý đếm cơ bản, Nguyên lý Chuồng bồ câu, Hoán vị, Tổ hợp và Nhị thức Newton.

## Hướng dẫn biên dịch LaTeX

### Yêu cầu môi trường

- Một bản phân phối TeX (ví dụ **TeX Live** hoặc **MiKTeX**) có hỗ trợ `pdflatex` (hoặc `latexmk`) và bộ gõ/gói tiếng Việt (`babel` với tùy chọn `vietnamese`, bảng mã `T5`).
- Các gói LaTeX được sử dụng trong tài liệu: `inputenc`, `fontenc`, `babel`, `mathptmx`, `geometry`, `amsmath`, `amssymb`, `array`, `booktabs`, `enumitem`, `xcolor`, `tikz`, `tcolorbox`, `titlesec`, `needspace`, `parskip`, `hyperref`.

> **Lưu ý:** Các file `.tex` hiện dùng `\usepackage[utf8]{inputenc}` và `\usepackage[T5]{fontenc}`, nên cần biên dịch bằng **`pdflatex`** (không dùng `xelatex` hoặc `lualatex` nếu giữ nguyên phần khai báo này).

### Cách biên dịch

Di chuyển vào thư mục của chương cần biên dịch và chạy `pdflatex` hoặc `latexmk`:

```bash
cd BaiGiang.tex/Chuong1
pdflatex Chuong1.tex
```

Hoặc dùng `latexmk` để tự động xử lý số lần chạy biên dịch:

```bash
cd BaiGiang.tex/Chuong1
latexmk -pdf Chuong1.tex
```

Để dọn dẹp các file tạm sinh ra trong quá trình biên dịch (`.aux`, `.log`, `.out`, ...):

```bash
latexmk -c
```

## Ghi chú

- Các file trong `BaiGiang/` là slide bài giảng gốc của giảng viên **TS. Nguyễn Văn Hợi** (UIT).
- Các file trong `BaiGiang.tex/` là phần ghi chú cá nhân phục vụ mục đích học tập và tra cứu.
