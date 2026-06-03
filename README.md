# Notes Docs

Kho tài liệu tĩnh dùng HTML/CSS cơ bản để triển khai bằng GitHub Pages.

Mục tiêu của repo:

- Lưu tài liệu kỹ thuật cá nhân.
- Mỗi tài liệu có bản HTML đọc đẹp trong `docs/`.
- Homepage `index.html` chỉ đóng vai trò thư viện/liệt kê tài liệu.
- Giao diện thống nhất bằng `assets/css/styles.css`.

---

## 1. Cấu trúc thư mục chuẩn

```text
notes/
├── index.html
├── README.md
├── assets/
│   └── css/
│       └── styles.css
├── docs/
│   └── antigravity-google.html
└── *.md
```

Ý nghĩa:

| Đường dẫn | Vai trò |
|---|---|
| `index.html` | Trang chủ, chỉ liệt kê tài liệu. |
| `docs/*.html` | Các trang tài liệu HTML đọc trên web. |
| `assets/css/styles.css` | CSS dùng chung toàn site. |
| `README.md` | Chuẩn style để AI/người dùng tạo docs mới. |
| `*.md` | Markdown gốc hoặc bản nháp, không phải trang đọc chính. |

---

## 2. Quy tắc tổng quan khi AI tạo tài liệu HTML

Khi tạo tài liệu mới, AI phải tuân thủ các luật sau:

1. **Không tạo thêm framework**: không dùng React, Vue, Tailwind, Bootstrap, build tool.
2. **Chỉ dùng HTML/CSS cơ bản**: HTML nằm trong `docs/`, style dùng class có sẵn trong `styles.css`.
3. **Không inline CSS nếu không thật sự cần**.
4. **Không phá layout chung**: header, footer, container, article-shell phải giữ cùng format.
5. **Không link Markdown gốc trên homepage** trừ khi user yêu cầu.
6. **Homepage chỉ hiển thị danh sách tài liệu**, không giải thích cấu trúc project, không quảng cáo HTML/CSS/GitHub Pages.
7. **Tài liệu phải dễ đọc**: heading rõ, đoạn ngắn, bảng khi cần so sánh, code block khi có lệnh/prompt.
8. **Ngôn ngữ mặc định: tiếng Việt**.
9. **Dark mode là mặc định**.
10. **Tối ưu đọc trên mobile**: không tạo bảng quá rộng nếu có thể thay bằng list.

---

## 3. Template HTML chuẩn cho một trang docs

Tạo file mới trong `docs/ten-tai-lieu.html` theo mẫu:

```html
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="Mô tả ngắn của tài liệu." />
  <title>Tên tài liệu | Notes Docs</title>
  <link rel="stylesheet" href="../assets/css/styles.css" />
</head>
<body class="article-page">
  <header class="site-header">
    <div class="container header-inner">
      <a class="brand" href="../index.html" aria-label="Notes Docs Home">
        <span class="brand-mark">N</span>
        <span class="brand-text">Notes Docs</span>
      </a>
      <nav class="site-nav" aria-label="Điều hướng chính">
        <a href="../index.html">Docs</a>
        <a href="https://github.com/anhvu0510/notes" target="_blank" rel="noopener noreferrer">GitHub</a>
      </nav>
    </div>
  </header>

  <main class="article-layout">
    <article class="article-shell">
      <a class="back-link" href="../index.html">← Về trang chủ</a>

      <p class="eyebrow">CATEGORY · TYPE</p>
      <h1>Tên tài liệu</h1>

      <p class="article-note">
        Tóm tắt ngắn tài liệu này dùng để làm gì, ai nên đọc, và kết quả nhận được sau khi đọc.
      </p>

      <h2>1. Khái niệm</h2>
      <p>Nội dung giải thích...</p>

      <h2>2. Cách sử dụng</h2>
      <p>Nội dung hướng dẫn...</p>

      <h2>3. Ứng dụng thực tế</h2>
      <p>Nội dung ví dụ...</p>

      <h2>4. Best practices</h2>
      <ul>
        <li>Quy tắc 1.</li>
        <li>Quy tắc 2.</li>
      </ul>

      <h2>5. Nguồn tham khảo</h2>
      <ul>
        <li><a href="URL" target="_blank" rel="noopener noreferrer">Tên nguồn</a></li>
      </ul>
    </article>
  </main>

  <footer class="site-footer">
    <div class="container footer-inner">
      <p>© Notes Docs</p>
      <a href="https://github.com/anhvu0510/notes" target="_blank" rel="noopener noreferrer">Repository</a>
    </div>
  </footer>
</body>
</html>
```

---

## 4. Chuẩn nội dung tài liệu

Một tài liệu tốt nên có cấu trúc:

```text
1. Khái niệm
2. Vì sao cần dùng
3. Cách cài đặt / chuẩn bị
4. Cách sử dụng cơ bản
5. Cách sử dụng nâng cao
6. Ứng dụng thực tế
7. Workflow khuyến nghị
8. Best practices
9. Lỗi thường gặp
10. Nguồn tham khảo
```

Không bắt buộc đủ 10 phần. Tùy nội dung nhưng phải ưu tiên:

- **Dễ đọc** hơn là dài dòng.
- **Ví dụ thực tế** hơn là lý thuyết suông.
- **Code block rõ ràng** hơn là nhét lệnh vào đoạn văn.
- **Bảng** chỉ dùng khi thật sự giúp so sánh.

---

## 5. Chuẩn heading

Dùng heading theo thứ bậc:

```html
<h1>Tên tài liệu</h1>
<h2>1. Nhóm nội dung lớn</h2>
<h3>1.1 Ý nhỏ</h3>
```

Không nhảy cấp:

```html
<!-- Sai -->
<h1>Title</h1>
<h4>Mục nhỏ</h4>
```

---

## 6. Chuẩn code block

Dùng `pre > code` cho command, prompt, JSON, config:

```html
<pre><code>npm install
npm run build</code></pre>
```

Prompt dài cũng dùng code block:

```html
<pre><code>Hãy phân tích repo này và trả về:
- Kiến trúc tổng quan
- Module chính
- Rủi ro kỹ thuật</code></pre>
```

Không dùng screenshot thay cho text nếu nội dung có thể viết bằng text.

---

## 7. Chuẩn bảng

Dùng bảng khi so sánh rõ ràng:

```html
<table>
  <thead>
    <tr>
      <th>Tiêu chí</th>
      <th>Cách A</th>
      <th>Cách B</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Độ phức tạp</td>
      <td>Thấp</td>
      <td>Cao</td>
    </tr>
  </tbody>
</table>
```

Không tạo bảng quá nhiều cột. Nếu quá 4 cột, ưu tiên tách thành list.

---

## 8. Chuẩn note/cảnh báo

Dùng class `article-note` cho ghi chú nổi bật:

```html
<p class="article-note">
  Lưu ý: Không chạy migration trực tiếp trên production nếu chưa backup dữ liệu.
</p>
```

Chỉ dùng cho nội dung quan trọng:

- Cảnh báo bảo mật.
- Lưu ý dữ liệu.
- Kết luận quan trọng.
- Điều kiện bắt buộc.

---

## 9. Chuẩn homepage khi thêm tài liệu mới

Khi thêm tài liệu mới, update `index.html` trong `.docs-list` bằng card mới.

Mẫu card:

```html
<article class="doc-card-featured">
  <a class="doc-cover" href="docs/ten-tai-lieu.html" aria-label="Đọc tài liệu Tên tài liệu">
    <span class="doc-icon">TD</span>
    <span class="doc-status">Ready</span>
  </a>

  <div class="doc-content">
    <div class="doc-kicker">Guide · Category</div>
    <h3><a href="docs/ten-tai-lieu.html">Tên tài liệu</a></h3>
    <p>Mô tả ngắn tài liệu trong 1-2 câu.</p>

    <div class="doc-tags" aria-label="Chủ đề tài liệu">
      <span>Tag 1</span>
      <span>Tag 2</span>
      <span>Tag 3</span>
    </div>
  </div>

  <div class="doc-action">
    <a class="read-link" href="docs/ten-tai-lieu.html" aria-label="Đọc tài liệu Tên tài liệu">
      Đọc ngay
      <span aria-hidden="true">→</span>
    </a>
  </div>
</article>
```

Sau khi thêm card, cập nhật số lượng trong `hero-panel` nếu cần.

---

## 10. Quy tắc đặt tên file

Dùng kebab-case, không dấu, không khoảng trắng:

```text
Đúng:
docs/google-antigravity.html
docs/github-pages-guide.html
docs/nextjs-dashboard-ui.html

Sai:
docs/Google Antigravity.html
docs/Tài liệu mới.html
docs/new_doc.HTML
```

---

## 11. Checklist trước khi push

Trước khi commit, kiểm tra:

- [ ] File HTML nằm trong `docs/`.
- [ ] Trang có `lang="vi"`.
- [ ] Trang có `meta viewport`.
- [ ] Trang link đúng CSS: `../assets/css/styles.css`.
- [ ] Có header giống site.
- [ ] Có footer giống site.
- [ ] Có back link về `../index.html`.
- [ ] Không dùng inline style bừa bãi.
- [ ] Không dùng framework ngoài.
- [ ] Tất cả link ngoài có `target="_blank" rel="noopener noreferrer"`.
- [ ] Homepage có card trỏ tới tài liệu mới.
- [ ] Mobile không bị vỡ layout.

---

## 12. Prompt mẫu cho AI tạo tài liệu mới

Dùng prompt này khi muốn AI thêm một tài liệu mới vào repo:

```md
Hãy thêm một tài liệu HTML mới vào repo Notes Docs.

Yêu cầu:
- Đọc README.md trước để tuân thủ style.
- Tạo file mới trong docs/ bằng kebab-case.
- Dùng layout chuẩn: site-header, article-layout, article-shell, site-footer.
- Dùng dark mode CSS hiện có, không thêm framework.
- Nội dung viết bằng tiếng Việt, rõ ràng, dễ đọc.
- Có h1, h2, h3 đúng cấp.
- Dùng pre/code cho command, config, prompt.
- Dùng article-note cho lưu ý quan trọng.
- Update index.html để thêm card tài liệu mới.
- Không link Markdown gốc trên homepage.
- Sau khi xong, báo danh sách file đã sửa.
```

---

## 13. Triết lý trình bày

Trang này không phải landing page quảng cáo. Đây là **documentation library**.

Ưu tiên:

```text
Dễ đọc > Nhiều hiệu ứng
Rõ cấu trúc > Trang trí phức tạp
Nội dung chính > Nút phụ
HTML đơn giản > Framework nặng
Dark mode thống nhất > Mỗi trang một style
```
