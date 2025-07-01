# Multiple Choice Questions - Database Management
# คำถามแบบเลือกตอบ - การจัดการฐานข้อมูล

## Junior Level (Junior Developer - 0-2 years)

### Question 1 / คำถามที่ 1
**EN:** What does SQL stand for?
**TH:** SQL ย่อมาจากอะไร?

A) Structured Query Language / ภาษาคิวรีที่มีโครงสร้าง
B) Simple Query Language / ภาษาคิวรีอย่างง่าย
C) Standard Query Language / ภาษาคิวรีมาตรฐาน
D) Secure Query Language / ภาษาคิวรีที่ปลอดภัย

**Answer:** A
**Explanation / คำอธิบาย:**
- EN: SQL stands for Structured Query Language, used for managing relational databases
- TH: SQL ย่อมาจาก Structured Query Language ใช้สำหรับจัดการฐานข้อมูลเชิงสัมพันธ์

### Question 2 / คำถามที่ 2
**EN:** Which SQL command is used to retrieve data from a database?
**TH:** คำสั่ง SQL ใดที่ใช้ดึงข้อมูลจากฐานข้อมูล?

A) INSERT
B) UPDATE
C) SELECT
D) DELETE

**Answer:** C
**Explanation / คำอธิบาย:**
- EN: SELECT is used to query and retrieve data from database tables
- TH: SELECT ใช้สำหรับสอบถามและดึงข้อมูลจากตารางฐานข้อมูล

### Question 3 / คำถามที่ 3
**EN:** What is a primary key in a database table?
**TH:** Primary key ในตารางฐานข้อมูลคือ?

A) The first column in a table / คอลัมน์แรกในตาราง
B) A unique identifier for each row / ตัวระบุเฉพาะสำหรับแต่ละแถว
C) The largest value in a table / ค่าที่ใหญ่ที่สุดในตาราง
D) A password for database access / รหัสผ่านสำหรับเข้าถึงฐานข้อมูล

**Answer:** B
**Explanation / คำอธิบาย:**
- EN: A primary key uniquely identifies each record in a database table and ensures no duplicate rows
- TH: Primary key เป็นตัวระบุเฉพาะของแต่ละระเบียนในตารางฐานข้อมูลและป้องกันแถวที่ซ้ำกัน

## Mid Level (Mid-level Developer - 2-5 years)

### Question 4 / คำถามที่ 4
**EN:** What is the purpose of database indexing?
**TH:** จุดประสงค์ของการทำ index ฐานข้อมูลคือ?

A) To backup data / เพื่อสำรองข้อมูล
B) To improve query performance / เพื่อปรับปรุงประสิทธิภาพของคิวรี
C) To encrypt sensitive data / เพื่อเข้ารหัสข้อมูลที่สำคัญ
D) To compress database files / เพื่ออัดไฟล์ฐานข้อมูล

**Answer:** B
**Explanation / คำอธิบาย:**
- EN: Database indexes create shortcuts to data locations, significantly improving query performance, especially for SELECT operations
- TH: Database index สร้างทางลัดไปยังตำแหน่งข้อมูล ช่วยปรับปรุงประสิทธิภาพของคิวรีอย่างมาก โดยเฉพาะการดำเนินการ SELECT

### Question 5 / คำถามที่ 5
**EN:** What is a database transaction?
**TH:** Database transaction คือ?

A) A single SQL statement / คำสั่ง SQL เดียว
B) A group of SQL operations that execute as a single unit / กลุ่มของการดำเนินการ SQL ที่ทำงานเป็นหน่วยเดียว
C) A database backup process / กระบวนการสำรองฐานข้อมูล
D) A user login session / เซสชันการเข้าสู่ระบบของผู้ใช้

**Answer:** B
**Explanation / คำอธิบาย:**
- EN: A transaction is a logical unit of work that contains one or more SQL statements, following ACID properties
- TH: Transaction เป็นหน่วยงานเชิงตรรกะที่ประกอบด้วยคำสั่ง SQL หนึ่งหรือหลายคำสั่ง โดยเป็นไปตามคุณสมบัติ ACID

### Question 6 / คำถามที่ 6
**EN:** What does ACID stand for in database systems?
**TH:** ACID ย่อมาจากอะไรในระบบฐานข้อมูล?

A) Atomicity, Consistency, Isolation, Durability / ความเป็นอะตอม, ความสอดคล้อง, การแยก, ความทนทาน
B) Authentication, Consistency, Integration, Database / การรับรองตัวตน, ความสอดคล้อง, การรวม, ฐานข้อมูล
C) Availability, Consistency, Integrity, Durability / ความพร้อมใช้, ความสอดคล้อง, ความสมบูรณ์, ความทนทาน
D) Access, Control, Information, Database / การเข้าถึง, การควบคุม, ข้อมูล, ฐานข้อมูล

**Answer:** A
**Explanation / คำอธิบาย:**
- EN: ACID properties ensure reliable database transactions: Atomicity (all or nothing), Consistency (valid state), Isolation (concurrent execution), Durability (permanent changes)
- TH: คุณสมบัติ ACID ช่วยให้ transaction ของฐานข้อมูลเชื่อถือได้: Atomicity (ทั้งหมดหรือไม่เลย), Consistency (สถานะที่ถูกต้อง), Isolation (การทำงานพร้อมกัน), Durability (การเปลี่ยนแปลงถาวร)

## Senior Level (Senior Developer - 5+ years)

### Question 7 / คำถามที่ 7
**EN:** When would you choose a NoSQL database over a relational database?
**TH:** คุณจะเลือกฐานข้อมูล NoSQL แทนฐานข้อมูลเชิงสัมพันธ์เมื่อไร?

A) When you need ACID compliance / เมื่อต้องการความสอดคล้องกับ ACID
B) When you have complex relationships between data / เมื่อมีความสัมพันธ์ที่ซับซ้อนระหว่างข้อมูล
C) When you need horizontal scalability and flexible schema / เมื่อต้องการความสามารถในการขยายแนวนอนและ schema ที่ยืดหยุ่น
D) When you have small amounts of data / เมื่อมีข้อมูลจำนวนน้อย

**Answer:** C
**Explanation / คำอธิบาย:**
- EN: NoSQL databases excel at horizontal scaling, handling large volumes of unstructured data, and providing schema flexibility for rapidly evolving applications
- TH: ฐานข้อมูล NoSQL เหมาะสำหรับการขยายแนวนอน การจัดการข้อมูลที่ไม่มีโครงสร้างจำนวนมาก และให้ความยืดหยุ่นของ schema สำหรับแอปพลิเคชันที่พัฒนาอย่างรวดเร็ว

### Question 8 / คำถามที่ 8
**EN:** What is database sharding?
**TH:** Database sharding คือ?

A) Creating backup copies of data / การสร้างสำเนาสำรองของข้อมูล
B) Encrypting sensitive database information / การเข้ารหัสข้อมูลที่สำคัญในฐานข้อมูล
C) Horizontally partitioning data across multiple databases / การแบ่งข้อมูลแนวนอนผ่านฐานข้อมูลหลายฐาน
D) Compressing database files to save space / การอัดไฟล์ฐานข้อมูลเพื่อประหยัดพื้นที่

**Answer:** C
**Explanation / คำอธิบาย:**
- EN: Sharding is a database architecture pattern that horizontally partitions data across multiple database instances to improve scalability and performance
- TH: Sharding เป็นรูปแบบสถาปัตยกรรมฐานข้อมูลที่แบ่งข้อมูลแนวนอนผ่าน database instance หลายตัวเพื่อปรับปรุงความสามารถในการขยายและประสิทธิภาพ

### Question 9 / คำถามที่ 9
**EN:** What is the difference between optimistic and pessimistic locking?
**TH:** ความแตกต่างระหว่าง optimistic locking และ pessimistic locking คือ?

A) Optimistic assumes conflicts won't occur, pessimistic assumes they will / Optimistic สมมติว่าจะไม่มีความขัดแย้ง, pessimistic สมมติว่าจะมี
B) Optimistic is faster, pessimistic is slower / Optimistic เร็วกว่า, pessimistic ช้ากว่า
C) They are the same thing / เป็นสิ่งเดียวกัน
D) Optimistic works with NoSQL, pessimistic works with SQL / Optimistic ทำงานกับ NoSQL, pessimistic ทำงานกับ SQL

**Answer:** A
**Explanation / คำอธิบาย:**
- EN: Optimistic locking assumes conflicts are rare and checks for conflicts only when committing. Pessimistic locking prevents conflicts by locking resources immediately
- TH: Optimistic locking สมมติว่าความขัดแย้งเกิดขึ้นน่อยและตรวจสอบความขัดแย้งเฉพาะเมื่อ commit Pessimistic locking ป้องกันความขัดแย้งโดยการล็อกทรัพยากรทันที

---

**Time Allocation / การจัดสรรเวลา:**
- Junior: 2-3 minutes per question / 2-3 นาทีต่อคำถาม
- Mid-level: 3-4 minutes per question / 3-4 นาทีต่อคำถาม
- Senior: 4-5 minutes per question / 4-5 นาทีต่อคำถาม

**Topics Covered / หัวข้อที่ครอบคลุม:**
- Basic SQL operations / การดำเนินการ SQL พื้นฐาน
- Database design principles / หลักการออกแบบฐานข้อมูล
- Performance optimization / การปรับปรุงประสิทธิภาพ
- Transaction management / การจัดการ transaction
- Advanced database concepts / แนวคิดฐานข้อมูลขั้นสูง
