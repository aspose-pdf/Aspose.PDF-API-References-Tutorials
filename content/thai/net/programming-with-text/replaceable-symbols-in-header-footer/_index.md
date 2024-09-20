---
title: สัญลักษณ์ที่แทนที่ได้ในส่วนหัวส่วนท้าย
linktitle: สัญลักษณ์ที่แทนที่ได้ในส่วนหัวส่วนท้าย
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีใช้สัญลักษณ์ที่แทนที่ได้ในส่วนหัวและส่วนท้ายของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 320
url: /th/net/programming-with-text/replaceable-symbols-in-header-footer/
---
## การแนะนำ

เมื่อทำงานกับไฟล์ PDF คุณอาจต้องปรับแต่งส่วนหัวและส่วนท้ายด้วยเนื้อหาแบบไดนามิก เช่น หมายเลขหน้า ชื่อรายงาน หรือวันที่ที่สร้างขึ้น โชคดีที่ Aspose.PDF สำหรับ .NET ทำให้กระบวนการนี้ง่ายขึ้น ช่วยให้คุณสร้าง PDF ที่มีสัญลักษณ์ที่อัปเดตโดยอัตโนมัติในส่วนหัวและส่วนท้าย เช่น หมายเลขหน้าหรือรายละเอียดการสร้างรายงาน บทความนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอนในการแทนที่สัญลักษณ์ในส่วนหัวและส่วนท้ายโดยใช้ Aspose.PDF สำหรับ .NET ซึ่งไม่เพียงแต่จะง่ายแต่ยังมีประสิทธิภาพอย่างเหลือเชื่ออีกด้วย

## ข้อกำหนดเบื้องต้น

ก่อนจะดูรายละเอียดในคู่มือทีละขั้นตอน โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

-  Aspose.PDF สำหรับไลบรารี .NET –[ดาวน์โหลด](https://releases.aspose.com/pdf/net/) หรือรับ[ทดลองใช้งานฟรี](https://releases.aspose.com/).
- Visual Studio หรือ IDE C# ใด ๆ ที่ติดตั้งในระบบของคุณ
- ความรู้พื้นฐานเกี่ยวกับการพัฒนา C# และ .NET
-  ถูกต้อง[ใบอนุญาต](https://purchase.aspose.com/temporary-license/) สำหรับ Aspose.PDF หรือคุณสามารถใช้เวอร์ชันทดลองใช้ได้

## แพ็คเกจนำเข้า

ในการเริ่มต้น คุณต้องนำเข้าเนมสเปซที่จำเป็นซึ่งจะเปิดใช้งานฟังก์ชันการทำงานของ Aspose.PDF สำหรับ .NET ด้านล่างนี้คือการนำเข้าที่จำเป็น:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

สิ่งเหล่านี้มีความจำเป็นสำหรับการจัดการการสร้าง PDF การจัดการข้อความ และการจัดการส่วนหัว/ส่วนท้าย

มาแบ่งโค้ดตัวอย่างออกเป็นขั้นตอนที่เข้าใจง่ายกัน

## ขั้นตอนที่ 1: ตั้งค่าเอกสารและหน้า

ขั้นแรก เราต้องสร้างเอกสารใหม่และเพิ่มหน้าเข้าไป การทำเช่นนี้จะเป็นการวางรากฐานสำหรับการเพิ่มส่วนหัวและส่วนท้าย

```csharp
// ตั้งค่าไดเรกทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// เริ่มต้นวัตถุเอกสาร
Document doc = new Document();

// เพิ่มหน้าลงในเอกสาร
Page page = doc.Pages.Add();
```

 ที่นี่เราจะตั้งค่าเอกสาร PDF โดยใช้`Document` คลาสและการเพิ่มหน้าด้วย`doc.Pages.Add()`หน้าเพจนี้จะมีส่วนหัว ส่วนท้าย และเนื้อหาอื่นๆ

## ขั้นตอนที่ 2: กำหนดค่าระยะขอบหน้า

ต่อไปเราจะกำหนดระยะขอบให้กับหน้าเพื่อให้แน่ใจว่าเนื้อหาของเราจะไม่ไปจนชิดขอบเกินไป

```csharp
// กำหนดค่าระยะขอบ
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

 ที่นี่เราได้กำหนดระยะขอบด้านบน ด้านล่าง ด้านซ้าย และด้านขวาโดยใช้`MarginInfo` คลาสและนำมาประยุกต์ใช้กับหน้าเพจโดยใช้`page.PageInfo.Margin`.

## ขั้นตอนที่ 3: สร้างและกำหนดค่าส่วนหัว

ตอนนี้เรามาสร้างส่วนหัวและเพิ่มลงในหน้ากัน ส่วนหัวจะรวมชื่อและหัวเรื่องของรายงาน

```csharp
// สร้างส่วนหัว
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;

// ตั้งค่าระยะขอบส่วนหัว
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

// เพิ่มชื่อเรื่องลงในส่วนหัว
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t1);

// เพิ่มชื่อรายงานลงในส่วนหัว
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.FontSize = 12;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t2);
```

 เราได้เพิ่มสอง`TextFragment` วัตถุในส่วนหัว: หนึ่งอันสำหรับชื่อรายงานและอีกอันสำหรับชื่อรายงาน ข้อความจะถูกกำหนดรูปแบบโดยใช้`TextState` คุณสมบัติเช่นแบบอักษร ขนาด และการจัดตำแหน่ง

## ขั้นตอนที่ 4: สร้างและกำหนดค่าส่วนท้าย

ตอนนี้ถึงเวลาตั้งค่าส่วนท้ายซึ่งจะมีเนื้อหาแบบไดนามิกเช่น หมายเลขหน้าและวันที่สร้าง

```csharp
// สร้างส่วนท้าย
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;

// ตั้งค่าระยะขอบส่วนท้าย
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

// เพิ่มเนื้อหาส่วนท้าย
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("Report Name");
TextFragment t5 = new TextFragment("Page $p of $P");
```

ในส่วนท้าย เราใส่ส่วนต่างๆ สำหรับวันที่สร้าง ชื่อรายงาน และหมายเลขหน้าแบบไดนามิก (`$p` และ`$P` แสดงถึงหมายเลขหน้าปัจจุบันและจำนวนหน้าทั้งหมดตามลำดับ)

## ขั้นตอนที่ 5: สร้างตารางในส่วนท้าย

คุณสามารถเพิ่มองค์ประกอบที่ซับซ้อนมากขึ้น เช่น ตารางในส่วนท้ายเพื่อจัดระเบียบข้อมูลของคุณได้ดีขึ้น

```csharp
// สร้างตารางสำหรับส่วนท้าย
Table tab2 = new Table();
hfFoot.Paragraphs.Add(tab2);
tab2.ColumnWidths = "165 172 165";

// สร้างแถวและเซลล์สำหรับตาราง
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();

// ตั้งค่าการจัดตำแหน่งสำหรับแต่ละเซลล์
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;

// เพิ่มเนื้อหาลงในเซลล์ตาราง
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
```

บล็อกโค้ดนี้จะสร้างตาราง 3 คอลัมน์ในส่วนท้าย โดยแต่ละคอลัมน์จะมีข้อมูลที่แตกต่างกัน เช่น วันที่สร้าง ชื่อรายงาน และหมายเลขหน้า

## ขั้นตอนที่ 6: เพิ่มเนื้อหาลงในหน้า

นอกจากส่วนหัวและส่วนท้ายแล้ว คุณสามารถเพิ่มเนื้อหาลงในเนื้อหาของหน้า PDF ได้ด้วย โดยในที่นี้ เราจะเพิ่มตารางพร้อมข้อความตัวแทน

```csharp
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
page.Paragraphs.Add(table);

// เพิ่มเนื้อหาตาราง
for (int i = 0; i <= 10; i++)
{
    Row row = table.Rows.Add();
    for (int c = 0; c <= 2; c++)
    {
        Cell cell = row.Cells.Add("Content " + c);
        cell.Margin = new MarginInfo { Left = 30, Top = 10, Bottom = 10 };
    }
}
```

โค้ดนี้จะเพิ่มตารางง่าย ๆ ที่มีสามคอลัมน์ลงในเพจ คุณสามารถปรับเปลี่ยนให้เหมาะกับความต้องการเฉพาะของคุณได้

## ขั้นตอนที่ 7: บันทึก PDF

เมื่อตั้งค่าทุกอย่างเสร็จเรียบร้อยแล้ว ขั้นตอนสุดท้ายคือการบันทึกเอกสาร PDF ในตำแหน่งที่คุณต้องการ

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("Symbols replaced successfully in header and footer. File saved at " + dataDir);
```

 คุณระบุเส้นทางไฟล์และบันทึกเอกสารโดยใช้`doc.Save()`. เสร็จเรียบร้อย! คุณได้สร้าง PDF ที่มีส่วนหัวและส่วนท้ายที่กำหนดเองสำเร็จแล้ว

## บทสรุป

การแทนที่สัญลักษณ์ในส่วนหัวและส่วนท้ายโดยใช้ Aspose.PDF สำหรับ .NET นั้นไม่เพียงแต่ตรงไปตรงมาแต่ยังทรงพลังอีกด้วย โดยปฏิบัติตามคำแนะนำทีละขั้นตอนข้างต้น คุณสามารถปรับแต่ง PDF ของคุณได้อย่างง่ายดายด้วยเนื้อหาแบบไดนามิก เช่น หมายเลขหน้า ชื่อรายงาน และวันที่ วิธีนี้มีความยืดหยุ่นสูง ช่วยให้คุณสามารถแทรกตาราง ปรับการจัดรูปแบบ และควบคุมเค้าโครงให้เหมาะกับความต้องการเฉพาะของคุณได้

## คำถามที่พบบ่อย

### ฉันสามารถปรับแต่งแบบอักษรสำหรับส่วนหัวและส่วนท้ายได้หรือไม่  
ใช่ คุณสามารถปรับแต่งแบบอักษร ขนาด สี และรูปแบบของข้อความในส่วนหัวและส่วนท้ายได้อย่างเต็มที่

### ฉันจะเพิ่มรูปภาพลงในส่วนหัวและส่วนท้ายได้อย่างไร?  
 คุณสามารถใช้`ImageStamp` การแทรกภาพลงในส่วนหัวและส่วนท้ายของคุณ

### สามารถเพิ่มไฮเปอร์ลิงก์ในส่วนหัวหรือส่วนท้ายได้หรือไม่  
 ใช่คุณสามารถใช้`TextFragment` ด้วยไฮเปอร์ลิงก์โดยตั้งค่า`Hyperlink` คุณสมบัติ.

### ฉันสามารถใช้ส่วนหัวที่แตกต่างกันสำหรับหน้าคี่และหน้าคู่ได้หรือไม่  
ใช่ Aspose.PDF ช่วยให้คุณระบุส่วนหัวและส่วนท้ายที่ต่างกันสำหรับหน้าคี่และหน้าคู่ได้

### ฉันจะปรับตำแหน่งส่วนหัวและส่วนท้ายได้อย่างไร  
คุณสามารถปรับระยะขอบและคุณสมบัติการจัดตำแหน่งเพื่อควบคุมตำแหน่งส่วนหัวและส่วนท้ายได้