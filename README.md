# ติวสอบ IC License

เนื้อหาติวสอบใบอนุญาตผู้แนะนำการลงทุน (Investment Consultant) มีทั้งแบบฝึกหัด เฉลยพร้อมคำอธิบาย แผนการเรียน และเว็บบทเรียน

**เว็บบทเรียน:** https://triple-tgg.github.io/ic-plain-study/

## หลักสูตรที่มี

| หลักสูตร | เว็บ | เนื้อหาต้นฉบับ |
|---|---|---|
| IC Plain (ตราสารทั่วไป) | [เปิดเว็บ](https://triple-tgg.github.io/ic-plain-study/ic-plain/) | [`content/ic-plain/`](content/ic-plain/) |

## โครงสร้าง

```
.
├── docs/                         # เว็บไซต์ที่ GitHub Pages ใช้ deploy
│   ├── .nojekyll                 # เสิร์ฟไฟล์ตรง ๆ ไม่ผ่าน Jekyll
│   ├── index.html                # หน้าแรก (ตอนนี้พาไปหน้า ic-plain/)
│   └── ic-plain/
│       └── index.html            # เว็บบทเรียน IC Plain 28 วัน
└── content/                      # เนื้อหาต้นฉบับ (Markdown) แยกตามหลักสูตร
    └── ic-plain/
        ├── exercises/            # แบบฝึกหัด แยกเป็นชุด
        │   ├── 01-ethics.md
        │   ├── 02-calculation.md
        │   ├── 03-mutual-funds.md
        │   ├── 04-equity.md
        │   └── 05-debt-instruments.md
        └── guides/               # ไฟล์ที่เขียนเพิ่มจากแบบฝึกหัด
            ├── study-plan.md     # วิเคราะห์แบบฝึกหัด แผนเรียน 4 สัปดาห์ สูตร เทคนิค
            └── answer-key.md     # เฉลยครบทั้ง 5 ชุด พร้อมคำอธิบาย
```

### แบบฝึกหัด IC Plain

| ชุด | ไฟล์ | หัวข้อ | จำนวนข้อ |
|---|---|---|---|
| 1 | [`01-ethics.md`](content/ic-plain/exercises/01-ethics.md) | จรรยาบรรณ | 33 |
| 2 | [`02-calculation.md`](content/ic-plain/exercises/02-calculation.md) | คำนวณ | 39 |
| 3 | [`03-mutual-funds.md`](content/ic-plain/exercises/03-mutual-funds.md) | กองทุนรวม | 27 |
| 4 | [`04-equity.md`](content/ic-plain/exercises/04-equity.md) | ตราสารทุน | 26 |
| 5 | [`05-debt-instruments.md`](content/ic-plain/exercises/05-debt-instruments.md) | ตราสารหนี้ | 27 |

## วิธีเพิ่มเนื้อหา

### ตั้งชื่อไฟล์

- ใช้ภาษาอังกฤษตัวเล็ก คั่นคำด้วย `-` เช่น `06-derivatives.md` เพราะชื่อไทยจะกลายเป็น `%E0%B8...` ใน URL และ terminal
- แบบฝึกหัดให้ขึ้นต้นด้วยเลขชุดสองหลัก (`01-`, `02-`, …) ไฟล์จะได้เรียงตามลำดับ
- ใส่ชื่อหัวข้อภาษาไทยไว้ในหัวเรื่องบรรทัดแรกของไฟล์ แล้วเพิ่มในตารางของ README นี้

### เพิ่มแบบฝึกหัดชุดใหม่ในหลักสูตรที่มีอยู่

1. เพิ่มไฟล์ใน `content/<หลักสูตร>/exercises/` ใช้เลขชุดถัดไป
2. เพิ่มเฉลยของชุดนั้นใน `content/<หลักสูตร>/guides/answer-key.md`
3. อัปเดตตารางแบบฝึกหัดใน README

### เพิ่มหลักสูตรใหม่ (เช่น IC Complex)

1. สร้างโฟลเดอร์ `content/ic-complex/exercises/` และ `content/ic-complex/guides/`
2. ถ้ามีเว็บ ให้วางไว้ที่ `docs/ic-complex/index.html` เว็บจะอยู่ที่ `https://triple-tgg.github.io/ic-plain-study/ic-complex/`
3. เปลี่ยน `docs/index.html` จากหน้าที่พาไป ic-plain เป็นหน้ารวมลิงก์ทุกหลักสูตร
4. เพิ่มแถวในตาราง "หลักสูตรที่มี"

## Deploy

GitHub Pages ตั้งค่าให้ deploy จาก branch `main` โฟลเดอร์ `/docs` แค่ push ขึ้น `main` เว็บจะอัปเดตเองภายใน 1–2 นาที

```bash
git add .
git commit -m "อธิบายสิ่งที่เปลี่ยน"
git push
```

ไฟล์ HTML ใน `docs/` ต้องเป็นไฟล์เดียวจบ (CSS/JS อยู่ในไฟล์) หรืออ้างไฟล์อื่นด้วย path แบบ relative เท่านั้น ห้ามขึ้นต้นด้วย `/` เพราะเว็บอยู่ใต้ `/ic-plain-study/`
