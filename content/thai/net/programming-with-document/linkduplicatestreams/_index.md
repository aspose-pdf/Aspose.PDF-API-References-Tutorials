---
title: ลิงก์สตรีมที่ซ้ำกัน
linktitle: ลิงก์สตรีมที่ซ้ำกัน
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีใช้ Aspose.PDF สำหรับฟีเจอร์ .NET Link Duplicate Streams เพื่อปรับเอกสาร PDF ของคุณให้เหมาะสมด้วยคำแนะนำทีละขั้นตอนนี้
type: docs
weight: 230
url: /th/net/programming-with-document/linkduplicatestreams/
---
Aspose.PDF สำหรับ .NET เป็นไลบรารี่ที่ครอบคลุมและทรงพลังซึ่งมีฟีเจอร์ที่หลากหลายเพื่อทำงานกับไฟล์ PDF หนึ่งในคุณสมบัติที่สำคัญคือความสามารถในการปรับแต่งไฟล์ PDF ให้เหมาะสม ในบทความนี้ เราจะอธิบายวิธีใช้ฟีเจอร์ Link Duplicate Streams ของ Aspose.PDF สำหรับ .NET เพื่อปรับไฟล์ PDF ให้เหมาะสม เราจะให้คำแนะนำทีละขั้นตอนและรวมตัวอย่างซอร์สโค้ดแบบเต็มเพื่อให้นักพัฒนาปฏิบัติตามได้ง่าย

## ขั้นตอนที่ 1: การเปิดเอกสาร PDF

หากต้องการเปิดเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ให้ทำตามขั้นตอนเหล่านี้:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

ในโค้ดด้านบน ให้แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางไปยังไดเรกทอรีโครงการของคุณ

## ขั้นตอนที่ 2: การตั้งค่าตัวเลือก LinkDuplicateStreams

เมื่อต้องการตั้งค่าตัวเลือก LinkDuplicateStreams ให้ทำตามขั้นตอนเหล่านี้:

```csharp
// ตั้งค่าตัวเลือก LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    LinkDuplcateStreams = true
};
```

ในโค้ดด้านบน เราได้สร้างอินสแตนซ์ใหม่ของ OptimizationOptions และตั้งค่าตัวเลือก LinkDuplicateStreams เป็นจริง

## ขั้นตอนที่ 3: การเพิ่มประสิทธิภาพเอกสาร PDF

หากต้องการปรับเอกสาร PDF ให้เหมาะสม ให้ทำตามขั้นตอนเหล่านี้:

```csharp
// ปรับเอกสาร PDF ให้เหมาะสมโดยใช้ OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

ในโค้ดด้านบน เราใช้วิธี OptimizeResources ของออบเจ็กต์ pdfDocument เพื่อปรับเอกสาร PDF ให้เหมาะสมโดยใช้ OptimizationOptions ที่เราสร้างไว้ก่อนหน้านี้

## ขั้นตอนที่ 4: บันทึกเอกสารที่อัปเดต

หากต้องการบันทึกเอกสารที่อัปเดต ให้ทำตามขั้นตอนเหล่านี้:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
// บันทึกเอกสารที่อัปเดต
pdfDocument.Save(dataDir);
```

ในโค้ดด้านบน เราใช้เมธอด Save ของออบเจ็กต์ pdfDocument เพื่อบันทึกเอกสารที่อัปเดตเป็นไฟล์ใหม่ชื่อ "OptimizeDocument_out.pdf" ในไดเร็กทอรีโปรเจ็กต์

### ตัวอย่างซอร์สโค้ดสำหรับลิงก์สตรีมที่ซ้ำกันโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// ตั้งค่าตัวเลือก LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	LinkDuplcateStreams = true
};
// ปรับเอกสาร PDF ให้เหมาะสมโดยใช้ OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// บันทึกเอกสารที่อัปเดต
pdfDocument.Save(dataDir);
```

## บทสรุป

คุณลักษณะ Link Duplicate Streams ของ Aspose.PDF สำหรับ .NET มอบวิธีที่มีประสิทธิภาพในการเพิ่มประสิทธิภาพไฟล์ PDF โดยการลดขนาดลง ด้วยการระบุและเชื่อมโยงสตรีมที่ซ้ำกัน ไลบรารีจะช่วยสร้างเอกสาร PDF ที่มีประสิทธิภาพมากขึ้น โดยไม่สูญเสียความสมบูรณ์ของข้อมูลหรือคุณภาพของภาพ นักพัฒนาสามารถใช้คุณสมบัตินี้ได้อย่างง่ายดายโดยใช้ขั้นตอนและตัวอย่างซอร์สโค้ดที่ให้มา ซึ่งจะช่วยเพิ่มประสิทธิภาพและประสิทธิภาพการจัดเก็บไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของฟีเจอร์ Link Duplicate Streams ใน Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: คุณลักษณะ Link Duplicate Streams ใน Aspose.PDF สำหรับ .NET ใช้เพื่อเพิ่มประสิทธิภาพไฟล์ PDF โดยการระบุและเชื่อมโยงสตรีมที่ซ้ำกันภายในเอกสาร ในไฟล์ PDF อาจมีสตรีมที่ซ้ำกัน (เช่น รูปภาพหรือแบบอักษร) ที่ใช้พื้นที่โดยไม่จำเป็น ด้วยการเชื่อมโยงสตรีมที่ซ้ำกันเหล่านี้ ขนาดไฟล์จะลดลง ส่งผลให้เอกสาร PDF มีประสิทธิภาพและมีขนาดเล็กลง

#### ถาม: ฟีเจอร์ Link Duplicate Streams ทำงานอย่างไร

ตอบ: คุณสมบัติ Link Duplicate Streams ทำงานโดยการวิเคราะห์สตรีมเนื้อหาของเอกสาร PDF และระบุสตรีมที่ซ้ำกันซึ่งมีเนื้อหาเดียวกัน แทนที่จะจัดเก็บสตรีมที่ซ้ำกันเหล่านี้แยกกัน คุณลักษณะนี้จะสร้างลิงก์ระหว่างสตรีมเหล่านั้น เพื่อแชร์เนื้อหาเดียวกันได้อย่างมีประสิทธิภาพ เทคนิคการปรับให้เหมาะสมนี้จะช่วยลดขนาดโดยรวมของเอกสาร PDF โดยไม่ส่งผลกระทบต่อรูปลักษณ์หรือฟังก์ชันการทำงานของเอกสาร

#### ถาม: ฟีเจอร์ Link Duplicate Streams สามารถทำให้ข้อมูลหรือคุณภาพในเอกสาร PDF สูญหายได้หรือไม่

ตอบ: ไม่ คุณสมบัติ Link Duplicate Streams จะไม่ทำให้ข้อมูลหรือคุณภาพในเอกสาร PDF สูญหาย จะปรับขนาดไฟล์ให้เหมาะสมโดยการเชื่อมโยงสตรีมที่ซ้ำกันเท่านั้น โดยไม่เปลี่ยนแปลงเนื้อหาหรือลักษณะที่ปรากฏของเอกสาร คุณลักษณะนี้ได้รับการออกแบบมาเพื่อให้แน่ใจว่าเอกสาร PDF ยังคงสภาพเดิมและรักษาคุณภาพต้นฉบับไว้