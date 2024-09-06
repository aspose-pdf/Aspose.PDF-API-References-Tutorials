---
title: การจัดตำแหน่งข้อความสำหรับเนื้อหาแถวตาราง
linktitle: การจัดตำแหน่งข้อความสำหรับเนื้อหาแถวตาราง
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีจัดเรียงเนื้อหาแถวในตาราง PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 210
url: /th/net/programming-with-tables/text-alignment-for-table-row-content/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณทีละขั้นตอนในการจัดแนวเนื้อหาของแถวในตารางของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายโค้ดต้นฉบับ C# ที่ให้มาและแสดงวิธีการใช้งานให้คุณดู

## ขั้นตอนที่ 1: การสร้างเอกสาร PDF
ก่อนอื่นเราจะสร้างเอกสาร PDF:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## ขั้นตอนที่ 2: การเริ่มต้นตาราง
ต่อไปเราจะสร้างตารางเริ่มต้น:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## ขั้นตอนที่ 3: ตั้งค่าสีเส้นขอบตาราง
เราจะกำหนดสีเส้นขอบตาราง:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## ขั้นตอนที่ 4: การกำหนดค่าเส้นขอบเซลล์ตาราง
เราจะกำหนดค่าเส้นขอบเซลล์ของตาราง:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## ขั้นตอนที่ 5: วนซ้ำเพื่อเพิ่ม 10 แถวลงในตาราง
ตอนนี้เราจะใช้ลูปเพื่อเพิ่ม 10 แถวลงในตาราง:

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

## ขั้นตอนที่ 7: เพิ่มเนื้อหาลงในเซลล์แถว
เรากำลังจะเพิ่มเนื้อหาลงในเซลล์แถว:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## ขั้นตอนที่ 8: การเพิ่มตารางลงในหน้าเอกสาร
ตอนนี้เรามาเพิ่มตารางลงในหน้าเอกสารกัน:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## ขั้นตอนที่ 9: บันทึกเอกสาร PDF
สุดท้ายเราจะบันทึกเอกสาร PDF:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการจัดตำแหน่งข้อความสำหรับเนื้อหาแถวตารางโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// เริ่มต้นอินสแตนซ์ใหม่ของตาราง
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// ตั้งค่าสีเส้นขอบตารางเป็นสีเทาอ่อน
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// กำหนดเส้นขอบให้กับเซลล์ตาราง
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// สร้างลูปเพื่อเพิ่ม 10 แถว
for (int row_count = 0; row_count < 10; row_count++)
{
	// เพิ่มแถวเข้าตาราง
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// เพิ่มวัตถุตารางลงในหน้าแรกของเอกสารอินพุต
tocPage.Paragraphs.Add(table);
// บันทึกเอกสารอัปเดตที่มีวัตถุตาราง
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## บทสรุป
ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีการจัดแนวเนื้อหาของแถวในตารางในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET แล้ว คำแนะนำทีละขั้นตอนนี้จะแสดงวิธีการสร้างเอกสาร เริ่มต้นตาราง กำหนดค่าเส้นขอบและการจัดแนว เพิ่มเนื้อหา และบันทึกเอกสาร PDF ตอนนี้คุณสามารถนำความรู้นี้ไปใช้กับโครงการของคุณเองได้แล้ว

### คำถามที่พบบ่อย

#### ถาม: ฉันจะจัดเรียงเนื้อหาของเซลล์ตารางในแนวนอนได้อย่างไร

 A: คุณสามารถจัดตำแหน่งเนื้อหาของเซลล์ตารางในแนวนอนได้โดยการตั้งค่า`HorizontalAlign` คุณสมบัติของตัวเซลล์`TextState` วัตถุ ตัวอย่างเช่น หากต้องการจัดข้อความให้อยู่กึ่งกลาง ให้ใช้`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . คุณยังสามารถตั้งค่าได้`HorizontalAlignment.Left` หรือ`HorizontalAlignment.Right` สำหรับการจัดตำแหน่งซ้ายและขวาตามลำดับ

#### ถาม: ฉันสามารถใช้รูปแบบเส้นขอบและสีที่แตกต่างกันกับเซลล์แต่ละเซลล์ภายในตารางได้หรือไม่

 A: ใช่ คุณสามารถใช้รูปแบบและสีเส้นขอบที่แตกต่างกันกับเซลล์แต่ละเซลล์ภายในตารางได้ หากต้องการปรับแต่งเส้นขอบสำหรับเซลล์ใดเซลล์หนึ่ง ให้ตั้งค่า`cell.Border` ทรัพย์สินให้เป็นใหม่`BorderInfo`วัตถุด้วยการตั้งค่าตามต้องการ เช่น ขอบด้าน ความกว้าง และสี

#### ถาม: ฉันจะปรับการจัดแนวแนวตั้งของเนื้อหาตารางภายในเซลล์ได้อย่างไร

 A: คุณสามารถปรับการจัดแนวแนวตั้งของเนื้อหาตารางภายในเซลล์ได้โดยการตั้งค่า`VerticalAlignment` ทรัพย์สินของแถวนั้น`VerticalAlignment.Center`, `VerticalAlignment.Top` , หรือ`VerticalAlignment.Bottom`คุณสมบัตินี้จะควบคุมการจัดตำแหน่งแนวตั้งของเซลล์ทั้งหมดในแถวนั้น

#### ถาม: สามารถเพิ่มคอลัมน์หรือแถวเพิ่มเติมในตารางแบบไดนามิกได้หรือไม่

 A: ใช่ คุณสามารถเพิ่มคอลัมน์และแถวเพิ่มเติมลงในตารางแบบไดนามิกได้โดยใช้`table.Rows.Add()` วิธีการเพิ่มแถวใหม่และ`row.Cells.Add()` วิธีการเพิ่มเซลล์ใหม่ลงในแถว คุณสามารถทำได้ภายในลูปหรือตามความต้องการเฉพาะของคุณ

#### ถาม: ฉันจะตั้งค่าสีพื้นหลังให้กับเซลล์เฉพาะหรือตารางทั้งหมดได้อย่างไร

 ก: หากต้องการตั้งค่าสีพื้นหลังสำหรับเซลล์เฉพาะหรือตารางทั้งหมด ให้ใช้`BackgroundColor` ทรัพย์สินของ`Cell` หรือ`Table` วัตถุ ตัวอย่างเช่น ในการตั้งค่าสีพื้นหลังของเซลล์ ให้ใช้`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.