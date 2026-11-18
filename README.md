# data-storytelling — Claude Code skill

Skill giúp Claude phân tích và trình bày dữ liệu theo hướng storytelling: chọn ý chính, chọn chart
theo thông điệp, thêm mốc so sánh (target, kỳ trước, benchmark), dẫn mắt người xem và tránh các
cách vẽ gây hiểu lầm.

- [SKILL.md](SKILL.md) — quy trình 7 bước + bảng "Tránh → Áp dụng".
- [references/visual-catalog.md](references/visual-catalog.md) — 62 ảnh mẫu, gắn nhãn ❌ BAD / ✅ GOOD theo từng panel.
- `examples/` — ảnh mẫu, tên file mô tả nội dung (`<nhóm>_<mô-tả>.png`).

## Cài đặt

**Không cần tài khoản GitHub.** Chọn một trong hai cách:

- **Không có git:** trên trang repo bấm **Code → Download ZIP**, giải nén rồi đổi tên thư mục thành
  `data-storytelling` và đặt vào `C:\Users\<tên bạn>\.claude\skills\` (Windows) hoặc
  `~/.claude/skills/` (macOS/Linux). Kiểm tra: file `SKILL.md` phải nằm ngay trong
  `.claude\skills\data-storytelling\`, không lồng thêm một thư mục con.
- **Có git:** clone thẳng vào thư mục skills của Claude Code:

**Windows (PowerShell)**
```powershell
git clone https://github.com/jsph9090/data-storytelling-skill.git "$env:USERPROFILE\.claude\skills\data-storytelling"
```

**macOS / Linux**
```bash
git clone https://github.com/jsph9090/data-storytelling-skill.git ~/.claude/skills/data-storytelling
```

Mở một phiên Claude Code mới — skill `data-storytelling` sẽ có trong danh sách. Claude tự dùng khi
bạn yêu cầu vẽ chart, làm dashboard, trình bày số liệu; hoặc gọi trực tiếp `/data-storytelling`.

## Cập nhật

Nếu cài bằng git:
```powershell
git -C "$env:USERPROFILE\.claude\skills\data-storytelling" pull
```
Nếu cài bằng ZIP: tải ZIP mới và chép đè thư mục cũ.

## Nguồn

Các ví dụ minh họa trong `examples/` là ảnh chụp từ loạt bài data storytelling của **Chartosaur**;
bản quyền thuộc tác giả gốc. Repo này chỉ tổng hợp và gắn nhãn để học tập, tham khảo.
