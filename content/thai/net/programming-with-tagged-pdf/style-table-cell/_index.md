---
title: สไตล์ตารางเซลล์
linktitle: สไตล์ตารางเซลล์
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีจัดรูปแบบเซลล์ตารางใน PDF โดยใช้ Aspose.PDF สำหรับ .NET ด้วยบทช่วยสอนโดยละเอียดนี้ ปฏิบัติตามคำแนะนำเพื่อสร้างและจัดรูปแบบตาราง PDF ที่สวยงาม
type: docs
weight: 160
url: /th/net/programming-with-tagged-pdf/style-table-cell/
---
## การแนะนำ

การสร้างตาราง PDF ที่ดูเป็นมืออาชีพอาจเป็นเรื่องยาก แต่ด้วย Aspose.PDF สำหรับ .NET คุณสามารถทำได้อย่างง่ายดายอย่างน่าประหลาดใจ ไม่ว่าคุณจะต้องการกำหนดรูปแบบส่วนหัว ส่วนท้าย หรือเซลล์ตารางเฉพาะ ไลบรารีอันทรงพลังนี้มอบเครื่องมือทั้งหมดที่คุณต้องการเพื่อสร้างเอกสาร PDF ที่มีรูปแบบสวยงาม ในบทช่วยสอนนี้ เราจะแนะนำวิธีกำหนดรูปแบบเซลล์ตารางในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ไม่ต้องกังวล เราจะแบ่งทุกอย่างออกเป็นขั้นตอนที่ทำตามได้ง่าย

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกโค้ด ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. Aspose.PDF สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.PDF เวอร์ชันล่าสุดจาก[ที่นี่](https://releases.aspose.com/pdf/net/).
2. IDE (เช่น Visual Studio): ตั้งค่าสภาพแวดล้อมการพัฒนา .NET
3. ความรู้พื้นฐานในการเขียนโปรแกรม C#: ต้องมีความคุ้นเคยกับ C# เล็กน้อย
4.  ใบอนุญาต Aspose.PDF: รับใบอนุญาตชั่วคราวหรือเต็มรูปแบบเพื่อปลดล็อกคุณสมบัติทั้งหมดของไลบรารี คุณสามารถรับรุ่นทดลองใช้งานฟรีได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

## แพ็คเกจนำเข้า

ก่อนเริ่มต้น โปรดแน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นแล้ว คุณจะต้องมีสิ่งต่อไปนี้ในโครงการของคุณ:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

ตอนนี้ทุกอย่างพร้อมแล้ว มาดูคำแนะนำทีละขั้นตอนกันเลย!

เราจะสร้างตารางในเอกสาร PDF และกำหนดรูปแบบเซลล์ของตาราง แต่ละขั้นตอนจะอธิบายกระบวนการโดยละเอียด

## ขั้นตอนที่ 1: สร้างเอกสาร PDF ใหม่

 ขั้นตอนแรกคือการสร้างเอกสาร PDF ใหม่ ใน Aspose.PDF คุณสามารถเริ่มต้นเอกสาร PDF ใหม่ได้`Document` วัตถุซึ่งแสดงถึงไฟล์ PDF ของคุณ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร PDF ใหม่
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

ที่นี่ เราจะเริ่มต้นเอกสาร PDF และตั้งชื่อและภาษาของเอกสาร ซึ่งจะทำให้เอกสารของคุณมีโครงสร้างที่เหมาะสม ซึ่งเป็นสิ่งสำคัญสำหรับการปฏิบัติตามมาตรฐาน PDF/UA

## ขั้นตอนที่ 2: ตั้งค่าโครงสร้างตาราง

ตารางใน PDF ถูกกำหนดไว้ภายในองค์ประกอบโครงสร้าง มาสร้างตารางและกำหนดแถวและคอลัมน์ของตารางกัน

```csharp
// รับองค์ประกอบโครงสร้างราก
StructureElement rootElement = taggedContent.RootElement;

// สร้างองค์ประกอบโครงสร้างตาราง
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

ตอนนี้เราได้กำหนดส่วนหัวของตารางแล้ว (`TableTHeadElement`), ร่างกาย (`TableTBodyElement`) และเท้า (`TableTFootElement`) ส่วนต่างๆ คุณสามารถคิดถึงสิ่งเหล่านี้เป็นโครงร่างของตารางของคุณ

## ขั้นตอนที่ 3: กำหนดรูปแบบเซลล์ส่วนหัว

การกำหนดสไตล์เซลล์ส่วนหัวจะทำให้เซลล์โดดเด่นขึ้น ในที่นี้ เราจะใช้สีพื้นหลัง ขอบ และการจัดตำแหน่งข้อความ

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

ในขั้นตอนนี้ เราจะวนซ้ำเซลล์ส่วนหัวแต่ละเซลล์ โดยให้พื้นหลังเป็นสีเขียวเหลือง ขอบเป็นสีเทา และข้อความจัดชิดขวา คุณสามารถปรับคุณสมบัติเหล่านี้ให้ตรงกับการออกแบบที่คุณต้องการได้

## ขั้นตอนที่ 4: เติมเนื้อหาและจัดรูปแบบตัวตาราง

เนื้อหาตารางประกอบด้วยข้อมูลจริง ต่อไปนี้เป็นวิธีกำหนดรูปแบบเซลล์แต่ละเซลล์ด้วยระยะขอบ เส้นขอบ และการตั้งค่าข้อความที่เฉพาะเจาะจง

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 ในขั้นตอนนี้ เราจะเติมเนื้อหาตารางด้วยสี่แถว และจัดรูปแบบแต่ละเซลล์ด้วยพื้นหลังสีเหลืองและข้อความสีน้ำเงินตัวหนาตรงกลาง นอกจากนี้ เรายังใช้`MarginInfo`คลาสที่จะกำหนดการเติมรอบข้อความ

## ขั้นตอนที่ 5: ปรับแต่งส่วนท้าย

เพื่อให้ตารางมีโครงสร้างที่สมบูรณ์ เราจึงเพิ่มและกำหนดรูปแบบเซลล์ส่วนท้าย เช่นเดียวกับที่เราทำกับส่วนหัว

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

ส่วนท้ายกระดาษได้รับการออกแบบให้มีลักษณะคล้ายกับส่วนหัว ช่วยให้ผู้อ่านสามารถติดตามโครงสร้างของตารางได้ง่าย

## ขั้นตอนที่ 6: บันทึกและตรวจสอบเอกสาร PDF

สุดท้ายเราบันทึกเอกสาร PDF และตรวจสอบว่าสอดคล้องกับ PDF/UA หรือไม่

```csharp
// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "StyleTableCell.pdf");

// การตรวจสอบความสอดคล้องของ PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 เราบันทึก PDF และใช้`Validate` วิธีการเพื่อให้แน่ใจว่าเป็นไปตามมาตรฐานการเข้าถึง (สอดคล้องกับ PDF/UA)

## บทสรุป

การจัดรูปแบบตารางใน PDF โดยใช้ Aspose.PDF สำหรับ .NET นั้นทั้งทรงพลังและยืดหยุ่น ด้วยโค้ดเพียงไม่กี่บรรทัด คุณสามารถสร้างการออกแบบตารางแบบกำหนดเองที่จะทำให้เอกสาร PDF ของคุณโดดเด่นได้ ตั้งแต่การปรับแต่งขอบเซลล์และพื้นหลังไปจนถึงการรับรองความสอดคล้องในการเข้าถึง Aspose.PDF ช่วยให้คุณสร้างไฟล์ PDF ที่สวยงามได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### ฉันสามารถใช้รูปแบบที่แตกต่างกันกับเซลล์ตารางแต่ละเซลล์ได้หรือไม่  
ใช่ คุณสามารถกำหนดรูปแบบเซลล์แต่ละเซลล์ได้โดยปรับแต่ง`TableTDElement` คุณสมบัติ.

### ฉันจะรวมเซลล์ตารางได้อย่างไร  
 คุณสามารถใช้`ColSpan` และ`RowSpan` คุณสมบัติในการผสานเซลล์ในตาราง

### เป็นไปได้ไหมที่จะสร้างตารางที่สอดคล้องกับ PDF/UA?  
 ใช่ ตามที่แสดงในคู่มือนี้ คุณสามารถมั่นใจได้ว่าเอกสารของคุณเป็นไปตามมาตรฐาน PDF/UA โดยการตรวจสอบเอกสารของคุณโดยใช้`Validate` วิธี.

### ฉันสามารถใช้แบบอักษรที่แตกต่างกันในเซลล์ตารางได้หรือไม่  
 แน่นอน! คุณสามารถระบุแบบอักษรที่แตกต่างกันได้โดยใช้`TextState` วัตถุสำหรับแต่ละเซลล์

### ฉันจะดาวน์โหลด Aspose.PDF สำหรับ .NET ได้อย่างไร?  
 คุณสามารถดาวน์โหลดได้จาก[หน้าวางจำหน่าย](https://releases.aspose.com/pdf/net/).