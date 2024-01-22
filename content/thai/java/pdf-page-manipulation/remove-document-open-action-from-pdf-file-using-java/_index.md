---
title: ลบ Document Open Action ออกจากไฟล์ PDF โดยใช้ Java
linktitle: ลบ Document Open Action ออกจากไฟล์ PDF โดยใช้ Java
second_title: Aspose.PDF Java PDF การประมวลผล API
description: เรียนรู้วิธีลบ Document Open Action ออกจากไฟล์ PDF โดยใช้ Java และ Aspose.PDF สำหรับ Java เพิ่มความปลอดภัยและการปรับแต่ง
type: docs
weight: 11
url: /th/java/pdf-page-manipulation/remove-document-open-action-from-pdf-file-using-java/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการลบ Document Open Action จากไฟล์ PDF โดยใช้ Java

ไฟล์ PDF มักจะมี Document Open Actions ซึ่งสามารถดำเนินการเฉพาะเมื่อเปิด PDF อย่างไรก็ตาม ในบางกรณี คุณอาจต้องลบการกระทำนี้ออกเพื่อความปลอดภัยหรือการปรับแต่ง ในคำแนะนำทีละขั้นตอนนี้ เราจะสำรวจวิธีลบ Document Open Action ออกจากไฟล์ PDF โดยใช้ Java และ Aspose.PDF สำหรับ Java

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.PDF สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้ง Aspose.PDF สำหรับไลบรารี Java จาก[ที่นี่](https://releases.aspose.com/pdf/java/).

- สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา Java บนระบบของคุณ

## คำแนะนำทีละขั้นตอน

### 1. การโหลดเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ Java

ขั้นแรก เริ่มต้นด้วยการโหลดเอกสาร PDF ที่เราต้องการแก้ไข คุณสามารถใช้โค้ด Java ต่อไปนี้:

```java
// โหลดเอกสาร PDF
Document pdfDocument = new Document("input.pdf");
```

### 2. การระบุและการเข้าถึงเอกสาร Open Action

หากต้องการลบ Document Open Action เราจำเป็นต้องระบุและเข้าถึงภายในเอกสาร PDF ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```java
// เข้าถึงการดำเนินการเปิดเอกสาร
PdfAction openAction = pdfDocument.getOpenAction();
```

### 3. การลบการดำเนินการเปิดเอกสาร

ตอนนี้เรามาดำเนินการลบ Document Open Action กัน:

```java
// ลบการดำเนินการเปิดเอกสาร
pdfDocument.setOpenAction(null);
```

### 4. บันทึกเอกสาร PDF ที่แก้ไขแล้ว

สุดท้าย ให้บันทึกเอกสาร PDF ที่แก้ไขด้วย Document Open Action ที่ถูกลบออก:

```java
// บันทึก PDF ที่แก้ไขแล้ว
pdfDocument.save("output.pdf");
```

## ตัวอย่างซอร์สโค้ด

เพื่อความสะดวกของคุณ นี่คือข้อมูลโค้ดสำหรับแต่ละขั้นตอนพร้อมคำอธิบาย:

ขั้นตอนที่ 1: กำลังโหลดเอกสาร PDF
```java
Document pdfDocument = new Document("input.pdf");
```

ขั้นตอนที่ 2: การระบุและการเข้าถึงเอกสาร Open Action
```java
PdfAction openAction = pdfDocument.getOpenAction();
```

ขั้นตอนที่ 3: การลบการดำเนินการเปิดเอกสาร
```java
pdfDocument.setOpenAction(null);
```

ขั้นตอนที่ 4: บันทึกเอกสาร PDF ที่แก้ไข
```java
pdfDocument.save("output.pdf");
```

## บทสรุป

ในคู่มือนี้ เราได้เรียนรู้วิธีลบ Document Open Action ออกจากไฟล์ PDF โดยใช้ Java และ Aspose.PDF สำหรับ Java กระบวนการนี้สามารถปรับปรุงความปลอดภัยและการปรับแต่งเอกสาร PDF ของคุณได้ อย่าลืมสำรวจเอกสาร Aspose.PDF สำหรับ Java เพื่อดูคุณสมบัติและตัวเลือกขั้นสูงเพิ่มเติม

## คำถามที่พบบ่อย

### Document Open Action ทำงานอย่างไรในไฟล์ PDF

Document Open Action ในไฟล์ PDF เป็นคุณสมบัติที่ช่วยให้คุณระบุการดำเนินการที่จะดำเนินการเมื่อเปิดเอกสาร PDF การดำเนินการเหล่านี้อาจรวมถึงการนำทางไปยังหน้าใดหน้าหนึ่ง การเรียกใช้โค้ด JavaScript หรือการเปิดเว็บลิงก์

### เหตุใดฉันจึงต้องการลบ Document Open Action

คุณอาจต้องการลบ Document Open Action ด้วยเหตุผลด้านความปลอดภัย โดยเฉพาะอย่างยิ่งหากคุณได้รับ PDF ที่อาจเป็นอันตราย นอกจากนี้ยังมีประโยชน์เมื่อปรับแต่งลักษณะการทำงานของเอกสาร PDF อีกด้วย

### ฉันสามารถแก้ไข Document Open Action แทนที่จะลบออกได้หรือไม่

ได้ คุณสามารถแก้ไข Document Open Action ที่มีอยู่เพื่อปรับแต่งลักษณะการทำงานตามความต้องการของคุณได้ Aspose.PDF สำหรับ Java มีวิธีการแก้ไขการดำเนินการ

### Aspose.PDF สำหรับ Java เป็นไลบรารีเดียวที่จะลบ Document Open Action หรือไม่

ไม่ มีไลบรารีและเครื่องมืออื่นๆ สำหรับการทำงานกับ PDF ใน Java อย่างไรก็ตาม Aspose.PDF สำหรับ Java เป็นตัวเลือกยอดนิยมเนื่องจากมีคุณสมบัติที่แข็งแกร่งและใช้งานง่าย

### ฉันจะหาข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.PDF สำหรับ Java ได้ที่ไหน

 คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมสำหรับ Aspose.PDF สำหรับ Java ได้ที่[ที่นี่](https://reference.aspose.com/pdf/java/).