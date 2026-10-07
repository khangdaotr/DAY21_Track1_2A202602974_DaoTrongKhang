## Lab 21 — Phân tích rủi ro AI qua case study thực tế

- Họ và tên: Đào Trọng Khang
- MSSV / mã học viên: 2A202602974
- Lớp: H201
- Ngành đã chọn: HR / tuyển dụng

### 1. Industry Risk Snapshot

| Nội dung | Đánh giá | Lý do ngắn |
|---|---|---|
| Harm chính | Sinh viên có thể bị định hướng sai hoặc giảm cơ hội nghề nghiệp | AI có thể phân tích CV–JD sai, bịa nội dung, chấm phỏng vấn thiếu chính xác hoặc đưa ra lời khuyên không phù hợp. Sinh viên có thể sửa CV sai hướng, hiểu sai năng lực và bỏ lỡ vị trí phù hợp. |
| Mức độ high-stakes | Trung bình–cao | Hệ thống không trực tiếp quyết định tuyển dụng nhưng tác động đến CV, quá trình chuẩn bị phỏng vấn và cơ hội việc làm của sinh viên. Tác động tăng lên nếu cố vấn hoặc nhà tuyển dụng sử dụng điểm AI để xếp hạng hay loại ứng viên. |
| Dữ liệu nhạy cảm | Cao| CV và lịch sử phỏng vấn có thể chứa họ tên, email, số điện thoại, địa chỉ, học vấn, kinh nghiệm, kỹ năng và thông tin cá nhân khác. Ghi chú riêng của cố vấn và tin nhắn với sinh viên cũng có thể chứa đánh giá nhạy cảm. |
| Nhu cầu human review | Cao – bắt buộc tại các bước quan trọng | Sinh viên phải kiểm tra và Accept/Edit/Reject trước khi áp dụng nội dung vào CV. Cố vấn nên xem lại các kết quả bất thường, điểm thấp, đề xuất thiếu bằng chứng hoặc trường hợp có thể ảnh hưởng lớn đến định hướng nghề nghiệp. AI chỉ hỗ trợ, không được tự quyết định thay con người. |
**Kết luận ngắn:** Hệ thống đang xét là hệ thống hỗ trợ quyết định có tác động đáng kể đến cơ hội nghề nghiệp. Vì vậy, hệ thống cần bảo vệ dữ liệu cá nhân, giải thích kết quả bằng bằng chứng và duy trì quyền quyết định cuối cùng của sinh viên hoặc cố vấn.


### 2. Case study 1 — Amazon: Công cụ sàng lọc CV thiên lệch đối với phụ nữ

#### Brief Case

- Tổ chức / sản phẩm AI: Amazon — công cụ AI thử nghiệm dùng để xếp hạng CV ứng viên.
- Thời gian, địa điểm / bối cảnh: Phát triển từ năm 2014 tại Amazon; vụ việc được Reuters công bố vào tháng 10/2018 trong bối cảnh tuyển dụng nhân sự kỹ thuật.
- AI được dùng để làm gì: Đọc và chấm điểm CV để hỗ trợ nhà tuyển dụng xác định ứng viên tiềm năng.
- Vấn đề hoặc sự kiện đáng chú ý: Công cụ được huấn luyện bằng hồ sơ ứng tuyển trong quá khứ, phần lớn đến từ nam giới. Hệ thống đã hạ điểm một số CV chứa từ ngữ liên quan đến phụ nữ. Amazon không thể bảo đảm đã loại bỏ hết các dạng thiên lệch và đã dừng dự án.
- Số liệu có nguồn: Hệ thống sử dụng dữ liệu hồ sơ ứng tuyển trong khoảng 10 năm. Reuters không công bố số ứng viên thực tế bị loại bởi công cụ.
- Nguồn: “Amazon scraps secret AI recruiting tool that showed bias against women” — Jeffrey Dastin, Reuters — 10/10/2018 — [URL (https://www.investing.com/news/stock-market-news/amazon-scraps-secret-ai-recruiting-tool-that-showed-bias-against-women-1637988)](<https://www.investing.com/news/stock-market-news/amazon-scraps-secret-ai-recruiting-tool-that-showed-bias-against-women-1637988>) — phần mô tả dữ liệu huấn luyện, biểu hiện thiên lệch và quyết định dừng dự án.
- Phân biệt bằng chứng và nhận định: Nguồn xác nhận công cụ thể hiện thiên lệch giới tính và Amazon đã dừng dự án. Nguồn không xác nhận có bao nhiêu ứng viên bị từ chối trực tiếp vì công cụ. Việc ứng viên nữ có thể mất cơ hội phỏng vấn là nhận định về nguy cơ, không phải thiệt hại đã được định lượng.

#### Harm Map Worksheet


#### Harm Map Worksheet

| Trường | Phân tích của tôi |
|---|---|
| High-risk moment | Khi công cụ AI chấm CV từ 1–5 sao và nhà tuyển dụng dùng kết quả đó để xác định hồ sơ nào đáng được xem xét tiếp. |
| Stakeholder bị ảnh hưởng | Ứng viên nữ bị giảm cơ hội được xem xét khi CV chứa các dấu hiệu mà mô hình liên hệ với giới tính. Nhà tuyển dụng có thể bỏ sót ứng viên phù hợp khi tin vào bảng xếp hạng thiên lệch. |
| Failure mode | **Bias / fairness** — kết quả chấm CV tạo bất lợi không công bằng cho ứng viên nữ. |
| Layer bắt đầu lỗi | **Model** — Reuters xác nhận các mô hình được huấn luyện từ khoảng 10 năm hồ sơ, phần lớn do nam giới nộp, và đã học các mẫu ưu tiên nam giới. |
| Harm xảy ra là gì? | Ứng viên nữ có nguy cơ bị xếp hạng thấp, ít được xem CV hoặc mất cơ hội phỏng vấn. Công cụ đã tạo điểm thiên lệch, nhưng nguồn không xác nhận số ứng viên thực tế bị loại vì điểm này. |
| Harm lens | **Opportunity loss**; có thể kèm **dignity loss** vì ứng viên không được đánh giá công bằng dựa trên năng lực. |
| Severity | **High** — nếu điểm AI ảnh hưởng việc CV có được xem tiếp, ứng viên có thể mất cơ hội nghề nghiệp và thu nhập. |
| Scale | **Chưa đủ dữ liệu để đánh giá.** Công cụ được thiết kế cho hoạt động tuyển dụng quy mô lớn, nhưng Reuters không công bố số CV hoặc ứng viên bị ảnh hưởng trực tiếp. |
| Probability | **High đối với khả năng tạo điểm thiên lệch** vì hành vi này đã được phát hiện trong hệ thống. Chưa đủ dữ liệu để đánh giá xác suất một ứng viên bị từ chối việc làm vì điểm AI. |
| Frequency | **Chưa đủ dữ liệu để đánh giá.** Lỗi có khả năng lặp lại khi gặp các CV có tín hiệu tương tự, nhưng nguồn không công bố số lần xảy ra. |
| Vì sao? | Reuters xác nhận mô hình hạ điểm một số dấu hiệu liên quan đến phụ nữ và Amazon không thể bảo đảm đã loại bỏ hết các biến đại diện khác. Tuy nhiên, nhà tuyển dụng không chỉ dựa vào công cụ này, nên không thể kết luận mọi điểm thiên lệch đều dẫn tới quyết định từ chối. |

***

### 3. Case study 2 — iTutorGroup: Phần mềm tự động loại ứng viên lớn tuổi

#### Brief Case

- Tổ chức / sản phẩm AI: iTutorGroup và phần mềm tuyển dụng trực tuyến của doanh nghiệp.
- Thời gian, địa điểm / bối cảnh: Hoạt động tuyển giáo viên tiếng Anh làm việc từ xa tại Hoa Kỳ trong năm 2020; EEOC công bố thỏa thuận giải quyết ngày 11/09/2023.
- AI được dùng để làm gì: Tiếp nhận và tự động sàng lọc hồ sơ ứng tuyển giáo viên trực tuyến.
- Vấn đề hoặc sự kiện đáng chú ý: Theo vụ kiện của EEOC, phần mềm được lập trình để tự động từ chối ứng viên nữ từ 55 tuổi trở lên và ứng viên nam từ 60 tuổi trở lên.
- Số liệu có nguồn: Hơn 200 ứng viên đủ điều kiện tại Hoa Kỳ bị từ chối vì tuổi. Thỏa thuận yêu cầu chi trả tổng cộng 365.000 USD. EEOC sẽ giám sát việc tuân thủ trong ít nhất 5 năm hoặc lâu hơn nếu doanh nghiệp tuyển dụng trở lại tại Hoa Kỳ.
- Nguồn: “iTutorGroup to Pay $365,000 to Settle EEOC Discriminatory Hiring Suit” — U.S. Equal Employment Opportunity Commission — 11/09/2023 — [URL (https://www.eeoc.gov/newsroom/itutorgroup-pay-365000-settle-eeoc-discriminatory-hiring-suit)](<https://www.eeoc.gov/newsroom/itutorgroup-pay-365000-settle-eeoc-discriminatory-hiring-suit>) — phần mô tả quy tắc loại theo tuổi, số ứng viên và nội dung thỏa thuận.
- Phân biệt bằng chứng và nhận định: EEOC xác nhận nội dung cáo buộc, số người bị ảnh hưởng và thỏa thuận giải quyết. Vì vụ việc được giải quyết bằng thỏa thuận, không nên trình bày rằng tòa án đã xét xử và kết luận toàn bộ cáo buộc là sự thật.

#### Harm Map Worksheet

#### Harm Map Worksheet

| Trường | Phân tích của tôi |
|---|---|
| High-risk moment | Khi phần mềm kiểm tra tuổi và giới tính rồi tự động từ chối hồ sơ trước khi ứng viên được con người xem xét. |
| Stakeholder bị ảnh hưởng | Hơn 200 ứng viên lớn tuổi bị mất cơ hội được xem xét tuyển dụng khi phần mềm áp dụng ngưỡng tuổi. iTutorGroup chịu chi phí dàn xếp và trách nhiệm tuân thủ. Học viên có thể mất cơ hội học với những giáo viên đủ năng lực. |
| Failure mode | **Bias / fairness** — hệ thống tạo kết quả bất lợi trực tiếp dựa trên tuổi và giới tính. |
| Layer bắt đầu lỗi | **Safety** — hệ thống không ngăn chặn mà còn thực thi một quy tắc sàng lọc phân biệt đối xử. Nguồn không công bố kiến trúc kỹ thuật, vì vậy đây là phân loại theo chức năng bảo vệ bị thiếu, không phải khẳng định về cấu trúc phần mềm. |
| Harm xảy ra là gì? | Theo EEOC, hơn 200 ứng viên đủ điều kiện tại Hoa Kỳ đã bị từ chối vì tuổi. Đây là hậu quả đã xảy ra theo cáo buộc được giải quyết bằng thỏa thuận, không chỉ là nguy cơ giả định. |
| Harm lens | **Opportunity loss** và **dignity loss**. |
| Severity | **High** — ứng viên bị mất cơ hội việc làm và thu nhập do đặc điểm không phản ánh năng lực. Không chọn Critical vì nguồn không ghi nhận tổn hại thể chất nghiêm trọng hoặc hậu quả không thể phục hồi. |
| Scale | **Hơn 200 ứng viên đủ điều kiện tại Hoa Kỳ**, theo EEOC. |
| Probability | **High đối với ứng viên thuộc điều kiện loại** vì quy tắc được áp dụng tự động khi hồ sơ đáp ứng ngưỡng tuổi và giới tính. Nguồn không cung cấp tỷ lệ trên tổng số hồ sơ. |
| Frequency | **High trong phạm vi nhóm bị áp dụng quy tắc** vì cùng một điều kiện tự động có thể lặp lại với mỗi hồ sơ phù hợp. Tổng số lần phần mềm chạy không được công bố. |
| Vì sao? | EEOC nêu rõ ngưỡng tuổi, cơ chế từ chối tự động, hơn 200 người bị ảnh hưởng và khoản dàn xếp 365.000 USD. Tuy nhiên, nguồn chỉ gọi đây là phần mềm ứng tuyển trực tuyến, không đủ bằng chứng để khẳng định hệ thống sử dụng machine learning hay mô hình AI. |

***

### 4. Case study 3 — HireVue: Loại bỏ phân tích hình ảnh khỏi đánh giá phỏng vấn

#### Brief Case

- Tổ chức / sản phẩm AI: HireVue — nền tảng phỏng vấn và đánh giá ứng viên bằng AI.
- Thời gian, địa điểm / bối cảnh: Hoa Kỳ và thị trường tuyển dụng trực tuyến; HireVue công bố quyết định loại bỏ phân tích hình ảnh khỏi các mô hình đánh giá mới vào ngày 12/01/2021.
- AI được dùng để làm gì: Phân tích phỏng vấn để đánh giá năng lực và mức độ phù hợp của ứng viên với công việc. Các phiên bản trước từng sử dụng đặc trưng hình ảnh.
- Vấn đề hoặc sự kiện đáng chú ý: HireVue loại bỏ phân tích hình ảnh sau khi nghiên cứu nội bộ cho thấy thành phần này không tạo thêm giá trị đáng kể so với phân tích ngôn ngữ. Tính năng cũng bị đặt câu hỏi về tính minh bạch, căn cứ khoa học và khả năng ảnh hưởng không công bằng đến ứng viên.
- Số liệu có nguồn: Nguồn của HireVue không công bố số ứng viên bị chấm sai, tỷ lệ sai lệch giữa các nhóm hoặc số quyết định tuyển dụng bị ảnh hưởng. Vì vậy, chưa có cơ sở để bổ sung con số thiệt hại cụ thể.
- Nguồn: “Industry Leadership: New Audit Results, Decision on Visual Analysis” — Lindsey Zuloaga, HireVue — 12/01/2021 — [URL (https://www.hirevue.com/blog/hiring/industry-leadership-new-audit-results-and-decision-on-visual-analysis)](<https://www.hirevue.com/blog/hiring/industry-leadership-new-audit-results-and-decision-on-visual-analysis>) — phần quyết định loại bỏ visual analysis; “Our Science” — HireVue — [URL (https://www.hirevue.com/platform/our-science)](<https://www.hirevue.com/platform/our-science>) — phần mô tả dữ liệu được hệ thống hiện tại sử dụng.
- Phân biệt bằng chứng và nhận định: Nguồn của công ty xác nhận việc loại bỏ phân tích hình ảnh và lý do dựa trên nghiên cứu nội bộ. Nguồn không chứng minh tính năng đã gây phân biệt đối xử cho một số lượng ứng viên cụ thể. Rủi ro đối với người khuyết tật hoặc người có cách biểu đạt khác biệt là nhận định cần thêm nghiên cứu độc lập để kiểm chứng.

#### Harm Map Worksheet

| Trường | Phân tích của tôi |
|---|---|
| High-risk moment | Khi hệ thống sử dụng tín hiệu hình ảnh hoặc phi ngôn ngữ trong video để tạo điểm đánh giá và điểm đó được dùng để quyết định ứng viên có đi tiếp hay không. |
| Stakeholder bị ảnh hưởng | Ứng viên có biểu cảm, đặc điểm khuyết tật hoặc cách giao tiếp khác biệt có nguy cơ bị chấm không công bằng khi tín hiệu hình ảnh được dùng làm đại diện cho năng lực. Nhà tuyển dụng có thể loại nhầm ứng viên phù hợp. |
| Failure mode | **Bias / fairness** — tín hiệu hình ảnh có thể tạo kết quả bất lợi không công bằng giữa các nhóm ứng viên. Không chọn `Privacy leak` vì nguồn không chứng minh dữ liệu đã bị rò rỉ. |
| Layer bắt đầu lỗi | **Model** — theo HireVue, phân tích hình ảnh có tương quan với hiệu quả công việc thấp hơn các yếu tố khác và không bổ sung đáng kể khả năng dự đoán. Nguồn chưa đủ để xác định chi tiết kiến trúc hoặc cách từng đặc trưng được tính điểm. |
| Harm xảy ra là gì? | Ứng viên có nguy cơ bị chấm thấp hoặc mất cơ hội đi tiếp vì tín hiệu hình ảnh không phản ánh chính xác năng lực. Việc từng sử dụng visual analysis được xác nhận, nhưng chưa có bằng chứng trong nguồn này về số ứng viên thực tế bị loại sai. |
| Harm lens | **Opportunity loss**, **dignity loss** và nguy cơ **privacy loss** do video khuôn mặt được xử lý. Nguồn chưa ghi nhận một vụ rò rỉ dữ liệu cụ thể. |
| Severity | **High** nếu điểm ảnh hưởng trực tiếp đến quyết định tuyển dụng; hậu quả có thể là mất cơ hội nghề nghiệp. |
| Scale | **Chưa đủ dữ liệu để đánh giá.** HireVue là nền tảng tuyển dụng được nhiều tổ chức sử dụng, nhưng các nguồn đang dùng không công bố số ứng viên được chấm bằng visual analysis hoặc số người chịu tác động bất lợi. |
| Probability | **Chưa đủ dữ liệu để đánh giá.** Việc tín hiệu hình ảnh không bổ sung đáng kể khả năng dự đoán cho thấy cơ sở sử dụng nó yếu, nhưng không cung cấp tỷ lệ chấm sai. |
| Frequency | **Chưa đủ dữ liệu để đánh giá.** Nguy cơ có thể lặp lại theo mỗi lần visual analysis được sử dụng, nhưng nguồn không công bố tần suất lỗi. |
| Vì sao? | HireVue xác nhận từng sử dụng visual analysis và sau đó loại bỏ nó khỏi các thuật toán tuyển dụng. Tuy nhiên, nguồn chính là công bố của doanh nghiệp và không cung cấp số liệu về thiệt hại. Vì vậy, các hậu quả được ghi là nguy cơ, không trình bày như sự cố phân biệt đối xử đã được chứng minh. |

