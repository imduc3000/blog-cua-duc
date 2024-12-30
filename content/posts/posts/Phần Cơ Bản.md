---
title: PHẦN CƠ BẢN
date: 2024-12-30
draft: false
tags:
  - firstblog
  - mangmaytinh
---
1. **Các giao thức mạng và cách thức hoạt động của chúng**
    
    - HTTP và HTTPs
        
        - Viết tắt của Hypertext Transfer protocol và Secure Hypertext Transfer protocol
        - Đây là giao thức giúp ta truy cập vào các Website
        - Ngày nay thường sử dụng HTTPs nhiều hơn vì tính bảo mật cao hơn (thông tin truyền từ client đến server thông qua public internet sẽ được mã hóa, thay vì hiển thị ở dạng nguyên bản như HTTP điều này giúp tránh các rủi ro bị hack)
        - HTTPs sử dụng hai giao thức mã hóa phổ biến là: SSL (Secure Sockets Layer) và TLS (Transport Layer Security) → Mới nhất hiện nay
            - SSL
                1. Viết tắt của Secure Sockets Layer
                2. Là một giao thức bảo mật của mạng
                3. Cách thức hoạt động: Khi một trình duyệt web kết nối đến một website có dùng SSL, trình duyệt sẽ yêu cầu trang web chứng minh độ đáng tin cậy, khi này website sẽ gửi cho trình duyệt một certificate SSL chứng minh độ an toàn của bản thân, sau đó dữ liệu mới được truyền đi
        - Cách thức hoạt động của HTTP: Khi người dùng nhập một trang web trên trình duyệt hoặc nhấn vào một link, trình duyệt sẽ tạo ra một yêu cầu HTTP (HTTP request) - yêu cầu này bao gồm một dòng yêu cầu (request line), các tiêu đề yêu cầu (request header) và có thể là một thân yêu cầu (request body); Máy chủ web nhận được một yêu cầu HTTP xử lý nó và gửi lại một phản hồi HTTP (HTTP responds), phản hồi này bao gồm một dòng trạng thái (status line), các tiêu đề phản hồi (response body) chứa các trang như HTML, hình ảnh, tài liệu,…; Cuối cùng trình duyệt nhận được phản hồi từ máy chủ và hiện thị nội dung lên cho người dùng
        - Cách thức hoạt động của HTTPs: Giống với HTTP, nhưng đầu tiên trình duyệt sẽ tạo một kết nối bảo mật với máy chủ web thông qua SSL/TLS, Sau đó trình duyệt và máy chủ sẽ thực hiện một quá trình “SSL/TLS handshake”: Máy Client sẽ gửi một request yêu cầu chứng minh độ đáng tin cậy về Sever cần truy cập, sever gửi lại một cái certificate để chứng minh độ đáng tin cậy, sau đó quá trình truyền dữ liệu mới bắt đầu được diễn ra
    - Telnet
        
        - Viết tắt của Teletype Network
        - Là một hình thức giúp ta điều khiển các server, Switch, router từ xa thông qua Terminal
        - Vì không có giao diện trực quan nên tốc độ của Telnet rất nhanh
        - Tính bảo mật của Telnet không cao do thông tin truyền đi không được mã hóa mà hiển thị hoàn toàn dưới dạng Plain Text
        - Cách thức hoạt động: Đầu tiên người dùng sử dụng một ứng dụng Telnet để kết nối với máy chủ Telnet, sau đó người dùng sẽ nhập tên đăng nhập và mật khẩu, cuối cùng một cửa số như terminal sẽ hiện ra giúp người dùng tương tác với máy chủ từ xa như thể đang trực tiếp điều khiển máy chủ đó
    - SSH
        
        - Viết tắt của Secure Shell
        - Là Telnet nhưng bảo mật hơn vì thông tin truyền đi được mã hóa
        - Cách thức hoạt động: Giống với Telnet, khác ở chỗ có thêm bước: SSH sẽ thiết lập một kênh mã hoá giữa máy khách và máy chủ trước khi người dùng đăng nhập, để đảm bảo tính bảo mật
    - VLAN
        
        - Viết tắt của Virtual LAN
        - Tạo ra các mạng con ảo trên một mạng lớn bằng Switch: Chia một mạng Vật lý lớn thành các mạng con nhỏ hơn mà không cần thêm phần cứng mới
        - Mục tiêu của VLAN là: Cải thiện tính bảo mật, điều khiển giao thông mạng, Đơn giản hoá một mạng
        
        ```python
        +----------------------------------------+
        |               Switch                   |
        | +---------------------+  +------------+|
        | | Port 1   | VLAN 10  |  | VLAN 20    ||
        | | Port 2   | VLAN 10  |  +------------+|
        | | Port 3   | VLAN 20  |                |
        | | Port 4   | VLAN 20  |                |
        | +---------------------+                |
        |                                        |
        |           VLAN Trunk (Ports 1-4)       |
        +----------------------------------------+
                        |
                        |
                        v
        +----------------------------------------+
        |                Router                  |
        | +---------------------+  +------------+|
        | | Interface 1| VLAN 10 |  | VLAN 20    ||
        | | Interface 2| VLAN 20 |  +------------+|
        | +---------------------+                |
        |                                        |
        +----------------------------------------+
                        |
                        |
                        v
        +-------------------------+  +-------------------------+
        |      VLAN 10 Network    |  |      VLAN 20 Network    |
        |  +-------------------+  |  |  +-------------------+  |
        |  | Computer A        |  |  |  | Computer C        |  |
        |  | (IP: 192.168.10.2)|  |  |  | (IP: 192.168.20.2)|  |
        |  +-------------------+  |  |  +-------------------+  |
        |  +-------------------+  |  |  +-------------------+  |
        |  | Computer B        |  |  |  | Computer D        |  |
        |  | (IP: 192.168.10.3)|  |  |  | (IP: 192.168.20.3)|  |
        |  +-------------------+  |  |  +-------------------+  |
        +-------------------------+  +-------------------------+
        ```
        
        - Giải thích về VLAN:
            - Giả sử có ba loại màu máy tính đại diện cho ba phòng ban khác nhau trong một công ty, đặt trường hợp nếu kết nối tất cả các máy tính này vào cùng một switch, thì các phòng ban khác sẽ có thể thấy và biết được những gì đã và đang xảy ra ở các phòng ban khác. Điều này là vô cùng bất tiện
            - Vậy nên Switch có kết hợp VLAN ra đời: Vẫn là switch nơi các máy tính kết nối vào nhau, nhưng giờ đây, VLAN giúp tạo ra các mạng ảo và các phòng ban khác nhau giờ đây sẽ được sử dụng các đường truyền khác nhau tuy vẫn được cắm vào cùng một switch.
        - Giải thích về hình ảnh minh hoạ:
            - Có tổng cộng 4 cổng trên một Switch lần lượt là 1,2,3 và 4; Với cổng 1 và 2 thuộc VLAN 10 còn cổng 3 và 4 thuộc VLAN 20
            - Máy tính A và B ở cùng phòng, máy tính C và D ở cùng phòng ban nhưng A&B khác phòng ban với C&D. Vậy nên để dữ liệu của các phòng ban là bảo mật và chỉ về thuộc về phòng ban đó. Ta thực hiện kết nối máy tính A và B vào port 1 và port 2 để hai đứa nó cùng một VLAN 10. Và tương tự với máy tính C và D ta thực hiện kết nối vào port 3 và port 4 để hai đứa nó cùng một VLAN 20. Từ đó, hai thằng A&B không dính dáng gì tới C&D
    - VPN
        
        - Viết tắt của Virtual Private Network
        - Khi ta truy cập vào các website, các ISP sẽ biết được ta đã truy cập vào những trang nào vào thời điểm nào và có thể bán những thông tin này cho các nhà quảng cáo hoặc chính phủ, VPN ra đời để tạo thêm một lớp bảo mật nhằm ngăn chặn chuyện này
        - VPN giúp ta chuyển vùng sang nước ngoài để truy cập vào các nội dung bị giới hạn quốc gia (do VPN thay đổi địa chỉ IP của ta)
        - VPN giấu địa chỉ IP thật của ta khi lướt Web: IP của ta trước khi đến với ISP sẽ được đi qua server VPN trước sau đó ta sẽ được server VPN gán cho một địa chỉ IP khác của server rồi mới bắt đầu truy cập vào Internet
        - VPN giúp ngăn chặn các cuộc tấn công Man-in-the-middle
        - Tạo ra mạng riêng bảo mật để người work from home có thể trao đổi và tải file từ công ty một cách bảo mật: Chỉ những người có VPN được các tổ chức, công ty cung cấp mới có thể truy cập được vào các tệp file của các công ty, tổ chức này
    - Firewall
        
        - Firewall của phần mền giống với firewall vật lý ở các toà nhà: Khi có hoả hoạn xảy ra, firewall giữ đám cháy lại và ngăn nó cháy lan ra các nơi khác trong toà nhà. Tương tự với Firewall phần mềm, nó ngăn chặn các thông tin độc hại, xâm nhập và lan toả gây thiệt hại nặng nệ đến cả một hệ thống.
            
        - Firewall được thiết lập bởi admin, quy định rằng các IP address nào có thể truy cập vào và ra khi này chỉ những IP được cấp quyền mới có khả năng đi vào bên trong, bên cạnh quy định địa chỉ IP, admin còn có thể đặt ra các quy định về Domain name, Port, Protocols, phần mền, tên tệp,…
            
        - Có hai loại firewall là: Host-based Firewall (Firewall dạng phần mềm, Chỉ bảo vệ máy tính) và Network-based Firewall (Firewall dạng phần cứng và phần mềm, Bảo vệ toàn bộ hệ thống mạng, có thể là một dạng modem vật lý rời hoặc có thể ở dạng tích hợp sẵn trong router wifi) - Thông thường, để nâng cao khả năng bảo vệ, người ta sẽ sử dụng cả hai loại firewall này cùng nhau
            
            ```python
            +------------------------------------------+
            |                                          |
            |           Internet                       |
            |                                          |
            +------------------------------------------+
                             |
                             |
                             v
            +------------------------------------------+
            |                Firewall                  |
            |  +------------------------------------+  |
            |  |                                    |  |
            |  |  Allow:                            |  |
            |  |  - HTTP (Port 80)                  |  |
            |  |  - HTTPS (Port 443)                |  |
            |  |  - SMTP (Port 25)                  |  | 
            |  |                                    |  |
            |  |  Deny:                             |  |
            |  |  - All other traffic               |  |
            |  |                                    |  |
            |  +------------------------------------+  |
            +------------------------------------------+
                             |
                             |
                             v
            +------------------------------------------+
            |                                          |
            |             Internal Network             |
            |                                          |
            |  +---------+    +---------+    +---------+ |
            |  | Server  |    | Server  |    | Server  | | 
            |  |   A     |    |   B     |    |   C     | |
            |  +---------+    +---------+    +---------+ |
            |                                          |
            +------------------------------------------+
            ```
            
    - Giải thích hình ảnh minh hoạ: Dữ liệu đi từ Internet vào nhà ta khi gặp firewall sẽ bị dịnh lại và xét duyệt, trong trường hợp này chỉ cho phép các data từ HTTP, HTTPs, SMTP đi qua. Và cấm tất cả các data từ nơi khác
        
    - DHCP
        
        - Viết tắt của Dynamic host configuration protocol
        - Trước đây phải tự thêm IP thủ công cho từng máy tính bên cạnh đó cần phải thêm cả Subnet Mask, Default Gateway, DNS server,… nếu có nhiều máy tính việc thêm thủ công này là rất mất thời gian (Cách thêm IP thủ công gọi là Static IP address)
        - Thêm IP bằng DHCP gọi là Dynamic IP
        - Cách thức hoạt động: Máy tínhh request một IP address, DHCP server nhận được yêu cầu và cấp IP cho máy gửi yêu cầu, nhưng DHCP server chỉ lease IP address chứ không cho luôn, vì khi cho luôn đặt trường hợp một máy tính bị tách khỏi DHCP server, IP mà nó mang cũng sẽ bị mang đi theo, thành ra DHCP server sẽ bị mất IP đó. Vậy nên đôi lúc, máy tính sẽ phải gửi một thông báo đến DHCP server báo rằng nó vẫn đang tồn tại để DHCP server tiếp tục cung cấp địa chỉ IP cho nó
    - DNS
        
        - Viết tắt của Domain Name System
        - Công dụng: Dịch tên miền thành địa chỉ IP
        - Cách thức hoạt động: Khi bạn nhập môn tên miền vào thanh search trên trình duyệt, khi đó hệ điều hành hoặc trình duyệt bạn đang dùng sẽ tìm kiếm địa chỉ IP của tên miền bạn vừa nhập vào, nếu Browser hoặc hệ điều hành không tìm thấy, nó sẽ gửi yêu cầu của bạn tới một nơi gọi là Resolver server hay còn gọi là ISP (nhà cung cấp mạng: VNPT, FPT,…). Khi yêu cầu đến đây, các ISP sẽ kiểm tra bộ nhớ để tìm ra địa chỉ IP của tên miền ta đang tìm kiếm. Nếu vẫn không tìm thấy, nó tiếp tục chuyển yêu cầu của ta tới root server đây là gốc rễ của DNS server, nhưng thay vì nó chứa địa chỉ IP của các tên miền, root server chỉ đường cho ta đến nơi biết thứ ta cần tìm và thông thường nó sẽ chuyển hướng ta đến TLD hay top level domain server giành cho các tên miền kết thúc là .com. TLD lưu giữ những domain name phổ biến thường kết thúc bằng .com .net .org. Nhưng nếu nó vẫn không biết gì về thông tin mà người dùng yêu cầu, nó sẽ chuyển hướng người dùng đến trùm cuối: authoritative name server và sẽ phản hồi lại máy tính địa chỉ IP của domain name người dùng cần tìm, khi đó máy tính sẽ biết được nó cần phải đến đâu, máy tính sau đó sẽ lưu lại địa chỉ IP và domain name này vào bộ nhớ của nó cho những lần truy cập tiếp theo để đỡ mất thời gian
    - FTP
        
        - Viết tắt của File Transfer Protocol
        - Hoạt động dựa trên nguyên lý Client-Sever: Client đăng nhập vào nhập tên và mật khẩu, truy cập vào sever FTP thực hiện các tác vụ như upload, download file,…
        - FTP không bảo mật vì các thông tin bao gồm tên đăng nhập, mật khẩu đều được truyền đi dưới dạng plain text, khi có các cuộc tấn công mạng dữ liệu rất dễ bị đánh cắp ⇒ Vậy nên người ta tạo ra SFTP (Secure File Transfer Protocol), về cơ bản mọi thứ đều giống với FTP nhưng giờ đây quá trình trao đổi dữ liệu giữa client và server sẽ được bảo mật bằng Secure Shell, vậy nên data khi truyền đi sẽ không còn ở dạng plain text, giờ đây mọi data truyền đi đều được mã hoá
        - FTP và SFTP sử dụng giao thức TCP để truyền file điều này đồng nghĩa với việc đảm bảo file sẽ đến nơi
            - TCP
                1. Viết tắt của Transmission control protocol
                2. Là một giao thức để các máy tính có thể giao tiếp và trao đổi thông tin với nhau (giống như một ngôn ngữ chung giữa các máy tính để chúng có thể hiểu thằng kia đang nói gì, cần gì và làm gì,…)
                3. TCP đảm bảo việc dữ liệu được truyền đi đầy đủ và đến nơi đến chốn một cách lành lặn, không thiếu thằng nào, không mất bất cứ cái gì trong quá trình truyền đi. Nếu có lỡ mất, TCP sẽ truyền lại vì TCP LIÊM, không ăn bớt của ai cái gì cả.
                4. Thường được ứng dụng trong việc tải FIle vì ta cần một file với đầy đủ thông tin chứ không phải một file chỗ có chỗ không, chỗ này thiếu cái này chỗ kia thiếu cái nọ
                5. Trước khi hai máy giao tiếp được với nhau, hai thằng phải tạo ra một cái session với nhau, và sau đó là verify lẫn nhau bằng cách sử dụng three-way handshake: Máy tính 1 gửi một tệp tin SYN đến máy tính 2, máy tính 2 nhận được và phản hồi bằng một tệp SYN ACK báo với máy 1 là tao đã nhận được tệp tin của mày rồi và cuối cùng máy tính 1 gửi một tệp tin ACK RECIEVED đến máy 2 và việc truyền dữ liệu giữa hai thằng mới chính thức được bắt đầu
            - UDP
                1. Viết tắt của User Datagram Protocol
                2. Đặc điểm của UDP: Khác với TCP, UDP nổi bật với tốc độ của nó vì vậy thường được ứng dụng trong truyền tải các video livestream trực tiếp, nhạc, trò chơi,… UDP truyền dữ liệu dưới dạng datagram nó không đảm bảo tính đúng thứ tự khi truyền đi cũng như không đảm bảo việc tập tin có đến được địa điểm hay không, vì vậy truyền tải bằng UDP là rất nhanh. Ngoài ra UDP cũng không được mã hóa, vì vậy có rất nhiều nguy cơ bảo mật có thể xảy ra
        - Và cuối cùng là TFTP (Trivial File Transfer Protocol): Không dùng để chuyển file qua lại trên internet, thường dùng để chuyển file trong LAN, dùng UDP để chuyển file mà không secure vì chỉ dùng trong LAN
    - SMTP
        
        - Viết tắt của Simple Mail Transfer Protocol
        - Cách thức hoạt động: Khi ta gửi mail cho người khác sử dụng các nền tảng gửi mail như GMAIL của Google, mail của chúng ta sẽ đến sever SMTP sau đó nó sẽ được chuyển tiếp đến sever SMTP của người nhận, tại đây nó được lưu trữ lại vào hộp thư của người nhận và chờ người nhận truy cập
        - Hai giao thức liên quan đến SMTP là IMAP và POP3 đây là hai giao thức dùng để truy cập và quản lý email từ máy chủ email
        - IMAP: Không cần tải mail về máy tính cục bộ để chỉnh sửa, quản lý, tự động đồng bộ hóa trên sever nên có thể sử dụng trên nhiều thiết bị (Cần được cung cấp internet); cho phép tổ chức email vào các thư mục khác nhau trên máy tính
        - POP3: Tải tất cả các mail về máy tính cục bộ để duyệt và quản lý làm tiêu tốn dung lượng dùng để lưu trữ, Không tự động đông bộ hóa trên server nên không thể sử dụng nhiều thiết bị để truy cập ở nhiều địa điểm khác nhau. Thông thường khi tải về, server sẽ tự động xóa các mail đã tải trên server nếu không được lập trình để giữ lại, không cho phép tổ chức email vào các thư mục
    - ARP
        
        - Viết tắt của Address Resolution Protocol
        - Lưu địa chỉ MAC của một thiết bị dựa trên địa chỉ IP của nó (Lần đầu tiên, nó sẽ Broadcast ra toàn bộ thiết bị để biết được IP address nó cần tìm là của địa chỉ MAC nào, sau khi biết được, nó thực hiện việc lưu địa chỉ MAC nó vừa tìm được song song với địa chỉ IP ban đầu để sử dụng cho những lần tiếp theo mà không cần phải broadcast lại lần nữa)
        - Nguyên lý hoạt động
            1. **Thiết bị cần gửi dữ liệu**: Khi một thiết bị cần gửi dữ liệu tới một địa chỉ IP cụ thể nhưng không biết địa chỉ MAC của thiết bị đích.
            2. **Gửi yêu cầu ARP**: Thiết bị gửi một gói tin yêu cầu ARP lên mạng, hỏi rằng “Địa chỉ MAC của địa chỉ IP này là gì?”
            3. **Phản hồi ARP**: Thiết bị sở hữu địa chỉ IP được yêu cầu sẽ trả lời với địa chỉ MAC của nó.
            4. **Bảng ARP**: Địa chỉ MAC được lưu trữ trong bảng ARP của thiết bị gửi để sử dụng cho các giao dịch trong tương lai.
        - Có hai loại ARP là: Dynamic (Tự động Broadcast để tìm kiếm và ghi lại); Static (Nhập thủ công)
    - RARP
        
        - Viết tắt của Reverses Address Resolution Protocol
        - Nguyên lý hoạt động
            1. **Thiết bị cần địa chỉ IP**: Khi một thiết bị khởi động và cần một địa chỉ IP nhưng chỉ biết địa chỉ MAC của nó.
            2. **Gửi yêu cầu RARP**: Thiết bị sẽ gửi một yêu cầu RARP lên mạng, hỏi rằng “Địa chỉ IP của tôi là gì?” dựa trên địa chỉ MAC của nó.
            3. **RARP Server**: Một máy chủ RARP trên mạng nhận yêu cầu và tra cứu bảng ánh xạ địa chỉ MAC tới địa chỉ IP để xác định địa chỉ IP tương ứng.
            4. **Phản hồi**: Máy chủ RARP gửi phản hồi trở lại thiết bị với địa chỉ IP tương ứng.
    - Half Duplex
        
        - Cơ chế P2P system: Kết nối hai máy tính lại với nhau bằng một dây ethernet. Một và chỉ một thiết bị có thể truyền tin đi tại một thời điểm, tức nếu máy tính 1 đang truyền dữ liệu thì máy tính 2 phải đợi máy tính 1 truyền xong thì máy tính 2 mới được phép truyền dữ liệu (Chỉ có thể truyền dữ liệu đi 1 chiều duy nhất)
        - Hoạt động giống bộ đàm: Chỉ có một người nhấn bộ đàm và nói, tất cả những người còn lại không được nhấn bộ đàm và nói. Nếu nhấn cùng lúc. sẽ bị trùng đàm và không ai nghe ai nữa cả
        - Dễ bị xảy ra Collision nên cần đến CSMA/CD để giảm thiểu và khắc phục khi có va chạm xảy ra
        - Hub dùng Half Duplex
            - CSMA/CD
                
                1. Viết tắt của Carrier Sense Multiple Access with collision detection
                2. Sử dụng trong mạng có dây
                3. Công nghệ này đã ra đời rất lâu về trước vào thời điểm người ta dùng Coaxial Cable và Twisted pair
                
                - Nguyên lý hoạt động:
                    1. Đầu tiên các máy tính trong một Network sẽ kiểm tra xem có máy tính nào truyền data đi không, nếu không có nó mới bắt đầu truyền data của bản thân đi. Nhưng nếu cả hai máy tính đều thấy không có máy tính nào khác đang truyền data và hai máy tính này truyền data đi cùng một lúc, khi này va chạm sẽ xảy ra
                    2. Khi va chạm xảy ra, hai máy tính tạo ra va chạm sẽ phát một tín hiệu tới tất cả máy tính còn lại trong Network báo rằng hai đứa tao mới va chạm nhau (jamming signal) và hai máy tính sẽ đợi một khoảng thời gian ngẫu nhiên (Mỗi máy đợi một khoảng thời gian random khác nhau) và bắt đầu quá trình truyền data lại
            - CSMA/CA
                
                1. Viết tắt của Carrier Sense Multiple Access with Collision Avoidance
                2. Sử dụng trong mạng không dây
                3. Nguyên lý hoạt động:
                    - Các máy tính kết nối với mạng không dây thường không nghe và không biết được có va chạm xảy ra hay không, nên tất cả các máy tính thường cố gắng phòng tránh va chạm nhiều nhất có thể bằng cách: khi muốn truyền dữ liệu đi, đầu tiên máy tính sẽ cố gắng lắng nghe xem có thiết bị nào đang truyền dữ liệu đi không, nếu có nó sẽ đợi một đến khi thiết bị đó truyền xong và không còn nhận thấy sự truyền dữ liệu của bất kì thiết bị nào khác. Khi này nó sẽ đợi một khoảng thời gian random và rồi truyền dữ liệu đi → Khi điểm đến nhận được dữ liệu từ máy tính, nó sẽ gửi một đoạn tin confirm đã nhận được dữ liệu, nếu máy tính không nhận được đoạn tin này đồng nghĩa với việc điểm đến chưa nhận được data và máy tính khi này sẽ tiến hành gửi lại data
                    - Protocol dùng trong CSMA/CA: RTS và CTS
                        - Khi một thiết bị trong một mạng muốn truyền data đi, nó sẽ gửi một yêu cầu RTS (Ready to send) đến Wireless Access Point, khi WAP nhận được yêu cầu này, nó sẽ dừng tất cả những đường truyền khác lại và gửi đến máy tính một tín hiệu CTS (Clear to send), khi này máy tính bắt đầu thực hiện quá trình truyền data
    - Full Duplex
        
        - Ngược lại với Half Duplex: Hai thiết bị có thể giao tiếp qua lại cùng một lúc ở hai chiều khác nhau
        - Ví dụ thực tế: Điện thoại bàn (Cả hai đều có thể nghe và nói cùng một lúc)
    - Token Ring
        
        - Được sản xuất bởi IBM vào những năm 1980 cho mạng LAN
        - Mặc dù kết cục là dây vật lý đã thắng cuộc trong việc lựa chọn cái gì sẽ được dùng để kết nối trong LAN nhưng vẫn nên biết Token Ring
        - Sử dụng Ring Topology: giống như một chiếc Taxi chạy trong một vòng tròn Network, khi gói hàng đã đến được đúng người nhận (B), B sẽ thực hiện copy gói hàng và gắn một lá cờ lên gói hàng báo rằng đã nhận được tệp tin, sau đó gói hàng lại được chuyển ngược về A, A sẽ remove tin nhắn này từ B cũng như gói hàng nó đang mang, trả lại một chiếc Taxi trống như ban đầu
        - Ưu điểm so với Ethernet: Không gây ra va chạm
        - Nhược điểm: Mắc vãi lồn (IBM tính phí mắc gấp 5-6 lần so với Ethernet thông thường)
        
        ```python
             +------+      +------+      +------+      +------+
             | Node |      | Node |      | Node |      | Node |
             |  A   |----->|  B   |----->|  C   |----->|  D   |
             +------+      +------+      +------+      +------+
                 ^                                        |
                 |                                        v
                 +----------------------------------------+
        ```
        
    - ICMP
        
        - ICMP (Internet Control Message Protocol) là một giao thức trong bộ giao thức Internet được sử dụng để gửi các thông báo lỗi và thông tin hoạt động trong các mạng IP
2. **Các khái niệm/định nghĩa về end systems, end devices, hosts, network edge, network core, ….**
    
    - End system
        
        - Dịch ra là hệ thống đầu cuối, là các thiết bị ở rìa của mạng lưới nơi các giao tiếp mạng bắt đầu hoặc kết thúc
        - End system có thể là máy tính cá nhân, server, thiết bị di động, nói chung là bất cứ thiết bị nào có khả năng kết nối và trao đổi thông tin thông qua internet
    - End devices
        
        - Thiết bị đầu cuối, là phần cứng mà user sử dụng để truy cập vào internet
        - Bao gồm: Máy tính để bàn và máy tính xách tay, Điện thoại thông minh và máy tính bảng, Máy in và máy quét, Camera an ninh và thiết bị IoT
    - Host
        
        - **Host** là bất kỳ thiết bị nào có khả năng kết nối vào mạng và có địa chỉ IP. Hosts có thể là bất kỳ thiết bị nào đóng vai trò là nguồn hoặc đích của dữ liệu trong một mạng: Máy tính cá nhân, Máy tính xách tay, Điện thoại thông minh, Máy tính bảng, Máy chủ (Server),Thiết bị lưu trữ mạng (NAS - Network Attached Storage), …
        - Sự khác nhau của End system, End devices và Host theo tao vì Chat GPT giải thích rất loằng ngoằng là: Host → End system → End devices; Host là thằng lớn nhất chứa cả hai thằng còn lại, chứa nhiều thiết bị hơn rồi tới End system và sau cùng là End devices
    - Network Edge
        
        - Là nơi mà các hệ thống đầu cuối (End system) và thiết bị đầu (End devices) cuối kết nối vào mạng. Đây là điểm bắt đầu và kết thúc của các kết nối mạng. Các thiết bị tại rìa mạng thường bao gồm:
            - Router: Kết nối mạng nội bộ với mạng bên ngoài (internet).
            - Switch: Kết nối các thiết bị đầu cuối trong cùng một mạng nội bộ.
            - Access Point: Cung cấp kết nối không dây cho các thiết bị đầu cuối.
    - Network Core
        
        - Là trung tâm của mạng lưới, nơi các thiết bị mạng và đường truyền kết nối với nhau để truyền tải dữ liệu giữa các phần khác nhau của mạng. Lõi mạng chịu trách nhiệm cho việc định tuyến và truyền tải dữ liệu một cách hiệu quả. Các thiết bị tại lõi mạng thường bao gồm:
            - Core Router: Router ở cấp độ cao, chịu trách nhiệm định tuyến lưu lượng giữa các mạng lớn.
            - Core Switch: Switch với dung lượng và hiệu suất cao, được sử dụng trong các trung tâm dữ liệu và các mạng lưới lớn.
3. **Các tầng và nguyên lý, chức năng hoạt động của các tầng trong mô hình mạng OSI, TCP/IP, IP Stack**
    
    - Mô hình mạng OSI (mô hình 7 tầng)
        
        - Được phát triển bởi Tổ chức Tiêu chuẩn hóa Quốc tế (ISO), đây là mô hình lý thuyết tức là thực tế trong đời sống ngày nay người ta đếch dùng cái này, người ta dùng mô hình 4 tầng TCP/IP. Nhưng khi nhắc về lý thuyết, khi nhắc về học thuật người ta lại ca ngợi và chỉ nhắc đến OSI - đúng đời
        
        **1. Tầng Vật lý (Physical Layer)**
        
        - **Chức năng:**
            
            - Truyền dữ liệu dạng bit qua môi trường vật lý.
            - Quản lý các thiết bị truyền thông như cáp, tín hiệu điện và ánh sáng.
            
            ⇒ Truyền các bit dữ liệu qua các phương tiện truyền thông vật lý, tầng vật lý nên cái gì liên quan tới vật lý cầm nắm được thì dính tới tầng này
            
        - **Những thứ có liên quan tới tầng này:**
            
            - Cáp Ethernet, cáp quang, điện, tia điện,….
        
        **2. Tầng Liên kết Dữ liệu (Data Link Layer)**
        
        - **Chức năng:**
            
            - Điều khiển truy cập vào môi trường truyền thông (IP)
            - Định nghĩa cách thức các bit được tổ chức thành các khung dữ liệu (frames)
            
            ⇒ Đóng gói dữ liệu vào khung (frames) và cung cấp truyền dữ liệu không lỗi giữa các thiết bị liền kề
            
        - **Những thứ có liên quan tới tầng này:**
            
            - Ethernet, P2P (Point-to-Point Protocol), địa chỉ MAC (địa chỉ Switch dùng)
        
        **3. Tầng Mạng (Network Layer)**
        
        - **Chức năng:**
            
            - Định tuyến và chuyển tiếp các gói tin (packets) giữa các mạng khác nhau.
            - Quản lý địa chỉ IP và các chính sách định tuyến.
            - Chuyển tiếp các gói tin đến đúng địa chỉ đích.
            
            ⇒ Định tuyến các gói tin và quản lý địa chỉ IP.
            
        - **Những thứ có liên quan tới tầng này:**
            
            - IP (Internet Protocol), router, địa chỉ IP.
        
        **4. Tầng Giao Vận (Transport Layer)**
        
        - **Chức năng:**
            
            - Đảm bảo truyền dữ liệu toàn vẹn và đáng tin cậy.
            - Quản lý việc phân chia dữ liệu thành các phân đoạn (segments) và tái tổ hợp chúng.
            - Cung cấp dịch vụ kiểm soát lỗi, kiểm soát luồng và khôi phục lỗi.
            
            ⇒ Đảm bảo truyền dữ liệu toàn vẹn và đáng tin cậy, quản lý kiểm soát lỗi và phân chia dữ liệu.
            
        - **Những thứ có liên quan tới tầng này:**
            
            - TCP (Transmission Control Protocol), UDP (User Datagram Protocol), cổng (ports).
        
        **5. Tầng Phiên (Session Layer)**
        
        - **Chức năng:**
            
            - Quản lý các phiên giao tiếp giữa các ứng dụng.
            - Thiết lập, duy trì và kết thúc các phiên giao tiếp.
            
            ⇒ Quản lý các phiên giao tiếp giữa các ứng dụng.
            
        - **Những thứ có liên quan tới tầng này:**
            
            - Giao thức điều khiển phiên NetBIOS, RPC (Remote Procedure Call).
        
        **6. Tầng Trình bày (Presentation Layer)**
        
        - **Chức năng:**
            
            - Chuyển đổi dữ liệu giữa định dạng mà ứng dụng sử dụng và định dạng chuẩn để truyền trên mạng.
            - Mã hóa và giải mã dữ liệu để bảo mật.
            - Nén và giải nén dữ liệu để tối ưu băng thông.
            
            ⇒ Chuyển đổi, mã hóa, giải mã, nén và giải nén dữ liệu.
            
        - **Những thứ có liên quan tới tầng này:**
            
            - SSL/TLS (Secure Sockets Layer/Transport Layer Security), định dạng dữ liệu như JPEG, GIF, HTML.
        
        **7. Tầng Ứng dụng (Application Layer)**
        
        - **Chức năng:**
            
            - Tương tác trực tiếp với phần mềm ứng dụng để thực hiện các chức năng giao tiếp.
            - Cung cấp các giao thức cho email, truyền tệp, và truy cập web…
            
            ⇒ Cung cấp các dịch vụ mạng trực tiếp cho các ứng dụng người dùng.
            
        - **Những thứ có liên quan tới tầng này:**
            
            - HTTP (Hypertext Transfer Protocol), FTP (File Transfer Protocol), SMTP (Simple Mail Transfer Protocol), DNS (Domain Name System).
        
        ```python
          +---------------------------+
          |     Application Layer     |  - Tầng ứng dụng
          +---------------------------+
          |     Presentation Layer    |  - Tầng trình bày
          +---------------------------+
          |        Session Layer      |  - Tầng phiên
          +---------------------------+
          |       Transport Layer     |  - Tầng vận chuyển
          +---------------------------+
          |        Network Layer      |  - Tầng mạng
          +---------------------------+
          |      Data Link Layer      |  - Tầng liên kết dữ liệu
          +---------------------------+
          |      Physical Layer       |  - Tầng vật lý
          +---------------------------+
        ```
        
    - Mô hình mạng TCP/IP (mô hình 4 tầng)
        
        - **Mô hình TCP/IP (Transmission Control Protocol/Internet Protocol)** được phát triển bởi Bộ Quốc phòng Hoa Kỳ để kết nối các thiết bị mạng trên Internet.
        
        **1. Tầng Giao Tiếp Mạng (Network Interface Layer)**
        
        - **Chức năng:**
            
            - Quản lý việc truyền dữ liệu qua môi trường vật lý.
            - Điều khiển việc truy cập vào mạng cục bộ và truyền các gói tin qua các liên kết vật lý.
            
            ⇒ Quản lý truyền dữ liệu qua môi trường vật lý và điều khiển truy cập vào mạng cục bộ.
            
        - **Những thứ có liên quan tới tầng này:**
            
            - Ethernet, Wi-Fi, ARP (Address Resolution Protocol).
        
        **2. Tầng Internet (Internet Layer)**
        
        - **Chức năng:**
            
            - Định tuyến các gói tin trên mạng.
            - Địa chỉ hóa các thiết bị mạng và xác định đường đi tốt nhất cho các gói tin từ nguồn đến đích.
            
            ⇒ Định tuyến các gói tin và quản lý địa chỉ IP.
            
        - **Những thứ có liên quan tới tầng này:**
            
        - IP (Internet Protocol), ICMP (Internet Control Message Protocol), IGMP (Internet Group Management Protocol).
            
        
        **3. Tầng Giao Vận (Transport Layer)**
        
        - **Chức năng:**
            
            - Đảm bảo truyền dữ liệu toàn vẹn và đáng tin cậy giữa hai thiết bị.
            - Quản lý các kết nối giữa các thiết bị mạng và đảm bảo dữ liệu được truyền đúng thứ tự.
            
            ⇒ Đảm bảo truyền dữ liệu toàn vẹn và đáng tin cậy giữa các thiết bị.
            
        - **Những thứ có liên quan tới tầng này:**
            
            - TCP (Transmission Control Protocol), UDP (User Datagram Protocol).
        
        **4. Tầng Ứng Dụng (Application Layer)**
        
        - **Chức năng:**
            
            - Cung cấp các giao diện và giao thức cho các ứng dụng để trao đổi dữ liệu qua mạng.
            - Tương tác trực tiếp với người dùng và cung cấp các dịch vụ như truyền tệp, gửi email, duyệt web, và nhiều ứng dụng mạng khác.
            
            ⇒ Cung cấp giao diện và giao thức cho các ứng dụng để trao đổi dữ liệu qua mạng.
            
        - **Những thứ có liên quan tới tầng này:**
            
            - HTTP (Hypertext Transfer Protocol), FTP (File Transfer Protocol), SMTP (Simple Mail Transfer Protocol), DNS (Domain Name System).
        
        ```python
          +---------------------------+
          |     Application Layer     |  - Tầng ứng dụng
          +---------------------------+
          |      Transport Layer      |  - Tầng vận chuyển
          +---------------------------+
          |       Internet Layer      |  - Tầng mạng
          +---------------------------+
          | Network Interface Layer   |  - Tầng giao diện mạng
          +---------------------------+
        ```
        
        - Mô hình IP Stack giống với mô hình TCP/IP
    - So sánh Mô hình TCP/IP và Mô hình OSI
        
        - **Số tầng:** Mô hình OSI có bảy tầng, trong khi mô hình TCP/IP có bốn tầng.
        - **Tính phổ biến:** Mô hình TCP/IP là mô hình chuẩn thực tế được sử dụng rộng rãi trên Internet, trong khi mô hình OSI thường được sử dụng như một công cụ giảng dạy.
        - **Chức năng tương ứng:**
            - Tầng Giao Tiếp Mạng (TCP/IP) tương ứng với tầng Vật lý và tầng Liên kết Dữ liệu (OSI).
            - Tầng Internet (TCP/IP) tương ứng với tầng Mạng (OSI).
            - Tầng Giao Vận (TCP/IP) tương ứng với tầng Giao Vận (OSI).
            - Tầng Ứng Dụng (TCP/IP) tương ứng với tầng Ứng Dụng, tầng Trình bày, và tầng Phiên (OSI).
4. **Quá trình đóng gói dữ liệu**
    
    - Quy trình đóng gói dữ liệu (Encapsulation) đối với mô hình TCP/IP (mô hình 4 tầng)
        - Note: Tầng Network Access ở đây được chia thành hai tầng là Physical và Data Link còn tầng Network thật chất là tầng Internet; mục địch của việc ghi thế này là để nó giống hơn với mô hình OSI cho dể hình dung chứ về bản chất thì không đổi
        - Ví dụ Johnny truy cập vào NetworkChuk Coffee để mua Cà phê
        - Đầu tiên Johnny vào trình duyệt web và gõ tên miền [NetworkChuk.coffee](http://NetworkChuk.coffee) → Tầng Application (tầng 7) sử dụng giao thức HTTPs
        - Sau đó gửi Data xuống tầng Transport (Tầng 4) → Tại đây nó được gắn vào một Layer 4 header chứa giao thức dùng để truyền đi VD: TCP or UDP và con số của Cổng mà nó sẽ truyền đi ⇒ Tạo thành một Segment
        - Sau đó xuống đến tầng Network (Tầng 3) → Tại đây nó được gắn thêm một Layer 3 header chứa địa chỉ IP nguồn (Source IP address) và địa chỉ IP đích (Destination IP address) → Địa chỉ IP chỉ đường cho Router để truyền thông tin đến nơi cần tới ⇒ Tạo thành một Packet
        - Sau đó xuống đến tầng Data Link (Tầng 2) → Tại đây nó được gắn thêm một Layer 2 header và một Layer 2 Trailer, Layer 2 header chứa địa chỉ Source Mac address (Địa chỉ làm việc với Switch) và địa chỉ Destination Mac address; Còn Layer 2 trailer chưa một số giao thức kiểm tra lỗi đảm bảo gói tin được truyền đến nơi, đầy đủ và theo đúng thứ tự ⇒ Tạo thành một Frame
        - Cuối cùng là đến tầng Physical layer (Tầng 1) để truyền đi
        - Làm ngược lại để có được quá trình Decapsulation
    - Quy trình đóng gói dữ liệu (Encapsulation) đối với mô hình OSI (mô hình 7 tầng)
        - Giống hệt mô hình TCP/IP phía trên, khác một chỗ là được bổ sung thêm hai tầng:
            - Presentation: Liên quan đến Data Format (Kiểu của data là gì VD như PDF, HTML) và Encryption (Mã hóa chống Hacker)
            - Session: Tạo ra một kết nối để bắt đầu truyền Data với nhau đảm bảo mọi thứ diễn ra thông suốt nhanh
5. **Các đơn vị dữ liệu giao thức (PDU) tại các tầng trong mô hình OSI**
    
    - PDU (Protocol Data Units)
        
        - Tầng Physical (Tầng 1): Bits
        - Tầng Data Link (Tầng 2): Frames
        - Tầng Network (Tầng 3): Packets
        - Tầng Transport (Tầng 4): Segments (TCP) - DataGrams (UDP)
        - Tầng Session (Tầng 5): Data hoặc Message
        - Tầng Presentation (Tầng 6): Data hoặc Message
        - Tầng Application (Tầng 7): Data hoặc Message
        
        ⇒ Cách nhớ từ tầng 4 đến tầng 1: Some People Fear Birthday
        
6. Các thuật ngữ viết tắt
    
    - LAN
        - Local area network (Mạng cục bộ)
    - WAN
        - Wide Area Network (Mạng toàn bộ)
    - ISP
        - Internet service provider (Nha cung cấp mạng VD: VNPT, FPT,…)