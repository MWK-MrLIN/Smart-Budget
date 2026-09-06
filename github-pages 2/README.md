# Smart Budget & Smart Fridge บน GitHub Pages

โฟลเดอร์นี้เป็นหน้าเว็บตัวครอบสำหรับ GitHub Pages โดยฝัง Google Apps Script Web App ผ่าน `<iframe>`

> Google Apps Script ยังคงเป็น Backend หลัก ดังนั้นระบบยังใช้ `google.script.run` และยังบันทึกข้อมูลลง Google ชีตเดิมได้

## วิธีใช้งาน

สร้างหรือเปิด GitHub repository ที่ต้องการใช้ จากนั้นอัปโหลดไฟล์ `index.html` ในโฟลเดอร์นี้ไปไว้ที่ root ของ repository แล้วไปที่ **Settings → Pages** เลือก **Deploy from a branch** เลือก branch `main` และโฟลเดอร์ `/root` จากนั้นกด Save

หลัง GitHub สร้างเว็บไซต์แล้ว URL จะมีลักษณะดังนี้:

```text
https://ชื่อผู้ใช้.github.io/ชื่อ-repository/
```

หน้า GitHub จะโหลด Web App จาก URL นี้:

```text
https://script.google.com/macros/s/AKfycbxA7FWPivO7gdWGS3uqEA48QzAel3PdB87ZH4xfiU8dnCO2MKh_hAxWrPxRCpJMhPz8TA/exec
```

## เงื่อนไขสำคัญ

ต้องตั้งค่า Deployment ของ Apps Script เป็น Web App ที่ผู้ใช้งานมีสิทธิ์เข้าถึงได้ตามที่ต้องการ และต้องเปิด **Who has access** ให้เหมาะสม หากตั้งให้เฉพาะผู้ใช้ที่ล็อกอิน ระบบจะยังขอให้ผู้ใช้ล็อกอิน Google เมื่อเปิดจาก GitHub Pages

ถ้าแก้ไข `Index.html` หรือ `รหัส.gs` ใน Apps Script ต้องสร้าง Deployment เวอร์ชันใหม่ ส่วนหน้า GitHub Pages จะยังใช้ URL `/exec` เดิมและจะโหลดโค้ด Web App เวอร์ชันล่าสุดที่ Deploy แล้ว

## ข้อจำกัดของวิธีนี้

GitHub Pages ทำหน้าที่เป็นหน้าแสดงผลเท่านั้น ไม่ได้ย้าย Backend หรือฐานข้อมูลออกจาก Google Apps Script หากเปิดไฟล์ `index.html` จากเครื่องโดยตรงด้วย `file://` อาจไม่ใช่สภาพแวดล้อมเดียวกับ GitHub Pages จึงควรทดสอบผ่าน URL GitHub Pages จริง
