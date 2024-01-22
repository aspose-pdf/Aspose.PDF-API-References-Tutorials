---
title: แยกข้อความคอลัมน์ในไฟล์ PDF
linktitle: แยกข้อความคอลัมน์ในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีแยกข้อความคอลัมน์ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 150
url: /th/net/programming-with-text/extract-columns-text/
---
บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการแยกข้อความคอลัมน์ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ที่ติดตั้งบนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose หรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการแยกข้อความของคอลัมน์ ให้เพิ่มคำสั่งต่อไปนี้โดยใช้คำสั่งที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเร็กทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่เก็บเอกสารของคุณ

## ขั้นตอนที่ 4: เปิดเอกสาร PDF
 เปิดเอกสาร PDF ที่มีอยู่โดยใช้ไฟล์`Document`Constructor และส่งเส้นทางไปยังไฟล์ PDF อินพุต

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## ขั้นตอนที่ 5: ปรับขนาดตัวอักษร
ลดขนาดแบบอักษรของส่วนย่อยของข้อความลง 0.7 เท่า เพื่อเพิ่มความสามารถในการอ่านและแสดงข้อความแบบเรียงเป็นแนวได้ดีขึ้น

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## ขั้นตอนที่ 6: แยกข้อความออกจากคอลัมน์
 บันทึกเอกสาร PDF ที่แก้ไขแล้วลงในสตรีมหน่วยความจำและโหลดซ้ำเป็นเอกสารใหม่ จากนั้นใช้`TextAbsorber` คลาสเพื่อแยกข้อความออกจากคอลัมน์

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
บันทึกข้อความที่แยกออกมาเป็นไฟล์ข้อความตามเส้นทางไฟล์เอาต์พุตที่ระบุ

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับแยกข้อความคอลัมน์โดยใช้ Aspose.PDF สำหรับ .NET 
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
	// ต้องลดขนาดตัวอักษรอย่างน้อย 70%
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
คุณได้แยกข้อความคอลัมน์ออกจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว ข้อความที่แยกออกมาได้รับการบันทึกลงในไฟล์เอาท์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้คืออะไร?

ตอบ: บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนในการแยกคอลัมน์ข้อความจากไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาเป็นการสาธิตขั้นตอนที่จำเป็นในทางปฏิบัติ

#### ถาม: ฉันควรนำเข้าเนมสเปซใด

ตอบ: ในไฟล์โค้ดที่คุณต้องการแยกคอลัมน์ข้อความ ให้รวมคำสั่งต่อไปนี้ไว้ที่ตอนต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร

 ตอบ: ค้นหาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` ในโค้ดและแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะเปิดเอกสาร PDF ที่มีอยู่ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 4 คุณจะเปิดเอกสาร PDF ที่มีอยู่โดยใช้ไฟล์`Document` ตัวสร้างและจัดเตรียมเส้นทางไปยังไฟล์ PDF อินพุต

#### ถาม: เหตุใดจึงต้องปรับขนาดตัวอักษร

ตอบ: ขั้นตอนที่ 5 เกี่ยวข้องกับการลดขนาดตัวอักษรของส่วนข้อความลง 0.7 เท่า การปรับเปลี่ยนนี้ช่วยเพิ่มความสามารถในการอ่านและแสดงข้อความแบบเรียงเป็นแนวได้แม่นยำยิ่งขึ้น

#### ถาม: ฉันจะแยกข้อความออกจากคอลัมน์ได้อย่างไร

 ตอบ: ขั้นตอนที่ 6 ประกอบด้วยการบันทึกเอกสาร PDF ที่แก้ไขแล้วลงในสตรีมหน่วยความจำ โหลดซ้ำเป็นเอกสารใหม่ จากนั้นใช้`TextAbsorber` คลาสเพื่อแยกข้อความออกจากคอลัมน์

#### ถาม: จุดประสงค์ของการบันทึกข้อความที่แยกออกมาคืออะไร?

ตอบ: ในขั้นตอนที่ 7 คุณจะบันทึกข้อความที่แยกออกมาเป็นไฟล์ข้อความที่เส้นทางไฟล์เอาต์พุตที่ระบุ

#### ถาม: เหตุใดจึงต้องลดขนาดตัวอักษรก่อนทำการแตกไฟล์

ตอบ: การลดขนาดฟอนต์ช่วยให้มั่นใจได้ว่าข้อความที่แยกออกมาจะจัดเรียงอย่างเหมาะสมภายในคอลัมน์ ทำให้แสดงเค้าโครงดั้งเดิมได้แม่นยำยิ่งขึ้น

#### ถาม: สิ่งสำคัญที่ได้รับจากบทช่วยสอนนี้คืออะไร

ตอบ: เมื่อทำตามบทช่วยสอนนี้ คุณจะได้รับความรู้และทักษะที่จำเป็นในการแยกคอลัมน์ข้อความจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ข้อความผลลัพธ์ได้รับการบันทึกลงในไฟล์เอาต์พุตที่ระบุ