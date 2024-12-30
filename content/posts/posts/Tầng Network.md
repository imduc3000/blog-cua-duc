---
title: TẦNG NETWORK
date: 2024-12-30
draft: false
tags:
  - firstblog
  - mangmaytinh
---
1. **Vai trò, chức năng, nguyên lý hoạt động của Router?**

- Chức năng của Router
    - Kết nối các mạng khác nhau lại với nhau
    - **Định tuyến (Routing)**: Router sử dụng các bảng định tuyến và giao thức định tuyến để tìm và duy trì các đường dẫn tốt nhất cho việc truyền dữ liệu.
    - **Chuyển tiếp Gói tin (Packet Forwarding)**: Router nhận, phân tích và chuyển tiếp các gói tin đến địa chỉ đích.
    - **Kiểm soát Truy cập (Access Control)**: Router sử dụng các quy tắc để cho phép hoặc từ chối các gói tin dựa trên nguồn, đích hoặc nội dung.
    - **NAT (Network Address Translation)**: Router chuyển đổi địa chỉ IP nội bộ sang địa chỉ IP công cộng để giao tiếp với Internet.

1. **So sánh sự khác nhau giữa Ipv4 và Ipv6 (VD: độ dài Ipv4, Ipv6 là bao nhiêu bits?, …..)**

- IP là gì
    
    - Địa chỉ IP là một dãy số
    - Mọi thiết bị muốn truy cập và truyền thông tin trên Internet đều cần có một địa chỉ IP để giao tiếp với nhau
    - Địa chỉ IP gồm hai phần: Phần Network và Phần Host
    - Hai loại IP phổ biến: IPV4 và IPV6
- IPV4
    
    - IP gồm 32 bit phân cách bằng bốn dấu chấm (VD: 192.168.1.1)
    - Mội một cụm số trước dấu chấm được gọi là 1 Octet
    - Mỗi Octet có range từ 0-255
    - Có 2^32 địa chỉ IPV4 ~ 4,3 tỷ IP
    - Máy tính đọc địa chỉ IPV4 bằng số nhị phân (số binary)
    - Có 5 lớp trong địa chỉ IPV4:
        - Class A,B,C có thể dùng cho Host
        - Class D dùng để Multicast
        - Class E dùng để Experimental
    
    ```python
    +------+----------------------------+----------------+
    | Class|      IP Address Range      | Default Subnet |
    |      |                            |      Mask      |
    +------+----------------------------+----------------+
    |   A  |  1.0.0.0 - 126.255.255.255 |  255.0.0.0     |
    |   B  |  128.0.0.0 - 191.255.255.0 |  255.255.0.0   |
    |   C  |  192.0.0.0 - 223.255.255.0 |  255.255.255.0 |
    |   D  |  224.0.0.0 - 239.255.255.0 |  Multicast     |
    |   E  |  240.0.0.0 - 255.255.255.0 |  Reserved      |
    +------+----------------------------+----------------+
    ```
    
- IPV6
    
    - IP gồm 128 bit ở thể thập lục phân
    - Có 2^128 địa chỉ IPV6
    - Cách chia IPV6

```python
+------+-----+
| Hex  | Bin |
+------+-----+
|  10  |  A  |
|  11  |  B  |
|  12  |  C  |
|  13  |  D  |
|  14  |  E  |
|  15  |  F  |
+------+-----+

4 Bit Chart:
+---+---+---+---+
| 8 | 4 | 2 | 1 |
+---+---+---+---+
| 1 | 0 | 1 | 1 | = B (11)

Binary: 0010 0110 1101 1011
Hex:    2    6    D    B
```

- IPIPA
    - Viết tắt của Automatic Private IP addressing
    - Khi request DHCP fail, máy WINDOW sẽ được tự động gán cho địa chỉ IPIPA
    - Địa chỉ này có range từ: 169.254.0.1 - 169.254.255.254 với Subnet Mask: 255.255.0.0
    - Địa chỉ IP này sẽ giúp máy liên lạc được với các máy khác trong mạng cục bộ nhưng không vào được Internet hoặc kết nối với máy tính ở mạng khác
- Public và Private IP address
    - Public IP address: Địa chỉ này là có hạn và là độc nhất, khi đi thuê mạng từ các ISP họ sẽ cung cấp cho chúng ta một Public IP Address
        
    - Private IP address: Địa chỉ này là không độc nhất, Khi ISP cung cấp một địa chỉ Public IP address, bên trong Router có sẵn một giao thức NAT (Network Address Translation) và một DHCP sever: DHCP sever dùng để chia địa chỉ Private cho các thiết bị bên trong sử dụng còn giao thức NAT dịch các địa chỉ Private thành Public mỗi lần có thiết bị nào truy cập vào Internet, điều này giúp tiết kiệm rất nhiều địa chỉ Public IP address
        
        ```python
        +-------+---------------------------+-----------------+
        | Class |     IP Address Range      | Default Subnet  |
        |       |                           |      Mask       |
        +-------+---------------------------+-----------------+
        |   A   | 10.0.0.0 - 10.255.255.255 |  255.0.0.0      |
        |   B   | 172.16.0.0 - 172.31.255.255|  255.255.0.0    |
        |   C   | 192.168.0.0 - 192.168.255.255|255.255.255.0|
        +-------+---------------------------+-----------------+
        ```
        

1. Các thuật ngữ viết tắt (NAT, ARP, RIP, DNS, IPS,…..)

- **NAT (Network Address Translation)**
    - **Chức năng**: NAT là một kỹ thuật được sử dụng trong mạng máy tính để thay đổi địa chỉ IP nguồn trong các gói tin khi chúng đi qua một bộ định tuyến hoặc cổng tường lửa.
    - **Mục đích**: Mục đích chính của NAT là bảo tồn địa chỉ IPv4 công cộng và tăng cường bảo mật mạng bằng cách ẩn địa chỉ IP nội bộ.
    - **Hoạt động**: NAT có thể hiểu đơn giản là một phiên dịch viên đứng giữa và thường được tích hợp vào router. Khi đi đăng kí wifi FPT sẽ cũng cấp cho mỗi nhà một địa chỉ IP công cộng, Địa chỉ IP này đi qua router sẽ được router tạo ra các private IP và dùng DHCP server chia đều cho các thiết bị trong nhà. Tuy nhiên private IP không dùng để truy cập vào Internet được mà chỉ public IP mới làm được vậy nên NAT có mặt để phiên dịch private IP thành public và ngược lại
- **RIP (Routing Information Protocol)**
    - **Chức năng**: RIP là một giao thức định tuyến được sử dụng trong các mạng LAN và WAN để giúp các bộ định tuyến chia sẻ thông tin về cấu trúc mạng và chọn đường đi tốt nhất cho dữ liệu.
    - **Mục đích**: Cung cấp một phương thức đơn giản để các bộ định tuyến trao đổi thông tin định tuyến và duy trì bảng định tuyến.
    - **Hoạt động**: RIP sử dụng một thuật toán khoảng cách vector, gửi các bản cập nhật bảng định tuyến định kỳ (thường là 30 giây một lần) tới tất cả các bộ định tuyến khác trong mạng. Mỗi bộ định tuyến cập nhật bảng định tuyến của mình dựa trên thông tin nhận được.
- **IPS (Intrusion Prevention System)**
    - **Chức năng**: IPS là một hệ thống bảo mật mạng được thiết kế để phát hiện và ngăn chặn các hoạt động tấn công hoặc xâm nhập vào mạng.
    - **Mục đích**: Bảo vệ mạng khỏi các mối đe dọa bằng cách ngăn chặn các cuộc tấn công trước khi chúng có thể gây ra thiệt hại.
    - **Hoạt động**: IPS giám sát lưu lượng mạng để tìm các hành vi đáng ngờ hoặc các mẫu tấn công đã biết. Khi phát hiện một mối đe dọa, IPS có thể tự động chặn hoặc ngăn chặn hoạt động đó, gửi cảnh báo cho quản trị viên, và ghi lại chi tiết về sự kiện để phân tích thêm.
- **IDS (Intrusion Detection System)**
    - **IDS** (Hệ thống phát hiện xâm nhập) là một hệ thống an ninh mạng được thiết kế để phát hiện các hoạt động bất thường hoặc xâm nhập trong mạng hoặc hệ thống máy tính. IDS hoạt động bằng cách theo dõi, ghi lại và phân tích lưu lượng mạng để phát hiện các dấu hiệu của các hành vi không mong muốn hoặc xâm nhập trái phép.
- **SPI (Stateful Packet Inspection)**
    - **SPI** (Kiểm tra gói trạng thái) là một kỹ thuật bảo mật được sử dụng trong tường lửa (firewall) để giám sát các trạng thái của các kết nối mạng. SPI không chỉ kiểm tra các thông tin tiêu đề của các gói dữ liệu (header) mà còn theo dõi trạng thái của các phiên kết nối để đưa ra quyết định chặn hoặc cho phép lưu lượng dựa trên trạng thái của kết nối đó.

1. **Thành thạo trong việc chia Subnet, cách tính Subnet Mask, cách chia Subnet bằng kỹ thuật VLSM, ….(nhiều câu hỏi liên quan phần này)**
    
    [https://youtube.com/playlist?list=PLTb4KXKc98BYRiUZlzgm4C5LEKyzbhEmL&si=whgj4SyEvnjzJGSU](https://youtube.com/playlist?list=PLTb4KXKc98BYRiUZlzgm4C5LEKyzbhEmL&si=whgj4SyEvnjzJGSU)
    
    - Note: Xem hết các video trên là chia subnet theo VLSM bao mượt