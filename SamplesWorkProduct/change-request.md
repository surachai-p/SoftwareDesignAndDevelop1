# แบบฟอร์มคำขอเปลี่ยนแปลง
# (Change Request Form)

| หัวข้อ | รายละเอียด |
|-------|------------|
| เลขที่คำขอ | CR-HOTEL-2024-005 |
| วันที่แจ้ง | 5 ธันวาคม 2024 |
| เวลาที่แจ้ง | 14:30 น. |
| ผู้แจ้ง | นางสาว สมหญิง ใจดี - Front Office Manager |
| แผนก | ฝ่ายต้อนรับ |
| สถานะ | รออนุมัติ |

## 1. รายละเอียดการขอเปลี่ยนแปลง

### 1.1 ประเภทการเปลี่ยนแปลง
- [x] เพิ่มฟีเจอร์ใหม่ (New Feature)
- [ ] แก้ไขฟีเจอร์ที่มีอยู่ (Enhancement)
- [ ] แก้ไขข้อผิดพลาด (Bug Fix)
- [ ] เปลี่ยนแปลงโครงสร้างระบบ (System Change)
- [ ] เปลี่ยนแปลงเอกสาร (Documentation)

### 1.2 ระบบที่เกี่ยวข้อง
- ระบบจองห้องพักออนไลน์
- โมดูล: ระบบจองห้องพัก และ ระบบชำระเงิน
- เวอร์ชัน: 1.2.0

### 1.3 ชื่อการเปลี่ยนแปลง
เพิ่มระบบการชำระเงินผ่าน E-Wallet และ QR Code Payment

### 1.4 เหตุผลในการขอเปลี่ยนแปลง
1. **ความต้องการของลูกค้า**: ลูกค้ามากกว่า 60% ขอชำระเงินผ่าน E-Wallet แต่ระบบปัจจุบันรองรับเฉพาะบัตรเครดิติและโอนเงิน
2. **แนวโน้มตลาด**: การชำระเงินผ่าน E-Wallet และ QR Code เติบโตอย่างรวดเร็ว โดยเฉพาะในกลุ่มลูกค้าหนุ่มสาว
3. **การแข่งขัน**: โรงแรมคู่แข่งส่วนใหญ่รองรับช่องทางการชำระเงินนี้แล้ว
4. **ความสะดวก**: ลดขั้นตอนการชำระเงิน เพิ่มความรวดเร็วในการ Check-in

### 1.5 รายละเอียดการเปลี่ยนแปลงที่ต้องการ

#### 1.5.1 ฟีเจอร์ที่ต้องการเพิ่ม
1. **การชำระผ่าน E-Wallet**:
   - รองรับ TrueMoney Wallet
   - รองรับ PromptPay
   - รองรับ ShopeePay
   - รองรับ LINE Pay
   - รองรับ Alipay (สำหรับลูกค้าต่างชาติ)

2. **การชำระผ่าน QR Code**:
   - สร้าง QR Code สำหรับการชำระเงินอัตโนมัติ
   - แสดง QR Code บนหน้าจอชำระเงิน
   - ส่ง QR Code ทางอีเมล
   - รองรับ PromptPay QR Code

3. **การยืนยันการชำระเงิน**:
   - ระบบตรวจสอบการชำระเงินอัตโนมัติ
   - แจ้งเตือนเมื่อชำระเงินสำเร็จ
   - อัพเดตสถานะการจองอัตโนมัติ
   - ออกใบเสร็จอิเล็กทรอนิกส์

4. **การจัดการการคืนเงิน**:
   - รองรับการคืนเงินผ่าน E-Wallet
   - ประมวลผลการคืนเงินอัตโนมัติ
   - แจ้งเตือนสถานะการคืนเงิน

#### 1.5.2 การปรับปรุง UI/UX
1. เพิ่มตัวเลือก E-Wallet ในหน้าเลือกวิธีชำระเงิน
2. แสดงโลโก้ E-Wallet ที่รองรับ
3. ออกแบบหน้าจอสแกน QR Code
4. เพิ่มคำแนะนำการใช้งานแต่ละช่องทาง

#### 1.5.3 การเชื่อมต่อกับระบบภายนอก
1. Payment Gateway ของ E-Wallet แต่ละรายการ
2. PromptPay API
3. ระบบตรวจสอบการชำระเงินแบบ Real-time

## 2. การวิเคราะห์ผลกระทบ (Impact Assessment)

### 2.1 Traceability Matrix (ตามมาตรฐาน ISO/IEC 29110)

| Requirement ID | Requirement Description | Change Type | New/Modified | Priority |
|---------------|------------------------|-------------|--------------|----------|
| PAY-01 | ระบบต้องรองรับการชำระเงินผ่าน:<br>- บัตรเครดิต/เดบิต<br>- Internet Banking<br>- E-Wallet<br>- QR Payment | Add | Modified | High |
| PAY-02 | ระบบต้องแสดงรายละเอียดค่าใช้จ่ายทั้งหมดก่อนชำระเงิน | Enhance | Modified | High |
| PAY-03 | ระบบต้องออกใบเสร็จ/ใบกำกับภาษีอิเล็กทรอนิกส์ | Enhance | Modified | High |
| BKG-04 | ระบบต้องรองรับการจองห้องพัก (รวมการชำระเงิน) | Enhance | Modified | High |
| UI-01 | หน้าเว็บไซต์สำหรับลูกค้า | Add | Modified | High |
| SW-01 | ระบบชำระเงินออนไลน์ | Add | New | High |

### 2.2 Configuration Items Affected (รายการที่ได้รับผลกระทบ)

| CI ID | Configuration Item | Type | Version | Change Action | Owner |
|-------|-------------------|------|---------|---------------|-------|
| CI-BE-001 | Payment Service API | Code | 1.2.0 → 2.0.0 | Major Update | Backend Team |
| CI-BE-002 | Payment Gateway Integration | Code | - → 1.0.0 | New | Backend Team |
| CI-DB-001 | Payment_Transactions Table | Database | 1.2.0 → 1.3.0 | Add Columns | Database Team |
| CI-DB-002 | Ewallet_Providers Table | Database | - → 1.0.0 | New Table | Database Team |
| CI-FE-001 | Payment Selection Component | Code | 1.2.0 → 2.0.0 | Major Update | Frontend Team |
| CI-FE-002 | QR Code Display Component | Code | - → 1.0.0 | New | Frontend Team |
| CI-DOC-001 | User Manual | Documentation | 1.2.0 → 2.0.0 | Update | Documentation Team |
| CI-DOC-002 | API Documentation | Documentation | 1.2.0 → 2.0.0 | Update | Documentation Team |
| CI-TEST-001 | Payment Test Cases | Test | 1.2.0 → 2.0.0 | Major Update | QA Team |

### 2.3 Version Control Information

| Artifact | Current Version | Target Version | Branch | Release Date |
|----------|----------------|----------------|--------|--------------|
| Backend API | v1.2.0 | v2.0.0 | feature/ewallet-integration | TBD |
| Frontend App | v1.2.0 | v2.0.0 | feature/ewallet-ui | TBD |
| Database Schema | v1.2.0 | v1.3.0 | feature/payment-schema | TBD |
| Documentation | v1.2.0 | v2.0.0 | feature/ewallet-docs | TBD |

### 2.4 ผลกระทบต่อระบบ

| ระบบ/โมดูล | ผลกระทบ | ระดับ | รายละเอียด |
|-----------|---------|-------|------------|
| ระบบจองห้องพัก | ปานกลาง | Medium | ต้องเพิ่มตัวเลือกช่องทางชำระเงิน |
| ระบบชำระเงิน | สูง | High | ต้องพัฒนา Integration ใหม่ทั้งหมด |
| Database | ปานกลาง | Medium | ต้องเพิ่มตารางและฟิลด์ใหม่ |
| UI/UX | ปานกลาง | Medium | ต้องออกแบบหน้าจอใหม่ |
| ระบบรายงาน | ต่ำ | Low | ต้องเพิ่มรายงานช่องทางการชำระเงิน |

### 2.2 ผลกระทบต่อผู้ใช้งาน

| กลุ่มผู้ใช้ | ผลกระทบ | รายละเอียด |
|-----------|---------|------------|
| ลูกค้า | บวก | มีตัวเลือกการชำระเงินมากขึ้น สะดวกและรวดเร็ว |
| พนักงานต้อนรับ | บวก | ลดขั้นตอนการรับชำระเงิน ลดปัญหาเงินทอน |
| ฝ่ายบัญชี | บวก | การกระทบยอดง่ายขึ้น ลดความผิดพลาด |
| ฝ่าย IT | ปานกลาง | ต้องเรียนรู้ระบบใหม่ ดูแลระบบเพิ่มเติม |

### 2.3 ผลกระทบด้านเทคนิค

| หัวข้อ | รายละเอียด | ระดับความซับซ้อน |
|-------|------------|-----------------|
| การพัฒนา | ต้องพัฒนา API Integration 5 รายการ | สูง |
| การทดสอบ | ต้องทดสอบแต่ละ E-Wallet ทั้งหมด | สูง |
| Security | ต้องเข้ารหัสข้อมูลการชำระเงิน | สูง |
| Performance | ต้องรองรับการทำงานพร้อมกัน | ปานกลาง |
| Infrastructure | อาจต้องเพิ่ม Server Capacity | ต่ำ |

### 2.4 ผลกระทบด้านงบประมาณและเวลา

| รายการ | ประมาณการ | หมายเหตุ |
|-------|-----------|----------|
| ค่าพัฒนาระบบ | 450,000 บาท | รวมค่า Integration และ Testing |
| ค่า License/API | 50,000 บาท/ปี | ค่าธรรมเนียมต่อรายการ |
| ค่า Transaction Fee | 2-3% ต่อรายการ | ขึ้นอยู่กับ E-Wallet |
| ระยะเวลาพัฒนา | 6-8 สัปดาห์ | รวมการทดสอบ |
| ระยะเวลาทดสอบ | 2 สัปดาห์ | UAT และ Security Testing |

## 3. แผนการดำเนินงาน

### 3.1 ขั้นตอนการพัฒนา

| ลำดับ | กิจกรรม | ระยะเวลา | ผู้รับผิดชอบ |
|------|---------|----------|--------------|
| 1 | วิเคราะห์ความต้องการเพิ่มเติม | 3 วัน | Business Analyst |
| 2 | ออกแบบ API Integration | 5 วัน | Solution Architect |
| 3 | ออกแบบ UI/UX | 5 วัน | UI/UX Designer |
| 4 | ลงนามสัญญากับ Payment Gateway | 7 วัน | Procurement |
| 5 | พัฒนา Backend | 15 วัน | Backend Team |
| 6 | พัฒนา Frontend | 10 วัน | Frontend Team |
| 7 | Integration Testing | 7 วัน | QA Team |
| 8 | Security Testing | 5 วัน | Security Team |
| 9 | UAT | 5 วัน | Users & QA |
| 10 | Deploy to Production | 1 วัน | DevOps |
| 11 | Training & Documentation | 3 วัน | Training Team |

**รวมระยะเวลา: 8 สัปดาห์**

### 3.2 ทรัพยากรที่ต้องการ

| ทรัพยากร | จำนวน | ระยะเวลา | ค่าใช้จ่าย |
|----------|--------|----------|-----------|
| Solution Architect | 1 คน | 2 สัปดาห์ | 80,000 |
| Backend Developer | 2 คน | 6 สัปดาห์ | 180,000 |
| Frontend Developer | 2 คน | 5 สัปดาห์ | 150,000 |
| QA Engineer | 2 คน | 3 สัปดาห์ | 90,000 |
| Security Consultant | 1 คน | 1 สัปดาห์ | 40,000 |
| Payment Gateway Setup | - | - | 50,000 |

**รวมงบประมาณ: 590,000 บาท**

### 3.3 ความเสี่ยงและแนวทางแก้ไข

| ความเสี่ยง | โอกาสเกิด | ผลกระทบ | แนวทางแก้ไข |
|-----------|-----------|----------|-------------|
| Payment Gateway ไม่เสถียร | ปานกลาง | สูง | - ทดสอบอย่างละเอียด<br>- มี Fallback Plan<br>- Monitor 24/7 |
| Security Breach | ต่ำ | สูงมาก | - ใช้ Encryption<br>- Security Audit<br>- Penetration Testing |
| Integration Delay | ปานกลาง | ปานกลาง | - เริ่มงานล่วงหน้า<br>- มี Mock API สำหรับทดสอบ |
| User Adoption | ต่ำ | ปานกลาง | - จัดอบรมพนักงาน<br>- ทำคู่มือที่เข้าใจง่าย |

## 4. เงื่อนไขการยอมรับ (Acceptance Criteria)

### 4.1 Verification and Validation Plan (ตามมาตรฐาน ISO/IEC 29110)

#### 4.1.1 Unit Testing
| Test ID | Test Description | Test Data | Expected Result | Responsible |
|---------|------------------|-----------|-----------------|-------------|
| UT-PAY-001 | ทดสอบ TrueMoney API Integration | Mock transaction | Success response | Backend Team |
| UT-PAY-002 | ทดสอบ PromptPay QR Generation | Payment amount | Valid QR Code | Backend Team |
| UT-PAY-003 | ทดสอบ ShopeePay Callback | Payment notification | Status updated | Backend Team |
| UT-PAY-004 | ทดสอบ LINE Pay API | Payment request | Transaction ID | Backend Team |
| UT-PAY-005 | ทดสอบ Alipay Integration | International payment | Currency conversion | Backend Team |

#### 4.1.2 Integration Testing
| Test ID | Integration Point | Test Scenario | Success Criteria | Duration |
|---------|------------------|---------------|------------------|----------|
| IT-PAY-001 | Frontend → Backend → Payment Gateway | End-to-end payment flow | Transaction completed | 2 days |
| IT-PAY-002 | Payment Gateway → Webhook → Database | Payment notification handling | DB updated correctly | 1 day |
| IT-PAY-003 | QR Code → Scanner → Verification | QR code payment | Payment verified | 1 day |
| IT-PAY-004 | Refund Request → Gateway → Customer | Refund processing | Money returned | 2 days |

#### 4.1.3 System Testing
| Test Category | Test Cases | Coverage | Acceptance Level |
|--------------|------------|----------|------------------|
| Functional Testing | 45 test cases | 100% features | 100% pass |
| Performance Testing | 10 scenarios | All payment methods | < 3s response |
| Security Testing | 15 test cases | Payment data security | 100% pass |
| Usability Testing | 8 scenarios | User experience | > 4.5/5 satisfaction |
| Compatibility Testing | 12 environments | Browsers & devices | 100% compatible |

#### 4.1.4 User Acceptance Testing (UAT)
| UAT Scenario | Test Users | Duration | Acceptance Criteria |
|-------------|-----------|----------|---------------------|
| Customer payment via E-Wallet | 10 users | 3 days | > 90% completion rate |
| Staff processing E-Wallet payment | 5 users | 2 days | 100% successful transactions |
| Refund via E-Wallet | 5 users | 2 days | 100% correct refunds |
| QR Code payment | 10 users | 2 days | > 95% scan success |

### 4.2 เงื่อนไขด้านฟังก์ชันการทำงาน
- [x] รองรับ E-Wallet อย่างน้อย 5 ช่องทาง
- [x] สร้างและแสดง QR Code สำหรับชำระเงินได้
- [x] ตรวจสอบการชำระเงินอัตโนมัติภายใน 30 วินาที
- [x] ออกใบเสร็จอิเล็กทรอนิกส์อัตโนมัติ
- [x] รองรับการคืนเงินผ่าน E-Wallet
- [x] บันทึกประวัติการทำรายการทั้งหมด

### 4.2 เงื่อนไขด้านประสิทธิภาพ
- [x] Response Time < 3 วินาที
- [x] Transaction Success Rate > 99%
- [x] รองรับการทำงานพร้อมกัน 100 รายการ
- [x] ระบบทำงาน 24/7 ไม่ขัดข้อง

### 4.3 เงื่อนไขด้านความปลอดภัย
- [x] ผ่าน Security Audit
- [x] ข้อมูลการชำระเงินถูกเข้ารหัส
- [x] ปฏิบัติตาม PCI-DSS Standard
- [x] มี Transaction Log ครบถ้วน

### 4.4 เงื่อนไขด้านเอกสาร
- [x] คู่มือการใช้งานสำหรับพนักงาน
- [x] คู่มือการใช้งานสำหรับลูกค้า
- [x] Technical Documentation
- [x] API Documentation

## 5. การพิจารณาและอนุมัติ

### 5.1 ผลการพิจารณาเบื้องต้น

| หน่วยงาน | ผู้พิจารณา | ความเห็น | วันที่ |
|---------|-----------|---------|--------|
| ฝ่ายต้อนรับ | นางสาว สมหญิง ใจดี | เห็นควรดำเนินการ - จำเป็นต่อธุรกิจ | 5/12/2024 |
| ฝ่ายบัญชี | นาย สมชาย คิดเงิน | เห็นด้วย - ช่วยลดข้อผิดพลาด | 5/12/2024 |
| ฝ่าย IT | นาย สมศักดิ์ เก่งกล้า | เห็นด้วย - ทำได้ แต่ต้องใช้เวลา | 5/12/2024 |
| ฝ่ายการตลาด | นางสาว สมใจ ขายดี | เห็นด้วยอย่างยิ่ง - เพิ่มความสามารถในการแข่งขัน | 5/12/2024 |

### 5.2 การประเมินลำดับความสำคัญ

| เกณฑ์ | คะแนน (1-5) | น้ำหนัก | คะแนนรวม |
|-------|-------------|---------|----------|
| ผลกระทบต่อธุรกิจ | 5 | 30% | 1.5 |
| ความต้องการของลูกค้า | 5 | 25% | 1.25 |
| ROI | 4 | 20% | 0.8 |
| ความเร่งด่วน | 4 | 15% | 0.6 |
| ความเสี่ยง | 3 | 10% | 0.3 |

**คะแนนรวม: 4.45/5 = ลำดับความสำคัญสูง**

### 5.3 การอนุมัติ

#### Change Control Board (CCB)

| ตำแหน่ง | ชื่อ | การตัดสินใจ | ลงนาม | วันที่ |
|---------|-----|-------------|--------|--------|
| Project Manager | นาย สมชาย รักงาน | ☐ อนุมัติ<br>☐ ไม่อนุมัติ<br>☐ เลื่อนพิจารณา | __________ | _______ |
| Technical Lead | นาย สมศักดิ์ เก่งกล้า | ☐ อนุมัติ<br>☐ ไม่อนุมัติ<br>☐ เลื่อนพิจารณา | __________ | _______ |
| Business Manager | นาย สมบัติ ผู้จัดการ | ☐ อนุมัติ<br>☐ ไม่อนุมัติ<br>☐ เลื่อนพิจารณา | __________ | _______ |
| Finance Director | นางสาว สมปรารถนา การเงิน | ☐ อนุมัติ<br>☐ ไม่อนุมัติ<br>☐ เลื่อนพิจารณา | __________ | _______ |

### 5.4 เงื่อนไขการอนุมัติ
- ☐ งบประมาณได้รับการอนุมัติ
- ☐ ทรัพยากรพร้อมใช้งาน
- ☐ ไม่กระทบต่อแผนงานหลัก
- ☐ ผู้มีส่วนได้ส่วนเสียเห็นชอบ
- ☐ ความเสี่ยงอยู่ในระดับที่ยอมรับได้

### 5.5 ข้อเสนอแนะเพิ่มเติม
```
_________________________________________________________________

_________________________________________________________________

_________________________________________________________________
```

## 6. การติดตามผล

### 6.1 ตัวชี้วัดความสำเร็จ (KPI)

| ตัวชี้วัด | เป้าหมาย | วิธีการวัด |
|----------|----------|-----------|
| สัดส่วนการใช้ E-Wallet | > 40% ของการชำระเงินทั้งหมด | รายงานจากระบบ |
| Transaction Success Rate | > 99% | รายงานจากระบบ |
| ความพึงพอใจของลูกค้า | > 4.5/5 | แบบสอบถาม |
| ระยะเวลาในการชำระเงิน | ลดลง 30% | เปรียบเทียบข้อมูล |
| ข้อผิดพลาดในการชำระเงิน | < 0.1% | รายงานจากระบบ |

### 6.2 กำหนดการทบทวน

| งวด | วันที่ทบทวน | หัวข้อการทบทวน | ผู้รับผิดชอบ |
|-----|------------|----------------|--------------|
| 1 | หลัง Go-Live 1 เดือน | - การใช้งานจริง<br>- ปัญหาที่พบ<br>- ข้อเสนอแนะ | Project Manager |
| 2 | หลัง Go-Live 3 เดือน | - ประสิทธิภาพระบบ<br>- ROI<br>- ความพึงพอใจ | Business Manager |
| 3 | หลัง Go-Live 6 เดือน | - สรุปผลโดยรวม<br>- แนวทางพัฒนาต่อ | Steering Committee |

## 7. Change Control Process (ตามมาตรฐาน ISO/IEC 29110)

### 7.1 Configuration Management

#### 7.1.1 Baseline Before Change
| Baseline Item | Version | Date | Repository | Status |
|--------------|---------|------|------------|--------|
| Payment System | v1.2.0 | 30/11/2024 | GitHub: main branch | Approved |
| Database Schema | v1.2.0 | 30/11/2024 | Migration files | Approved |
| API Documentation | v1.2.0 | 30/11/2024 | Confluence | Approved |
| Test Suite | v1.2.0 | 30/11/2024 | GitHub: test branch | Approved |

#### 7.1.2 Baseline After Change (Target)
| Baseline Item | Version | Target Date | Repository | Expected Status |
|--------------|---------|-------------|------------|-----------------|
| Payment System | v2.0.0 | 31/01/2025 | GitHub: main branch | To be approved |
| Database Schema | v1.3.0 | 31/01/2025 | Migration files | To be approved |
| API Documentation | v2.0.0 | 31/01/2025 | Confluence | To be approved |
| Test Suite | v2.0.0 | 31/01/2025 | GitHub: test branch | To be approved |

### 7.2 Change Control Workflow

```
[Change Request Submitted]
         ↓
[Initial Review by PM] → [Rejected] → [End]
         ↓ Approved
[Impact Assessment]
         ↓
[Technical Review by Tech Lead]
         ↓
[CCB Meeting]
         ↓
    [Decision]
    ↙    ↓    ↘
Approved  Deferred  Rejected
    ↓
[Implementation]
    ↓
[Testing & Verification]
    ↓
[UAT]
    ↓
[Deployment to Production]
    ↓
[Post-Implementation Review]
    ↓
[Close Change Request]
```

### 7.3 Communication Plan

| Stakeholder | Information Needed | Method | Frequency |
|------------|-------------------|---------|-----------|
| Project Sponsor | Status, Budget, Risks | Status Report | Weekly |
| Development Team | Tasks, Technical details | Daily Standup | Daily |
| QA Team | Test Requirements, Bugs | Test Management System | Daily |
| Business Users | Features, Training | Email, Workshop | As needed |
| Support Team | New features, Known issues | Documentation | Before release |

### 7.4 Rollback Plan

| Scenario | Trigger | Action | Responsible | SLA |
|----------|---------|--------|-------------|-----|
| Critical Bug in Production | > 10% transaction failure | Rollback to v1.2.0 | DevOps | 30 min |
| Security Vulnerability | Security breach detected | Immediate rollback | Security Team | 15 min |
| Performance Degradation | Response time > 5s | Rollback and investigate | Tech Lead | 1 hour |
| Integration Failure | Payment gateway error | Switch to fallback | Backend Team | 30 min |

## 8. Quality Assurance (ตามมาตรฐาน ISO/IEC 29110)

### 8.1 Quality Metrics

| Metric | Target | Measurement Method | Review Frequency |
|--------|--------|--------------------|------------------|
| Code Quality | > 80% (SonarQube) | Automated analysis | Daily |
| Test Coverage | > 85% | Coverage tools | Daily |
| Defect Density | < 0.5 per KLOC | Defect tracking | Weekly |
| Code Review Efficiency | 100% reviewed before merge | Pull request metrics | Daily |

### 8.2 Review and Audit

| Review Type | Participants | Schedule | Deliverable |
|------------|-------------|----------|-------------|
| Design Review | Architects, Tech Lead | Week 2 | Design approval |
| Code Review | Developers, Tech Lead | Continuous | Approved PRs |
| Security Review | Security Team | Week 6 | Security clearance |
| CCB Review | Stakeholders | Before deployment | Go/No-go decision |

---

## 9. เอกสารแนบ
1. ข้อเสนอจาก Payment Gateway Providers
2. ตัวอย่าง UI/UX Design (Mockup)
3. Technical Specification Document
4. Risk Assessment Detail
5. Cost-Benefit Analysis

---

**หมายเหตุ:**
- เอกสารนี้เป็นส่วนหนึ่งของกระบวนการ Change Management
- การเปลี่ยนแปลงจะเริ่มดำเนินการเมื่อได้รับการอนุมัติจาก CCB
- หากมีการเปลี่ยนแปลงขอบเขตหรืองบประมาณ ต้องยื่น Change Request ใหม่
- การติดตามผลจะรายงานใน Project Status Meeting

---

**ผู้จัดทำเอกสาร:**

| ตำแหน่ง | ชื่อ | ลงนาม | วันที่ |
|---------|-----|--------|--------|
| ผู้ขอเปลี่ยนแปลง | นางสาว สมหญิง ใจดี | __________ | 5/12/2024 |
| Business Analyst | นางสาว สมใจ วิเคราะห์ดี | __________ | 5/12/2024 |
| Project Manager | นาย สมชาย รักงาน | __________ | 5/12/2024 |
