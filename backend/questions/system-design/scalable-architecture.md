# System Design Questions - Scalable Architecture
# คำถามการออกแบบระบบ - สถาปัตยกรรมที่ขยายได้

## Mid Level (2-5 years experience)

### Design Challenge 1: URL Shortener Service / ความท้าทายการออกแบบที่ 1: บริการย่อ URL

**EN:** Design a URL shortening service like bit.ly or tinyurl.com

**TH:** ออกแบบบริการย่อ URL เช่น bit.ly หรือ tinyurl.com

#### Requirements / ความต้องการ:

**Functional Requirements / ความต้องการด้านการทำงาน:**
- EN: 
  - Shorten long URLs to shorter aliases
  - Redirect short URLs to original URLs
  - Custom aliases (optional)
  - Analytics (click tracking)
  - URL expiration

- TH:
  - ย่อ URL ยาวให้เป็นชื่อแทนที่สั้น
  - เปลี่ยนเส้นทาง URL สั้นไปยัง URL เดิม
  - ชื่อแทนที่กำหนดเอง (ตัวเลือก)
  - การวิเคราะห์ (การติดตามการคลิก)
  - การหมดอายุของ URL

**Non-Functional Requirements / ความต้องการด้านไม่ใช่การทำงาน:**
- EN:
  - 100:1 read/write ratio
  - 100M URLs shortened per month
  - Low latency for redirects (<100ms)
  - 99.9% availability

- TH:
  - อัตราส่วนการอ่าน/เขียน 100:1
  - ย่อ URL 100 ล้านครั้งต่อเดือน
  - ความหน่วงต่ำสำหรับการเปลี่ยนเส้นทาง (<100ms)
  - ความพร้อมใช้งาน 99.9%

#### Design Areas to Cover / ด้านการออกแบบที่ต้องครอบคลุม:

1. **High-Level Architecture / สถาปัตยกรรมระดับสูง**
2. **Database Design / การออกแบบฐานข้อมูล**
3. **Algorithm for URL Encoding / อัลกอริทึมสำหรับการเข้ารหัส URL**
4. **Caching Strategy / กลยุทธ์การแคช**
5. **Load Balancing / การกระจายโหลด**

**Expected Discussion Points / จุดอภิปรายที่คาดหวัง:**
- Base62 encoding vs. counter-based approach
- Database partitioning/sharding strategy
- Cache layer design (Redis/Memcached)
- Rate limiting and security considerations
- Analytics data storage and processing

**Time Allocation / การจัดสรรเวลา:** 45 minutes

---

### Design Challenge 2: Chat Application / ความท้าทายการออกแบบที่ 2: แอปพลิเคชันแชท

**EN:** Design a real-time chat application like WhatsApp or Slack

**TH:** ออกแบบแอปพลิเคชันแชทแบบเรียลไทม์เช่น WhatsApp หรือ Slack

#### Requirements / ความต้องการ:

**Functional Requirements / ความต้องการด้านการทำงาน:**
- EN:
  - Send and receive messages in real-time
  - One-on-one and group conversations
  - Message history and search
  - Online/offline status
  - Message delivery status

- TH:
  - ส่งและรับข้อความแบบเรียลไทม์
  - การสนทนาแบบตัวต่อตัวและกลุ่ม
  - ประวัติข้อความและการค้นหา
  - สถานะออนไลน์/ออฟไลน์
  - สถานะการส่งข้อความ

**Scale Requirements / ความต้องการด้านขนาด:**
- EN:
  - 50M daily active users
  - Each user sends 40 messages per day
  - Support for groups up to 100 members

- TH:
  - ผู้ใช้งานใช้งานรายวัน 50 ล้านคน
  - ผู้ใช้แต่ละคนส่งข้อความ 40 ข้อความต่อวัน
  - รองรับกลุ่มสมาชิกได้ถึง 100 คน

#### Design Areas to Cover / ด้านการออกแบบที่ต้องครอบคลุม:

1. **Real-time Communication / การสื่อสารแบบเรียลไทม์**
2. **Message Storage / การเก็บข้อความ**
3. **User Management / การจัดการผู้ใช้**
4. **Notification System / ระบบการแจ้งเตือน**
5. **Mobile Considerations / การพิจารณาสำหรับมือถือ**

**Time Allocation / การจัดสรรเวลา:** 45 minutes

---

## Senior Level (5+ years experience)

### Design Challenge 3: Social Media Feed / ความท้าทายการออกแบบที่ 3: ฟีดโซเชียลมีเดีย

**EN:** Design a social media news feed system like Facebook or Twitter

**TH:** ออกแบบระบบฟีดข่าวโซเชียลมีเดียเช่น Facebook หรือ Twitter

#### Requirements / ความต้องการ:

**Functional Requirements / ความต้องการด้านการทำงาน:**
- EN:
  - Users can post updates (text, images, videos)
  - Users can follow other users
  - Generate personalized news feed
  - Like, comment, and share posts
  - Real-time notifications

- TH:
  - ผู้ใช้สามารถโพสต์อัปเดต (ข้อความ รูปภาพ วิดีโอ)
  - ผู้ใช้สามารถติดตามผู้ใช้อื่น
  - สร้างฟีดข่าวส่วนบุคคล
  - กดไลค์ แสดงความคิดเห็น และแชร์โพสต์
  - การแจ้งเตือนแบบเรียลไทม์

**Scale Requirements / ความต้องการด้านขนาด:**
- EN:
  - 1B registered users, 300M daily active users
  - Each user follows 200 people on average
  - 300M posts per day
  - Feed generation should be under 200ms

- TH:
  - ผู้ใช้ลงทะเบียน 1 พันล้านคน ผู้ใช้งานรายวัน 300 ล้านคน
  - ผู้ใช้แต่ละคนติดตาม 200 คนโดยเฉลี่ย
  - โพสต์ 300 ล้านโพสต์ต่อวัน
  - การสร้างฟีดควรใช้เวลาไม่เกิน 200ms

#### Advanced Design Considerations / การพิจารณาการออกแบบขั้นสูง:

1. **Feed Generation Algorithms / อัลกอริทึมการสร้างฟีด**
   - Pull vs Push vs Hybrid model
   - Content ranking and personalization
   - Machine learning integration

2. **Data Storage Strategy / กลยุทธ์การเก็บข้อมูล**
   - User data partitioning
   - Timeline data storage
   - Media storage (CDN strategy)

3. **Performance Optimization / การปรับปรุงประสิทธิภาพ**
   - Multi-level caching
   - Database optimization
   - Content delivery networks

4. **Reliability & Consistency / ความเชื่อถือได้และความสอดคล้อง**
   - Data replication strategy
   - Eventual consistency considerations
   - Disaster recovery

**Time Allocation / การจัดสรรเวลา:** 60 minutes

---

### Design Challenge 4: Distributed Cache System / ความท้าทายการออกแบบที่ 4: ระบบแคชแบบกระจาย

**EN:** Design a distributed caching system like Redis Cluster or Memcached

**TH:** ออกแบบระบบแคชแบบกระจายเช่น Redis Cluster หรือ Memcached

#### Requirements / ความต้องการ:

**Functional Requirements / ความต้องการด้านการทำงาน:**
- EN:
  - GET, PUT, DELETE operations
  - Distributed across multiple nodes
  - Automatic failover and recovery
  - Data expiration (TTL)
  - Consistent hashing for load distribution

- TH:
  - การดำเนินการ GET, PUT, DELETE
  - กระจายข้ามหลายโหนด
  - การสลับและกู้คืนอัตโนมัติ
  - การหมดอายุของข้อมูล (TTL)
  - การแฮชที่สอดคล้องสำหรับการกระจายโหลด

**Performance Requirements / ความต้องการด้านประสิทธิภาพ:**
- EN:
  - Sub-millisecond latency
  - Handle 1M requests per second
  - 99.9% availability
  - Linear scalability

- TH:
  - ความหน่วงต่ำกว่าหนึ่งมิลลิวินาที
  - จัดการคำขอ 1 ล้านครั้งต่อวินาที
  - ความพร้อมใช้งาน 99.9%
  - การขยายแบบเชิงเส้น

#### Advanced Topics / หัวข้อขั้นสูง:

1. **Consistency Models / โมเดลความสอดคล้อง**
2. **Replication Strategies / กลยุทธ์การทำสำเนา**
3. **Conflict Resolution / การแก้ไขความขัดแย้ง**
4. **Network Partitions Handling / การจัดการการแบ่งเครือข่าย**
5. **Monitoring and Observability / การตรวจสอบและความสามารถในการสังเกต**

**Time Allocation / การจัดสรรเวลา:** 60 minutes

---

## Assessment Criteria / เกณฑ์การประเมิน

### Problem Understanding / ความเข้าใจปัญหา (20%)
- **Requirements Clarification / การชี้แจงความต้องการ:** Asks relevant questions to understand requirements
- **Scope Definition / การกำหนดขอบเขต:** Properly defines system boundaries and constraints

### System Architecture / สถาปัตยกรรมระบบ (30%)
- **High-Level Design / การออกแบบระดับสูง:** Clear system components and their interactions
- **Scalability / ความสามารถในการขยาย:** Addresses horizontal and vertical scaling
- **Trade-offs / การแลกเปลี่ยน:** Discusses pros and cons of design decisions

### Technical Depth / ความลึกทางเทคนิค (25%)
- **Database Design / การออกแบบฐานข้อมูล:** Appropriate data modeling and storage solutions
- **Algorithms / อัลกอริทึม:** Efficient algorithms for core functionalities
- **Performance / ประสิทธิภาพ:** Considers latency, throughput, and optimization

### Reliability & Scalability / ความเชื่อถือได้และความสามารถในการขยาย (25%)
- **Fault Tolerance / ความทนทานต่อข้อผิดพลาด:** Handles failures gracefully
- **Consistency / ความสอดคล้อง:** Addresses data consistency requirements
- **Monitoring / การตรวจสอบ:** Includes observability and alerting

---

**Evaluation Guidelines / แนวทางการประเมิน:**

### Excellent (90-100%) / ยอดเยี่ยม
- Comprehensive system design with all major components
- Addresses scalability, reliability, and performance
- Discusses multiple solutions and trade-offs
- Shows deep understanding of distributed systems

### Good (75-89%) / ดี
- Solid system design covering most requirements
- Addresses some scalability and reliability concerns
- Shows good understanding of system components
- Some minor gaps in design or explanation

### Average (60-74%) / ปานกลาง
- Basic system design meeting functional requirements
- Limited discussion of non-functional requirements
- Shows understanding of core concepts
- Missing some important design considerations

### Below Average (<60%) / ต่ำกว่าเกณฑ์
- Incomplete or flawed system design
- Fails to address key requirements
- Limited understanding of system design principles
- Unable to discuss trade-offs or alternatives
