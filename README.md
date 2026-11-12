# 🎮 MINEDRONE: Drone Log Web (Assignment #2)

เว็บไซต์สำหรับดูการตั้งค่า (Config) ของโดรน บันทึกอุณหภูมิ และดูประวัติ log ย้อนหลัง ซึ่งออกแบบหน้าตา User Interface (UI) ในสไตล์เกมพิกเซลอาร์ต (Pixel Art)[cite: 7]

**Deployment:** [https://chanidaphaboonyubon.github.io/AssignmentWebApp_2/](https://chanidaphaboonyubon.github.io/AssignmentWebApp_2/)

**Code main:** [https://github.com/ChanidaphaBoonyubon/AssignmentWebApp_2.git](https://github.com/ChanidaphaBoonyubon/AssignmentWebApp_2.git)

## 🌟 ฟีเจอร์หลัก

* **ดู Config (View Config):** หน้าแสดงโปรไฟล์ของโดรน โดยจะดึงข้อมูลชื่อ, หมายเลข ID, สถานะไฟแสดงผล, และชื่อประเทศมาจัดแสดงในรูปแบบการ์ด[cite: 8]
* **บันทึกอุณหภูมิ (Add Temperature Log):** หน้าสำหรับป้อนข้อมูลอุณหภูมิ (หน่วยองศาเซลเซียส) เพื่อส่งเข้าระบบ มาพร้อมแถบสไลด์และปุ่มเลือกค่าด่วน (10, 20, 40, 60, 80) เพื่อความรวดเร็วในการกรอก[cite: 9]
* **ดูประวัติ (View Logs):** หน้าแสดงผลข้อมูลประวัติการบันทึกอุณหภูมิในรูปแบบตารางที่อ่านง่าย พร้อมระบุวันที่และเวลาที่บันทึกข้อมูลอย่างชัดเจน[cite: 10]

---

## ⚙️ การตั้งค่าระบบ (Configuration)

ก่อนเริ่มต้นใช้งาน ให้เข้าไปแก้ไขค่าตัวแปรที่ต้นไฟล์ `script.js` เพื่อกำหนดเป้าหมายการเชื่อมต่อ:

```javascript
const API_BASE = '...';      // ระบุ URL ของ API Server
const DRONE_ID = '67010174'; // ระบุหมายเลข ID ของโดรนเป้าหมาย

## 💻 วิธีรันกรณี localhost

1. ติดตั้ง Node.js 18 ขึ้นไป
2. เปิดโฟลเดอร์ใน VS Code แล้วสร้าง Terminal โดยใช้ Command Prompt แล้วรันคำสั่ง:
   ```bash
   npm install
   ```
3. สร้างไฟล์ `.env` ในโฟลเดอร์เดียวกัน แล้วใส่ค่าจริงลงไป:
   ```env
   PORT=3000
   CONFIG_URL=<URL Config Drone Server ของ>
   LOG_URL=<URL Drone Log Server ของ>
   LOG_API_TOKEN=<Bearer token>
   ```
4. เริ่มการทำงานของเซิร์ฟเวอร์ด้วยคำสั่ง:
   ```bash
   npm start
   ```
5. ใช้ส่วนเสริม **Live Server** กด Go Live ที่ไฟล์ `index.html`