---
title: TẦNG APPLICATION
date: 2024-12-30
draft: false
tags:
  - firstblog
  - mangmaytinh
---
- **Các ứng dụng và các giao thức tương ứng thuộc tầng Application?**
    
    1. **HTTP/HTTPS (HyperText Transfer Protocol / HyperText Transfer Protocol Secure)**
        
        - **Ứng dụng:** Trình duyệt web (Chrome, Firefox, Safari)
        - **Mô tả:** Sử dụng để truyền tải tài liệu siêu văn bản (như trang web) trên World Wide Web. HTTPS là phiên bản bảo mật của HTTP
    2. **FTP (File Transfer Protocol)**
        
        - **Ứng dụng:** Các ứng dụng FTP client (FileZilla, WinSCP)
        - **Mô tả:** Sử dụng để truyền tải file giữa các máy tính trên mạng.
    3. **SMTP (Simple Mail Transfer Protocol)**
        
    
    - **Ứng dụng:** Ứng dụng gửi email (Microsoft Outlook, Mozilla Thunderbird)
    - **Mô tả:** Sử dụng để gửi email từ máy khách tới máy chủ hoặc giữa các máy chủ email.
    
    4. **POP3 (Post Office Protocol version 3)**
    
    - **Ứng dụng:** Ứng dụng nhận email (Outlook, Thunderbird)
    - **Mô tả:** Sử dụng để truy xuất email từ máy chủ tới máy khách.
    
    5. **IMAP (Internet Message Access Protocol)**
    
    - **Ứng dụng:** Ứng dụng nhận email (Gmail, Outlook, Thunderbird)
    - **Mô tả:** Sử dụng để truy cập email từ máy chủ, cho phép quản lý email trực tiếp trên máy chủ.
    
    6. **DNS (Domain Name System)**
    
    - **Ứng dụng:** Trình duyệt web, ứng dụng mạng khác
    - **Mô tả:** Sử dụng để phân giải tên miền thành địa chỉ IP.
    
    7. **DHCP (Dynamic Host Configuration Protocol)**
    
    - **Ứng dụng:** Hệ điều hành, các thiết bị mạng
    - **Mô tả:** Sử dụng để cấp phát địa chỉ IP động cho các thiết bị trong mạng.
    
    8. **Telnet**
    
    - **Ứng dụng:** Ứng dụng Telnet client
    - **Mô tả:** Sử dụng để truy cập từ xa vào một máy tính khác qua mạng.
    
    9. **SSH (Secure Shell)**
    
    - **Ứng dụng:** Ứng dụng SSH client (PuTTY, OpenSSH)
    - **Mô tả:** Sử dụng để truy cập từ xa an toàn vào một máy tính khác qua mạng.
    
    10. **RDP (Remote Desktop Protocol)**
    
    - **Ứng dụng:** Remote Desktop Client của Windows
    - **Mô tả:** Sử dụng để kết nối và điều khiển từ xa một máy tính chạy Windows.
- **Thời gian phân phối tệp tin (File Distribution) giữa client-server và P2P phụ thuộc vào:**
    
    - **Client-Server:**
        1. **Server Bandwidth**: Tổng dung lượng băng thông của server ảnh hưởng trực tiếp đến thời gian phân phối. Nếu băng thông của server bị giới hạn, việc phân phối sẽ chậm hơn, ngược lại nếu băng thông của server lớn đồng nghĩa với việc phân phối tập tin nhanh hơn
        2. **Number of Clients**: Số lượng clients yêu cầu tệp tin từ server càng nhiều thì thời gian phân phối càng lâu, vì server phải chia sẻ băng thông giữa các clients.
        3. **Network Latency**: Độ trễ mạng giữa server và các clients ảnh hưởng đến tốc độ truyền tải tệp tin.
        4. **Server Load**: Mức tải hiện tại của server, bao gồm cả các yêu cầu xử lý khác, có thể ảnh hưởng đến thời gian phân phối tệp tin.
    - **Peer-to-Peer (P2P):**
        1. **Peer Bandwidth**: Băng thông của từng peer (máy ngang hàng) trong mạng P2P ảnh hưởng đến tốc độ tải lên và tải xuống của tệp tin.
        2. **Number of Peers**: Số lượng peers tham gia vào việc chia sẻ tệp tin. Nhiều peers có thể giúp tăng tốc độ phân phối tệp tin vì tải được chia đều giữa các peers.
        3. **Availability of Pieces**: Tệp tin được chia thành nhiều phần nhỏ, và mỗi phần có thể được tải xuống từ các peers khác nhau. Tính sẵn có của các phần này ảnh hưởng đến thời gian phân phối.
        4. **Network Latency**: Độ trễ mạng giữa các peers ảnh hưởng đến tốc độ truyền tải tệp tin.
        5. **Peer Contribution**: Khả năng và mức độ chia sẻ của từng peer. Nếu nhiều peers chia sẻ tích cực, thời gian phân phối sẽ nhanh hơn.
    
    ⇒ Trong mô hình P2P, thời gian phân phối tệp tin thường có xu hướng giảm khi số lượng peers tăng, vì các peers có thể tải tệp tin từ nhiều nguồn cùng một lúc, trái ngược với mô hình client-server nơi server là điểm duy nhất cung cấp tệp tin.
    
- **Circuit switching vs Packet switching**
    
    - Switching: là quá trình Data được truyền đi từ thiết bị này sang thiết bị khác. Và Packet switching và Circuit switching là hai phương thức để các thiết bị trao đổi Data với nhau
    - Circuit switching: Thường được sử dụng bằng đường dây điện thoại, trước khi truyền data giữa hai thiết bị với nhau, chúng tạo ra một cái channel (Circuit) giữa hai đứa trước, rồi sau đó mới bắt đầu trao đổi data với nhau. Điều này đồng nghĩa với việc không có thiết bị nào có thể chui vô giữa làm Tuesday khi quá trình truyền data của hai đứa nó đang diễn ra cho tới khi quá trình truyền data này kết thúc. Circuit switching thường được sử dụng liên quan tới điện thoại, data sẽ được truyền từ sender tới reciever trên một đường đi độc nhất và data được truyền đi theo đúng trình tự nghĩa là thằng reciever sẽ không cần phải sắp xếp lại data mà nó nhận
    - Packet switching: Được sử dụng trên hệ thống internet toàn cầu, được sử dụng bởi router. Ngược lại với Circuit switching, nó không cần tạo ra các channel trước khi truyền data. Vậy nên khi một thiết bị truyền data, gói data này sẽ được chia nhỏ ra thành nhiều phần khác nhau và đi theo nhiều đường khác nhau để tới điểm đích. Vì mỗi đứa đi một hướng nên khi data đến thiết bị nhận, thiết bị này sẽ thực hiện sắp xếp lại data nó nhận được theo đúng thứ tự
    - So sánh các điểm khác nhau chính giữa hai thằng:
    
    **Circuit switching**
    
    - Chất lượng và độ ổn định tốt hơn nên thường được ứng dụng trong việc gọi điện thoại
    
    **Packet switching**
    
    - Vẫn có thể ứng dụng vào voice call như VOIP (Voice over IP), nhưng không bằng Circuit switching
        
    - Flexible hơn vì bên cạnh truyền voice còn truyền được cả video, web data, mail
        
    - **Số port (port number) trên máy chạy các dịch vụ ứng dụng (FTP, DNS, SMTP, HTTP, ….)**
        
        1. **FTP (File Transfer Protocol)**
        
        - Port: 21 (Control)
        - Port: 20 (Data Transfer)
        
        2. **SMTP (Simple Mail Transfer Protocol)**
        
        - Port: 25
        
        3. **HTTP (HyperText Transfer Protocol)**
        
        - Port: 80
        
        4. **HTTPS (HyperText Transfer Protocol Secure)**
        
        - Port: 443
        
        5. **POP3 (Post Office Protocol version 3)**
        
        - Port: 110
        
        6. **IMAP (Internet Message Access Protocol)**
        
        - Port: 143
        
        7. **DNS (Domain Name System)**
        
        - Port: 53
        
        8. **Telnet**
        
        - Port: 23
        
        9. **SSH (Secure Shell)**
        
        - Port: 22
        
        10. **TFTP (Trivial File Transfer Protocol)**
        
        - Port: 69
        
        11. **LDAP (Lightweight Directory Access Protocol)**
        
        - Port: 389
        
        12. **NTP (Network Time Protocol)**
        
        - Port: 123
        
        13. **SFTP (SSH File Transfer Protocol)**
        
        - Port: 22 (Uses SSH)
        
        14. **FTPS (FTP Secure)**
        
        - Port: 990 (Control)
        - Port: 989 (Data Transfer)
    - **Cấu trúc gói tin TCP/UDP (TCP/UDP segment format): độ dài của các trường (fields) trong cấu trúc gói tin Ipv6 và Ipv4 (VD: Source port #, Destination port #, length, checksum, header, ….)**
        
    - **Cấu trúc gói tin TCP**
        
        1. **Source Port**: 16 bits
        2. **Destination Port**: 16 bits
        3. **Sequence Number**: 32 bits
        4. **Acknowledgment Number**: 32 bits
        5. **Data Offset**: 4 bits
        6. **Flags**: 9 bits
        7. **Window Size**: 16 bits
        8. **Checksum**: 16 bits
        9. **Urgent Pointer**: 16 bits
        10. **Options and Padding**: variable length
    - **Cấu trúc gói tin UDP**
        
        1. **Source Port**: 16 bits
        2. **Destination Port**: 16 bits
        3. **Length**: 16 bits
        4. **Checksum**: 16 bits
    - **Cấu trúc gói tin IPv4**
        
        1. **Version**: 4 bits
        2. **IHL**: 4 bits
        3. **Type of Service**: 8 bits
        4. **Total Length**: 16 bits
        5. **Identification**: 16 bits
        6. **Flags and Fragment Offset**: 16 bits
        7. **Time to Live**: 8 bits
        8. **Protocol**: 8 bits
        9. **Header Checksum**: 16 bits
        10. **Source Address**: 32 bits
        11. **Destination Address**: 32 bits
        12. **Options and Padding**: variable length
    - **Cấu trúc gói tin IPv6**
        
        1. **Version**: 4 bits
        2. **Traffic Class**: 8 bits
        3. **Flow Label**: 20 bits
        4. **Payload Length**: 16 bits
        5. **Next Header**: 8 bits
        6. **Hop Limit**: 8 bits
        7. **Source Address**: 128 bits
        8. **Destination Address**: 128 bits