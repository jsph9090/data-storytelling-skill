# Visual Catalog — Ảnh mẫu đã gắn nhãn BAD / GOOD

Tất cả ảnh nằm trong `../examples/`. Tên file = `<nhóm>_<mô-tả>.png`.

## Cách đọc nhãn

| Nhãn | Ý nghĩa | Hành động |
|---|---|---|
| ❌ **BAD** | Cách vẽ thô, gây nhiễu, hoặc gây hiểu lầm | **Không** dùng khi trình bày / kể chuyện |
| ⚠️ **DISCOVERY-ONLY** | Chấp nhận được khi người đọc tự khám phá (analyst), nhưng **sai** cho báo cáo / slide / dashboard ra quyết định | Chỉ dùng cho bảng tra cứu nội bộ |
| ✅ **GOOD** | Cách vẽ có câu chuyện | **Áp dụng** |
| 📘 **REF** | Tài liệu tham khảo (danh mục chart, cheat sheet), không có đúng/sai | Dùng để chọn phương án |
| 🚧 **WARNING** | Chart hợp lệ nhưng có giới hạn cần kiểm tra | Dùng có điều kiện |

**Nhãn gắn theo TỪNG PANEL, không gắn cho cả ảnh.** Một ảnh thường chứa cả bad case lẫn good case
đặt cạnh nhau để so sánh, nên không ảnh nào là "ảnh BAD" hay "ảnh GOOD" nguyên khối. Cột "Bố cục"
cho biết panel nào mang nhãn nào:
- Đa số: **TRÊN = ❌ BAD ("Show the data") / DƯỚI = ✅ GOOD**.
- Một số: **TRÁI ❌ → PHẢI ✅** (`dashboard_tip-*`, `anchor_spent-vs-budget-*`).
- Ảnh chỉ có **một panel** (KPI card, case study, chart tham khảo…) mới mang một nhãn duy nhất.
  Khi đó nội dung cột ❌ là bad case **ngầm định, không có trong ảnh** — ghi ra để biết đang tránh điều gì.
- Ảnh `principle_*`: cả hai panel đều đúng tùy người xem — trên dùng cho Discovery, dưới dùng cho Direction.

Khi đọc một ảnh mẫu, luôn tra bảng này trước — **chỉ bắt chước panel ✅, không tái tạo panel ❌**.

---

## principle_ — Discovery vs Direction

| File | Bố cục | ❌/⚠️ Phần tránh | ✅ Phần áp dụng |
|---|---|---|---|
| `principle_discovery-vs-direction-line-annotated.png` | Trên ⚠️ / Dưới ✅ | Line + dải CI 95%, tiêu đề chung chung "Signups (n)" | Tiêu đề kết luận "Down in April, Up by December", chấm đỏ + chú thích 3 sự kiện tại điểm gãy |
| `principle_discovery-vs-direction-bar-sorted-highlight.png` | Trên ⚠️ / Dưới ✅ | Bar dọc có error bar, xếp alphabet, một màu cho tất cả | Bar ngang **sắp xếp giảm dần**, top 2 tô tím, còn lại xám, nhãn số trực tiếp, tiêu đề "Slate & Cobalt Are the Clear Winners" |
| `principle_discovery-vs-direction-dumbbell-to-arrows.png` | Trên ⚠️ / Dưới ✅ | Dumbbell xanh/cam phải đọc legend t1/t2, không sắp xếp | Arrow chart sắp theo mức thay đổi, **xanh = tăng / đỏ = giảm**, nhãn +27/−22, tiêu đề "Three Grew. Two Went Backwards." |

## focus_ — Dẫn mắt

| File | Bố cục | ❌ Tránh | ✅ Áp dụng |
|---|---|---|---|
| `focus_noise-vs-signal-one-color-rest-grey.png` | Trên ❌ / Dưới ✅ | Mọi đường đều có màu riêng (cầu vồng) → nhiễu | 1 đường đỏ là tín hiệu, các đường khác xám |
| `focus_line-highlight-segment-below-threshold.png` | Trên ❌ / Dưới ✅ | Cả đường cùng một màu, không biết nhìn đâu | Đường xám, chỉ đoạn rơi dưới ngưỡng tô đỏ + mũi tên |
| `focus_multiline-to-leader-eras-shaded.png` | Trên ❌ / Dưới ✅ | 3 đường giao nhau, người xem tự tìm ai dẫn đầu | Tô vùng nền theo giai đoạn dẫn đầu (Alpha → Beta 2004 → Gamma 2015), đường không dẫn đầu xám |
| `focus_spaghetti-to-small-multiples.png` | Trên ❌ / Dưới ✅ | 4 đường chồng nhau (spaghetti) | Small multiples: mỗi ô nhấn 1 series, nền là các series khác màu xám |
| `focus_bar-concentration-bracket-share-of-total.png` | Trên ❌ / Dưới ✅ | Bar xám không có điểm nhấn | 3 thanh cuối tô đỏ + ngoặc "28% of total" |

## annotate_ — Chú thích & ý nghĩa

| File | Bố cục | ❌ Tránh | ✅ Áp dụng |
|---|---|---|---|
| `annotate_line-event-marker-post-event-red.png` | Trên ❌ / Dưới ✅ | Đường tụt nhưng không giải thích | Đường dọc nét đứt "Event", đoạn sau sự kiện tô đỏ |
| `annotate_turning-point-event-line.png` | Trên ❌ / Dưới ✅ | Các đường đổi chiều mà không có mốc | Đường dọc "Event X", đoạn sau bước ngoặt tô đỏ |
| `annotate_line-multiple-events-abc.png` | Trên ❌ / Dưới ✅ | Đường nhiều lần gãy không chú thích | Chấm đỏ + nhãn Event A/B/C tại từng điểm gãy |
| `annotate_line-drawdown-recovery-days.png` | Trên ❌ / Dưới ✅ | Đường lên xuống không đo lường | Tô vùng sụt giảm + ghi "20 days / 14 days" để hồi phục |
| `annotate_scatter-to-quadrant-meaning-2x2.png` | Trên ❌ / Dưới ✅ | Scatter Effort × Value không có ý nghĩa vùng | Chia 4 góc có tên: Quick wins / Major projects / Fill-ins / Avoid |

## anchor_ — Mốc so sánh

| File | Bố cục | ❌ Tránh | ✅ Áp dụng |
|---|---|---|---|
| `anchor_types-cheat-sheet.png` | 📘 REF (ảnh đơn) | — | 6 loại anchor: kỳ trước, tiến độ goal, đồng nhóm, benchmark, TB lịch sử, baseline cố định |
| `anchor_spent-vs-budget-bullet-bar.png` | **Trái ❌ / Phải ✅** | "Money Spent": chỉ có số tiền, không biết nhiều hay ít | "Spent vs Budget": thanh đỏ trên nền xám = budget, nhãn 60% |
| `anchor_bar-budget-line-excess-red.png` | Trên ❌ / Dưới ✅ | Bar cầu vồng, không có mốc | Bar xám + đường Budget nét đứt, phần vượt tô đỏ có số (10, 16) |
| `anchor_bar-variance-to-target-plus-minus.png` | Trên ❌ / Dưới ✅ | Bar mỗi cột một màu, không có target | Bar xám + đường Target, phần chênh xanh (+7, +16) / đỏ (−12, −7) |
| `anchor_line-vs-plan-shortfall-gap-shaded.png` | Trên ❌ / Dưới ✅ | Đường đi lên trông như tốt | Đường Plan nét đứt, tô vùng hụt, "Shortfall −37%" → thật ra đang thiếu |
| `anchor_beeswarm-pass-threshold-percent-below.png` | Trên ❌ / Dưới ✅ | Beeswarm xám không ngưỡng | Đường Pass mark, điểm dưới ngưỡng tô đỏ, "12% / 48% / 68% below" |
| `anchor_table-heat-highlight-plus-sparklines.png` | Trên ❌ / Dưới ✅ | Bảng số trần | Tô vàng ô nổi bật + cột sparkline 5 năm (xanh tăng / đỏ giảm) |

## kpi_ — KPI card (mỗi ảnh 1 panel ✅; cột ❌ là bad case ngầm định, không có trong ảnh)

| File | Bố cục | ❌ Tránh | ✅ Áp dụng |
|---|---|---|---|
| `kpi_card-bar-vs-target-gap.png` | ✅ ảnh đơn | Ghi "$4.2M" trơ trọi | Thanh $4.2M + đường "November target $5.4M" + phần thiếu "−$1.2M" |
| `kpi_card-qualitative-band-weak-fair-strong.png` | ✅ ảnh đơn | Như trên | Chấm $4.2M trên dải Weak / Fair / Strong |
| `kpi_card-value-on-distribution-percentile.png` | ✅ ảnh đơn | Như trên | "Us $4.2M" trên đường phân phối: Bottom 6% / Top 94% |

## compare_ — So sánh & thay đổi

| File | Bố cục | ❌ Tránh | ✅ Áp dụng |
|---|---|---|---|
| `compare_grouped-bar-to-slope-chart-movers.png` | Trên ❌ / Dưới ✅ | Grouped bar 2 năm + legend, khó thấy ai tăng/giảm | Slope chart, nhãn trực tiếp hai đầu ("Apples 8 → 45") |
| `compare_side-by-side-bars-to-dumbbell.png` | Trên ❌ / Dưới ✅ | 2 bar chart tách rời, mắt phải đối chiếu qua lại | Dumbbell: 2 chấm trên cùng trục, đường nối = chênh lệch |
| `compare_paired-bars-to-span-range-bar.png` | Trên ❌ / Dưới ✅ | Cặp bar cũ/mới đặt chồng | Span bar từ giá trị cũ → mới (72→91, 34→86, 21→69) |
| `compare_raw-vs-per-capita-normalized.png` | Trên ❌ / Dưới ✅ | Metric thô khi các đối tượng khác quy mô (A dẫn đầu sai) | Metric/Capita: thứ hạng đổi hẳn (E, C dẫn đầu) |
| `compare_100pct-stacked-to-marimekko-show-scale.png` | Trên ❌ (khi quy mô khác nhau) / Dưới ✅ | 100% stacked che mất quy mô thật | Marimekko: độ rộng cột = $20B / $30B / $60B |
| `compare_likert-diverging-stacked-bar-unlabeled.png` | ✅ 1 panel (bản dựng, chưa nhãn) | *(ngầm định, không có trong ảnh)* Stacked 100% thường, neutral nằm giữa | Diverging: disagree trái / agree phải của trục 0, neutral tách riêng bên phải |
| `compare_likert-diverging-stacked-bar-labeled.png` | ✅ 1 panel (bản hoàn chỉnh) | *(ngầm định)* Như trên | Như trên + nhãn % trong từng đoạn |

## dist_ — Phân phối

| File | Bố cục | ❌ Tránh | ✅ Áp dụng |
|---|---|---|---|
| `dist_average-bars-vs-boxplot.png` | Trên ❌ / Dưới ✅ | 4 cột trung bình bằng nhau → kết luận sai "giống nhau" | Box plot lộ ra độ phân tán, outlier khác nhau |
| `dist_average-bars-vs-beeswarm.png` | Trên ❌ / Dưới ✅ | Chỉ trung bình | Beeswarm: thấy B có 2 cụm, D có outlier |
| `dist_average-bars-vs-density-overlay.png` | Trên ❌ / Dưới ✅ | Chỉ trung bình | Các đường density chồng lớp |
| `dist_average-bars-vs-ecdf.png` | Trên ❌ / Dưới ✅ | Chỉ trung bình | ECDF (tích lũy) cho so sánh phân vị |
| `dist_dots-to-ridgeline-distribution.png` | Trên ❌ / Dưới ✅ | 1 chấm / nhóm, mất hình dạng | Ridgeline |
| `dist_scatter-to-hexbin-density.png` | Trên ❌ / Dưới ✅ | Scatter quá dày, điểm chồng | Hexbin heatmap mật độ |
| `dist_density-plus-rug-reveal-detail.png` | Trên ⚠️ (thiếu chi tiết) / Dưới ✅ | Chỉ đường density mượt | Density + rug plot (từng quan sát) |
| `dist_kde-two-groups.png` | 📘 REF | — | KDE A vs B chồng lớp |
| `dist_butterfly-back-to-back-histogram.png` | 📘 REF | — | Histogram A trái / B phải chung trục |
| `dist_boxplot-two-groups.png` | 📘 REF | — | Box plot A vs B |
| `dist_histograms-stacked-shared-axis.png` | 📘 REF | — | 2 histogram xếp dọc chung trục x |
| `dist_violin-two-groups.png` | 📘 REF | — | Violin A vs B |

## uncertainty_ — Bất định & dữ liệu thiếu

| File | Bố cục | ❌ Tránh | ✅ Áp dụng |
|---|---|---|---|
| `uncertainty_forecast-dashed-vs-confidence-fan.png` | Trên ❌ / Dưới ✅ | Forecast chỉ là một nét đứt (giả vờ chắc chắn) | Nét đứt + dải confidence loe rộng dần |
| `uncertainty_missing-data-dotted-line-note.png` | Trên ❌ / Dưới ✅ | Đường liền nối qua năm thiếu dữ liệu (che giấu) | Chấm ở năm có dữ liệu, nét chấm + ghi chú "missing data 2021, 2022" |

## label_ — Nhãn

| File | Bố cục | ❌ Tránh | ✅ Áp dụng |
|---|---|---|---|
| `label_legend-box-vs-inline-labels.png` | Trên ❌ / Dưới ✅ | Hộp legend tách rời ("Legend Afterthought") | Nhãn ở cuối mỗi đường ("Legend Inline") |

## chartchoice_ — Chọn chart

| File | Bố cục | ❌ Tránh | ✅ Áp dụng |
|---|---|---|---|
| `chartchoice_same-data-chart-catalog.png` | 📘 REF | — | 1 bảng dữ liệu → 6 cách vẽ; chọn theo thông điệp |
| `chartchoice_differences-dumbbell-vs-totals-stacked.png` | 📘 REF (cả hai đúng) | Cố nói cả chênh lệch lẫn tổng trong một chart | Muốn nhấn chênh lệch → dumbbell; muốn nhấn tổng → stacked bar |
| `chartchoice_slope-chart-limitations.png` | 🚧 WARNING | Slope khi nhãn sát nhau (chồng lấn) hoặc hai cột không có thứ tự thời gian | Chỉ dùng slope khi có thứ tự trước/sau và nhãn đủ thưa |

## dashboard_ — Dashboard

| File | Bố cục | ❌ Tránh | ✅ Áp dụng |
|---|---|---|---|
| `dashboard_tip-add-anchors-target-line.png` | **Trái ❌ → Phải ✅** | Bar không mốc | Thêm đường "Sales Target" nét đứt |
| `dashboard_tip-dont-show-everything-one-idea.png` | **Trái ❌ → Phải ✅** | View Sales lẫn Server uptime, Build Failures | Chỉ giữ ô liên quan Sales |
| `dashboard_tip-reduce-clutter-one-color.png` | **Trái ❌ → Phải ✅** | Gridline dày + mỗi cột một màu | Một màu, bỏ grid |
| `dashboard_tip-add-hierarchy-size-placement.png` | **Trái ❌ → Phải ✅** | Lưới 3×3 ô bằng nhau | 1 ô lớn + các ô nhỏ theo mức quan trọng |
| `dashboard_number-only-vs-context-goal-yoy-target.png` | Trên ❌ / Dưới ✅ | Tile chỉ có số ($1.8M, 3.4%) | "82% of goal", "▲18% vs last year", bar năm nay vs năm trước, thanh tới target |
| `dashboard_even-grid-vs-grouped-by-related.png` | Trên ❌ / Dưới ✅ | 9 tile xếp đều không nhóm | Nhóm Revenue / Audience / Performance, khung màu nền nhạt |
| `dashboard_show-everything-vs-what-matters-hero.png` | Trên ❌ / Dưới ✅ | 8 tile ngang hàng | 1 tile hero Revenue + 3 tile phụ |

## pitfall_ — Bẫy gây hiểu lầm

| File | Bố cục | ❌ Tránh | ✅ Áp dụng |
|---|---|---|---|
| `pitfall_cherry-picked-window-vs-full-picture.png` | Trên ❌ / Dưới ✅ | "What they show you": chỉ đoạn tăng gần đây | "The full picture": xu hướng giảm dài hạn, đoạn tăng chỉ là nhịp hồi (tô vùng) |
| `pitfall_bump-chart-rank-overtake.png` | ❌ **toàn ảnh** | Bump chart "The Overtake" — kể chuyện thứ hạng khi giá trị gần nhau | — |
| `pitfall_bump-chart-real-values-ranks-clustered.png` | ✅ bước kiểm chứng | — | Vẽ giá trị thật: hạng 3–8 gần như trùng → không có câu chuyện "vượt mặt" |

## case_ — Case study chart điện năng châu Âu 2018 (tất cả ✅)

| File | Bố cục | ✅ Bài học áp dụng |
|---|---|---|
| `case_europe-electricity-annotated-variable-width-bars.png` | ✅ | Độ rộng cột = tổng sản lượng; callout ngắn tại điểm đáng chú ý (Na Uy, Đức, Pháp, Ba Lan) |
| `case_legend-as-mini-diagram.png` | ✅ | Legend là sơ đồ mini giải thích cách đọc, không chỉ là bảng màu |
| `case_anchor-baseline-matches-comparison-goal.png` | Chart chính ✅; 2 hình nhỏ bên phải: trên "anchored on" ✅ / dưới "instead of" ❌ | Đặt trục 0 tại ranh giới sạch / không sạch thay vì ở đáy |
| `case_sorted-by-key-metric.png` | ✅ | Sắp theo % điện sạch để trả lời ngay câu hỏi hiển nhiên |
