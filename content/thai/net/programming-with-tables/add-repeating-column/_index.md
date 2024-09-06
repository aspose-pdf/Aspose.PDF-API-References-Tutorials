---
title: เพิ่มคอลัมน์ที่ซ้ำกันในเอกสาร PDF
linktitle: เพิ่มคอลัมน์ที่ซ้ำกันในเอกสาร PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการเพิ่มคอลัมน์ที่ทำซ้ำในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 20
url: /th/net/programming-with-tables/add-repeating-column/
---
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีเพิ่มคอลัมน์ซ้ำในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายโค้ดต้นฉบับใน C# ทีละขั้นตอน เมื่อจบบทช่วยสอนนี้ คุณจะทราบวิธีสร้างตารางที่มีคอลัมน์ซ้ำในเอกสาร PDF มาเริ่มกันเลย!

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ขั้นแรก ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา C# ด้วย Aspose.PDF สำหรับ .NET แล้ว เพิ่มการอ้างอิงไปยังไลบรารีและนำเข้าเนมสเปซที่จำเป็น

## ขั้นตอนที่ 2: การสร้างเอกสาร PDF
ในขั้นตอนนี้เราจะสร้างเอกสาร PDF ใหม่

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

เราได้สร้างเอกสาร PDF เปล่าขึ้นมาซึ่งเราจะเพิ่มเนื้อหาได้

## ขั้นตอนที่ 3: การสร้างตาราง
ในขั้นตอนนี้เราจะสร้างตารางหลัก (`outerTable`) และตารางซ้อนกัน (`mytable`) ซึ่งจะซ้ำกันในคอลัมน์

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

เราได้ระบุคุณสมบัติของตารางเช่นความกว้างของคอลัมน์และโหมดการแบ่งตารางแบบซ้อน

## ขั้นตอนที่ 4: การเพิ่มตารางลงในเอกสาร
ตอนนี้เราเพิ่มตารางที่สร้างขึ้นลงในเอกสาร PDF

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

ก่อนอื่นเราจะเพิ่มตารางหลัก (`outerTable`) ลงในเอกสาร PDF ต่อไปเราจะเพิ่มตารางซ้อน (`mytable` ) เป็นย่อหน้าในเซลล์ในตารางหลัก เรายังระบุจำนวนคอลัมน์ที่ซ้ำกันสำหรับ`mytable` (ในตัวอย่างนี้ 5 คอลัมน์)

## ขั้นตอนที่ 5: การเพิ่มส่วนหัวและบรรทัด
ตอนนี้เราเพิ่มส่วนหัวและแถวลงในตาราง

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// -
// เพิ่มหัวข้ออื่น ๆ ที่นี่

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // -
     // เพิ่มคอลัมน์อื่น ๆ ที่นี่
}
```

ก่อนอื่นเราจะเพิ่มส่วนหัวลงในแถวแรกของตาราง (`headerRow`) จากนั้นเราจะเพิ่มแถวข้อมูลจากลูป ในตัวอย่างนี้ เราจะเพิ่มข้อมูล 6 แถว

## ขั้นตอนที่ 6: บันทึกเอกสาร PDF
สุดท้ายเราบันทึกเอกสาร PDF ลงในไฟล์ที่ระบุ

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

ตรวจสอบให้แน่ใจว่าคุณระบุไดเร็กทอรีและชื่อไฟล์ที่ถูกต้องเพื่อบันทึกไฟล์ PDF ผลลัพธ์

### ตัวอย่างโค้ดต้นฉบับสำหรับการเพิ่มคอลัมน์ที่ซ้ำกันโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// สร้างเอกสารใหม่
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// สร้างตัวอย่างตารางภายนอกที่ใช้พื้นที่ทั้งหน้า
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//สร้างอินสแตนซ์ของวัตถุตารางที่จะซ้อนอยู่ภายใน outerTable ที่จะแยกออกภายในหน้าเดียวกัน
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// เพิ่ม outerTable ลงในย่อหน้าของหน้า
// เพิ่ม mytable ลงใน outerTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// เพิ่มแถวส่วนหัว
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการเพิ่มคอลัมน์ที่ซ้ำกันในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้คู่มือทีละขั้นตอนนี้เพื่อสร้างตารางที่มีคอลัมน์ที่ซ้ำกันในโปรเจ็กต์ C# ของคุณเองได้

### คำถามที่พบบ่อยสำหรับการเพิ่มคอลัมน์ที่ซ้ำกันในเอกสาร PDF

#### ถาม: ฉันสามารถกำหนดจำนวนคอลัมน์ที่ทำซ้ำในตารางที่ซ้อนกันได้หรือไม่

 A: ใช่ คุณสามารถกำหนดจำนวนคอลัมน์ที่ซ้ำกันในตารางที่ซ้อนกันได้ ในตัวอย่างที่ให้มา เราจะตั้งค่า`mytable.RepeatingColumnsCount = 5;`ซึ่งหมายความว่าจะมีคอลัมน์ที่ซ้ำกัน 5 คอลัมน์ คุณสามารถเปลี่ยนค่านี้เป็นตัวเลขที่ต้องการได้

#### ถาม: เป็นไปได้ไหมที่จะเพิ่มแถวเพิ่มเติมลงในตารางที่ซ้อนกันแบบไดนามิก?

A: ใช่ คุณสามารถเพิ่มแถวเพิ่มเติมในตารางแบบซ้อนได้แบบไดนามิกในลักษณะเดียวกับที่แสดงในบทช่วยสอน คุณสามารถใช้ลูปหรือตรรกะอื่นๆ เพื่อเพิ่มแถวตามข้อมูลของคุณได้

#### ถาม: ฉันสามารถนำสไตล์และการจัดรูปแบบไปใช้กับตารางและเซลล์ได้หรือไม่

A: ใช่ คุณสามารถใช้รูปแบบและการจัดรูปแบบกับตารางและเซลล์ได้โดยใช้ Aspose.PDF สำหรับ .NET ไลบรารีนี้มีคุณสมบัติและวิธีการต่างๆ เพื่อปรับแต่งลักษณะของตารางและเนื้อหา

#### ถาม: Aspose.PDF สำหรับ .NET เข้ากันได้กับ .NET Core หรือไม่

A: ใช่ Aspose.PDF สำหรับ .NET เข้ากันได้กับ .NET Core คุณสามารถใช้ได้ในแอปพลิเคชัน .NET Framework และ .NET Core

#### ถาม: ฉันสามารถใช้แนวทางนี้เพื่อเพิ่มคอลัมน์ที่ทำซ้ำในเอกสาร PDF ที่มีอยู่ได้หรือไม่

A: ใช่ คุณสามารถใช้แนวทางนี้เพื่อเพิ่มคอลัมน์ที่ซ้ำกันในเอกสาร PDF ที่มีอยู่ได้ เพียงโหลดเอกสารที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET และทำตามขั้นตอนเดียวกันเพื่อสร้างและเพิ่มคอลัมน์ที่ซ้ำกัน