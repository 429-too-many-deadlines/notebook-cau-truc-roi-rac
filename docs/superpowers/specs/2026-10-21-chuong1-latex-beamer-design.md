# Thiết kế chi tiết: Chuyển đổi Slide Chương 1 sang LaTeX Beamer (Hoc.tex/Chuong1)

- **Ngày tạo:** 2026-10-21
- **Môn học:** Cấu Trúc Rời Rạc / Toán Rời Rạc (UIT)
- **Tác giả tài liệu gốc:** TS. Nguyễn Văn Hợi
- **File gốc:** `Hoc/Chuong1.pdf`
- **File đích:** `Hoc.tex/Chuong1/Chuong1.tex`

---

## 1. Mục tiêu và Phạm vi

Chuyển đổi toàn diện và bám sát nội dung từ file slide bài giảng `Hoc/Chuong1.pdf` sang định dạng LaTeX Beamer:
- Tái lập bố cục slide chuẩn tỉ lệ 16:9 (`aspectratio=169`), nền trắng, tiêu đề màu xanh dương chuẩn UIT (`uitblue`).
- Tái lập thanh chân trang 3 khoang: `TS. Nguyễn Văn Hợi` | `UIT – Cấu Trúc Rời Rạc` | `x / 35`.
- Chế độ hoàn chỉnh từng slide (không lặp qua 283 trang hiệu ứng `\pause`), đảm bảo cô đọng trong đúng 35 slide chuẩn, hiển thị đầy đủ mọi bảng chân trị, ví dụ, công thức và đáp án/lời giải.
- Đóng gói toàn bộ cấu hình, macro và 35 frames trong một file duy nhất `Hoc.tex/Chuong1/Chuong1.tex`.

---

## 2. Cấu trúc Preamble & Theme Beamer

### 2.1 Khai báo Document Class
```latex
\documentclass[aspectratio=169, 11pt]{beamer}
\setbeamertemplate{navigation symbols}{}
\setbeamercolor{background canvas}{bg=white}
```

### 2.2 Gói hỗ trợ Tiếng Việt và Toán học
```latex
\usepackage[utf8]{inputenc}
\usepackage[T5]{fontenc}
\usepackage[vietnamese]{babel}
\usepackage{amsmath, amssymb, amsfonts}
\usepackage{array, tabularx, booktabs}
\usepackage{xcolor}
```

### 2.3 Bảng màu và Định dạng Tiêu đề
```latex
\definecolor{uitblue}{RGB}{0, 0, 204}      % Xanh dương tiêu đề
\definecolor{footleft}{RGB}{0, 0, 204}     % Khoang trái footline
\definecolor{footmid}{RGB}{0, 0, 153}      % Khoang giữa footline
\definecolor{footright}{RGB}{0, 0, 115}    % Khoang phải footline

\setbeamercolor{frametitle}{fg=uitblue}
\setbeamerfont{frametitle}{series=\bfseries, size=\large}
```

### 2.4 Tùy biến Footline 3 khoang
```latex
\setbeamertemplate{footline}{%
  \leavevmode%
  \hbox{%
    \begin{beamercolorbox}[wd=.333333\paperwidth,ht=2.5ex,dp=1ex,left]{footleftbox}%
      \hspace*{2ex}\textbf{\color{white}\small TS. Nguyễn Văn Hợi}%
    \end{beamercolorbox}%
    \begin{beamercolorbox}[wd=.333333\paperwidth,ht=2.5ex,dp=1ex,center]{footmidbox}%
      \textbf{\color{white}\small UIT -- Cấu Trúc Rời Rạc}%
    \end{beamercolorbox}%
    \begin{beamercolorbox}[wd=.333334\paperwidth,ht=2.5ex,dp=1ex,right]{footrightbox}%
      \textbf{\color{white}\small \insertframenumber{} / 35}\hspace*{2ex}%
    \end{beamercolorbox}%
  }%
  \vskip0pt%
}
```

---

## 3. Danh mục 35 Slide chi tiết

### Nhóm 1: Mở đầu về Mệnh đề (Slide 1 -- 2)
1. **Slide 1:** `Mệnh đề là gì?` -- Định nghĩa mệnh đề (khẳng định Đúng hoặc Sai). Ví dụ và phản ví dụ kèm phân loại (Hà Nội là thủ đô $\to$ Đúng; $0 > 2 \to$ Sai; 3 là số nguyên tố $\to$ Đúng; $x > 3$, câu hỏi, mệnh lệnh $\to$ Không phải mệnh đề).
2. **Slide 2:** `Ký hiệu và Phân loại` -- Biến mệnh đề $p, q, r, s...$, chân trị Đúng ($1$/T/Đ), Sai ($0$/F/S). Phân loại mệnh đề sơ cấp (nguyên tử) và mệnh đề phức hợp.

### Nhóm 2: Các toán tử Logic (Slide 3 -- 9)
3. **Slide 3:** `2. Các toán tử Logic` (Section divider frame `[plain]`, chữ lớn xanh ở giữa kèm thanh kẻ).
4. **Slide 4:** `1. Phép phủ định (NOT)` -- Ký hiệu $\neg p$ hoặc $\bar{p}$, bảng chân lý hoàn chỉnh ($p=0 \to \bar{p}=1; p=1 \to \bar{p}=0$).
5. **Slide 5:** `2. Phép hoặc (OR) và 3. Phép giao (AND)` -- Ký hiệu $\lor, \land$, định nghĩa và 2 bảng chân lý song song (chân trị $0, 1$).
6. **Slide 6:** `4. Phép tuyển loại (XOR)` -- Ký hiệu $\oplus$, định nghĩa, bảng chân trị và ví dụ thực tế ("Món ăn kèm súp hoặc salad").
7. **Slide 7:** `5. Phép kéo theo và 6. Phép tương đương` -- Ký hiệu $\rightarrow, \leftrightarrow$, giả thiết -- kết luận, điều kiện cần/đủ, 2 bảng chân lý.
8. **Slide 8:** `Hiểu phép kéo theo qua một lời hứa` -- Ví dụ lời hứa phụ huynh "Nếu được điểm 10 thì thưởng 100k" với 4 trường hợp chân lý.
9. **Slide 9:** `Kiểm tra nhanh` -- Trắc nghiệm tính đúng sai của các phép toán logic cơ bản kèm đáp án.

### Nhóm 3: Biểu thức phức hợp & Tương đương Logic (Slide 10 -- 23)
10. **Slide 10:** `3. Biểu thức phức hợp` (Section divider frame `[plain]`).
11. **Slide 11:** `Bảng chân lý của các Mệnh đề phức hợp` -- Ví dụ bảng chân lý từng bước cho biểu thức $(p \lor \neg q) \rightarrow (p \land q)$.
12. **Slide 12:** `Ví dụ 2: Kiểm tra tương đương logic` -- Bảng chân lý chứng minh luật De Morgan $\neg(p \lor q) \equiv \neg p \land \neg q$.
13. **Slide 13:** `Ví dụ 3: Biểu thức có 3 biến` -- Bảng chân trị 8 dòng ($2^3 = 8$) cho $(p \lor q) \rightarrow r$.
14. **Slide 14:** `Bài tập: Chứng minh tương đương logic qua bảng chân lý:` -- Đề bài câu (a), (b), (c).
15. **Slide 15:** `Bảng các tương đương Logic (Phần 1)` -- Bảng tổng hợp các luật: Đồng nhất, Nuốt (thống trị), Lũy đẳng, Phủ định kép, Giao hoán, Kết hợp, Phân phối.
16. **Slide 16:** `Lời giải: Câu (b)` -- Bảng chân lý chi tiết lời giải câu (b).
17. **Slide 17:** `Lời giải: Câu (c)` -- Bảng chân lý chi tiết lời giải câu (c).
18. **Slide 18:** `Bảng các tương đương Logic (Phần 2)` -- Bảng tổng hợp các luật: De Morgan, Kéo theo ($p \rightarrow q \equiv \neg p \lor q$), Đảo/Phản đảo, Tương đương, Hấp thụ.
19. **Slide 19:** `Ví dụ: Chứng minh tương đương Logic` -- Biến đổi tương đương logic từng bước có chú thích tên luật áp dụng.
20. **Slide 20:** `Ví dụ: Chứng minh một hằng đúng` -- Chứng minh biểu thức là tautology bằng đại số logic.
21. **Slide 21:** `Bài tập: Áp dụng các luật logic` -- Danh sách 5 bài tập biến đổi logic.
22. **Slide 22:** `Lời giải: Bài 2` -- Từng bước biến đổi chi tiết.
23. **Slide 23:** `Lời giải: Bài 5` -- Từng bước biến đổi chi tiết.

### Nhóm 4: Suy luận và Chứng minh & Bài toán thực tế (Slide 24 -- 35)
24. **Slide 24:** `5. Suy luận và Chứng minh` (Section divider frame `[plain]`).
25. **Slide 25:** `Các quy tắc suy luận (Phần 1)` -- Modus Ponens, Modus Tollens, Tam đoạn luận giả thiết, Tam đoạn luận tuyển.
26. **Slide 26:** `Các quy tắc suy luận (Phần 2)` -- Quy tắc Cộng, Rút gọn, Hội, Phân giải (Resolution).
27. **Slide 27:** `Bài tập: Kiểm tra tính hợp lệ của các lập luận` -- Đề bài bài (a), (b), (c).
28. **Slide 28:** `Lời giải chi tiết: Bài (a)` -- Hình thức hóa và áp dụng quy tắc suy luận.
29. **Slide 29:** `Lời giải chi tiết: Bài (b)` -- Hình thức hóa và áp dụng quy tắc suy luận.
30. **Slide 30:** `Lời giải chi tiết: Bài (c)` -- Hình thức hóa và áp dụng quy tắc suy luận.
31. **Slide 31:** `Bài toán thực tế` -- Tình huống suy luận thực tế (phân tích giả thiết).
32. **Slide 32:** `Bài toán thực tế (tt)` -- Các bước suy luận giải quyết bài toán.
33. **Slide 33:** `Bài toán: Đi bơi hay đi canô?` -- Đề bài câu đố logic cuộc dã ngoại.
34. **Slide 34:** `Bài toán: Đặt mệnh đề và hình thức hóa` -- Đặt các biến mệnh đề $p, q, r, s...$ và các biểu thức tiền đề.
35. **Slide 35:** `Bài toán: Lời giải` -- Các bước suy luận logic từng bước đi đến kết luận cuối cùng.

---

## 4. Kiểm thử và Nghiệm thu

- Biên dịch thử nghiệm: `pdflatex -interaction=nonstopmode -output-directory=Hoc.tex/Chuong1 Hoc.tex/Chuong1/Chuong1.tex`.
- Kiểm tra số trang kết quả trong PDF: đúng 35 trang.
- Kiểm tra tính toàn vẹn của ký hiệu toán học, bảng chân lý, không lỗi ngắt dòng hay tràn lề.

