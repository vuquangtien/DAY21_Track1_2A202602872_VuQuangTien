# Lab 21 — Phân tích rủi ro AI qua case study thực tế

- **Họ và tên:** Vũ Quang Tiến
- **MSSV / mã học viên:** 2A202602872
- **Lớp:** Track 1 — 2A
- **Ngành đã chọn:** HR / tuyển dụng (AI sàng lọc và xếp hạng ứng viên)
- **Ngày hoàn thiện nguồn:** 07/10/2026

> **Cách đọc báo cáo:** Các câu có liên kết nguồn là dữ kiện/sự kiện được nguồn đó nêu. Những nhận định đánh giá trong Harm Map được ghi rõ là phân tích của tôi. Tôi không coi một rủi ro có thể xảy ra là thiệt hại đã được nguồn xác nhận.

## 1. Industry Risk Snapshot

| Nội dung | Đánh giá của tôi và lý do |
| --- | --- |
| Những tác hại chính có thể xảy ra | **Mất cơ hội việc làm** khi hệ thống chấm/rút gọn danh sách bất lợi cho một nhóm; **mất phẩm giá** khi ứng viên bị đánh giá bằng tín hiệu không liên quan đến năng lực; và **mất riêng tư** khi CV/video/phỏng vấn chứa dữ liệu cá nhân bị thu thập hoặc dùng sai mục đích. Người chịu tác động trực tiếp là ứng viên; nhà tuyển dụng cũng có nguy cơ tuyển sai và vi phạm nghĩa vụ chống phân biệt đối xử. |
| Mức độ high-stakes | **Cao.** Quyết định vào/ra ở vòng tuyển dụng ảnh hưởng trực tiếp đến thu nhập, con đường nghề nghiệp và cơ hội của một người. Dù AI chỉ “hỗ trợ”, việc tự động loại hoặc xếp hạng thấp có thể khiến ứng viên không tới được bước gặp con người. |
| Dữ liệu nhạy cảm có thể được sử dụng | CV (họ tên, liên hệ, lịch sử học tập/việc làm), ngày sinh/tuổi, giới tính hoặc tín hiệu suy ra giới tính, tình trạng khuyết tật, địa chỉ, video/giọng nói và câu trả lời phỏng vấn. Không đưa dữ liệu ứng viên thật vào repo. |
| Nhu cầu human review | **Cao.** Nhân sự có thẩm quyền cần kiểm tra các quyết định loại/xếp hạng bất lợi trước khi từ chối ứng viên, kiểm thử chênh lệch theo nhóm trước và trong khi vận hành, và có kênh để ứng viên yêu cầu xem xét lại. Không nên để điểm AI là quyết định cuối cùng. |

## 2. Case study 1 — Công cụ tuyển dụng thử nghiệm của Amazon có thiên lệch giới

### Brief Case

- **Tổ chức / sản phẩm AI:** Amazon; công cụ học máy nội bộ, thử nghiệm để rà soát và chấm CV cho các vị trí kỹ thuật.
- **Thời gian, địa điểm / bối cảnh:** Hoa Kỳ; nhóm Amazon xây dựng công cụ từ năm 2014. Đến năm 2015, công ty nhận ra công cụ không chấm các vị trí kỹ thuật theo cách trung lập về giới; bài điều tra được Reuters công bố ngày 10/10/2018.
- **AI được dùng để làm gì:** Tự động chấm ứng viên trên thang **1–5 sao** nhằm hỗ trợ tìm CV tốt và rút ngắn danh sách ứng viên.
- **Vấn đề hoặc sự kiện đáng chú ý:** Theo điều tra Reuters, mô hình đã học từ mẫu CV quá khứ mà phần lớn là của nam giới, nên hạ điểm các CV chứa từ “women’s” và CV của một số trường nữ sinh. Amazon đã thử sửa các trọng số nhưng sau đó giải thể nhóm làm công cụ. Reuters cũng dẫn lời Amazon rằng công cụ này **không được tuyển dụng viên dùng để đánh giá ứng viên**; vì vậy không đủ bằng chứng để khẳng định một ứng viên cụ thể đã bị từ chối bởi công cụ.
- **Số liệu có nguồn:** Dữ liệu huấn luyện gồm CV trong **10 năm**; công cụ chấm **1–5 sao**; việc xây dựng bắt đầu từ **2014** và vấn đề được nhận ra vào **2015**. Các số này mô tả phạm vi dữ liệu/cơ chế, không phải số người bị hại.
- **Nguồn:** [“Amazon scraps secret AI recruiting tool that showed bias against women” — Jeffrey Dastin, Reuters, 10/10/2018 (bản đăng lại đầy đủ)](https://finance.yahoo.com/news/amazon-scraps-secret-ai-recruiting-174002175.html). Tham chiếu độc lập trong hồ sơ điều trần của Quốc hội Hoa Kỳ cũng tóm tắt việc công cụ phạt CV có từ “women’s” và hạ đánh giá người tốt nghiệp trường nữ sinh: [U.S. House Committee on Energy and Commerce, 2019, tr. 17](https://www.govinfo.gov/content/pkg/CHRG-116hhrg37565/pdf/CHRG-116hhrg37565.pdf).
- **Phân biệt bằng chứng và nhận định:** Nguồn xác nhận bối cảnh thử nghiệm, 10 năm CV, thang 1–5, dấu hiệu thiên lệch và việc không triển khai cho tuyển dụng viên. Nhận định của tôi là một công cụ như vậy, nếu dùng để loại người, có thể gây mất cơ hội việc làm; nguồn không chứng minh thiệt hại đó đã xảy ra với ứng viên cụ thể.

### Harm Map Worksheet

| Trường | Phân tích của tôi |
| --- | --- |
| High-risk moment | Khi hệ thống chuyển CV thành điểm 1–5 hoặc dùng điểm đó để ưu tiên/loại ứng viên cho vị trí kỹ thuật. |
| Stakeholder bị ảnh hưởng | Ứng viên nữ và ứng viên có tín hiệu liên quan đến giới; tuyển dụng viên và Amazon (quyết định tuyển kém chất lượng/rủi ro phân biệt đối xử). |
| Failure mode | **Bias / fairness:** kết quả chấm không trung lập về giới. |
| Layer bắt đầu lỗi | **Grounding / dữ liệu đầu vào lịch sử** là căn cứ mạnh nhất: nguồn nêu mô hình học từ 10 năm CV chủ yếu của nam. Có thể liên quan đến Model, nhưng kiến trúc/thuật toán không được công bố nên chưa đủ bằng chứng để kết luận lỗi bắt đầu tại Model. |
| Harm xảy ra là gì? | **Đã được nguồn xác nhận:** công cụ chấm CV có dấu hiệu bất lợi theo giới. **Nguy cơ, chưa được nguồn xác nhận là đã xảy ra:** ứng viên nữ bị loại hoặc xếp sau, từ đó mất cơ hội phỏng vấn/việc làm. Reuters nêu công cụ không được dùng để tuyển dụng viên đánh giá ứng viên. |
| Harm lens | Opportunity loss (mất cơ hội) và dignity loss (bị đối xử không công bằng theo giới). |
| Severity | **High (đánh giá cá nhân)** nếu dùng ở vòng loại: mất cơ hội việc làm có thể ảnh hưởng lớn tới thu nhập và nghề nghiệp. Không chọn Critical vì nguồn không ghi nhận tổn hại thể chất hay thiệt hại đặc biệt nghiêm trọng đã xảy ra. |
| Scale | **Chưa đủ dữ liệu để định lượng.** Dữ liệu trải 10 năm cho thấy phạm vi tiềm năng đáng kể, nhưng nguồn không công bố số CV bị chấm, số ứng viên hay số người bị ảnh hưởng. |
| Probability | **Cao trong chính phiên bản đã được phát hiện:** thiên lệch đã được báo cáo. **Không thể suy ra tỷ lệ ứng viên bị hại**, vì không có số lần chấm hoặc tỷ lệ sai lệch. |
| Frequency | **Chưa đủ dữ liệu để đánh giá.** Nguồn cho biết vấn đề được phát hiện vào 2015, không nêu tần suất kết quả thiên lệch theo từng đợt tuyển dụng. |
| Vì sao? | Nhãn Bias dựa trên mô tả trực tiếp của Reuters về dữ liệu quá khứ và các tín hiệu “women’s”. Các mức Severity/Probability là phân tích của tôi; giới hạn quan trọng là công cụ là thử nghiệm và nguồn không chứng minh có ứng viên nào bị từ chối bởi nó. |

## 3. Case study 2 — iTutorGroup tự động loại ứng viên lớn tuổi

### Brief Case

- **Tổ chức / sản phẩm AI:** iTutorGroup và các công ty tích hợp; phần mềm nộp đơn/ sàng lọc gia sư trực tuyến. Nguồn chính thức gọi đây là “tutor application software” được lập trình để tự động từ chối, **không nêu kiến trúc hay khẳng định đây là machine learning**. Vì vậy case này được phân tích như một hệ thống tuyển dụng tự động/thuật toán; không suy diễn nó là mô hình ML.
- **Thời gian, địa điểm / bối cảnh:** Ứng viên gia sư ở Hoa Kỳ làm việc từ xa cho dịch vụ dạy tiếng Anh cho học viên ở Trung Quốc. EEOC Hoa Kỳ thông báo dàn xếp vụ kiện ngày 11/09/2023.
- **AI được dùng để làm gì:** Tự động sàng lọc đơn ứng tuyển gia sư ở bước đầu.
- **Vấn đề hoặc sự kiện đáng chú ý:** Theo đơn kiện của EEOC, phần mềm đã được lập trình tự động từ chối phụ nữ từ **55 tuổi** trở lên và nam giới từ **60 tuổi** trở lên. EEOC cho biết iTutorGroup từ chối hơn 200 ứng viên đủ điều kiện tại Hoa Kỳ dựa trên tuổi; vụ việc được dàn xếp với khoản chi trả 365.000 USD và các biện pháp khắc phục khác.
- **Số liệu có nguồn:** **Hơn 200** ứng viên đủ điều kiện bị từ chối; ngưỡng tự động là nữ **≥55** và nam **≥60** tuổi; khoản dàn xếp **365.000 USD**. EEOC sẽ giám sát việc tuân thủ ít nhất **5 năm** nếu iTutorGroup hoạt động tuyển dụng gia sư ở Hoa Kỳ trở lại.
- **Nguồn:** [“iTutorGroup to Pay $365,000 to Settle EEOC Discriminatory Hiring Suit” — U.S. Equal Employment Opportunity Commission (EEOC), 11/09/2023](https://www.eeoc.gov/newsroom/itutorgroup-pay-365000-settle-eeoc-discriminatory-hiring-suit). Bài tổng quan sau đó của EEOC xác nhận lại các ngưỡng tuổi, “more than 200” người và khoản 365.000 USD: [EEOC, “Older Women at Work”](https://www.eeoc.gov/older-women-work-intersection-age-and-sex-discrimination).
- **Phân biệt bằng chứng và nhận định:** EEOC xác nhận nội dung cáo buộc, số người bị từ chối theo cáo buộc, thỏa thuận dàn xếp và biện pháp khắc phục. Tôi không khẳng định hệ thống này dùng ML/LLM, cũng không suy ra tỷ lệ lỗi trên toàn bộ đơn ứng tuyển. Đánh giá layer và mức độ harm dưới đây là phân tích của tôi dựa trên hành vi tự động loại được EEOC mô tả.

### Harm Map Worksheet

| Trường | Phân tích của tôi |
| --- | --- |
| High-risk moment | Ngay khi phần mềm đọc thông tin tuổi/ngày sinh và tự động quyết định từ chối đơn trước khi ứng viên được đánh giá năng lực gia sư. |
| Stakeholder bị ảnh hưởng | Hơn 200 ứng viên đủ điều kiện bị từ chối theo EEOC; người học mất cơ hội được học với gia sư giàu kinh nghiệm; iTutorGroup chịu rủi ro pháp lý, tài chính và uy tín. |
| Failure mode | **Bias / fairness** (phân biệt theo tuổi và ngưỡng tuổi khác nhau theo giới); đồng thời có dấu hiệu **escalation failure** nếu một quyết định loại tự động không được chuyển sang người xem xét. Phần “không có bước xem xét” là giả thuyết hợp lý, không phải sự kiện mà nguồn xác nhận. |
| Layer bắt đầu lỗi | **Safety / policy logic**: nguồn nói rõ phần mềm được “programmed” để tự động từ chối theo ngưỡng tuổi; điều này phù hợp với lỗi ở quy tắc bảo vệ/quy trình ra quyết định hơn là lỗi năng lực Model. Chưa đủ bằng chứng về UX, grounding hay kiến trúc mô hình. |
| Harm xảy ra là gì? | **Đã xảy ra theo cáo buộc được EEOC giải quyết:** hơn 200 ứng viên đủ điều kiện ở Hoa Kỳ bị tự động từ chối dựa trên tuổi — một mất mát cơ hội tiếp cận việc làm. Không suy ra thu nhập thực tế mỗi người đã mất vì nguồn không công bố. |
| Harm lens | Opportunity loss là chính; dignity loss do bị đối xử bất lợi bởi đặc điểm tuổi/giới thay vì năng lực. |
| Severity | **High (đánh giá cá nhân):** từ chối ngay đầu quy trình có thể chặn hoàn toàn cơ hội tiếp cận việc làm của người đủ điều kiện. |
| Scale | **Medium, có căn cứ số liệu:** hơn 200 người là tác động đã được EEOC nêu. Không chọn High vì nguồn không cho biết tổng số hồ sơ hoặc phạm vi toàn ngành. |
| Probability | **Cao đối với nhóm khớp ngưỡng tuổi:** logic được lập trình để tự động từ chối. Không có mẫu số nên không nêu tỷ lệ phần trăm. |
| Frequency | **Chưa đủ dữ liệu để đánh giá tần suất theo thời gian.** Việc EEOC nêu hơn 200 trường hợp cho thấy hành vi không chỉ là một lần đơn lẻ, nhưng nguồn không cho số đợt tuyển dụng hoặc thời gian vận hành. |
| Vì sao? | Nguồn EEOC là nguồn cơ quan thực thi, cung cấp ngưỡng tuổi, số “more than 200”, khoản dàn xếp và thời hạn giám sát. Severity/Scale/Probability là đánh giá của tôi; giới hạn là thông cáo không mô tả thuật toán chi tiết hay mẫu số tổng đơn. |

## 4. Tổng kết và đề xuất kiểm soát

Hai case cùng thuộc tuyển dụng, nhưng biểu hiện khác nhau: Amazon cho thấy dữ liệu lịch sử có thể làm hệ thống học thiên lệch; iTutorGroup cho thấy quy tắc tự động có thể mã hóa trực tiếp tiêu chí loại trừ. Vì vậy, với AI hỗ trợ tuyển dụng, tôi đề xuất:

1. Không dùng thuộc tính bảo vệ hoặc biến đại diện (proxy) để tự động loại ứng viên; kiểm tra chênh lệch kết quả giữa các nhóm trước khi triển khai và định kỳ sau triển khai.
2. Mọi trường hợp bị AI đề xuất loại phải có cơ chế human review độc lập, ghi lại lý do và cho ứng viên đường phản hồi/xem xét lại.
3. Giảm dữ liệu xuống mức cần thiết, thông báo rõ dữ liệu nào được xử lý và thời gian lưu giữ; đặc biệt thận trọng với video, giọng nói và dữ liệu suy ra.
4. Công bố giới hạn của công cụ, lưu log/audit trail và dừng triển khai khi phát hiện chênh lệch chưa giải thích được.

## 5. Checklist trước khi nộp

- [x] Chọn đúng một ngành: HR / tuyển dụng.
- [x] Có Industry Risk Snapshot đủ bốn nội dung.
- [x] Có 2 case khác nhau cùng ngành; mỗi case có mô tả, số liệu và nguồn mở được.
- [x] Mỗi case có Harm Map đủ 11 trường.
- [x] Phân biệt sự kiện có nguồn với nhận định/nguy cơ của cá nhân.
- [ ] Commit thay đổi, kiểm tra repo ở chế độ ẩn danh, rồi nộp URL repo trên AI Codelabs.
