# Multiple Choice Questions - Core Programming Concepts
# คำถามแบบเลือกตอบ - แนวคิดการเขียนโปรแกรมพื้นฐาน

## Junior Level (Junior Developer - 0-2 years)

### Question 1 / คำถามที่ 1
**EN:** What is the difference between `==` and `===` in JavaScript?
**TH:** ความแตกต่างระหว่าง `==` และ `===` ใน JavaScript คือ?

A) `==` compares value, `===` compares type / `==` เปรียบเทียบค่า, `===` เปรียบเทียบประเภท
B) `==` compares value and type, `===` compares only value / `==` เปรียบเทียบค่าและประเภท, `===` เปรียบเทียบแค่ค่า  
C) `===` compares value and type, `==` compares only value / `===` เปรียบเทียบค่าและประเภท, `==` เปรียบเทียบแค่ค่า
D) No difference / ไม่มีความแตกต่าง

**Answer:** C
**Explanation / คำอธิบาย:** 
- EN: `===` (strict equality) compares both value and type, while `==` (loose equality) only compares value after type coercion
- TH: `===` (เท่ากันอย่างเข้มงวด) เปรียบเทียบทั้งค่าและประเภท ขณะที่ `==` (เท่ากันแบบหลวม) เปรียบเทียบเฉพาะค่าหลังจากแปลงประเภท

### Question 2 / คำถามที่ 2
**EN:** What is the purpose of an API?
**TH:** จุดประสงค์ของ API คือ?

A) To design user interfaces / เพื่อออกแบบส่วนติดต่อผู้ใช้
B) To allow communication between different software systems / เพื่อให้ระบบซอฟต์แวร์ต่างๆ สื่อสารกันได้
C) To store data in databases / เพื่อเก็บข้อมูลในฐานข้อมูล
D) To create mobile applications / เพื่อสร้างแอปพลิเคชันมือถือ

**Answer:** B
**Explanation / คำอธิบาย:**
- EN: API (Application Programming Interface) serves as an intermediary that allows different software applications to communicate with each other
- TH: API (Application Programming Interface) ทำหน้าที่เป็นตัวกลางที่ให้แอปพลิเคชันซอฟต์แวร์ต่างๆ สื่อสารกันได้

### Question 3 / คำถามที่ 3
**EN:** Which HTTP status code indicates "Not Found"?
**TH:** รหัสสถานะ HTTP ใดที่หมายถึง "ไม่พบ"?

A) 200
B) 404
C) 500
D) 301

**Answer:** B
**Explanation / คำอธิบาย:**
- EN: HTTP 404 status code indicates that the server cannot find the requested resource
- TH: รหัสสถานะ HTTP 404 หมายถึงเซิร์ฟเวอร์ไม่สามารถค้นหาทรัพยากรที่ร้องขอได้

## Mid Level (Mid-level Developer - 2-5 years)

### Question 4 / คำถามที่ 4
**EN:** What is the main advantage of using connection pooling in database operations?
**TH:** ข้อดีหลักของการใช้ connection pooling ในการดำเนินการฐานข้อมูลคือ?

A) Improved security / ความปลอดภัยที่ดีขึ้น
B) Better performance by reusing connections / ประสิทธิภาพที่ดีขึ้นโดยการใช้การเชื่อมต่อซ้ำ
C) Automatic data backup / การสำรองข้อมูลอัตโนมัติ
D) Enhanced data encryption / การเข้ารหัสข้อมูลที่ดีขึ้น

**Answer:** B
**Explanation / คำอธิบาย:**
- EN: Connection pooling improves performance by maintaining a pool of reusable database connections, reducing the overhead of establishing new connections
- TH: Connection pooling ช่วยปรับปรุงประสิทธิภาพโดยการรักษาพูลของการเชื่อมต่อฐานข้อมูลที่ใช้ซ้ำได้ ลดการใช้ทรัพยากรในการสร้างการเชื่อมต่อใหม่

### Question 5 / คำถามที่ 5
**EN:** What is the difference between SQL and NoSQL databases?
**TH:** ความแตกต่างระหว่างฐานข้อมูล SQL และ NoSQL คือ?

A) SQL is faster than NoSQL / SQL เร็วกว่า NoSQL
B) SQL uses structured data with fixed schema, NoSQL uses flexible schema / SQL ใช้ข้อมูลที่มีโครงสร้างกับ schema คงที่, NoSQL ใช้ schema ที่ยืดหยุ่น
C) NoSQL only works with small datasets / NoSQL ทำงานได้แค่กับชุดข้อมูลเล็ก
D) They are the same thing / พวกมันเป็นสิ่งเดียวกัน

**Answer:** B
**Explanation / คำอธิบาย:**
- EN: SQL databases use structured data with predefined schemas and ACID properties, while NoSQL databases offer flexible schemas and are designed for specific use cases
- TH: ฐานข้อมูล SQL ใช้ข้อมูลที่มีโครงสร้างพร้อม schema ที่กำหนดไว้ล่วงหน้าและคุณสมบัติ ACID ขณะที่ฐานข้อมูล NoSQL มี schema ที่ยืดหยุ่นและออกแบบมาสำหรับกรณีการใช้งานเฉพาะ

## Senior Level (Senior Developer - 5+ years)

### Question 6 / คำถามที่ 6
**EN:** Which design pattern would you use to ensure only one instance of a class exists throughout the application lifecycle?
**TH:** คุณจะใช้ design pattern ใดเพื่อให้แน่ใจว่ามีเพียง instance เดียวของ class ที่มีอยู่ตลอดวงจรชีวิตของแอปพลิเคชัน?

A) Factory Pattern
B) Observer Pattern  
C) Singleton Pattern
D) Strategy Pattern

**Answer:** C
**Explanation / คำอธิบาย:**
- EN: Singleton pattern ensures that only one instance of a class is created and provides global access to that instance
- TH: Singleton pattern ช่วยให้แน่ใจว่ามีการสร้าง instance เพียงตัวเดียวของ class และให้การเข้าถึงแบบ global ไปยัง instance นั้น

### Question 7 / คำถามที่ 7
**EN:** What is the CAP theorem in distributed systems?
**TH:** CAP theorem ในระบบกระจาย (distributed systems) คือ?

A) Consistency, Availability, Performance / ความสอดคล้อง, ความพร้อมใช้งาน, ประสิทธิภาพ
B) Consistency, Availability, Partition tolerance / ความสอดคล้อง, ความพร้อมใช้งาน, ความทนทานต่อการแบ่งแยก
C) Concurrency, Atomicity, Performance / การทำงานพร้อมกัน, ความเป็นอะตอม, ประสิทธิภาพ
D) Caching, Authentication, Performance / การแคช, การรับรองตัวตน, ประสิทธิภาพ

**Answer:** B
**Explanation / คำอธิบาย:**
- EN: CAP theorem states that in a distributed system, you can only guarantee two out of three: Consistency, Availability, and Partition tolerance
- TH: CAP theorem ระบุว่าในระบบกระจาย คุณสามารถรับประกันได้เพียงสองใน tiga: ความสอดคล้อง ความพร้อมใช้งาน และความทนทานต่อการแบ่งแยก

---

**Time Allocation / การจัดสรรเวลา:**
- Junior: 2-3 minutes per question / 2-3 นาทีต่อคำถาม
- Mid-level: 3-4 minutes per question / 3-4 นาทีต่อคำถาม  
- Senior: 4-5 minutes per question / 4-5 นาทีต่อคำถาม
