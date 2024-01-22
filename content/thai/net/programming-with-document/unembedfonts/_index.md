---
title: แบบอักษรที่ยกเลิกการฝังและปรับไฟล์ PDF ให้เหมาะสม
linktitle: แบบอักษรที่ยกเลิกการฝังและปรับไฟล์ PDF ให้เหมาะสม
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อรับแบบอักษรที่ยังไม่ได้ฝังและปรับไฟล์ PDF ให้เหมาะสม คำแนะนำทีละขั้นตอน
type: docs
weight: 370
url: /th/net/programming-with-document/unembedfonts/
---
Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งมีคุณลักษณะมากมายในการทำงานกับเอกสาร PDF หนึ่งในคุณสมบัติคือการรับแบบอักษรที่ไม่ถูกฝังจากเอกสาร PDF สิ่งนี้มีประโยชน์หากคุณต้องการแยกแบบอักษรออกจากเอกสาร PDF และใช้ในแอปพลิเคชันอื่น

เราจะให้คำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ต่อไปนี้ของฟีเจอร์รับแบบอักษรที่ยังไม่ได้ฝังของ Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 1: กำหนดเส้นทางไปยังไดเร็กทอรีเอกสาร

ก่อนที่เราจะเริ่ม เราต้องกำหนดเส้นทางไปยังไดเร็กทอรีที่มีเอกสาร PDF ของเราอยู่ เราจะเก็บเส้นทางนี้ไว้ในตัวแปรที่เรียกว่า "dataDir"

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีที่มีเอกสาร PDF ของคุณอยู่

## ขั้นตอนที่ 2: เปิดเอกสาร PDF

 ขั้นตอนแรกคือการโหลดเอกสาร PDF ที่คุณต้องการใช้`Document` คลาสของ Aspose.PDF สำหรับ .NET ข้อมูลโค้ดต่อไปนี้แสดงวิธีการโหลดเอกสาร PDF:

```csharp
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## ขั้นตอนที่ 3: ตั้งค่าตัวเลือก UnembedFonts

 หากต้องการรับแบบอักษรที่ยกเลิกการฝังจากเอกสาร PDF คุณต้องตั้งค่า`UnembedFonts` ตัวเลือกในการ`true` . ตัวเลือกนี้มีอยู่ใน`OptimizationOptions` ระดับ. ข้อมูลโค้ดต่อไปนี้แสดงวิธีการตั้งค่า`UnembedFonts` ตัวเลือก:

```csharp
// ตั้งค่าตัวเลือก UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## ขั้นตอนที่ 4: ปรับเอกสาร PDF ให้เหมาะสม

 หลังจากตั้งค่า`UnembedFonts` ตัวเลือก คุณสามารถเพิ่มประสิทธิภาพเอกสาร PDF โดยใช้ไฟล์`OptimizeResources` วิธีการของ`Document` ระดับ. ข้อมูลโค้ดต่อไปนี้แสดงวิธีเพิ่มประสิทธิภาพเอกสาร PDF:

```csharp
// ปรับเอกสาร PDF ให้เหมาะสมโดยใช้ OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## ขั้นตอนที่ 5: บันทึกเอกสารที่อัปเดต

 เมื่อเอกสาร PDF ได้รับการปรับให้เหมาะสมแล้ว คุณสามารถบันทึกเอกสารที่อัปเดตได้โดยใช้`Save` วิธีการของ`Document`ระดับ. ข้อมูลโค้ดต่อไปนี้แสดงวิธีการบันทึกเอกสารที่อัปเดต:

```csharp
// บันทึกเอกสารที่อัปเดต
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## ขั้นตอนที่ 6: รับขนาดไฟล์ดั้งเดิมและขนาดไฟล์ที่ลดลง

 สุดท้าย คุณสามารถรับขนาดไฟล์ต้นฉบับและขนาดไฟล์ที่ลดลงของเอกสาร PDF ได้โดยใช้`FileInfo` คลาสของ System.IO ข้อมูลโค้ดต่อไปนี้แสดงวิธีรับไฟล์ต้นฉบับและลดขนาดไฟล์:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### ตัวอย่างซอร์สโค้ดสำหรับรับแบบอักษรที่ไม่ถูกฝังโดยใช้ Aspose.PDF สำหรับ .NET

นี่คือตัวอย่างซอร์สโค้ดที่สมบูรณ์สำหรับการรับฟอนต์ที่ไม่ถูกฝังจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET:

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
// ปรับเอกสาร PDF ให้เหมาะสมโดยใช้ OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// บันทึกเอกสารที่อัปเดต
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สาธิตวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อรับแบบอักษรที่ยังไม่ได้ฝังจากเอกสาร PDF ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถนำคุณสมบัตินี้ไปใช้ในแอปพลิเคชัน C# ของคุณได้อย่างง่ายดาย การเลิกฝังฟอนต์อาจเป็นประโยชน์เมื่อคุณต้องการทำงานกับฟอนต์ที่แยกออกมาแยกกัน หรือรับประกันการใช้งานฟอนต์ที่สอดคล้องกันบนแพลตฟอร์มต่างๆ

## คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของการยกเลิกการฝังแบบอักษรจากเอกสาร PDF คืออะไร

ตอบ: การเลิกฝังแบบอักษรจากเอกสาร PDF ช่วยให้คุณสามารถแยกแบบอักษรที่ฝังไว้และนำไปใช้ในแอปพลิเคชันอื่นได้ สิ่งนี้มีประโยชน์ในการรับรองการแสดงผลแบบอักษรที่สอดคล้องกันและรักษาลักษณะที่ปรากฏของเอกสาร

#### ถาม: ฉันจะระบุเส้นทางไปยังไดเร็กทอรีเอกสารในโค้ด C# ได้อย่างไร

 ตอบ: หากต้องการระบุเส้นทางไปยังไดเร็กทอรีเอกสาร ให้แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดพร้อมเส้นทางจริงไปยังไดเร็กทอรีที่มีเอกสาร PDF ของคุณอยู่

####  ถาม: อะไร`UnembedFonts` option do, and where is it set?

 ตอบ:`UnembedFonts` ตัวเลือกที่มีอยู่ใน`OptimizationOptions` คลาส เปิดหรือปิดใช้งานการเลิกฝังแบบอักษรจากเอกสาร PDF เพื่อตั้งค่าตัวเลือกนี้เป็น`true`ให้ใช้รหัสต่อไปนี้:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### ถาม: ฉันสามารถคืนค่าการเปลี่ยนแปลงที่ทำระหว่างกระบวนการปรับให้เหมาะสมได้หรือไม่

ตอบ: Aspose.PDF สำหรับ .NET จะไม่ทำการเปลี่ยนแปลงเอกสาร PDF ต้นฉบับอย่างถาวรระหว่างการปรับให้เหมาะสม กระบวนการปรับให้เหมาะสมจะดำเนินการกับสำเนาของเอกสาร โดยคงต้นฉบับเอาไว้

#### ถาม: ฉันจะตรวจสอบขนาดไฟล์ต้นฉบับและขนาดไฟล์ที่ลดลงหลังการปรับให้เหมาะสมได้อย่างไร

ตอบ: คุณสามารถใช้`FileInfo` ชั้นเรียนของ`System.IO` เพื่อให้ได้ไฟล์ต้นฉบับและขนาดไฟล์ที่ลดลง นี่คือตัวอย่างโค้ดเพื่อให้บรรลุเป้าหมายนี้:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```