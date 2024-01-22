---
title: บูรณาการกับฐานข้อมูลในรูปแบบไฟล์ PDF
linktitle: บูรณาการกับฐานข้อมูลในรูปแบบไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: ฝังข้อมูลจากฐานข้อมูลในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 120
url: /th/net/programming-with-tables/integrate-with-database/
---
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีฝังข้อมูลจากฐานข้อมูลในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ดใน C# ทีละขั้นตอน ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีนำเข้าข้อมูลตารางจากฐานข้อมูลไปยังเอกสาร PDF เริ่มกันเลย!

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ตรวจสอบให้แน่ใจว่าคุณได้กำหนดค่าสภาพแวดล้อมการพัฒนา C# ของคุณด้วย Aspose.PDF สำหรับ .NET เพิ่มการอ้างอิงไปยังไลบรารีและนำเข้าเนมสเปซที่จำเป็น

## ขั้นตอนที่ 2: การสร้าง DataTable
เราสร้างอินสแตนซ์ของ DataTable เพื่อแสดงข้อมูลที่เราต้องการฝังในเอกสาร PDF ในตัวอย่างนี้ เราสร้าง DataTable ที่มีสามคอลัมน์: Employee_ID, Employee_Name และ Gender นอกจากนี้เรายังเพิ่มสองแถวลงใน DataTable ด้วยข้อมูลจำลอง

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
เราสร้างอินสแตนซ์ของเอกสารและเพิ่มหน้าให้กับเอกสารนี้ ต่อไป เราจะสร้างอินสแตนซ์ Table เพื่อแสดงตารางของเราในเอกสาร PDF เรากำหนดความกว้างของคอลัมน์ตารางและรูปแบบเส้นขอบ

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## ขั้นตอนที่ 4: การนำเข้าข้อมูลจาก DataTable ลงในตาราง
เราใช้วิธี ImportDataTable เพื่อนำเข้าข้อมูลจาก DataTable ลงในตารางในเอกสาร PDF

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## ขั้นตอนที่ 5: การเพิ่มตารางลงในเอกสาร
เราเพิ่มตารางลงในคอลเลกชันย่อหน้าของหน้าเอกสาร

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## ขั้นตอนที่ 6: บันทึกเอกสาร
เราบันทึกเอกสาร PDF ด้วยข้อมูลจากฐานข้อมูลแบบฝัง

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

ยินดีด้วย! ตอนนี้คุณรู้วิธีฝังข้อมูลฐานข้อมูลลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET แล้ว

### ตัวอย่างซอร์สโค้ดสำหรับการผสานรวมกับฐานข้อมูลโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// เพิ่ม 2 แถวลงในวัตถุ DataTable โดยทางโปรแกรม
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
// ตั้งค่าสีเส้นขอบตารางเป็น LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// กำหนดเส้นขอบให้กับเซลล์ตาราง
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// เพิ่มวัตถุตารางลงในหน้าแรกของเอกสารอินพุต
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// บันทึกเอกสารที่อัปเดตซึ่งมีวัตถุตาราง
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีฝังข้อมูลจากฐานข้อมูลลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้คำแนะนำทีละขั้นตอนนี้เพื่อนำเข้าข้อมูลจากฐานข้อมูลของคุณเองและแสดงในเอกสาร PDF สำรวจเอกสารประกอบ Aspose.PDF เพิ่มเติมเพื่อค้นหาคุณสมบัติและความเป็นไปได้อื่นๆ ที่นำเสนอโดยไลบรารีอันทรงพลังนี้

### คำถามที่พบบ่อยสำหรับการบูรณาการกับฐานข้อมูลในรูปแบบไฟล์ PDF

#### ถาม: ฉันสามารถใช้ Aspose.PDF สำหรับ .NET กับฐานข้อมูลประเภทต่างๆ เช่น MySQL, SQL Server หรือ Oracle ได้หรือไม่

ตอบ: ได้ คุณสามารถใช้ Aspose.PDF สำหรับ .NET กับฐานข้อมูลประเภทต่างๆ เช่น MySQL, SQL Server, Oracle และอื่นๆ Aspose.PDF สำหรับ .NET มีฟังก์ชันในการอ่านข้อมูลจากแหล่งข้อมูลต่างๆ รวมถึงฐานข้อมูล ไฟล์ XML และอื่นๆ คุณสามารถดึงข้อมูลจากประเภทฐานข้อมูลที่คุณต้องการและเติมลงใน DataTable หรือโครงสร้างข้อมูลอื่นใดที่เข้ากันได้กับ Aspose.PDF สำหรับ .NET

#### ถาม: ฉันจะปรับแต่งลักษณะที่ปรากฏของตารางในเอกสาร PDF ได้อย่างไร

ตอบ: คุณสามารถปรับแต่งลักษณะที่ปรากฏของตารางในเอกสาร PDF ได้โดยใช้คุณสมบัติต่างๆ ที่ได้รับจากไลบรารี Aspose.PDF สำหรับ .NET ตัวอย่างเช่น คุณสามารถตั้งค่าลักษณะเส้นขอบ สีพื้นหลัง ลักษณะแบบอักษร และการจัดแนวที่แตกต่างกันสำหรับตารางและเซลล์ของตารางได้ โปรดดูเอกสารประกอบ Aspose.PDF สำหรับ .NET สำหรับรายละเอียดเพิ่มเติมเกี่ยวกับการปรับแต่งลักษณะที่ปรากฏของตาราง

#### ถาม: เป็นไปได้ไหมที่จะเพิ่มไฮเปอร์ลิงก์หรือองค์ประกอบเชิงโต้ตอบให้กับข้อมูลที่นำเข้าจากฐานข้อมูล

ตอบ: ได้ คุณสามารถเพิ่มไฮเปอร์ลิงก์หรือองค์ประกอบเชิงโต้ตอบอื่นๆ ลงในข้อมูลที่นำเข้าจากฐานข้อมูลได้ Aspose.PDF สำหรับ .NET รองรับการเพิ่มไฮเปอร์ลิงก์ บุ๊กมาร์ก และองค์ประกอบเชิงโต้ตอบอื่นๆ ลงในเอกสาร PDF คุณสามารถจัดการเนื้อหาใน DataTable ก่อนที่จะนำเข้าลงในตาราง และรวมไฮเปอร์ลิงก์หรือคุณลักษณะแบบโต้ตอบอื่นๆ ได้

#### ถาม: ฉันสามารถแบ่งหน้าตารางได้หรือไม่หากเกินจำนวนแถวที่กำหนด

 ตอบ: ได้ คุณสามารถแบ่งหน้าตารางได้หากเกินจำนวนแถวที่กำหนด เพื่อให้บรรลุเป้าหมายนี้ คุณสามารถใช้`IsInNewPage`คุณสมบัติของออบเจ็กต์แถวเพื่อระบุว่าหน้าใหม่ควรเริ่มต้นหลังจากแถวใดแถวหนึ่ง คุณสามารถคำนวณจำนวนแถวที่จะแสดงต่อหน้าและตั้งค่าได้`IsInNewPage` ทรัพย์สินตามนั้น

#### ถาม: ฉันจะส่งออกเอกสาร PDF ที่มีข้อมูลฐานข้อมูลแบบฝังไปยังรูปแบบไฟล์ต่างๆ เช่น DOCX หรือ XLSX ได้อย่างไร

ตอบ: Aspose.PDF สำหรับ .NET ช่วยให้คุณสามารถแปลงเอกสาร PDF เป็นรูปแบบไฟล์อื่นๆ ได้มากมาย รวมถึง DOCX (Microsoft Word) และ XLSX (Microsoft Excel) คุณสามารถใช้ไลบรารี Aspose.PDF สำหรับ .NET ร่วมกับไลบรารี Aspose อื่นๆ เช่น Aspose.Words และ Aspose.Cells เพื่อให้บรรลุเป้าหมายนี้ได้ ขั้นแรก บันทึกเอกสาร PDF ด้วยข้อมูลฐานข้อมูลแบบฝัง จากนั้นใช้ไลบรารี Aspose ที่เกี่ยวข้องเพื่อแปลงเป็นรูปแบบไฟล์ที่คุณต้องการ