# System Design Questions - Frontend Architecture
# คำถามการออกแบบระบบ - สถาปัตยกรรม Frontend

## Mid Level (2-5 years experience)

### Design Challenge 1: E-commerce Product Listing Page / ความท้าทายการออกแบบที่ 1: หน้ารายการสินค้าอีคอมเมิร์ซ

**EN:** Design a scalable product listing page for an e-commerce website

**TH:** ออกแบบหน้ารายการสินค้าที่ขยายได้สำหรับเว็บไซต์อีคอมเมิร์ซ

#### Requirements / ความต้องการ:

**Functional Requirements / ความต้องการด้านการทำงาน:**
- EN:
  - Display 20 products per page with pagination
  - Filter by category, price range, brand
  - Sort by price, popularity, ratings
  - Search functionality
  - Add to cart functionality
  - Responsive design for mobile/desktop

- TH:
  - แสดงสินค้า 20 รายการต่อหน้าพร้อม pagination
  - กรองตามหมวดหมู่ ช่วงราคา แบรนด์
  - เรียงตามราคา ความนิยม คะแนน
  - ฟังก์ชันการค้นหา
  - ฟังก์ชันเพิ่มลงตะกร้า
  - การออกแบบ responsive สำหรับมือถือ/เดสก์ท็อป

**Performance Requirements / ความต้องการด้านประสิทธิภาพ:**
- EN:
  - Initial page load under 3 seconds
  - Smooth scrolling and filtering
  - Handle 10,000+ products
  - SEO-friendly URLs and meta tags

- TH:
  - การโหลดหน้าแรกภายใน 3 วินาที
  - การเลื่อนและกรองที่ลื่นไหล
  - รองรับสินค้า 10,000+ รายการ
  - URL และ meta tag ที่เป็นมิตรกับ SEO

#### Design Areas to Cover / ด้านการออกแบบที่ต้องครอบคลุม:

1. **Component Architecture / สถาปัตยกรรม Component**
2. **State Management / การจัดการ State**
3. **API Design / การออกแบบ API**
4. **Performance Optimization / การปรับปรุงประสิทธิภาพ**
5. **SEO and Accessibility / SEO และการเข้าถึง**

**Expected Discussion Points / จุดอภิปรายที่คาดหวัง:**
- Virtual scrolling for large lists
- Debouncing for search and filters
- Caching strategies (browser cache, CDN)
- Progressive loading and skeleton screens
- URL state management for bookmarkable filters

**Time Allocation / การจัดสรรเวลา:** 45 minutes

---

### Design Challenge 2: Real-time Chat Interface / ความท้าทายการออกแบบที่ 2: อินเทอร์เฟซแชทแบบเรียลไทม์

**EN:** Design a web-based chat application interface similar to Slack or Discord

**TH:** ออกแบบอินเทอร์เฟซแอปพลิเคชันแชทบนเว็บคล้าย Slack หรือ Discord

#### Requirements / ความต้องการ:

**Functional Requirements / ความต้องการด้านการทำงาน:**
- EN:
  - Real-time message sending and receiving
  - Multiple chat rooms/channels
  - User online/offline status
  - Message history with infinite scroll
  - File upload and image preview
  - Emoji reactions and mentions

- TH:
  - การส่งและรับข้อความแบบเรียลไทม์
  - ห้องแชท/ช่องหลายห้อง
  - สถานะออนไลน์/ออฟไลน์ของผู้ใช้
  - ประวัติข้อความพร้อม infinite scroll
  - อัปโหลดไฟล์และดูตัวอย่างรูปภาพ
  - ปฏิกิริยาอีโมจิและการแท็ก

**Technical Requirements / ความต้องการทางเทคนิค:**
- EN:
  - WebSocket connections for real-time updates
  - Handle connection drops and reconnection
  - Optimistic UI updates
  - Message synchronization across devices

- TH:
  - การเชื่อมต่อ WebSocket สำหรับอัปเดตแบบเรียลไทม์
  - จัดการการขาดการเชื่อมต่อและการเชื่อมต่อใหม่
  - การอัปเดต UI แบบ optimistic
  - การซิงค์ข้อความข้ามอุปกรณ์

#### Design Areas to Cover / ด้านการออกแบบที่ต้องครอบคลุม:

1. **Real-time Communication / การสื่อสารแบบเรียลไทม์**
2. **Message Threading / การจัดลำดับข้อความ**
3. **Connection Management / การจัดการการเชื่อมต่อ**
4. **UI State Synchronization / การซิงค์สถานะ UI**
5. **Mobile Responsiveness / การตอบสนองบนมือถือ**

**Time Allocation / การจัดสรรเวลา:** 45 minutes

---

## Senior Level (5+ years experience)

### Design Challenge 3: Dashboard with Multiple Data Sources / ความท้าทายการออกแบบที่ 3: แดชบอร์ดพร้อมแหล่งข้อมูลหลายแหล่ง

**EN:** Design a business analytics dashboard that aggregates data from multiple APIs

**TH:** ออกแบบแดชบอร์ดวิเคราะห์ธุรกิจที่รวบรวมข้อมูลจาก API หลายตัว

#### Requirements / ความต้องการ:

**Functional Requirements / ความต้องการด้านการทำงาน:**
- EN:
  - Real-time charts and graphs (line, bar, pie, heatmap)
  - Customizable dashboard layout (drag-and-drop widgets)
  - Date range filtering across all widgets
  - Export functionality (PDF, CSV, PNG)
  - User role-based permissions
  - Dashboard sharing and embedding

- TH:
  - แผนภูมิและกราฟแบบเรียลไทม์ (เส้น แท่ง วงกลม ฮีตแมป)
  - เลย์เอาท์แดชบอร์ดที่กำหนดได้ (ลาก-วาง widget)
  - การกรองช่วงวันที่ทั่วทั้ง widget
  - ฟังก์ชันส่งออก (PDF, CSV, PNG)
  - สิทธิ์ตามบทบาทผู้ใช้
  - การแชร์และฝังแดชบอร์ด

**Performance Requirements / ความต้องการด้านประสิทธิภาพ:**
- EN:
  - Handle 50+ concurrent API calls
  - Dashboard loads within 5 seconds
  - Smooth interactions with large datasets (100K+ records)
  - Memory-efficient chart rendering
  - Auto-refresh without performance degradation

- TH:
  - รองรับการเรียก API พร้อมกัน 50+ ครั้ง
  - แดชบอร์ดโหลดภายใน 5 วินาที
  - การโต้ตอบที่ลื่นไหลกับชุดข้อมูลขนาดใหญ่ (100K+ ระเบียน)
  - การเรนเดอร์แผนภูมิที่มีประสิทธิภาพด้านหน่วยความจำ
  - การรีเฟรชอัตโนมัติโดยไม่ลดประสิทธิภาพ

#### Advanced Design Considerations / การพิจารณาการออกแบบขั้นสูง:

1. **Data Flow Architecture / สถาปัตยกรรมการไหลของข้อมูล**
   - Multiple API integration strategies
   - Data transformation and normalization
   - Caching layers (Redis, browser cache)
   - Error handling and retry mechanisms

2. **State Management / การจัดการ State**
   - Global state for dashboard configuration
   - Widget-level state isolation
   - Undo/redo functionality
   - Persistent dashboard layouts

3. **Performance Optimization / การปรับปรุงประสิทธิภาพ**
   - Virtual scrolling for large datasets
   - Chart data sampling and aggregation
   - Webworkers for heavy computations
   - Progressive data loading

4. **User Experience / ประสบการณ์ผู้ใช้**
   - Skeleton loading states
   - Contextual help and tooltips
   - Keyboard shortcuts
   - Accessibility compliance (WCAG)

**Time Allocation / การจัดสรรเวลา:** 60 minutes

---

### Design Challenge 4: Micro-frontend Architecture / ความท้าทายการออกแบบที่ 4: สถาปัตยกรรม Micro-frontend

**EN:** Design a micro-frontend architecture for a large-scale web application

**TH:** ออกแบบสถาปัตยกรรม micro-frontend สำหรับเว็บแอปพลิเคชันขนาดใหญ่

#### Requirements / ความต้องการ:

**System Requirements / ความต้องการของระบบ:**
- EN:
  - 5+ independent teams working on different features
  - Different technology stacks (React, Vue, Angular)
  - Shared components and design system
  - Independent deployment of micro-frontends
  - SEO and performance optimization
  - Cross-team communication and shared state

- TH:
  - ทีมอิสระ 5+ ทีมทำงานบนฟีเจอร์ต่างๆ
  - เทคโนโลยีสแต็กที่แตกต่างกัน (React, Vue, Angular)
  - component และ design system ที่แชร์ใช้
  - การ deploy micro-frontend แบบอิสระ
  - การปรับปรุง SEO และประสิทธิภาพ
  - การสื่อสารข้ามทีมและ shared state

**Technical Challenges / ความท้าทายทางเทคนิค:**
- EN:
  - Bundle size optimization
  - Runtime integration patterns
  - Shared dependency management
  - Cross-application routing
  - Testing strategies across micro-frontends
  - CI/CD pipeline coordination

- TH:
  - การปรับปรุงขนาด bundle
  - รูปแบบการรวมระหว่างรันไทม์
  - การจัดการ dependency ที่แชร์ใช้
  - การกำหนดเส้นทางข้ามแอปพลิเคชัน
  - กลยุทธ์การทดสอบข้าม micro-frontend
  - การประสานงาน CI/CD pipeline

#### Advanced Topics / หัวข้อขั้นสูง:

1. **Integration Patterns / รูปแบบการรวม**
   - Build-time vs Runtime integration
   - Module Federation (Webpack 5)
   - Server-side composition
   - Edge-side includes (ESI)

2. **Governance and Standards / การกำกับดูแลและมาตรฐาน**
   - API contracts between micro-frontends
   - Design system enforcement
   - Performance budgets
   - Security boundaries

3. **DevOps and Deployment / DevOps และการ Deploy**
   - Independent CI/CD pipelines
   - Feature flags and canary deployments
   - Monitoring and observability
   - Rollback strategies

4. **Performance Considerations / การพิจารณาประสิทธิภาพ**
   - Code splitting strategies
   - Shared vendor chunks
   - Critical path optimization
   - Progressive loading patterns

**Time Allocation / การจัดสรรเวลา:** 60 minutes

---

## Assessment Criteria / เกณฑ์การประเมิน

### System Understanding / ความเข้าใจระบบ (25%)
- **Problem Analysis / การวิเคราะห์ปัญหา:** Clear understanding of requirements and constraints
- **User Experience Focus / การมุ่งเน้นประสบการณ์ผู้ใช้:** Considers end-user needs and workflows
- **Technical Feasibility / ความเป็นไปได้ทางเทคนิค:** Realistic solutions within technical constraints

### Architecture Design / การออกแบบสถาปัตยกรรม (25%)
- **Component Structure / โครงสร้าง Component:** Well-organized, reusable component hierarchy
- **Data Flow / การไหลของข้อมูล:** Efficient data management and state flow
- **API Integration / การรวม API:** Smart API design and integration patterns

### Technical Depth / ความลึกทางเทคนิค (25%)
- **Modern Frontend Practices / แนวปฏิบัติ Frontend สมัยใหม่:** Uses current best practices and patterns
- **Performance Optimization / การปรับปรุงประสิทธิภาพ:** Identifies bottlenecks and optimization strategies
- **Security Considerations / การพิจารณาความปลอดภัย:** Addresses security concerns appropriately

### Scalability & Maintainability / ความสามารถในการขยายและบำรุงรักษา (25%)
- **Code Organization / การจัดระเบียบโค้ด:** Maintainable and scalable code structure
- **Testing Strategy / กลยุทธ์การทดสอบ:** Comprehensive testing approach
- **Documentation / เอกสารประกอบ:** Clear documentation and knowledge sharing

---

**Evaluation Guidelines / แนวทางการประเมิน:**

### Excellent (90-100%) / ยอดเยี่ยม
- Comprehensive solution addressing all requirements
- Demonstrates deep understanding of frontend architecture
- Considers performance, security, and accessibility
- Shows experience with modern frontend ecosystem

### Good (75-89%) / ดี
- Solid solution meeting most requirements
- Good understanding of frontend principles
- Some consideration of non-functional requirements
- Shows familiarity with common patterns

### Average (60-74%) / ปานกลาง
- Basic solution meeting core requirements
- Limited discussion of architecture trade-offs
- Focuses mainly on functional requirements
- Shows basic frontend knowledge

### Below Average (<60%) / ต่ำกว่าเกณฑ์
- Incomplete or flawed solution
- Limited understanding of frontend architecture
- Fails to address key requirements
- Shows gaps in fundamental knowledge
