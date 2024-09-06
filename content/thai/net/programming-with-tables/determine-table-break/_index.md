---
title: กำหนดการแบ่งตารางในไฟล์ PDF
linktitle: กำหนดการแบ่งตารางในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการกำหนดตัวแบ่งตารางในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 60
url: /th/net/programming-with-tables/determine-table-break/
---
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีการกำหนดการแบ่งตารางในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายโค้ดต้นฉบับใน C# ทีละขั้นตอน เมื่อจบบทช่วยสอนนี้ คุณจะทราบวิธีการกำหนดว่าตารางเกินระยะขอบหน้ากระดาษหรือไม่ มาเริ่มกันเลย!

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ขั้นแรก ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา C# ด้วย Aspose.PDF สำหรับ .NET แล้ว เพิ่มการอ้างอิงไปยังไลบรารีและนำเข้าเนมสเปซที่จำเป็น

## ขั้นตอนที่ 2: การสร้างเอกสาร PDF
 ในขั้นตอนนี้เราจะสร้างใหม่`Document` วัตถุที่จะแสดงเอกสาร PDF

```csharp
pdf-Document = new Document();
```

เอกสารนี้จะใช้ในการเพิ่มส่วนและตาราง

## ขั้นตอนที่ 3: การเพิ่มส่วนและตาราง
ตอนนี้เรากำลังจะเพิ่มส่วนลงในเอกสาร PDF และสร้างตารางภายในส่วนนี้

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

นอกจากนี้ เรายังกำหนดระยะขอบบนของตารางไว้ที่ 300 จุด คุณสามารถปรับค่านี้ตามความต้องการของคุณได้

## ขั้นตอนที่ 4: การจัดโต๊ะ
ในขั้นตอนนี้ เราจะกำหนดค่าคุณสมบัติของตาราง เช่น ความกว้างของคอลัมน์และเส้นขอบ

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

ที่นี่เราจะกำหนดความกว้างของคอลัมน์ตารางและขอบเซลล์ คุณสามารถปรับค่าเหล่านี้ได้ตามความต้องการของคุณ

## ขั้นตอนที่ 5: เพิ่มแถวและเซลล์ลงในตาราง
ตอนนี้เราจะสร้างแถวและเซลล์ในตารางโดยใช้ลูป

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

ที่นี่เราสร้าง 17 แถวในตารางและเพิ่ม 3 เซลล์ในแต่ละแถว คุณสามารถปรับหัวเข็มขัดตามความต้องการของคุณ

## ขั้นตอนที่ 6: การกำหนดการแบ่งตาราง
ตอนนี้เราจะพิจารณาว่าตารางเกินระยะขอบหน้าหรือไม่ โดยการเปรียบเทียบความสูงของหน้ากับความสูงรวมของวัตถุในตาราง

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

เราคำนวณความสูงของหน้าและความสูงรวมของวัตถุโดยคำนึงถึงระยะขอบ หากความแตกต่างอยู่ที่ 10 หรือต่ำกว่า ตารางจะเกินระยะขอบหน้า

## ขั้นตอนที่ 7: บันทึกเอกสาร PDF
สุดท้ายเราบันทึกเอกสาร PDF พร้อมผลลัพธ์

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

อย่าลืมระบุไดเรกทอรีเอกสารที่ถูกต้อง ไฟล์ PDF ที่ได้จะถูกบันทึกพร้อมการแบ่งตารางตามที่กำหนด

### ตัวอย่างซอร์สโค้ดสำหรับการกำหนดการแบ่งตารางโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างอินสแตนซ์ของคลาส PDF ของวัตถุ
Document pdf = new Document();
// เพิ่มส่วนนี้ลงในคอลเล็กชั่นส่วนเอกสาร PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// สร้างอินสแตนซ์ของวัตถุตาราง
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// เพิ่มตารางในคอลเลกชันย่อหน้าของส่วนที่ต้องการ
page.Paragraphs.Add(table1);
// ตั้งค่าด้วยความกว้างของคอลัมน์ของตาราง
table1.ColumnWidths = "100 100 100";
// ตั้งค่าเส้นขอบเซลล์เริ่มต้นโดยใช้ BorderInfo object
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// กำหนดเส้นขอบตารางโดยใช้ BorderInfo วัตถุที่กำหนดเองอื่น
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// สร้างวัตถุ MarginInfo และตั้งค่าระยะขอบซ้าย ล่าง ขวา และบน
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// ตั้งค่าการเติมเซลล์เริ่มต้นเป็นวัตถุ MarginInfo
table1.DefaultCellPadding = margin;
// ถ้าเพิ่มตัวนับเป็น 17 โต๊ะจะพัง
// เพราะไม่สามารถรองรับได้มากกว่านี้อีกแล้ว
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
// รับข้อมูลความสูงรวมของขอบบนและล่างของหน้า
// ระยะขอบด้านบนของโต๊ะและความสูงของโต๊ะ
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// แสดงความสูงของหน้า ความสูงของตาราง ขอบด้านบนของตาราง และด้านบนของหน้า
// และข้อมูลระยะขอบล่าง
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// ตรวจสอบว่าเราได้หักผลรวมของ Page top margin + Page Bottom margin หรือไม่
// + ขอบด้านบนของตารางและความสูงของตารางจากความสูงของหน้ากระดาษและน้อยกว่า
// มากกว่า 10 (แถวเฉลี่ยสามารถมากกว่า 10 ได้)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// หากค่าน้อยกว่า 10 จะแสดงข้อความ
	//ซึ่งแสดงว่าไม่สามารถวางแถวอื่นได้และหากเราเพิ่มแถวใหม่
	// แถว ตารางจะแตก ขึ้นอยู่กับค่าความสูงของแถว
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// บันทึกเอกสาร PDF
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการกำหนดการแบ่งตารางในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้คู่มือทีละขั้นตอนนี้เพื่อตรวจสอบว่าตารางเกินระยะขอบหน้ากระดาษในโปรเจ็กต์ C# ของคุณหรือไม่

### คำถามที่พบบ่อยสำหรับการกำหนดการแบ่งตารางในไฟล์ PDF

#### ถาม: จุดประสงค์ของการกำหนดการแบ่งตารางในเอกสาร PDF คืออะไร

A: จุดประสงค์ของการกำหนดการแบ่งตารางในเอกสาร PDF คือเพื่อตรวจสอบว่าตารางเกินระยะขอบหน้าหรือไม่ วิธีนี้จะช่วยให้มั่นใจว่าเนื้อหาของตารางจะแสดงอย่างถูกต้องภายในพื้นที่หน้าว่าง เมื่อตรวจจับการแบ่งตารางได้แล้ว คุณสามารถจัดการกับเนื้อหาที่ล้นออกมาและปรับเค้าโครงตารางให้เหมาะสมได้

#### ถาม: ฉันจะปรับระยะขอบบนของตารางได้อย่างไร

 A: ในโค้ดต้นฉบับ C# ที่ให้มา คุณสามารถปรับระยะขอบด้านบนของตารางได้โดยการแก้ไขค่าของ`table1.Margin.Top`คุณสมบัติ เพิ่มหรือลดค่าตามต้องการเพื่อตั้งค่าระยะขอบบนที่ต้องการสำหรับตาราง

#### ถาม: ฉันสามารถกำหนดลักษณะของตาราง เช่น สีเซลล์และขนาดแบบอักษรได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งรูปลักษณ์ของตารางและเซลล์ได้โดยใช้คุณสมบัติและวิธีการต่างๆ ที่ Aspose.PDF สำหรับ .NET จัดเตรียมไว้ ตัวอย่างเช่น คุณสามารถเปลี่ยนสีพื้นหลังของเซลล์ ขนาดฟอนต์ ตระกูลฟอนต์ การจัดตำแหน่งข้อความ และอื่นๆ อีกมากมาย โปรดดูเอกสารประกอบอย่างเป็นทางการเพื่อดูข้อมูลเพิ่มเติมเกี่ยวกับวิธีปรับแต่งรูปลักษณ์ของตาราง

#### ถาม: จะเกิดอะไรขึ้นถ้าตารางเกินระยะขอบหน้า?

A: หากตารางยาวเกินขอบหน้ากระดาษ อาจทำให้เนื้อหาถูกตัดทอนหรือทับซ้อนกัน ทำให้เอกสาร PDF อ่านและจัดระเบียบได้ยากขึ้น คุณสามารถมั่นใจได้ว่าเนื้อหาจะยังคงแสดงอย่างถูกต้องภายในพื้นที่หน้ากระดาษที่พร้อมใช้งานได้ โดยการตรวจจับการแบ่งตารางและจัดการกับส่วนที่เกิน

#### ถาม: ฉันสามารถกำหนดการแบ่งตารางสำหรับตารางหลายตารางในเอกสาร PDF เดียวกันได้หรือไม่

A: ใช่ คุณสามารถกำหนดการแบ่งตารางสำหรับตารางหลายตารางในเอกสาร PDF เดียวกันได้ เพียงทำซ้ำขั้นตอนสำหรับแต่ละตารางที่คุณต้องการวิเคราะห์ และปรับเค้าโครงตารางตามความจำเป็นเพื่อป้องกันเนื้อหาล้น