---
title: TẦNG DATA
date: 2024-12-30
draft: false
tags:
  - firstblog
  - mangmaytinh
---
1. **Những thiết bị nào hoạt động tại tầng DataLink**
    
    - Switch (Bộ chuyển mạch): là thiết bị mạng chuyển tiếp dữ liệu giữa các thiết bị trong một mạng LAN
    - Bridge (Cầu nối): Kết nối hai hoặc nhiều phân đoạn mạng lại với nhau tạo thành một mạng Logic duy nhất; giảm xung đột mạng bằng cách chia một mạng lớn thành nhiều phần nhỏ
    - NIC (Network Interface Card: Card mạng): Giúp các thiết bị kết nối được vào mạng, tham gia vào quá trình đóng mở gói
2. **Địa chỉ MAC**
    
    - Viết tắt của Media access control address
    - Đây là địa chỉ vật lý duy nhất và độc nhất được gán cho thiết bị, địa chỉ MAC hoạt động ở tầng thứ 2 (Datalink) trong mô hình OSI
    - Chiều dài: 48 bit chia thành, chia thành 6 ô, mỗi ô 2 ký tự theo hệ thập lục phân (decimnalhexa), mỗi ô được ngăn cách với nhau bằng dấu hai chấm (:) hoặc dấu gạch ngang (-). VD: 1A:2B:3C:4D:5E:6F or 1A-2B-3C-4D-5E-6F
    - Địa chỉ MAC được chia thành hai phần:
        - OUI (Organizationally Unique Identifier): 24 bit đầu tiên được dùng để xác định nhà sản xuất thiết bị là ai và do IEEE gán cho nhà sản xuất thiết bị
        - NIC (Network Interface Controller): 24 bit còn lại mới thật sự là địa chỉ MAC của thiết bị được gán một cách độc nhất cho thiết bị để bảo đảm không có 2 thiết bị nào có cùng địa chỉ MAC
3. **Các giao thức chuẩn IEEE (Institute of Electrical and Electronics Engineers)**
    
    - Là chuẩn chung nhằm đảm bảo khả năng tương thích và tương tác giữa các thiết bị điện, điện tử thuộc nhiều nhà sản xuất khác nhau trên thị trường
    - Một số chuẩn phổ biến:
        - Ethernet (IEEE 802.3): dây vật lý dùng trong mạng LAN
        - Wifi (IEEE 802.11): Chuẩn cho mạng không dây
        - IEEE 802.1: Tiêu chuẩn liên quan đến quản lý mạng và bảo mật
        - WPAN (IEEE 802.15): Tiêu chuẩn cho điểm truy cập cá nhân không dây