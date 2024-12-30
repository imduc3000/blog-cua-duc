---
title: TẦNG PHYSICAL
date: 2024-12-30
draft: false
tags:
  - firstblog
  - mangmaytinh
---
1. **Các loại cáp thường gặp trong tầng Physical**
    
    - Cáp đôi xoắn (Twisted Pair Cable)
        
        - Cáp UTP (Unshield Twisted Pair): Gồm nhiều cáp được xoắn lại với nhau nhưng không có lớp bảo vệ bên ngoài để khử nhiễu, được dùng phổ biến hiện nay ở nhà ở các business vừa, nhỏ; dùng chuẩn RJ-45
            
        - Cáp STP (Shield Twisted Pair): Giống UTP nhưng có thêm lớp Shield bảo vệ bên ngoài để khử nhiễu; dùng chuẩn RJ-48
            
        - Hai loại chuẩn phổ biến trong mạng LAN: Straight Cable (Cáp thẳng) và Crossover Cable (Cáp chéo)
            
            - Hai chuẩn mà cáp thẳng (Straight Cable) này dùng là 568A và 568B: Hai chuẩn này là tương tự nhau nhưng ở US người Mễ dùng 568B nhiều hơn ⇒ Straight Cable: Dùng cùng một chuẩn đầu ra (cả hai đầu ra đều sử dụng cùng 1 chuẩn 568A hoặc 568B), sử dụng phổ biến trong LAN, được dùng để kết nối các thiết bị khác nhau lại với nhau (Kết nối máy tính, hub, switch, router,…)
            
            ```python
            568A Wiring Standard (T568A)
            Pin 1: White/Green
            Pin 2: Green
            Pin 3: White/Orange
            Pin 4: Blue
            Pin 5: White/Blue
            Pin 6: Orange
            Pin 7: White/Brown
            Pin 8: Brown
            
            +--------+--------+--------+--------+--------+--------+--------+--------+
            |  Pin 1 |  Pin 2 |  Pin 3 |  Pin 4 |  Pin 5 |  Pin 6 |  Pin 7 |  Pin 8 |
            | White/ | Green  | White/ |  Blue  | White/ | Orange | White/ | Brown  |
            | Green  |        | Orange |        |  Blue  |        | Brown  |        |
            +--------+--------+--------+--------+--------+--------+--------+--------+
            ```
            
            ```python
            568B Wiring Standard (T568B)
            Pin 1: White/Orange
            Pin 2: Orange
            Pin 3: White/Green
            Pin 4: Blue
            Pin 5: White/Blue
            Pin 6: Green
            Pin 7: White/Brown
            Pin 8: Brown
            
            +--------+--------+--------+--------+--------+--------+--------+--------+
            |  Pin 1 |  Pin 2 |  Pin 3 |  Pin 4 |  Pin 5 |  Pin 6 |  Pin 7 |  Pin 8 |
            | White/ | Orange | White/ |  Blue  | White/ | Green  | White/ | Brown  |
            | Orange |        | Green  |        |  Blue  |        | Brown  |        |
            +--------+--------+--------+--------+--------+--------+--------+--------+
            ```
            
            - Crossover Cable: Cũng được dùng trong LAN, Gọi là cáp xoắn vì hai đầu ra sử dụng hai loại chuẩn khác nhau (1 đầu dùng chuẩn 568A, đầu còn lại dùng chuẩn 868B); Dùng để trực tiếp kết nối hai thiết bị giống nhau lại với nhau mà không cần dùng tới hub hay switch, hoặc có thể dùng để kết nối hub - hub, switch - switch
        - Một số loại cáp Twisted Pair Cable phổ biến (Cat 3-8):
            
        
        [https://www.youtube.com/watch?v=_NX99ad2FUA](https://www.youtube.com/watch?v=_NX99ad2FUA)
        
    - Cáp UTP (Untwisted pair cable) có các chuẩn CAT từ 2-6
        
    - Cáp quang:
        
        - Multimode có khoảng cách truyền đi ngắn hơn Singlemode; Core (phần lõi trong cùng bằng thuỷ tinh) của Multimode to hơn của Singlemode; Nguyên lý hoạt động: Truyền ánh sáng đi theo chiều chéo để ánh sáng bounce và truyền đi liên tục
        - Singlemode có khoảng cách truyền đi dài hơn; Nguyên lý hoạt động: Truyền đi thẳng một hàng và không bounce
2. **Một số chuẩn bảo vệ các loại cáp (Lớp bảo vệ bên ngoài)**
    
    - Plenum Cable: Có khả năng chống cháy cao, và không tạo ra khi độc khi bị cháy
    - PVC (non plenum): Viết tắt của Polyvinyl đồng thời là chất liệu của vỏ bọc bên ngoài, loại chất liệu này có khả năng chống cháy kém và khi bị cháy sẽ tạo ra khi độc gây hại đến con người
    - Riser (CMR): Sử dụng để đi dây giữa các tường (có thể là trên tường hoặc âm tường), khả năng chống cháy thấp hơn so với Plenum Cable
    - CM: Được sử dụng rộng rãi, rẻ và có ít tính năng đảm bảo an toàn
3. **Các đầu kết nối của các loại cáp khác nhau**
    

- RJ-45: Rất phổ biến ngày nay, Được dùng với UTP (Unshield Twisted Pair Cable)
- RJ-48: Sử dụng cho STP (Shield Twisted Pair Cable), sử dụng với T1 lines (Truyền tải dữ liệu và thoại)
- RJ-11: Sử dụng DSL, liên quan đến điện thoại
- BNC: Sử dụng với cáp đồng, có một số loại như BNC T, BNC Coupler, BNC Terminator
- F-Type: Cũng dùng với cáp đồng, đây là đầu để gắn dây cáp đồng vào modem
- Một số đầu mà cáp quang dùng: SC (Square Connector), MT-RJ, LC, ST
- EMI (Electromagnetic Interference) là hiện tượng nhiễu điện từ

1. **Đặc điểm của các chuẩn mã hoá không dây WPA, WEP, …**
    - Đây là những giao thức dùng để bảo mật mạng không dây, điển hình như thông thường khi muốn sử dụng wifi người ta phải nhập mật khẩu của wifi đó rồi mới bắt đầu truy cập và sử dụng được, các giao thức này thường xuất hiện trong các Router để người dùng chủ động lựa chọn phương thức bảo mật cho mạng nhà mình
    - WEP: Wired Equivalent Privacy - ra đời năm 1999 là giao thức bảo mật mạng không dây ra đời sớm nhất, nó sử dụng các cơ chế bảo mật mạng có dây (mã hoá 40 bits) để bảo mật cho mạng không dây, thành ra giao thức này khá cùi và ngày nay không còn được sử dụng nữa thậm chí các router ngày này còn không có option WEP để lựa chọn cho việc bảo mật. Và thế là một giao thức bảo mật hơn ra đời: WPA
    - WPA: Wifi protected access - Sử dụng một giao thức mã hoá mạnh mẽ hơn mang tên TKIP(temporal key integrity protocol), TKIP cải thiện bảo mật bằng cách thay đổi khóa mã hóa sử dụng trong mạng Wi-Fi một cách định kỳ và động. Tuy nhiên mặc dù là bảo mật hơn WEP nhưng WPA vẫn như cứt và dể bị hack vl. Và thế là WPA2 ra đời
    - WPA2: Cung cấp mã hoá mạnh mẽ hơn WPA, sử dụng một giao thức mã hoá mạnh mẽ hơn, thay vì dùng TKIP như WPA, nó dùng AES (Advanced Encryption standard) để mã hoá aka mã hoá đối xứng (sử dụng cùng một khóa cho cả quá trình mã hóa và giải mã dữ liệu, điều này giúp tăng hiệu quả và tốc độ của quá trình mã hóa) điều này giúp chống lại các cuộc tấn công Brute-force (một phương pháp tấn công mật mã học trong đó kẻ tấn công thử tất cả các tổ hợp có thể của các ký tự để tìm ra mật khẩu, khóa mã hóa, hoặc mã xác thực) - AES bảo mật tới mức chính phũ nước Mễ sử dụng để mã hoá và bảo mật các dữ liệu nhạy cảm của chính phũ
    - Trong một số Router sẽ có option bảo mật kết hợp cả hai giao thức bảo mật WPA - WPA2, bởi vì có một số thiết bị cũ hơn khi kết nối sẽ sử dụng sao thức WPA còn các thiết bị hiện đại hơn mới hơn sau này sẽ sử dụng WPA2. Vậy tại sao ta không sử dụng WPA - WPA2 là chế độ bảo mật mặc định đi, phải lựa chọn và sinh ra thêm nhiều cái khác chi cho nhức đầu? Trong WPA - WPA2 để sử dụng AES trước tiên phải đi qua TKIP thành ra nó sẽ không được bảo mật 100% thành ra nếu tất cả các thiết bị của ta đều là các thiết bị hiện đại ngày nay việc lựa chọn WPA2 thay vì WPA - WPA2 chắc chắn sẽ đem lại độ bảo mật cao hơn rất rất nhiều
    - WPA3 ra đời năm 2018, nói chung là hiện đại nhất và bảo mật cao nhất. Đơn giản hoá quá trình mã hoá nhưng không làm giảm chất lượng mã hoá, chống đoán mật khẩu tốt hơn
    - WPS: Wifi protected setup - được tạo ra để người dùng truy cập vào mạng không dây một cách đơn giản và thuận tiện nhất: Có một số cách mà các nhà sản xuất đính kèm vào router như chỉ cần lại gần cái router và nhấn một cái nút nào đó trên nó và thiết bị của bạn sẽ tự động kết nối vào internet (thần kỳ vl)