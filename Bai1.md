# BÀI LÀM THỰC HÀNH: HỆ THỐNG GIAO ĐỒ ĂN QUICKBITE
**Khóa học:** Phân tích & Thiết kế Hệ thống (IT105)  
**Session:** 03 - Phân tích Yêu cầu Phần mềm & Kỹ thuật Thu thập  
**Vai trò thực hiện:** System Analyst (SA)

---

## NHIỆM VỤ 1: PHÂN TÍCH MÔI TRƯỜNG HỆ THỐNG VÀ XÁC ĐỊNH STAKEHOLDERS

### 1. Phân tích 3 Nhóm Môi trường Hoạt động

| Nhóm Môi trường | Mô tả Đặc điểm & Tác động đến Hệ thống QuickBite |
| :--- | :--- |
| **1. Môi trường Kinh doanh tại nhà hàng** | - Chuỗi Cơm Tấm Sài Gòn có **15 chi nhánh** tại TP.HCM với quy trình phục vụ truyền thống, giờ cao điểm (trưa 11h-13h, tối 18h-20h) lượng đơn dồn dập.<br>- Đồ ăn cần chuẩn bị nhanh, giữ nhiệt độ tốt khi giao.<br>- Môi trường nhà bếp nhiều khói bụi, nhiệt độ cao, dầu mỡ, tiếng ồn lớn ảnh hưởng đến việc tiếp nhận tín hiệu thông báo đơn từ thiết bị POS. |
| **2. Môi trường Kỹ thuật Hạ tầng / Di động** | - **Kết nối mạng:** 3G/4G/5G hoặc Wi-Fi không ổn định khi tài xế di chuyển ngoài đường hoặc trong hẻm sâu, khu vực sóng yếu.<br>- **Thiết bị:** Khách hàng và Tài xế sử dụng đa dạng thiết bị di động (iOS/Android) từ giá rẻ đến cao cấp; màn hình POS đặt cố định tại nhà hàng.<br>- **Dịch vụ tích hợp:** GPS/Bản đồ chỉ đường (Google Maps/Mapbox), Cổng thanh toán trực tuyến (Momo, VNPay, ZaloPay, Thẻ ATM/Visa/Mastercard), Dịch vụ Push Notification. |
| **3. Môi trường Con người** | - **Khách hàng:** Đa dạng độ tuổi (dân văn phòng, học sinh/sinh viên, hộ gia đình), mong muốn thao tác đặt món nhanh, minh bạch giá cả và thời gian giao.<br>- **Chủ nhà hàng / Quản lý:** Lớn tuổi hoặc thói quen quản lý truyền thống, cần giao diện POS cực kỳ đơn giản, trực quan, dễ thao tác.<br>- **Tài xế giao hàng:** Thường xuyên di chuyển trên đường, thao tác bằng một tay hoặc thao tác nhanh trên giá đỡ điện thoại, cần chữ to, nút bấm rõ ràng.<br>- **Quản trị viên (Admin):** Thành thạo công nghệ, cần hệ thống báo cáo tổng quan, chính xác để vận hành toàn bộ chuỗi. |

---

### 2. Danh sách Stakeholders, Nguồn Thu thập & Nhu cầu Cốt lõi

| STT | Bên liên quan (Stakeholder) | Nguồn Thu thập Yêu cầu Phù hợp | Nhu cầu Cốt lõi (Core Needs) |
| :---: | :--- | :--- | :--- |
| **1** | **Khách hàng (Customer)** | **Nguồn con người:** Khảo sát người dùng, phỏng vấn nhóm khách hàng.<br>**Nguồn thị trường/đối thủ:** Phân tích ứng dụng đối thủ (GrabFood, ShopeeFood, Baemin). | - Tìm kiếm món ăn nhanh chóng, chính xác.<br>- Đặt món và thanh toán trực tuyến tiện lợi, an toàn.<br>- Theo dõi trạng thái đơn hàng và vị trí tài xế theo thời gian thực (Real-time tracking). |
| **2** | **Chủ nhà hàng / Quản lý (Restaurant Owner)** | **Nguồn con người:** Phỏng vấn sâu Bác chủ quán và quản lý chi nhánh.<br>**Nguồn tài liệu:** Hóa đơn cũ, sổ sách kế toán, quy trình vận hành nhà hàng hiện tại.<br>**Nguồn hệ thống hiện tại:** Phần mềm quản lý bán hàng cũ (nếu có). | - Tiếp nhận và xác nhận đơn hàng từ QuickBite tức thì trên POS.<br>- Quản lý danh mục món ăn (bật/tắt món tạm hết, chỉnh giá).<br>- Xem báo cáo doanh thu, số lượng đơn hàng chi tiết theo chi nhánh và theo ca. |
| **3** | **Tài xế giao hàng (Driver)** | **Nguồn con người:** Khảo sát diện rộng nhóm tài xế.<br>**Nguồn thị trường/đối thủ:** Tham khảo tính năng app tài xế của Grab, Gojek, ShopeeFood. | - Nhận thông báo đơn hàng mới gần vị trí hiện tại.<br>- Bản đồ chỉ đường chính xác, tối ưu lộ trình giao hàng.<br>- Đối soát thu nhập, tiền phí giao hàng và tiền thưởng minh bạch theo ngày/tuần. |
| **4** | **Quản trị viên (Admin System)** | **Nguồn con người:** Phỏng vấn đội ngũ vận hành nội bộ QuickBite.<br>**Nguồn tài liệu:** Quy trình vận hành chuỗi cung ứng, chính sách chiết khấu, quy định pháp lý. | - Giám sát toàn bộ luồng vận hành (Khách hàng - Nhà hàng - Tài xế).<br>- Xử lý tranh chấp, khiếu nại (bùng đơn, giao sai món, trễ đơn).<br>- Phân quyền người dùng và quản lý cấu hình hệ thống. |

---

## NHIỆM VỤ 2: LỰA CHỌN KỸ THUẬT THU THẬP YÊU CẦU PHÙ HỢP

### 1. Bảng Lựa chọn Kỹ thuật cho các Tình huống

| Tình huống Thu thập | Kỹ thuật Lựa chọn | Giải thích Lý do Phù hợp |
| :--- | :--- | :--- |
| **1. Tìm hiểu cấu trúc danh mục món ăn và giá tiền từ hóa đơn giấy cũ của quán.** | **Phân tích tài liệu (Document Analysis)** | - Hóa đơn giấy là tài liệu lưu trữ sẵn có, phản ánh chính xác cấu trúc dữ liệu thực tế (tên món, nhóm món, giá tiền, topping, thuế/phiếu thu).<br>- Tiết kiệm thời gian, tránh phiền hà cho chủ quán khi hỏi lại những thông tin đã được ghi chép cố định. |
| **2. Tìm hiểu quy trình phối hợp thực tế giữa đầu bếp và nhân viên soạn đồ ăn tại bếp.** | **Quan sát thực tế (Observation)** | - Quy trình tại nhà bếp diễn ra theo phản xạ tự nhiên, nhịp độ nhanh và có nhiều thao tác không niêm yết trong tài liệu.<br>- Việc quan sát trực tiếp giúp phát hiện điểm nghẽn (bottlenecks), sự chồng chéo hoặc thói quen phối hợp thực tế mà nhân viên khó mô tả đầy đủ bằng lời. |
| **3. Khai thác các trăn trở về quản lý doanh thu và kỳ vọng của Bác chủ nhà hàng.** | **Phỏng vấn chuyên sâu (In-depth Interview)** | - Bác chủ nhà hàng là Stakeholder quan trọng (Key Stakeholder) có góc nhìn chiến lược, trăn trở kinh doanh sâu sắc và quyết định sự thành bại của dự án.<br>- Phỏng vấn 1-1 tạo không gian cởi mở, tin cậy để lắng nghe các góc khuất, mong muốn thầm kín và kỳ vọng cụ thể về quản lý tài chính. |
| **4. Thu thập ý kiến đánh giá cước phí giao hàng của 1.000 tài xế rải rác toàn thành phố.** | **Khảo sát diện rộng (Survey / Questionnaire)** | - Số lượng đối tượng quá lớn (1.000 người) và vị trí địa lý phân tán khắp thành phố.<br>- Khảo sát trực tuyến/qua app giúp thu thập số lượng lớn dữ liệu định lượng nhanh chóng, chi phí thấp và dễ dàng tổng hợp, phân tích thống kê. |

---

### 2. Giải thích lý do KHÔNG chọn "Phỏng vấn chuyên sâu" cho 1.000 Tài xế

Không nên chọn kỹ thuật **Phỏng vấn chuyên sâu** cho tình huống thu thập ý kiến của 1.000 tài xế vì các lý do sau:

1. **Chi phí thời gian và nhân lực quá lớn:** Nếu phỏng vấn 1.000 tài xế, giả sử mỗi cuộc phỏng vấn kéo dài 20-30 phút, tổng thời gian sẽ là 333 - 500 giờ làm việc. Điều này gây lãng phí nguồn lực ngân sách và kéo dài tiến độ dự án không cần thiết.
2. **Khó khăn về mặt logistics:** Tài xế giao hàng di chuyển liên tục ngoài đường, làm việc theo ca tự do. Việc đặt lịch hẹn phỏng vấn 1-1 với 1.000 người là cực kỳ khó khả thi.
3. **Mục tiêu thu thập là dữ liệu định lượng:** Yêu cầu thu thập ở đây là "đánh giá cước phí giao hàng" (mức phí cao/thấp/hợp lý, mức chiết khấu mong muốn). Đây là dạng câu hỏi khảo sát định lượng, hoàn toàn có thể thu thập qua bảng hỏi trắc nghiệm thay vì cần khai thác tâm lý/chiến lược sâu như phỏng vấn 1-1.

---

## NHIỆM VỤ 3: PHÂN LOẠI VÀ CHUẨN HÓA YÊU CẦU FR VÀ NFR

### 1. Phân loại 6 Phát biểu Yêu cầu

| STT | Phát biểu Yêu cầu | Phân loại | Giải thích ngắn |
| :---: | :--- | :---: | :--- |
| **1** | "Khách hàng có thể gõ từ khóa để tìm kiếm món ăn trên ứng dụng." | **FR** *(Functional Requirement)* | Tính năng tìm kiếm món ăn direct cho người dùng. |
| **2** | "Thời gian hiển thị kết quả tìm kiếm phải dưới 1.5 giây." | **NFR** *(Non-Functional Requirement)* | Tiêu chuẩn về hiệu năng (Performance). |
| **3** | "Chủ nhà hàng có thể bấm xác nhận tiếp nhận đơn hàng trên màn hình POS." | **FR** *(Functional Requirement)* | Hành động xử lý nghiệp vụ của Chủ nhà hàng. |
| **4** | "Ứng dụng phải chịu tải 10.000 người dùng truy cập cùng lúc." | **NFR** *(Non-Functional Requirement)* | Tiêu chuẩn về khả năng mở rộng/chịu tải (Scalability). |
| **5** | "Giao dịch thanh toán thẻ phải được mã hóa truyền tải an toàn." | **NFR** *(Non-Functional Requirement)* | Tiêu chuẩn về bảo mật dữ liệu (Security). |
| **6** | "Tài xế có thể bật/tắt chế độ sẵn sàng nhận đơn hàng mới." | **FR** *(Functional Requirement)* | Tính năng thay đổi trạng thái hoạt động của tài xế. |

---

### 2. Bổ sung Chỉ số Đo lường Định lượng (KPI/SLA) cho các NFR

| Yêu cầu NFR ban đầu | Phát biểu Chuẩn hóa bổ sung KPI/SLA cụ thể | Chỉ số đo lường (KPI/SLA) |
| :--- | :--- | :--- |
| **"Thời gian hiển thị kết quả tìm kiếm phải dưới 1.5 giây."** | Hệ thống phải phản hồi và hiển thị danh sách kết quả tìm kiếm món ăn cho Khách hàng trong thời gian **<= 1.5 giây** ở điều kiện mạng 4G tiêu chuẩn (băng thông tối thiểu 10 Mbps). | **Response Time:** <= 1.5s (Percentile 95th). |
| **"Ứng dụng phải chịu tải 10.000 người dùng truy cập cùng lúc."** | Hệ thống Backend phải duy trì khả năng phục vụ **10.000 người dùng truy cập đồng thời (Concurrent Users)** với tỷ lệ lỗi giao dịch (Error Rate) **< 0.1%** và thời gian phản hồi trung bình **<= 2 giây**. | **Concurrency:** 10,000 CCU.<br>**Error Rate:** < 0.1%.<br>**Uptime:** 99.9%. |
| **"Giao dịch thanh toán thẻ phải được mã hóa truyền tải an toàn."** | Tất cả dữ liệu giao dịch thanh toán thẻ phải được mã hóa truyền tải qua giao thức **TLS 1.3**, tuân thủ tiêu chuẩn bảo mật quốc tế **PCI-DSS Level 1** và thuật toán mã hóa dữ liệu **AES-256 bits**. | **Encryption Standard:** TLS 1.3, AES-256.<br>**Compliance:** PCI-DSS Level 1. |

---

## NHIỆM VỤ 4: XÂY DỰNG BỘ USER STORY CĂN BẢN CHO QUICKBITE

### 1. Bộ User Story chuẩn 3 thành phần (6 câu)

Cấu trúc: **Là một [Vai trò], Tôi muốn [Hành động], Để [Giá trị/Mục tiêu]**

#### A. Nhóm Khách hàng (Customer)
- **US-CUST-01:**  
  *Là một* **Khách hàng**,  
  *Tôi muốn* **gõ từ khóa tên món ăn (ví dụ: "Cơm tấm sườn bì chả") vào thanh tìm kiếm trên app mobile**,  
  *Để* **nhanh chóng tìm thấy món ăn yêu thích mà không mất thời gian lướt xem toàn bộ danh mục.**

- **US-CUST-02:**  
  *Là một* **Khách hàng**,  
  *Tôi muốn* **theo dõi vị trí di chuyển của tài xế trên bản đồ theo thời gian thực (Real-time tracking)**,  
  *Để* **chủ động biết chính xác khi nào đồ ăn được giao tới nơi để nhận hàng.**

#### B. Nhóm Chủ nhà hàng (Restaurant Owner)
- **US-POS-01:**  
  *Là một* **Chủ nhà hàng**,  
  *Tôi muốn* **bấm nút xác nhận tiếp nhận đơn hàng mới ngay trên màn hình POS trong vòng 1 chạm**,  
  *Để* **báo cho nhà bếp bắt đầu chế biến món ăn kịp thời, giảm thiểu thời gian chờ đợi của khách.**

- **US-POS-02:**  
  *Là một* **Chủ nhà hàng**,  
  *Tôi muốn* **bật/tắt nhanh trạng thái "Hết hàng" của từng món ăn trên màn hình POS**,  
  *Để* **khách hàng không thể đặt những món đã hết nguyên liệu, tránh việc phải hủy đơn và gây thất vọng cho khách.**

#### C. Nhóm Tài xế giao hàng (Driver)
- **US-DRV-01:**  
  *Là một* **Tài xế giao hàng**,  
  *Tôi muốn* **bật/tắt công tắc chế độ "Sẵn sàng nhận đơn" trên ứng dụng mobile**,  
  *Để* **chủ động kiểm soát thời gian làm việc và chỉ nhận đơn hàng mới khi tôi sẵn sàng chạy.**

- **US-DRV-02:**  
  *Là một* **Tài xế giao hàng**,  
  *Tôi muốn* **xem màn hình tổng hợp đối soát thu nhập và tiền phí giao hàng chi tiết theo ngày**,  
  *Để* **nắm rõ số tiền mình đã kiếm được và đảm bảo tính minh bạch, chính xác trong việc tính lương/thưởng.**

---

### 2. Giải thích lý do thành phần "Để [Giá trị]" là QUAN TRỌNG NHẤT

Trong câu User Story, thành phần **"Để [Giá trị / Mục tiêu]"** (So that [Benefit/Value]) là thành phần mang ý nghĩa quan trọng nhất vì các lý do sau:

1. **Xác định Động lực & Mục tiêu cốt lõi (The "WHY"):** Thành phần này trả lời cho câu hỏi *"Tại sao tính năng này lại cần tồn tại?"*. Nếu thiếu phần giá trị, tính năng chỉ là một hành động kỹ thuật đơn thuần mà không rõ mục đích kinh doanh.
2. **Cung cấp bối cảnh cho Đội ngũ Phát triển (Dev/Tester):** Khi lập trình viên và kiểm thử viên hiểu được mục đích kinh doanh đằng sau tính năng, họ sẽ thiết kế giải pháp kỹ thuật (UI/UX, kiến trúc phần mềm) tối ưu hơn, phù hợp nhất với mục tiêu của người dùng thay vì chỉ làm đúng theo mô tả bề nổi.
3. **Căn cứ để Đánh giá Ưu tiên (Prioritization):** Giúp Product Owner / System Analyst dễ dàng so sánh giá trị mang lại của các User Story khác nhau để xếp thứ tự ưu tiên phát triển (Story nào mang lại giá trị cao hơn cho người dùng/doanh nghiệp sẽ được làm trước).
4. **Tránh xây dựng tính năng dư thừa (Waste Reduction):** Nếu một câu User Story không thể chỉ ra được giá trị rõ ràng ở phần "Để...", đó là dấu hiệu cho thấy tính năng đó có thể không cần thiết và nên xem xét loại bỏ.
