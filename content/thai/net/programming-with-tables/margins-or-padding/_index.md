---
title: ขอบหรือช่องว่างภายใน
linktitle: ขอบหรือช่องว่างภายใน
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีตั้งค่าระยะขอบหรือช่องว่างภายในตารางโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 140
url: /th/net/programming-with-tables/margins-or-padding/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนของการใช้ Aspose.PDF สำหรับ .NET เพื่อตั้งค่าระยะขอบหรือช่องว่างภายในตาราง เราจะให้คำอธิบายและตัวอย่างโค้ดเพื่อช่วยให้คุณเข้าใจและใช้งานฟังก์ชันนี้ในซอร์สโค้ด C# ของคุณ

## ขั้นตอนที่ 1: การตั้งค่าเอกสารและหน้า
ในการเริ่มต้น คุณต้องตั้งค่าเอกสารและหน้าโดยใช้โค้ดต่อไปนี้:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างอินสแตนซ์ของวัตถุ Document โดยการเรียก Constructor ว่าง
Document doc = new Document();
Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 2: การสร้างตาราง
ต่อไป เราจะสร้างวัตถุตารางโดยใช้คลาส Aspose.Pdf.Table:

```csharp
// สร้างอินสแตนซ์ของวัตถุตาราง
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// เพิ่มตารางลงในคอลเลกชันย่อหน้าของส่วนที่ต้องการ
page.Paragraphs.Add(tab1);
```

## ขั้นตอนที่ 3: การตั้งค่าความกว้างของคอลัมน์และเส้นขอบเซลล์เริ่มต้น
หากต้องการตั้งค่าความกว้างของคอลัมน์และเส้นขอบเซลล์เริ่มต้นของตาราง ให้ใช้โค้ดต่อไปนี้:

```csharp
// กำหนดความกว้างของคอลัมน์ของตาราง
tab1. ColumnWidths = "50 50 50";
// ตั้งค่าเส้นขอบเซลล์เริ่มต้นโดยใช้วัตถุ BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## ขั้นตอนที่ 4: การตั้งค่าเส้นขอบตารางและช่องว่างภายในเซลล์
หากต้องการตั้งค่าเส้นขอบตารางและช่องว่างภายในเซลล์ ให้สร้างวัตถุ MarginInfo และตั้งค่าคุณสมบัติ:

```csharp
// สร้างวัตถุ MarginInfo และตั้งค่าระยะขอบซ้าย ล่าง ขวา และบน
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// ตั้งค่าการเติมเซลล์เริ่มต้นเป็นวัตถุ MarginInfo
tab1. DefaultCellPadding = margin;

// ตั้งค่าเส้นขอบตารางโดยใช้วัตถุ BorderInfo แบบกำหนดเองอื่น
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## ขั้นตอนที่ 5: การเพิ่มแถวและเซลล์
ตอนนี้ เรามาเพิ่มแถวและเซลล์ลงในตารางกัน เราจะสร้างแถวใหม่และเพิ่มเซลล์ลงไป:

```csharp
// สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## ขั้นตอนที่ 6: การเพิ่มข้อความลงในเซลล์
หากต้องการเพิ่มข้อความลงในเซลล์ ให้สร้างวัตถุ TextFragment และเพิ่มลงในเซลล์ที่ต้องการ:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## ขั้นตอนที่ 7: บันทึก PDF
หากต้องการบันทึกเอกสาร PDF ให้ใช้รหัสต่อไปนี้:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// บันทึก PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับ Margins Or Padding โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างอินสแตนซ์วัตถุ Document โดยการเรียก Constructor ว่าง
Document doc = new Document();
Page page = doc.Pages.Add();
// สร้างอินสแตนซ์ของวัตถุตาราง
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// เพิ่มตารางในคอลเลกชันย่อหน้าของส่วนที่ต้องการ
page.Paragraphs.Add(tab1);
// กำหนดความกว้างของคอลัมน์ของตาราง
tab1.ColumnWidths = "50 50 50";
// ตั้งค่าเส้นขอบเซลล์เริ่มต้นโดยใช้วัตถุ BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// ตั้งค่าเส้นขอบตารางโดยใช้วัตถุ BorderInfo ที่กำหนดเองอื่น
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// สร้างวัตถุ MarginInfo และตั้งค่าระยะขอบด้านซ้าย ล่าง ขวา และบน
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
// Row1.Cells.Add("col3 มีข้อความขนาดใหญ่ที่จะวางไว้ภายในเซลล์");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// บันทึก PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีตั้งค่าระยะขอบหรือช่องว่างภายในตารางโดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว ความรู้นี้จะช่วยคุณเพิ่มความสามารถในการจัดรูปแบบเอกสาร และทำให้ตารางของคุณดูน่าดึงดูด

### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถกำหนดระยะขอบหรือช่องว่างภายในที่แตกต่างกันสำหรับแต่ละเซลล์ในตารางได้หรือไม่

ตอบ: ได้ คุณสามารถตั้งค่าระยะขอบหรือช่องว่างภายในที่แตกต่างกันสำหรับแต่ละเซลล์ในตารางได้โดยใช้ Aspose.PDF สำหรับ .NET ในตัวอย่างที่ให้มา เราตั้งค่าช่องว่างภายในเซลล์เริ่มต้นสำหรับทั้งตารางโดยใช้`DefaultCellPadding` คุณสมบัติ. หากต้องการตั้งค่าช่องว่างภายในที่แตกต่างกันสำหรับเซลล์ใดเซลล์หนึ่ง คุณสามารถเข้าถึง`MarginInfo` ของแต่ละเซลล์แยกกันและแก้ไขระยะขอบ

#### ถาม: ฉันจะเปลี่ยนสีเส้นขอบหรือสไตล์ของตารางได้อย่างไร

 ตอบ: หากต้องการเปลี่ยนสีเส้นขอบหรือสไตล์ของตาราง คุณสามารถปรับเปลี่ยนได้`Color` และ`Width` คุณสมบัติของ`BorderInfo` วัตถุ. ในตัวอย่างที่กำหนด เราตั้งค่าสีเส้นขอบเป็นสีดำและใช้ความกว้าง 1F (หนึ่งจุด)`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. คุณสามารถปรับสีและความกว้างได้ตามความต้องการของคุณ

#### ถาม: สามารถเพิ่มส่วนหัวหรือส่วนท้ายลงในตารางได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มส่วนหัวหรือส่วนท้ายลงในตารางได้โดยใช้ Aspose.PDF สำหรับ .NET โดยทั่วไปส่วนหัวและส่วนท้ายจะเป็นแถวที่แยกจากกันซึ่งมีข้อมูลเพิ่มเติม เช่น ป้ายชื่อคอลัมน์ ชื่อตาราง หรือข้อมูลสรุป คุณสามารถสร้างแถวเพิ่มเติม จัดรูปแบบให้แตกต่างออกไป และเพิ่มไว้ด้านบนหรือด้านล่างเนื้อหาตารางได้

#### ถาม: ฉันจะปรับการจัดแนวข้อความภายในเซลล์ตารางได้อย่างไร

 ตอบ: หากต้องการปรับการจัดแนวข้อความภายในเซลล์ตาราง คุณสามารถใช้`HorizontalAlignment` และ`VerticalAlignment` คุณสมบัติของ`TextFragment` วัตถุ. ตัวอย่างเช่น หากต้องการจัดกึ่งกลางข้อความในแนวนอน คุณสามารถตั้งค่าได้`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . ในทำนองเดียวกันคุณสามารถตั้งค่าได้`mytext.VerticalAlignment` เพื่อควบคุมการจัดแนวแนวตั้ง

#### ถาม: ฉันสามารถเพิ่มรูปภาพลงในเซลล์ตารางแทนข้อความได้หรือไม่

 ตอบ: ได้ คุณสามารถเพิ่มรูปภาพลงในเซลล์ตารางได้โดยใช้ Aspose.PDF สำหรับ .NET แทนที่จะสร้าง.`TextFragment` วัตถุคุณสามารถสร้าง`Image` วัตถุ โหลดไฟล์รูปภาพ และเพิ่มลงในเซลล์ที่ต้องการโดยใช้`cell.Paragraphs.Add(image);` วิธี. ซึ่งจะทำให้คุณสามารถแทรกรูปภาพลงในตารางข้างเนื้อหาข้อความได้