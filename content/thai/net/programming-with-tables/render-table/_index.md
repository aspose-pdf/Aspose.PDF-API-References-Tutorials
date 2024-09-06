---
title: เรนเดอร์ตารางในเอกสาร PDF
linktitle: เรนเดอร์ตารางในเอกสาร PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการแสดงตารางในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 170
url: /th/net/programming-with-tables/render-table/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณทีละขั้นตอนในการแสดงตารางในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายโค้ดต้นฉบับ C# ที่ให้มาและแสดงวิธีการใช้งานให้คุณดู

## ขั้นตอนที่ 1: การสร้างเอกสาร
ก่อนอื่นเราจะสร้างเอกสาร PDF ใหม่:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างเอกสารใหม่
Document doc = new Document();
```

## ขั้นตอนที่ 2: การกำหนดค่าระยะขอบและทิศทางของหน้า
ต่อไปเราจะกำหนดค่าระยะขอบหน้าและตั้งค่าการวางแนวเป็นโหมดแนวนอน:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## ขั้นตอนที่ 3: การสร้างตารางและคอลัมน์
ตอนนี้เรามาสร้างตารางและกำหนดความกว้างของคอลัมน์กัน:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## ขั้นตอนที่ 4: เพิ่มแถวและเซลล์ลงในตาราง
ต่อไปเราจะเพิ่มแถวและเซลล์ลงในตารางโดยใช้ลูป:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## ขั้นตอนที่ 5: การเพิ่มตารางลงในหน้า
ตอนนี้เรามาเพิ่มตารางลงในหน้าเอกสารกัน:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## ขั้นตอนที่ 6: การแสดงตารางบนหน้าใหม่
ต่อไปเราจะสร้างตารางใหม่และตั้งค่าคุณสมบัติ "IsInNewPage" เป็น "true" เพื่อแสดงตารางบนหน้าใหม่:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## ขั้นตอนที่ 7: บันทึก PDF
สุดท้ายเราบันทึกเอกสาร PDF:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการเรนเดอร์ตารางโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// เพิ่มหน้าแล้ว
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// ผมต้องการเก็บตารางที่ 1 ไว้หน้าถัดไปครับ...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## บทสรุป
ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีแสดงตารางในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET แล้ว คำแนะนำทีละขั้นตอนนี้จะแสดงให้คุณเห็นถึงวิธีการสร้างเอกสาร กำหนดค่าระยะขอบและทิศทางของหน้า เพิ่มตาราง และแสดงตารางในหน้าใหม่ ตอนนี้คุณสามารถนำความรู้เหล่านี้ไปใช้กับโปรเจ็กต์ของคุณเองได้แล้ว

### คำถามที่พบบ่อยสำหรับการเรนเดอร์ตารางในเอกสาร PDF

#### ถาม: ฉันจะปรับเปลี่ยนรูปลักษณ์ของตาราง เช่น เปลี่ยนสีเซลล์หรือเพิ่มเส้นขอบ ได้อย่างไร

A: หากต้องการปรับเปลี่ยนลักษณะของตาราง คุณสามารถตั้งค่าคุณสมบัติต่างๆ ของ`Aspose.Pdf.Table` และเซลล์ของมัน ตัวอย่างเช่น คุณสามารถตั้งค่า`BackgroundColor` คุณสมบัติของเซลล์ที่จะเปลี่ยนสีพื้นหลัง คุณยังสามารถตั้งค่า`Border` คุณสมบัติของตารางหรือเซลล์แต่ละเซลล์ในการเพิ่มเส้นขอบ นอกจากนี้ คุณยังสามารถปรับแต่งแบบอักษร สีข้อความ และการจัดตำแหน่งของเนื้อหาตารางได้โดยการแก้ไข`TextState` ของ`TextFragment` วัตถุที่ถูกเพิ่มเข้าไปในเซลล์

#### ถาม: ฉันสามารถเพิ่มส่วนหัวหรือส่วนท้ายลงในตารางได้หรือไม่

A: ใช่ คุณสามารถเพิ่มส่วนหัวหรือส่วนท้ายของตารางได้โดยการสร้างแถวเพิ่มเติมที่จุดเริ่มต้นหรือจุดสิ้นสุดของตารางและกำหนดเนื้อหาที่เหมาะสมในเซลล์ คุณสามารถปรับแต่งส่วนหัวหรือส่วนท้ายของตารางได้แยกจากเนื้อหาอื่นๆ ในตารางโดยการเพิ่มรูปแบบหรือเนื้อหาที่แตกต่างกันในแถวเฉพาะเหล่านี้

#### ถาม: ฉันจะควบคุมตำแหน่งของตารางบนหน้าได้อย่างไร

 A: เพื่อควบคุมตำแหน่งของตารางบนหน้า คุณสามารถปรับได้`MarginInfo` ของ`PageInfo` วัตถุ.`MarginInfo`ช่วยให้คุณตั้งค่าระยะขอบซ้าย ขวา บน และล่างของหน้า ซึ่งจะส่งผลต่อพื้นที่ว่างของตาราง นอกจากนี้คุณยังสามารถใช้`PositioningType` ทรัพย์สินของ`Aspose.Pdf.Table` เพื่อควบคุมการจัดตำแหน่งแนวนอนและแนวตั้งภายในพื้นที่เนื้อหาของหน้า

#### ถาม: ฉันสามารถส่งออกตารางไปยังรูปแบบไฟล์อื่น เช่น Excel หรือ CSV ได้หรือไม่

A: Aspose.PDF สำหรับ .NET ได้รับการออกแบบมาโดยเฉพาะสำหรับการทำงานกับเอกสาร PDF แม้ว่าจะสามารถส่งออกเอกสาร PDF เป็นรูปภาพหรือ XPS ได้ แต่จะไม่รองรับการส่งออกตารางเป็นรูปแบบเช่น Excel หรือ CSV โดยตรง หากต้องการส่งออกข้อมูลตารางเป็นรูปแบบไฟล์อื่น คุณอาจต้องใช้ไลบรารีหรือวิธีการเพิ่มเติมเพื่อแปลงเนื้อหา PDF เป็นรูปแบบที่ต้องการ

#### ถาม: ฉันจะเพิ่มไฮเปอร์ลิงก์ลงในเซลล์ตารางได้อย่างไร

 A: หากต้องการเพิ่มไฮเปอร์ลิงก์ลงในเซลล์ตาราง คุณสามารถใช้`Aspose.Pdf.WebHyperlink` คลาสเพื่อสร้างไฮเปอร์ลิงก์แล้วเพิ่มเป็นจุดยึดไปยัง`TextFragment`ภายในเซลล์ ช่วยให้คุณสามารถเชื่อมโยง URL หรือลิงก์เป้าหมายกับข้อความหรือเนื้อหาเฉพาะภายในเซลล์ เพื่อสร้างไฮเปอร์ลิงก์ที่สามารถคลิกได้