---
title: ปรับแต่งโครงสร้างข้อความใน PDF โดยใช้ Java
linktitle: ปรับแต่งโครงสร้างข้อความใน PDF โดยใช้ Java
second_title: API การประมวลผล PDF ของ Java PDF ของ Aspose.PDF
description: เรียนรู้วิธีจัดรูปแบบโครงสร้างข้อความใน PDF โดยใช้ Java ด้วยคู่มือทีละขั้นตอนของเรา ปรับแต่งแบบอักษร สี ไฮเปอร์ลิงก์ และอื่นๆ เพื่อให้เอกสารดูเป็นมืออาชีพ
type: docs
weight: 11
url: /th/java/pdf-styles-and-formatting/style-text-structure-in-pdf-using-java/
---

## การแนะนำ

PDF กลายเป็นรูปแบบมาตรฐานสำหรับการแชร์เอกสาร รายงาน และเนื้อหาประเภทต่างๆ เมื่อทำงานกับ PDF ใน Java สิ่งสำคัญคือต้องไม่เพียงแค่เพิ่มข้อมูลลงในไฟล์เท่านั้น แต่ยังต้องปรับแต่งรูปแบบข้อความเพื่อให้ดูสวยงามด้วย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) แล้ว
- ดาวน์โหลดและตั้งค่าไลบรารี Aspose.PDF สำหรับ Java แล้ว

## การจัดเตรียมสภาพแวดล้อม

หากต้องการเริ่มจัดรูปแบบข้อความใน PDF โดยใช้ Java คุณต้องตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ ทำตามขั้นตอนเหล่านี้:

1.  ดาวน์โหลด Aspose.PDF สำหรับไลบรารี Java จาก[ที่นี่](https://releases.aspose.com/pdf/java/).

2. รวมไลบรารีไว้ในโครงการ Java ของคุณ

3. นำเข้าคลาสที่จำเป็นจาก Aspose.PDF ในโค้ดของคุณ

## การเพิ่มข้อความลงใน PDF

ตอนนี้เรามาเริ่มต้นด้วยการเพิ่มข้อความลงในเอกสาร PDF กัน นี่คือตัวอย่างง่ายๆ:

```java
// สร้างเอกสาร PDF ใหม่
com.aspose.pdf.Document pdfDocument = new com.aspose.pdf.Document();

// เพิ่มหน้าลงในเอกสาร
pdfDocument.getPages().add();

// สร้างวัตถุ TextFragment
com.aspose.pdf.TextFragment textFragment = new com.aspose.pdf.TextFragment("Hello, PDF!");

// เพิ่ม TextFragment ลงในหน้า
pdfDocument.getPages().get_Item(1).getParagraphs().add(textFragment);

// บันทึกเอกสาร
pdfDocument.save("output.pdf");
```

โค้ดนี้จะสร้างเอกสาร PDF เพิ่มหน้า และแทรกข้อความ "สวัสดี PDF!" ลงในหน้า

## การจัดรูปแบบตัวอักษร

คุณสามารถปรับแต่งแบบอักษรของข้อความได้ ต่อไปนี้คือวิธีเปลี่ยนแบบอักษรและขนาด:

```java
textFragment.getTextState().setFont(FontRepository.findFont("Arial"));
textFragment.getTextState().setFontSize(12);
```

## ขนาดและสีของตัวอักษร

การปรับขนาดและสีของข้อความเป็นเรื่องง่าย:

```java
textFragment.getTextState().setFontSize(16);
textFragment.getTextState().setForegroundColor(com.aspose.pdf.Color.getBlue());
```

## การจัดตำแหน่งข้อความ

ควบคุมการจัดตำแหน่งข้อความภายใน PDF ของคุณ:

```java
textFragment.getTextState().setHorizontalAlignment(HorizontalAlignment.Center);
```

## การเพิ่มส่วนหัวและส่วนท้าย

ปรับปรุงโครงสร้างเอกสารด้วยส่วนหัวและส่วนท้าย:

```java
Page page = pdfDocument.getPages().get_Item(1);
HeaderFooter header = new HeaderFooter();
page.setFooter(header);

TextFragment footerText = new TextFragment("Page Number: ");
header.getParagraphs().add(footerText);

footerText = new TextFragment("1");
footerText.getTextState().setFont(FontRepository.findFont("Arial"));
footerText.getTextState().setFontSize(12);
footerText.getTextState().setForegroundColor(com.aspose.pdf.Color.getBlack());

header.getParagraphs().add(footerText);
```

## การเพิ่มรายการแบบมีหัวข้อย่อย

สร้างรายการที่จัดระเบียบใน PDF ของคุณ:

```java
ListSection listSection = new ListSection();
page.getParagraphs().add(listSection);

TextFragmentListItem listItem = new TextFragmentListItem("Item 1");
listItem.getSegments().get_Item(0).getTextState().setFont(FontRepository.findFont("Arial"));
listItem.getSegments().get_Item(0).getTextState().setFontSize(12);
listSection.getListItems().add(listItem);

listItem = new TextFragmentListItem("Item 2");
listItem.getSegments().get_Item(0).getTextState().setFont(FontRepository.findFont("Arial"));
listItem.getSegments().get_Item(0).getTextState().setFontSize(12);
listSection.getListItems().add(listItem);
```

## การสร้างไฮเปอร์ลิงก์

เพิ่มไฮเปอร์ลิงก์ไปยัง PDF ของคุณสำหรับเนื้อหาแบบโต้ตอบ:

```java
TextFragment linkText = new TextFragment("Visit our website");
linkText.getTextState().setFont(FontRepository.findFont("Arial"));
linkText.getTextState().setFontSize(12);

Hyperlink link = new Hyperlink(linkText);
link.setAction(new GoToURIAction("https://www.example.com");

page.getParagraphs().add(link);
```

## การแปลงข้อความ

แปลงข้อความตามต้องการ:

```java
textFragment.getTextState().setTextRise(5); // ยกข้อความขึ้น
textFragment.getTextState().setTextScaling(200); // ปรับขนาดข้อความ
textFragment.getTextState().setUnderline(true);
```

## เค้าโครงหน้าและระยะขอบ

ควบคุมเค้าโครงของหน้า PDF ของคุณ:

```java
page.setPageSize(PageSize.getA4());
page.getPageInfo().getMargin().setLeft(50);
page.getPageInfo().getMargin().setRight(50);
```

## การจัดการการแบ่งหน้า

ให้แน่ใจว่าเนื้อหาของคุณมีการแบ่งหน้าอย่างเหมาะสม:

```java
textFragment.getTextState().setIsAutoTruncated(true);
textFragment.getTextState().setIsWordWrapped(true);
```

## การเพิ่มลายน้ำ

ปกป้องเนื้อหาของคุณด้วยลายน้ำ:

```java
TextFragment watermark = new TextFragment("Confidential");
watermark.getTextState().setFont(FontRepository.findFont("Arial"));
watermark.getTextState().setFontSize(36);
watermark.getTextState().setForegroundColor(com.aspose.pdf.Color.getGray());

page.getParagraphs().add(watermark);
```

## บทสรุป

ในคู่มือนี้ เราได้ศึกษาถึงวิธีการจัดรูปแบบโครงสร้างข้อความใน PDF โดยใช้ Java ด้วยความช่วยเหลือของ Aspose.PDF ตอนนี้คุณสามารถสร้างเอกสาร PDF ที่มีโครงสร้างสวยงามและตอบสนองความต้องการเฉพาะของคุณได้ ทดลองใช้เทคนิคที่ให้มาและปรับปรุงทักษะการสร้าง PDF ของคุณ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนแบบอักษรของข้อความใน PDF ได้อย่างไร?

 หากต้องการเปลี่ยนแบบอักษรของข้อความใน PDF ให้ใช้`setTextState()` วิธีการและระบุแบบอักษรที่ต้องการโดยใช้`setFont()`. ตัวอย่างเช่น:

```java
textFragment.getTextState().setFont(FontRepository.findFont("Arial"));
```

### ฉันสามารถเพิ่มไฮเปอร์ลิงก์ไปยัง PDF โดยใช้ Aspose.PDF สำหรับ Java ได้หรือไม่

 ใช่ คุณสามารถเพิ่มไฮเปอร์ลิงก์ไปยัง PDF ของคุณได้โดยใช้ Aspose.PDF สำหรับ Java ใช้`Hyperlink` คลาสสำหรับสร้างลิงก์และระบุการกระทำ เช่น การเปิด URL

### วิธีการที่แนะนำในการจัดการแบ่งหน้าใน PDF คืออะไร

 ในการจัดการการแบ่งหน้าใน PDF ให้ตั้งค่า`IsAutoTruncated` และ`IsWordWrapped` คุณสมบัติให้`true` ใน`TextState`การดำเนินการนี้จะช่วยให้แน่ใจว่าข้อความถูกตัดทอนและห่ออย่างถูกต้องเพื่อให้พอดีกับขอบเขตของหน้า

### ฉันจะปกป้องเอกสาร PDF ของฉันด้วยลายน้ำได้อย่างไร

คุณสามารถป้องกันเอกสาร PDF ของคุณด้วยลายน้ำได้โดยการเพิ่มข้อความลายน้ำลงใน PDF ปรับแต่งลักษณะของลายน้ำ เช่น ขนาดและสีของแบบอักษร เพื่อให้ได้เอฟเฟกต์ตามต้องการ

### ฉันสามารถหาข้อมูลและเอกสารเพิ่มเติมสำหรับ Aspose.PDF สำหรับ Java ได้ที่ไหน

 คุณสามารถค้นหาเอกสารประกอบที่ครอบคลุมสำหรับ Aspose.PDF สำหรับ Java ได้ที่[ที่นี่](https://reference.aspose.com/pdf/java/).