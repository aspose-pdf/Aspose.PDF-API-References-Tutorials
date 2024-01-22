---
title: เพิ่มบุ๊คมาร์คเด็กลงใน PDF
linktitle: เพิ่มบุ๊คมาร์คเด็กลงใน PDF
second_title: Aspose.PDF Java PDF การประมวลผล API
description: เรียนรู้วิธีปรับปรุงเอกสาร PDF ด้วยบุ๊กมาร์กลูกโดยใช้ Aspose.PDF สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดเพื่อปรับปรุงการนำทางและการจัดระเบียบ
type: docs
weight: 11
url: /th/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการเพิ่มบุ๊คมาร์คเด็กลงใน PDF

ในบทความนี้ เราจะสำรวจวิธีเพิ่มบุ๊กมาร์กลูกลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ Java บุ๊กมาร์กเด็กเป็นวิธีที่สะดวกในการจัดระเบียบและนำทางผ่านเนื้อหาของเอกสาร PDF ทำให้ผู้ใช้สามารถค้นหาส่วนหรือหัวข้อเฉพาะภายในเอกสารได้ง่ายขึ้น

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกเรื่องการนำไปใช้งาน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- สภาพแวดล้อมการพัฒนา Java ที่ติดตั้งบนระบบของคุณ
-  Aspose.PDF สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/pdf/java/).

## การตั้งค่าสภาพแวดล้อม

1. ดาวน์โหลดไลบรารี Aspose.PDF สำหรับ Java จากลิงก์ที่ให้ไว้
2. เพิ่มไลบรารีให้กับโปรเจ็กต์ Java ของคุณ

ตอนนี้เรามาเริ่มต้นด้วยการสร้างเอกสาร PDF ใหม่และเพิ่มบุ๊กมาร์กย่อยลงไปทีละขั้นตอน

## การสร้างเอกสาร PDF ใหม่

ในการเริ่มต้น เราต้องเริ่มต้นเอกสาร PDF และเพิ่มหน้าเข้าไป นี่คือข้อมูลโค้ดสำหรับเริ่มต้น:

```java
// เริ่มต้นเอกสาร PDF
Document pdfDocument = new Document();

// เพิ่มหน้าลงใน PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

ในตัวอย่างนี้ เราได้สร้างเอกสาร PDF ใหม่และเพิ่มสองหน้าลงไป

## การเพิ่มบุ๊กมาร์กผู้ปกครอง

บุ๊กมาร์กหลักทำหน้าที่เป็นส่วนหลักหรือหมวดหมู่ในเอกสาร PDF ของคุณ มาสร้างบุ๊กมาร์กหลักกัน:

```java
// สร้างบุ๊กมาร์กผู้ปกครอง
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

เราได้เพิ่มบุ๊กมาร์กหลักสองรายการ ได้แก่ "บุ๊กมาร์กหลัก 1" และ "บุ๊กมาร์กหลัก 2"

## การเพิ่มบุ๊กมาร์กเด็ก

ถึงเวลาเพิ่มบุ๊กมาร์กย่อยลงในบุ๊กมาร์กหลักที่เราสร้างไว้ก่อนหน้านี้ บุ๊กมาร์กย่อยแสดงถึงหัวข้อหรือส่วนย่อยเฉพาะภายในบุ๊กมาร์กหลักแต่ละอัน ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```java
// เพิ่มบุ๊กมาร์กลูกไปที่บุ๊กมาร์กหลัก 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//เพิ่มบุ๊กมาร์กลูกไปที่ Parent Bookmark 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

เราได้เพิ่มบุ๊กมาร์กย่อยให้กับทั้ง "บุ๊กมาร์กหลัก 1" และ "บุ๊กมาร์กหลัก 2"

## การปรับแต่งลักษณะที่ปรากฏของบุ๊กมาร์ก

คุณสามารถปรับแต่งรูปลักษณ์ของบุ๊กมาร์กได้โดยเปลี่ยนข้อความและสไตล์ นอกจากนี้ คุณสามารถเพิ่มไอคอนลงในบุ๊กมาร์กเพื่อให้เห็นภาพได้ดีขึ้น นี่คือตัวอย่างวิธีการ:

```java
// ปรับแต่งรูปลักษณ์บุ๊กมาร์ก
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

ในตัวอย่างนี้ เราได้ทำให้บุ๊กมาร์กหลักเป็นตัวเอียง เปลี่ยนสีข้อความของบุ๊กมาร์กลูกเป็นสีเขียว และเพิ่มไอคอนตัวเอียงให้กับบุ๊กมาร์กลูก

## การจัดการเหตุการณ์

บุ๊กมาร์กยังสามารถมีการดำเนินการที่เกี่ยวข้องกันได้ ตัวอย่างเช่น คุณสามารถเพิ่มการกระทำที่เกิดขึ้นเมื่อผู้ใช้คลิกที่บุ๊กมาร์ก ต่อไปนี้คือวิธีที่คุณสามารถจัดการกับเหตุการณ์การคลิกบุ๊กมาร์ก:

```java
// เพิ่มการกระทำลงในบุ๊กมาร์ก
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

ในโค้ดนี้ เราได้เพิ่มการดำเนินการ "GoTo" ลงในบุ๊กมาร์กย่อยที่จะนำผู้ใช้ไปยังหน้าที่สองของ PDF เมื่อคลิก

## กำลังบันทึก PDF

เมื่อคุณเพิ่มบุ๊กมาร์กที่จำเป็นทั้งหมดและปรับแต่งรูปลักษณ์และการทำงานแล้ว คุณสามารถบันทึกเอกสาร PDF ที่แก้ไขแล้วได้:

```java
// บันทึกเอกสาร PDF
pdfDocument.save("output.pdf");
```

เอกสาร PDF ของคุณพร้อมบุ๊กมาร์กลูกพร้อมแล้ว

## กรอกซอร์สโค้ดให้สมบูรณ์

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการเพิ่มบุ๊กมาร์กลูกลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ Java:

```java
// เริ่มต้นเอกสาร PDF
Document pdfDocument = new Document();

// เพิ่มหน้าลงใน PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// สร้างบุ๊กมาร์กผู้ปกครอง
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// เพิ่มบุ๊กมาร์กลูกไปที่บุ๊กมาร์กหลัก 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//เพิ่มบุ๊กมาร์กลูกไปที่ Parent Bookmark 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// ปรับแต่งรูปลักษณ์บุ๊กมาร์ก
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// เพิ่มการกระทำลงในบุ๊กมาร์ก
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// บันทึกเอกสาร PDF
pdfDocument.save("output.pdf");
```

## บทสรุป

การเพิ่มบุ๊กมาร์กลูกลงใน PDF โดยใช้ Aspose.PDF สำหรับ Java เป็นคุณสมบัติอันทรงพลังที่ปรับปรุงการนำทางและการจัดระเบียบเอกสารของคุณ เมื่อทำตามขั้นตอนที่อธิบายไว้ในบทความนี้ คุณจะสามารถสร้าง PDF ที่มีโครงสร้างที่ดีพร้อมบุ๊กมาร์กหลักและรอง ปรับแต่งลักษณะที่ปรากฏ และเพิ่มการดำเนินการเพื่อปรับปรุงประสบการณ์ผู้ใช้ได้

## คำถามที่พบบ่อย

### ฉันจะดาวน์โหลด Aspose.PDF สำหรับ Java ได้อย่างไร

 คุณสามารถดาวน์โหลด Aspose.PDF สำหรับ Java ได้จากเว็บไซต์[ที่นี่](https://releases.aspose.com/pdf/java/).

### บุ๊กมาร์กลูกรองรับโปรแกรมดู PDF ทั้งหมดหรือไม่

ใช่ บุ๊กมาร์กย่อยได้รับการสนับสนุนในโปรแกรมดู PDF ที่ทันสมัยที่สุด และมอบประสบการณ์ผู้ใช้ที่ได้รับการปรับปรุงสำหรับการนำทางผ่านเอกสาร PDF

### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของบุ๊กมาร์กเพิ่มเติมได้หรือไม่

ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของบุ๊กมาร์กได้โดยการปรับสไตล์ข้อความ สี และไอคอนให้เหมาะกับการออกแบบเอกสารของคุณ

### ฉันสามารถเพิ่มการดำเนินการอื่นใดลงในบุ๊กมาร์กได้บ้าง?

นอกจากการดำเนินการ "GoTo" แล้ว คุณยังสามารถเพิ่มการดำเนินการ เช่น การดำเนินการ "URI" เพื่อเปิดลิงก์เว็บ หรือการดำเนินการ "JavaScript" เพื่อเรียกใช้สคริปต์ที่กำหนดเองเมื่อมีการคลิกบุ๊กมาร์ก

### Aspose.PDF สำหรับ Java เหมาะสำหรับโครงการเชิงพาณิชย์หรือไม่

ใช่ Aspose.PDF สำหรับ Java เหมาะสำหรับทั้งโครงการส่วนบุคคลและเชิงพาณิชย์ และมีคุณสมบัติที่หลากหลายสำหรับการจัดการและสร้าง PDF