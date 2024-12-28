---
title: PHẦN CƠ BẢN
date: 2024-12-28
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
        - Tính bảo mật của Telnet không cao do thông tin truyền đi không được mã hóa
        - Cách thức hoạt động: Đầu tiên người dùng sử dụng một ứng dụng Telnet để kết nối với máy chủ Telnet, sau đó người dùng sẽ nhập tên đăng nhập và mật khẩu, cuối cùng một cửa số như terminal sẽ hiện ra giúp người dùng tương tác với máy chủ từ xa như thể đang trực tiếp điều khiển máy chủ đó
    - SSH
        
        - Viết tắt của Secure Shell
        - Là Telnet nhưng bảo mật hơn vì thông tin truyền đi được mã hóa
        - Cách thức hoạt động: Giống với Telnet, khác ở chỗ có thêm bước SSH sẽ thiết lập một kênh mã hoá giữa máy khách và máy chủ trước khi người dùng đăng nhập, để đảm bảo tính bảo mật
    - VLAN
        
        - Viết tắt của Virtual LAN
        - Tạo ra các mạng con ảo trên một mạng lớn bằng Switch: Chia một mạng Vật lý lớn thành các mạng con nhỏ hơn mà không cần thêm phần cứng mới
        - Mục tiêu của VLAN là: Cải thiện tính bảo mật, điều khiển giao thông mạng, Đơn giản hoá một mạng
        
        ![[IMG 439.jpg]]
        
        - Giải thích:
            - Giả sử có ba loại màu máy tính đại diện cho ba phòng ban khác nhau trong một công ty, đặt trường hợp nếu kết nối tất cả các máy tính này vào cùng một switch, thì các phòng ban khác sẽ có thể thấy và biết được những gì đã và đang xảy ra ở các phòng ban khác. Điều này là vô cùng bất tiện
                
            - Vậy nên Switch có kết hợp VLAN ra đời: Vẫn là switch nơi các máy tính kết nối vào nhau, nhưng giờ đây, VLAN giúp tạo ra các mạng ảo và các phòng ban khác nhau giờ đây sẽ được sử dụng các đường truyền khác nhau tuy vẫn được cắm vào cùng một switch.
                
                ![Screenshot 2024-12-19 at 18.12.45.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/57a28937-0a02-4eae-a8ce-d385132961ac/02fc73bd-0b98-4919-b04f-5f737005a2ef/Screenshot_2024-12-19_at_18.12.45.png)
                
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
            
            ![Screenshot 2024-12-21 at 10.36.32.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/57a28937-0a02-4eae-a8ce-d385132961ac/f489b988-0620-4122-a27c-fde8e93da1e1/Screenshot_2024-12-21_at_10.36.32.png)
            
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
            
            ![Ảnh màn hình 2024-11-24 lúc 21.43.48.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/57a28937-0a02-4eae-a8ce-d385132961ac/a1b91a47-36e2-448e-b722-2033a4f38fcc/Anh_man_hinh_2024-11-24_luc_21.43.48.png)
            
        - Ưu điểm so với Ethernet: Không gây ra va chạm
            
        - Nhược điểm: Mắc vãi lồn (IBM tính phí mắc gấp 5-6 lần so với Ethernet thông thường)
            
    - ICMP
        
        - ICMP (Internet Control Message Protocol) là một giao thức trong bộ giao thức Internet được sử dụng để gửi các thông báo lỗi và thông tin hoạt động trong các mạng IP