# Project Requirement Specification (PRS)

## D Codescape of BUCA --- แบบทดสอบ DNA สายการทำงานของคุณ

**Document status:** Draft v0.1\
**Role of this document:** Source of truth สำหรับเป้าหมาย ขอบเขต
และพฤติกรรมของระบบ\
**Rule:** ห้าม Claude หรือผู้พัฒนาเติม Requirement ที่ไม่มีในเอกสารนี้เอง
หากข้อมูลไม่พอให้หยุดและถาม

------------------------------------------------------------------------

## 1. Project Identity

### Project Name

**แบบทดสอบ DNA สายการทำงานของคุณ**

### Brand / Experience World

**D Codescape of BUCA**

D Codescape of BUCA เป็นพื้นที่ที่รวบรวมผู้มี Passion และความฝันที่แตกต่างกันไว้
ทุกคนที่ก้าวเข้ามาต่างต้องการตามหาประสบการณ์ผ่าน 5 DCode
เพื่อพัฒนาตัวตนและตามหาความฝัน

### 5 DCode

1.  **Discovery** --- ค้นพบตัวตนและ Passion ที่แท้จริง
2.  **Dream** --- มองเห็นเป้าหมายและความฝันที่อยากไปถึง
3.  **Design** --- ออกแบบแนวทางและสร้างสรรค์ Idea
4.  **Develop** --- ลงมือทำจริง เรียนรู้จากประสบการณ์ และพัฒนาทักษะของตัวเอง
5.  **Debut** --- แสดงศักยภาพและก้าวสู่ Version ที่ดีที่สุดของตัวเอง

จุดเริ่มต้นของประสบการณ์คือ **Import Skill** ก่อนออกเดินทางผ่าน 5 DCode
เพื่อถอดรหัสศักยภาพของตัวเอง

------------------------------------------------------------------------

## 2. Business / User Goal

### Website Goal

ให้ผู้เข้าทำแบบทดสอบรู้ตัวตนของตัวเองในระยะเริ่มต้น โดยทำหน้าที่คล้าย Guideline
นำทางที่เปิดกว้างสำหรับผู้ทำแบบทดสอบ

### Problem to Solve

ผู้เข้าทำแบบทดสอบอาจยังไม่รู้ว่าตัวเองมีตัวตน ความถนัด
หรือแนวทางการทำงานแบบใดในบริบทของคณะนิเทศศาสตร์

### Target Users

-   นักเรียน
-   นักศึกษา
-   เด็กซิ่ว
-   ผู้ที่มี Passion ด้านนิเทศศาสตร์
-   ผู้ที่สนใจค้นหาศักยภาพของตนเอง ไม่ว่าจะถนัดงานเบื้องหน้าหรือเบื้องหลัง
-   ผู้ที่มาจากสายวิทย์หรือสายศิลป์

### Intended Outcome

เปิดโอกาสให้ผู้ใช้ค้นหาตัวเอง เรียนรู้ พัฒนาศักยภาพ
และกล้าที่จะก้าวตามความฝันบนเส้นทางนักนิเทศศาสตร์

### Primary CTA

**Find your DNA**

------------------------------------------------------------------------

## 3. Scope --- Website Structure

ลำดับหลักของ Website:

1.  Landing
2.  Start the Test
3.  Quiz
4.  Question
5.  Loading
6.  Result / DNA
7.  Share
8.  Register
9.  Career
10. Role Detail
11. About
12. Contact

### Quiz navigation requirement

-   แบบทดสอบมี **10 ข้อ**
-   ลำดับข้อเป็น **Fixed Order**
-   ผู้ใช้ต้องสามารถย้อนกลับไปยังคำถามก่อนหน้าได้
-   ผู้ใช้ต้องสามารถแก้ไขคำตอบระหว่างทำแบบทดสอบได้
-   เมื่อแก้คำตอบแล้ว ระบบต้องนำคำตอบล่าสุดไปใช้คำนวณผล
-   ห้ามสร้างการย้อนกลับที่ทำให้คำตอบหายโดยไม่ได้ตั้งใจ
-   ต้องมีสถานะความคืบหน้าของแบบทดสอบ

### Result download requirement

หลังจบแบบทดสอบ ต้องมีปุ่มสำหรับ **Download รูปผลแบบทดสอบทั้งหมด** -
ต้องเก็บข้อมูลที่จำเป็นสำหรับการสร้างภาพผลลัพธ์ - รูปที่ดาวน์โหลดต้องสะท้อนผลล่าสุดของผู้ใช้ -
รูปแบบไฟล์/ขนาดไฟล์/วิธีสร้างภาพยังไม่ได้กำหนดใน PRS นี้ และห้ามเดา

------------------------------------------------------------------------

## 4. Assessment Model

### Number of Questions

**10 questions**

วัตถุประสงค์ของแบบทดสอบคือเป็น **Guideline เริ่มต้น** ไม่ใช่การวินิจฉัยทางจิตวิทยา

### Scoring Model

-   **RIASEC = 80%**
-   **Big Five = 20%**

RIASEC ใช้กรอบ 6 กลุ่มของ Holland: - Realistic - Investigative - Artistic -
Social - Enterprising - Conventional

RIASEC เป็นกรอบสำรวจความสนใจทางอาชีพ
ไม่ควรตีความเป็นการรับรองว่าผู้ใช้เหมาะกับอาชีพใดอย่างเด็ดขาด

Big Five ประกอบด้วยมิติบุคลิกภาพหลัก 5 ด้าน ได้แก่: - Openness -
Conscientiousness - Extraversion - Agreeableness - Neuroticism

### Accuracy Rule

คำถามและการ Mapping ไปยัง 4 Roles ต้องได้รับการตรวจสอบก่อนนำไปใช้งานจริง

**ห้าม Claude สร้างคำถามหรือ Mapping โดยอ้างว่าเป็นผลทางจิตวิทยาที่ได้รับการรับรอง
หากยังไม่มีหลักฐาน/ผู้เชี่ยวชาญรับรอง**

ด้วยข้อจำกัด 10 ข้อ ผลลัพธ์ต้องสื่อสารในฐานะ **แนวทางเริ่มต้น / self-exploration
guide** ไม่ใช่ psychometric diagnosis

------------------------------------------------------------------------

## 5. Four Result Roles

มี 4 Roles ตามลำดับที่กำหนด:

1.  **นักสื่อสาร**
2.  **นักวางแผน**
3.  **นักออกแบบ**
4.  **นักผลิตสื่อ**

ตัวละครที่ผู้ใช้ส่งมาใช้เป็น **ตัวแทนของ 4 Roles** และใช้กับ Result + Mascot
เท่านั้นตาม Requirement

### Important accuracy boundary

การเชื่อม RIASEC + Big Five → 4 Roles เป็น **custom assessment mapping
ของโปรเจกต์** ไม่ใช่สิ่งที่สามารถอ้างว่าเป็นมาตรฐานของ RIASEC หรือ Big Five โดยตรง

ดังนั้นเอกสารนี้ยังไม่กำหนด: - item wording - answer scale - item-to-trait
matrix - trait-to-role weights - tie-breaking - minimum score -
confidence level

ข้อมูลเหล่านี้ต้องผ่านการออกแบบและตรวจสอบก่อน Implementation

------------------------------------------------------------------------

## 6. BUCA Career Reference

เว็บไซต์ต้องอ้างอิงข้อมูลสาขาวิชาของคณะนิเทศศาสตร์
มหาวิทยาลัยกรุงเทพเป็นฐานในการนำเสนอเส้นทางการเรียน/อาชีพ

ข้อมูลที่ผู้ใช้ระบุ: - Communication & New Media - Digital Advertising - Digital
Public Relations - Creative Branding - Influencer Branding - Digital
Communication and Media Industry - Broadcasting and Streaming Media
Production - Creative Content and Digital Experience - Event Production
and MICE Management - Performing Arts

**หมายเหตุ:** การจัดกลุ่มสาขาเหล่านี้เข้ากับ 4 Roles ยังต้องกำหนด Mapping
อย่างเป็นทางการก่อนนำไปใช้ในระบบ

------------------------------------------------------------------------

## 7. Result Page Content

เรียงลำดับ: 1. Description 2. Strength 3. Weakness 4. Suitable Career 5.
Faculty

นอกจากนี้ระบบต้องแสดงผลคะแนนของ 4 Roles ในรูปแบบวงล้อสรุปผลข้อมูล
โดยเรียงจากคะแนนมากไปน้อยตามที่กำหนด

รูปแบบ Chart ที่แน่นอนยังไม่ถูกกำหนด จึงห้าม Claude เลือกประเภท Chart เองใน
Requirement นี้

------------------------------------------------------------------------

## 8. Data Collection

ระบบต้องเก็บข้อมูล: - จำนวนครั้งที่มีการใช้งาน - จำนวนครั้งที่ทำแบบทดสอบ -
ผลลัพธ์ส่วนใหญ่ - สัดส่วนเปอร์เซ็นต์ของแต่ละ Role - ผลของผู้ใช้ในแต่ละครั้ง

### Guest Requirement

ผู้ใช้เป็น **Guest** ไม่จำเป็นต้อง Login

**ยังต้องกำหนดวิธีระบุผู้ใช้แบบไม่เปิดเผยตัวตน และนโยบาย retention / deletion /
consent ก่อน Production**

------------------------------------------------------------------------

## 9. Analytics

ใช้: - Google Analytics 4 (GA4) - Microsoft Clarity

Core Analytics & Features: 1. Conversion Rate 2. Traffic Source / Medium
3. Heatmaps 4. Rage Clicks 5. Session Recordings / Playback

Analytics ต้องไม่เก็บข้อมูลเกินความจำเป็น และต้องกำหนด consent/privacy behavior
ก่อน Production

------------------------------------------------------------------------

## 10. Accessibility

Target: **WCAG 2.1 Level A**

Level A เป็นระดับขั้นต่ำของ WCAG 2.1

------------------------------------------------------------------------

## 11. Language

-   Thai
-   English

------------------------------------------------------------------------

## 12. Responsive

**Mobile First**

------------------------------------------------------------------------

## 13. Animation

### Level 1 --- UI & Micro-Interactions

เน้น: - ใช้งานจริง - เรียบหรู - นุ่มนวล - ไม่รบกวนการทำแบบทดสอบ

Technologies / references: - Framer Motion สำหรับ React / Next.js - CSS
Animation - Nothing-inspired interaction language - Dot-matrix /
Glyph-inspired motion - Micro interaction ของปุ่มและ icon

**ยังไม่อนุญาตให้เพิ่ม WebGL / 3D / heavy animation เป็น Requirement
โดยอัตโนมัติ**

------------------------------------------------------------------------

## 14. Deployment

**Vercel**

------------------------------------------------------------------------

## 15. Development Environment

-   Claude AI --- สร้าง / วิเคราะห์ / Review Code
-   VS Code --- Run / Debug / แก้ไข
-   GitHub --- Repository / Version Control / Collaboration / Deployment
    integration

------------------------------------------------------------------------

## 16. Performance

ต้องกำหนดทรัพยากรตามสภาพการใช้งานจริง และประเมินจากการทดสอบระบบเบื้องต้น

Target traffic ที่ใช้เป็นบริบทการออกแบบ: **มากกว่า 2,000 users/day**

ยังไม่กำหนด SLA หรือ hard performance threshold จนกว่าจะมีผล Load Test

------------------------------------------------------------------------

## 17. Non-Goals / Do Not Assume

Claude MUST NOT: - เปลี่ยนชื่อ Project - เปลี่ยน 5 DCode - เปลี่ยน 4 Roles -
เพิ่มจำนวนข้อสอบ - เปลี่ยนสัดส่วน 80/20 - เพิ่ม Login ที่ผู้ใช้ไม่ได้ระบุ - เปลี่ยน Guest
เป็น Account System - เปลี่ยน Mobile First - เปลี่ยน Vercel - เปลี่ยน WCAG
target - ใช้ตัวละครเป็น UI หลักโดยอัตโนมัติ -
สร้างข้อมูลทางจิตวิทยาแล้วอ้างว่าได้รับการรับรอง - สร้าง Career Mapping
โดยไม่มีหลักฐานหรือการอนุมัติ - เติม Requirement ที่ไม่มีในเอกสาร

เมื่อข้อมูลไม่พอ: **ถามก่อน**

------------------------------------------------------------------------

## 18. Open Questions Before Production

1.  คำถาม 10 ข้อจริงและตัวเลือกคำตอบคืออะไร?
2.  ใช้ Rating Scale กี่ระดับ?
3.  แต่ละข้อวัด RIASEC ตัวใดและ Big Five ตัวใด?
4.  จะคำนวณ 80/20 อย่างไรในระดับคะแนนดิบ?
5.  Mapping จาก 6 RIASEC + 5 Big Five ไป 4 Roles ใครเป็นผู้อนุมัติ?
6.  จะใช้ผลอย่างไรเมื่อคะแนน 2 Roles ใกล้กัน?
7.  คำว่า Weakness ต้องใช้คำว่า "ข้อควรพัฒนา" หรือ "จุดอ่อน" ใน UI?
8.  จะใช้ข้อมูลสาขา BUCA เป็นเพียงข้อมูลแนะนำ หรือใช้เป็นส่วนหนึ่งของ scoring?
9.  Guest identity จะใช้ session ID, anonymous ID หรือวิธีอื่น?
10. ระยะเวลาเก็บข้อมูลและวิธีลบข้อมูลคืออะไร?
11. ต้องมี consent banner สำหรับ Analytics หรือไม่ และเงื่อนไขใด?
12. Download Result เป็น PNG/JPEG/PDF หรือหลายรูปแบบ?
13. ภาพ Download ต้องเป็น 1 ภาพรวม หรือหลายภาพ?
14. ภาษา EN เป็น translation ของ content ทั้งหมดหรือเฉพาะ UI?
15. ต้องการ CMS/admin สำหรับแก้คำถามและข้อมูล Role หรือไม่?

------------------------------------------------------------------------

## 19. Source / Verification Policy

ข้อมูลเกี่ยวกับ BUCA programs ต้องตรวจสอบกับข้อมูลจากมหาวิทยาลัยกรุงเทพก่อนใช้งานจริง

ข้อมูล RIASEC ต้องอ้างอิงกรอบ Holland อย่างถูกต้อง และ Big Five ต้องใช้
terminology ตามแหล่งอ้างอิงที่เชื่อถือได้

แหล่งอ้างอิงที่ใช้ตรวจสอบในการจัดทำ Draft: - Bangkok University School of
Communication Arts - University of Washington Career & Internship Center
--- Holland/RIASEC - APA Dictionary of Psychology --- Big Five - W3C ---
WCAG 2.1
