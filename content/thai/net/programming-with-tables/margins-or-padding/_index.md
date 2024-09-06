---
title: ระยะขอบหรือการเติม
linktitle: ระยะขอบหรือการเติม
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการตั้งค่าระยะขอบหรือการเว้นระยะในตารางโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 140
url: /th/net/programming-with-tables/margins-or-padding/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการใช้ Aspose.PDF สำหรับ .NET เพื่อตั้งค่าระยะขอบหรือระยะห่างในตาราง เราจะให้คำอธิบายและตัวอย่างโค้ดเพื่อช่วยให้คุณเข้าใจและนำฟังก์ชันนี้ไปใช้งานในโค้ดต้นฉบับ C# ของคุณได้

## ขั้นตอนที่ 1: การตั้งค่าเอกสารและหน้า
ในการเริ่มต้น คุณต้องตั้งค่าเอกสารและหน้าโดยใช้โค้ดต่อไปนี้:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างอินสแตนซ์ของวัตถุเอกสารโดยเรียกคอนสตรัคเตอร์ที่ว่างเปล่า
Document doc = new Document();
Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 2: การสร้างตาราง
ต่อไปเราจะสร้างวัตถุตารางโดยใช้คลาส Aspose.Pdf.Table:

```csharp
// สร้างอินสแตนซ์ของวัตถุตาราง
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// เพิ่มตารางลงในคอลเล็กชั่นย่อหน้าของส่วนที่ต้องการ
page.Paragraphs.Add(tab1);
```

## ขั้นตอนที่ 3: การตั้งค่าความกว้างของคอลัมน์และเส้นขอบเซลล์เริ่มต้น
หากต้องการตั้งค่าความกว้างของคอลัมน์และเส้นขอบเซลล์เริ่มต้นของตาราง ให้ใช้โค้ดดังต่อไปนี้:

```csharp
// กำหนดความกว้างของคอลัมน์ของตาราง
tab1. ColumnWidths = "50 50 50";
// ตั้งค่าเส้นขอบเซลล์เริ่มต้นโดยใช้วัตถุ BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## ขั้นตอนที่ 4: ตั้งค่าเส้นขอบตารางและการเติมเซลล์
ในการตั้งค่าเส้นขอบตารางและการเติมเซลล์ ให้สร้างอ็อบเจ็กต์ MarginInfo และตั้งค่าคุณสมบัติ:

```csharp
// สร้างวัตถุ MarginInfo และตั้งค่าระยะขอบซ้าย ล่าง ขวา และบน
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// ตั้งค่าการเติมเซลล์เริ่มต้นเป็นวัตถุ MarginInfo
tab1. DefaultCellPadding = margin;

// กำหนดเส้นขอบตารางโดยใช้ BorderInfo วัตถุที่กำหนดเองอื่น
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## ขั้นตอนที่ 5: การเพิ่มแถวและเซลล์
ตอนนี้เรามาเพิ่มแถวและเซลล์ลงในตารางกัน เราจะสร้างแถวใหม่และเพิ่มเซลล์ลงไป:

```csharp
// สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## ขั้นตอนที่ 6: การเพิ่มข้อความลงในเซลล์
หากต้องการเพิ่มข้อความลงในเซลล์ ให้สร้างอ็อบเจ็กต์ TextFragment และเพิ่มลงในเซลล์ที่ต้องการ:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## ขั้นตอนที่ 7: บันทึก PDF
หากต้องการบันทึกเอกสาร PDF ให้ใช้รหัสดังต่อไปนี้:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// บันทึกไฟล์ PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับ Margins หรือ Padding โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างวัตถุเอกสารโดยเรียกใช้คอนสตรัคเตอร์ที่ว่างเปล่า
Document doc = new Document();
Page page = doc.Pages.Add();
// สร้างอินสแตนซ์ของวัตถุตาราง
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// เพิ่มตารางในคอลเลกชันย่อหน้าของส่วนที่ต้องการ
page.Paragraphs.Add(tab1);
// ตั้งค่าด้วยความกว้างของคอลัมน์ของตาราง
tab1.ColumnWidths = "50 50 50";
// ตั้งค่าเส้นขอบเซลล์เริ่มต้นโดยใช้ BorderInfo object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// กำหนดเส้นขอบตารางโดยใช้ BorderInfo วัตถุที่กำหนดเองอื่น
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// สร้างวัตถุ MarginInfo และตั้งค่าระยะขอบซ้าย ล่าง ขวา และบน
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// ตั้งค่าการเติมเซลล์เริ่มต้นเป็นวัตถุ MarginInfo
tab1.DefaultCellPadding = margin;
// สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 ที่มีสตริงข้อความขนาดใหญ่ที่จะวางไว้ภายในเซลล์");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// บันทึกไฟล์ PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## บทสรุป
ขอแสดงความยินดี! คุณได้เรียนรู้วิธีตั้งค่าระยะขอบหรือระยะห่างในตารางโดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว ความรู้เหล่านี้จะช่วยให้คุณปรับปรุงความสามารถในการจัดรูปแบบเอกสารและทำให้ตารางของคุณดูน่าสนใจยิ่งขึ้น

### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถตั้งค่าระยะขอบหรือระยะห่างที่แตกต่างกันสำหรับแต่ละเซลล์ในตารางได้หรือไม่

A: ใช่ คุณสามารถตั้งค่าระยะขอบหรือการเว้นระยะที่แตกต่างกันสำหรับเซลล์แต่ละเซลล์ในตารางได้โดยใช้ Aspose.PDF สำหรับ .NET ในตัวอย่างที่ให้มา เราตั้งค่าการเว้นระยะเซลล์เริ่มต้นสำหรับตารางทั้งหมดโดยใช้`DefaultCellPadding` คุณสมบัติ หากต้องการตั้งค่าการเติมที่แตกต่างกันสำหรับเซลล์เฉพาะ คุณสามารถเข้าถึง`MarginInfo` ของแต่ละเซลล์แยกกันและแก้ไขระยะขอบของเซลล์เหล่านั้น

#### ถาม: ฉันจะเปลี่ยนสีขอบหรือรูปแบบของตารางได้อย่างไร

 A: หากต้องการเปลี่ยนสีขอบหรือรูปแบบของตาราง คุณสามารถแก้ไข`Color` และ`Width` คุณสมบัติของ`BorderInfo` วัตถุ ในตัวอย่างที่กำหนด เรากำหนดสีเส้นขอบเป็นสีดำและความกว้าง 1F (หนึ่งจุด) โดยใช้`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. คุณสามารถปรับเปลี่ยนสีและความกว้างได้ตามความต้องการ

#### ถาม: สามารถเพิ่มส่วนหัวหรือส่วนท้ายลงในตารางได้หรือไม่

A: ใช่ คุณสามารถเพิ่มส่วนหัวหรือส่วนท้ายของตารางได้โดยใช้ Aspose.PDF สำหรับ .NET ส่วนหัวและส่วนท้ายของตารางโดยทั่วไปจะเป็นแถวแยกกันที่มีข้อมูลเพิ่มเติม เช่น ป้ายชื่อคอลัมน์ ชื่อตาราง หรือข้อมูลสรุป คุณสามารถสร้างแถวเพิ่มเติม จัดรูปแบบให้แตกต่างกัน และเพิ่มแถวเหล่านี้ไว้ด้านบนหรือด้านล่างของเนื้อหาตารางได้

#### ถาม: ฉันจะปรับการจัดตำแหน่งข้อความภายในเซลล์ตารางได้อย่างไร

 ก: หากต้องการปรับการจัดตำแหน่งข้อความภายในเซลล์ตาราง คุณสามารถใช้`HorizontalAlignment` และ`VerticalAlignment` คุณสมบัติของ`TextFragment` วัตถุ ตัวอย่างเช่น หากต้องการจัดข้อความให้ตรงกลางในแนวนอน คุณสามารถตั้งค่า`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . ในทำนองเดียวกันคุณสามารถตั้งค่า`mytext.VerticalAlignment` เพื่อควบคุมการจัดวางแนวตั้ง

#### ถาม: ฉันสามารถเพิ่มรูปภาพลงในเซลล์ตารางแทนข้อความได้หรือไม่

 A: ใช่ คุณสามารถเพิ่มรูปภาพลงในเซลล์ตารางได้โดยใช้ Aspose.PDF สำหรับ .NET แทนที่จะสร้าง`TextFragment` วัตถุ คุณสามารถสร้างได้`Image` วัตถุ โหลดไฟล์ภาพและเพิ่มลงในเซลล์ที่ต้องการโดยใช้`cell.Paragraphs.Add(image);` วิธีการนี้ทำให้คุณสามารถแทรกภาพลงในตารางควบคู่ไปกับเนื้อหาข้อความได้