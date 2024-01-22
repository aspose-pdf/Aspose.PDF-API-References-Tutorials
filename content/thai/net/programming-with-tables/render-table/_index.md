---
title: แสดงผลตารางในเอกสาร PDF
linktitle: แสดงผลตารางในเอกสาร PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีแสดงตารางในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 170
url: /th/net/programming-with-tables/render-table/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณทีละขั้นตอนในการแสดงตารางในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและแสดงวิธีใช้งาน

## ขั้นตอนที่ 1: การสร้างเอกสาร
ขั้นแรก เราจะสร้างเอกสาร PDF ใหม่:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างเอกสารใหม่
Document doc = new Document();
```

## ขั้นตอนที่ 2: การกำหนดค่าระยะขอบหน้าและการวางแนว
ต่อไป เราจะกำหนดค่าระยะขอบของหน้าและตั้งค่าการวางแนวเป็นโหมดแนวนอน:

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
ตอนนี้เรามาสร้างตารางและตั้งค่าความกว้างของคอลัมน์:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## ขั้นตอนที่ 4: เพิ่มแถวและเซลล์ลงในตาราง
ต่อไป เราจะเพิ่มแถวและเซลล์ลงในตารางโดยใช้การวนซ้ำ:

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

## ขั้นตอนที่ 5: การเพิ่มตารางลงในเพจ
ตอนนี้เรามาเพิ่มตารางในหน้าเอกสาร:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## ขั้นตอนที่ 6: การแสดงตารางในหน้าใหม่
ต่อไป เราจะสร้างตารางใหม่และตั้งค่าคุณสมบัติ "IsInNewPage" เป็น "true" เพื่อแสดงตารางในหน้าใหม่:

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
สุดท้าย เราบันทึกเอกสาร PDF:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับ Render Table โดยใช้ Aspose.PDF สำหรับ .NET

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
// ขอเก็บตาราง 1 ไว้หน้าต่อไปครับ...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## บทสรุป
ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีการแสดงตารางในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET แล้ว คำแนะนำทีละขั้นตอนนี้แสดงให้คุณเห็นถึงวิธีการสร้างเอกสาร กำหนดค่าระยะขอบและการวางแนวของหน้า เพิ่มตาราง และแสดงตารางบนหน้าใหม่ ตอนนี้คุณสามารถใช้ความรู้นี้กับโครงการของคุณเองได้แล้ว

### คำถามที่พบบ่อยสำหรับการเรนเดอร์ตารางในเอกสาร PDF

#### ถาม: ฉันจะปรับเปลี่ยนลักษณะของตาราง เช่น การเปลี่ยนสีของเซลล์หรือการเพิ่มเส้นขอบได้อย่างไร

ตอบ: หากต้องการแก้ไขรูปลักษณ์ของตาราง คุณสามารถตั้งค่าคุณสมบัติต่างๆ ของตารางได้`Aspose.Pdf.Table` และเซลล์ของมัน ตัวอย่างเช่น คุณสามารถตั้งค่า`BackgroundColor` คุณสมบัติของเซลล์ในการเปลี่ยนสีพื้นหลัง คุณยังสามารถตั้งค่า`Border` คุณสมบัติของตารางหรือแต่ละเซลล์เพื่อเพิ่มเส้นขอบ นอกจากนี้ คุณสามารถปรับแต่งแบบอักษร สีข้อความ และการจัดตำแหน่งของเนื้อหาตารางได้โดยการแก้ไข`TextState` ของ`TextFragment` วัตถุที่เพิ่มเข้าไปในเซลล์

#### ถาม: ฉันสามารถเพิ่มส่วนหัวหรือส่วนท้ายลงในตารางได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มส่วนหัวหรือส่วนท้ายลงในตารางได้โดยการสร้างแถวเพิ่มเติมที่จุดเริ่มต้นหรือจุดสิ้นสุดของตาราง และตั้งค่าเนื้อหาที่เหมาะสมในเซลล์ คุณสามารถปรับแต่งส่วนหัวหรือส่วนท้ายได้อย่างอิสระจากเนื้อหาตารางที่เหลือโดยการเพิ่มสไตล์หรือเนื้อหาที่แตกต่างกันให้กับแถวเฉพาะเหล่านี้

#### ถาม: ฉันจะควบคุมตำแหน่งของตารางบนเพจได้อย่างไร?

 ตอบ: หากต้องการควบคุมตำแหน่งของตารางบนเพจ คุณสามารถปรับเปลี่ยนได้`MarginInfo` ของ`PageInfo` วัตถุ. ที่`MarginInfo`ให้คุณตั้งค่าระยะขอบซ้าย ขวา บน และล่างของหน้า ซึ่งส่งผลต่อพื้นที่ว่างของตาราง คุณยังสามารถใช้`PositioningType` ทรัพย์สินของ`Aspose.Pdf.Table` เพื่อควบคุมการจัดตำแหน่งแนวนอนและแนวตั้งภายในพื้นที่เนื้อหาของหน้า

#### ถาม: ฉันสามารถส่งออกตารางเป็นรูปแบบไฟล์ต่างๆ เช่น Excel หรือ CSV ได้หรือไม่

ตอบ: Aspose.PDF สำหรับ .NET ได้รับการออกแบบมาเพื่อทำงานกับเอกสาร PDF เป็นหลัก แม้ว่าจะสามารถส่งออกเอกสาร PDF เป็นรูปภาพหรือ XPS ได้ แต่ก็ไม่รองรับการส่งออกตารางเป็นรูปแบบเช่น Excel หรือ CSV โดยตรง หากต้องการส่งออกข้อมูลตารางเป็นรูปแบบไฟล์ต่างๆ คุณอาจจำเป็นต้องใช้ไลบรารีหรือวิธีการเพิ่มเติมเพื่อแปลงเนื้อหา PDF เป็นรูปแบบที่ต้องการ

#### ถาม: ฉันจะเพิ่มไฮเปอร์ลิงก์ลงในเซลล์ตารางได้อย่างไร

 ตอบ: หากต้องการเพิ่มไฮเปอร์ลิงก์ลงในเซลล์ตาราง คุณสามารถใช้ไฟล์`Aspose.Pdf.WebHyperlink` คลาสเพื่อสร้างไฮเปอร์ลิงก์แล้วเพิ่มเป็นจุดยึดให้กับ`TextFragment`ภายในเซลล์ ซึ่งจะทำให้คุณสามารถเชื่อมโยง URL หรือเป้าหมายลิงก์กับข้อความหรือเนื้อหาเฉพาะภายในเซลล์ ทำให้เกิดเป็นไฮเปอร์ลิงก์ที่คลิกได้