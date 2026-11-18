---
name: data-storytelling
description: Tư duy phân tích và trình bày dữ liệu theo hướng storytelling (kể chuyện bằng dữ liệu). Dùng khi cần phân tích số liệu rồi trình bày thành chart, báo cáo, slide, dashboard hoặc KPI card cho người khác đọc — ví dụ báo cáo hiệu quả quảng cáo, so sánh kỳ, CPA vs target, phân tích phân phối, dashboard theo dõi. Trigger khi người dùng nói "visualize", "vẽ chart", "trình bày số liệu", "làm dashboard", "báo cáo", "insight", "storytelling", "chart nào phù hợp". Bổ sung cho skill `dataviz` (màu sắc/kỹ thuật vẽ): skill này quyết định NÓI GÌ và CHỈ VÀO ĐÂU, còn `dataviz` quyết định vẽ thế nào cho đẹp.
---

# Data Storytelling — Phân tích & minh họa dữ liệu

Nguyên tắc cốt lõi: **"Show the data" là chưa đủ — phải "Show the point."**
Mỗi biểu đồ tốt là một phép biến đổi từ *dữ liệu thô* sang *ý chính*: cùng dữ liệu đó, nhưng
người xem hiểu ngay điều cần hiểu mà không phải tự suy luận.

Bộ ví dụ minh họa (62 ảnh) nằm trong `examples/`. **Mỗi ảnh chứa cả BAD case lẫn GOOD case**,
và đã được gắn nhãn ❌ BAD / ⚠️ DISCOVERY-ONLY / ✅ GOOD / 📘 REF / 🚧 WARNING trong
[references/visual-catalog.md](references/visual-catalog.md).

> **Quy tắc đọc ảnh mẫu:** nhãn gắn theo **từng panel**, không cho cả ảnh — một ảnh thường đặt
> bad case và good case cạnh nhau để so sánh. Mặc định nửa TRÊN (tiêu đề "Show the data") = ❌ BAD, nửa DƯỚI = ✅ GOOD.
> Ngoại lệ: `dashboard_tip-*` và `anchor_spent-vs-budget-*` là TRÁI ❌ → PHẢI ✅;
> `pitfall_bump-chart-rank-overtake` là ❌ toàn ảnh; ảnh `kpi_`, `case_`, `dist_*-two-groups` là ✅/📘 ảnh đơn.
> **Luôn tra catalog trước khi lấy một ảnh làm mẫu — chỉ bắt chước phần ✅, không bao giờ tái tạo phần ❌.**

## Bảng tránh → áp dụng (tóm tắt từ toàn bộ ảnh mẫu)

| ❌ TRÁNH (bad case) | ✅ ÁP DỤNG (good case) | Ảnh mẫu |
|---|---|---|
| Tiêu đề mô tả chung chung ("Signups theo tháng") | Tiêu đề là kết luận ("Giảm tháng 4, phục hồi tháng 12") | `principle_*` |
| Mỗi cột / mỗi đường một màu (cầu vồng) | 1 màu nhấn cho ý chính, còn lại xám | `focus_noise-vs-signal-*`, `dashboard_tip-reduce-clutter-*` |
| Sắp xếp alphabet / theo thứ tự dữ liệu gốc | Sắp theo giá trị hoặc theo chỉ số then chốt | `principle_…-bar-sorted-highlight`, `case_sorted-by-key-metric` |
| Hộp legend tách rời | Nhãn trực tiếp ở cuối đường / trên thanh | `label_legend-box-vs-inline-labels` |
| Gridline dày, trang trí thừa | Bỏ grid, tối giản | `dashboard_tip-reduce-clutter-*` |
| Con số đứng một mình | Kèm target / kỳ trước / benchmark / percentile / dải Weak–Fair–Strong | `anchor_*`, `kpi_*` |
| Đường đi lên trông "tốt" nhưng không so với plan | Đường plan nét đứt + tô vùng hụt + "Shortfall −37%" | `anchor_line-vs-plan-shortfall-*` |
| 2 bar chart đặt cạnh nhau để so sánh | Dumbbell / slope / arrow chart trên cùng một trục | `compare_side-by-side-bars-to-dumbbell`, `compare_grouped-bar-to-slope-*` |
| Grouped bar 2 kỳ để nói "ai tăng ai giảm" | Slope chart hoặc arrow chart xanh tăng / đỏ giảm | `compare_grouped-bar-to-slope-*`, `principle_…-dumbbell-to-arrows` |
| Số thô khi các đối tượng khác quy mô | Chuẩn hóa (per capita, rate, %) | `compare_raw-vs-per-capita-normalized` |
| 100% stacked khi quy mô các nhóm khác nhau | Marimekko (độ rộng = quy mô) | `compare_100pct-stacked-to-marimekko-*` |
| Chỉ vẽ trung bình | Box plot / beeswarm / density / ECDF / ridgeline | `dist_average-bars-vs-*`, `dist_dots-to-ridgeline-*` |
| Scatter quá dày điểm chồng | Hexbin / density | `dist_scatter-to-hexbin-density` |
| Spaghetti nhiều đường | Small multiples hoặc 1 đường nhấn + xám | `focus_spaghetti-to-small-multiples` |
| Đường gãy / tụt không giải thích | Đường dọc sự kiện, chấm + nhãn Event A/B/C, đổi màu sau sự kiện | `annotate_*` |
| Scatter trần không có nghĩa vùng | Chia 4 góc phần tư có tên | `annotate_scatter-to-quadrant-meaning-2x2` |
| Forecast một nét đứt (giả vờ chắc chắn) | Nét đứt + dải confidence loe rộng | `uncertainty_forecast-*` |
| Đường liền nối qua khoảng thiếu dữ liệu | Nét chấm + ghi chú "missing data" | `uncertainty_missing-data-*` |
| Cắt khung thời gian chỉ lấy đoạn đẹp | Hiển thị toàn bộ, tô vùng đoạn đang nói | `pitfall_cherry-picked-window-*` |
| Bump chart khi giá trị gần như bằng nhau | Vẽ giá trị thật trước; chỉ dùng rank khi thứ hạng là trọng tâm | `pitfall_bump-chart-*` |
| Slope chart khi nhãn chồng nhau / không có thứ tự thời gian | Dumbbell hoặc bar ngang | `chartchoice_slope-chart-limitations` |
| Likert stacked thường, neutral nằm giữa | Diverging quanh trục 0, neutral tách riêng | `compare_likert-*` |
| Dashboard nhiều tile ngang hàng, lẫn chủ đề | 1 tile hero + tile phụ, nhóm theo liên quan, 1 view = 1 ý | `dashboard_*` |

---

## Bước 0 — Xác định nhiệm vụ của chart: Discovery hay Direction?

| | **Discovery** (khám phá) | **Direction** (dẫn dắt) |
|---|---|---|
| Người đọc | Analyst, người muốn tự tra cứu | Sếp, khách hàng, người ra quyết định |
| Gánh nặng | Người đọc tự tìm insight | Người làm chart đã tìm sẵn insight |
| Hình thức | Đầy đủ: trục, error bar, CI, legend, sắp theo alphabet | Tiêu đề = kết luận, sắp xếp theo ý, 1 màu nhấn + xám, nhãn trực tiếp, chú thích sự kiện |
| Ví dụ tiêu đề | "Signups (n) theo tháng" | "Giảm trong tháng 4, phục hồi vào tháng 12" |

→ Báo cáo/slide/dashboard cho người khác **mặc định là Direction**. Xem
`examples/principle_discovery-vs-direction-*.png`.

## Bước 1 — Chốt câu hỏi và ý chính TRƯỚC khi vẽ

1. Người xem cần **quyết định** gì sau khi nhìn chart? (tăng/giảm budget, đổi target, dừng chiến dịch…)
2. Viết ý chính thành **một câu khẳng định** → câu đó chính là tiêu đề chart (action title).
   - Tệ: "CPA theo chiến dịch". Tốt: "2 chiến dịch vượt Target CPA, chiếm 70% chi phí lãng phí".
3. **Analyst quyết định cái gì quan trọng**: cùng một bảng số, nhấn *chênh lệch* (dumbbell) khác
   hoàn toàn với nhấn *tổng* (stacked bar). Chọn một, đừng cố nói cả hai trong một chart.
   (`chartchoice_differences-dumbbell-vs-totals-stacked.png`, `chartchoice_same-data-chart-catalog.png`)
4. Mỗi chart / mỗi view chỉ gắn với **một ý, một quyết định hoặc một chủ đề**.

## Bước 2 — Phân tích cho đúng trước khi kể chuyện (checklist trung thực)

- [ ] **Chuẩn hóa** khi quy mô khác nhau: per capita, per click, %, rate. Thứ hạng có thể đảo ngược
      hoàn toàn sau khi chuẩn hóa. (`compare_raw-vs-per-capita-normalized.png`)
- [ ] **Đừng chỉ nhìn trung bình**: 4 nhóm có cùng mean có thể có phân phối khác hẳn (hẹp, hai đỉnh,
      trải rộng, outlier). Kiểm tra bằng box plot / beeswarm / density / ECDF. (`dist_average-bars-vs-*.png`)
- [ ] **Xem đủ khung thời gian**: một đoạn "tăng trưởng" có thể chỉ là nhịp hồi trong xu hướng giảm dài
      hạn. Đừng cắt khung để đẹp số. (`pitfall_cherry-picked-window-vs-full-picture.png`)
- [ ] **Thứ hạng ≠ độ lớn**: bump chart phóng đại khác biệt khi giá trị thực gần như bằng nhau.
      Kiểm tra giá trị thật trước khi kể chuyện "vượt mặt". (`pitfall_bump-chart-*.png`)
- [ ] **Dữ liệu thiếu phải lộ ra**: nối nét đứt + ghi chú "thiếu dữ liệu 2021–2022", chấm điểm ở các
      giá trị có thật. (`uncertainty_missing-data-dotted-line-note.png`)
- [ ] **Dự báo phải kèm độ tin cậy**: nét đứt + dải confidence loe rộng dần.
      (`uncertainty_forecast-dashed-vs-confidence-fan.png`)
- [ ] **Biết giới hạn của chart**: slope chart ngầm định thứ tự thời gian (A trước B) và dễ chồng nhãn.
      (`chartchoice_slope-chart-limitations.png`)
- [ ] Tổng thể tích: khi tỷ lệ % giống nhau nhưng quy mô khác nhau, hãy cho thấy quy mô
      (Marimekko: độ rộng = quy mô). (`compare_100pct-stacked-to-marimekko-show-scale.png`)

## Bước 3 — Chọn dạng chart theo THÔNG ĐIỆP (không theo thói quen)

| Thông điệp muốn nói | Dạng chart nên dùng | Ví dụ |
|---|---|---|
| Ai đứng đầu / xếp hạng | Bar ngang **đã sắp xếp**, nhấn top-N | `principle_discovery-vs-direction-bar-sorted-highlight` |
| Thay đổi giữa 2 thời điểm | Slope chart, arrow chart (xanh tăng / đỏ giảm), span bar | `compare_grouped-bar-to-slope-chart-movers`, `principle_…-dumbbell-to-arrows`, `compare_paired-bars-to-span-range-bar` |
| Chênh lệch giữa 2 nhóm trên nhiều mục | Dumbbell (2 chấm nối 1 đường) | `compare_side-by-side-bars-to-dumbbell` |
| Xu hướng theo thời gian | Line; nhiều series → small multiples hoặc 1 màu nhấn + xám | `focus_spaghetti-to-small-multiples` |
| Ai dẫn đầu từng giai đoạn | Line + tô vùng theo "kỷ nguyên" của series dẫn đầu | `focus_multiline-to-leader-eras-shaded` |
| Thứ tự là trọng tâm (BXH cuối mùa) | Bump chart — **chỉ khi** thứ hạng thật sự là điều quan trọng | `pitfall_bump-chart-rank-overtake` |
| Cơ cấu % + quy mô | 100% stacked → Marimekko | `compare_100pct-stacked-to-marimekko-show-scale` |
| Khảo sát Likert | Diverging stacked bar, neo tại 0, **neutral tách riêng** bên cạnh | `compare_likert-diverging-stacked-bar-labeled` |
| Phân phối 1–2 nhóm | Histogram, KDE, box, violin, butterfly | `dist_*-two-groups`, `dist_butterfly-…`, `dist_histograms-…` |
| Phân phối nhiều nhóm | Ridgeline, beeswarm, box plot, ECDF | `dist_dots-to-ridgeline-distribution`, `dist_average-bars-vs-*` |
| Nhiều điểm chồng lên nhau | Hexbin / density thay cho scatter | `dist_scatter-to-hexbin-density` |
| Ưu tiên / phân loại 2 chiều | Scatter + 4 góc phần tư có tên (Quick wins / Major projects / Fill-ins / Avoid) | `annotate_scatter-to-quadrant-meaning-2x2` |
| Bảng số cần đọc chi tiết | Bảng + tô màu ô nổi bật + cột sparkline xu hướng | `anchor_table-heat-highlight-plus-sparklines` |
| Một con số KPI | KPI card **kèm mốc so sánh** (xem Bước 4) | `kpi_card-*` |

Quy tắc: **so sánh chênh lệch → đặt các giá trị trên cùng một trục** (dumbbell, slope) thay vì để hai
biểu đồ cạnh nhau bắt mắt người xem tự đối chiếu.

## Bước 4 — Thêm "mỏ neo" (anchor): một con số đứng một mình không nói lên điều gì

Nếu người xem không biết ngay một con số là **tốt hay xấu, đang lên hay xuống, có đáng lo không**
→ chart đang thiếu câu chuyện. Anchoring dẫn tới quyết định.

| Loại anchor | Ví dụ câu chữ | Cách vẽ |
|---|---|---|
| So với kỳ trước | "+12% vs tuần trước" | Mũi tên ▲▼ màu, delta cạnh số |
| Tiến độ tới mục tiêu | "95% target đạt" | Bullet bar: phần đã đạt trên nền xám = target |
| So với đồng nhóm | "Top 20% reps" | Đặt giá trị lên phân phối, ghi percentile |
| Benchmark ngành | "Thấp hơn TB ngành 5%" | Đường tham chiếu nét đứt |
| Trung bình lịch sử | "+18% so với TB 6 tháng" | Đường TB + vùng dao động |
| Baseline cố định | "+3% vs baseline 01/2022" | Đặt trục 0 tại baseline |

Kỹ thuật vẽ anchor (đều có ảnh mẫu `anchor_*`, `kpi_*`):
- **Đường target/budget nét đứt** + phần vượt tô đỏ kèm số (`anchor_bar-budget-line-excess-red`).
- **Variance to target**: cột xám + đoạn chênh xanh (+) / đỏ (−) có nhãn (`anchor_bar-variance-to-target-plus-minus`).
- **Plan vs actual**: đường plan nét đứt, tô vùng thiếu hụt, ghi "Shortfall −37%" (`anchor_line-vs-plan-shortfall-gap-shaded`).
- **Ngưỡng đạt** (pass mark): điểm dưới ngưỡng tô đỏ + "% dưới ngưỡng" mỗi nhóm (`anchor_beeswarm-pass-threshold-percent-below`).
- **Dải định tính** Weak / Fair / Strong — "cho thấy thế nào là tốt" (`kpi_card-qualitative-band-weak-fair-strong`).
- **Vị trí trên phân phối**: "Chúng ta $4.2M — Bottom 6%" (`kpi_card-value-on-distribution-percentile`).
- **Chọn baseline phù hợp mục tiêu so sánh** (vd. trục 0 đặt giữa phần sạch/không sạch) (`case_anchor-baseline-matches-comparison-goal`).

## Bước 5 — Dẫn mắt người xem (direct attention)

1. **Xám hóa mọi thứ, tô màu một thứ**: series/cột quan trọng có màu nhấn, phần còn lại xám nhạt
   (`focus_noise-vs-signal-one-color-rest-grey`, `principle_…-bar-sorted-highlight`).
2. **Tô riêng một đoạn**: chỉ phần đường đi xuống dưới ngưỡng mới đổi màu đỏ + mũi tên
   (`focus_line-highlight-segment-below-threshold`).
3. **Đánh dấu sự kiện / bước ngoặt**: đường dọc nét đứt "Event X", phần sau sự kiện đổi màu
   (`annotate_line-event-marker-post-event-red`, `annotate_turning-point-event-line`).
4. **Chú thích nhiều mốc** A/B/C ngay tại điểm trên đường — giải thích *vì sao* số thay đổi
   (`annotate_line-multiple-events-abc`, `principle_discovery-vs-direction-line-annotated`).
5. **Gom nhóm & đếm thay người xem**: ngoặc nhọn "28% tổng" cho nhóm cột cuối
   (`focus_bar-concentration-bracket-share-of-total`); "20 ngày / 14 ngày" để hồi phục
   (`annotate_line-drawdown-recovery-days`).
6. **Gán ý nghĩa cho không gian**: chia góc phần tư và đặt tên vùng (`annotate_scatter-to-quadrant-meaning-2x2`).
7. **Sắp xếp theo chỉ số then chốt** — trả lời ngay câu hỏi hiển nhiên (`case_sorted-by-key-metric`).
8. **Màu mang nghĩa**: xanh = tăng/tốt, đỏ = giảm/xấu/vượt ngưỡng, xám = bối cảnh. Không dùng cầu vồng.

## Bước 6 — Giảm nhiễu & ghi nhãn

- Bỏ gridline dày, viền, màu cầu vồng → một màu, ít đường kẻ (`dashboard_tip-reduce-clutter-one-color`).
- **Nhãn trực tiếp ở cuối đường** thay cho hộp legend (`label_legend-box-vs-inline-labels`).
- Nếu cần legend phức tạp, biến legend thành **mini-diagram** giải thích cách đọc (`case_legend-as-mini-diagram`).
- Ghi giá trị ngay trên thanh/điểm thay vì bắt người xem dò trục.
- Callout chữ ngắn cho các điểm đáng chú ý (`case_europe-electricity-annotated-variable-width-bars`).
- Tiêu đề = kết luận; phụ đề = bối cảnh (đơn vị, khoảng thời gian, nguồn).

## Bước 7 — Dashboard (khi trình bày nhiều chart cùng lúc)

1. **Đừng show mọi thứ**: loại các ô không phục vụ chủ đề của view (vd. server uptime trong dashboard sales)
   (`dashboard_tip-dont-show-everything-one-idea`, `dashboard_show-everything-vs-what-matters-hero`).
2. **Phân cấp (hierarchy)**: một ô "hero" lớn cho KPI chính ở góc trên trái, các ô phụ nhỏ hơn; dùng kích
   thước, vị trí, nhóm để dẫn mắt (`dashboard_tip-add-hierarchy-size-placement`).
3. **Nhóm theo liên quan**: Revenue / Audience / Performance, mỗi nhóm một khung màu nền nhạt
   (`dashboard_even-grid-vs-grouped-by-related`).
4. **Số kèm bối cảnh**: % of goal, ▲ so với năm trước, cột năm nay vs năm trước, thanh tiến độ tới target
   (`dashboard_number-only-vs-context-goal-yoy-target`, `dashboard_tip-add-anchors-target-line`).
5. **Giảm nhiễu** như Bước 6.

## Checklist cuối trước khi giao

- [ ] Tiêu đề có phải là một câu kết luận không? Người xem có hiểu ý chính trong 5 giây không?
- [ ] Mỗi chart chỉ một ý? Đã chọn nói *chênh lệch* hay *tổng* (không nói cả hai)?
- [ ] Mọi con số đều có anchor (target, kỳ trước, benchmark, phân phối)?
- [ ] Chỉ một (hoặc rất ít) màu nhấn, còn lại xám? Màu có nghĩa nhất quán?
- [ ] Đã sắp xếp theo thông điệp? Nhãn trực tiếp thay cho legend?
- [ ] Đã chuẩn hóa khi cần? Đã kiểm tra phân phối thay vì chỉ trung bình?
- [ ] Khung thời gian đầy đủ, không cherry-pick? Dữ liệu thiếu và độ bất định được thể hiện?
- [ ] Nếu là Discovery chart: đã đủ trục, đơn vị, error bar/CI, nguồn cho người tự khám phá chưa?

## Cách dùng skill này khi làm việc

1. Hỏi/xác định: người xem là ai, quyết định gì, Discovery hay Direction (Bước 0–1). Nếu chưa rõ, hỏi lại
   người dùng trước khi vẽ.
2. Chạy checklist phân tích (Bước 2) trên dữ liệu thật — ghi lại cảnh báo nếu có (mean che phân phối,
   thiếu dữ liệu, cần chuẩn hóa…).
3. Viết action title, chọn chart theo bảng Bước 3, tra `references/visual-catalog.md` để xem ảnh mẫu.
4. Thêm anchor (Bước 4), dẫn mắt (Bước 5), giảm nhiễu (Bước 6).
5. Về màu sắc, font, light/dark, code vẽ: theo skill `dataviz` nếu có.
6. Rà checklist cuối.

*Nguồn ví dụ: loạt bài "Show the data → Show the …" của Chartosaur (ảnh chụp màn hình lưu cục bộ để tham khảo nội bộ).*
