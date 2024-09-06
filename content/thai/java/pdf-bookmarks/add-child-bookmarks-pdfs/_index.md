---
title: เพิ่มบุ๊กมาร์กย่อยลงใน PDF
linktitle: เพิ่มบุ๊กมาร์กย่อยลงใน PDF
second_title: API การประมวลผล PDF ของ Java PDF ของ Aspose.PDF
description: เรียนรู้วิธีการปรับปรุงเอกสาร PDF ด้วยบุ๊กมาร์กย่อยโดยใช้ Aspose.PDF สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดสำหรับการนำทางและการจัดระเบียบที่ดีขึ้น
type: docs
weight: 11
url: /th/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## การแนะนำการเพิ่มบุ๊กมาร์กย่อยลงใน PDF

ในบทความนี้ เราจะมาสำรวจวิธีการเพิ่มบุ๊กมาร์กย่อยในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ Java บุ๊กมาร์กย่อยเป็นวิธีที่สะดวกในการจัดระเบียบและนำทางผ่านเนื้อหาของเอกสาร PDF ช่วยให้ผู้ใช้ค้นหาหัวข้อหรือส่วนที่ต้องการในเอกสารได้ง่ายขึ้น

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกการใช้งานจริง ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- สภาพแวดล้อมการพัฒนา Java ติดตั้งอยู่บนระบบของคุณ
-  Aspose.PDF สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/pdf/java/).

## การจัดเตรียมสภาพแวดล้อม

1. ดาวน์โหลดไลบรารี Aspose.PDF สำหรับ Java จากลิงก์ที่ให้มา
2. เพิ่มไลบรารีลงในโปรเจ็กต์ Java ของคุณ

ตอนนี้เรามาเริ่มต้นด้วยการสร้างเอกสาร PDF ใหม่และเพิ่มบุ๊กมาร์กย่อยลงไปทีละขั้นตอน

## การสร้างเอกสาร PDF ใหม่

ในการเริ่มต้น เราต้องสร้างเอกสาร PDF และเพิ่มหน้าเข้าไป นี่คือตัวอย่างโค้ดเพื่อเริ่มต้น:

```java
// เริ่มต้นเอกสาร PDF
Document pdfDocument = new Document();

// เพิ่มหน้าลงใน PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

ในตัวอย่างนี้ เราได้สร้างเอกสาร PDF ใหม่ และเพิ่มหน้าสองหน้าลงไป

## การเพิ่มบุ๊กมาร์กของผู้ปกครอง

บุ๊กมาร์กหลักทำหน้าที่เป็นส่วนหรือหมวดหมู่หลักในเอกสาร PDF ของคุณ มาสร้างบุ๊กมาร์กหลักกัน:

```java
// สร้างบุ๊กมาร์กของผู้ปกครอง
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

เราได้เพิ่มบุ๊กมาร์กหลัก 2 รายการคือ "บุ๊กมาร์กหลัก 1" และ "บุ๊กมาร์กหลัก 2"

## การเพิ่มบุ๊กมาร์กเด็ก

ตอนนี้ถึงเวลาเพิ่มบุ๊กมาร์กย่อยลงในบุ๊กมาร์กหลักที่เราสร้างไว้ก่อนหน้านี้แล้ว บุ๊กมาร์กย่อยจะแสดงหัวข้อหรือหัวข้อย่อยเฉพาะภายในบุ๊กมาร์กหลักแต่ละรายการ คุณสามารถทำได้ดังนี้:

```java
// เพิ่มบุ๊กมาร์กย่อยลงในบุ๊กมาร์กหลัก 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//เพิ่มบุ๊กมาร์กย่อยลงในบุ๊กมาร์กหลัก 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

เราได้เพิ่มบุ๊กมาร์กย่อยให้กับทั้ง "บุ๊กมาร์กหลัก 1" และ "บุ๊กมาร์กหลัก 2"

## การปรับแต่งรูปลักษณ์ของบุ๊กมาร์ก

คุณสามารถปรับแต่งรูปลักษณ์ของบุ๊กมาร์กได้โดยการเปลี่ยนข้อความและรูปแบบ นอกจากนี้ คุณยังสามารถเพิ่มไอคอนลงในบุ๊กมาร์กเพื่อให้แสดงภาพได้ดีขึ้น นี่คือตัวอย่างวิธีการดำเนินการ:

```java
// ปรับแต่งลักษณะที่ปรากฏของบุ๊กมาร์ก
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

ในตัวอย่างนี้ เราได้สร้างบุ๊กมาร์กหลักให้เป็นแบบเอียง เปลี่ยนสีข้อความของบุ๊กมาร์กย่อยเป็นสีเขียว และเพิ่มไอคอนแบบเอียงให้กับบุ๊กมาร์กย่อย

## การจัดการกิจกรรม

บุ๊กมาร์กสามารถมีการดำเนินการที่เกี่ยวข้องได้ด้วย ตัวอย่างเช่น คุณสามารถเพิ่มการดำเนินการที่จะทริกเกอร์เมื่อผู้ใช้คลิกที่บุ๊กมาร์ก นี่คือวิธีจัดการเหตุการณ์การคลิกบุ๊กมาร์ก:

```java
// เพิ่มการกระทำลงในบุ๊กมาร์ก
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

ในโค้ดนี้ เราได้เพิ่มการดำเนินการ "GoTo" ลงในบุ๊กมาร์กย่อย ซึ่งจะนำผู้ใช้ไปยังหน้าที่สองของ PDF เมื่อคลิก

## การบันทึกไฟล์ PDF

เมื่อคุณเพิ่มบุ๊กมาร์กที่จำเป็นทั้งหมดแล้ว และปรับแต่งลักษณะและการดำเนินการของบุ๊กมาร์กเหล่านั้น คุณสามารถบันทึกเอกสาร PDF ที่แก้ไขแล้วได้:

```java
// บันทึกเอกสาร PDF
pdfDocument.save("output.pdf");
```

ตอนนี้เอกสาร PDF ของคุณพร้อมบุ๊กมาร์กย่อยแล้ว

## ซอร์สโค้ดที่สมบูรณ์

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการเพิ่มบุ๊กมาร์กย่อยลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ Java:

```java
// เริ่มต้นเอกสาร PDF
Document pdfDocument = new Document();

// เพิ่มหน้าลงใน PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// สร้างบุ๊กมาร์กของผู้ปกครอง
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// เพิ่มบุ๊กมาร์กย่อยลงในบุ๊กมาร์กหลัก 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//เพิ่มบุ๊กมาร์กย่อยลงในบุ๊กมาร์กหลัก 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// ปรับแต่งลักษณะที่ปรากฏของบุ๊กมาร์ก
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

การเพิ่มบุ๊กมาร์กย่อยลงใน PDF โดยใช้ Aspose.PDF สำหรับ Java เป็นฟีเจอร์อันทรงพลังที่ช่วยเพิ่มการนำทางและการจัดระเบียบเอกสารของคุณ เมื่อทำตามขั้นตอนที่ระบุไว้ในบทความนี้ คุณก็สามารถสร้าง PDF ที่มีโครงสร้างที่ดีพร้อมบุ๊กมาร์กหลักและบุ๊กมาร์กย่อย ปรับแต่งรูปลักษณ์ของบุ๊กมาร์ก และเพิ่มการกระทำเพื่อปรับปรุงประสบการณ์ของผู้ใช้ได้

## คำถามที่พบบ่อย

### ฉันสามารถดาวน์โหลด Aspose.PDF สำหรับ Java ได้อย่างไร

 คุณสามารถดาวน์โหลด Aspose.PDF สำหรับ Java ได้จากเว็บไซต์[ที่นี่](https://releases.aspose.com/pdf/java/).

### โปรแกรมดู PDF ทั้งหมดรองรับบุ๊กมาร์กย่อยหรือไม่

ใช่ โปรแกรมดู PDF สมัยใหม่ส่วนใหญ่รองรับบุ๊กมาร์กสำหรับเด็ก และมอบประสบการณ์การใช้งานที่ดียิ่งขึ้นสำหรับการนำทางผ่านเอกสาร PDF

### ฉันสามารถปรับแต่งลักษณะของบุ๊กมาร์กเพิ่มเติมได้หรือไม่

ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏของบุ๊กมาร์กได้โดยการปรับแต่งรูปแบบข้อความ สีและไอคอนให้เหมาะกับการออกแบบเอกสารของคุณ

### ฉันสามารถเพิ่มการกระทำอื่น ๆ อะไรลงในบุ๊กมาร์กได้บ้าง

นอกจากการดำเนินการ "GoTo" แล้ว คุณสามารถเพิ่มการดำเนินการต่างๆ เช่น การดำเนินการ "URI" เพื่อเปิดลิงก์เว็บ หรือการดำเนินการ "JavaScript" เพื่อรันสคริปต์ที่กำหนดเองเมื่อมีการคลิกที่บุ๊กมาร์ก

### Aspose.PDF สำหรับ Java เหมาะกับโปรเจ็กต์เชิงพาณิชย์หรือไม่

ใช่ Aspose.PDF สำหรับ Java เหมาะสำหรับทั้งโปรเจ็กต์ส่วนบุคคลและเชิงพาณิชย์ และยังมีฟีเจอร์ต่างๆ มากมายสำหรับการจัดการและสร้าง PDF