# data-storytelling — Claude Code skill

Skill giúp Claude phân tích và trình bày dữ liệu theo hướng storytelling: chọn ý chính, chọn chart
theo thông điệp, thêm mốc so sánh (target, kỳ trước, benchmark), dẫn mắt người xem và tránh các
cách vẽ gây hiểu lầm.

- [SKILL.md](SKILL.md) — quy trình 7 bước + bảng "Tránh → Áp dụng".
- [references/visual-catalog.md](references/visual-catalog.md) — 62 ảnh mẫu, gắn nhãn ❌ BAD / ✅ GOOD theo từng panel.
- `examples/` — ảnh mẫu, tên file mô tả nội dung (`<nhóm>_<mô-tả>.png`).

## Cài đặt

Clone thẳng vào thư mục skills của Claude Code:

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

```powershell
git -C "$env:USERPROFILE\.claude\skills\data-storytelling" pull
```

## Lưu ý

Ảnh trong `examples/` là ảnh chụp các bài đăng của Chartosaur, chỉ dùng tham khảo nội bộ.
Không chuyển repo sang public.
