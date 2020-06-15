# saungan.com
Trang web giới thiệu in ấn áo thun, áo thun đặc biệt, đặt áo online.
Cài đặt một số phần mềm sau:
1/ Git for window
2/ XAMPP với PHP 7+, MySQL 5.6+ - XAMPP
3/ Composer - trình quản lý các gói package PHP - Composer
4/ HeidiSQL hoặc workbend - quản lý thực thi câu truy vấn SQL - HeidiSQL
5/ Visual Studio Code IDE - trình gõ code - Visual Studio Code
6/ TortoiseGIT - TortoiseGIT


Bước 1:
git clone https://github.com/davidnghi/saungan.com.git
Bước 2:tạo tên miền ảo trên máy cục bộ (virtual host on localhost) bằng XAMPP
1. Thêm tên miền ảo cho XAMPP
Hiệu chỉnh file C:xampp/apache/conf/extra/httpd-vhosts.conf
Bổ sung thêm đoạn script sau vào cuối file:
<VirtualHost *:80>
    #Thay thế bằng email của Quản trị web của bạn
	  ServerAdmin webmaster@saungan.com.local
	
	  #Thay thế bằng đường dẫn đến source của bạn
    DocumentRoot "C:/xamp/saungan.com"
	
	  #Thay thế bằng tên trang web bạn mong muốn
    ServerName  saunngan.com.local
	
	  #Thay thế bằng tên file log bạn mong muốn
    ErrorLog "logs/saunngan.com.log"
    CustomLog "logs/saunngan.com.log" common
	
	  #Thay thế bằng đường dẫn đến source của bạn
    <Directory "C:/xamp/saungan.com">
        Options FollowSymLinks
        AllowOverride All
        DirectoryIndex index.php
        Require all granted
    </Directory>
</VirtualHost>
2. Add host cho tên miền saunngan.com.local
Lưu ý: để hiệu chỉnh file hệ thống, bạn cần quyền Administrator
Hiệu chỉnh file C:/Windows/System32/drivers/etc/hosts
#Bổ sung địa chỉ IP ánh xạ với tên miền bạn mong muốn (Tương ứng với tên miền bạn đặt trong host ảo)
127.0.0.1		saunngan.com.local

Bước 3: install các thư viện (package) cần thiết thông qua composer
Trỏ đường dẫn vào thư mục C:/xamp/saungan.com, chạy câu lệnh sau để cài đặt
cd C:/xamp/saungan.com
composer install

Bước 4:
Cấu hình tài khoản để commit/push - pull source
Mở Start -> Run -> cmd
git config --global user.email "dqnghi26@gmail.com"
git config --global user.name "dqnghi26@gmail.com"
Thay đổi email và name bằng tài khoản các bạn đã đăng ký trên GitHub

Bước 5:
Sau khi đã cấu hình trước khi viết code thì clone về, sau đó pull, rồi commit xong mới push.
