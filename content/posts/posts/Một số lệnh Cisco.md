---
title: MỘT SỐ LỆNH CISCO
date: 2024-12-30
draft: false
tags:
  - firstblog
  - mangmaytinh
---
- Switch>
- Switch> enable (hoặc ena rồi tab/ruturn) → Switch#
- Switch#
    - Switch#show running-config (show mật khẩu,…)
    - Switch#copy running-config startup-config: Lưu tất cả những cấu hình đã làm để khi shut down thiết bị, cấu hình vẫn được lưu
    - Switch# configuration terminal → Switch(config)#
- Switch(config)#
    - Switch(config)#hostname MinhDuc → Đổi tên switch thành MinhDuc
        
    - Switch(config)#show version
        
    - Switch(config)#enable password Layer2 → Đặt mật khẩu để vào Switch#, mật khẩu được đặt thành Layer2
        
    - Switch(config)#enable secret MinhDuc → Đổi mật khẩu Layer 2 thành MinhDuc và mã hóa để người khác không biết mật khẩu là gì
        
    - Switch(config)#service password-encryption: Mã hóa tất cả password đang có
        
    - Switch(config)#banner motd “CAM PHA HOAI!!!”: Thêm banner ngay khi truy cập vào CLI
        
    - Switch(config)# → Ctrl + C → witch# → ‘Exit’ → Switch>
        
    - Switch(config)#line console 0 → Switch(config-line)#password letmein (set password khởi đầu, password là letmein) → Switch(config-line)#login
        
    - Switch(config)# interface gigabitEthernet 0/0 →Switch(config-if)#ip address 192.168.1.1 255.255.255.0 → Switch(config-if)#no shutdown (add IP)
        
    - **Lệnh Cisco truy cập vào các chế độ**
        
        |**Mô tả**|**Lệnh**|
        |---|---|
        |**User mode (chế độ user)**|**Switch>**|
        |**Enter Privilege mode (vào chế độ đặc quyền)**|**Switch>enable**|
        |**Privileged mode (chế độ đặc quyền)**|**Switch#**|
        |**Enter configuration mode (vào chế độ cấu hình)**|**Switch#configure terminal**|
        |**Global Config mode**|**Switch(config)#**|
        |**Vào Interface mode**|**Switch(config)#interface fa0/1**|
        |**Interface mode**|**Switch(config-if)**|
        |**Return to global configuration (Trở về Global Config)**|**Switch(config-if)exit**|
        |**Exit Global Config mode (Thoát Global Config)**|**Switch(config)#exit**|
        |**Return to user mode (Trở về user mode)**|**Switch#disable**|
        |**Logout (Đăng xuất)**|**Switch>exit**|
        
    - **Các lệnh đặc quyền (Privilege Commands) trên Switch**
        
        |Displays the config held in DRAM. Which is lost if not copy run start command is not used: Hiển thị cấu hình lưu trong DRAM. Cấu hình này bị mất khi lệnh not copy run start không được sử dụng.|Switch#show running-config|
        |---|---|
        |Displays the NVRAM (None volatile) config: Hiển thị cấu hình NVRAM.|Switch#show startup-config|
        |Saves the config: Lưu cấu hình, nếu không có lệnh này tất cả các thay đổi, cấu hình sẽ bị mất.|Switch#copy running-config startup-config|
        |Erase the config held in NVRAM: Xóa cấu hình lưu trong VNRAM. Nếu thực hiện lệnh này kèm với reload thì tất cả cấu hình sẽ bị mất.|Switch#erase startup-config|
        |Reboots the device: Khởi động lại switch.|Switch#reload|
        |Show the current sessions: Xem phiên hiện tại, phiên nào có * là phiên hiện hoạt.|Switch#show sessions|
        |Display the IOS version along with other useful info: Xem phiên bản IOS và các thông tin hữu ích khác như uptime hệ thống, cấu hình register...|Switch#show version|
        |Xem giờ.|Switch#show clock|
        |Xem user hiện đang đăng nhập.|Switch#show users|
        |By default displays the last 10 commands: Xem 10 lệnh vừa dùng.|Switch#show history|
        |Displays the ARP cache: Xem cache ARP.|Switch#show arp|
        |Lists all the configured vlans: Liệt kê tất cả vlan đã cấu hình.|Switch#show vlan|
        |Ping selected address: Ping một địa chỉ IP.|Switch#ping 10.1.1.1|
        |Extended ping: Phải thực hiện trong chế độ privilege.|Switch#ping|
        |Display the interface status: Hiển thị trạng thái interface.|Switch#show int fa0/1|
        |Display switch MAC Addresses table. These entries are learnt from the source mac address in the Ethernet frames: Xem bảng địa chỉ MAC, lấy từ địa chỉ MAC nguồn trong Ethernet frame.|Switch#show mac address-table|
        
    - **Lệnh cấu hình Router cơ bản**
        
        | Set a console password to cisco: Đặt mật khẩu console là Cisco. | Router(config)#line con 0 Router(config-line)#login Router(config-line)#password cisco | | --- | --- | | Set a telnet password: Đặt mật khẩu telnet. | Router(config)#line vty 0 4 Router(config-line)#login Router(config-line)#password cisco | | Stop console timing out: Console không bị log off. | Router(config)#line con 0 Router(config-line)#exec-timeout 0 0 | | Set the enable password to cisco: Đặt mật khẩu enable là cisco. | Router(config)#enable password cisco | | Set the enable secret password to peter: Đặt mật khẩu secret là peter. Mật khẩu này ghi đè lên mật khẩu enable và được mã hóa trong file cấu hình. | Router(config)#enable secret peter | | Enable an interface: Bật interface. | Router(config-if)#no shutdown | | To disable an interface: Tắt interface. | Router(config-if)#shutdown | | Set the clock rate for a router with a DCE cable to 64K: Đặt clock rate cho router với cáp DCE là 64000. | Router(config-if)clock rate 64000 | | Set a logical bandwidth assignment of 64K to the serial interface: Gán băng thông logic cho serial interface. | Router(config-if)bandwidth 64 | | To add an IP address to a interface: Thêm IP cho interface. | Router(config-if)#ip addr 10.1.1.1 255.255.255.0 | | Vô hiệu hóa Disables DNS lookup. Hữu ích khi lệnh bị gõ lỗi. | Router(config)#no ip domain-lookup | | | |
        
    - Route - RIP routing IPV6:
        
        ```python
        Router(config)#ipv6 unicast-routing
        Router(config)#ipv6 router rip RIPng
        Router(config-router)#network 2001:db8:cafe:a00::/64
        Router(config-router)#exit
        Router(config)#interface s0/1/1
        Router(config-if)#ipv6 address 2001:db8:cafe:a00::1/64
        Router(config-if)#ipv6 enable
        Router(config-if)#ipv6 rip RIPng enable
        Router(config-if)#exit
        ```
        
    - Route - RIP routing IPV4:
        
        ```python
        Router1(config)#router rip
        Router1(config-router)#version 2
        Router1(config-router)#no auto-summary
        Router1(config-router)#network 10.10.10.0
        Router1(config-router)#network 172.16.16.0
        Router1(config-router)#network 192.168.1.0
        Router1(config-router)#network 192.168.1.128
        Router1(config-router)#network 192.168.1.192
        Router1(config-router)#network 192.168.1.224
        ```
        