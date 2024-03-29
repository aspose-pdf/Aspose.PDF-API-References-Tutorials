---
title: รูปภาพและหมายเลขหน้าในส่วนท้ายของส่วนหัวแบบอินไลน์
linktitle: รูปภาพและหมายเลขหน้าในส่วนท้ายของส่วนหัวแบบอินไลน์
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มรูปภาพและหมายเลขหน้าในส่วนหัวและส่วนท้ายโดยใช้ย่อหน้าแบบอินไลน์ด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 120
url: /th/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณทีละขั้นตอนเกี่ยวกับวิธีเพิ่มรูปภาพและหมายเลขหน้าในส่วนหัวและส่วนท้ายของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะใช้ซอร์สโค้ด C# ที่ให้มาเพื่อสร้างหน้า ตั้งค่าส่วนหัวและส่วนท้าย เพิ่มรูปภาพและข้อความโดยใช้ย่อหน้าแบบอินไลน์ในส่วนหัวของเอกสาร PDF

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไว้
- ไลบรารี Aspose.PDF สำหรับ .NET ดาวน์โหลดและอ้างอิงในโครงการของคุณ

## ขั้นตอนที่ 2: การสร้างเอกสาร PDF และหน้า

ขั้นตอนแรกคือการสร้างออบเจ็กต์เอกสารใหม่และหน้าในเอกสาร PDF มีวิธีดังนี้:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างวัตถุเอกสารใหม่
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// สร้างหน้าในเอกสาร
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

โค้ดด้านบนจะสร้างออบเจ็กต์เอกสารใหม่และหน้าว่างในเอกสาร PDF

## ขั้นตอนที่ 3: การเพิ่มส่วนหัวด้วยรูปภาพและข้อความในบรรทัด

เมื่อสร้างเพจแล้ว เราก็สามารถเพิ่มส่วนหัวที่มีรูปภาพและข้อความโดยใช้ย่อหน้าแบบอินไลน์ได้ มีวิธีดังนี้:

```csharp
// สร้างส่วนหัว
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// ตั้งค่าส่วนหัวของหน้า
page. Header = header;

// สร้างวัตถุ TextFragment สำหรับข้อความอินไลน์ข้อความแรก
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// ระบุสีข้อความ
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// สร้างวัตถุรูปภาพสำหรับรูปภาพ
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// กำหนดเส้นทางภาพ
image1.File = dataDir + "aspose-logo.jpg";

// กำหนดขนาดของภาพ
image1.FixWidth = 50;
image1.FixHeight = 20;

// ระบุว่าข้อความอินไลน์แรกเป็นรูปภาพ
image1.IsInLineParagraph = true;

// สร้างข้อความอินไลน์ที่สอง
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// เพิ่มรายการลงในส่วนหัว
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

โค้ดด้านบนสร้างส่วนหัว ตั้งค่าส่วนหัวของหน้าด้วยส่วนนี้ เพิ่ม TextFragment พร้อมข้อความในบรรทัดและออบเจ็กต์รูปภาพในบรรทัด

## ขั้นตอนที่ 4: บันทึกเอกสาร PDF ที่แก้ไข

เมื่อเพิ่มส่วนหัวพร้อมรูปภาพและข้อความในบรรทัดแล้ว เราก็สามารถบันทึกเอกสาร PDF ที่แก้ไขแล้วได้ มีวิธีดังนี้:

```csharp
// บันทึกเอกสาร PDF ที่แก้ไข
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

โค้ดด้านบนจะบันทึกเอกสาร PDF ที่แก้ไขแล้วไปยังไดเร็กทอรีที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับรูปภาพและหมายเลขหน้าในส่วนหัวส่วนท้ายแบบอินไลน์โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างอินสแตนซ์ของวัตถุ Document โดยการเรียก Constructor ว่าง
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// สร้างหน้าในวัตถุ Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();

// สร้างส่วนหัวของเอกสาร
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// ตั้งค่าส่วนหัวของไฟล์ PDF
page.Header = header;

// สร้างวัตถุข้อความ
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// ระบุสี
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// สร้างวัตถุรูปภาพในส่วน
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// กำหนดเส้นทางของไฟล์รูปภาพ
image1.File = dataDir + "aspose-logo.jpg";

// ตั้งค่าข้อมูลความกว้างของภาพ
image1.FixWidth = 50;
image1.FixHeight = 20;

// ระบุว่า InlineParagraph ของ seg1 เป็นรูปภาพ
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// บันทึก PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีเพิ่มรูปภาพและหมายเลขหน้าในส่วนหัวและส่วนท้ายของเอกสาร PDF โดยใช้ย่อหน้าแบบอินไลน์ด้วย Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถปรับแต่งส่วนหัวและส่วนท้ายของเอกสาร PDF ของคุณได้อย่างยืดหยุ่น

### คำถามที่พบบ่อย

#### ถาม: ข้อดีของการใช้ย่อหน้าแบบอินไลน์ในการเพิ่มรูปภาพและข้อความที่ส่วนหัวของเอกสาร PDF คืออะไร

ตอบ: การใช้ย่อหน้าแบบอินไลน์ช่วยให้คุณสามารถรวมรูปภาพและข้อความภายในย่อหน้าเดียวกันได้อย่างราบรื่น โดยให้การควบคุมตำแหน่งและการจัดรูปแบบที่แม่นยำ วิธีการนี้มีประโยชน์อย่างยิ่งสำหรับการสร้างส่วนหัวที่กำหนดเองด้วยองค์ประกอบภาพ

#### ถาม: ซอร์สโค้ด C# ที่ให้มาบรรลุย่อหน้าแบบอินไลน์สำหรับส่วนหัวในเอกสาร PDF ได้อย่างไร

ตอบ: รหัสที่ให้มาจะสาธิตวิธีการสร้างเอกสาร PDF เพิ่มหน้า และปรับแต่งส่วนหัวโดยใช้ย่อหน้าแบบอินไลน์ โดยจะเพิ่ม TextFragment พร้อมด้วยข้อความในบรรทัด รูปภาพในบรรทัด และ TextFragment ในบรรทัดอื่นๆ

#### ถาม: ฉันจะระบุสีของข้อความอินไลน์ในส่วนหัวได้อย่างไร

 ตอบ: สีของข้อความอินไลน์ถูกกำหนดโดยใช้`ForegroundColor` ทรัพย์สินของ`TextState` ของ`TextFragment` วัตถุ.

#### ถาม: ฉันสามารถปรับขนาดของรูปภาพอินไลน์ในส่วนหัวได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับขนาดของรูปภาพในบรรทัดได้โดยใช้`FixWidth` และ`FixHeight` คุณสมบัติของ`Image` วัตถุ. ซึ่งช่วยให้คุณควบคุมความกว้างและความสูงของรูปภาพภายในส่วนหัวได้

#### ถาม: ฉันสามารถใส่องค์ประกอบอินไลน์เพิ่มเติม เช่น ไฮเปอร์ลิงก์หรือรูปแบบตัวอักษรอื่น ๆ ไว้ในส่วนหัวได้หรือไม่

 ตอบ: ได้ คุณสามารถรวมองค์ประกอบอินไลน์เพิ่มเติมในส่วนหัวได้โดยการสร้างเพิ่มเติม`TextFragment` หรือ`Image` วัตถุที่มีคุณสมบัติที่ต้องการ ซึ่งจะทำให้คุณสามารถปรับแต่งส่วนหัวเพิ่มเติมได้ รวมถึงไฮเปอร์ลิงก์ รูปแบบตัวอักษรที่แตกต่างกัน หรือองค์ประกอบภาพอื่นๆ

#### ถาม: ฉันจะมั่นใจได้อย่างไรว่ารูปภาพและข้อความในบรรทัดยังคงสอดคล้องและจัดรูปแบบอย่างเหมาะสมในอุปกรณ์และโปรแกรมดูต่างๆ

ตอบ: Aspose.PDF สำหรับ .NET ช่วยให้มั่นใจได้ว่ารูปภาพและข้อความในบรรทัดได้รับการจัดตำแหน่งและจัดรูปแบบอย่างเหมาะสม ส่งผลให้มีรูปลักษณ์ที่สอดคล้องกันในอุปกรณ์ต่างๆ และโปรแกรมดู PDF

#### ถาม: ฉันสามารถใช้ย่อหน้าแบบอินไลน์กับส่วนท้ายกระดาษด้วยได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้เทคนิคเดียวกันนี้ในการใช้ย่อหน้าแบบอินไลน์กับส่วนท้ายกระดาษได้โดยการสร้าง`Footer` วัตถุและเพิ่มองค์ประกอบแบบอินไลน์ เช่น ข้อความและรูปภาพลงไป

#### ถาม: เป็นไปได้ไหมที่จะรวมย่อหน้าแบบอินไลน์เข้ากับวิธีปรับแต่งส่วนหัวหรือส่วนท้ายอื่นๆ

ตอบ: ได้ คุณสามารถรวมย่อหน้าแบบอินไลน์เข้ากับวิธีการปรับแต่งส่วนหัวหรือส่วนท้ายอื่นๆ ที่ให้บริการโดย Aspose.PDF สำหรับ .NET เพื่อสร้างการออกแบบส่วนหัวหรือส่วนท้ายที่ซับซ้อนและปรับแต่งได้มากขึ้น

#### ถาม: ฉันสามารถลบหรือล้างองค์ประกอบอินไลน์ออกจากส่วนหัวได้หรือไม่ หากจำเป็น

 ตอบ: ได้ คุณสามารถลบหรือล้างองค์ประกอบอินไลน์ได้โดยการแก้ไขเนื้อหาของ`HeaderFooter` คัดค้านและลบย่อหน้าอินไลน์ตามลำดับ

#### ถาม: ฉันจะใช้ย่อหน้าแบบอินไลน์กับหน้าเฉพาะของเอกสาร PDF ได้อย่างไร

 ตอบ: หากต้องการใช้ย่อหน้าแบบอินไลน์กับหน้าใดหน้าหนึ่ง คุณสามารถสร้างแยกต่างหากได้`HeaderFooter` ออบเจ็กต์สำหรับแต่ละหน้าและกำหนดโดยใช้`Header` ทรัพย์สินของบุคคลนั้น ๆ`Aspose.Pdf.Page` วัตถุ