---
title: องค์ประกอบตารางสไตล์
linktitle: องค์ประกอบตารางสไตล์
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการสร้างและกำหนดรูปแบบองค์ประกอบตารางใน Aspose.PDF สำหรับ .NET พร้อมด้วยคำแนะนำทีละขั้นตอน การกำหนดรูปแบบแบบกำหนดเอง และการปฏิบัติตาม PDF/UA
type: docs
weight: 170
url: /th/net/programming-with-tagged-pdf/style-table-element/
---
## การแนะนำ

ในบทความนี้ เราจะเจาะลึกถึงวิธีการสร้างและกำหนดรูปแบบองค์ประกอบตารางโดยใช้ Aspose.PDF สำหรับ .NET คุณจะได้เรียนรู้วิธีการสร้างโครงสร้างตาราง การใช้รูปแบบที่กำหนดเอง และตรวจสอบความสอดคล้องของ PDF/UA ของเอกสารของคุณ เมื่ออ่านบทช่วยสอนนี้จบ คุณจะสามารถสร้างตารางที่ดูเป็นมืออาชีพใน PDF ได้อย่างง่ายดาย!

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน คุณจะต้องแน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. Visual Studio หรือ IDE ที่คล้ายกันติดตั้งบนเครื่องของคุณ
2. .NET Framework หรือ .NET Core SDK สำหรับการรันแอปพลิเคชัน
3.  ดาวน์โหลดและอ้างอิงไลบรารี Aspose.PDF สำหรับ .NET ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดเวอร์ชันล่าสุดได้จาก[ที่นี่](https://releases.aspose.com/pdf/net/).
4.  ใบอนุญาต Aspose ที่ถูกต้องหรือ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อปลดล็อคฟังก์ชั่นต่างๆ ของห้องสมุดได้อย่างเต็มรูปแบบ

## แพ็คเกจนำเข้า

ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นลงในโครงการของคุณ:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

เนมสเปซเหล่านี้ครอบคลุมการดำเนินการ PDF หลัก เนื้อหาที่แท็ก ตาราง และการจัดรูปแบบข้อความ

ตอนนี้เรามาอธิบายขั้นตอนการสร้างและกำหนดรูปแบบตารางใน Aspose.PDF กัน เราจะอธิบายแต่ละส่วนอย่างละเอียดเพื่อให้คุณทำตามได้

## ขั้นตอนที่ 1: สร้างเอกสาร PDF ใหม่และตั้งค่าเนื้อหาที่แท็ก

ในขั้นตอนแรกนี้ เราจะสร้างเอกสาร PDF เปล่าและตั้งค่าเนื้อหาที่แท็กไว้

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร PDF ใหม่
Document document = new Document();

// ตั้งค่าเนื้อหาที่แท็ก
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 เราเริ่มต้นด้วยการสร้างสิ่งใหม่`Document` วัตถุที่แสดงถึง PDF ของเรา`TaggedContent`วัตถุถูกใช้เพื่อจัดการโครงสร้างของเอกสารเพื่อให้เป็นไปตามมาตรฐานการเข้าถึง เรากำหนดชื่อและภาษาของเอกสารเพื่อให้แท็กได้อย่างเหมาะสม

## ขั้นตอนที่ 2: กำหนดองค์ประกอบราก

ต่อไปเราจะสร้างองค์ประกอบโครงสร้างรากซึ่งทำหน้าที่เป็นคอนเทนเนอร์สำหรับเนื้อหาทั้งหมดใน PDF ของเรา

```csharp
// รับองค์ประกอบโครงสร้างราก
StructureElement rootElement = taggedContent.RootElement;
```

 การ`RootElement` ทำหน้าที่เป็นคอนเทนเนอร์พื้นฐานสำหรับองค์ประกอบที่มีโครงสร้างทั้งหมด รวมถึงตารางของเรา ช่วยรักษาลำดับชั้นโครงสร้างของเอกสาร ซึ่งมีความสำคัญทั้งต่อการจัดระบบและการเข้าถึง

## ขั้นตอนที่ 3: สร้างและกำหนดรูปแบบองค์ประกอบตาราง

 ตอนนี้เมื่อองค์ประกอบรากถูกตั้งค่าแล้ว เราจะสร้าง`TableElement` และใช้สไตล์เช่นสีพื้นหลัง ขอบ และการจัดตำแหน่ง

```csharp
// สร้างองค์ประกอบโครงสร้างตาราง
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// จัดรูปแบบตาราง
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 เราสร้าง`TableElement` ซึ่งกำหนดโครงสร้างตารางของเรา`BackgroundColor`, `Border` , และ`Alignment` คุณสมบัติช่วยให้เราปรับแต่งลักษณะของตารางได้`Broken` คุณสมบัตินี้รับประกันว่าถ้าตารางแบ่งข้ามหน้า ตารางจะแบ่งตามแนวตั้งด้วย

## ขั้นตอนที่ 4: ตั้งค่าขนาดตารางและรูปแบบเซลล์

ในขั้นตอนนี้เราจะกำหนดจำนวนคอลัมน์ การเติมเซลล์ และคุณสมบัติตารางที่สำคัญอื่นๆ

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 เราระบุความกว้างของคอลัมน์เพื่อให้แน่ใจว่าแต่ละคอลัมน์ในตารางมีระยะห่างเท่ากัน`DefaultCellBorder`, `DefaultCellPadding` , และ`DefaultCellTextState` กำหนดรูปแบบเริ่มต้นให้กับเซลล์ รวมถึงเส้นขอบ การเติมสีข้อความ และขนาดแบบอักษร

## ขั้นตอนที่ 5: เพิ่มแถวที่ซ้ำกันและสไตล์ที่กำหนดเอง

นอกจากนี้เรายังสามารถกำหนดรูปแบบสำหรับการทำซ้ำแถวและองค์ประกอบตารางเฉพาะอื่นๆ เช่น ส่วนหัวและส่วนท้ายได้

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 การ`RepeatingRowsCount` เพื่อให้แน่ใจว่าสามแถวแรกจะทำซ้ำหากตารางครอบคลุมหลายหน้า เราตั้งค่า`RepeatingRowsStyle` เพื่อใช้สีพื้นหลังแบบกำหนดเองกับแถวเหล่านี้

## ขั้นตอนที่ 6: เพิ่มองค์ประกอบส่วนหัว ส่วนลำตัว และส่วนท้ายของตาราง

ตอนนี้มาสร้างส่วนหัว ส่วนเนื้อหา และส่วนท้ายของตาราง และใส่เนื้อหาลงไป

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// สร้างแถวส่วนหัว
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// เติมเนื้อหาตาราง
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 ตารางแบ่งออกเป็น 3 ส่วน คือ ส่วนหัว ส่วนลำตัว และส่วนท้าย ขั้นแรก เราจะสร้างแถวส่วนหัวโดยใช้`TableTHElement`และเพิ่มส่วนหัวคอลัมน์ จากนั้นเติมเนื้อหาในตารางด้วย`TableTDElement`โดยเติมแต่ละเซลล์ด้วยป้ายกำกับที่รวมตำแหน่งของเซลล์นั้นๆ ไว้

## ขั้นตอนที่ 7: บันทึกเอกสาร

สุดท้ายเราบันทึกเอกสาร PDF ลงในไดเร็กทอรีที่ระบุ

```csharp
// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "StyleTableElement.pdf");
```

ขั้นตอนนี้จะทำให้กระบวนการสร้างเอกสารเสร็จสิ้นโดยการบันทึกไฟล์ PDF ด้วยตารางสไตล์

## ขั้นตอนที่ 8: ตรวจสอบการปฏิบัติตาม PDF/UA

หลังจากบันทึกเอกสารแล้ว สิ่งสำคัญคือต้องตรวจสอบให้แน่ใจว่าเอกสารเป็นไปตามมาตรฐาน PDF/UA (การเข้าถึงสากล)

```csharp
// ตรวจสอบความสอดคล้องของ PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

ที่นี่ เราจะโหลดเอกสารใหม่และตรวจสอบความถูกต้องตามมาตรฐาน PDF/UA การปฏิบัติตามข้อกำหนดจะช่วยให้ PDF ของคุณตรงตามข้อกำหนดการเข้าถึง ทำให้เหมาะสำหรับผู้ใช้หลากหลายกลุ่ม

## บทสรุป

ด้วย Aspose.PDF สำหรับ .NET การสร้างและกำหนดรูปแบบตารางในเอกสาร PDF ของคุณนั้นง่ายและใช้งานง่าย ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถสร้างตารางที่มีรูปแบบที่กำหนดเองได้และรับรองว่า PDF ของคุณเป็นไปตามมาตรฐานการเข้าถึง ไม่ว่าคุณจะกำลังสร้างรายงานหรือสร้างเอกสารที่มีโครงสร้าง ตารางเป็นเครื่องมือที่มีประสิทธิภาพสำหรับการนำเสนอข้อมูลอย่างชัดเจน

## คำถามที่พบบ่อย

### ฉันสามารถเพิ่มรูปภาพภายในเซลล์ตารางได้หรือไม่
 ใช่ คุณสามารถแทรกภาพลงในเซลล์ตารางได้โดยใช้`Image` องค์ประกอบ.

### ฉันจะปรับความกว้างของคอลัมน์แบบไดนามิกได้อย่างไร
 คุณสามารถตั้งค่าได้`ColumnAdjustment` ทรัพย์สินที่จะ`AutoFitToWindow` เพื่อปรับความกว้างของคอลัมน์โดยอัตโนมัติตามเนื้อหา

### การปฏิบัติตาม PDF/UA บังคับใช้กับเอกสารทั้งหมดหรือไม่
แม้ว่าจะไม่บังคับ แต่ขอแนะนำให้ใช้สำหรับเอกสารที่ต้องมีมาตรฐานการเข้าถึงสูง

### ฉันสามารถใช้รูปแบบที่แตกต่างกันกับแถวเฉพาะเจาะจงได้ไหม
 ใช่ คุณสามารถปรับแต่งแถวหรือเซลล์แต่ละแถวได้โดยการปรับ`TextState` หรือ`BackgroundColor`.

### ประโยชน์ของการใช้เนื้อหาที่ถูกแท็กคืออะไร
เนื้อหาที่แท็กช่วยปรับปรุงการเข้าถึงเอกสารและช่วยให้มั่นใจได้ว่าเป็นไปตามมาตรฐานเช่น PDF/UA