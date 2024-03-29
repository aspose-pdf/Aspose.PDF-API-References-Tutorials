---
title: เพิ่มข้อความที่หมุนใน PDF โดยใช้ Java
linktitle: เพิ่มข้อความที่หมุนใน PDF โดยใช้ Java
second_title: Aspose.PDF Java PDF การประมวลผล API
description: เรียนรู้วิธีแทรกข้อความที่หมุนลงในเอกสาร PDF โดยใช้ Java ทำตามคำแนะนำทีละขั้นตอนโดยละเอียดพร้อมตัวอย่างโค้ดเพื่อปรับปรุง PDF ของคุณด้วยข้อความที่หมุน
type: docs
weight: 14
url: /th/java/pdf-page-manipulation/add-rotated-text-in-pdf-using-java/
---

## การแนะนำ

ในบทช่วยสอนที่ครอบคลุมนี้ เราจะเจาะลึกกระบวนการเพิ่มข้อความที่หมุนลงในเอกสาร PDF โดยใช้ Java ไม่ว่าคุณจะต้องติดป้ายกำกับไดอะแกรม สร้างลายน้ำ หรือเพิ่มเอฟเฟกต์พิเศษให้กับ PDF ของคุณ คู่มือนี้จะแนะนำคุณตลอดขั้นตอนต่างๆ เราจะใช้ Aspose.PDF สำหรับ Java ซึ่งเป็นไลบรารีที่มีประสิทธิภาพสำหรับการจัดการ PDF เพื่อสาธิตกระบวนการ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว

2.  Aspose.PDF สำหรับ Java: ดาวน์โหลดและรวมไลบรารี Aspose.PDF ในโปรเจ็กต์ Java ของคุณ คุณสามารถค้นหาลิงค์ดาวน์โหลด[ที่นี่](https://releases.aspose.com/pdf/java/).

## ขั้นตอนที่ 1: สร้างเอกสาร PDF ใหม่

เริ่มต้นด้วยการสร้างเอกสาร PDF ใหม่โดยใช้ Aspose.PDF เอกสารนี้จะทำหน้าที่เป็นผืนผ้าใบสำหรับข้อความที่หมุนของเรา

```java
// เริ่มต้นเอกสาร PDF
com.aspose.pdf.Document pdfDocument = new com.aspose.pdf.Document();
```

## ขั้นตอนที่ 2: เพิ่มหน้า

จากนั้น เพิ่มหน้าลงในเอกสาร PDF ที่คุณต้องการแทรกข้อความที่หมุน:

```java
//เพิ่มหน้าใหม่ให้กับเอกสาร
com.aspose.pdf.Page page = pdfDocument.getPages().add();
```

## ขั้นตอนที่ 3: กำหนดข้อความที่หมุน

ตอนนี้ เรามากำหนดข้อความที่คุณต้องการแทรกและหมุนกัน คุณสามารถปรับแต่งข้อความ แบบอักษร และมุมการหมุนได้ตามความต้องการของคุณ:

```java
// กำหนดเนื้อหาข้อความ
String text = "Rotated Text Example";

// สร้างวัตถุ TextFragment
com.aspose.pdf.TextFragment textFragment = new com.aspose.pdf.TextFragment(text);

// กำหนดขนาดและรูปแบบตัวอักษร
textFragment.getTextState().setFontSize(12);
textFragment.getTextState().setFont(com.aspose.pdf.FontRepository.findFont("Arial"));

// กำหนดมุมการหมุน (เป็นองศา)
textFragment.setTextRotation(45);
```

ในตัวอย่างนี้ เราได้ตั้งค่าข้อความเป็น "ตัวอย่างข้อความแบบหมุน" เลือกแบบอักษร Arial ตั้งค่าขนาดแบบอักษรเป็น 12 และหมุนข้อความ 45 องศา ปรับพารามิเตอร์เหล่านี้ให้ตรงกับความต้องการเฉพาะของคุณ

## ขั้นตอนที่ 4: วางตำแหน่งข้อความที่หมุน

ระบุตำแหน่งบนหน้าที่คุณต้องการวางข้อความที่หมุน:

```java
// กำหนดตำแหน่งของข้อความ
textFragment.setPosition(new com.aspose.pdf.Position(100, 200));
```

ที่นี่ เราได้วางตำแหน่งข้อความไว้ที่พิกัด (100, 200) บนหน้า แก้ไขพิกัดเหล่านี้เพื่อวางข้อความในตำแหน่งที่คุณต้องการอย่างแม่นยำ

## ขั้นตอนที่ 5: เพิ่มข้อความที่หมุนไปที่หน้า

ตอนนี้ เพิ่มข้อความที่หมุนไปที่หน้า:

```java
// เพิ่มข้อความที่หมุนไปที่หน้า
page.getParagraphs().add(textFragment);
```

## ขั้นตอนที่ 6: บันทึก PDF

สุดท้าย ให้บันทึกเอกสาร PDF ด้วยข้อความที่หมุน:

```java
// บันทึกเอกสาร PDF
pdfDocument.save("output.pdf");
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการเพิ่มข้อความที่หมุนลงในเอกสาร PDF โดยใช้ Java และ Aspose.PDF สำหรับ Java คุณได้เรียนรู้วิธีสร้าง PDF ใหม่ กำหนดข้อความที่หมุนด้วยสไตล์ที่กำหนดเอง วางตำแหน่งบนหน้า และบันทึก PDF ที่แก้ไขแล้ว

ข้อความที่หมุนอาจเป็นส่วนเสริมอันทรงคุณค่าให้กับ PDF ของคุณเพื่อวัตถุประสงค์ต่างๆ เช่น การติดป้ายกำกับไดอะแกรม การใส่ลายน้ำ หรือการเพิ่มองค์ประกอบที่สร้างสรรค์ให้กับเอกสารของคุณ

ปรับปรุงเอกสาร PDF ของคุณด้วยการรวมข้อความที่หมุนได้อย่างง่ายดาย ด้วยความสามารถของ Aspose.PDF สำหรับ Java

---

## คำถามที่พบบ่อย (คำถามที่พบบ่อย)

### 1. ฉันสามารถหมุนข้อความตามมุมต่างๆ ใน PDF เดียวกันได้หรือไม่
   ได้ คุณสามารถเพิ่มข้อความที่หมุนแล้วหลายอินสแตนซ์พร้อมมุมที่แตกต่างกันลงในเอกสาร PDF เดียวกันได้ เพียงทำซ้ำขั้นตอนที่อธิบายไว้ในบทช่วยสอนนี้สำหรับข้อความที่หมุนแต่ละชิ้น

### 2. ฉันจะเปลี่ยนสีของข้อความที่หมุนได้อย่างไร?
    หากต้องการเปลี่ยนสีข้อความ ให้ใช้`textFragment.getTextState().setForegroundColor` วิธีการและระบุสีในรูปแบบ RGB ตัวอย่างเช่น หากต้องการตั้งค่าสีข้อความเป็นสีแดง ให้ใช้`textFragment.getTextState().setForegroundColor(com.aspose.pdf.Color.getRed());`.

### 3. Aspose.PDF สำหรับ Java เป็นไลบรารี่ฟรีหรือไม่
   Aspose.PDF สำหรับ Java เป็นไลบรารีเชิงพาณิชย์ที่ทรงพลัง แต่มีเวอร์ชันทดลองใช้ฟรีสำหรับการทดสอบและประเมินผล คุณสามารถเลือกตัวเลือกการออกใบอนุญาตที่เหมาะสมได้ ทั้งนี้ขึ้นอยู่กับข้อกำหนดของโครงการของคุณ

### 4. ฉันสามารถหมุนข้อความ 90 องศาเพื่อสร้างข้อความแนวตั้งได้หรือไม่
   ได้ คุณสามารถหมุนข้อความได้ 90 องศาเพื่อสร้างข้อความแนวตั้ง เพียงตั้งค่ามุมการหมุนเป็น 90 องศา แล้วข้อความจะปรากฏในแนวตั้งบนหน้า

### 5. มีไลบรารีอื่นสำหรับการทำงานกับ PDF ใน Java หรือไม่?
   ใช่ ไลบรารีหลายแห่ง เช่น iText และ PDFBox พร้อมใช้งานสำหรับการจัดการ PDF ใน Java แต่ละไลบรารีมีคุณสมบัติและความสามารถเฉพาะตัว ดังนั้นเลือกไลบรารีที่เหมาะกับความต้องการของโปรเจ็กต์ของคุณมากที่สุด