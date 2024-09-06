---
title: ยกเลิกการฝังฟอนต์และเพิ่มประสิทธิภาพไฟล์ PDF
linktitle: ยกเลิกการฝังฟอนต์และเพิ่มประสิทธิภาพไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อรับฟอนต์ที่ไม่ได้ฝังและเพิ่มประสิทธิภาพไฟล์ PDF คำแนะนำทีละขั้นตอน
type: docs
weight: 370
url: /th/net/programming-with-document/unembedfonts/
---
Aspose.PDF สำหรับ .NET เป็นไลบรารีอันทรงพลังที่มีคุณลักษณะมากมายสำหรับทำงานกับเอกสาร PDF หนึ่งในคุณลักษณะของ Aspose.PDF คือการรับแบบอักษรที่ไม่ได้ฝังจากเอกสาร PDF ซึ่งอาจมีประโยชน์หากคุณต้องการแยกแบบอักษรจากเอกสาร PDF และนำไปใช้ในแอปพลิเคชันอื่น

เราจะให้คำแนะนำทีละขั้นตอนเพื่ออธิบายโค้ดต้นฉบับ C# ต่อไปนี้สำหรับฟีเจอร์การแยกแบบอักษรของ Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไปยังไดเรกทอรีเอกสาร

ก่อนที่เราจะเริ่มต้น เราต้องกำหนดเส้นทางไปยังไดเร็กทอรีที่เอกสาร PDF ของเราตั้งอยู่ เราจะเก็บเส้นทางนี้ไว้ในตัวแปรที่เรียกว่า "dataDir"

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

แทนที่ “ไดเรกทอรีเอกสารของคุณ” ด้วยเส้นทางจริงไปยังไดเรกทอรีที่เอกสาร PDF ของคุณตั้งอยู่

## ขั้นตอนที่ 2: เปิดเอกสาร PDF

 ขั้นตอนแรกคือการโหลดเอกสาร PDF ที่คุณต้องการใช้`Document` คลาส Aspose.PDF สำหรับ .NET ตัวอย่างโค้ดต่อไปนี้แสดงวิธีโหลดเอกสาร PDF:

```csharp
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## ขั้นตอนที่ 3: ตั้งค่าตัวเลือก UnembedFonts

 หากต้องการรับแบบอักษรที่ไม่ได้ฝังจากเอกสาร PDF คุณจำเป็นต้องตั้งค่า`UnembedFonts` ตัวเลือกที่จะ`true` . ตัวเลือกนี้มีให้เลือกใน`OptimizationOptions` คลาส ตัวอย่างโค้ดต่อไปนี้แสดงวิธีการตั้งค่า`UnembedFonts` ตัวเลือก:

```csharp
// ตั้งค่าตัวเลือก UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## ขั้นตอนที่ 4: เพิ่มประสิทธิภาพเอกสาร PDF

 หลังจากตั้งค่าแล้ว`UnembedFonts` ตัวเลือกนี้ คุณสามารถเพิ่มประสิทธิภาพเอกสาร PDF ได้โดยใช้`OptimizeResources` วิธีการของ`Document` คลาส ตัวอย่างโค้ดต่อไปนี้แสดงวิธีเพิ่มประสิทธิภาพเอกสาร PDF:

```csharp
// เพิ่มประสิทธิภาพเอกสาร PDF โดยใช้ OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## ขั้นตอนที่ 5: บันทึกเอกสารที่อัปเดต

 เมื่อเอกสาร PDF ได้รับการเพิ่มประสิทธิภาพแล้ว คุณสามารถบันทึกเอกสารที่อัปเดตโดยใช้`Save` วิธีการของ`Document`คลาส ตัวอย่างโค้ดต่อไปนี้แสดงวิธีบันทึกเอกสารที่อัปเดต:

```csharp
// บันทึกเอกสารอัพเดต
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## ขั้นตอนที่ 6: รับขนาดไฟล์ต้นฉบับและขนาดที่เล็กลง

 ในที่สุด คุณสามารถรับขนาดไฟล์ต้นฉบับและขนาดย่อของเอกสาร PDF ได้โดยใช้`FileInfo` คลาสของ System.IO ตัวอย่างโค้ดต่อไปนี้แสดงวิธีการรับขนาดไฟล์ต้นฉบับและขนาดที่ลดลง:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการแยกฟอนต์ออกจากกันโดยใช้ Aspose.PDF สำหรับ .NET

นี่คือตัวอย่างซอร์สโค้ดที่สมบูรณ์สำหรับการรับแบบอักษรที่ไม่ได้ฝังจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// ตั้งค่าตัวเลือก UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// เพิ่มประสิทธิภาพเอกสาร PDF โดยใช้ OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// บันทึกเอกสารอัพเดต
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สาธิตวิธีการใช้ Aspose.PDF สำหรับ .NET เพื่อรับฟอนต์ที่แยกออกจากเอกสาร PDF โดยปฏิบัติตามคำแนะนำทีละขั้นตอน คุณสามารถนำฟีเจอร์นี้ไปใช้กับแอปพลิเคชัน C# ของคุณได้อย่างง่ายดาย การแยกฟอนต์ออกจากไฟล์อาจเป็นประโยชน์เมื่อคุณต้องทำงานกับฟอนต์ที่แยกออกมาแยกกันหรือต้องแน่ใจว่าการใช้งานฟอนต์มีความสม่ำเสมอในแพลตฟอร์มต่างๆ

## คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของการถอนแบบอักษรออกจากเอกสาร PDF คืออะไร

A: การถอดแบบอักษรออกจากเอกสาร PDF ช่วยให้คุณสามารถแยกแบบอักษรที่ฝังไว้และนำไปใช้ในแอปพลิเคชันอื่นได้ วิธีนี้มีประโยชน์ในการทำให้มั่นใจว่าการแสดงผลแบบอักษรจะสม่ำเสมอและรักษารูปลักษณ์ของเอกสาร

#### ถาม: ฉันจะระบุเส้นทางไปยังไดเร็กทอรีเอกสารในโค้ด C# ได้อย่างไร

 A: เพื่อระบุเส้นทางไปยังไดเรกทอรีเอกสาร ให้แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดพร้อมเส้นทางจริงไปยังไดเร็กทอรีที่เอกสาร PDF ของคุณตั้งอยู่

####  ถาม: อะไร`UnembedFonts` option do, and where is it set?

 ก. การ`UnembedFonts` ตัวเลือกที่มีใน`OptimizationOptions` คลาส เปิดใช้งานหรือปิดใช้งานการยกเลิกการฝังฟอนต์จากเอกสาร PDF หากต้องการตั้งค่าตัวเลือกนี้`true`ใช้โค้ดดังต่อไปนี้:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### ถาม: ฉันสามารถคืนค่าการเปลี่ยนแปลงที่เกิดขึ้นระหว่างกระบวนการเพิ่มประสิทธิภาพได้หรือไม่

A: Aspose.PDF สำหรับ .NET จะไม่ทำการเปลี่ยนแปลงเอกสาร PDF ต้นฉบับอย่างถาวรในระหว่างการเพิ่มประสิทธิภาพ กระบวนการเพิ่มประสิทธิภาพจะดำเนินการกับสำเนาของเอกสาร โดยปล่อยให้เอกสารต้นฉบับไม่เปลี่ยนแปลง

#### ถาม: ฉันสามารถตรวจสอบขนาดไฟล์ต้นฉบับและขนาดไฟล์ที่ลดลงหลังจากการเพิ่มประสิทธิภาพได้อย่างไร

 A: คุณสามารถใช้`FileInfo` ชั้นเรียนของ`System.IO` เพื่อให้ได้ขนาดไฟล์ดั้งเดิมและขนาดที่เล็กลง นี่คือตัวอย่างโค้ดสั้นๆ เพื่อให้บรรลุสิ่งนี้:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```