# Convert PRD

Skill สำหรับแปลงเสียงหรือวิดีโอการประชุมเป็นเอกสาร PRD ภาษาไทย โดยใช้ workflow เดียวกันบน Codex, Claude Code และ agent ที่รองรับรูปแบบ Agent Skills

## Workflow

1. ถอดเสียงและสรุปด้วย `references/Prompt_Transcript.md` → `Transcript.md`
2. สกัด requirements ด้วย `references/Convert_Requirement.md` → `Raw_Requirements.md`
3. จัดทำ PRD ด้วย `references/Convert_to_PRD.md` → `PRD.md`
4. ตรวจความครบถ้วน รหัสอ้างอิง และ Acceptance Criteria ก่อนส่งมอบ

คง `[AMBIGUOUS]` และ `[DRAFT]` สำหรับข้อมูลที่ยังไม่ยืนยัน ไม่แต่ง requirement เพิ่ม

## ติดตั้ง

เปิดแชตกับ Codex, Claude Code หรือ agent ที่ใช้อยู่ แล้ววางข้อความนี้ได้เลย:

```text
ช่วยติดตั้ง skill convert-prd จาก repo นี้ให้ใช้งานใน agent ที่ฉันกำลังใช้:
https://github.com/NUX-Design/convert-prd

คุณเข้าถึง repo นี้ได้แล้ว ให้ติดตั้ง SKILL.md พร้อม references และไฟล์ประกอบให้ครบ
เลือกตำแหน่งติดตั้งที่ agent นี้รองรับ ตรวจสอบว่าติดตั้งสำเร็จ แล้วบอกวิธีเรียกใช้ให้ฉันด้วย
หากมี skill เวอร์ชันเดิมอยู่แล้ว ให้ตรวจและรักษาการแก้ไขในเครื่องก่อนอัปเดต
```

ไม่ต้องรันคำสั่ง Terminal เอง โดย agent ต้องมีเครื่องมือเข้าถึง GitHub และเขียนไฟล์ในเครื่องได้ Repo นี้เป็น Private จึงต้องใช้บัญชีที่มีสิทธิ์เข้าถึง หาก agent ยังเข้าถึงไม่ได้ ให้เชื่อมต่อ GitHub ใน agent นั้นก่อน

### ตัวอย่างสั้นสำหรับแต่ละ agent

**Codex**

```text
ติดตั้ง skill นี้ใน Codex ให้หน่อย https://github.com/NUX-Design/convert-prd
```

**Claude Code**

```text
ติดตั้ง skill นี้ใน Claude Code ให้ใช้ได้ทุกโปรเจกต์ https://github.com/NUX-Design/convert-prd
```

**Agent อื่น ๆ**

```text
ติดตั้ง skill นี้ให้ใช้งานกับ agent นี้ https://github.com/NUX-Design/convert-prd
ตรวจรูปแบบและตำแหน่ง skills ที่รองรับ พร้อมคัดลอกไฟล์อ้างอิงให้ครบด้วย
```

Agent ที่ไม่มีระบบติดตั้ง skills หรือไม่มีสิทธิ์เขียนไฟล์ อาจต้องให้ผู้ใช้ติดตั้งเองตามวิธีของแพลตฟอร์มนั้น

## เรียกใช้งานหลังติดตั้ง

สำหรับ Codex:

```text
ใช้ $convert-prd แปลงไฟล์เสียงที่แนบเป็น PRD.md
```

สำหรับ Claude Code:

```text
/convert-prd แปลงไฟล์เสียงที่แนบเป็น PRD.md
```

สำหรับ agent อื่น ให้ใช้วิธีเรียกที่ agent แจ้งหลังติดตั้ง พร้อมแนบไฟล์เสียงหรือระบุ path ของไฟล์

## สิ่งที่ต้องมีและข้อจำกัด

- เครื่องมือถอดเสียงที่รองรับภาษาของไฟล์ และการอ่าน/เขียนไฟล์ใน workspace
- Repo นี้เป็นคำสั่งและ template ไม่ได้ติดตั้งบริการถอดเสียง API key หรือโมเดลเสียงให้
- หากไม่มีเครื่องมือถอดเสียง skill จะบอกข้อจำกัดและขอ Transcript แทน
- ผลลัพธ์เริ่มต้นอยู่ใน `.artifacts/convert-prd/<ชื่อไฟล์เสียง>/` หรือตำแหน่งที่ผู้ใช้ระบุ
- ตรวจโครงสร้างและความครบถ้วนของ package แล้ว การถอดเสียงจริงขึ้นกับเครื่องมือของแต่ละ agent; ไม่ได้ทดสอบ runtime ของทุก agent

## โครงสร้าง

```text
convert-prd/
├── SKILL.md
├── agents/openai.yaml
├── references/
│   ├── Prompt_Transcript.md
│   ├── Convert_Requirement.md
│   └── Convert_to_PRD.md
└── README.md
```

`SKILL.md` และ `references/` เป็นเนื้อหากลาง ส่วน `agents/openai.yaml` เป็น metadata ของ Codex

## อัปเดต

วางข้อความนี้ใน agent ที่ติดตั้ง skill ไว้:

```text
อัปเดต skill convert-prd จาก https://github.com/NUX-Design/convert-prd ให้หน่อย
ตรวจเวอร์ชันที่ติดตั้งและรักษาการแก้ไขในเครื่องก่อนอัปเดต แล้วตรวจว่าไฟล์ประกอบครบ
```

## เอกสารอ้างอิง

- [Agent Skills specification](https://agentskills.io/specification)
- [Claude Code skills](https://code.claude.com/docs/en/skills)

ต้นทาง: skill `convert-prd` จาก [NUX-Design/uxui_skills_a](https://github.com/NUX-Design/uxui_skills_a)
