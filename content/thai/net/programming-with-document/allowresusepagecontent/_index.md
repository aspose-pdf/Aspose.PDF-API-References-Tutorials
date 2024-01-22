---
title: อนุญาตให้ใช้เนื้อหาหน้าซ้ำ
linktitle: อนุญาตให้ใช้เนื้อหาหน้าซ้ำ
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีปรับ PDF ให้เหมาะสมโดยเปิดใช้งานคุณสมบัติ "อนุญาตให้ใช้เนื้อหาหน้าซ้ำ" โดยใช้ Aspose.PDF สำหรับ .NET ลดขนาดไฟล์และปรับปรุงประสิทธิภาพ
type: docs
weight: 50
url: /th/net/programming-with-document/allowresusepagecontent/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีเปิดใช้งานฟีเจอร์ "อนุญาตให้นำเนื้อหาเพจกลับมาใช้ใหม่" โดยใช้ Aspose.PDF สำหรับ .NET คุณสมบัตินี้ปรับเอกสาร PDF ให้เหมาะสมโดยการนำเนื้อหาของหน้ากลับมาใช้ใหม่ ลดขนาดไฟล์และปรับปรุงประสิทธิภาพ ทำตามคำแนะนำทีละขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: โหลดเอกสาร PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## ขั้นตอนที่ 2: ตั้งค่าตัวเลือก AllowReusePageContent

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## ขั้นตอนที่ 3: ปรับเอกสาร PDF ให้เหมาะสม

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## ขั้นตอนที่ 4: บันทึกเอกสารที่อัปเดต

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## ขั้นตอนที่ 5: ตรวจสอบการลดขนาดไฟล์

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

ยินดีด้วย! คุณได้อนุญาตให้นำเนื้อหาของหน้าซ้ำในเอกสาร PDF ของคุณสำเร็จแล้ว

### ตัวอย่างซอร์สโค้ดสำหรับการอนุญาตให้นำเนื้อหาเพจกลับมาใช้ใหม่โดยใช้ Aspose.PDF สำหรับ .NET:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// ตั้งค่าตัวเลือก AllowReusePageContent
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
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

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

ตอนนี้คุณสามารถเพิ่มประสิทธิภาพเอกสาร PDF ของคุณได้อย่างมีประสิทธิภาพโดยอนุญาตให้นำเนื้อหาของหน้ามาใช้ซ้ำ

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายวิธีเปิดใช้งานฟีเจอร์ "อนุญาตให้ใช้เนื้อหาเพจซ้ำ" โดยใช้ Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนที่ให้ไว้และใช้ซอร์สโค้ด C# คุณสามารถเพิ่มประสิทธิภาพเอกสาร PDF ของคุณได้อย่างมีประสิทธิภาพโดยอนุญาตให้นำเนื้อหาของหน้ากลับมาใช้ใหม่ การเพิ่มประสิทธิภาพนี้ส่งผลให้ไฟล์ PDF มีขนาดเล็กลง ซึ่งอาจส่งผลให้เวลาในการโหลดเร็วขึ้น และปรับปรุงประสิทธิภาพเมื่อจัดการเอกสาร PDF ขนาดใหญ่ Aspose.PDF สำหรับ .NET นำเสนอโซลูชันที่มีประสิทธิภาพและใช้งานง่ายสำหรับการเพิ่มประสิทธิภาพ PDF ซึ่งช่วยให้คุณสามารถสร้างไฟล์ PDF ที่มีประสิทธิภาพและมีคุณภาพสูงได้อย่างง่ายดาย

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของการเปิดใช้งานฟีเจอร์ "อนุญาตให้ใช้เนื้อหาหน้าซ้ำ" ในเอกสาร PDF คืออะไร

ตอบ: การเปิดใช้งานคุณสมบัติ "อนุญาตให้ใช้เนื้อหาหน้าซ้ำ" ในเอกสาร PDF จะปรับไฟล์ให้เหมาะสมโดยการนำเนื้อหาของหน้ากลับมาใช้ใหม่ ซึ่งจะช่วยลดขนาดไฟล์และปรับปรุงประสิทธิภาพโดยรวม การเพิ่มประสิทธิภาพนี้ส่งผลให้ไฟล์ PDF มีขนาดเล็กลงโดยไม่กระทบต่อคุณภาพของเนื้อหา

#### ถาม: ฟีเจอร์ "อนุญาตให้ใช้เนื้อหาเพจซ้ำ" ทำงานอย่างไร

ตอบ: เมื่อเปิดใช้งานคุณสมบัติ "อนุญาตให้ใช้เนื้อหาเพจซ้ำ" ออบเจ็กต์หน้าที่เหมือนกันภายในเอกสาร PDF จะถูกแชร์และนำมาใช้ซ้ำ แทนที่จะทำซ้ำในแต่ละเหตุการณ์ การแชร์เนื้อหาเพจนี้จะช่วยลดขนาดไฟล์โดยรวมลงอย่างมาก

#### ถาม: ฉันสามารถคืนค่าการปรับให้เหมาะสมและกู้คืนเอกสารต้นฉบับได้หรือไม่

ตอบ: ไม่ เมื่อดำเนินการปรับให้เหมาะสมด้วย "อนุญาตให้ใช้ซ้ำเนื้อหาเพจ" และบันทึกเอกสาร PDF แล้ว การเปลี่ยนแปลงจะมีผลถาวร ขอแนะนำให้สำรองข้อมูลเอกสารต้นฉบับก่อนดำเนินการปรับให้เหมาะสมที่สุด

#### ถาม: การเปิดใช้งานฟีเจอร์นี้จะส่งผลต่อรูปลักษณ์หรือเนื้อหาของเอกสาร PDF หรือไม่

ตอบ: การเปิดใช้งานฟีเจอร์ "อนุญาตให้ใช้เนื้อหาเพจซ้ำ" จะไม่ส่งผลต่อลักษณะที่ปรากฏหรือเนื้อหาของเอกสาร PDF โดยจะปรับโครงสร้างภายในของไฟล์ให้เหมาะสมเพื่อลดความซ้ำซ้อนและเพิ่มประสิทธิภาพ

#### ถาม: Aspose.PDF สำหรับ .NET เป็นโซลูชันที่เชื่อถือได้สำหรับการเพิ่มประสิทธิภาพและการจัดการ PDF หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET เป็นไลบรารีที่เชื่อถือได้และมีฟีเจอร์มากมายสำหรับการเพิ่มประสิทธิภาพและการจัดการ PDF มีตัวเลือกมากมายในการเพิ่มประสิทธิภาพไฟล์ PDF รวมถึงการลดขนาดไฟล์ การลบทรัพยากรที่ไม่ได้ใช้ และเพิ่มประสิทธิภาพโดยรวม