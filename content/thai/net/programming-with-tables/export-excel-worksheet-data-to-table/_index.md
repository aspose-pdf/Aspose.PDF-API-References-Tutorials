---
title: การส่งออกข้อมูลแผ่นงาน Excel ไปยังตาราง
linktitle: การส่งออกข้อมูลแผ่นงาน Excel ไปยังตาราง
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: ส่งออกข้อมูลจากแผ่นงาน Excel ไปยังตาราง PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 70
url: /th/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีการส่งออกข้อมูลจากเวิร์กชีต Excel และสร้างตารางในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะอธิบายโค้ดต้นฉบับทีละขั้นตอนและอธิบายแต่ละส่วนอย่างละเอียด เมื่อจบบทช่วยสอนนี้ คุณจะสามารถสร้างไฟล์ PDF ที่มีตารางซึ่งประกอบด้วยข้อมูลจากเวิร์กชีต Excel ได้ มาเริ่มกันเลย!

## ความต้องการ
ก่อนที่เราจะเริ่ม โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio บนเครื่องของคุณ
- เพิ่มไลบรารี Aspose.PDF สำหรับ .NET ลงในโปรเจ็กต์ของคุณแล้ว

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน Visual Studio เพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET โดยคลิกขวาที่โปรเจ็กต์ของคุณใน Solution Explorer เลือก "จัดการแพ็คเกจ NuGet" และค้นหา "Aspose.PDF" ติดตั้งแพ็คเกจแล้วคุณก็พร้อมใช้งานได้เลย

## ขั้นตอนที่ 2: การโหลดแผ่นงาน Excel
ในขั้นตอนแรกของโค้ด เราจะกำหนดเส้นทางไปยังไดเร็กทอรีที่มีเอกสาร Excel แทนที่ "YOUR DOCUMENT DIRECTORY" ด้วยเส้นทางไดเร็กทอรีจริงที่ไฟล์ Excel ของคุณตั้งอยู่

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

ที่นี่ เราใช้ไลบรารี Aspose.Cells เพื่อโหลดเวิร์กบุ๊ก Excel อย่าลืมแทนที่ "newBook1.xlsx" ด้วยชื่อไฟล์ Excel ของคุณ

## ขั้นตอนที่ 3: การเข้าถึงแผ่นงาน
 ต่อไปเราต้องเข้าถึงเวิร์กชีตแรกในไฟล์ Excel เราทำสิ่งนี้โดยใช้`Worksheets` การรวบรวมของ`Workbook` วัตถุ.

```csharp
// การเข้าถึงแผ่นงานแรกในไฟล์ Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 หากไฟล์ Excel ของคุณมีเวิร์กชีตหลายแผ่น คุณสามารถเปลี่ยนค่าดัชนีได้`[0]` เพื่อเข้าถึงแผ่นงานอื่น

## ขั้นตอนที่ 4: การส่งออกข้อมูลไปยัง DataTable
 ตอนนี้เราจะส่งออกเนื้อหาของเวิร์กชีต Excel ไปยัง`DataTable` วัตถุ เราระบุช่วงของเซลล์ที่จะส่งออกโดยใช้`ExportDataTable` วิธี.

```csharp
// การส่งออกเนื้อหา 7 แถวและ 2 คอลัมน์เริ่มจากเซลล์ที่ 1 ไปยัง DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

ในตัวอย่างนี้ เราจะส่งออกแถวและคอลัมน์ทั้งหมดโดยเริ่มตั้งแต่เซลล์แรก (0, 0) จนถึงเซลล์สุดท้ายในเวิร์กชีต ตั้งค่าช่วงที่เหมาะสมตามความต้องการของคุณ

## ขั้นตอนที่ 5: การสร้างเอกสาร PDF
ตอนนี้เราจะสร้างเอกสาร PDF ใหม่โดยใช้ไลบรารี Aspose.PDF

```csharp
// สร้างอินสแตนซ์เอกสาร
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

นี่จะสร้างเอกสาร PDF เปล่าที่เราสามารถเพิ่มเนื้อหาได้

## ขั้นตอนที่ 6: การเพิ่มหน้าและตาราง
เพื่อแสดงข้อมูลในรูปแบบตาราง เราจำเป็นต้องเพิ่มหน้าและตารางลงในเอกสาร PDF

```csharp
// สร้างหน้าในอินสแตนซ์เอกสาร
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// สร้างวัตถุตาราง
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// เพิ่มวัตถุตารางในคอลเล็กชั่นย่อหน้าของส่วน
sec1.Paragraphs.Add(tab1);
```

ที่นี่ เราสร้างหน้าใหม่และอ็อบเจ็กต์ตาราง จากนั้นเพิ่มตารางลงในคอลเล็กชันย่อหน้าของหน้า

## ขั้นตอนที่ 7: การตั้งค่าคุณสมบัติตาราง
ก่อนที่จะนำเข้าข้อมูล เราจำเป็นต้องตั้งค่าคุณสมบัติบางอย่างของตาราง เช่น ความกว้างของคอลัมน์และเส้นขอบเซลล์เริ่มต้น

```csharp
// กำหนดความกว้างของคอลัมน์ของตาราง
tab1.ColumnWidths = "40 100 100";

// ตั้งค่าเส้นขอบเซลล์เริ่มต้นของตารางโดยใช้วัตถุ BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

ในตัวอย่างนี้ เราตั้งค่าความกว้างของคอลัมน์เป็น 40, 100 และ 100 หน่วย ปรับค่าตามข้อมูลของคุณ นอกจากนี้ เรายังตั้งค่าเส้นขอบเซลล์เริ่มต้นให้แสดงเส้นขอบทุกด้านของแต่ละเซลล์อีกด้วย

## ขั้นตอนที่ 8: การนำเข้าข้อมูลสู่ตาราง
 ตอนนี้เราจะนำเข้าข้อมูลจาก`DataTable` วัตถุลงในตารางโดยใช้`ImportDataTable` วิธี.

```csharp
// นำเข้าข้อมูลลงในวัตถุตารางจาก DataTable ที่สร้างขึ้นด้านบน
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 ที่นี่ เราจะระบุช่วงของแถวและคอลัมน์ที่จะนำเข้า ในตัวอย่างนี้ เราจะนำเข้าแถวและคอลัมน์ทั้งหมดจาก`dataTable` วัตถุ.

## ขั้นตอนที่ 9: การจัดรูปแบบตาราง
เพื่อปรับปรุงรูปลักษณ์ของตาราง เราสามารถจัดรูปแบบเซลล์หรือแถวเฉพาะได้ ในขั้นตอนนี้ เราจะจัดรูปแบบแถวแรกและแถวสลับของตาราง

```csharp
// รับแถวที่ 1 จากตาราง
Aspose.Pdf.Row row1 = tab1.Rows[0];

// จัดรูปแบบแถวแรก
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // ตั้งค่าสีพื้นหลังของเซลล์ในแถวแรก
     curCell.BackgroundColor = Color.Blue;// ตั้งค่าหน้าสำหรับเซลล์ในแถวแรก
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // ตั้งค่าสีตัวอักษรของเซลล์ในแถวแรก
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // ตั้งค่าการจัดตำแหน่งข้อความสำหรับเซลล์ในแถวแรก
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// รูปแบบแถวสลับ
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // ตั้งค่าสีพื้นหลังของเซลล์ในแถวสลับกัน
         curCell.BackgroundColor = Color.Gray;
        
         // ตั้งค่าสีข้อความของเซลล์ในแถวสลับกัน
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

ที่นี่ เราจะวนซ้ำผ่านเซลล์ในแถวแรกและตั้งค่าสีพื้นหลัง แบบอักษร สีแบบอักษร และการจัดตำแหน่งข้อความ จากนั้น เราจะวนซ้ำผ่านเซลล์ทั้งหมดในแถวสลับและตั้งค่าสีพื้นหลังและข้อความ

## ขั้นตอนที่ 10: บันทึกเอกสาร PDF
สุดท้ายเราบันทึกเอกสาร PDF ในตำแหน่งที่ระบุ

```csharp
// บันทึกไฟล์ PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางไดเรกทอรีและชื่อไฟล์ที่ต้องการสำหรับไฟล์ PDF เอาท์พุต

### ตัวอย่างโค้ดต้นฉบับสำหรับการส่งออกข้อมูลเวิร์กชีต Excel ไปยังตารางโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// การเข้าถึงแผ่นงานแรกในไฟล์ Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// การส่งออกเนื้อหา 7 แถวและ 2 คอลัมน์เริ่มจากเซลล์ที่ 1 ไปยัง DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// สร้างอินสแตนซ์เอกสาร
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// สร้างหน้าในอินสแตนซ์เอกสาร
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// สร้างวัตถุตาราง
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// เพิ่มวัตถุตารางในคอลเล็กชั่นย่อหน้าของส่วน
sec1.Paragraphs.Add(tab1);

// กำหนดความกว้างของคอลัมน์ของตาราง เราต้องระบุ ColumnCount ด้วยตนเอง
// เนื่องจากเวิร์กชีต Excel ปัจจุบันมีสามคอลัมน์ ดังนั้นเราจึงระบุจำนวนเท่ากัน
tab1.ColumnWidths = "40 100 100";

// ตั้งค่าเส้นขอบเซลล์เริ่มต้นของตารางโดยใช้วัตถุ BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// นำเข้าข้อมูลลงในวัตถุตารางจาก DataTable ที่สร้างขึ้นด้านบน
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// รับแถวที่ 1 จากตาราง
Aspose.Pdf.Row row1 = tab1.Rows[0];

// ทำซ้ำผ่านเซลล์ทั้งหมดในแถวที่ 1 และตั้งค่าสีพื้นหลังเป็นสีน้ำเงิน
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// ตั้งค่าพื้นหลังของเซลล์ทั้งหมดในแถวแรกของตาราง
	curCell.BackgroundColor = Color.Blue;
	// ตั้งค่าแบบอักษรสำหรับเซลล์แถวแรกในตาราง
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// ตั้งค่าสีแบบอักษรของเซลล์ทั้งหมดในแถวแรกของตาราง
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// ตั้งค่าการจัดตำแหน่งข้อความสำหรับเซลล์แถวที่ 1 เป็นศูนย์กลาง
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// ทำซ้ำผ่านเซลล์ทั้งหมดในแถวที่ 1 และตั้งค่าสีพื้นหลังเป็นสีน้ำเงิน
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// ตั้งค่าสีพื้นหลังของเซลล์ทั้งหมด ยกเว้นแถวที่ 1
		curCell.BackgroundColor = Color.Gray;
		// ตั้งค่าสีข้อความของเซลล์ทั้งหมด ยกเว้นแถวที่ 1
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// บันทึกไฟล์ PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการส่งออกข้อมูลจากเวิร์กชีต Excel ไปยังตาราง PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราได้กล่าวถึงกระบวนการทีละขั้นตอนในการโหลดเวิร์กชีต Excel การสร้างเอกสาร PDF การเพิ่มตาราง การนำเข้าข้อมูล และการจัดรูปแบบตาราง ขณะนี้ คุณสามารถสร้างไฟล์ PDF ที่มีตารางที่มีข้อมูล Excel ได้ด้วยโปรแกรม

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของการส่งออกข้อมูลเวิร์กชีต Excel ไปยังตาราง PDF คืออะไร

A: การส่งออกข้อมูลเวิร์กชีต Excel ไปยังตาราง PDF ช่วยให้คุณสามารถนำเสนอข้อมูลในรูปแบบที่มีโครงสร้างและเป็นระเบียบ ช่วยให้คุณสามารถสร้างไฟล์ PDF ที่มีตารางที่มีข้อมูลจากเวิร์กชีต Excel ทำให้แชร์และเก็บรักษาข้อมูลในรูปแบบเอกสารพกพาได้ง่ายขึ้น

#### ถาม: ฉันสามารถปรับแต่งลักษณะของตาราง PDF ได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งลักษณะของตาราง PDF ได้โดยใช้คุณสมบัติต่างๆ ที่ Aspose.PDF สำหรับ .NET จัดเตรียมไว้ให้ ในโค้ดต้นฉบับ C# ที่ให้มา คุณสามารถปรับเปลี่ยนความกว้างของคอลัมน์ ขอบเซลล์ การจัดตำแหน่งข้อความ สไตล์ฟอนต์ และอื่นๆ เพื่อให้เหมาะกับความต้องการเฉพาะของคุณ

#### ถาม: ฉันจะจัดการไฟล์ Excel ที่มีเวิร์กชีตหลายแผ่นได้อย่างไร

 A: ในโค้ด C# ที่ให้มา เราเข้าถึงเวิร์กชีตแรกในไฟล์ Excel โดยใช้ดัชนี`[0]` หากไฟล์ Excel ของคุณมีเวิร์กชีตหลายแผ่น คุณสามารถเข้าถึงเวิร์กชีตเหล่านั้นได้โดยเปลี่ยนค่าดัชนีให้เหมาะสม เช่น`[1]` สำหรับแผ่นงานที่สองหรือ`[2]` สำหรับแผ่นงานที่สาม

#### ถาม: ฉันสามารถใช้การจัดรูปแบบที่แตกต่างกันกับแถวหรือเซลล์เฉพาะในตาราง PDF ได้หรือไม่

A: ใช่ คุณสามารถใช้การจัดรูปแบบที่แตกต่างกันกับแถวหรือเซลล์เฉพาะในตาราง PDF ได้ ในโค้ดต้นฉบับ C# ที่ให้มา เราได้สาธิตวิธีการจัดรูปแบบแถวแรกและสลับแถวให้แตกต่างกันโดยการเปลี่ยนสีพื้นหลัง สไตล์แบบอักษร และสีแบบอักษร คุณสามารถใช้เทคนิคการจัดรูปแบบที่คล้ายคลึงกันกับแถวหรือเซลล์เฉพาะใดๆ ได้ตามต้องการ

#### ถาม: Aspose.PDF สำหรับ .NET เป็นไลบรารีเดียวเท่านั้นที่อนุญาตให้ส่งออกข้อมูล Excel ไปยังตาราง PDF หรือไม่

A: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพสำหรับการทำงานกับเอกสาร PDF ในแอปพลิเคชัน .NET แม้ว่าจะมีไลบรารีอื่นๆ ให้เลือกใช้ แต่ Aspose.PDF สำหรับ .NET นำเสนอคุณลักษณะและความสามารถที่หลากหลายสำหรับการสร้าง จัดการ และส่งออกไฟล์ PDF ที่มีตารางจากข้อมูล Excel ทำให้เป็นตัวเลือกยอดนิยมสำหรับงานประเภทนี้