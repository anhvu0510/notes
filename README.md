# Notes Docs

Kho tài liệu tĩnh dùng HTML/CSS cơ bản để triển khai bằng GitHub Pages.

Mục tiêu:

- Tài liệu được tổ chức theo từng folder/chủ đề.
- Homepage `index.html` là thư viện tài liệu, không phải landing page quảng cáo.
- Mỗi folder trong `docs/` chứa các file HTML docs liên quan.
- Giao diện thống nhất bằng `assets/css/styles.css`.
- Dark mode là mặc định.

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
│   ├── ai-tools/
│   │   └── antigravity-google.html
│   ├── frontend/
│   ├── backend/
│   ├── database/
│   └── security/
└── *.md
```

Ý nghĩa:

| Đường dẫn | Vai trò |
|---|---|
| `index.html` | Trang chủ, hiển thị folder/chủ đề và docs bên trong. |
| `docs/<folder>/*.html` | Trang tài liệu HTML theo từng nhóm. |
| `assets/css/styles.css` | CSS dùng chung toàn site. |
| `README.md` | Chuẩn style để AI/người dùng tạo docs mới. |
| `*.md` | Markdown gốc hoặc bản nháp, không phải trang đọc chính. |

---

## 2. Folder docs được khuyến nghị

| Folder | Dùng cho |
|---|---|
| `docs/ai-tools/` | AI coding tools, agent workflow, MCP, skills, rules, automation. |
| `docs/frontend/` | UI/UX, HTML, CSS, JavaScript, React, Next.js, dashboard. |
| `docs/backend/` | API, service, auth, queue, server architecture. |
| `docs/database/` | SQL, SQLite, PostgreSQL, migration, indexing. |
| `docs/security/` | CVE, audit, secure coding, auth, upload security. |
| `docs/devops/` | GitHub Actions, deploy, Docker, CI/CD. |

Nếu tài liệu không khớp folder hiện có, tạo folder mới bằng kebab-case.

---

## 3. Quy tắc bắt buộc khi AI tạo tài liệu HTML

1. Không dùng React, Vue, Tailwind, Bootstrap hoặc build tool.
2. Chỉ dùng HTML/CSS cơ bản.
3. Không inline CSS nếu không thật sự cần.
4. Không phá layout chung: `site-header`, `article-layout`, `article-shell`, `site-footer`.
5. File docs phải nằm trong `docs/<folder>/ten-file.html`.
6. Homepage phải tổ chức theo folder, không tạo hero to đùng, không hiển thị block thống kê thừa.
7. Không link Markdown gốc trên homepage trừ khi user yêu cầu.
8. Nội dung mặc định viết bằng tiếng Việt.
9. Dark mode là mặc định.
10. Tối ưu mobile, không để table/card vỡ layout.

---

## 4. Template HTML chuẩn cho file trong folder

Ví dụ file nằm tại `docs/ai-tools/antigravity-google.html`, đường dẫn CSS phải là `../../assets/css/styles.css`.

```html
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="Mô tả ngắn của tài liệu." />
  <title>Tên tài liệu | Notes Docs</title>
  <link rel="stylesheet" href="../../assets/css/styles.css" />
</head>
<body class="article-page">
  <header class="site-header">
    <div class="container header-inner">
      <a class="brand" href="../../index.html" aria-label="Notes Docs Home">
        <span class="brand-mark">N</span>
        <span class="brand-text">Notes Docs</span>
      </a>
      <nav class="site-nav" aria-label="Điều hướng chính">
        <a href="../../index.html">Docs</a>
        <a href="https://github.com/anhvu0510/notes" target="_blank" rel="noopener noreferrer">GitHub</a>
      </nav>
    </div>
  </header>

  <main class="article-layout">
    <article class="article-shell">
      <a class="back-link" href="../../index.html">← Về thư viện</a>

      <p class="eyebrow">CATEGORY · TYPE</p>
      <h1>Tên tài liệu</h1>

      <p class="article-note">
        Tóm tắt ngắn: tài liệu này dùng để làm gì, ai nên đọc, đọc xong làm được gì.
      </p>

      <h2>1. Khái niệm</h2>
      <p>Nội dung...</p>

      <h2>2. Cách sử dụng</h2>
      <p>Nội dung...</p>

      <h2>3. Ứng dụng thực tế</h2>
      <p>Nội dung...</p>

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

## 5. Chuẩn homepage theo folder

Homepage phải có cấu trúc:

```text
Header
Intro ngắn
Folder layout
├── Sidebar danh mục folder
└── Folder content
    ├── Folder heading
    └── Doc tiles
Footer
```

Không thêm:

- Block `Available Docs / Format / Deploy`.
- Hero quá lớn che hết tài liệu.
- Section giải thích GitHub Pages.
- Link Markdown gốc trên card.

Mẫu doc tile:

```html
<article class="doc-tile">
  <a class="tile-icon" href="docs/folder/ten-file.html" aria-label="Đọc Tên tài liệu">
    <span>AB</span>
  </a>
  <div class="tile-body">
    <div class="doc-kicker">Guide · Category</div>
    <h3><a href="docs/folder/ten-file.html">Tên tài liệu</a></h3>
    <p>Mô tả ngắn tài liệu trong 1-2 câu.</p>
    <div class="doc-tags" aria-label="Chủ đề tài liệu">
      <span>Tag 1</span>
      <span>Tag 2</span>
    </div>
  </div>
  <a class="tile-read" href="docs/folder/ten-file.html">Đọc →</a>
</article>
```

---

## 6. Chuẩn nội dung tài liệu

Một tài liệu tốt nên có:

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

Không bắt buộc đủ 10 phần. Ưu tiên rõ ràng, thực tế, có ví dụ.

---

## 7. Chuẩn heading

```html
<h1>Tên tài liệu</h1>
<h2>1. Nhóm nội dung lớn</h2>
<h3>1.1 Ý nhỏ</h3>
```

Không nhảy cấp heading.

---

## 8. Chuẩn code block

Dùng `pre > code` cho command, prompt, JSON, config:

```html
<pre><code>npm install
npm run build</code></pre>
```

---

## 9. Chuẩn note/cảnh báo

Dùng `article-note` cho nội dung quan trọng:

```html
<p class="article-note">
  Lưu ý: Không chạy migration trực tiếp trên production nếu chưa backup dữ liệu.
</p>
```

---

## 10. Quy tắc đặt tên file

Dùng kebab-case, không dấu, không khoảng trắng:

```text
Đúng:
docs/ai-tools/google-antigravity.html
docs/frontend/nextjs-dashboard-ui.html
docs/database/sqlite-guide.html

Sai:
docs/Google Antigravity.html
docs/Tài liệu mới.html
docs/new_doc.HTML
```

---

## 11. Checklist trước khi push

- [ ] File HTML nằm trong `docs/<folder>/`.
- [ ] Trang có `lang="vi"`.
- [ ] Trang có `meta viewport`.
- [ ] Trang link CSS đúng: `../../assets/css/styles.css`.
- [ ] Header link về `../../index.html`.
- [ ] Back link ghi `← Về thư viện`.
- [ ] Không dùng framework ngoài.
- [ ] Không inline CSS bừa bãi.
- [ ] Link ngoài có `target="_blank" rel="noopener noreferrer"`.
- [ ] Homepage đã thêm folder/doc tile tương ứng.
- [ ] Mobile không vỡ layout.

---

## 12. Prompt mẫu cho AI tạo tài liệu mới

```md
Hãy thêm một tài liệu HTML mới vào repo Notes Docs.

Yêu cầu:
- Đọc README.md trước để tuân thủ style.
- Xác định folder phù hợp trong docs/. Nếu chưa có thì tạo folder mới bằng kebab-case.
- Tạo file mới trong docs/<folder>/ten-file.html.
- Dùng layout chuẩn: site-header, article-layout, article-shell, site-footer.
- Link CSS đúng theo độ sâu: ../../assets/css/styles.css.
- Viết bằng tiếng Việt, rõ ràng, thực tế.
- Dùng h1, h2, h3 đúng cấp.
- Dùng pre/code cho command, config, prompt.
- Dùng article-note cho lưu ý quan trọng.
- Update index.html theo cấu trúc folder UI, thêm doc tile vào đúng folder.
- Không tạo hero lớn, không thêm thống kê thừa, không link Markdown gốc trên homepage.
- Không dùng framework, không inline CSS bừa bãi.
- Sau khi xong, báo danh sách file đã tạo/sửa.
```

---

## 13. Triết lý trình bày

```text
Folder rõ ràng > Danh sách lộn xộn
Tài liệu dễ đọc > Landing page màu mè
Nội dung chính > Block thống kê thừa
HTML đơn giản > Framework nặng
Dark mode thống nhất > Mỗi trang một style
```
