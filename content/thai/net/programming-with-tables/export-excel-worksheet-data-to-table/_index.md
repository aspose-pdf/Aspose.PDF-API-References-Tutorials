---
title: ส่งออกข้อมูลแผ่นงาน Excel ไปยังตาราง
linktitle: ส่งออกข้อมูลแผ่นงาน Excel ไปยังตาราง
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: ส่งออกข้อมูลจากแผ่นงาน Excel ไปยังตาราง PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 70
url: /th/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีส่งออกข้อมูลจากเวิร์กชีต Excel และสร้างตารางในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ดทีละขั้นตอนและอธิบายแต่ละส่วนโดยละเอียด เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถสร้างไฟล์ PDF พร้อมตารางที่มีข้อมูลจากแผ่นงาน Excel ได้ มาเริ่มกันเลย!

## ความต้องการ
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว
- Aspose.PDF สำหรับไลบรารี .NET ถูกเพิ่มในโครงการของคุณ

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน Visual Studio เพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET โดยการคลิกขวาที่โปรเจ็กต์ของคุณใน Solution Explorer เลือก "จัดการแพ็คเกจ NuGet" และค้นหา "Aspose.PDF" ติดตั้งแพ็คเกจและคุณพร้อมที่จะใช้งานแล้ว

## ขั้นตอนที่ 2: กำลังโหลดแผ่นงาน Excel
ในขั้นตอนแรกของโค้ด เราจะกำหนดเส้นทางไปยังไดเร็กทอรีที่มีเอกสาร Excel แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางไดเรกทอรีจริงที่มีไฟล์ Excel ของคุณ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

ที่นี่ เราใช้ไลบรารี Aspose.Cells เพื่อโหลดเวิร์กบุ๊ก Excel ตรวจสอบให้แน่ใจว่าได้แทนที่ "newBook1.xlsx" ด้วยชื่อไฟล์ Excel ของคุณ

## ขั้นตอนที่ 3: การเข้าถึงแผ่นงาน
 ต่อไปเราต้องเข้าถึงแผ่นงานแรกในไฟล์ Excel เราทำสิ่งนี้โดยใช้`Worksheets` คอลเลกชันของ`Workbook` วัตถุ.

```csharp
// การเข้าถึงแผ่นงานแรกในไฟล์ Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 หากไฟล์ Excel ของคุณมีหลายแผ่นงาน คุณสามารถเปลี่ยนค่าดัชนีได้`[0]` เพื่อเข้าถึงแผ่นงานอื่น

## ขั้นตอนที่ 4: การส่งออกข้อมูลไปยัง DataTable
 ตอนนี้ เราจะส่งออกเนื้อหาของแผ่นงาน Excel ไปที่`DataTable` วัตถุ. เราระบุช่วงของเซลล์ที่จะส่งออกโดยใช้`ExportDataTable` วิธี.

```csharp
// ส่งออกเนื้อหาของ 7 แถวและ 2 คอลัมน์โดยเริ่มจากเซลล์ที่ 1 ไปยัง DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

ในตัวอย่างนี้ เราส่งออกแถวและคอลัมน์ทั้งหมดโดยเริ่มจากเซลล์แรก (0, 0) ไปยังเซลล์สุดท้ายในเวิร์กชีต กำหนดช่วงที่เหมาะสมตามความต้องการของคุณ

## ขั้นตอนที่ 5: การสร้างเอกสาร PDF
ตอนนี้ เราจะสร้างเอกสาร PDF ใหม่โดยใช้ไลบรารี Aspose.PDF

```csharp
// สร้างอินสแตนซ์ของอินสแตนซ์เอกสาร
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

สิ่งนี้จะสร้างเอกสาร PDF เปล่าที่เราสามารถเพิ่มเนื้อหาได้

## ขั้นตอนที่ 6: การเพิ่มหน้าและตาราง
ในการแสดงข้อมูลในรูปแบบตาราง เราจำเป็นต้องเพิ่มหน้าและตารางลงในเอกสาร PDF

```csharp
// สร้างหน้าในอินสแตนซ์เอกสาร
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// สร้างวัตถุตาราง
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// เพิ่มวัตถุตารางในคอลเลกชันย่อหน้าของส่วน
sec1.Paragraphs.Add(tab1);
```

ที่นี่ เราสร้างหน้าใหม่และวัตถุตาราง จากนั้นเราเพิ่มตารางลงในคอลเลกชันย่อหน้าของหน้า

## ขั้นตอนที่ 7: การตั้งค่าคุณสมบัติของตาราง
ก่อนที่จะนำเข้าข้อมูล เราจำเป็นต้องตั้งค่าคุณสมบัติบางอย่างของตาราง เช่น ความกว้างของคอลัมน์และเส้นขอบเซลล์เริ่มต้น

```csharp
// กำหนดความกว้างของคอลัมน์ของตาราง
tab1.ColumnWidths = "40 100 100";

// ตั้งค่าเส้นขอบเซลล์เริ่มต้นของตารางโดยใช้วัตถุ BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

ในตัวอย่างนี้ เราตั้งค่าความกว้างของคอลัมน์เป็น 40, 100 และ 100 หน่วย ปรับค่าตามข้อมูลของคุณ นอกจากนี้เรายังตั้งค่าเส้นขอบเซลล์เริ่มต้นเพื่อแสดงเส้นขอบทุกด้านของแต่ละเซลล์

## ขั้นตอนที่ 8: การนำเข้าข้อมูลไปยังตาราง
 ตอนนี้เราจะนำเข้าข้อมูลจาก`DataTable` วัตถุลงในตารางโดยใช้`ImportDataTable` วิธี.

```csharp
// นำเข้าข้อมูลลงในวัตถุ Table จาก DataTable ที่สร้างขึ้นด้านบน
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 ที่นี่ เราระบุช่วงของแถวและคอลัมน์ที่จะนำเข้า ในตัวอย่างนี้ เรานำเข้าแถวและคอลัมน์ทั้งหมดจาก`dataTable` วัตถุ.

## ขั้นตอนที่ 9: การจัดรูปแบบตาราง
เพื่อปรับปรุงลักษณะที่ปรากฏของตาราง เราสามารถใช้การจัดรูปแบบกับเซลล์หรือแถวที่ต้องการได้ ในขั้นตอนนี้ เราจะจัดรูปแบบแถวแรกและแถวสลับกันของตาราง

```csharp
// รับแถวที่ 1 จากตาราง
Aspose.Pdf.Row row1 = tab1.Rows[0];

// จัดรูปแบบแถวแรก
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // กำหนดสีพื้นหลังของเซลล์ในแถวแรก
     curCell.BackgroundColor = Color.Blue;// กำหนดใบหน้าให้กับเซลล์ในแถวแรก
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // กำหนดสีแบบอักษรของเซลล์ในแถวแรก
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // ตั้งค่าการจัดแนวข้อความสำหรับเซลล์ในแถวแรก
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// รูปแบบแถวสลับกัน
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // กำหนดสีพื้นหลังของเซลล์ในแถวสลับกัน
         curCell.BackgroundColor = Color.Gray;
        
         // ตั้งค่าสีข้อความของเซลล์ในแถวสลับกัน
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

ที่นี่ เราวนซ้ำเซลล์ต่างๆ ในแถวแรก และตั้งค่าสีพื้นหลัง หน้าตาแบบอักษร สีแบบอักษร และการจัดแนวข้อความ จากนั้นเราวนซ้ำเซลล์ทั้งหมดในแถวสลับและตั้งค่าพื้นหลังและสีข้อความ

## ขั้นตอนที่ 10: บันทึกเอกสาร PDF
สุดท้าย เราจะบันทึกเอกสาร PDF ไปยังตำแหน่งที่ระบุ

```csharp
// บันทึก PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

ตรวจสอบให้แน่ใจว่าได้แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางไดเรกทอรีและชื่อไฟล์ที่ต้องการสำหรับไฟล์ PDF เอาท์พุต

### ตัวอย่างซอร์สโค้ดสำหรับส่งออกข้อมูลแผ่นงาน Excel ไปยังตารางโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// การเข้าถึงแผ่นงานแรกในไฟล์ Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// ส่งออกเนื้อหาของ 7 แถวและ 2 คอลัมน์โดยเริ่มจากเซลล์ที่ 1 ไปยัง DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// สร้างอินสแตนซ์ของอินสแตนซ์เอกสาร
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// สร้างหน้าในอินสแตนซ์เอกสาร
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// สร้างวัตถุตาราง
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// เพิ่มวัตถุตารางในคอลเลกชันย่อหน้าของส่วน
sec1.Paragraphs.Add(tab1);

// กำหนดความกว้างของคอลัมน์ของตาราง เราจำเป็นต้องระบุ ColumnCount ด้วยตนเอง
// เนื่องจากแผ่นงาน Excel ปัจจุบันมีสามคอลัมน์ ดังนั้นเราจึงระบุจำนวนเดียวกัน
tab1.ColumnWidths = "40 100 100";

// ตั้งค่าเส้นขอบเซลล์เริ่มต้นของตารางโดยใช้วัตถุ BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// นำเข้าข้อมูลลงในวัตถุ Table จาก DataTable ที่สร้างขึ้นด้านบน
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// รับแถวที่ 1 จากตาราง
Aspose.Pdf.Row row1 = tab1.Rows[0];

// วนซ้ำทุกเซลล์ในแถวที่ 1 และตั้งค่าสีพื้นหลังเป็นสีน้ำเงิน
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// ตั้งค่าพื้นหลังของเซลล์ทั้งหมดในแถวที่ 1 ของตาราง
	curCell.BackgroundColor = Color.Blue;
	// กำหนดลักษณะแบบอักษรสำหรับเซลล์ของแถวที่ 1 ในตาราง
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// ตั้งค่าสีแบบอักษรของเซลล์ทั้งหมดในแถวที่ 1 ของตาราง
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// ตั้งค่าการจัดแนวข้อความสำหรับเซลล์ของแถวที่ 1 ให้เป็นศูนย์กลาง
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// วนซ้ำทุกเซลล์ในแถวที่ 1 และตั้งค่าสีพื้นหลังเป็นสีน้ำเงิน
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// กำหนดสีพื้นหลังของเซลล์ทั้งหมดยกเว้นแถวที่ 1
		curCell.BackgroundColor = Color.Gray;
		// ตั้งค่าสีข้อความของเซลล์ทั้งหมดยกเว้นแถวที่ 1
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// บันทึก PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีส่งออกข้อมูลจากแผ่นงาน Excel ไปยังตาราง PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราได้กล่าวถึงกระบวนการทีละขั้นตอนในการโหลดแผ่นงาน Excel การสร้างเอกสาร PDF การเพิ่มตาราง การนำเข้าข้อมูล และการจัดรูปแบบตาราง ตอนนี้คุณสามารถสร้างไฟล์ PDF ด้วยตารางที่มีข้อมูล Excel โดยทางโปรแกรมได้

### คำถามที่พบบ่อย

#### ถาม: การส่งออกข้อมูลเวิร์กชีต Excel ไปยังตาราง PDF มีจุดประสงค์อะไร

ตอบ: การส่งออกข้อมูลเวิร์กชีต Excel ไปยังตาราง PDF ช่วยให้คุณสามารถนำเสนอข้อมูลในรูปแบบที่มีโครงสร้างและจัดระเบียบได้ ช่วยให้คุณสามารถสร้างไฟล์ PDF ด้วยตารางที่มีข้อมูลจากแผ่นงาน Excel ทำให้ง่ายต่อการแชร์และเก็บรักษาข้อมูลในรูปแบบเอกสารแบบพกพา

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของตาราง PDF ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของตาราง PDF ได้โดยใช้คุณสมบัติต่างๆ ที่ Aspose.PDF สำหรับ .NET มอบให้ ในซอร์สโค้ด C# ที่ให้มา คุณสามารถแก้ไขความกว้างของคอลัมน์ เส้นขอบเซลล์ การจัดตำแหน่งข้อความ รูปแบบแบบอักษร และอื่นๆ เพื่อให้เหมาะกับความต้องการเฉพาะของคุณ

#### ถาม: ฉันจะจัดการไฟล์ Excel ที่มีแผ่นงานหลายแผ่นได้อย่างไร

 ตอบ: ในโค้ด C# ที่ให้มา เราเข้าถึงเวิร์กชีตแรกในไฟล์ Excel โดยใช้ดัชนี`[0]` . หากไฟล์ Excel ของคุณมีหลายแผ่นงาน คุณสามารถเข้าถึงได้โดยการเปลี่ยนค่าดัชนีตามลำดับ เช่น`[1]` สำหรับแผ่นงานที่สองหรือ`[2]` สำหรับใบงานที่สาม

#### ถาม: ฉันสามารถใช้การจัดรูปแบบอื่นกับแถวหรือเซลล์ที่ระบุในตาราง PDF ได้หรือไม่

ตอบ: ได้ คุณสามารถใช้การจัดรูปแบบที่แตกต่างกันกับแถวหรือเซลล์ที่ต้องการในตาราง PDF ได้ ในซอร์สโค้ด C# ที่ให้มา เราได้สาธิตวิธีการจัดรูปแบบแถวแรกและสลับแถวให้แตกต่างกันโดยการเปลี่ยนสีพื้นหลัง ลักษณะแบบอักษร และสีแบบอักษร คุณสามารถใช้เทคนิคการจัดรูปแบบที่คล้ายกันกับแถวหรือเซลล์ที่ต้องการได้

#### ถาม: Aspose.PDF สำหรับ .NET เป็นไลบรารีเดียวที่อนุญาตให้ส่งออกข้อมูล Excel ไปยังตาราง PDF หรือไม่

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพสำหรับการทำงานกับเอกสาร PDF ในแอปพลิเคชัน .NET แม้ว่าอาจมีไลบรารีอื่นๆ ให้ใช้งาน แต่ Aspose.PDF สำหรับ .NET นำเสนอฟีเจอร์และความสามารถที่หลากหลายสำหรับการสร้าง จัดการ และส่งออกไฟล์ PDF ด้วยตารางจากข้อมูล Excel ทำให้เป็นตัวเลือกยอดนิยมสำหรับงานดังกล่าว