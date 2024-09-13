---
title: แยกคอลัมน์ข้อความในไฟล์ PDF
linktitle: แยกคอลัมน์ข้อความในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการแยกข้อความในคอลัมน์ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 150
url: /th/net/programming-with-text/extract-columns-text/
---
บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับกระบวนการแยกข้อความในคอลัมน์ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ติดตั้งอยู่บนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose อย่างเป็นทางการหรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการแยกข้อความในคอลัมน์ ให้เพิ่มคำสั่ง using ต่อไปนี้ที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเรกทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณเก็บเอกสารไว้

## ขั้นตอนที่ 4: เปิดเอกสาร PDF
 เปิดเอกสาร PDF ที่มีอยู่โดยใช้`Document`ตัวสร้างและส่งผ่านเส้นทางไปยังไฟล์ PDF อินพุต

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## ขั้นตอนที่ 5: ปรับขนาดตัวอักษร
ลดขนาดตัวอักษรของข้อความส่วนต่างๆ ลงเหลือ 0.7 เท่า เพื่อให้สามารถอ่านได้ง่ายขึ้น และแสดงข้อความแบบคอลัมน์ได้ดีขึ้น

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## ขั้นตอนที่ 6: แยกข้อความจากคอลัมน์
 บันทึกเอกสาร PDF ที่แก้ไขแล้วลงในสตรีมหน่วยความจำและโหลดซ้ำเป็นเอกสารใหม่ จากนั้นใช้`TextAbsorber` คลาสที่จะแยกข้อความจากคอลัมน์

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## ขั้นตอนที่ 7: บันทึกข้อความที่แยกออกมา
บันทึกข้อความที่แยกออกมาไปยังไฟล์ข้อความที่เส้นทางไฟล์เอาต์พุตที่ระบุ

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการแยกคอลัมน์ข้อความโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// ต้องลดขนาดตัวอักษรลงอย่างน้อย 70%
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## บทสรุป
คุณได้แยกข้อความคอลัมน์จากเอกสาร PDF สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ข้อความที่แยกออกมาได้รับการบันทึกลงในไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้คืออะไร?

A: บทช่วยสอนนี้นำเสนอคำแนะนำทีละขั้นตอนในการแยกคอลัมน์ข้อความจากไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่แนบมาจะแสดงการสาธิตขั้นตอนที่จำเป็นในทางปฏิบัติ

#### ถาม: ฉันควรนำเข้าเนมสเปซอะไรบ้าง?

ก: ในไฟล์โค้ดที่คุณต้องการแยกคอลัมน์ข้อความ ให้ใส่คำสั่ง using ต่อไปนี้ไว้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร?

 ก. ค้นหาเส้น`string dataDir = "YOUR DOCUMENT DIRECTORY";` ในโค้ดและแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะเปิดเอกสาร PDF ที่มีอยู่ได้อย่างไร

 ก: ในขั้นตอนที่ 4 คุณจะเปิดเอกสาร PDF ที่มีอยู่โดยใช้`Document` ตัวสร้างและกำหนดเส้นทางไปยังไฟล์ PDF อินพุต

#### ถาม: ทำไมขนาดตัวอักษรถึงต้องถูกปรับ?

A: ขั้นตอนที่ 5 คือการลดขนาดตัวอักษรของข้อความบางส่วนลง 0.7 เท่า การปรับเปลี่ยนนี้จะช่วยให้สามารถอ่านได้ง่ายขึ้นและแสดงข้อความแบบคอลัมน์ได้แม่นยำยิ่งขึ้น

#### ถาม: ฉันจะแยกข้อความจากคอลัมน์ได้อย่างไร

 ก: ขั้นตอนที่ 6 ประกอบด้วยการบันทึกเอกสาร PDF ที่แก้ไขแล้วลงในสตรีมหน่วยความจำ โหลดซ้ำเป็นเอกสารใหม่ แล้วจึงใช้`TextAbsorber` คลาสที่จะแยกข้อความจากคอลัมน์

#### ถาม: จุดประสงค์ของการบันทึกข้อความที่แยกออกมาคืออะไร?

ก: ในขั้นตอนที่ 7 คุณจะบันทึกข้อความที่แยกออกมาไปยังไฟล์ข้อความที่เส้นทางไฟล์เอาต์พุตที่ระบุ

#### ถาม: เหตุใดจึงต้องลดขนาดตัวอักษรก่อนทำการแยกไฟล์?

A: การลดขนาดตัวอักษรช่วยให้แน่ใจว่าข้อความที่แยกออกมาจะจัดตำแหน่งอย่างถูกต้องภายในคอลัมน์ ทำให้แสดงเค้าโครงเดิมได้แม่นยำยิ่งขึ้น

#### ถาม: สิ่งสำคัญที่ได้จากบทช่วยสอนนี้คืออะไร?

A: เมื่อทำตามบทช่วยสอนนี้แล้ว คุณจะได้รับความรู้และทักษะที่จำเป็นในการแยกคอลัมน์ข้อความจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ข้อความที่ได้จะถูกบันทึกลงในไฟล์เอาต์พุตที่ระบุ