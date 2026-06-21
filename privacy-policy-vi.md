---
layout: default
title: Chính sách Bảo mật NaviCast
permalink: /privacy-policy-vi.html
lang: vi
---

# Chính sách Bảo mật — NaviCast

**Tên ứng dụng**: NaviCast
**Application ID**: `com.gioitv.navicast`
**Nhà phát triển**: gioitv (gioitv86@gmail.com)
**Ngày hiệu lực**: 2026-05-08
**Cập nhật lần cuối**: 2026-06-20

---

## 1. Tóm tắt nhanh

NaviCast là ứng dụng Android đi kèm điện thoại, có nhiệm vụ chuyển biểu tượng dẫn đường (rẽ trái, rẽ phải, vòng xuyến…) từ Google Maps lên đồng hồ thông minh Huawei thông qua ứng dụng Huawei Health. **NaviCast không thu thập, không lưu trữ và không truyền bất kỳ dữ liệu cá nhân nào ra khỏi thiết bị của bạn.** Mọi xử lý diễn ra cục bộ trên máy.

Nếu bạn chỉ có thời gian đọc 1 dòng:
- ❌ Không có tài khoản, không cần đăng nhập.
- ❌ Không có analytics, không có tracking, không có quảng cáo.
- ❌ Nội dung thông báo (chữ, địa điểm, ETA, tên đường) **không bao giờ** được upload, không lưu lên server, không chia sẻ với bên thứ ba.
- ❌ Không truy cập vị trí, danh bạ, micro, camera, SMS hay bộ nhớ.
- ✅ Đọc thông báo của Google Maps (chỉ Google Maps) trên máy bạn, dịch sang biểu tượng cho đồng hồ, đẩy notification cục bộ để Huawei Health forward.
- 💳 NaviCast miễn phí dùng thử. Sau thời gian dùng thử, **một lần mua trong ứng dụng** sẽ mở khoá vĩnh viễn. Giao dịch do **Google Play Billing** xử lý hoàn toàn — NaviCast không bao giờ thấy, không xử lý và không lưu thông tin thẻ của bạn, và không gắn giao dịch với bất kỳ tài khoản nào của chúng tôi (chúng tôi không có tài khoản nào).

---

## 2. Dữ liệu thu thập

**KHÔNG.** NaviCast không thu thập, không truyền và không lưu trữ bất kỳ dữ liệu cá nhân nào. Cụ thể:

| Loại dữ liệu | Có thu thập? | Ghi chú |
|---|---|---|
| Định danh cá nhân (tên, email, số điện thoại, ID tài khoản) | ❌ Không | App không có hệ thống tài khoản |
| Vị trí | ❌ Không | App **không** xin quyền vị trí |
| Danh bạ, SMS, lịch sử cuộc gọi | ❌ Không | Các quyền này **không** được xin |
| Nội dung thông báo (text maneuver Google Maps, địa danh) | ⚠️ Đọc tại chỗ | Chỉ dùng để render biểu tượng + nhãn khoảng cách trên 1 thông báo cục bộ. **Không** lưu, không log, không truyền. |
| Định danh thiết bị (IMEI, advertising ID) | ❌ Không | App **không** đọc device IDs |
| Báo cáo crash, analytics, diagnostics | ❌ Không | NaviCast không dùng Firebase, Crashlytics, Sentry hay bất kỳ analytics SDK nào |
| File, ảnh, media | ❌ Không | App **không** xin quyền bộ nhớ |
| Thông tin thanh toán / thẻ | ❌ Không | Giao dịch mua một lần do **Google Play Billing** xử lý. NaviCast không bao giờ nhận số thẻ, địa chỉ thanh toán hay bất kỳ dữ liệu phương tiện thanh toán nào. |
| Trạng thái mua hàng | ⚠️ Chỉ trên máy | Sau khi mua, NaviCast lưu một cờ "đã mở khoá" cục bộ và hỏi Google Play để xác nhận quyền. Cờ này không phải dữ liệu cá nhân và không được gửi cho chúng tôi (chúng tôi không có server). |

**Cài đặt app** (preset đồng hồ, đơn vị khoảng cách, ngôn ngữ, theme, vibration toggle, cờ đã hoàn thành onboarding) lưu cục bộ trên máy qua Android Jetpack DataStore trong vùng riêng tư của app. Các cài đặt này:
- Không bao giờ rời thiết bị.
- Tự xoá khi gỡ app.
- Không chứa dữ liệu cá nhân — chỉ là tuỳ chọn UI.

---

## 3. Quyền yêu cầu

NaviCast chỉ xin **đúng tối thiểu** quyền cần để hoạt động:

| Quyền | Lý do |
|---|---|
| `BIND_NOTIFICATIONS_LISTENER_SERVICE` | Để đọc thông báo dẫn đường của Google Maps. Đây là cách **duy nhất** biết khi nào sắp có khúc rẽ. Hệ thống Android quản lý quyền này qua toggle "Notification access" — bạn chủ động bật/tắt khi nào. |
| `POST_NOTIFICATIONS` (Android 13+) | Để tạo 1 thông báo cục bộ chứa biểu tượng maneuver, Huawei Health sẽ forward lên đồng hồ. |
| `FOREGROUND_SERVICE` + `FOREGROUND_SERVICE_SPECIAL_USE` | Giữ trình đọc thông báo sống khi đang dẫn đường (Android sẽ kill listener sau vài phút trên 1 số máy). |
| `com.android.vending.BILLING` | Để cung cấp giao dịch mua một lần trong ứng dụng mở khoá sau thời gian dùng thử, qua Google Play Billing. NaviCast không xử lý dữ liệu thanh toán nào. |

App **KHÔNG** xin: vị trí, danh bạ, SMS, micro, camera, bộ nhớ, Bluetooth, trạng thái điện thoại, hay "query all packages".

Bạn có thể tắt `BIND_NOTIFICATION_LISTENER_SERVICE` bất cứ lúc nào:
**Cài đặt → Ứng dụng → Quyền đặc biệt → Quyền truy cập thông báo → tắt NaviCast.**

Khi tắt, NaviCast không thể đọc bất kỳ thông báo nào, kể cả Google Maps. Việc chuyển tiếp dừng ngay lập tức.

---

## 4. Dịch vụ bên thứ ba

NaviCast chỉ dùng **một** dịch vụ bên thứ ba — Google Play Billing, để xử lý giao dịch. Cụ thể:
- ❌ Không Firebase, Google Analytics, hay SDK Google Play Services nào ngoài system service mặc định và billing.
- ❌ Không Crashlytics, Sentry, Bugsnag hay crash reporter khác.
- ❌ Không SDK quảng cáo.
- ❌ Không đăng nhập mạng xã hội.
- ✅ **Google Play Billing** — chỉ dùng để xử lý giao dịch mua một lần mở khoá ứng dụng sau thời gian dùng thử.

**Google Play Billing.** Khi bạn chọn mua, NaviCast chuyển bạn sang ứng dụng Google Play Store; Play Store thu thập và xử lý thanh toán hoàn toàn ở phía họ. NaviCast chỉ nhận lại một purchase token / trạng thái quyền xác nhận đã mở khoá — không bao giờ nhận số thẻ, địa chỉ thanh toán hay phương tiện thanh toán. Việc Google xử lý dữ liệu thanh toán đó tuân theo **Chính sách Bảo mật của Google** (https://policies.google.com/privacy), không phải của chúng tôi.

NaviCast tương tác với **Huawei Health** chỉ gián tiếp: post 1 Android notification thông thường; Huawei Health (bạn cài + cấu hình riêng) đọc nó như đọc bất kỳ notification nào khác. App không dùng API của Huawei Health trực tiếp.

---

## 5. Chia sẻ dữ liệu

**Không chia sẻ với ai.** Vì không có dữ liệu nào để chia sẻ — không có gì rời thiết bị.

Cụ thể:
- Không bán dữ liệu của bạn.
- Không chia sẻ với nhà quảng cáo.
- Không chia sẻ với analytics provider.
- Không chia sẻ với cơ quan thực thi pháp luật (chúng tôi không có dữ liệu để cung cấp).

Ngoại lệ duy nhất là **xử lý thanh toán**: nếu bạn mua hàng, giao dịch diễn ra trực tiếp giữa bạn và **Google Play**, theo chính sách bảo mật riêng của Google. NaviCast không nhận và không chuyển tiếp dữ liệu thanh toán đó — chúng tôi chỉ biết việc mở khoá có thành công hay không.

---

## 6. Riêng tư trẻ em

NaviCast không nhắm tới trẻ em dưới 13 tuổi. App không cố ý thu thập dữ liệu từ ai, kể cả trẻ em. Vì không thu thập gì, không có vấn đề gì về dữ liệu trẻ em cần lưu/xoá/báo cáo.

---

## 7. Quyền của bạn

Vì NaviCast không thu thập dữ liệu, không có dữ liệu nào để truy cập, xoá hay export. Tuy nhiên:

- **Để dừng app đọc thông báo**: thu hồi quyền (Cài đặt → Ứng dụng → Quyền đặc biệt → Quyền truy cập thông báo → NaviCast → tắt).
- **Để dừng app hoàn toàn**: gỡ cài đặt. Toàn bộ cài đặt local sẽ bị xoá.
- **Để hỏi thông tin**: liên hệ nhà phát triển (xem §10 dưới). Chúng tôi trả lời trong vòng 30 ngày.

Nếu bạn ở EU/UK (GDPR/UK DPA), EEA, California (CCPA) hoặc các khu vực có luật tương tự, quyền truy cập/đính chính/xoá dữ liệu cá nhân được bảo toàn mặc định — đơn giản vì không có dữ liệu cá nhân nào đang được xử lý.

---

## 8. Bảo mật

NaviCast tuân thủ best practice bảo mật:
- Mọi xử lý **chỉ trên thiết bị**. Không có server.
- Nội dung thông báo giữ trong RAM tạm thời cho 1 phiên dẫn đường, sau đó giải phóng.
- Nội dung thông báo **không bao giờ** log trong release build (verified qua audit source code + ProGuard rules).
- APK release được ký qua quy trình CI tự động; khoá ký không bao giờ rời môi trường bảo mật của nhà phát triển.
- Mã nguồn đóng và được rà soát trước mỗi bản phát hành.

---

## 9. Thay đổi chính sách

Nếu chính sách thay đổi:
1. Cập nhật ngày "Cập nhật lần cuối" ở đầu file.
2. Ghi chú trong release notes Play Store.
3. Nếu thay đổi mang tính trọng yếu (vd nếu chúng tôi bao giờ bắt đầu thu thập dữ liệu — chưa có kế hoạch nào như vậy), chúng tôi sẽ yêu cầu user đồng ý explicit trước khi thay đổi có hiệu lực.

Bạn có thể xem phiên bản hiện tại tại: `https://gioiktvt.github.io/navicast-legal/privacy-policy-vi.html` (Tiếng Việt) hoặc `https://gioiktvt.github.io/navicast-legal/privacy-policy.html` (English).

---

## 10. Liên hệ

Cho câu hỏi, yêu cầu, hoặc khiếu nại về Chính sách Bảo mật:

- **Email**: gioitv86@gmail.com

Vui lòng dùng tiếng Việt hoặc tiếng Anh.

---

## 11. Lưu ý nhãn hiệu

"Google Maps" và logo Google Maps là nhãn hiệu của Google LLC.
"Vietmap" là nhãn hiệu của Công ty Cổ phần Vietmap.
"Waze" là nhãn hiệu của Waze Mobile Ltd.
"Huawei", "Huawei Health", "Huawei Watch", "Huawei Band", "Huawei Watch GT", "Huawei Watch Fit" là nhãn hiệu của Huawei Technologies Co., Ltd.

NaviCast là **ứng dụng độc lập của bên thứ ba**. NaviCast **không liên kết, không được tài trợ, không được chứng thực** bởi Google, Vietmap, Waze hay Huawei. NaviCast không sử dụng API của các công ty này (ngoài việc đọc Android notification công khai — bất kỳ app cài đặt bởi user nào với quyền notification access đều có thể làm).

---

*Chính sách này được viết bằng tiếng Việt phổ thông. Bản tiếng Anh tại [privacy-policy-en.md](privacy-policy-en.md). Hai phiên bản có giá trị pháp lý tương đương; trong trường hợp có khác biệt, bản tiếng Việt áp dụng cho người dùng tại Việt Nam, bản tiếng Anh áp dụng cho khu vực khác.*
