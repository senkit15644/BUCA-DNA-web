# UX/UI Design Specification

## D Codescape of BUCA --- DNA Career Discovery

**Document status:** Draft v0.1\
**Rule:** ภาพ Reference เป็น Design Reference เท่านั้น
ห้ามคัดลอกข้อมูลหรือสร้างองค์ประกอบที่ไม่ได้รับ Requirement

------------------------------------------------------------------------

## 1. Design Objective

สร้างประสบการณ์แบบทดสอบที่ให้ผู้ใช้รู้สึกว่ากำลัง "ค้นหา / ถอดรหัสตัวเอง" แต่ยังต้องอ่านง่าย
ใช้งานง่าย และไม่ทำให้ Visual ขัดขวางการตอบคำถาม

Primary CTA: **Find your DNA**

Primary experience: **Discover → Answer → Decode → Understand →
Explore**

------------------------------------------------------------------------

## 2. Reference Image Analysis --- UX/UI Only

จาก Reference Website ที่ผู้ใช้ส่งมา สามารถจำแนกองค์ประกอบ UX/UI ได้ดังนี้:

### A. Global Navigation

-   Header แบบ horizontal
-   Brand mark ด้านซ้าย
-   Navigation links
-   System/status information
-   Primary CTA
-   Utility/menu control

### B. Hero

-   Section number / metadata
-   Large editorial headline
-   Supporting paragraph
-   Primary CTA
-   Secondary action
-   Large visual/data area
-   Coordinate / system labels

### C. Information Grid

-   หลักการ/คุณสมบัติในรูปแบบ card
-   Icon
-   Heading
-   Supporting copy
-   Repeated grid system

### D. Content / Work Cards

-   Thumbnail
-   Category
-   Title
-   Supporting label
-   Arrow / action affordance

### E. System Status

-   Metrics
-   Progress bars
-   Status indicator
-   Technical labels

### F. CTA / Form

-   Short message
-   Input
-   CTA button
-   Decorative system details

### G. Footer

-   Brand
-   Navigation
-   Resources
-   Social
-   System / location information

------------------------------------------------------------------------

## 3. Visual Language Derived From Reference

Reference ให้ภาษาภาพที่มีลักษณะ: - Editorial grid - Technical interface -
High contrast - Black / white base - Accent color - Monospace /
technical labels - Thin rules / dividers - Numbered sections - Data
visualization - System status - Micro details

### Important

Reference ไม่ได้หมายความว่า Website ต้องมีทุกองค์ประกอบ

Claude ต้องเลือกใช้เฉพาะองค์ประกอบที่สนับสนุน UX ของแบบทดสอบ

------------------------------------------------------------------------

## 4. Character Usage

ตัวละคร 4 ตัวเป็นตัวแทนของ: 1. นักผลิตสื่อ 2. นักวางแผน 3. นักสื่อสาร 4. นักออกแบบ

การใช้งาน: - Result - Mascot

ห้ามนำตัวละครมาแทน UI component โดยอัตโนมัติ ห้ามเปลี่ยนบทบาทของตัวละคร ห้ามตีความ
character design เป็น scoring logic

------------------------------------------------------------------------

## 5. Page Architecture

### 01 --- Landing

Purpose: แนะนำ D Codescape of BUCA และเชิญชวนเข้าสู่การค้นหา DNA

ต้องมี: - Project identity - 5 DCode narrative - Primary CTA: Find your
DNA - Visual language จาก Reference

### 02 --- Start the Test

Purpose: อธิบายก่อนเริ่มทำแบบทดสอบ

ต้องไม่เพิ่มข้อความหรือคำเตือนที่ไม่ได้รับการอนุมัติ

### 03 --- Quiz / Question

Purpose: แสดงคำถามทีละข้อ

Requirements: - Fixed Order - 10 questions - Progress indicator - Back -
Next - Answer state - Current question state - แก้ไขคำตอบย้อนหลังได้

### 04 --- Loading

Purpose: เป็น transition ระหว่างการส่งคำตอบและการแสดงผล DNA

Loading copy และ animation ต้องไม่อ้างว่าระบบกำลังทำสิ่งที่ไม่ได้เกิดขึ้นจริง

### 05 --- Result / DNA

Order: 1. Description 2. Strength 3. Weakness 4. Suitable Career 5.
Faculty

ต้องมี: - 4-role percentage wheel - Role ranking - Character - Download
Result - Share

### 06 --- Share

Purpose: ให้ผู้ใช้แชร์ผลลัพธ์

วิธีแชร์จริงยังต้องกำหนด

### 07 --- Register

ปัจจุบัน Requirement ระบุ Guest ดังนั้น Register ต้องไม่บังคับก่อนทำแบบทดสอบ

หน้าที่ของ Register ยังต้องระบุเพิ่มเติมว่ามีไว้เพื่ออะไร

### 08 --- Career

Purpose: สำรวจเส้นทางสายงาน/สาขาที่เกี่ยวข้อง

### 09 --- Role Detail

Purpose: ขยายข้อมูล Role ที่ผู้ใช้สนใจ

### 10 --- About

ข้อมูลโครงการ / D Codescape of BUCA

### 11 --- Contact

ข้อมูลติดต่อที่ได้รับอนุมัติเท่านั้น

------------------------------------------------------------------------

## 6. Quiz Interaction Rules

### Progress

ต้องเห็น: - Question number - Total questions - Current progress

### Back

Back ต้อง: - กลับไปข้อก่อนหน้า - รักษาคำตอบเดิม - ให้แก้ไขได้ - ไม่ reset แบบทดสอบ

### Forward

Next ต้อง: - ตรวจว่ามีคำตอบตาม requirement ของคำถามหรือไม่ - หากยังตอบไม่ได้
ให้แสดง validation ที่เข้าใจง่าย - ห้ามข้ามโดยทำให้ state ผิด

### Final Submit

เมื่อส่งคำตอบ: - Freeze final answer set - ส่งเข้าสู่ scoring - ไป Loading -
แล้ว Result

------------------------------------------------------------------------

## 7. Result Visualization

ระบบต้องแสดง 4 Roles เป็นเปอร์เซ็นต์

Ranking: คะแนนมาก → น้อย

ยังไม่กำหนดชนิด Chart ใน Requirement

**ห้าม Claude ตัดสินใจแทนโดยไม่มี Design Approval**

------------------------------------------------------------------------

## 8. Download Result UX

ต้องมี CTA: **Download Result**

Output ต้องเป็นภาพผลลัพธ์ทั้งหมดตามที่ผู้ใช้กำหนด

สิ่งที่ยังต้องอนุมัติ: - PNG / JPEG / PDF - 1 image / multiple images - image
dimension - sharing-safe version - branding / logo - background -
typography

------------------------------------------------------------------------

## 9. Responsive

Strategy: **Mobile First**

Breakpoints ต้องออกแบบจาก content ไม่ใช่เลือกตัวเลขโดยไม่มีเหตุผล

Priority: 1. Quiz usability 2. Result readability 3. CTA accessibility
4. Touch target 5. Performance

------------------------------------------------------------------------

## 10. Accessibility --- WCAG 2.1 Level A

Minimum: - Keyboard operability - Text alternatives - Semantic HTML -
Form labels - Focus states - Error identification - Logical reading
order - Sufficient interaction clarity - Reduced-motion consideration

WCAG 2.1 Level A เป็น minimum target ของโปรเจกต์

------------------------------------------------------------------------

## 11. Animation System

### Level 1

-   Page transition
-   Button interaction
-   Hover
-   Press
-   Progress
-   Loading
-   Result reveal

Primary: **Framer Motion**

Secondary: **CSS Animation**

Visual language: **Nothing-inspired dot-matrix / glyph / technical
micro-motion**

Animation MUST: - support comprehension - not block quiz interaction -
not cause excessive motion - respect reduced-motion preferences

------------------------------------------------------------------------

## 12. UX Writing Rules

Tone: - Human - Clear - Encouraging - Not judgmental - Not deterministic

Avoid: - "คุณเหมาะกับอาชีพนี้ 100%" - "นี่คือตัวตนที่แท้จริงของคุณ" -
"ผลนี้บอกอนาคตของคุณ"

Prefer: - "ผลลัพธ์เบื้องต้นของคุณ" - "แนวทางที่อาจสอดคล้อง" - "ลองสำรวจต่อ"

Exact copy ต้องได้รับการอนุมัติก่อน Production

------------------------------------------------------------------------

## 13. Design Tokens --- Pending Approval

ยังไม่ได้กำหนด: - exact color values - typography family - font weights -
spacing scale - radius - shadows - border thickness - icon set

Claude ห้ามกำหนดค่าเหล่านี้เป็น Final Design โดยพลการ

------------------------------------------------------------------------

## 14. UX Acceptance Criteria

หน้า Quiz ผ่านเมื่อ: - อ่านคำถามได้ชัด - ตอบได้ด้วย touch - Back แล้วคำตอบไม่หาย -
แก้คำตอบแล้วผลใช้ค่าล่าสุด - progress ถูกต้อง - mobile ใช้งานได้

หน้า Result ผ่านเมื่อ: - เห็น Role ranking - เห็น percentage - เห็น Description
/ Strength / Weakness / Career / Faculty - Download ทำงานจริง - Share
ไม่ทำลายข้อมูล

------------------------------------------------------------------------

## 15. UX Open Questions

1.  Landing ต้องการความยาวระดับไหน?
2.  5 DCode ต้องเป็น section แยกหรือเป็น journey animation?
3.  Start page ต้องมี disclaimer เรื่องแบบทดสอบหรือไม่?
4.  คำถาม 10 ข้อจะแสดงแบบ card, statement, scenario หรือรูปแบบอื่น?
5.  Answer control เป็น radio, card selection, slider หรือแบบอื่น?
6.  Result wheel ต้องการ visual แบบใด?
7.  Character อยู่ตำแหน่งไหนของ Result?
8.  Share ไปแพลตฟอร์มใด?
9.  Register มีวัตถุประสงค์อะไร?
10. Career page ต้องค้นหา/กรองได้หรือไม่?
