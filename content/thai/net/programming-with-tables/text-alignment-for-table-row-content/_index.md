---
title: การจัดแนวข้อความสำหรับเนื้อหาแถวตาราง
linktitle: การจัดแนวข้อความสำหรับเนื้อหาแถวตาราง
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีจัดแนวเนื้อหาแถวในตาราง PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 210
url: /th/net/programming-with-tables/text-alignment-for-table-row-content/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณทีละขั้นตอนในการจัดแนวเนื้อหาของแถวในตารางของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและแสดงวิธีใช้งาน

## ขั้นตอนที่ 1: การสร้างเอกสาร PDF
ขั้นแรก เราจะสร้างเอกสาร PDF:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## ขั้นตอนที่ 2: การเริ่มต้นตาราง
ต่อไปเราจะเริ่มต้นตาราง:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## ขั้นตอนที่ 3: การตั้งค่าสีเส้นขอบตาราง
เราจะกำหนดค่าสีของเส้นขอบตาราง:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## ขั้นตอนที่ 4: การกำหนดค่าเส้นขอบเซลล์ของตาราง
เราจะกำหนดค่าเส้นขอบเซลล์ของตาราง:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## ขั้นตอนที่ 5: วนซ้ำเพื่อเพิ่ม 10 แถวลงในตาราง
ตอนนี้เราจะใช้การวนซ้ำเพื่อเพิ่ม 10 แถวลงในตาราง:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## ขั้นตอนที่ 6: การกำหนดค่าการจัดตำแหน่งเส้นแนวตั้ง
เราจะกำหนดค่าการจัดตำแหน่งแนวตั้งของแถวของตาราง:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## ขั้นตอนที่ 7: การเพิ่มเนื้อหาลงในเซลล์แถว
เราจะเพิ่มเนื้อหาลงในเซลล์แถว:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## ขั้นตอนที่ 8: การเพิ่มตารางลงในหน้าเอกสาร
ตอนนี้เรามาเพิ่มตารางในหน้าเอกสาร:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## ขั้นตอนที่ 9: บันทึกเอกสาร PDF
สุดท้าย เราจะบันทึกเอกสาร PDF:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับการจัดตำแหน่งข้อความสำหรับเนื้อหาแถวตารางโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// เริ่มต้นอินสแตนซ์ใหม่ของตาราง
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// ตั้งค่าสีเส้นขอบตารางเป็น LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// กำหนดเส้นขอบให้กับเซลล์ตาราง
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// สร้างลูปเพื่อเพิ่ม 10 แถว
for (int row_count = 0; row_count < 10; row_count++)
{
	// เพิ่มแถวลงในตาราง
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// เพิ่มวัตถุตารางลงในหน้าแรกของเอกสารอินพุต
tocPage.Paragraphs.Add(table);
// บันทึกเอกสารที่อัปเดตซึ่งมีวัตถุตาราง
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## บทสรุป
ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีจัดแนวเนื้อหาของแถวในตารางในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนนี้จะแสดงวิธีสร้างเอกสาร เริ่มต้นตาราง กำหนดค่าเส้นขอบและการจัดแนว เพิ่มเนื้อหา และบันทึกเอกสาร PDF ตอนนี้คุณสามารถใช้ความรู้นี้กับโครงการของคุณเองได้แล้ว

### คำถามที่พบบ่อย

#### ถาม: ฉันจะจัดตำแหน่งเนื้อหาของเซลล์ตารางในแนวนอนได้อย่างไร

 ตอบ: คุณสามารถจัดแนวเนื้อหาของเซลล์ตารางในแนวนอนได้โดยการตั้งค่า`HorizontalAlign` คุณสมบัติของเซลล์`TextState` วัตถุ. ตัวอย่างเช่น หากต้องการจัดข้อความให้อยู่กึ่งกลาง ให้ใช้`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . คุณยังสามารถตั้งค่าเป็น`HorizontalAlignment.Left` หรือ`HorizontalAlignment.Right` เพื่อการจัดตำแหน่งซ้ายและขวาตามลำดับ

#### ถาม: ฉันสามารถใช้สไตล์และสีเส้นขอบที่แตกต่างกันกับแต่ละเซลล์ภายในตารางได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้สไตล์และสีเส้นขอบที่แตกต่างกันกับแต่ละเซลล์ภายในตารางได้ หากต้องการปรับแต่งเส้นขอบสำหรับเซลล์ใดเซลล์หนึ่ง ให้ตั้งค่า`cell.Border` คุณสมบัติใหม่`BorderInfo`วัตถุด้วยการตั้งค่าที่ต้องการ เช่น ด้านเส้นขอบ ความกว้าง และสี

#### ถาม: ฉันจะปรับการจัดตำแหน่งแนวตั้งของเนื้อหาตารางภายในเซลล์ได้อย่างไร

 ตอบ: คุณสามารถปรับการจัดตำแหน่งแนวตั้งของเนื้อหาตารางภายในเซลล์ได้โดยการตั้งค่า`VerticalAlignment` คุณสมบัติของแถวถึง`VerticalAlignment.Center`, `VerticalAlignment.Top` , หรือ`VerticalAlignment.Bottom`. คุณสมบัตินี้ควบคุมการจัดแนวแนวตั้งของเซลล์ทั้งหมดในแถวนั้น

#### ถาม: เป็นไปได้หรือไม่ที่จะเพิ่มคอลัมน์หรือแถวลงในตารางแบบไดนามิก

 ตอบ: ได้ คุณสามารถเพิ่มคอลัมน์และแถวลงในตารางแบบไดนามิกได้โดยใช้`table.Rows.Add()` วิธีการเพิ่มแถวใหม่และ`row.Cells.Add()` วิธีการเพิ่มเซลล์ใหม่ให้กับแถว คุณสามารถทำสิ่งนี้ภายในลูปหรือตามความต้องการเฉพาะของคุณ

#### ถาม: ฉันจะกำหนดสีพื้นหลังสำหรับเซลล์ที่ต้องการหรือทั้งตารางได้อย่างไร

 ตอบ: หากต้องการตั้งค่าสีพื้นหลังสำหรับเซลล์ที่ต้องการหรือทั้งตาราง ให้ใช้`BackgroundColor` ทรัพย์สินของ`Cell` หรือ`Table` วัตถุ. ตัวอย่างเช่น หากต้องการกำหนดสีพื้นหลังของเซลล์ ให้ใช้`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.