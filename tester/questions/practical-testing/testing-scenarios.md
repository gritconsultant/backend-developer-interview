# Practical Testing Scenarios
# สถานการณ์การทดสอบจริง

## Junior Level Scenarios (0-2 years experience)

### Scenario 1: E-commerce Login Testing / สถานการณ์ที่ 1: การทดสอบการเข้าสู่ระบบ E-commerce

**EN:** You are testing the login functionality of an e-commerce website. Write test cases for the following scenarios:

**TH:** คุณกำลังทดสอบการทำงานของการเข้าสู่ระบบของเว็บไซต์ e-commerce เขียน test case สำหรับสถานการณ์ต่อไปนี้:

**Test Scenarios / สถานการณ์การทดสอบ:**
1. Valid username and password
2. Invalid username and valid password  
3. Valid username and invalid password
4. Empty username and password fields
5. SQL injection attempt in login fields
6. Password visibility toggle functionality
7. "Remember me" checkbox functionality
8. "Forgot password" link functionality

**Expected Deliverables / สิ่งที่คาดหวังที่จะได้รับ:**
- Test case document with clear steps
- Expected results for each scenario
- Priority and severity levels
- Test data requirements

**Time Limit / ระยะเวลา:** 45 minutes

---

### Scenario 2: Mobile App Navigation Testing / สถานการณ์ที่ 2: การทดสอบการนำทางแอปมือถือ

**EN:** Test the navigation functionality of a food delivery mobile app. Create a test plan covering the main user flows.

**TH:** ทดสอบการทำงานของการนำทางของแอปส่งอาหารมือถือ สร้าง test plan ที่ครอบคลุม user flow หลัก

**App Features to Test / ฟีเจอร์ของแอปที่ต้องทดสอบ:**
- Bottom navigation menu (Home, Search, Orders, Profile)
- Search functionality with filters
- Restaurant selection and menu browsing
- Add to cart and checkout process
- Order tracking
- Back button functionality
- Deep linking from notifications

**Expected Deliverables / สิ่งที่คาดหวังที่จะได้รับ:**
- Test plan document
- User flow diagrams
- Test scenarios for each navigation path
- Device compatibility considerations

**Time Limit / ระยะเวลา:** 60 minutes

---

## Mid Level Scenarios (2-5 years experience)

### Scenario 3: API Testing Scenario / สถานการณ์ที่ 3: สถานการณ์การทดสอบ API

**EN:** You need to test a REST API for a user management system. Design comprehensive API test cases.

**TH:** คุณต้องทดสอบ REST API สำหรับระบบจัดการผู้ใช้ ออกแบบ API test case ที่ครอบคลุม

**API Endpoints / API Endpoint:**
```
GET /api/users - Get all users
GET /api/users/{id} - Get user by ID
POST /api/users - Create new user
PUT /api/users/{id} - Update user
DELETE /api/users/{id} - Delete user
POST /api/auth/login - User authentication
```

**Testing Areas / พื้นที่การทดสอบ:**
- Request/Response validation
- HTTP status codes
- Authentication and authorization
- Data validation and boundary testing
- Error handling
- Performance testing
- Security testing (SQL injection, XSS)

**Expected Deliverables / สิ่งที่คาดหวังที่จะได้รับ:**
- API test cases with request/response examples
- Test data sets
- Automation strategy recommendations
- Risk assessment

**Time Limit / ระยะเวลา:** 90 minutes

---

### Scenario 4: Cross-Browser Compatibility Testing / สถานการณ์ที่ 4: การทดสอบความเข้ากันได้ข้ามเบราว์เซอร์

**EN:** Design a cross-browser testing strategy for a responsive web application that includes a dashboard with charts and forms.

**TH:** ออกแบบกลยุทธ์การทดสอบข้ามเบราว์เซอร์สำหรับเว็บแอปพลิเคชันที่ตอบสนองที่รวม dashboard พร้อมชาร์ตและฟอร์ม

**Requirements / ข้อกำหนด:**
- Support for Chrome, Firefox, Safari, Edge
- Mobile browsers (iOS Safari, Chrome Mobile)
- Different screen resolutions and orientations
- JavaScript functionality across browsers
- CSS rendering consistency
- Form validation and submission
- Chart rendering and interactions

**Expected Deliverables / สิ่งที่คาดหวังที่จะได้รับ:**
- Browser compatibility matrix
- Testing methodology and approach
- Test cases for critical functionalities
- Tools and automation recommendations
- Defect reporting template

**Time Limit / ระยะเวลา:** 75 minutes

---

## Senior Level Scenarios (5+ years experience)

### Scenario 5: Test Automation Strategy / สถานการณ์ที่ 5: กลยุทธ์การทดสอบอัตโนมัติ

**EN:** Design a comprehensive test automation strategy for a complex microservices-based e-commerce platform.

**TH:** ออกแบบกลยุทธ์การทดสอบอัตโนมัติที่ครอบคลุมสำหรับแพลตฟอร์ม e-commerce ที่ซับซ้อนที่ใช้ microservices

**System Architecture / สถาปัตยกรรมระบบ:**
- Frontend: React web app, React Native mobile app
- Backend: 8 microservices (User, Product, Order, Payment, Inventory, Notification, Analytics, Gateway)
- Databases: PostgreSQL, MongoDB, Redis
- Message Queue: RabbitMQ
- Cloud Infrastructure: AWS

**Expected Deliverables / สิ่งที่คาดหวังที่จะได้รับ:**
- Test automation pyramid strategy
- Tool selection and justification
- Framework architecture design
- CI/CD integration plan
- Maintenance and scaling strategy
- ROI analysis and metrics
- Risk mitigation plan

**Time Limit / ระยะเวลา:** 120 minutes

---

### Scenario 6: Performance Testing Strategy / สถานการณ์ที่ 6: กลยุทธ์การทดสอบประสิทธิภาพ

**EN:** Design a performance testing strategy for a social media platform expecting 1 million concurrent users during peak hours.

**TH:** ออกแบบกลยุทธ์การทดสอบประสิทธิภาพสำหรับแพลตฟอร์มโซเชียลมีเดียที่คาดว่าจะมีผู้ใช้พร้อมกัน 1 ล้านคนในช่วงเวลาเร่งด่วน

**System Requirements / ข้อกำหนดระบบ:**
- Real-time messaging and notifications
- Image and video upload/streaming
- News feed with infinite scroll
- Search functionality
- User profiles and social interactions
- Mobile and web applications

**Performance Goals / เป้าหมายประสิทธิภาพ:**
- Response time < 2 seconds for 95% of requests
- 99.9% uptime during peak hours
- Handle 10,000 messages per second
- Support 100GB data transfer per minute

**Expected Deliverables / สิ่งที่คาดหวังที่จะได้รับ:**
- Performance testing strategy document
- Test scenarios and user journeys
- Load modeling and test data strategy
- Monitoring and alerting plan
- Bottleneck identification methodology
- Scalability recommendations
- Performance regression testing approach

**Time Limit / ระยะเวลา:** 150 minutes

---

## Assessment Criteria / เกณฑ์การประเมิน

### Test Design Skills / ทักษะการออกแบบการทดสอบ
- Completeness and coverage of test scenarios
- Risk-based testing approach
- Test case clarity and maintainability
- Boundary and edge case identification

### Technical Knowledge / ความรู้ทางเทคนิค
- Understanding of testing principles and methodologies
- Tool knowledge and practical application
- Integration with development workflows
- Automation feasibility assessment

### Analytical Thinking / การคิดวิเคราะห์
- Problem decomposition and prioritization
- Root cause analysis capabilities
- Quality risk assessment
- Strategic thinking for complex scenarios

### Communication / การสื่อสาร
- Clear documentation and reporting
- Stakeholder communication
- Defect reporting quality
- Knowledge transfer capabilities

---

**Tools and Resources Allowed / เครื่องมือและทรัพยากรที่อนุญาต:**
- Testing documentation templates
- Online resources and references
- Testing tool documentation
- Sample test data generators

**Note:** Focus on practical application of testing principles and real-world problem-solving approaches.
**หมายเหตุ:** เน้นการประยุกต์ใช้หลักการทดสอบจริงและแนวทางการแก้ปัญหาในโลกแห่งความเป็นจริง
