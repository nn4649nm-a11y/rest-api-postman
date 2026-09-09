# REST API & Postman Testing (5-Day Challenge)

Repository นี้เป็นส่วนหนึ่งของกิจกรรม **Learn Anything in 5 Days Challenge**  
- **ผู้จัดทำ:** อรรถนนท์ นาคดิษฐ์
- **รหัสนักศึกษา:** 68365996
- **หัวข้อ:** REST API & Postman Testing

---

## 📌 ภาพรวมโครงการ
ศึกษาหลักการทำงานของ REST API, สถาปัตยกรรม Client-Server, โครงสร้าง HTTP Methods, Headers, Request Body และการแปลความหมายของ HTTP Status Codes โดยใช้โปรแกรม **Postman Desktop** ทดสอบกับ Mock API สาธารณะจาก [JSONPlaceholder](https://jsonplaceholder.typicode.com/)
##รายการคำขอที่ทดสอบ (CRUD Operations)

| Method | Request Name | Endpoint | รายละเอียด / ผลลัพธ์ |
| :--- | :--- | :--- | :--- |
| **GET** | `Get data` | `/posts/1` | ดึงข้อมูลโพสต์ที่ 1 (`Status: 200 OK`) |
| **POST** | `Post data` | `/posts` | สร้างโพสต์ใหม่พร้อมแนบ JSON Body (`Status: 201 Created`) |
| **PUT** | `Put` | `/posts/1` | อัปเดตแทนที่ข้อมูลเดิมทั้งชุด (`Status: 200 OK`) |
| **PATCH** | `Patch` | `/posts/1` | แก้ไขข้อมูลเฉพาะฟิลด์ (`Status: 200 OK`) |
| **DELETE** | `Delete` | `/posts/1` | ลบข้อมูลโพสต์ที่ระบุ (`Status: 200 OK`) |


## การจำลองสถานการณ์ข้อผิดพลาด (Gotchas & Error Cases)
ได้ทำการทดลองสร้าง Error จริง 3 รูปแบบเพื่อทำความเข้าใจการอ่าน HTTP Status Code:
1. **`404 Not Found` (GET):** เรียกดู Resource ID ที่ไม่มีอยู่จริง (`/posts/999999`)
2. **`404 Not Found` (POST):** ส่งคำขอไปยัง Endpoint ที่สะกด Path ผิด (`/posts/postsaaa`)
3. **`500 Internal Server Error` (PUT):** ส่งคำขอ PUT ด้วย ID ที่ระบบไม่รองรับ จนเซิร์ฟเวอร์เกิด Exception (`TypeError: Cannot read properties of undefined`)


## วิธีนำ Collection ไปรันบน Postman
1. ดาวน์โหลดไฟล์ `rest api + postman.json` จากหน้านี้ลงเครื่อง
2. เปิดโปรแกรม **Postman**
3. กดปุ่ม **Import** ที่มุมซ้ายบน แล้วลากไฟล์ `.json` เข้าไป
4. จะได้โฟลเดอร์ **My Collection** พร้อมคำสั่งทั้งหมดไปกด Send ทดสอบได้ทันที
