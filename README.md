1. Register
- method = POST
- URL: http://localhost:3000/auth/register
- đăng ký thành công
<img width="1919" height="1079" alt="image" src="public/img/register.png" />
- Hiển thị người dùng trong database
<img width="1919" height="1079" alt="image" src="public/img/registerdatabase.png" />


2. Login
Method = POST 
URL: http://localhost:3000/auth/login
-Login thành công kết quả trả về 
{
    "message": "Logged in successfully",
    "user": {
        "_id": "68d7c8e7945d3220f6ca3124",
        "username": "admin",
        "password": "$2b$10$DROT8OzO18xJJVMHAKQw/eP9AbCuUiox4jR8BVefeLFGrBfzqN2P2",
        "__v": 0
    }
}
<img width="1919" height="1079" alt="image" src="public/img/login.png" />
-Sau khi login thành công postman trả về session cookie được tự sinh ra với thư viện passport-local
<img width="1919" height="1079" alt="image" src="public/img/cookielogin.png" />

3. Login thất bại
Trả về thông báo "Unauthorized"
<img width="1919" height="1079" alt="image" src="public/img/saiuser.png" />


4. Truy cập route bảo vệ /auth/profile khi đã login
Method = GET 
URL: http://localhost:3000/auth/profile

truy cập thành công và trả về kết quả gồm usernam và password đã được mã hóa
<img width="1919" height="1079" alt="image" src="public/img/profile.png" />
password được mã hóa giông với password được lưu trong database
<img width="1919" height="1079" alt="image" src="public/img/profiledb.png" />
có cookie giống với cookie khi login được trả về
<img width="1919" height="1079" alt="image" src="public/img/cookieprofile.png" />


5. Logout
Method = GET 
URL: http://localhost:3000/auth/logout

Logout thành công và trả về thông báo 
<img width="1919" height="1079" alt="image" src="public/img/logout.png" />


6. Truy cập route bảo vệ /auth/profile khi đã logout
Method = GET 
URL: http://localhost:3000/auth/profile

Không xem được thông tin 
<img width="1919" height="1079" alt="image" src="public/img/logoutprofile.png" />


