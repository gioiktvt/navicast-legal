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
**Cập nhật lần cuối**: 2026-09-06

---

## 1. Tóm tắt nhanh

NaviCast là ứng dụng Android đi kèm điện thoại, chuyển biểu tượng dẫn đường (rẽ trái, rẽ phải, vòng xuyến…) từ Google Maps lên đồng hồ thông minh đã ghép nối. Hiện hỗ trợ đồng hồ Huawei, qua Huawei Health và Huawei Wear Engine.

**Nội dung thông báo — chữ hướng rẽ, địa chỉ, thời gian tới nơi, tên địa điểm mà NaviCast đọc — không bao giờ được thu thập, lưu trữ hay truyền ra khỏi thiết bị của bạn, ở bất kỳ phiên bản nào.** Nó được xử lý cục bộ rồi bỏ đi.

Thứ duy nhất rời khỏi điện thoại là **vị trí**, và chỉ ở bản Ultimate khi bạn bật bản đồ trực tiếp: toạ độ được gửi tới các dịch vụ bản đồ mã nguồn mở để nhận về ô bản đồ, tuyến đường và tên địa điểm. Xem mục 2b.

Nếu bạn chỉ có thời gian đọc 1 dòng:
- ❌ Không có tài khoản, không cần đăng nhập.
- ❌ Không có analytics, không có tracking, không có quảng cáo.
- ❌ Nội dung thông báo (chữ, địa điểm, ETA, tên đường) **không bao giờ** được upload, không lưu lên server, không chia sẻ với bên thứ ba.
- ❌ Không truy cập danh bạ, micro, camera, SMS hay bộ nhớ.
- ⚠️ **Vị trí** — chỉ bản Ultimate, và chỉ khi bạn bật bản đồ trực tiếp. Xem mục 2b.
- ✅ Đọc thông báo của Google Maps (chỉ Google Maps) trên máy bạn, dịch sang biểu tượng cho đồng hồ, rồi chuyển sang đồng hồ đã ghép nối — hiện qua Huawei Health hoặc Huawei Wear Engine.
- 💳 NaviCast miễn phí dùng thử. Sau thời gian dùng thử, **một lần mua trong ứng dụng** sẽ mở khoá vĩnh viễn. Giao dịch do **Google Play Billing** xử lý hoàn toàn — NaviCast không bao giờ thấy, không xử lý và không lưu thông tin thẻ của bạn, và không gắn giao dịch với bất kỳ tài khoản nào của chúng tôi (chúng tôi không có tài khoản nào).

---

## 2. Dữ liệu thu thập

**KHÔNG.** NaviCast không thu thập, không truyền và không lưu trữ bất kỳ dữ liệu cá nhân nào. Cụ thể:

| Loại dữ liệu | Có thu thập? | Ghi chú |
|---|---|---|
| Định danh cá nhân (tên, email, số điện thoại, ID tài khoản) | ❌ Không | App không có hệ thống tài khoản |
| Vị trí | ⚠️ Có — chỉ bản Ultimate | Dùng cho bản đồ trực tiếp và dẫn đường độc lập; toạ độ được gửi tới các dịch vụ bản đồ mã nguồn mở. Xem mục 2b |
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


## 2b. Vị trí — chỉ bản Ultimate

Bản **Ultimate** có bản đồ trực tiếp và chế độ dẫn đường độc lập. NaviCast **chỉ** xin quyền vị trí
chính xác (`ACCESS_FINE_LOCATION`) **khi bạn bật tính năng đó**. Bản **Standard** và **Pro** không
bao giờ xin quyền vị trí.

Vị trí được dùng để:
- căn bản đồ vào vị trí hiện tại và vẽ ảnh bản đồ gửi sang đồng hồ;
- tính tuyến đường và khoảng cách tới ngã rẽ kế tiếp;
- đổi toạ độ thành tên địa điểm khi bạn tìm kiếm hoặc chia sẻ một địa chỉ.

**Toạ độ của bạn được gửi tới các dịch vụ bản đồ mã nguồn mở sau**, chỉ để thực hiện đúng những việc
trên, và chỉ trong lúc bạn đang dẫn đường:

| Dịch vụ | Nhận gì | Để làm gì |
|---|---|---|
| `api.maptiler.com` hoặc `tiles.openfreemap.org` | vùng bản đồ quanh bạn | tải ô bản đồ |
| `valhalla1.openstreetmap.de` | điểm đi và điểm đến | tính tuyến đường |
| `photon.komoot.io` | toạ độ hoặc từ khoá tìm kiếm | tìm và đổi toạ độ thành tên địa điểm |

NaviCast **không có máy chủ riêng**, **không lưu lịch sử vị trí** của bạn ở đâu ngoài chính máy bạn,
và **không dùng vị trí cho quảng cáo, phân tích hay lập hồ sơ người dùng**. NaviCast **không** xin
quyền vị trí nền (`ACCESS_BACKGROUND_LOCATION`).

Dịch vụ tiền cảnh loại `location` chỉ chạy khi bạn bấm **Bắt đầu** và dừng ngay khi bạn bấm
**Dừng**. Tắt bản đồ, hoặc thu hồi quyền vị trí trong Cài đặt Android, là dừng hoàn toàn việc này.


## 3. Quyền yêu cầu

NaviCast chỉ xin **đúng tối thiểu** quyền cần để hoạt động:

| Quyền | Lý do |
|---|---|
| `BIND_NOTIFICATIONS_LISTENER_SERVICE` | Để đọc thông báo dẫn đường của Google Maps. Đây là cách **duy nhất** biết khi nào sắp có khúc rẽ. Hệ thống Android quản lý quyền này qua toggle "Notification access" — bạn chủ động bật/tắt khi nào. |
| `POST_NOTIFICATIONS` (Android 13+) | Để tạo 1 thông báo cục bộ chứa biểu tượng maneuver; ứng dụng đồng hành của đồng hồ (hiện là Huawei Health) sẽ forward lên đồng hồ. |
| `FOREGROUND_SERVICE` + `FOREGROUND_SERVICE_SPECIAL_USE` | Giữ trình đọc thông báo sống khi đang dẫn đường (Android sẽ kill listener sau vài phút trên 1 số máy). |
| `com.android.vending.BILLING` | Để cung cấp giao dịch mua một lần trong ứng dụng mở khoá sau thời gian dùng thử, qua Google Play Billing. NaviCast không xử lý dữ liệu thanh toán nào. |

App **KHÔNG** xin: danh bạ, SMS, micro, camera, bộ nhớ, Bluetooth, trạng thái điện thoại, "query all packages", hay **vị trí nền**.

App **CÓ** xin **vị trí chính xác** — chỉ bản Ultimate, và chỉ khi bạn bật bản đồ trực tiếp. Xem mục 2b.

Bạn có thể tắt `BIND_NOTIFICATION_LISTENER_SERVICE` bất cứ lúc nào:
**Cài đặt → Ứng dụng → Quyền đặc biệt → Quyền truy cập thông báo → tắt NaviCast.**

Khi tắt, NaviCast không thể đọc bất kỳ thông báo nào, kể cả Google Maps. Việc chuyển tiếp dừng ngay lập tức.

---

## 4. Dịch vụ bên thứ ba

NaviCast dùng Google Play Billing để xử lý giao dịch, và — chỉ ở bản Ultimate — các dịch vụ bản đồ mã nguồn mở cho tính năng bản đồ trực tiếp. Cụ thể:
- ❌ Không Firebase, Google Analytics, hay SDK Google Play Services nào ngoài system service mặc định và billing.
- ❌ Không Crashlytics, Sentry, Bugsnag hay crash reporter khác.
- ❌ Không SDK quảng cáo.
- ❌ Không đăng nhập mạng xã hội.
- ✅ **Google Play Billing** — chỉ dùng để xử lý giao dịch mua một lần mở khoá ứng dụng sau thời gian dùng thử.
- ✅ **Huawei IAP** — vai trò như Google Play Billing, cho bản cài từ AppGallery.
- ✅ **MapTiler / OpenFreeMap, Valhalla, Photon** — chỉ bản Ultimate, dùng cho ô bản đồ, định tuyến và tìm địa điểm. Các dịch vụ này nhận toạ độ của bạn trong lúc dẫn đường. Xem mục 2b.

**Google Play Billing.** Khi bạn chọn mua, NaviCast chuyển bạn sang ứng dụng Google Play Store; Play Store thu thập và xử lý thanh toán hoàn toàn ở phía họ. NaviCast chỉ nhận lại một purchase token / trạng thái quyền xác nhận đã mở khoá — không bao giờ nhận số thẻ, địa chỉ thanh toán hay phương tiện thanh toán. Việc Google xử lý dữ liệu thanh toán đó tuân theo **Chính sách Bảo mật của Google** (https://policies.google.com/privacy), không phải của chúng tôi.

NaviCast tương tác với **Huawei Health** chỉ gián tiếp: post 1 Android notification thông thường; Huawei Health (bạn cài + cấu hình riêng) đọc nó như đọc bất kỳ notification nào khác. App không dùng API của Huawei Health trực tiếp.

---

## 5. Chia sẻ dữ liệu

Ngoài hai trường hợp dưới đây, chúng tôi **không chia sẻ dữ liệu với bất kỳ ai**, và không có gì khác rời khỏi thiết bị của bạn. **Nội dung thông báo không bao giờ được truyền đi đâu, ở bất kỳ phiên bản nào.**

Cụ thể:
- Không bán dữ liệu của bạn.
- Không chia sẻ với nhà quảng cáo.
- Không chia sẻ với analytics provider.
- Không chia sẻ với cơ quan thực thi pháp luật (chúng tôi không có dữ liệu để cung cấp).

Ngoại lệ thứ nhất là **vị trí ở bản Ultimate**: trong lúc bạn dẫn đường, toạ độ được gửi tới các dịch vụ bản đồ mã nguồn mở liệt kê ở mục 2b để nhận về ô bản đồ, tuyến đường và tên địa điểm. Các dịch vụ này do bên thứ ba vận hành theo chính sách riêng của họ. Chúng tôi chỉ gửi đúng toạ độ và từ khoá cần cho yêu cầu đó — không kèm mã định danh, tài khoản, hay nội dung thông báo.

Ngoại lệ thứ hai là **xử lý thanh toán**: nếu bạn mua hàng, giao dịch diễn ra trực tiếp giữa bạn và **Google Play**, theo chính sách bảo mật riêng của Google. NaviCast không nhận và không chuyển tiếp dữ liệu thanh toán đó — chúng tôi chỉ biết việc mở khoá có thành công hay không.

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
"Huawei", "Huawei Health", "Huawei Watch", "Huawei Band", "Huawei Watch GT", "Huawei Watch Fit" là nhãn hiệu của Huawei Technologies Co., Ltd.

NaviCast là **ứng dụng độc lập của bên thứ ba**. NaviCast **không liên kết, không được tài trợ, không được chứng thực** bởi Google hay Huawei. NaviCast không sử dụng API của các công ty này (ngoài việc đọc Android notification công khai — bất kỳ app cài đặt bởi user nào với quyền notification access đều có thể làm).

---

*Chính sách này được viết bằng tiếng Việt phổ thông. Bản tiếng Anh tại [privacy-policy-en.md](privacy-policy-en.md). Hai phiên bản có giá trị pháp lý tương đương; trong trường hợp có khác biệt, bản tiếng Việt áp dụng cho người dùng tại Việt Nam, bản tiếng Anh áp dụng cho khu vực khác.*
