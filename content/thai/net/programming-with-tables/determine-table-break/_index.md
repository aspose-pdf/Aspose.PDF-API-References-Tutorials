---
title: กำหนดการแบ่งตารางในไฟล์ PDF
linktitle: กำหนดการแบ่งตารางในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีระบุตัวแบ่งตารางในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 60
url: /th/net/programming-with-tables/determine-table-break/
---
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีระบุตัวแบ่งตารางในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ดใน C# ทีละขั้นตอน ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีตรวจสอบว่าตารางเกินระยะขอบหน้าหรือไม่ เริ่มกันเลย!

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ขั้นแรก ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา C# ของคุณด้วย Aspose.PDF สำหรับ .NET เพิ่มการอ้างอิงไปยังไลบรารีและนำเข้าเนมสเปซที่จำเป็น

## ขั้นตอนที่ 2: การสร้างเอกสาร PDF
 ในขั้นตอนนี้ เราจะสร้างใหม่`Document` วัตถุเพื่อแสดงเอกสาร PDF

```csharp
pdf-Document = new Document();
```

เอกสารนี้จะใช้ในการเพิ่มส่วนและตาราง

## ขั้นตอนที่ 3: การเพิ่มส่วนและตาราง
ตอนนี้เรากำลังจะเพิ่มส่วนลงในเอกสาร PDF ของเราและสร้างตารางภายในส่วนนี้

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

นอกจากนี้เรายังระบุระยะขอบบน 300 จุดสำหรับตารางด้วย คุณสามารถปรับค่านี้ได้ตามความต้องการของคุณ

## ขั้นตอนที่ 4: การตั้งค่าตาราง
ในขั้นตอนนี้ เรากำหนดค่าคุณสมบัติของตาราง เช่น ความกว้างของคอลัมน์และเส้นขอบ

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

ที่นี่เรากำหนดความกว้างของคอลัมน์ตารางและเส้นขอบเซลล์ คุณสามารถปรับค่าเหล่านี้ได้ตามความต้องการของคุณ

## ขั้นตอนที่ 5: เพิ่มแถวและเซลล์ลงในตาราง
ตอนนี้เราจะสร้างแถวและเซลล์ในตารางโดยใช้การวนซ้ำ

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

ที่นี่เราสร้าง 17 แถวในตารางและเพิ่มเซลล์สามเซลล์ลงในแต่ละแถว คุณสามารถปรับหัวเข็มขัดได้ตามความต้องการของคุณ

## ขั้นตอนที่ 6: การกำหนดตัวแบ่งตาราง
ตอนนี้เราจะพิจารณาว่าตารางเกินระยะขอบหน้าหรือไม่โดยการเปรียบเทียบความสูงของหน้ากับความสูงรวมของวัตถุในตาราง

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

เราคำนวณความสูงของหน้าและความสูงรวมของวัตถุโดยคำนึงถึงระยะขอบ หากความแตกต่างคือ 10 หรือน้อยกว่า ตารางจะเกินระยะขอบหน้า

## ขั้นตอนที่ 7: บันทึกเอกสาร PDF
สุดท้าย เราจะบันทึกเอกสาร PDF พร้อมผลลัพธ์

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

อย่าลืมระบุไดเร็กทอรีเอกสารที่ถูกต้อง ไฟล์ PDF ที่ได้จะถูกบันทึกพร้อมกับตัวแบ่งตารางที่กำหนด

### ตัวอย่างซอร์สโค้ดสำหรับกำหนดตัวแบ่งตารางโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างอินสแตนซ์คลาส PDF ของวัตถุ
Document pdf = new Document();
// เพิ่มส่วนไปยังคอลเลกชันส่วนเอกสาร PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// สร้างอินสแตนซ์ของวัตถุตาราง
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// เพิ่มตารางในคอลเลกชันย่อหน้าของส่วนที่ต้องการ
page.Paragraphs.Add(table1);
// กำหนดความกว้างของคอลัมน์ของตาราง
table1.ColumnWidths = "100 100 100";
// ตั้งค่าเส้นขอบเซลล์เริ่มต้นโดยใช้วัตถุ BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// ตั้งค่าเส้นขอบตารางโดยใช้วัตถุ BorderInfo ที่กำหนดเองอื่น
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// สร้างวัตถุ MarginInfo และตั้งค่าระยะขอบด้านซ้าย ล่าง ขวา และบน
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// ตั้งค่าการเติมเซลล์เริ่มต้นเป็นวัตถุ MarginInfo
table1.DefaultCellPadding = margin;
// หากคุณเพิ่มตัวนับเป็น 17 โต๊ะจะพัง
// เพราะมันไม่สามารถรองรับได้อีกต่อไปในหน้านี้
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// รับข้อมูลความสูงของหน้า
float PageHeight = (float)pdf.PageInfo.Height;
// รับข้อมูลความสูงรวมของระยะขอบบนและล่างของหน้า
// ระยะขอบบนโต๊ะและความสูงของตาราง
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// แสดงความสูงของหน้า ความสูงของตาราง ขอบด้านบนของตาราง และด้านบนของหน้า
// และข้อมูลระยะขอบล่าง
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// ตรวจสอบว่าเราหักผลรวมของระยะขอบบนของหน้า + ขอบล่างของหน้าหรือไม่
// + ระยะขอบด้านบนของตารางและความสูงของตารางจากความสูงของหน้าและน้อยกว่า
// มากกว่า 10 (แถวเฉลี่ยสามารถมากกว่า 10 ได้)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// หากค่าน้อยกว่า 10 ให้แสดงข้อความ
	//ซึ่งแสดงว่าไม่สามารถวางแถวอื่นได้และถ้าเราเพิ่มแถวใหม่
	// แถวนั้นโต๊ะจะพัง ขึ้นอยู่กับค่าความสูงของแถว
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// บันทึกเอกสาร PDF
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีระบุตัวแบ่งตารางในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้คำแนะนำทีละขั้นตอนนี้เพื่อตรวจสอบว่าตารางเกินระยะขอบหน้าในโครงการ C# ของคุณเองหรือไม่

### คำถามที่พบบ่อยสำหรับการกำหนดตัวแบ่งตารางในไฟล์ PDF

#### ถาม: จุดประสงค์ในการกำหนดตัวแบ่งตารางในเอกสาร PDF คืออะไร

ตอบ: วัตถุประสงค์ในการพิจารณาการแบ่งตารางในเอกสาร PDF คือการตรวจสอบว่าตารางเกินระยะขอบหน้าหรือไม่ เพื่อให้แน่ใจว่าเนื้อหาของตารางจะแสดงอย่างถูกต้องภายในพื้นที่หน้าที่มีอยู่ ด้วยการตรวจจับการแตกตาราง คุณสามารถจัดการกับเนื้อหาล้นและปรับเค้าโครงตารางให้เหมาะสมได้

#### ถาม: ฉันจะปรับระยะขอบด้านบนของตารางได้อย่างไร

 ตอบ: ในซอร์สโค้ด C# ที่ให้มา คุณสามารถปรับระยะขอบด้านบนของตารางได้โดยการแก้ไขค่าของ`table1.Margin.Top`คุณสมบัติ. เพิ่มหรือลดค่าตามความจำเป็นเพื่อตั้งค่าระยะขอบด้านบนที่ต้องการสำหรับตาราง

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของตาราง เช่น สีของเซลล์และขนาดตัวอักษรได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของตารางและเซลล์ได้โดยใช้คุณสมบัติและวิธีการต่างๆ ที่ Aspose.PDF สำหรับ .NET มอบให้ ตัวอย่างเช่น คุณสามารถเปลี่ยนสีพื้นหลังของเซลล์ ขนาดแบบอักษร ตระกูลแบบอักษร การจัดแนวข้อความ และอื่นๆ ได้ โปรดดูเอกสารประกอบอย่างเป็นทางการสำหรับข้อมูลเพิ่มเติมเกี่ยวกับวิธีการปรับแต่งลักษณะที่ปรากฏของตาราง

#### ถาม: จะเกิดอะไรขึ้นหากตารางเกินระยะขอบหน้า?

ตอบ: หากตารางเกินระยะขอบหน้า อาจส่งผลให้เนื้อหาถูกตัดทอนหรือทับซ้อนกัน ทำให้เอกสาร PDF อ่านและจัดระเบียบได้น้อยลง ด้วยการตรวจจับตัวแบ่งตารางและจัดการกับการโอเวอร์โฟลว์ คุณสามารถมั่นใจได้ว่าเนื้อหายังคงแสดงอย่างเหมาะสมภายในพื้นที่เพจที่มีอยู่

#### ถาม: ฉันสามารถระบุตัวแบ่งตารางสำหรับหลายตารางในเอกสาร PDF เดียวกันได้หรือไม่

ตอบ: ได้ คุณสามารถกำหนดตัวแบ่งตารางสำหรับหลายตารางได้ในเอกสาร PDF เดียวกัน เพียงทำซ้ำขั้นตอนสำหรับแต่ละตารางที่คุณต้องการวิเคราะห์และปรับเค้าโครงตารางตามความจำเป็นเพื่อป้องกันเนื้อหาล้น