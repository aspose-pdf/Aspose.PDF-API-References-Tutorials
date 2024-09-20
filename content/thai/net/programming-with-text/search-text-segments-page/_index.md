---
title: ค้นหาหน้าส่วนข้อความในไฟล์ PDF
linktitle: ค้นหาหน้าส่วนข้อความในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีค้นหาข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนโดยละเอียดนี้ แยกข้อความ วิเคราะห์ข้อความ และอื่นๆ อีกมากมาย
type: docs
weight: 470
url: /th/net/programming-with-text/search-text-segments-page/
---
## การแนะนำ

คุณเคยสงสัยไหมว่าจะค้นหาข้อความเฉพาะเจาะจงภายในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร คุณโชคดีแล้ว! ในคู่มือนี้ เราจะแนะนำคุณทีละขั้นตอนในรูปแบบง่ายๆ ไม่ว่าคุณจะพยายามดึงข้อมูล วิเคราะห์ข้อความ หรือเพียงแค่ค้นหาความซับซ้อนของการจัดการ PDF Aspose.PDF สำหรับ .NET ก็ช่วยคุณได้ มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม เรามาตรวจสอบกันก่อนว่าคุณมีทุกสิ่งที่คุณต้องการ:

-  Aspose.PDF สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารีแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/pdf/net/).
- .NET Framework: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET ไว้ในเครื่องของคุณแล้ว
- สภาพแวดล้อมการพัฒนา: แนะนำให้ใช้ Visual Studio หรือ IDE อื่น ๆ ที่รองรับ .NET
- เอกสาร PDF: ไฟล์ PDF ที่คุณจะค้นหาส่วนข้อความ

 หากคุณยังไม่มี Aspose.PDF สำหรับ .NET ไม่ต้องกังวล! คุณสามารถทดลองใช้งานฟรีได้จาก[ที่นี่](https://releases.aspose.com/) หรือซื้อมัน[ที่นี่](https://purchase.aspose.com/buy).

## แพ็คเกจนำเข้า

ก่อนที่เราจะเริ่มเขียนโค้ด สิ่งสำคัญคือการนำเข้าแพ็คเกจที่จำเป็นลงในโปรเจ็กต์ของคุณ ซึ่งจะทำให้แน่ใจว่าคลาสและวิธีการที่จำเป็นทั้งหมดพร้อมใช้งานสำหรับงานการจัดการ PDF ของคุณ

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

เมื่อสิ่งสำคัญพร้อมแล้ว มาดูคำแนะนำทีละขั้นตอนกันเลย


## ขั้นตอนที่ 1: โหลดเอกสาร PDF

ขั้นตอนแรกในกระบวนการคือโหลดไฟล์ PDF ของคุณลงในโปรแกรม หากไม่มีเอกสารที่โหลดไว้ ก็ไม่มีอะไรให้ค้นหาใช่ไหม คุณสามารถทำได้ดังนี้

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

- `dataDir` :ตัวแปรนี้เก็บเส้นทางไปยังไฟล์ PDF ของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมไดเร็กทอรีจริงที่จัดเก็บไฟล์ของคุณ
- `pdfDocument` : การใช้`Document` คลาสเราโหลด PDF เข้าไปในหน่วยความจำ

## ขั้นตอนที่ 2: ตั้งค่าการค้นหาข้อความ

 ตอนนี้เอกสารของคุณโหลดเสร็จแล้ว ขั้นตอนต่อไปคือการสร้าง`TextFragmentAbsorber` วัตถุที่ช่วยให้เราค้นหาข้อความเฉพาะภายในเอกสารได้

```csharp
// สร้างวัตถุ TextAbsorber เพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีการค้นหาอินพุต
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

- `TextFragmentAbsorber` :วัตถุนี้ใช้เพื่อบันทึกข้อความทั้งหมดที่คุณกำลังค้นหา แทนที่`"text"` ด้วยข้อความจริงที่คุณต้องการค้นหา

## ขั้นตอนที่ 3: ยอมรับตัวดูดซับสำหรับหน้าเฉพาะ

คุณอาจไม่ต้องการค้นหาเอกสาร PDF ทั้งหมด ในตัวอย่างนี้ เราจะจำกัดขอบเขตให้เหลือเฉพาะหน้าใดหน้าหนึ่ง

```csharp
// รับตัวดูดซับสำหรับทุกหน้า
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

- `pdfDocument.Pages[2]`: หมายถึงว่าเรากำลังค้นหาเฉพาะหน้าที่สองของเอกสารเท่านั้น คุณสามารถแก้ไขดัชนีเพื่อกำหนดเป้าหมายไปที่หน้าอื่นๆ ได้
- `Accept()` : วิธีการนี้จะช่วยให้`TextFragmentAbsorber` เพื่อประมวลผลข้อความภายในหน้าที่ระบุ

## ขั้นตอนที่ 4: แยกชิ้นส่วนข้อความ

หลังจากค้นหาในหน้าแล้ว เราจะแยกชิ้นส่วนข้อความที่พบออกมาไว้ในคอลเลกชัน

```csharp
// รับชิ้นส่วนข้อความที่แยกออกมา
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`:คอลเลกชันนี้เก็บตัวอย่างทั้งหมดของชิ้นส่วนข้อความที่พบในระหว่างกระบวนการค้นหา

## ขั้นตอนที่ 5: วนซ้ำผ่านส่วนข้อความและแยกข้อมูล

ตอนนี้ เรามาวนซ้ำผ่านแต่ละส่วนของข้อความและแยกรายละเอียด เช่น ตำแหน่ง แบบอักษร และสี

```csharp
// วนผ่านชิ้นส่วน
foreach (TextFragment textFragment in textFragmentCollection)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        Console.WriteLine("Text : {0} ", textSegment.Text);
        Console.WriteLine("Position : {0} ", textSegment.Position);
        Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
        Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
        Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
        Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
        Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
        Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
        Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
        Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
    }
}
```

- `foreach (TextFragment textFragment in textFragmentCollection)` : เราวนผ่านแต่ละ`TextFragment` ในคอลเลคชั่น
- `foreach (TextSegment textSegment in textFragment.Segments)`:ในแต่ละส่วนจะมีส่วนต่างๆ มากมาย เราจะวนซ้ำส่วนต่างๆ เหล่านี้เพื่อรวบรวมข้อมูลที่เกี่ยวข้องทั้งหมด
-  คุณสมบัติต่างๆของ`textSegment`:สิ่งเหล่านี้ให้ข้อมูลรายละเอียดเกี่ยวกับข้อความ เช่น ตำแหน่ง (X และ Y) รายละเอียดแบบอักษร ขนาด และสี

## ขั้นตอนที่ 6: แสดงผลลัพธ์

ในที่สุด เมื่อดึงข้อมูลทั้งหมดออกมาแล้ว ผลลัพธ์จะถูกพิมพ์ออกมาในคอนโซล ซึ่งจะช่วยให้คุณเห็นตำแหน่งที่แน่นอนของข้อความและรายละเอียดการจัดรูปแบบ

นี่คือตัวอย่างผลลัพธ์เพื่อความชัดเจน:

```
Text : text
Position : X: 45.0, Y: 75.0
XIndent : 45.0
YIndent : 75.0
Font - Name : Arial
Font - IsAccessible : True
Font - IsEmbedded : False
Font - IsSubset : False
Font Size : 12.0
Foreground Color : System.Drawing.Color [Black]
```

- เอาท์พุตนี้จะแจ้งตำแหน่งที่แน่นอนและข้อมูลการจัดรูปแบบของข้อความ "ข้อความ" บนหน้าที่ระบุ

## บทสรุป

และแล้วคุณก็รู้แล้ว! คุณเพิ่งเรียนรู้วิธีการค้นหาข้อความเฉพาะภายในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET กระบวนการนี้มีประโยชน์มากเมื่อต้องจัดการกับ PDF ขนาดใหญ่ ช่วยให้คุณสามารถระบุและแยกข้อความสำคัญได้อย่างมีประสิทธิภาพ ไม่ว่าจะเป็นการวิเคราะห์ข้อมูล การแยกข้อมูล หรือเพียงแค่การนำทางผ่านเอกสาร Aspose.PDF มอบเครื่องมืออันทรงพลังให้กับคุณเพื่อทำงานให้สำเร็จ

## คำถามที่พบบ่อย

### ฉันสามารถค้นหาคำหรือวลีหลายๆ คำได้ไหม
 ใช่ คุณสามารถปรับเปลี่ยนได้`TextFragmentAbsorber`เพื่อค้นหาข้อความอื่นโดยการเปลี่ยนสตริงอินพุต

### สามารถค้นหาข้ามหน้าหลายๆ หน้าได้หรือไม่?
 แน่นอน! คุณสามารถวนซ้ำหน้าต่างๆ ใน PDF ได้โดยการวนซ้ำ`pdfDocument.Pages`.

### ฉันจะค้นหาข้อความที่ไม่คำนึงถึงตัวพิมพ์ใหญ่-เล็กได้อย่างไร
 คุณสามารถใช้`TextSearchOptions` เพื่อเปิดใช้งานการค้นหาโดยไม่คำนึงถึงตัวพิมพ์ใหญ่หรือเล็ก

### ฉันสามารถแก้ไขได้หลังจากค้นหาเจอแล้วหรือไม่?
 ใช่ เมื่อคุณพบแล้ว`TextFragment`คุณสามารถปรับเปลี่ยนคุณสมบัติข้อความได้

### วิธีการนี้สามารถนำไปใช้กับ PDF ที่เข้ารหัสได้หรือไม่
ใช่ ตราบใดที่คุณปลดล็อค PDF โดยใช้รหัสผ่านที่ถูกต้อง