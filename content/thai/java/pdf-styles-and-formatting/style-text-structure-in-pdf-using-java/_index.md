---
title: โครงสร้างข้อความสไตล์ในรูปแบบ PDF โดยใช้ Java
linktitle: โครงสร้างข้อความสไตล์ในรูปแบบ PDF โดยใช้ Java
second_title: Aspose.PDF Java PDF การประมวลผล API
description: เรียนรู้วิธีจัดรูปแบบโครงสร้างข้อความใน PDF โดยใช้ Java พร้อมคำแนะนำทีละขั้นตอนของเรา ปรับแต่งแบบอักษร สี ไฮเปอร์ลิงก์ และอื่นๆ อีกมากมายสำหรับเอกสารที่ดูเป็นมืออาชีพ
type: docs
weight: 11
url: /th/java/pdf-styles-and-formatting/style-text-structure-in-pdf-using-java/
---

## การแนะนำ

PDF กลายเป็นรูปแบบมาตรฐานสำหรับการแชร์เอกสาร รายงาน และเนื้อหาประเภทต่างๆ เมื่อทำงานกับ PDF ใน Java ไม่เพียงแต่จะต้องเติมข้อมูลลงในไฟล์เท่านั้น แต่ยังต้องจัดรูปแบบข้อความเพื่อให้มีรูปลักษณ์ที่สวยงามอีกด้วย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) แล้ว
- Aspose.PDF สำหรับไลบรารี Java ที่ดาวน์โหลดและตั้งค่า

## การตั้งค่าสภาพแวดล้อม

หากต้องการเริ่มจัดรูปแบบข้อความใน PDF โดยใช้ Java คุณต้องตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ ทำตามขั้นตอนเหล่านี้:

1.  ดาวน์โหลดไลบรารี Aspose.PDF สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/pdf/java/).

2. รวมไลบรารีในโครงการ Java ของคุณ

3. นำเข้าคลาสที่จำเป็นจาก Aspose.PDF ในโค้ดของคุณ

## การเพิ่มข้อความลงใน PDF

ตอนนี้ เรามาเริ่มต้นด้วยการเพิ่มข้อความลงในเอกสาร PDF นี่เป็นตัวอย่างง่ายๆ:

```java
// สร้างเอกสาร PDF ใหม่
com.aspose.pdf.Document pdfDocument = new com.aspose.pdf.Document();

// เพิ่มหน้าลงในเอกสาร
pdfDocument.getPages().add();

// สร้างวัตถุ TextFragment
com.aspose.pdf.TextFragment textFragment = new com.aspose.pdf.TextFragment("Hello, PDF!");

// เพิ่ม TextFragment ลงในเพจ
pdfDocument.getPages().get_Item(1).getParagraphs().add(textFragment);

// บันทึกเอกสาร
pdfDocument.save("output.pdf");
```

รหัสนี้จะสร้างเอกสาร PDF เพิ่มหน้า และแทรกข้อความ "Hello, PDF!" ลงบนหน้า

## การจัดรูปแบบตัวอักษร

คุณสามารถปรับแต่งแบบอักษรของข้อความของคุณได้ ต่อไปนี้เป็นวิธีเปลี่ยนตระกูลแบบอักษรและขนาด:

```java
textFragment.getTextState().setFont(FontRepository.findFont("Arial"));
textFragment.getTextState().setFontSize(12);
```

## ขนาดข้อความและสี

การปรับขนาดและสีของข้อความทำได้ง่าย:

```java
textFragment.getTextState().setFontSize(16);
textFragment.getTextState().setForegroundColor(com.aspose.pdf.Color.getBlue());
```

## การจัดตำแหน่งข้อความ

ควบคุมการจัดแนวข้อความภายใน PDF ของคุณ:

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

## การเพิ่มรายการสัญลักษณ์แสดงหัวข้อย่อย

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

เพิ่มไฮเปอร์ลิงก์ไปยัง PDF ของคุณสำหรับเนื้อหาเชิงโต้ตอบ:

```java
TextFragment linkText = new TextFragment("Visit our website");
linkText.getTextState().setFont(FontRepository.findFont("Arial"));
linkText.getTextState().setFontSize(12);

Hyperlink link = new Hyperlink(linkText);
link.setAction(new GoToURIAction("https://www.example.com"));

page.getParagraphs().add(link);
```

## การแปลงข้อความ

แปลงข้อความตามต้องการ:

```java
textFragment.getTextState().setTextRise(5); // ยกข้อความ
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

## การจัดการตัวแบ่งหน้า

ตรวจสอบให้แน่ใจว่าตัวแบ่งหน้าที่เหมาะสมสำหรับเนื้อหาของคุณ:

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

ในคู่มือนี้ เราได้สำรวจวิธีจัดรูปแบบโครงสร้างข้อความใน PDF โดยใช้ Java ด้วยความช่วยเหลือของ Aspose.PDF ตอนนี้คุณสามารถสร้างเอกสาร PDF ที่ดึงดูดสายตาและมีโครงสร้างที่ดีซึ่งตรงกับความต้องการเฉพาะของคุณได้แล้ว ทดลองใช้เทคนิคที่มีให้และพัฒนาทักษะการสร้าง PDF ของคุณ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนแบบอักษรของข้อความใน PDF ได้อย่างไร

 หากต้องการเปลี่ยนแบบอักษรของข้อความใน PDF ให้ใช้`setTextState()` และระบุแบบอักษรที่ต้องการโดยใช้`setFont()`. ตัวอย่างเช่น:

```java
textFragment.getTextState().setFont(FontRepository.findFont("Arial"));
```

### ฉันสามารถเพิ่มไฮเปอร์ลิงก์ไปยัง PDF ของฉันโดยใช้ Aspose.PDF สำหรับ Java ได้หรือไม่

 ใช่ คุณสามารถเพิ่มไฮเปอร์ลิงก์ไปยัง PDF ของคุณโดยใช้ Aspose.PDF สำหรับ Java ใช้`Hyperlink` คลาสเพื่อสร้างลิงก์และระบุการดำเนินการ เช่น การเปิด URL

### วิธีที่แนะนำในการจัดการตัวแบ่งหน้าใน PDF คืออะไร

 ในการจัดการกับตัวแบ่งหน้าใน PDF ให้ตั้งค่า`IsAutoTruncated` และ`IsWordWrapped` คุณสมบัติที่จะ`true` ใน`TextState`. เพื่อให้แน่ใจว่าข้อความถูกตัดและล้อมอย่างเหมาะสมเพื่อให้พอดีกับขอบเขตของหน้า

### ฉันจะป้องกันเอกสาร PDF ของฉันด้วยลายน้ำได้อย่างไร

คุณสามารถปกป้องเอกสาร PDF ของคุณด้วยลายน้ำได้โดยการเพิ่มส่วนข้อความลายน้ำลงใน PDF ปรับแต่งลักษณะของลายน้ำ เช่น ขนาดตัวอักษรและสี เพื่อให้ได้เอฟเฟกต์ที่ต้องการ

### ฉันจะหาข้อมูลและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.PDF สำหรับ Java ได้ที่ไหน

 คุณสามารถค้นหาเอกสารที่ครอบคลุมสำหรับ Aspose.PDF สำหรับ Java ได้ที่[ที่นี่](https://reference.aspose.com/pdf/java/).