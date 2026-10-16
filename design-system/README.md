# Discovery Design System

มาตรฐานการออกแบบกลางของ Discovery (Data Platform V4.1 · Storemesh) ใช้เป็นแหล่งอ้างอิงเดียวเวลาออกแบบหรือพัฒนาหน้าจอใหม่ ฉบับที่ดูได้แบบมีตัวอย่าง component อยู่ใน Discovery Design System บน Claude

| ไฟล์ | ใช้ทำอะไร |
|---|---|
| `tokens.json` | ค่าสี ตัวอักษร ระยะห่าง มุมโค้ง เงา พร้อมคำอธิบายการใช้ (แหล่งข้อมูลหลัก) |
| `tokens.css` | CSS variables และ class ตัวอักษร สร้างจาก `tokens.json` ใส่ในหน้าเว็บได้ทันที |
| `components/discovery-components.css` | สไตล์ component ทั้ง 12 ตัว (ใช้คู่กับ `tokens.css`) |
| `components/*.md` | แนวทางการใช้ component แต่ละตัว |
| `assets/discovery-mark.png` | โลโก้ |

วิธีใช้ในหน้าเว็บ: โหลด `tokens.css` แล้วตามด้วย `components/discovery-components.css` จากนั้นใส่ class `dd` ที่ element นอกสุด

---

Discovery เป็นแอปใน Data Platform V4.1 ของ Storemesh สำหรับ Project Manager และ Data Engineer ใช้ออกแบบชุดข้อมูล ตรวจโครงสร้าง และติดตามคุณภาพข้อมูล หน้าจอเน้นข้อมูลหนาแน่น (data-heavy) จึงใช้พื้นขาวสะอาดตาแนว Google Drive / Material Design 3 และใช้สีบอกสถานะคุณภาพเท่านั้น

## เนื้อหาและน้ำเสียง

- ข้อความบนหน้าจอเป็น**ภาษาอังกฤษ** ส่วนคู่มือและเอกสารเป็นภาษาไทย
- ปุ่มและเมนูระดับหน้าใช้ Title Case: "Create Data Product", "Add Row", "Platform Overview" ส่วน action ในแถวและข้อความอื่นใช้ sentence case: "Add to dictionary", "No description yet", "Right-click to rename or delete"
- ใช้คำศัพท์ชุดเดียวกันทุกหน้า: Data Product, Source, Data Dictionary, Preview, Lineage, Pass, Chain Exhausted, Completeness, E-Score, Missing, Not in design ห้ามใช้คำพ้อง เช่น dataset, table, origin
- Completeness คือสัดส่วนช่องที่**มีค่า** (ยิ่งสูงยิ่งดี) ทั้งในตารางและในกราฟ
- ตัวเลขเปอร์เซ็นต์เป็นจำนวนเต็ม (90%) ตัวเลขนับมีจุลภาค (1,800) วันที่บนปุ่มและแกนกราฟใช้รูปแบบสั้น "9 Oct" ใน Tooltip ใช้รูปแบบเต็ม "Fri, 9 Oct 2026" ในตารางใช้ dd/mm/yyyy
- ยังไม่มีข้อมูล แสดง "—" และป้าย "No data" ห้ามแสดง 0 แทน "ไม่มีข้อมูล"
- กล่องยืนยันบอกผลกระทบเป็นข้อ ๆ ก่อนให้กดยืนยัน ("What changes when you rename") ข้อความยืนยันหลังทำเสร็จเป็นอดีตกาล: Renamed "clean_data" to "trade_quality"
- ไม่ใช้ emoji

## สี

- พื้นหลักใช้ `surface` ส่วน sidebar, แถบตัวกรอง, หัวตาราง และการ์ด KPI ใช้ `surface-dim`
- ข้อความหลักใช้ `ink` ข้อความรองใช้ `ink-muted` และใช้ `ink-faint` เฉพาะ hint กับ "—" เท่านั้น (คอนทราสต์ไม่ผ่านเกณฑ์ข้อความ)
- `primary` ใช้กับสิ่งที่กดได้เท่านั้น: ปุ่มหลัก แท็บที่เลือก ไอคอนปฏิทิน focus ring
- สถานะที่เลือกใช้ `secondary-container` คู่กับ `on-secondary-container`: เมนูที่เปิดอยู่ Source chip และ preset ที่ตรงกับช่วงวันที่
- `brand` (#02A6E7) เป็นสีของโลโก้เท่านั้น ไม่ใช้กับข้อความหรือปุ่ม
- สีสถานะคุณภาพข้อมูลใช้ตามความหมายเสมอ และต้องมีคำหรือตัวเลขกำกับ ไม่ใช้สีอย่างเดียว:

| ตัวชี้วัด | ดี | เฝ้าระวัง | ต้องแก้ |
|---|---|---|---|
| E-Score | ≥ 80% `success` | 70–79% ส้ม | < 70% `danger` |
| Chain Exhausted | ≤ 10% | – | > 10% `danger-action` |
| Completeness | ≥ 90% | < 90% `warning` | – |
| คอลัมน์ใน Data Dictionary | ตรงกับแบบ (ไม่มีป้าย) | Missing `warning-soft` · Not in design `info-soft` | – |

- กราฟ Data Quality Trend: Pass เส้น `success-mark`, Chain Exhausted เส้น `danger-mark`, Completeness เส้นประ `info` แต่ละเส้นต้องมี legend เสมอ

## ตัวอักษร

ขนาดตัวอักษรทั้งหมด**ตรงกับ Google Drive** ซึ่งใช้ type scale ของ Material 3 ห้ามใช้ขนาดอื่นนอกตารางนี้ Google Drive ใช้ฟอนต์ Google Sans ซึ่งไม่เปิดให้ใช้ทั่วไป ระบบนี้จึงใช้ Inter แทน ส่วนตัวเลขนับ ชื่อคอลัมน์ ชื่อไฟล์ และชื่อกฎใช้ monospace และข้อความภาษาไทยในเอกสารใช้ `thai`

| Style (M3) | ขนาด / บรรทัด · น้ำหนัก | เทียบกับ Google Drive | ใช้กับ |
|---|---|---|---|
| `headline-medium` | 28 / 36 · 400 | – | ค่า E-Score ตัวใหญ่ (หน้าละ 1 จุด) |
| `headline-small` | 24 / 32 · 400 | ชื่อหน้า "My Drive" และชื่อ dialog "Rename" | ชื่อหน้า ชื่อ Data Product ชื่อ Modal |
| `title-large` | 22 / 28 · 400 | คำว่า "Drive" ข้างโลโก้ | คำว่า "Discovery" ข้างโลโก้ และตัวเลขในการ์ด KPI |
| `title-medium` | 16 / 24 · 500 | หัวข้อส่วน "Suggested files" | หัวข้อการ์ดและหัวข้อส่วน |
| `body-medium` | 14 / 20 · 400 (ป้ายและปุ่ม 500) | รายการไฟล์ เมนูซ้าย chip เมนู | ข้อมูลและหัวตาราง เมนู sidebar แท็บ ปุ่ม ตัวกรอง เมนูคลิกขวา toast |
| `body-small` | 12 / 16 · 400 | บรรทัดพื้นที่จัดเก็บ tooltip | คำอธิบายใต้หัวข้อ tooltip บรรทัด Storage ป้ายสถานะ E-Score |
| `label-small` | 11 / 16 · 500 | – | ป้าย chip ข้อความช่วยใต้ช่อง แกนและ legend ของกราฟ |

- หัวข้อทุกระดับใช้ sentence case หรือ Title Case **ไม่ใช้ตัวพิมพ์ใหญ่ทั้งคำ** ตามแบบ Google Drive (เช่น "All Data Product Table", "Top Issues")
- ชื่อหน้าและชื่อ Modal ใช้น้ำหนัก 400 ไม่ใช้ตัวหนา

## ระยะห่าง มุมโค้ง และเงา

- ระยะห่างใช้ฐาน 4px: `space-1` 4 · `space-2` 8 · `space-3` 12 · `space-4` 16 · `space-6` 24 · `space-8` 32 ช่องในตารางใช้ 14px × 24px ตามต้นแบบ
- มุมโค้งบอกบทบาท: ปุ่ม ป้าย chip และ nav pill ใช้ `radius-full` · select, ปุ่ม Time Range และเมนูใช้ `radius-lg` · การ์ด ตาราง และแถบตัวกรองใช้ `radius-xl` · Modal ใช้ `radius-dialog` (28px)
- เงาใช้น้อย: `shadow-xs` เป็นค่าปกติของการ์ดและปุ่ม `shadow-menu` สำหรับเมนูและ toast `shadow-dialog` สำหรับ Modal เท่านั้น แยกส่วนด้วยเส้นขอบ `border` มากกว่าเงา

## สถานะของ control

- Hover: nav pill ใช้ `surface-container-high` แถวตารางใช้ `row-hover` ปุ่มข้อความใช้ `primary-soft`
- Focus: เส้น `primary` ทึบ 2px เว้นระยะ 2px
- Disabled: ความทึบ 45% ไม่มีเงา และบอกเหตุผลใกล้ ๆ ปุ่ม
- การลบต้องพิมพ์ชื่อให้ตรงก่อนกด การเปลี่ยนชื่อต้องติ๊กยืนยันว่าเข้าใจผลกระทบ

## ไอคอน

- ใช้ไอคอนแบบเส้น (outline) กรอบ 24 × 24 เส้นหนา 2 ปลายมน แบบ Heroicons วาดเป็น inline SVG ใช้ `currentColor`
- ขนาด 16px ใน control ตาราง และการ์ด ส่วน 20px ใน sidebar และไอคอนสถานะใน Modal
- ไอคอนที่ใช้: home, plus, document, calendar, chevron-down, chevron-right, pencil, trash, rows, columns, archive, check-circle, exclamation

## โลโก้

- ใช้ไฟล์ `assets/Logos/discovery-mark.png` (สัญลักษณ์ดอกจันสีขาวบนสี่เหลี่ยม `brand`) ห้ามวาดใหม่ เปลี่ยนสี หรือยืดสัดส่วน
- ใน sidebar แสดงขนาด 40px มุม 8px คู่กับคำว่า "Discovery" คำเดียว ขนาด `title-large` (22px น้ำหนัก 400) สี `ink-muted` แบบเดียวกับ "Drive" ใน Google Drive ห้ามเติมคำว่า Application
- ใช้เป็น favicon ของแอปด้วย ขนาดเล็กสุดที่ใช้ได้คือ 16px

## การเข้าถึง

คู่สีจากต้นแบบที่คอนทราสต์ไม่ถึงเกณฑ์ (คงไว้ตามต้นแบบ และระบุไว้ใน usage ของ token): `ink-faint` 2.5:1, `info` 3.7:1 และ `warning` 3.6:1 เมื่อเป็นข้อความบน `surface`, `success-mark` 2.3:1 ในกราฟ, `border-control` 1.5:1 สำหรับขอบ control ถ้าจะปรับ ให้เพิ่ม theme ความคมชัดสูงแยกไว้ ไม่แก้สีของแบรนด์เดิม
