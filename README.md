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

### Mindmap Stakeholder

```text
                         ┌──────────────────┐
                         │   CAB SYSTEM     │
                         └────────┬─────────┘
                                  │
          ┌───────────────────────┼───────────────────────┐
          │                       │                       │
          ▼                       ▼                       ▼
   👤 NGƯỜI DÙNG             🏢 NỘI BỘ               🔗 ĐỐI TÁC
          │                       │                       │
     ┌────┴────┐          ┌───────┼───────┐          ┌────┴────┐
     ▼         ▼          ▼       ▼       ▼          ▼         ▼
 Khách hàng  Tài xế    Ban GĐ  Vận hành   IT     Thanh toán  Thông báo
     │         │          │       │       │          │         │
     ▼         ▼          ▼       ▼       ▼          ▼         ▼
 Đặt xe     Nhận xe    Phê duyệt Quản lý Phát triển  Payment   SMS/Email/
 Theo dõi   Thực hiện  Chiến lược Chuyến Hệ thống   điện tử    Push
 Thanh toán Cập nhật
 Đánh giá   vị trí
```
                         MỨC ĐỘ QUAN TÂM
                    THẤP ───────────────► CAO

            ▲
            │
      CAO   │  GIỮ HÀI LÒNG       QUẢN LÝ CHẶT
            │  • Kế toán           • Ban giám đốc
            │                      • Vận hành
QUYỀN       │                      • IT
LỰC         │
            │  THEO DÕI            GIỮ THÔNG TIN
      THẤP  │  • Notification      • Khách hàng
            │                      • Tài xế
            │                      • Payment
            └──────────────────────────────────►
