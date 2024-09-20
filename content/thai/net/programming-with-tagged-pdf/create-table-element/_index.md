---
title: สร้างองค์ประกอบตาราง
linktitle: สร้างองค์ประกอบตาราง
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: คู่มือทีละขั้นตอนในการสร้างองค์ประกอบอาร์เรย์ด้วย Aspose.PDF สำหรับ .NET สร้าง PDF แบบไดนามิกด้วยตารางได้อย่างง่ายดาย
type: docs
weight: 80
url: /th/net/programming-with-tagged-pdf/create-table-element/
---
## การแนะนำ

คุณเคยสงสัยไหมว่าคุณสามารถสร้างและปรับแต่งองค์ประกอบตารางใน PDF โดยใช้ .NET ได้อย่างไรอย่างง่ายดาย? Aspose.PDF สำหรับ .NET คือโซลูชันที่คุณต้องการ! ไม่ว่าคุณจะกำลังสร้างรายงานอัตโนมัติหรือสร้างตารางแบบไดนามิกสำหรับเอกสารต่างๆ Aspose.PDF ก็มี API ที่หลากหลายสำหรับทำงานกับองค์ประกอบตาราง คู่มือนี้จะแนะนำคุณทีละขั้นตอนในการสร้างตาราง ปรับแต่งรูปแบบ และแม้แต่ตรวจสอบว่าตารางนั้นตรงตามมาตรฐาน PDF/UA ฟังดูน่าตื่นเต้นใช่ไหม? มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น คุณจะต้องมีบางสิ่งบางอย่าง:
1.  Aspose.PDF สำหรับ .NET: ดาวน์โหลดเวอร์ชันล่าสุดได้จาก[ดาวน์โหลด Aspose.PDF สำหรับ .NET](https://releases.aspose.com/pdf/net/).
2. สภาพแวดล้อมการพัฒนา: IDE ที่รองรับ .NET ใดๆ (เช่น Visual Studio)
3. ความรู้พื้นฐานเกี่ยวกับ C#: แนะนำให้มีความคุ้นเคยกับการเขียนโปรแกรม C#

 สุดท้ายอย่าลืมใบอนุญาต Aspose.PDF ของคุณ หากคุณไม่มี คุณสามารถใช้ใบอนุญาตนี้ได้[ทดลองใช้งานฟรี](https://releases.aspose.com/) หรือร้องขอ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อทดสอบทุกสิ่งทุกอย่าง

## แพ็คเกจนำเข้า

ขั้นแรกเลยคือให้เราอิมพอร์ตแพ็คเกจที่จำเป็นก่อน วิธีนี้จะช่วยให้เราสามารถทำงานกับคลาสที่เกี่ยวข้องทั้งหมดเพื่อสร้างตารางในเอกสาร PDF ได้

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

ในส่วนนี้ เราจะแบ่งขั้นตอนการสร้างตารางออกเป็นหลายขั้นตอน โดยแต่ละขั้นตอนจะเน้นที่ส่วนต่างๆ ของกระบวนการสร้างและปรับแต่งตาราง

## ขั้นตอนที่ 1: สร้างเอกสาร PDF ใหม่

สิ่งแรกที่เราต้องทำคือสร้างเอกสาร PDF ใหม่ ซึ่งจะทำหน้าที่เป็นคอนเทนเนอร์สำหรับตารางของเรา

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร PDF ใหม่
Document document = new Document();
```

 ที่นี่ เรากำลังเริ่มต้นอินสแตนซ์ใหม่ของ`Document` คลาสนี้จะเป็นไฟล์ PDF เปล่าของเรา อย่าลืมกำหนดเส้นทางของไฟล์ด้วย!

## ขั้นตอนที่ 2: ตั้งค่าเนื้อหาที่ถูกแท็ก

ขั้นต่อไป เราต้องเปิดใช้งานเนื้อหาที่มีแท็ก ซึ่งจะทำให้ตารางสามารถเข้าถึงได้ PDF ที่มีแท็กเป็นสิ่งจำเป็นเพื่อให้เป็นไปตามมาตรฐาน PDF/UA (การเข้าถึงสากล)

```csharp
// เปิดใช้งานเนื้อหาที่แท็ก
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Table");
taggedContent.SetLanguage("en-US");
```

ขั้นตอนนี้จะกำหนดชื่อและภาษาของเอกสาร โดยให้แน่ใจว่าตารางเป็นไปตามมาตรฐานการเข้าถึง การมีเอกสารที่สามารถเข้าถึงได้ถือเป็นสิ่งสำคัญสำหรับประสบการณ์ของผู้ใช้และข้อกำหนดทางกฎหมายในบางอุตสาหกรรม

## ขั้นตอนที่ 3: สร้างองค์ประกอบตาราง

ตอนนี้มาถึงส่วนสนุก ๆ นั่นก็คือการสร้างตารางนั่นเอง!

```csharp
// รับองค์ประกอบโครงสร้างราก
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

 ที่นี่เราใช้`RootElement` ของเนื้อหาที่ถูกแท็กเพื่อผนวกตารางของเรา ซึ่งโดยพื้นฐานแล้วก็คือการเพิ่มตารางเป็นโหนดย่อยในโครงสร้างของเอกสาร

## ขั้นตอนที่ 4: ปรับแต่งขอบตารางและส่วนหัว

คุณคงไม่อยากให้โต๊ะของคุณดูจืดชืดใช่ไหม ลองเพิ่มสไตล์ให้โต๊ะดูบ้างดีกว่า!

```csharp
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

 เรากำลังกำหนดขอบเขตและเพิ่มส่วนหัว เนื้อหา และส่วนท้ายลงในตาราง โปรดสังเกตการใช้`BorderInfo` เพื่อตกแต่งขอบโต๊ะด้วยสีน้ำเงินเข้ม

## ขั้นตอนที่ 5: เพิ่มแถวและเซลล์ลงในตาราง

ตอนนี้เรามาเพิ่มแถวและเซลล์ลงในตารางกัน ขั้นตอนนี้เป็นขั้นตอนที่เราจะต้องกำหนดเค้าโครงของตาราง

### ขั้นตอนที่ 5.1: สร้างแถวส่วนหัว

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

 เรากำลังสร้างแถวส่วนหัวที่มี 4 คอลัมน์ และเซลล์ส่วนหัวแต่ละเซลล์ได้รับการออกแบบด้วยสีพื้นหลัง`GreenYellow`. เรายังกำหนดขอบและการจัดตำแหน่งให้กับส่วนหัวด้วย

### ขั้นตอนที่ 5.2: เพิ่มแถวเนื้อหา

```csharp
for (int rowIndex = 0; rowIndex < 50; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < 4; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Alignment = HorizontalAlignment.Center;
    }
}
```

ที่นี่ เรากำลังสร้างแถว 50 แถวและคอลัมน์ 4 คอลัมน์แบบไดนามิก โดยเติมข้อความและกำหนดรูปแบบเซลล์ สีพื้นหลังตั้งเป็นสีเหลือง โดยให้ข้อความอยู่ตรงกลาง

### ขั้นตอนที่ 5.3: เพิ่มแถวส่วนท้าย

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
    tdElement.Alignment = HorizontalAlignment.Center;
}
```

 เพื่อทำให้ตารางสมบูรณ์ เราจึงเพิ่มส่วนท้ายพร้อมข้อความตรงกลางและ`LightSeaGreen` พื้นหลัง

## ขั้นตอนที่ 6: ตรวจสอบการปฏิบัติตาม PDF/UA

เมื่อสร้างตารางแล้ว สิ่งสำคัญคือต้องแน่ใจว่า PDF สอดคล้องกับ PDF/UA

```csharp
document.Save(dataDir + "CreateTableElement.pdf");

// ตรวจสอบการปฏิบัติตาม PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

สไนปเป็ตนี้จะบันทึกไฟล์ PDF และตรวจสอบว่าเป็นไปตามมาตรฐาน PDF/UA หรือไม่ หากเอกสารเป็นไปตามมาตรฐาน ผู้ใช้ที่มีความทุพพลภาพจะสามารถเข้าถึงได้

## บทสรุป

ขอแสดงความยินดี! คุณได้สร้างตารางที่กำหนดเองได้อย่างสมบูรณ์ใน PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว ตั้งแต่การจัดรูปแบบตารางไปจนถึงการรับรองความสอดคล้องกับ PDF/UA ตอนนี้คุณมีพื้นฐานที่มั่นคงสำหรับการสร้างตารางแบบไดนามิกในเอกสาร PDF ของคุณแล้ว อย่าลืมสำรวจคุณสมบัติมากมายของ Aspose.PDF เพื่อปรับปรุงเอกสารของคุณให้ดียิ่งขึ้น!

## คำถามที่พบบ่อย

### ฉันสามารถปรับแต่งแบบอักษรและรูปแบบข้อความของตารางได้หรือไม่
ใช่ Aspose.PDF ช่วยให้คุณปรับแต่งแบบอักษร สไตล์ข้อความ และการจัดตำแหน่งได้อย่างเต็มที่โดยใช้`TextState` ระดับ.

### ฉันจะเพิ่มคอลัมน์หรือแถวเพิ่มเติมแบบไดนามิกได้อย่างไร
 คุณสามารถปรับจำนวนคอลัมน์หรือแถวได้โดยการแก้ไข`rowIndex` และ`colIndex` อยู่ในลูป

### สามารถรวมเซลล์ในตารางได้หรือไม่?
 ใช่คุณสามารถใช้`ColSpan` และ`RowSpan` คุณสมบัติในการผสานเซลล์ข้ามคอลัมน์หรือแถว

### การปฏิบัติตาม PDF/UA คืออะไร
การปฏิบัติตามมาตรฐาน PDF/UA ช่วยให้แน่ใจว่าผู้ใช้ที่มีความพิการสามารถเข้าถึงเอกสารได้ ซึ่งเป็นไปตามมาตรฐานการเข้าถึงระหว่างประเทศ

### ฉันจะทดสอบการปฏิบัติตามมาตรฐาน PDF/UA ใน Aspose.PDF ได้อย่างไร
 คุณสามารถใช้`Validate` วิธีการตรวจสอบว่าเอกสารเป็นไปตามมาตรฐาน PDF/UA หรือไม่