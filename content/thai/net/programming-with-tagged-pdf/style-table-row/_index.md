---
title: สไตล์แถวตาราง
linktitle: สไตล์แถวตาราง
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีกำหนดรูปแบบแถวตารางใน PDF โดยใช้ Aspose.PDF สำหรับ .NET พร้อมด้วยคำแนะนำทีละขั้นตอนเพื่อปรับปรุงการจัดรูปแบบเอกสารของคุณได้อย่างง่ายดาย
type: docs
weight: 180
url: /th/net/programming-with-tagged-pdf/style-table-row/
---
## การแนะนำ

เมื่อต้องสร้างเอกสาร PDF ที่มีโครงสร้างดีและจัดรูปแบบสวยงาม Aspose.PDF สำหรับ .NET คือโซลูชันที่คุณควรเลือกใช้ ไม่ว่าคุณจะกำลังสร้างรายงาน ใบแจ้งหนี้ หรือสร้างตารางแบบไดนามิก การจัดรูปแบบตารางด้วยรูปแบบต่างๆ ถือเป็นกุญแจสำคัญในการสร้างเอกสารที่สวยงาม ในบทช่วยสอนนี้ เราจะเจาะลึกเกี่ยวกับการจัดรูปแบบแถวตารางโดยใช้ Aspose.PDF สำหรับ .NET และไม่ต้องกังวล ฉันจะแนะนำคุณทีละขั้นตอนเหมือนกับการสนทนาดีๆ ระหว่างดื่มกาแฟ!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะลงรายละเอียด เรามาตรวจสอบกันก่อนว่าคุณจัดการทุกอย่างเรียบร้อยแล้ว คุณจะต้องมี:

1. Aspose.PDF สำหรับไลบรารี .NET  
    หากคุณยังไม่มี คุณสามารถคว้ามันได้จาก[ที่นี่](https://releases.aspose.com/pdf/net/) . คุณยังสามารถรับได้[ทดลองใช้งานฟรี](https://releases.aspose.com/) เพื่อเริ่มต้น
2. สภาพแวดล้อมการพัฒนา  
   ตั้งค่า Visual Studio หรือ IDE C# ใดๆ ตามที่คุณต้องการ คุณจะต้องติดตั้ง .NET ด้วย แต่ฉันเดาว่าคุณคงคุ้นเคยกับสิ่งนั้นอยู่แล้ว
3. ความรู้พื้นฐานเกี่ยวกับ C# และ .NET  
   ความเข้าใจที่ดีเกี่ยวกับ C# จะทำให้บทช่วยสอนนี้เป็นเรื่องง่าย แต่ไม่ต้องกังวล ฉันจะอธิบายแต่ละขั้นตอนอย่างละเอียด!

## แพ็คเกจนำเข้า

ก่อนที่เราจะเริ่มทำงานกับ Aspose.PDF เราจะต้องนำเข้าเนมสเปซที่จำเป็น ในโปรเจ็กต์ C# ของคุณ โปรดแน่ใจว่าคุณได้รวมสิ่งต่อไปนี้:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

สิ่งเหล่านี้มีความจำเป็นในการสร้างและกำหนดรูปแบบตาราง และแน่นอนว่าจำเป็นต่อการทำงานกับเนื้อหาที่แท็กเพื่อให้เป็นไปตามข้อกำหนด

ตอนนี้มาแบ่งงานออกเป็นขั้นตอนทีละขั้นตอนเพื่อให้คุณสามารถจัดรูปแบบแถวตารางของคุณได้อย่างมืออาชีพ!

## ขั้นตอนที่ 1: สร้างเอกสาร PDF ใหม่

ขั้นแรก: มาสร้างเอกสาร PDF ใหม่กันก่อน เอกสารนี้จะมีแถวตารางที่จัดรูปแบบไว้ทั้งหมด

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร
Document document = new Document();
```

 ที่นี่เราเพียงแค่กำลังเริ่มต้นสิ่งใหม่`Document` วัตถุที่จะแทนไฟล์ PDF ของเรา ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าเส้นทางไดเรกทอรีที่คุณจะบันทึกไฟล์เอาต์พุตของคุณ

## ขั้นตอนที่ 2: ทำงานกับเนื้อหาที่มีแท็ก

เราจะใช้เนื้อหาที่มีแท็กเพื่อสร้างโครงสร้าง PDF ของคุณให้เข้าถึงได้ง่าย ซึ่งจะช่วยสร้างองค์ประกอบที่มีโครงสร้าง เช่น ตาราง และทำให้มั่นใจว่าองค์ประกอบเหล่านั้นสอดคล้องกับมาตรฐานการเข้าถึง เช่น PDF/UA

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

ที่นี่ เราจะตั้งชื่อและภาษาสำหรับเนื้อหาที่แท็กใน PDF เหมือนกับการตั้งชื่อ PDF และบอกว่าควรใช้ภาษาอะไร!

## ขั้นตอนที่ 3: กำหนดโครงสร้างตาราง

ต่อไป เราจะมากำหนดโครงสร้างของตารางที่เรากำลังจะสร้าง ตารางทุกตารางต้องมีส่วนหัว เนื้อหา และส่วนท้าย เช่นเดียวกับโพสต์บล็อกที่จัดระบบอย่างดี!

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

สิ่งที่เรากำลังทำที่นี่คือการสร้างตารางที่มีส่วนหัว (`THead`), ร่างกาย (`TBody`) และส่วนท้าย (`TFoot`) องค์ประกอบเหล่านี้จะยึดแถวของเรา

## ขั้นตอนที่ 4: เพิ่มแถวส่วนหัวตาราง

ตารางที่ไม่มีส่วนหัวก็เหมือนหนังสือที่ไม่มีชื่อเรื่อง เรามาสร้างแถวส่วนหัวก่อนเพื่อให้ข้อมูลมีบริบท

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

ที่นี่ เราวนซ้ำและเพิ่มเซลล์ส่วนหัวสามเซลล์ (`TableTHElement`โดยให้แต่ละข้อมีคำอธิบายประกอบ ง่ายใช่ไหม?

## ขั้นตอนที่ 5: เพิ่มแถวเนื้อหาที่มีสไตล์

ตอนนี้มาถึงส่วนที่สนุกแล้ว – การกำหนดสไตล์ให้กับแถว! มาสร้างแถว 7 แถวพร้อมสไตล์ที่กำหนดเองกัน เราจะตั้งค่าสีพื้นหลัง ขอบ ระยะห่าง และการจัดแนวข้อความ

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- สีพื้นหลัง: เราใช้สีเหลืองทองอ่อนๆ เพื่อให้ดูเป็นมืออาชีพแต่ก็ยังดูอบอุ่น
- ขอบ: แต่ละแถวจะมีขอบด้านนอกสีเทาเข้มและขอบเซลล์สีน้ำเงินเพื่อให้ดูคมชัด
- ความสูงและการเติม: ความสูงของแถวได้รับการกำหนดแล้ว และเพิ่มการเติมเพื่อให้ดูสะอาดตา
- การแบ่งหน้า: เพื่อให้ตารางอ่านได้ง่ายขึ้น ทุกๆ แถวที่สองจะเริ่มต้นจากหน้าใหม่

## ขั้นตอนที่ 6: เพิ่มแถวส่วนท้าย

ส่วนท้ายของตารางจะทำหน้าที่ยึดตารางไว้เช่นเดียวกับส่วนหัว มาสร้างส่วนท้ายกัน

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

เราเพียงแค่วนซ้ำผ่านเซลล์ส่วนท้ายสามเซลล์และเพิ่มข้อความเล็กน้อย ข้อความทางเลือกสำหรับส่วนท้ายคือ "Foot Row" เพื่อให้เข้าถึงได้

## ขั้นตอนที่ 7: บันทึกเอกสาร PDF

ตอนนี้โต๊ะพร้อมแล้ว ถึงเวลาบันทึกผลงานชิ้นเอกของคุณ!

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

เพียงเท่านี้ PDF ของคุณก็จะถูกบันทึกพร้อมกับแถวตารางสวยงามทั้งหมดที่เราเพิ่งจัดรูปแบบไว้

## ขั้นตอนที่ 8: ตรวจสอบการปฏิบัติตาม PDF/UA

เพื่อให้แน่ใจว่า PDF ของเราเป็นไปตามมาตรฐานการเข้าถึง เราจะตรวจสอบว่าเป็นไปตาม PDF/UA หรือไม่

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

วิธีนี้จะช่วยให้มั่นใจว่า PDF ของคุณเป็นไปตามมาตรฐาน PDF/UA ทำให้ทุกคนเข้าถึงได้ การเข้าถึงได้คือสิ่งสำคัญ!

## บทสรุป

และแล้วคุณก็จะมีมัน! ด้วยโค้ดเพียงไม่กี่บรรทัด คุณก็สามารถสร้างตารางที่มีรูปแบบครบถ้วนใน PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้ ตั้งแต่ส่วนหัวไปจนถึงส่วนท้าย เราได้กำหนดรูปแบบให้กับแต่ละแถว เพิ่มองค์ประกอบการเข้าถึง และแม้แต่ตรวจสอบเอกสารเพื่อให้เป็นไปตามข้อกำหนด ไม่ว่าคุณจะกำลังทำงานกับรายงานขององค์กร การนำเสนอ หรือเพียงแค่สนุกสนานกับ PDF คู่มือนี้ครอบคลุมทุกสิ่งที่คุณต้องการ ตอนนี้ เริ่มกำหนดรูปแบบตารางของคุณอย่างมืออาชีพได้เลย!

## คำถามที่พบบ่อย

### ฉันสามารถเปลี่ยนรูปแบบอักษรของตารางได้หรือไม่  
 ใช่! คุณสามารถปรับเปลี่ยนรูปแบบตัวอักษรได้โดยใช้`TextState` วัตถุสำหรับแต่ละเซลล์ซึ่งช่วยให้ปรับแต่งได้เต็มที่

### ฉันจะเพิ่มคอลัมน์เพิ่มเติมในตารางของฉันได้อย่างไร  
 เพียงแค่ปรับ`colCount`ตัวแปรและเพิ่มเซลล์เพิ่มเติมในลูปสำหรับส่วนหัว เนื้อหา และส่วนท้าย

### จะเกิดอะไรขึ้นถ้าฉันไม่ตั้งค่าความสูงของแถว?  
หากคุณไม่ได้ตั้งค่าความสูงของแถว ตารางจะปรับตามเนื้อหาโดยอัตโนมัติ

### ฉันสามารถใช้สิ่งนี้สำหรับจำนวนแถวแบบไดนามิกได้หรือไม่  
แน่นอน! คุณสามารถดึงข้อมูลจากฐานข้อมูลหรือแหล่งอื่น ๆ และปรับจำนวนแถวและคอลัมน์แบบไดนามิกได้

### Aspose.PDF สำหรับ .NET ใช้ได้ฟรีหรือไม่?  
 Aspose.PDF สำหรับ .NET เป็นผลิตภัณฑ์ที่ได้รับอนุญาต แต่คุณสามารถลองใช้ได้โดยใช้[ทดลองใช้งานฟรี](https://releases.aspose.com/) หรือรับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).