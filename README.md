# Convert PRD

Skill สำหรับแปลงเสียงหรือวิดีโอการประชุมเป็นเอกสาร PRD ภาษาไทย โดยใช้ workflow เดียวกันบน Codex, Claude Code และ agent ที่รองรับรูปแบบ Agent Skills

## Workflow

1. ถอดเสียงและสรุปด้วย `references/Prompt_Transcript.md` → `Transcript.md`
2. สกัด requirements ด้วย `references/Convert_Requirement.md` → `Raw_Requirements.md`
3. จัดทำ PRD ด้วย `references/Convert_to_PRD.md` → `PRD.md`
4. ตรวจความครบถ้วน รหัสอ้างอิง และ Acceptance Criteria ก่อนส่งมอบ

คง `[AMBIGUOUS]` และ `[DRAFT]` สำหรับข้อมูลที่ยังไม่ยืนยัน ไม่แต่ง requirement เพิ่ม

## ติดตั้ง

Repository นี้เป็น Private ต้องใช้บัญชี GitHub ที่มีสิทธิ์เข้าถึงและตั้งค่า Git authentication ก่อน
คำสั่งด้านล่างต้องใช้ Git และ shell ที่รองรับรูปแบบ POSIX
หากโฟลเดอร์ปลายทางมีอยู่แล้ว อย่าเขียนทับ ให้ตรวจเวอร์ชันเดิมและสำรองการแก้ไขก่อนอัปเดต

### Codex

```sh
git clone https://github.com/NUX-Design/convert-prd.git "${CODEX_HOME:-$HOME/.codex}/skills/convert-prd"
```

เรียกใช้:

```text
ใช้ $convert-prd แปลงไฟล์เสียงที่แนบเป็น PRD.md
```

### Claude Code

ติดตั้งสำหรับผู้ใช้:

```sh
git clone https://github.com/NUX-Design/convert-prd.git "$HOME/.claude/skills/convert-prd"
```

หรือติดตั้งเฉพาะโปรเจกต์ โดยรันจากโฟลเดอร์โปรเจกต์:

```sh
git clone https://github.com/NUX-Design/convert-prd.git .claude/skills/convert-prd
```

เรียกใช้:

```text
/convert-prd แปลงไฟล์เสียงที่แนบเป็น PRD.md
```

### Agent อื่น ๆ

สำหรับ agent ที่รองรับ Agent Skills ให้ clone หรือคัดลอก repo ทั้งชุดเป็นโฟลเดอร์ `convert-prd` ในตำแหน่ง skills ที่ agent นั้นกำหนด โดยเก็บ `SKILL.md` และ `references/` ไว้ด้วยกัน ตำแหน่งติดตั้งและวิธีเรียกใช้ขึ้นกับ agent ไม่ใช่ทุก agent จะค้นพบ skill อัตโนมัติ

หาก agent อ่านไฟล์ Markdown ได้แต่ไม่มีระบบ skills ให้ระบุให้ agent อ่าน `SKILL.md` และไฟล์อ้างอิงตามขั้นตอนโดยตรง

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

รัน `git pull --ff-only` ภายในโฟลเดอร์ที่ clone หลังตรวจว่าการแก้ไขในเครื่องถูกเก็บแล้ว

## เอกสารอ้างอิง

- [Agent Skills specification](https://agentskills.io/specification)
- [Claude Code skills](https://code.claude.com/docs/en/skills)

ต้นทาง: skill `convert-prd` จาก [NUX-Design/uxui_skills_a](https://github.com/NUX-Design/uxui_skills_a)
