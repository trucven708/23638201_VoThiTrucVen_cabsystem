# 23638201_VoThiTrucVen_cabsystem
## 1. 
#### Vấn đề của hệ thống cũ
* Đặt xe còn thủ công.
* Phân công tài xế thủ công, mất thời gian.
* Khó theo dõi trạng thái và vị trí chuyến.
* Quản lý thanh toán chưa tập trung.
* Khó mở rộng khi số lượng người dùng tăng.
* Thông báo và xử lý sự cố còn hạn chế.
* Thiếu báo cáo, phân quyền và bảo mật.
  
#### Tại sao cần hệ thống mới?

* Hệ thống cũ còn nhiều thao tác **thủ công**, đặc biệt là phân công tài xế.
* Khó **theo dõi chuyến đi và quản lý thanh toán**.
* Khó đáp ứng khi **số lượng khách hàng và tài xế tăng**.
* Thiếu khả năng **quản lý, báo cáo và bảo mật**.

#### Hệ thống mới giúp ích gì?

* **Tự động tìm và phân công tài xế** → giảm thời gian vận hành.
* **Theo dõi chuyến theo thời gian thực** → khách hàng chủ động hơn.
* **Tập trung quản lý thanh toán và dữ liệu** → dễ kiểm soát, tra cứu.
* **Thông báo tự động** → tăng trải nghiệm khách hàng và tài xế.
* **Báo cáo, phân quyền** → hỗ trợ quản lý và ra quyết định.
* **Có khả năng mở rộng** → đáp ứng nhiều người dùng và dễ phát triển tính năng mới.

## 2.

| Stakeholder                 | Vai trò                                              | Tầm quan trọng |
| --------------------------- | ---------------------------------------------------- | -------------- |
| **Khách hàng**              | Đặt xe, theo dõi chuyến, thanh toán, đánh giá        | **Cao**        |
| **Tài xế**                  | Nhận và thực hiện chuyến, cập nhật trạng thái/vị trí | **Cao**        |
| **Nhân viên vận hành**      | Quản lý tài xế, khách hàng, chuyến đi và xử lý sự cố | **Cao**        |
| **Ban giám đốc**            | Định hướng, phê duyệt và theo dõi hiệu quả dự án     | **Cao**        |
| **Tài chính/Kế toán**       | Quản lý doanh thu, thanh toán và đối soát            | **Trung bình** |
| **IT/Đội phát triển**       | Xây dựng, triển khai và bảo trì hệ thống             | **Cao**        |
| **Nhà cung cấp thanh toán** | Xử lý thanh toán điện tử                             | **Trung bình** |
| **Nhà cung cấp thông báo**  | Cung cấp SMS/Email/Push Notification                 | **Trung bình** |

``` mermaid
quadrantChart
    title Ma trận Power - Interest của Stakeholder CAB
    x-axis "Mức độ quan tâm thấp" --> "Mức độ quan tâm cao"
    y-axis "Quyền lực thấp" --> "Quyền lực cao"

    quadrant-1 "Quản lý chặt"
    quadrant-2 "Giữ hài lòng"
    quadrant-3 "Theo dõi"
    quadrant-4 "Giữ thông tin"

    "Ban giám đốc": [0.88, 0.95]
    "Vận hành": [0.85, 0.82]
    "IT": [0.72, 0.78]
    "Kế toán": [0.55, 0.68]

    "Khách hàng": [0.88, 0.35]
    "Tài xế": [0.82, 0.32]
    "Payment": [0.48, 0.28]
    "Notification": [0.35, 0.20]
```
## 3.Mục đích nghiệp vụ của hệ thống CAB

* **Đáp ứng số lượng lớn khách hàng** và tài xế.
* **Tự động hóa việc phân công tài xế**, giảm thao tác thủ công.
* **Hỗ trợ nhiều phương thức thanh toán** như tiền mặt và thanh toán điện tử.
* **Nâng cao trải nghiệm khách hàng** thông qua theo dõi chuyến và thông báo.
* **Quản lý tập trung** khách hàng, tài xế, chuyến đi và giao dịch.
* **Tăng hiệu quả vận hành** và giảm thời gian xử lý.
* **Cung cấp báo cáo, thống kê** để hỗ trợ ra quyết định.
* **Đảm bảo hệ thống có khả năng mở rộng** và dễ bổ sung dịch vụ mới.
* **Tăng tính bảo mật và an toàn dữ liệu**.
  
## 4. Xác định phạm vi dự án trong 7 tuần

### Các module quan trọng để hệ thống CAB hoạt động

Có thể chia thành **8 module cốt lõi**:

| Module                     | Chức năng chính                               | 
| -------------------------- | --------------------------------------------- | 
| **1. User Management**     | Đăng ký, đăng nhập, quản lý khách hàng/tài xế | 
| **2. Booking & Trip**      | Tạo booking, quản lý trạng thái chuyến        | 
| **3. Driver & Vehicle**    | Quản lý tài xế, xe, trạng thái sẵn sàng       | 
| **4. Driver Dispatch**     | Tìm và phân công tài xế tự động               | 
| **5. Location & Tracking** | Vị trí tài xế, ETA, theo dõi chuyến           | 
| **6. Fare & Payment**      | Tính cước, tiền mặt/thanh toán điện tử        | 
| **7. Notification**        | Thông báo cho khách hàng và tài xế            | 
| **8. Admin/Ops**           | Quản lý và xử lý chuyến, tài xế, giao dịch    |

## 5. Yêu cầu nghiệp vụ (Business Requirements)

| ID       | Yêu cầu nghiệp vụ                                                                                     |
| -------- | ----------------------------------------------------------------------------------------------------- |
| **BR01** | Khách hàng có thể **đăng ký, đăng nhập và quản lý thông tin cá nhân**.                                |
| **BR02** | Khách hàng có thể **đặt xe**, nhập **điểm đón, điểm đến** và lựa chọn loại xe.                        |
| **BR03** | Hệ thống **tự động tìm và phân công tài xế phù hợp** dựa trên vị trí và trạng thái tài xế.            |
| **BR04** | Khách hàng được **thông báo** khi đặt xe thành công và khi tài xế nhận chuyến.                        |
| **BR05** | Khách hàng có thể **theo dõi chuyến đi**, vị trí tài xế và thời gian dự kiến đến.                     |
| **BR06** | Tài xế có thể **nhận/từ chối chuyến** và cập nhật trạng thái chuyến đi.                               |
| **BR07** | Sau khi chuyến hoàn thành, hệ thống **tính cước** và hiển thị số tiền khách hàng cần thanh toán.      |
| **BR08** | Khách hàng có thể **thanh toán bằng tiền mặt hoặc phương thức điện tử** theo chính sách doanh nghiệp. |
| **BR09** | Khách hàng có thể **xem lịch sử chuyến đi và giao dịch**.                                             |
| **BR10** | Khách hàng có thể **đánh giá tài xế sau khi hoàn thành chuyến**.                                      |
| **BR11** | Nhân viên vận hành có thể **quản lý khách hàng, tài xế, phương tiện và chuyến đi**.                   |
| **BR12** | Hệ thống cung cấp **báo cáo về số chuyến, doanh thu, tỷ lệ hoàn thành và hủy chuyến**.                |

### Luồng nghiệp vụ chính

**Đăng nhập → Nhập điểm đón/điểm đến → Đặt xe → Hệ thống tìm tài xế → Tài xế nhận → Theo dõi chuyến → Hoàn thành → Thanh toán → Đánh giá.**

## 6. Phân rã chức năng

### 1. Đặt xe

* Nhập điểm đón.
* Nhập điểm đến.
* Chọn loại xe.
* Xác nhận yêu cầu.
* Tạo chuyến đi.

### 2. Tìm tài xế

* Xác định vị trí khách hàng.
* Xác định bán kính tìm kiếm.
* Lập danh sách tài xế đang sẵn sàng.
* Kiểm tra loại xe phù hợp.
* Tính khoảng cách từ tài xế đến khách.
* Xếp hạng tài xế theo tiêu chí.
* Gửi yêu cầu cho tài xế.
* Chờ tài xế chấp nhận.
* Nếu từ chối/không phản hồi → tìm tài xế tiếp theo.
* Không có tài xế → thông báo khách hàng.

### 3. Thực hiện chuyến

* Tài xế xác nhận nhận chuyến.
* Theo dõi vị trí tài xế.
* Cập nhật: Đã đến → Đã đón khách → Đang di chuyển → Hoàn thành.
* Cập nhật ETA cho khách hàng.
* Gửi thông báo thay đổi trạng thái.

### 4. Tính cước & thanh toán

* Xác định loại dịch vụ.
* Tính khoảng cách/thời gian.
* Tính giá chuyến.
* Hiển thị số tiền cần trả.
* Thanh toán tiền mặt hoặc điện tử.
* Xử lý thanh toán thất bại.
* Lưu lịch sử giao dịch.

### 5. Sau chuyến

* Cập nhật chuyến hoàn thành.
* Gửi thông báo cho khách hàng.
* Khách hàng xem chi tiết/cước.
* Đánh giá tài xế.
* Lưu lịch sử chuyến.

### 6. Quản trị vận hành

* Quản lý khách hàng.
* Quản lý tài xế.
* Quản lý phương tiện.
* Theo dõi chuyến đang diễn ra.
* Xử lý chuyến lỗi/hủy.
* Tra cứu giao dịch.
* Xem báo cáo.

