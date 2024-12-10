# ระบบจองห้องพักออนไลน์
## Software Requirement Specification Document

**เวอร์ชัน:** 1.0  
**วันที่:** 10 ธันวาคม 2024  
**จัดทำโดย:** ทีมพัฒนาระบบจองห้องพักออนไลน์

---

## ประวัติการจัดทำเอกสาร

| วันที่ | เวอร์ชัน | รายละเอียดการเปลี่ยนแปลง | ผู้ดำเนินการ |
|-------|----------|------------------------|------------|
| 10/12/2024 | 1.0 | จัดทำเอกสารฉบับแรก | ทีมพัฒนา |

---

## สารบัญ
1. [Introduction](#1-introduction)
   - 1.1 วัตถุประสงค์
   - 1.2 ภาพรวมของระบบ
   - 1.3 ขอบเขต
   - 1.4 กลุ่มผู้ใช้งาน

2. [System Requirements](#2-system-requirements)
   - 2.1 Hardware Requirements
   - 2.2 Software Requirements
   - 2.3 External Interfaces

3. [Software Requirements](#3-software-requirements)
   - 3.1 ระบบสมาชิก
   - 3.2 ระบบจองห้องพัก
   - 3.3 ระบบชำระเงิน
   - 3.4 ระบบจัดการห้องพัก

4. [Non-Functional Requirements](#4-non-functional-requirements)
   - 4.1 Performance Requirements
   - 4.2 Security Requirements
   - 4.3 Usability Requirements
   - 4.4 Reliability Requirements
   - 4.5 Maintainability Requirements

---

## 1. Introduction

### 1.1 วัตถุประสงค์
- เพื่อพัฒนาระบบจองห้องพักออนไลน์ที่มีประสิทธิภาพ
- เพื่อเพิ่มความสะดวกในการจองห้องพักสำหรับลูกค้า
- เพื่อเพิ่มประสิทธิภาพในการบริหารจัดการห้องพัก

### 1.2 ภาพรวมของระบบ
ระบบจองห้องพักออนไลน์เป็นแพลตฟอร์มที่พัฒนาขึ้นเพื่อให้บริการจองห้องพักผ่านระบบอินเทอร์เน็ต โดยระบบจะช่วยอำนวยความสะดวกในการจองห้องพัก การชำระเงิน และการจัดการข้อมูลห้องพักแบบครบวงจร

ระบบงานประกอบด้วยส่วนสำคัญดังนี้:
1. ระบบสมาชิก - รองรับการลงทะเบียน เข้าสู่ระบบ และจัดการข้อมูลส่วนตัวของผู้ใช้
2. ระบบจองห้องพัก - ให้บริการค้นหาและจองห้องพัก พร้อมแสดงรายละเอียดและสถานะห้องแบบเรียลไทม์
3. ระบบชำระเงิน - รองรับการชำระเงินหลากหลายช่องทาง พร้อมออกเอกสารทางการเงินอัตโนมัติ
4. ระบบจัดการห้องพัก - สำหรับผู้ดูแลระบบในการบริหารจัดการข้อมูลห้องพักและการจอง
5. ระบบรายงาน - สรุปข้อมูลสถิติและรายงานต่างๆ สำหรับการบริหารจัดการ

### 1.3 ขอบเขต
- ระบบรองรับการจองห้องพักออนไลน์
- ระบบจัดการข้อมูลห้องพัก
- ระบบจัดการการชำระเงิน
- ระบบรายงานและสถิติ

### 1.4 กลุ่มผู้ใช้งาน
1. ลูกค้า
   - ผู้ใช้งานทั่วไป
   - สมาชิก
2. เจ้าหน้าที่โรงแรม
   - พนักงานต้อนรับ
   - ผู้จัดการ
3. ผู้ดูแลระบบ

---

## 2. System Requirements

### 2.1 Hardware Requirements
- Server Requirements:
  - CPU: Intel Xeon หรือเทียบเท่า
  - RAM: 16GB ขึ้นไป
  - Storage: SSD 500GB ขึ้นไป

- Client Requirements:
  - สามารถเข้าถึงอินเทอร์เน็ตได้
  - รองรับ Web Browser ที่ทันสมัย

### 2.2 Software Requirements
- Operating System: Windows Server 2019 หรือ Linux Server
- Web Server: Apache หรือ Nginx
- Database: MySQL 8.0 หรือสูงกว่า
- Programming Language: PHP 8.0 หรือสูงกว่า

### 2.3 External Interfaces

#### 2.3.1 User Interfaces
| Interface ID | Description | Platform/Technology |
|-------------|-------------|-------------------|
| UI-01 | หน้าเว็บไซต์สำหรับลูกค้า | Web Browser (Responsive) |
| UI-02 | หน้าจัดการระบบสำหรับเจ้าหน้าที่ | Web Browser (Desktop) |
| UI-03 | แอปพลิเคชันมือถือสำหรับลูกค้า | iOS, Android |

#### 2.3.2 Hardware Interfaces
| Interface ID | Description | Protocol |
|-------------|-------------|----------|
| HW-01 | เครื่องรูดบัตรเครดิต | HTTPS/TLS |
| HW-02 | เครื่องสแกน QR Code | TCP/IP |

#### 2.3.3 Software Interfaces
| Interface ID | Description | Protocol/API |
|-------------|-------------|--------------|
| SW-01 | ระบบชำระเงินออนไลน์ | REST API |
| SW-02 | ระบบส่งอีเมล | SMTP |
| SW-03 | LINE Notification | LINE API |
| SW-04 | Google Maps | Google Maps API |

#### 2.3.4 Communication Interfaces
| Interface ID | Description | Protocol |
|-------------|-------------|----------|
| COM-01 | การเชื่อมต่อกับระบบธนาคาร | HTTPS/SSL |
| COM-02 | การส่งข้อความ SMS | SMS Gateway |
| COM-03 | การแจ้งเตือนผ่าน LINE | HTTPS |

---

## 3. Software Requirements

### 3.1 ระบบสมาชิก (User Management)

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| USR-01 | ระบบต้องรองรับการลงทะเบียนสมาชิกด้วย:<br>- ชื่อ-นามสกุล<br>- อีเมล (ใช้เป็น Username)<br>- รหัสผ่าน<br>- เบอร์โทรศัพท์<br>- ที่อยู่ | High |
| USR-02 | ระบบต้องส่งอีเมลยืนยันตัวตนหลังการสมัครสมาชิก | High |
| USR-03 | ระบบต้องรองรับการลงทะเบียนผ่าน Social Media | Medium |
| USR-04 | ระบบต้องรองรับการเข้าสู่ระบบด้วย:<br>- อีเมลและรหัสผ่าน<br>- Social Media Account<br>- Two-Factor Authentication (optional) | High |
| USR-05 | ระบบต้องมีฟังก์ชันรีเซ็ตรหัสผ่านผ่านอีเมล | Medium |
| USR-06 | ระบบต้องบันทึกประวัติการเข้าสู่ระบบ | Medium |

### 3.2 ระบบค้นหาและจองห้องพัก (Search & Booking System)

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| BKG-01 | ระบบต้องรองรับการค้นหาห้องพักตามเงื่อนไข:<br>- วันเช็คอิน-เช็คเอาท์<br>- จำนวนผู้เข้าพัก<br>- ประเภทห้อง<br>- ช่วงราคา<br>- สิ่งอำนวยความสะดวก | High |
| BKG-02 | ระบบต้องแสดงข้อมูลห้องพักโดยละเอียด:<br>- รูปภาพห้องพักแบบ Gallery<br>- ราคาและค่าใช้จ่ายเพิ่มเติม<br>- สิ่งอำนวยความสะดวก<br>- ขนาดห้องและจำนวนผู้เข้าพักสูงสุด<br>- นโยบายการเข้าพักและยกเลิก | High |
| BKG-03 | ระบบต้องแสดงปฏิทินพร้อมสถานะห้องว่างและราคารายวัน | High |
| BKG-04 | ระบบต้องรองรับการจองห้องพัก:<br>- เลือกวันเช็คอิน-เช็คเอาท์<br>- เลือกจำนวนและประเภทห้อง<br>- ระบุจำนวนผู้เข้าพัก<br>- เลือกแพ็คเกจเสริม<br>- ใส่โค้ดส่วนลด | High |
| BKG-05 | ระบบต้องส่งอีเมลยืนยันการจองทันทีหลังจองสำเร็จ | High |

### 3.3 ระบบชำระเงิน (Payment System)

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| PAY-01 | ระบบต้องรองรับการชำระเงินผ่าน:<br>- บัตรเครดิต/เดบิต<br>- Internet Banking<br>- E-Wallet<br>- QR Payment | High |
| PAY-02 | ระบบต้องแสดงรายละเอียดค่าใช้จ่ายทั้งหมดก่อนชำระเงิน | High |
| PAY-03 | ระบบต้องออกใบเสร็จ/ใบกำกับภาษีอิเล็กทรอนิกส์ | High |
| PAY-04 | ระบบต้องรองรับการคืนเงินตามนโยบายการยกเลิก | High |

### 3.4 ระบบจัดการห้องพัก (Room Management)

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| ROM-01 | ระบบต้องรองรับการจัดการห้องพักสำหรับเจ้าหน้าที่:<br>- Check-in/Check-out<br>- บันทึกเอกสารประจำตัว<br>- กำหนดห้องพัก<br>- ออกคีย์การ์ด | High |
| ROM-02 | ระบบต้องคำนวณค่าใช้จ่ายเพิ่มเติมระหว่างเข้าพัก | High |
| ROM-03 | ระบบต้องอัพเดทสถานะห้องแบบ Real-time | High |
| ROM-04 | ระบบต้องรองรับการยืนยัน/ยกเลิกการจอง | High |

### 3.5 ระบบจัดการสำหรับผู้ดูแลระบบ (Admin System)

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| ADM-01 | ระบบต้องรองรับการจัดการผู้ใช้งาน:<br>- CRUD operations<br>- จัดการสิทธิ์<br>- ดูประวัติการใช้งาน<br>- ระงับการใช้งาน | High |
| ADM-02 | ระบบต้องรองรับการจัดการประเภทห้อง:<br>- CRUD operations<br>- จัดการราคาและโปรโมชัน<br>- อัพโหลดรูปภาพ<br>- กำหนดสิ่งอำนวยความสะดวก | High |
| ADM-03 | ระบบต้องสามารถออกรายงานต่างๆ | Medium |
| ADM-04 | ระบบต้องรองรับการจัดการโปรโมชัน | Medium |

---

## 4. Non-Functional Requirements

### 4.1 Performance Requirements

| Requirement ID | Requirement Description | Metric |
|---------------|------------------------|---------|
| PRF-01 | ระบบต้องรองรับผู้ใช้งานพร้อมกัน | ≥ 1,000 users |
| PRF-02 | เวลาตอบสนองการค้นหาห้องพัก | ≤ 3 วินาที |
| PRF-03 | เวลาประมวลผลการชำระเงิน | ≤ 5 วินาที |
| PRF-04 | เวลาในการโหลดหน้าเว็บ | ≤ 2 วินาที |

### 4.2 Security Requirements

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| SEC-01 | การเข้ารหัสข้อมูลด้วย SSL/TLS | High |
| SEC-02 | การเข้ารหัสรหัสผ่านด้วย bcrypt หรือเทียบเท่า | High |
| SEC-03 | การป้องกัน SQL Injection และ XSS | High |
| SEC-04 | การล็อคบัญชีหลังล็อกอินผิด 5 ครั้ง | Medium |
| SEC-05 | Session Timeout หลังไม่มีการใช้งาน 30 นาที | Medium |

### 4.3 Usability Requirements

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| USB-01 | ส่วนติดต่อผู้ใช้ต้องใช้งานง่าย | High |
| USB-02 | รองรับ Responsive Design | High |
| USB-03 | รองรับภาษาไทยและอังกฤษ | High |
| USB-04 | มีคู่มือการใช้งานออนไลน์ | Medium |
| USB-05 | มีระบบช่วยเหลือแบบ Live Chat | Low |

### 4.4 Reliability Requirements

| Requirement ID | Requirement Description | Metric |
|---------------|------------------------|---------|
| REL-01 | System Uptime | 99.9% |
| REL-02 | ระบบสำรองข้อมูลอัตโนมัติ | ทุก 24 ชั่วโมง |
| REL-03 | ระยะเวลาในการกู้คืนระบบ | ≤ 4 ชั่วโมง |
| REL-04 | การสำรองข้อมูลการจอง | Real-time |

### 4.5 Maintainability Requirements

| Requirement ID | Requirement Description | Priority |
|---------------|------------------------|----------|
| MNT-01 | มีเอกสารประกอบการพัฒนาระบบ | High |
| MNT-02 | มีระบบบันทึกและติดตามข้อผิดพลาด | High |
| MNT-03 | มีการแยกส่วนการทำงานเป็นโมดูล | High |
| MNT-04 | มีระบบทดสอบอัตโนมัติครอบคลุม 80% | Medium |