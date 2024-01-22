---
title: เพิ่มคอลัมน์การทำซ้ำในเอกสาร PDF
linktitle: เพิ่มคอลัมน์การทำซ้ำในเอกสาร PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มคอลัมน์ที่ซ้ำกันในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 20
url: /th/net/programming-with-tables/add-repeating-column/
---
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีเพิ่มคอลัมน์ซ้ำในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ดใน C# ทีละขั้นตอน ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีสร้างตารางที่มีคอลัมน์ซ้ำในเอกสาร PDF เริ่มกันเลย!

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ขั้นแรก ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา C# ของคุณด้วย Aspose.PDF สำหรับ .NET เพิ่มการอ้างอิงไปยังไลบรารีและนำเข้าเนมสเปซที่จำเป็น

## ขั้นตอนที่ 2: การสร้างเอกสาร PDF
ในขั้นตอนนี้ เราจะสร้างเอกสาร PDF ใหม่

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

เราได้สร้างเอกสาร PDF เปล่าที่เราสามารถเพิ่มเนื้อหาได้

## ขั้นตอนที่ 3: การสร้างตาราง
ในขั้นตอนนี้เราสร้างตารางหลัก (`outerTable`) และตารางที่ซ้อนกัน (`mytable`) ซึ่งจะซ้ำกันในคอลัมน์

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

เราระบุคุณสมบัติของตาราง เช่น ความกว้างของคอลัมน์ และโหมดตัวแบ่งตารางที่ซ้อนกัน

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

ก่อนอื่นเราเพิ่มตารางหลัก (`outerTable`) ไปยังเอกสาร PDF ต่อไปเราจะเพิ่มตารางที่ซ้อนกัน (`mytable` ) เป็นย่อหน้าในเซลล์ในตารางหลัก นอกจากนี้เรายังระบุจำนวนคอลัมน์ที่ซ้ำกันด้วย`mytable` (ในตัวอย่างนี้ 5 คอลัมน์)

## ขั้นตอนที่ 5: การเพิ่มส่วนหัวและบรรทัด
ตอนนี้เราเพิ่มส่วนหัวและแถวลงในตาราง

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
// เพิ่มส่วนหัวอื่นๆ ที่นี่

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // เพิ่มคอลัมน์อื่นๆ ที่นี่
}
```

ก่อนอื่นเราเพิ่มส่วนหัวไปที่แถวแรกของตาราง (`headerRow`). จากนั้นเราก็เพิ่มแถวข้อมูลจากลูป ในตัวอย่างนี้ เราเพิ่มข้อมูล 6 แถว

## ขั้นตอนที่ 6: บันทึกเอกสาร PDF
สุดท้ายเราจะบันทึกเอกสาร PDF ลงในไฟล์ที่ระบุ

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

ตรวจสอบให้แน่ใจว่าได้ระบุไดเร็กทอรีและชื่อไฟล์ที่ถูกต้องเพื่อบันทึกไฟล์ PDF เอาท์พุต

### ตัวอย่างซอร์สโค้ดสำหรับเพิ่มคอลัมน์ซ้ำโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// สร้างเอกสารใหม่
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// สร้างอินสแตนซ์ของตารางด้านนอกที่ใช้พื้นที่ทั้งหน้า
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//สร้างอินสแตนซ์ของวัตถุตารางที่จะซ้อนอยู่ภายใน outerTable ที่จะแยกออกในหน้าเดียวกัน
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// เพิ่มตารางด้านนอกลงในย่อหน้าของหน้า
// เพิ่ม mytable ให้กับouterTable
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
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเพิ่มคอลัมน์ที่ซ้ำกันในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้คำแนะนำทีละขั้นตอนนี้เพื่อสร้างตารางที่มีคอลัมน์ซ้ำในโปรเจ็กต์ C# ของคุณเอง

### คำถามที่พบบ่อยสำหรับการเพิ่มคอลัมน์ซ้ำในเอกสาร PDF

#### ถาม: ฉันสามารถปรับแต่งจำนวนคอลัมน์ที่ซ้ำกันในตารางที่ซ้อนกันได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งจำนวนคอลัมน์ที่ซ้ำกันในตารางที่ซ้อนกันได้ ในตัวอย่างที่ให้มา เราตั้งค่า`mytable.RepeatingColumnsCount = 5;`ซึ่งหมายความว่าจะมี 5 คอลัมน์ที่ซ้ำกัน คุณสามารถเปลี่ยนค่านี้เป็นตัวเลขที่ต้องการได้

#### ถาม: เป็นไปได้ไหมที่จะเพิ่มแถวลงในตารางที่ซ้อนกันแบบไดนามิก

ตอบ: ได้ คุณสามารถเพิ่มแถวแบบไดนามิกลงในตารางที่ซ้อนกันได้ในลักษณะเดียวกับที่แสดงในบทช่วยสอน คุณสามารถใช้ลูปหรือตรรกะอื่นๆ เพื่อเพิ่มแถวตามข้อมูลของคุณได้

#### ถาม: ฉันสามารถใช้สไตล์และการจัดรูปแบบกับตารางและเซลล์ได้หรือไม่

ตอบ: ได้ คุณสามารถใช้สไตล์และการจัดรูปแบบกับตารางและเซลล์โดยใช้ Aspose.PDF สำหรับ .NET ไลบรารีมีคุณสมบัติและวิธีการต่างๆ เพื่อปรับแต่งลักษณะที่ปรากฏของตารางและเนื้อหา

#### ถาม: Aspose.PDF สำหรับ .NET เข้ากันได้กับ .NET Core หรือไม่

ตอบ: ได้ Aspose.PDF สำหรับ .NET เข้ากันได้กับ .NET Core คุณสามารถใช้ได้ทั้งในแอปพลิเคชัน .NET Framework และ .NET Core

#### ถาม: ฉันสามารถใช้วิธีนี้เพื่อเพิ่มคอลัมน์ที่ซ้ำกันในเอกสาร PDF ที่มีอยู่ได้หรือไม่

ตอบ: ได้ คุณสามารถใช้วิธีนี้เพื่อเพิ่มคอลัมน์ที่ซ้ำกันในเอกสาร PDF ที่มีอยู่ได้ เพียงโหลดเอกสารที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET แล้วทำตามขั้นตอนเดียวกันเพื่อสร้างและเพิ่มคอลัมน์ที่ซ้ำกัน