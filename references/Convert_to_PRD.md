# Convert_to_PRD

## TASK

ให้นำ raw requirements summary จากด้านบนมาจัดทำเป็น PRD v1  
โดยใช้ template ที่ฉันจะให้ด้านล่าง

## STEPS

1. นำ Problems / Goals / Users / Use Cases / FR / BR จาก summary ไปจัดลงใน section ที่ถูกต้องของ PRD template
2. กำหนด ID ดังนี้:

   - PRD-ID: PRD--001
   - FR-IDs: FR--00X
   - UC-IDs: UC-00X
   - FLOW-IDs: FLOW--00X
   - AC-IDs: AC--00X

3. สำหรับแต่ละ Functional Requirement:

   - เขียนว่า ระบบต้องทำอะไร (WHAT) ในความยาว 1-3 ประโยค
   - อ้างอิงกลับไปยัง Use Cases และ Problems ที่เกี่ยวข้องด้วย ID

4. สำหรับแต่ละ FR ที่สำคัญ:

   - เสนอ Acceptance Criteria จำนวน 1-3 ข้อ ในรูปแบบ Given / When / Then
   - ให้ใส่เครื่องหมาย [DRAFT] ถ้าสิ่งนั้นไม่ได้ถูกระบุไว้อย่างชัดเจนใน input

5. หากมีข้อมูลที่ตกหล่น หรือยังไม่ชัดเจน ให้นำไปไว้ในหัวข้อ Open Questions

## RULES

- ห้ามสร้างฟีเจอร์ใหม่ที่ไม่มีอยู่ในข้อมูลต้นทาง ทั้งแบบระบุชัดเจนหรือโดยนัย
- ถ้าจำเป็นต้องมีการสมมติ ให้ระบุอย่างชัดเจนไว้ในหัวข้อ Assumptions
- ใช้หัวข้อใน PRD template ตามต้นฉบับแบบตรงตัว

## RAW SUMMARY

<วาง Requirement ที่ได้จากการทำ Convert Requirement ที่นี่>

## PRD TEMPLATE

# PRD: <ชื่อฟีเจอร์ / ชื่อโปรเจกต์> (PRD-ID: )

- เวอร์ชัน: 1.0
- สถานะ: Draft | In Review | Approved
- Owner:
- อัปเดตล่าสุด:

## 1. Product Context

- ฟีเจอร์/โปรดักต์นี้คืออะไร?
- ทำไมต้องทำตอนนี้? (บริบทธุรกิจ / บริบทผู้ใช้)

## 2. Problem Statement

- เรากำลังแก้ปัญหาอะไร?
- ใครคือคนที่มีปัญหาเหล่านี้?

## 3. Goals & Non-goals

- Goals (ถ้าวัดผลได้ให้ระบุด้วย)
- Non-goals (สิ่งที่เราระบุชัดเจนว่าจะไม่ทำ)

## 4. Target Users / Personas

- Persona 1: คำอธิบายสั้น ๆ + ความต้องการหลัก
- Persona 2: ...

## 5. Use Cases / Jobs To Be Done

- UC-001: ในฐานะ <ผู้ใช้> ฉันต้องการ <การกระทำ> เพื่อให้ <คุณค่า/ผลลัพธ์>
- UC-002: ...

## 6. Assumptions / Constraints / Dependencies

## 7. Functional Requirements

### FR-XXX-001: <ชื่อหัวข้อ>

- คำอธิบาย (ระบุว่า WHAT ไม่ใช่ HOW)
- Use cases ที่เกี่ยวข้อง: [UC-001,...]
- ผู้ใช้งานหลัก / actor หลัก:
- Triggers / inputs:
- ผลลัพธ์ที่คาดหวัง:

### FR-XXX-002: ...

## 8. Non-functional Requirements

- Performance:
- Reliability:
- Security / privacy:
- UX / accessibility:

## 9. Business Rules

- BR-XXX-001:
- BR-XXX-002:

## 10. User Flows (High-level)

- FLOW-XXX-001: <ชื่อ flow> (ลำดับขั้นตอน 1–n โดยยังไม่ลงรายละเอียด UI)

## 11. Edge Cases & Error Scenarios

## 12. Out-of-scope

## 13. Success Metrics

## 14. Acceptance Criteria (แยกตาม FR)

### AC-XXX-001 (สำหรับ FR-XXX-001)

GIVEN ...  
WHEN ...  
THEN ...

## 15. Open Questions

## 16. Changelog

- v1.0 - ดราฟต์แรกจาก discovery meeting
