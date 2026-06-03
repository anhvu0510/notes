# Google Antigravity — Khái niệm, cách sử dụng và ứng dụng thực tế

> Nguồn chính: https://antigravity.google/docs/home  
> Nội dung tổng hợp từ tài liệu chính thức Antigravity: Home, Overview, Features, MCP, Skills, Plugins, Rules/Workflows, Artifacts và CLI.

---

## 1. Google Antigravity là gì?

**Google Antigravity** là nền tảng phát triển phần mềm theo hướng **agent-first** của Google. Thay vì AI chỉ gợi ý code từng dòng trong editor, Antigravity cho phép bạn giao một nhiệm vụ lớn cho AI Agent, sau đó agent có thể lập kế hoạch, đọc code, sửa file, chạy terminal, kiểm thử, mở browser, tạo artifact và báo cáo lại kết quả.

Antigravity không chỉ là IDE có chatbot. Nó là môi trường làm việc nơi AI Agent được dùng như một “nhân sự kỹ thuật ảo” có thể thực hiện nhiều bước trong quy trình phát triển phần mềm.

### Tư duy cốt lõi

```text
IDE truyền thống:
User viết code -> AI gợi ý -> User tự kiểm tra -> User tự chạy test

Antigravity:
User giao mục tiêu -> Agent lập plan -> Agent sửa code -> Agent chạy test -> Agent tạo artifact -> User review
```

### Điểm khác biệt lớn

| Tiêu chí | IDE AI thông thường | Google Antigravity |
|---|---|---|
| Vai trò AI | Trợ lý gợi ý code | Agent có thể thực hiện task nhiều bước |
| Phạm vi thao tác | Chủ yếu trong editor/chat | Editor, terminal, browser, workspace, artifact |
| Cách làm việc | Hỏi - đáp liên tục | Giao nhiệm vụ, agent tự plan và thực thi |
| Kiểm chứng | User tự xem diff/test | Có artifact, plan, browser recording, kết quả chạy lệnh |
| Phù hợp | Sửa code nhỏ, autocomplete | Build feature, refactor, debug, test, nghiên cứu repo |

---

## 2. Các khái niệm quan trọng

## 2.1 Agent

**Agent** là AI worker có khả năng nhận mục tiêu, chia nhỏ công việc, thao tác trên project và tạo kết quả.

Agent trong Antigravity có thể:

- Đọc code trong workspace.
- Sửa file.
- Chạy lệnh terminal.
- Mở browser để kiểm tra UI/web app.
- Tạo kế hoạch thực hiện.
- Sinh artifact để người dùng review.
- Làm việc nền hoặc song song tùy workflow.

Ví dụ task phù hợp:

```text
Phân tích toàn bộ repo Next.js này, tìm nguyên nhân trang dashboard load chậm, tối ưu lại component/table, chạy test và báo cáo thay đổi.
```

---

## 2.2 Agent Manager

**Agent Manager** là khu vực quản lý các agent và task. Có thể hiểu như “mission control” cho nhiều agent.

Ứng dụng:

- Theo dõi agent đang làm gì.
- Chạy nhiều task song song.
- Giao task cho từng workspace/project.
- Review tiến độ, artifact, plan, kết quả.
- Quản lý background task.

Ví dụ thực tế:

```text
Agent 1: Refactor frontend dashboard.
Agent 2: Viết test cho API.
Agent 3: Đọc docs Supabase và kiểm tra migration.
Agent 4: Debug lỗi build production.
```

---

## 2.3 Editor

**Editor** là giao diện viết code quen thuộc, gần giống VS Code. Đây là nơi bạn:

- Mở project.
- Xem và sửa file.
- Review diff.
- Chat với agent trong ngữ cảnh code.
- Chạy task nhỏ trực tiếp trong project.

Editor phù hợp khi bạn muốn kiểm soát chặt từng thay đổi.

---

## 2.4 Terminal

Agent có thể dùng terminal để:

- Cài package.
- Chạy dev server.
- Chạy test.
- Build project.
- Kiểm tra lỗi TypeScript/lint.
- Chạy script migration hoặc script phân tích.

Ví dụ:

```bash
npm install
npm run lint
npm run test
npm run build
```

Terminal mạnh nhưng cần kiểm soát kỹ vì có thể thay đổi file, xóa file, ghi đè dữ liệu hoặc gọi network.

---

## 2.5 Browser

Browser tích hợp giúp agent kiểm tra app như người dùng thật.

Agent có thể:

- Mở localhost.
- Click UI.
- Ghi lại browser recording.
- Kiểm tra lỗi layout.
- Kiểm tra flow đăng nhập/form/table/dashboard.
- Chụp screenshot làm bằng chứng.

Ví dụ task:

```text
Chạy app, mở trang /dashboard, kiểm tra layout trên desktop và mobile, fix lỗi overflow table rồi ghi lại kết quả bằng screenshot.
```

---

## 2.6 Artifact

**Artifact** là sản phẩm trung gian hoặc kết quả do agent tạo ra để bạn kiểm chứng.

Artifact có thể gồm:

- Task list.
- Implementation plan.
- Visual code diff.
- Screenshot.
- Browser recording.
- Báo cáo kiểm thử.
- Tóm tắt thay đổi.

Artifact giúp bạn không phải tin mù quáng vào agent. Bạn có bằng chứng để review.

---

## 2.7 MCP — Model Context Protocol

**MCP** là cơ chế kết nối Antigravity với tool/server bên ngoài. Qua MCP, agent có thể thao tác với dịch vụ hoặc hệ thống bạn cấu hình.

Ví dụ:

- Supabase.
- GitHub.
- Database tool.
- Filesystem tool.
- Browser automation.
- Internal API.
- Custom server riêng của team.

Ví dụ ứng dụng:

```text
Agent đọc schema Supabase qua MCP, kiểm tra migration, sau đó sửa Prisma schema và cập nhật API route.
```

Lưu ý bảo mật: chỉ bật MCP server bạn tin tưởng, giới hạn quyền ghi/xóa nếu có thể.

---

## 2.8 Skills

**Skills** là các gói hướng dẫn/tư duy/workflow có thể tái sử dụng cho agent.

Một skill thường chứa:

- Cách tiếp cận một loại task.
- Quy tắc làm việc.
- Best practices.
- Ví dụ mẫu.
- Ràng buộc chất lượng.

Ví dụ skill:

```text
skills/design-taste-frontend/SKILL.md
```

Dùng cho các task thiết kế UI/UX, bắt agent luôn phân tích layout, spacing, hierarchy, responsive, animation, empty state, loading state trước khi code.

### Khi nào nên dùng Skills?

Dùng khi bạn có một loại task lặp lại nhiều lần:

- Thiết kế UI dashboard.
- Dịch truyện Trung - Việt.
- Audit security.
- Viết test.
- Refactor Next.js.
- Tạo API chuẩn REST.
- Review performance.

---

## 2.9 Rules / Workflows

**Rules** là luật hành vi áp dụng cho agent. Nếu skill là “năng lực theo nhiệm vụ”, thì rules là “luật nền” agent phải tuân thủ.

Ví dụ rules:

```md
- Luôn trả lời bằng tiếng Việt.
- Không đổi public API nếu user không yêu cầu.
- Trước khi sửa code phải đọc file liên quan.
- Sau khi sửa phải chạy lint/build nếu project có script.
- Không tự ý xóa file dữ liệu.
```

Rules phù hợp để chuẩn hóa phong cách làm việc dài hạn cho toàn project/team.

---

## 2.10 Plugins

**Plugins** là gói mở rộng có thể gom nhiều thành phần vào một package:

- Skills.
- Rules.
- MCP servers.
- Hooks.
- Agents.

Nếu bạn có workflow phức tạp, plugin giúp đóng gói toàn bộ để cài lại dễ dàng ở nhiều project.

Ví dụ plugin nội bộ:

```text
company-dashboard-plugin/
├── skills/ui-dashboard/SKILL.md
├── rules/frontend.md
├── mcp/supabase.json
└── hooks/pre-task.md
```

---

## 2.11 Hooks

**Hooks** là điểm móc để tự động chạy hành động ở một thời điểm nhất định trong workflow.

Ví dụ:

- Trước khi agent bắt đầu task: nhắc đọc rules.
- Sau khi sửa code: chạy formatter.
- Trước khi hoàn tất: chạy test/build.
- Sau khi tạo artifact: yêu cầu tóm tắt rủi ro.

Hooks giúp workflow ổn định hơn, giảm việc bạn phải nhắc đi nhắc lại.

---

## 2.12 Worktree Support

Antigravity 2.0 hỗ trợ mô hình làm việc theo project/worktree tốt hơn.

Ý nghĩa thực tế:

- Agent có thể xử lý task ở workspace riêng.
- Giảm rủi ro làm bẩn branch chính.
- Dễ chạy nhiều task song song.
- Dễ review/merge từng thay đổi.

Workflow khuyến nghị:

```text
main branch sạch
    ├── worktree/feature-dashboard-ui
    ├── worktree/fix-api-timeout
    └── worktree/add-tests
```

---

## 2.13 Antigravity CLI

**Antigravity CLI** là giao diện dòng lệnh cho agent. Phù hợp khi bạn thích terminal hoặc muốn tích hợp agent vào workflow dev hiện tại.

Ứng dụng:

- Giao task từ terminal.
- Quản lý background task/subagent.
- Dùng slash command.
- Kết hợp skills/plugins/MCP.
- Chạy workflow không cần thao tác nhiều trong UI.

Ví dụ ý tưởng sử dụng:

```bash
antigravity
/agents
/btw "refactor module auth và chạy test liên quan"
```

Tên lệnh cụ thể có thể thay đổi theo phiên bản, nên luôn kiểm tra docs chính thức trước khi dùng.

---

# 3. Cách sử dụng Google Antigravity

## 3.1 Cài đặt

Quy trình chung:

1. Truy cập trang chính thức: https://antigravity.google/
2. Tải bản phù hợp với hệ điều hành: macOS, Windows hoặc Linux.
3. Cài đặt app.
4. Đăng nhập bằng tài khoản Google được hỗ trợ.
5. Mở project code local.
6. Cấu hình model, rules, skills, MCP nếu cần.

Lưu ý: Antigravity thay đổi nhanh giữa các version, nên đọc docs chính thức trước khi làm theo tutorial cũ.

---

## 3.2 Mở project

Bạn có thể mở folder source code như IDE bình thường:

```text
File -> Open Folder -> chọn project
```

Sau khi mở project, agent sẽ có context từ:

- File trong workspace.
- Cấu trúc thư mục.
- Git diff.
- Terminal output.
- Rules/skills nếu đã cấu hình.

---

## 3.3 Giao task cho agent

Task nên viết theo format rõ mục tiêu, phạm vi, ràng buộc và tiêu chí hoàn thành.

Template tốt:

```md
## Mục tiêu
[Việc cần làm]

## Phạm vi
[File/folder/page/module liên quan]

## Ràng buộc
[Không được đổi gì, giữ API nào, style nào]

## Tiêu chí hoàn thành
- Build pass
- Test pass
- UI không vỡ responsive
- Có summary thay đổi
```

Ví dụ:

```md
## Mục tiêu
Tối ưu trang dashboard users để load nhanh hơn và UI chuyên nghiệp hơn.

## Phạm vi
- app/dashboard/users
- components/user-table
- API route liên quan nếu cần

## Ràng buộc
- Không đổi database schema.
- Không đổi response API hiện tại.
- Giữ menu hiện có.

## Tiêu chí hoàn thành
- npm run build pass.
- Table không overflow trên mobile.
- Có loading state và empty state.
- Trả về summary các file đã sửa.
```

---

## 3.4 Review plan trước khi cho agent sửa sâu

Với task lớn, nên yêu cầu agent tạo plan trước:

```text
Đọc project và lập plan trước, chưa sửa code. Sau khi tôi duyệt mới triển khai.
```

Việc này giúp tránh agent sửa sai hướng hoặc đụng vào file nhạy cảm.

---

## 3.5 Review diff và artifact

Sau khi agent chạy xong:

1. Xem diff từng file.
2. Đọc summary thay đổi.
3. Kiểm tra terminal output.
4. Xem screenshot/browser recording nếu có UI.
5. Tự chạy lại build/test nếu task quan trọng.
6. Commit thay đổi khi đã chắc.

Không nên merge chỉ vì agent báo “done”. Luôn review artifact.

---

## 3.6 Cấu hình Skills

Cấu trúc skill thường là:

```text
.agents/
└── skills/
    └── ten-skill/
        └── SKILL.md
```

Ví dụ `SKILL.md` cho UI:

```md
# design-taste-frontend

## Mục tiêu
Tạo UI hiện đại, rõ hierarchy, đẹp nhưng không phá chức năng.

## Quy tắc
- Ưu tiên readability trước hiệu ứng.
- Table phải có empty/loading/error state.
- Responsive từ mobile đến desktop.
- Không xóa logic nghiệp vụ nếu không được yêu cầu.
- Sau khi sửa phải mô tả file đã thay đổi.
```

Khi giao task:

```text
Dùng skill design-taste-frontend để redesign trang dashboard này.
```

---

## 3.7 Cấu hình Rules

Rules nên đặt ở nơi Antigravity nhận diện theo docs version bạn đang dùng. Nội dung nên ngắn, rõ, có tính bắt buộc.

Ví dụ rules cho project Next.js:

```md
# Project Rules

- Luôn dùng TypeScript strict.
- Không dùng `any` nếu có thể định nghĩa type.
- Component UI phải responsive.
- Không đổi route public nếu user không yêu cầu.
- Sau khi sửa code phải chạy `npm run lint` và `npm run build` nếu có script.
- Không tự ý xóa file `.env`, database, migration hoặc dữ liệu user.
```

---

## 3.8 Dùng MCP

Quy trình chung:

1. Chọn MCP server phù hợp.
2. Cấu hình server theo docs.
3. Cấp quyền tối thiểu cần thiết.
4. Test kết nối.
5. Giao task có nêu rõ phạm vi MCP.

Ví dụ prompt:

```text
Dùng MCP Supabase chỉ để đọc schema hiện tại, không chạy migration. Sau đó đề xuất thay đổi API cho module orders.
```

Luôn giới hạn quyền nếu task chỉ cần đọc.

---

# 4. Ứng dụng thực tế

## 4.1 Build feature mới

Ví dụ:

```text
Thêm chức năng export CSV cho bảng giao dịch, có button, loading state, xử lý lỗi và test cơ bản.
```

Agent có thể:

- Tìm component table.
- Thêm button export.
- Viết helper CSV.
- Cập nhật UI.
- Chạy build/test.
- Báo cáo file đã sửa.

---

## 4.2 Refactor codebase

Ví dụ:

```text
Refactor module auth để tách service, repository, validation. Không đổi API public.
```

Agent có thể:

- Đọc module auth.
- Tách logic.
- Giữ compatibility.
- Update import.
- Chạy test.

---

## 4.3 Debug lỗi production

Ví dụ:

```text
Dựa vào log này, tìm nguyên nhân API /checkout bị timeout và đề xuất fix an toàn.
```

Agent có thể:

- Đọc log.
- Tìm endpoint.
- Kiểm tra query/database call.
- Đề xuất index/cache/pagination.
- Sửa code nếu được phép.

---

## 4.4 Tối ưu UI/UX dashboard

Ví dụ:

```text
Dùng design-taste-frontend redesign dashboard analytics theo style SaaS hiện đại, giữ nguyên dữ liệu và chức năng.
```

Agent có thể:

- Phân tích layout hiện tại.
- Cải thiện spacing, typography, visual hierarchy.
- Thêm loading/empty/error state.
- Tối ưu responsive.
- Chụp screenshot trước/sau.

---

## 4.5 Viết test

Ví dụ:

```text
Viết unit test cho utils pricing và integration test cho API /orders. Không sửa logic nếu test fail, chỉ báo nguyên nhân.
```

Agent có thể:

- Tìm test framework.
- Viết test theo pattern có sẵn.
- Chạy test.
- Báo lỗi logic nếu có.

---

## 4.6 Review bảo mật

Ví dụ:

```text
Audit module upload file, tìm lỗi path traversal, file type bypass, size limit và auth check.
```

Agent có thể:

- Tìm endpoint upload.
- Kiểm tra validation.
- Kiểm tra quyền truy cập.
- Đề xuất fix.
- Viết test case bảo mật.

---

## 4.7 Tự động hóa quy trình dev

Với skills, rules, hooks, MCP và plugins, bạn có thể chuẩn hóa workflow:

```text
1. Agent đọc issue.
2. Agent lập plan.
3. Agent tạo branch/worktree.
4. Agent sửa code.
5. Agent chạy test/build.
6. Agent tạo artifact.
7. User review diff.
8. Merge nếu đạt.
```

---

# 5. Prompt mẫu dùng với Antigravity

## 5.1 Prompt phân tích repo

```md
Bạn là senior software engineer. Hãy phân tích repo này.

Yêu cầu:
- Giải thích kiến trúc tổng thể.
- Chỉ ra entrypoint chính.
- Liệt kê module quan trọng.
- Chỉ ra luồng dữ liệu chính.
- Chỉ ra rủi ro kỹ thuật.
- Chưa sửa code.

Output:
- Tổng quan kiến trúc.
- Cây thư mục rút gọn.
- Luồng request chính.
- Danh sách vấn đề nên cải thiện.
```

## 5.2 Prompt fix bug

```md
Mục tiêu: Fix lỗi [mô tả lỗi].

Context:
- Lỗi xảy ra ở: [page/API/module]
- Log: [paste log]
- Kỳ vọng: [hành vi đúng]

Ràng buộc:
- Không đổi API public.
- Không xóa test hiện có.
- Không sửa ngoài phạm vi nếu không cần.

Quy trình:
1. Đọc code liên quan.
2. Nêu nguyên nhân gốc.
3. Đề xuất plan ngắn.
4. Sửa code.
5. Chạy test/build.
6. Báo cáo file đã sửa.
```

## 5.3 Prompt redesign UI

```md
Dùng skill design-taste-frontend để redesign màn hình này.

Mục tiêu:
- Nâng cấp UI lên mức SaaS professional.
- Giữ nguyên logic và dữ liệu.
- Tối ưu table, card, spacing, typography.
- Có responsive mobile/tablet/desktop.

Bắt buộc:
- Không đổi API.
- Không xóa chức năng cũ.
- Thêm loading, empty, error state nếu thiếu.
- Sau khi sửa phải chụp screenshot hoặc mô tả visual diff.
```

## 5.4 Prompt viết test

```md
Viết test cho module [tên module].

Yêu cầu:
- Đọc pattern test hiện có trước.
- Viết test theo style của project.
- Cover happy path, edge case, error case.
- Không sửa business logic nếu test fail.
- Chạy test và báo cáo kết quả.
```

---

# 6. Best practices

## 6.1 Giao task rõ ràng

Prompt mơ hồ:

```text
Fix app này đi.
```

Prompt tốt:

```text
Fix lỗi trang /orders bị trắng màn hình khi API trả mảng rỗng. Không đổi API. Thêm empty state và chạy build.
```

---

## 6.2 Chia nhỏ task lớn

Không nên giao một lần:

```text
Build toàn bộ SaaS từ đầu đến cuối.
```

Nên chia:

```text
Task 1: Thiết kế schema.
Task 2: Build API auth.
Task 3: Build dashboard layout.
Task 4: Build billing page.
Task 5: Viết test.
```

---

## 6.3 Luôn yêu cầu plan với task rủi ro

```text
Trước khi sửa code, hãy đọc repo và đưa plan. Chỉ sửa sau khi tôi duyệt.
```

Dùng cho:

- Refactor lớn.
- Migration database.
- Xóa file.
- Đổi auth/payment.
- Đổi kiến trúc.

---

## 6.4 Luôn chạy kiểm chứng

Sau khi agent sửa:

```text
Chạy lint, test, build nếu project có script. Nếu không chạy được, báo rõ lý do.
```

---

## 6.5 Kiểm soát quyền terminal

Không nên cho agent tự do chạy mọi lệnh với project quan trọng.

Cẩn thận với:

```bash
rm -rf
sudo
chmod -R
chown -R
DROP DATABASE
prisma migrate reset
git reset --hard
git clean -fd
```

Nên yêu cầu:

```text
Không chạy lệnh xóa file, reset git, migrate database hoặc thay đổi quyền hệ thống nếu chưa hỏi tôi.
```

---

# 7. Rủi ro và lưu ý bảo mật

Antigravity mạnh vì agent có quyền thao tác thật. Nhưng quyền càng cao thì rủi ro càng lớn.

## 7.1 Rủi ro thường gặp

- Agent sửa quá phạm vi yêu cầu.
- Agent chạy lệnh terminal nguy hiểm.
- Agent đọc nhầm hoặc ghi đè file quan trọng.
- Prompt injection từ file Markdown, issue, webpage hoặc docs lạ.
- MCP server cấp quyền quá rộng.
- Thay đổi database/migration ngoài ý muốn.
- Build pass nhưng logic nghiệp vụ sai.

## 7.2 Cách giảm rủi ro

- Dùng Git trước khi giao task.
- Tạo branch/worktree riêng.
- Commit trạng thái sạch trước khi agent chạy.
- Giới hạn quyền MCP.
- Không để secret thật trong repo.
- Dùng `.env.example` thay vì `.env` thật.
- Yêu cầu plan trước với task lớn.
- Review diff thủ công.
- Chạy test/build lại.
- Backup dữ liệu trước khi migration.

---

# 8. Workflow khuyến nghị cho project thật

```text
Bước 1: Tạo branch/worktree mới
Bước 2: Giao task rõ ràng cho agent
Bước 3: Agent đọc code và tạo plan
Bước 4: User duyệt plan
Bước 5: Agent sửa code
Bước 6: Agent chạy lint/test/build
Bước 7: Agent tạo artifact/screenshot/report
Bước 8: User review diff
Bước 9: User tự test lại flow quan trọng
Bước 10: Commit/merge
```

Prompt mẫu:

```md
Hãy làm task này theo workflow an toàn:

1. Đọc code liên quan.
2. Tạo plan trước, chưa sửa.
3. Sau khi có plan, chỉ sửa trong phạm vi được nêu.
4. Không chạy lệnh xóa/reset/migration nếu chưa hỏi.
5. Sau khi sửa, chạy lint/test/build nếu có.
6. Tạo summary gồm: file đã sửa, lý do sửa, test đã chạy, rủi ro còn lại.
```

---

# 9. Khi nào nên dùng Antigravity?

Nên dùng khi:

- Project có nhiều file cần đọc hiểu.
- Task cần nhiều bước: đọc code -> sửa -> test -> verify.
- Cần agent kiểm tra UI bằng browser.
- Cần song song nhiều task.
- Cần chuẩn hóa workflow bằng skills/rules/hooks.
- Muốn AI làm việc như một coding agent thay vì chatbot.

Không nên dùng bừa khi:

- Task chỉ cần sửa một dòng rất nhỏ.
- Repo chứa secret hoặc dữ liệu nhạy cảm chưa được bảo vệ.
- Bạn chưa có Git backup.
- Task liên quan production database nhưng chưa có môi trường staging.
- Bạn không có thời gian review diff.

---

# 10. Tóm tắt nhanh

Google Antigravity là nền tảng IDE/agentic development của Google, giúp bạn giao việc cho AI Agent thực hiện các task phần mềm phức tạp. Điểm mạnh nhất nằm ở việc agent có thể làm việc xuyên suốt editor, terminal, browser, artifact, skills, MCP, rules, plugins và CLI.

Cách dùng hiệu quả:

1. Viết task rõ mục tiêu/phạm vi/ràng buộc.
2. Dùng plan trước khi sửa task lớn.
3. Dùng skills cho workflow lặp lại.
4. Dùng rules để khóa hành vi agent.
5. Dùng MCP có kiểm soát.
6. Review artifact/diff/test trước khi merge.
7. Luôn dùng Git branch/worktree để tránh mất dữ liệu.

Antigravity phù hợp nhất với workflow hiện đại: **user định hướng, agent thực thi, artifact kiểm chứng, human review quyết định**.

---

# 11. Nguồn tham khảo

- Google Antigravity Docs Home: https://antigravity.google/docs/home
- Overview: https://antigravity.google/docs/overview
- Features: https://antigravity.google/docs/features
- MCP: https://antigravity.google/docs/mcp
- Skills: https://antigravity.google/docs/skills
- Plugins: https://antigravity.google/docs/plugins
- Rules / Workflows: https://antigravity.google/docs/rules-workflows
- Artifacts: https://antigravity.google/docs/artifacts
- CLI Reference: https://antigravity.google/docs/cli-reference
- CLI Best Practices: https://antigravity.google/docs/cli-best-practices
