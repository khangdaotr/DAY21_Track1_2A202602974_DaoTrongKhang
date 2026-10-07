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

&#32;3\. Case study 2 — McDonald’s McHire: Lỗ hổng làm dữ liệu ứng viên có thể bị truy cập trái phép

#### Brief Case

- Tổ chức / sản phẩm AI: McDonald’s McHire và chatbot tuyển dụng Olivia do Paradox.ai phát triển.
- Thời gian, địa điểm / bối cảnh: Hoa Kỳ, tháng 6–7/2025; McHire được các nhà hàng nhượng quyền McDonald’s sử dụng để tiếp nhận và xử lý hồ sơ ứng tuyển.
- AI được dùng để làm gì: Chatbot Olivia thu thập thông tin ứng viên, thực hiện bước sàng lọc ban đầu, hỏi về thời gian làm việc, chuyển ứng viên tới bài đánh giá và hỗ trợ đặt lịch phỏng vấn.
- Vấn đề hoặc sự kiện đáng chú ý: Hai nhà nghiên cứu bảo mật Ian Carroll và Sam Curry truy cập được một tài khoản quản trị thử nghiệm bằng tên đăng nhập và mật khẩu `123456`. Sau đó, họ phát hiện lỗi kiểm soát truy cập trong API cho phép thay đổi ID để xem hồ sơ ứng viên khác.
- Số liệu có nguồn: Dãy ID cho thấy lỗi có khả năng cho phép truy cập tối đa khoảng **64 triệu bản ghi ứng tuyển**. Con số này là phạm vi có khả năng truy cập, không phải 64 triệu người đã chắc chắn bị đánh cắp dữ liệu. Theo phản hồi của Paradox được các nguồn dẫn lại, các nhà nghiên cứu chỉ xem một số ít hồ sơ để xác minh lỗi và không có bằng chứng tài khoản thử nghiệm đã bị bên thứ ba khác sử dụng.
- Nguồn:
  - “Poor Passwords Tattle on AI Hiring Bot Maker Paradox.ai” — Brian Krebs, KrebsOnSecurity — tháng 7/2025 — [URL (https://krebsonsecurity.com/2025/07/poor-passwords-tattle-on-ai-hiring-bot-maker-paradox-ai/)](<https://krebsonsecurity.com/2025/07/poor-passwords-tattle-on-ai-hiring-bot-maker-paradox-ai/>) — phần mô tả mật khẩu yếu và dữ liệu ứng viên có thể bị truy cập.
  - “Fast Food, Weak Passwords: McDonald’s AI Hiring Tool Exposed Millions of Applicants’ Data” — Chris Bernard, TechRepublic — 10/07/2025 — [URL (https://www.techrepublic.com/article/news-mcdonalds-applicants-ai-hiring-tool-security-vulnerability/)](<https://www.techrepublic.com/article/news-mcdonalds-applicants-ai-hiring-tool-security-vulnerability/>) — phần mô tả chatbot Olivia, tài khoản quản trị và phạm vi bản ghi.
  - “McDonald’s security blunder exposes job applicants’ data” — Leonard Bernardone, Australian Computer Society — 14/07/2025 — [URL (https://ia.acs.org.au/article/2025/mcdonald-s-security-blunder-exposes-job-applicants--data.html)](<https://ia.acs.org.au/article/2025/mcdonald-s-security-blunder-exposes-job-applicants--data.html>) — phần mô tả dữ liệu, lỗi bảo mật và con số 64 triệu.
- Phân biệt bằng chứng và nhận định: Nguồn xác nhận các nhà nghiên cứu truy cập được hệ thống bằng thông tin đăng nhập yếu và có thể chuyển giữa các bản ghi ứng viên. Khoảng 64 triệu là ước tính về số bản ghi có khả năng truy cập, không phải số hồ sơ đã bị tải xuống hoặc số nạn nhân đã chịu lạm dụng dữ liệu. Chưa có bằng chứng công khai cho thấy kẻ xấu đã khai thác lỗi trước khi nó được khắc phục.


#### Harm Map Worksheet

| Trường | Phân tích của tôi |
|---|---|
| High-risk moment | Khi thông tin do ứng viên cung cấp cho chatbot được lưu trong McHire và có thể được truy xuất qua tài khoản quản trị cùng API thiếu kiểm tra quyền trên từng hồ sơ. |
| Stakeholder bị ảnh hưởng | Ứng viên bị mất quyền kiểm soát dữ liệu khi người không có thẩm quyền xem thông tin liên hệ và nội dung ứng tuyển. McDonald’s và các nhà hàng nhượng quyền có thể mất uy tín. Paradox.ai phải chịu trách nhiệm về bảo mật nền tảng do mình cung cấp. |
| Failure mode | **Privacy leak** — hệ thống cho phép truy cập dữ liệu không nên được công khai cho tài khoản hoặc người dùng không có thẩm quyền. |
| Layer bắt đầu lỗi | **Safety** — tài khoản thử nghiệm dùng thông tin đăng nhập rất yếu và API không kiểm tra đầy đủ quyền truy cập đối với từng bản ghi. Đây là lỗi bảo vệ hệ thống, không phải lỗi suy luận của mô hình AI. |
| Harm xảy ra là gì? | Một số hồ sơ đã được các nhà nghiên cứu xem để xác nhận lỗ hổng. Tên, email, số điện thoại và nội dung trao đổi của ứng viên có nguy cơ bị truy cập trái phép. Chưa có bằng chứng công khai về việc toàn bộ dữ liệu bị tải xuống hoặc bị kẻ xấu khai thác. |
| Harm lens | **Privacy loss**; có thể dẫn đến **dignity loss** nếu nội dung ứng tuyển hoặc bài đánh giá cá nhân bị công khai hoặc sử dụng sai mục đích. |
| Severity | **High** — dữ liệu tuyển dụng có thể được dùng cho phishing, giả mạo hoặc gây tổn hại danh tiếng. Không chọn Critical vì chưa có bằng chứng về tổn hại thể chất nghiêm trọng hoặc việc toàn bộ dữ liệu đã bị khai thác. |
| Scale | **High về phạm vi có khả năng bị ảnh hưởng** — lỗi có thể cho phép truy cập khoảng 64 triệu bản ghi ứng tuyển. Đây là số bản ghi tiềm năng, không phải 64 triệu người đã được xác nhận là nạn nhân. |
| Probability | **High đối với khả năng khai thác kỹ thuật** vì tài khoản sử dụng thông tin đăng nhập dễ đoán và các nhà nghiên cứu đã chứng minh có thể truy cập hồ sơ khác. **Chưa đủ dữ liệu** để đánh giá xác suất kẻ xấu đã khai thác lỗi. |
| Frequency | **Chưa đủ dữ liệu để đánh giá.** Lỗi cho phép lặp lại việc thay đổi ID để truy cập nhiều hồ sơ, nhưng không có dữ liệu công khai về số lần truy cập trái phép trước khi được khắc phục. |
| Vì sao? | Các nhà nghiên cứu đã chứng minh chuỗi lỗi gồm tài khoản quản trị bảo vệ yếu và thiếu kiểm tra quyền trên từng bản ghi. Tuy nhiên, cần phân biệt phạm vi hệ thống có thể bị truy cập với thiệt hại thực tế đã xác nhận. Với **Hệ thống đang xét**, CV, câu trả lời phỏng vấn và thông tin liên hệ phải được bảo vệ bằng xác thực thật, phân quyền theo từng người dùng và kiểm tra quyền ở mọi API. |

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

