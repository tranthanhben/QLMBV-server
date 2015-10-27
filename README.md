# APIs

Context|http code|description
---|---|---
success | 200
not found | 404| query database fail
bad request |400| parse request fail
forbidden | 403 | post, put, delete in no session matched

## APIs Nhà phân phối

### Lấy thông tin chi tiết nhà phân phối theo {id}

```
GET /nha_phan_phoi/{id}

Success:
{
  <nha_phan_phoi>
}

Fail:
{
  code: "bad-request"/"not-found",
  message: "Bad Request"/"Not Found"
}
```

### Lấy danh sách nhà phân phối 

```
GET /nha_phan_phoi

Success:
[
  <nha_phan_phoi>
]

Fail:
{
  code: "bad-request"/"not-found",
  message: "Bad Request"/"Not Found"
}
```
**Query search (nhà phân phối & khách hàng)**

GET /nha_phan_phoi?name="abc"&sort="name"
* **name** (string) search value, no tone sign
* **sort** (string) "name"

### Tạo mới nhà phân phối (post)

```
POST /nha_phan_phoi

Request:
{
  <nha_phan_phoi>
}

Success:
{
  <nha_phan_phoi>
}

Fail:
{
  code: "bad-request"/"not-found"/"forbidden",
  message: "Bad Request"/"Not Found"/"Forbidden"
}
```

### Cập nhật Nhà phân phối (Put)

```
PUT /nha_phan_phoi/{id}

Request:
{
  <nha_phan_phoi>
}

Success:
{
  <nha_phan_phoi>
}

Fail:
{
  code: "bad-request"/"not-found"/"forbidden",
  message: "Bad Request"/"Not Found"/"Forbidden"
}
```

### Xóa Nhà phân phối (Delete)

```
DELETE /nha_phan_phoi/{id}

Success:
{
  code: "ok",
  message:"ok"
}

Fail:
{
  code: "bad-request"/"not-found"/"forbidden",
  message: "Bad Request"/"Not Found"/"Forbidden"
}
```

## APIs Khách hàng

### Lấy thông tin chi tiết Khách hàng theo {id}

```
GET /khach_hang/{id}

Success:
{
  <khach_hang>
}

Fail:
{
  code: "bad-request"/"not-found",
  message: "Bad Request"/"Not Found"
}
```

### Lấy danh sách khách hàng 

```
GET /khach_hang

Success:
[
  <khach_hang>
]

Fail:
{
  code: "bad-request"/"not-found",
  message: "Bad Request"/"Not Found"
}
```
**Query search ( khách hàng)**

GET /khach_hang?name="abc"&sort="name"
* **name** (string) search value, no tone sign
* **sort** (string) "name"

### Tạo khách hàng mới (post)

```
POST /khach_hang

Request:
{
  <khach_hang>
}

Success:
{
  <khach_hang>
}

Fail:
{
  code: "bad-request"/"not-found"/"forbidden",
  message: "Bad Request"/"Not Found"/"Forbidden"
}
```

### Cập nhật Khách hàng (Put)

```
PUT /khach_hang/{id}

Request:
{
  <khach_hang>
}

Success:
{
  <khach_hang>
}

Fail:
{
  code: "bad-request"/"not-found"/"forbidden",
  message: "Bad Request"/"Not Found"/"Forbidden"
}
```

### Xóa Khách hàng (Delete)

```
DELETE /khach_hang/{id}

Success:
{
  code: "ok",
  message:"ok"
}

Fail:
{
  code: "bad-request"/"not-found"/"forbidden",
  message: "Bad Request"/"Not Found"/"Forbidden"
}
```

## APIs Cây vải

### Lấy thông tin chi tiết Cây vải theo {id}

```
GET /cay_vai/{id}

Success:
{
  <cay_vai>
}

Fail:
{
  code: "bad-request"/"not-found",
  message: "Bad Request"/"Not Found"
}
```

### Lấy danh sách Cây vải 

```
GET /cay_vai

Success:
[
  <cay_vai>
]

Fail:
{
  code: "bad-request"/"not-found",
  message: "Bad Request"/"Not Found"
}
```
**Query search (cây vải)**

GET /cay_vai?name="abc"&color="red"&sort="name"
* **name** (string) search value, no tone sign
* **color** (string) search value, no tone sign
* ...
* **sort** (string) "name"

### Tạo Cây vải mới (post)

```
POST /cay_vai

Request:
{
  <cay_vai>
}

Success:
{
  <cay_vai>
}

Fail:
{
  code: "bad-request"/"not-found"/"forbidden",
  message: "Bad Request"/"Not Found"/"Forbidden"
}
```

### Cập nhật cây vải (Put)

```
PUT /cay_vai/{id}

Request:
{
  <cay_vai>
}

Success:
{
  <cay_vai>
}

Fail:
{
  code: "bad-request"/"not-found"/"forbidden",
  message: "Bad Request"/"Not Found"/"Forbidden"
}
```

### Xóa Cây vải (Delete)

```
DELETE /cay_vai/{id}

Success:
{
  code: "ok",
  message:"ok"
}

Fail:
{
  code: "bad-request"/"not-found"/"forbidden",
  message: "Bad Request"/"Not Found"/"Forbidden"
}
```


## APIs Tài khoản 


context|http code|description
---|---|---
success | 200
not found | 404|query database fail
bad request |400|parse request fail
invalid password | 400
duplicated email | 400



###  Register ( Đăng kí)

```
POST /register

Request:  
{
  <account>
 }
 
Success:
{
    <account>   
}

Fail: 
{
	code: "bad-request"/"not-found"/"duplicated-email"
	message: "Bad Request"/"Not Found"/"Duplicated Email"
}


```

###  Login (Đăng nhập)

```
POST /login

Request:
{
	email: <string>,
	password: <string>
}

Success:
{
	<account>
}

Fail:
{
	code: "bad-request"/"not-found"/"invalid-password",
	message: "Bad Request"/"Not Found"/"Invalid Password"
}
```

###  Logout (Đăng xuất)

```
POST /logout

Response:
{
	code: "ok",
	message: "ok"
}

```

###  Change Info (Thay đổi thông tin)

```
POST /change-info

Request:
{
	first_name: <string>,
	last_name: <string>
}

Success:
{
	<account>
}

Fail:
{
	code: "bad-request"/"not-found",
	message: "Bad Request"/"Not Found"
}
```

### Change password (Thay đổi thông tin mật khẩu)

```
POST /change-password

Request:
{
	old_password: <string>,
	new_password: <string>
}

Success:
{
	<account>
}

Fail:
{
	code: "bad-request"/"not-found"/"invalid-password",
	message: "Bad Request"/"Not Found"/"Invalid Password"
}
```

### Lấy thông tin Tài khoản hiện tại

```
GET /me

Success:
{
	<account>
}

Fail:
{
	code: "not-found",
	message: "Not Found"
}
```
