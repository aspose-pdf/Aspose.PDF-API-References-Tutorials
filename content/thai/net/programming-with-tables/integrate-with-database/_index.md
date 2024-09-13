---
title: บูรณาการกับฐานข้อมูลในไฟล์ PDF
linktitle: บูรณาการกับฐานข้อมูลในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: ฝังข้อมูลจากฐานข้อมูลในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 120
url: /th/net/programming-with-tables/integrate-with-database/
---
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีฝังข้อมูลจากฐานข้อมูลลงในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายโค้ดต้นฉบับใน C# ทีละขั้นตอน เมื่อจบบทช่วยสอนนี้ คุณจะทราบวิธีนำเข้าข้อมูลตารางจากฐานข้อมูลลงในเอกสาร PDF มาเริ่มกันเลย!

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ตรวจสอบให้แน่ใจว่าคุณได้กำหนดค่าสภาพแวดล้อมการพัฒนา C# ด้วย Aspose.PDF สำหรับ .NET แล้ว เพิ่มการอ้างอิงไปยังไลบรารีและนำเข้าเนมสเปซที่จำเป็น

## ขั้นตอนที่ 2: การสร้าง DataTable
เราสร้างอินสแตนซ์ของ DataTable เพื่อแสดงข้อมูลที่เราต้องการฝังในเอกสาร PDF ในตัวอย่างนี้ เราสร้าง DataTable ที่มีสามคอลัมน์ ได้แก่ Employee_ID, Employee_Name และ Gender นอกจากนี้ เรายังเพิ่มสองแถวใน DataTable ด้วยข้อมูลจำลอง

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## ขั้นตอนที่ 3: การสร้างเอกสาร PDF และตาราง
เราสร้างอินสแตนซ์ของ Document และเพิ่มหน้าลงในเอกสารนี้ จากนั้นเราสร้างอินสแตนซ์ Table เพื่อแสดงตารางของเราในเอกสาร PDF เรากำหนดความกว้างของคอลัมน์ตารางและรูปแบบเส้นขอบ

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## ขั้นตอนที่ 4: การนำเข้าข้อมูลจาก DataTable เข้าสู่ตาราง
เราใช้เมธอด ImportDataTable เพื่อนำเข้าข้อมูลจาก DataTable เข้าสู่ตารางในเอกสาร PDF

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## ขั้นตอนที่ 5: การเพิ่มตารางลงในเอกสาร
เราเพิ่มตารางลงในคอลเล็กชั่นย่อหน้าของหน้าเอกสาร

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## ขั้นตอนที่ 6: บันทึกเอกสาร
เราบันทึกเอกสาร PDF ด้วยข้อมูลจากฐานข้อมูลที่ฝังไว้

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

ขอแสดงความยินดี! ตอนนี้คุณทราบวิธีการฝังข้อมูลฐานข้อมูลลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET แล้ว

### ตัวอย่างซอร์สโค้ดสำหรับการผสานรวมกับฐานข้อมูลโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//เพิ่ม 2 แถวลงในออบเจ็กต์ DataTable ด้วยโปรแกรม
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// สร้างอินสแตนซ์เอกสาร
Document doc = new Document();
doc.Pages.Add();
// เริ่มต้นอินสแตนซ์ใหม่ของตาราง
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// กำหนดความกว้างของคอลัมน์ของตาราง
table.ColumnWidths = "40 100 100 100";
// ตั้งค่าสีเส้นขอบตารางเป็นสีเทาอ่อน
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// กำหนดเส้นขอบให้กับเซลล์ตาราง
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// เพิ่มวัตถุตารางลงในหน้าแรกของเอกสารอินพุต
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// บันทึกเอกสารอัปเดตที่มีวัตถุตาราง
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการฝังข้อมูลจากฐานข้อมูลลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้คำแนะนำทีละขั้นตอนนี้เพื่อนำเข้าข้อมูลจากฐานข้อมูลของคุณเองและแสดงข้อมูลดังกล่าวในเอกสาร PDF สำรวจเอกสาร Aspose.PDF เพิ่มเติมเพื่อค้นพบคุณลักษณะและความเป็นไปได้อื่นๆ ที่นำเสนอโดยไลบรารีอันทรงพลังนี้

### คำถามที่พบบ่อยสำหรับการบูรณาการกับฐานข้อมูลในไฟล์ PDF

#### ถาม: ฉันสามารถใช้ Aspose.PDF สำหรับ .NET กับประเภทฐานข้อมูลที่แตกต่างกัน เช่น MySQL, SQL Server หรือ Oracle ได้หรือไม่

A: ใช่ คุณสามารถใช้ Aspose.PDF สำหรับ .NET กับฐานข้อมูลประเภทต่างๆ เช่น MySQL, SQL Server, Oracle และอื่นๆ ได้ Aspose.PDF สำหรับ .NET มีฟังก์ชันการทำงานเพื่ออ่านข้อมูลจากแหล่งข้อมูลต่างๆ รวมถึงฐานข้อมูล ไฟล์ XML และอื่นๆ คุณสามารถดึงข้อมูลจากฐานข้อมูลประเภทที่ต้องการและใส่ข้อมูลลงใน DataTable หรือโครงสร้างข้อมูลอื่นๆ ที่เข้ากันได้กับ Aspose.PDF สำหรับ .NET

#### ถาม: ฉันจะปรับแต่งลักษณะของตารางในเอกสาร PDF ได้อย่างไร

A: คุณสามารถปรับแต่งรูปลักษณ์ของตารางในเอกสาร PDF ได้โดยใช้คุณสมบัติต่างๆ ที่จัดเตรียมไว้โดยไลบรารี Aspose.PDF สำหรับ .NET ตัวอย่างเช่น คุณสามารถตั้งค่ารูปแบบเส้นขอบ สีพื้นหลัง สไตล์แบบอักษร และการจัดตำแหน่งต่างๆ สำหรับตารางและเซลล์ของตารางได้ โปรดดูเอกสาร Aspose.PDF สำหรับ .NET สำหรับรายละเอียดเพิ่มเติมเกี่ยวกับการปรับแต่งรูปลักษณ์ของตาราง

#### ถาม: เป็นไปได้หรือไม่ที่จะเพิ่มไฮเปอร์ลิงก์หรือองค์ประกอบแบบโต้ตอบลงในข้อมูลที่นำเข้าจากฐานข้อมูล?

A: ใช่ คุณสามารถเพิ่มไฮเปอร์ลิงก์หรือองค์ประกอบแบบโต้ตอบอื่นๆ ลงในข้อมูลที่นำเข้าจากฐานข้อมูลได้ Aspose.PDF สำหรับ .NET รองรับการเพิ่มไฮเปอร์ลิงก์ บุ๊กมาร์ก และองค์ประกอบแบบโต้ตอบอื่นๆ ลงในเอกสาร PDF คุณสามารถจัดการเนื้อหาใน DataTable ก่อนนำเข้าในตาราง และรวมไฮเปอร์ลิงก์หรือคุณลักษณะแบบโต้ตอบอื่นๆ

#### ถาม: ฉันสามารถแบ่งหน้าตารางได้หรือไม่หากจำนวนแถวเกินที่กำหนด?

A: ใช่ คุณสามารถแบ่งหน้าตารางได้หากตารางมีแถวเกินจำนวนที่กำหนด หากต้องการทำเช่นนี้ คุณสามารถใช้`IsInNewPage` คุณสมบัติของอ็อบเจ็กต์แถวเพื่อระบุว่าหน้าใหม่ควรเริ่มต้นหลังจากแถวที่ระบุ คุณสามารถคำนวณจำนวนแถวที่จะแสดงต่อหน้าและตั้งค่า`IsInNewPage` ทรัพย์สินตามนั้น

#### ถาม: ฉันจะส่งออกเอกสาร PDF ที่มีข้อมูลฐานข้อมูลที่ฝังอยู่ไปยังรูปแบบไฟล์อื่น เช่น DOCX หรือ XLSX ได้อย่างไร

A: Aspose.PDF สำหรับ .NET ช่วยให้คุณแปลงเอกสาร PDF เป็นรูปแบบไฟล์อื่นๆ ได้หลากหลาย รวมถึง DOCX (Microsoft Word) และ XLSX (Microsoft Excel) คุณสามารถใช้ไลบรารี Aspose.PDF สำหรับ .NET ร่วมกับไลบรารี Aspose อื่นๆ เช่น Aspose.Words และ Aspose.Cells เพื่อให้บรรลุผลดังกล่าว ขั้นแรก ให้บันทึกเอกสาร PDF ที่มีข้อมูลฐานข้อมูลที่ฝังไว้ จากนั้นใช้ไลบรารี Aspose ที่เกี่ยวข้องเพื่อแปลงเป็นรูปแบบไฟล์ที่คุณต้องการ