---
title: แท็ก HTML ภายในตารางในไฟล์ PDF
linktitle: แท็ก HTML ภายในตารางในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีใช้แท็ก HTML ภายในตารางในไฟล์ PDF ด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 100
url: /th/net/programming-with-tables/html-tags-inside-table/
---
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีใช้แท็ก HTML ภายในตารางในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ดใน C# ทีละขั้นตอน ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีแทรกเนื้อหา HTML ลงในตารางในเอกสาร PDF เริ่มกันเลย!

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ตรวจสอบให้แน่ใจว่าคุณได้กำหนดค่าสภาพแวดล้อมการพัฒนา C# ของคุณด้วย Aspose.PDF สำหรับ .NET เพิ่มการอ้างอิงไปยังไลบรารีและนำเข้าเนมสเปซที่จำเป็น

## ขั้นตอนที่ 2: การสร้างข้อมูลตาราง
เราสร้าง DataTable ที่มีคอลัมน์ "data" ประเภท String จากนั้นเราเพิ่มแถวลงใน DataTable นี้โดยใช้เนื้อหา HTML

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## ขั้นตอนที่ 3: การสร้างเอกสารและตาราง
เราสร้างเอกสาร PDF ใหม่และเพิ่มหน้าในเอกสารนี้ ต่อไป เราจะเริ่มต้นอินสแตนซ์ของคลาส Table และตั้งค่าคุณสมบัติของตาราง

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## ขั้นตอนที่ 4: การนำเข้าข้อมูลลงในตาราง
เรานำเข้าข้อมูลจาก DataTable ลงในตารางโดยใช้วิธี "ImportDataTable" เราระบุพารามิเตอร์วิธีการเพื่อระบุช่วงของแถวและคอลัมน์ของ DataTable ที่ควรนำเข้า

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## ขั้นตอนที่ 5: การเพิ่มตารางลงในเอกสาร
เราเพิ่มตารางลงในหน้าเอกสาร

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## ขั้นตอนที่ 6: บันทึกเอกสาร
เราบันทึกเอกสาร PDF ด้วยตารางที่มีเนื้อหา HTML

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับแท็ก HTML ภายในตารางโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// เริ่มต้นอินสแตนซ์ใหม่ของตาราง
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//กำหนดความกว้างของคอลัมน์ของตาราง
tableProvider.ColumnWidths = "400 50 ";
// ตั้งค่าสีเส้นขอบตารางเป็น LightGray
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// กำหนดเส้นขอบให้กับเซลล์ตาราง
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้แท็ก HTML ภายในตารางในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้คำแนะนำทีละขั้นตอนนี้เพื่อแทรกเนื้อหา HTML ลงในเซลล์ตารางในเอกสาร PDF โดยใช้ C#

### คำถามที่พบบ่อยสำหรับแท็ก HTML ภายในตารางในไฟล์ PDF

#### ถาม: ฉันสามารถใช้แท็ก HTML และคุณลักษณะอื่นๆ ภายในเซลล์ตารางได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้แท็ก HTML และคุณลักษณะต่างๆ ภายในเซลล์ตารางได้ เช่น`<b>`, `<i>`, `<a>`และอื่น ๆ อีกมากมาย. Aspose.PDF สำหรับ .NET รองรับองค์ประกอบและสไตล์ HTML มากมายที่คุณสามารถใช้เพื่อจัดรูปแบบเนื้อหาภายในเซลล์ตาราง

#### ถาม: ฉันสามารถใช้สไตล์ CSS กับเนื้อหา HTML ภายในเซลล์ตารางได้หรือไม่

ตอบ: ได้ คุณสามารถใช้สไตล์ CSS กับเนื้อหา HTML ภายในเซลล์ตารางได้ Aspose.PDF สำหรับ .NET ให้การสนับสนุนสไตล์ CSS พื้นฐานที่สามารถนำไปใช้กับองค์ประกอบ HTML ได้

#### ถาม: เป็นไปได้ไหมที่จะเพิ่มรูปภาพพร้อมกับเนื้อหา HTML ภายในเซลล์ตาราง

 ตอบ: ได้ คุณสามารถเพิ่มรูปภาพพร้อมกับเนื้อหา HTML ภายในเซลล์ตารางได้ คุณสามารถใช้ HTML`<img>` แท็กเพื่อรวมรูปภาพจากแหล่งต่างๆ เช่น ไฟล์ในเครื่องหรือ URL

#### ถาม: ฉันจะระบุความกว้างของคอลัมน์ที่แตกต่างกันสำหรับตารางได้อย่างไร

 ตอบ: คุณสามารถระบุความกว้างของคอลัมน์ที่แตกต่างกันสำหรับตารางได้โดยใช้`ColumnWidths` คุณสมบัติของตาราง คุณสมบัติรับสตริงที่มีค่าที่คั่นด้วยช่องว่าง โดยแต่ละค่าแสดงถึงความกว้างของคอลัมน์เป็นจุด

#### ถาม: ฉันสามารถใช้ตารางที่ซ้อนกันภายในเซลล์ที่มีเนื้อหา HTML ได้หรือไม่

ตอบ: ได้ คุณสามารถใช้ตารางที่ซ้อนกันภายในเซลล์ที่มีเนื้อหา HTML ได้ คุณสามารถสร้างอินสแตนซ์ตารางแยกกันและเพิ่มเป็นส่วนหนึ่งของเนื้อหา HTML ภายในเซลล์เพื่อให้ได้เอฟเฟกต์แบบซ้อน