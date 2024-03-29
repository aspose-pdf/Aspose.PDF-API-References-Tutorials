---
title: PDF เป็น SVG
linktitle: PDF เป็น SVG
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการแปลง PDF เป็น SVG โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 180
url: /th/net/document-conversion/pdf-to-svg/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการแปลง PDF เป็นรูปแบบ SVG โดยใช้ Aspose.PDF สำหรับ .NET SVG (Scalable Vector Graphics) เป็นรูปแบบภาพเวกเตอร์ที่ช่วยรักษาคุณภาพและการปรับขนาดของกราฟิก เมื่อทำตามขั้นตอนด้านล่าง คุณจะสามารถแปลงไฟล์ PDF เป็นรูปแบบ SVG ได้

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีคุณสมบัติตรงตามข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ไลบรารี Aspose.PDF สำหรับ .NET ที่ติดตั้งบนระบบของคุณ
- สภาพแวดล้อมการพัฒนาเช่น Visual Studio

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร PDF
ในขั้นตอนนี้ เราจะโหลดไฟล์ PDF ต้นฉบับโดยใช้ Aspose.PDF สำหรับ .NET ทำตามรหัสด้านล่าง:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร PDF
Document doc = new Document(dataDir + "input.pdf");
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENTS DIRECTORY"` ด้วยไดเร็กทอรีจริงที่มีไฟล์ PDF ของคุณอยู่

## ขั้นตอนที่ 2: การสร้างอินสแตนซ์ของตัวเลือกการบันทึก SVG
หลังจากโหลดไฟล์ PDF แล้ว เราจะสร้างอินสแตนซ์ของตัวเลือกการบันทึก SVG ใช้รหัสต่อไปนี้:

```csharp
// สร้างอินสแตนซ์วัตถุ SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// อย่าบีบอัดรูปภาพ SVG ในไฟล์ Zip
saveOptions.CompressOutputToZipArchive = false;
```

## ขั้นตอนที่ 3: บันทึกไฟล์ SVG ที่ได้
ตอนนี้เราจะบันทึกไฟล์ PDF ที่แปลงแล้วในรูปแบบ SVG ใช้รหัสต่อไปนี้:

```csharp
// บันทึกเอาต์พุตเป็นไฟล์ SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 โค้ดด้านบนจะบันทึกรูปแบบ PDF ที่แปลงแล้วเป็น SVG พร้อมชื่อไฟล์`"PDFToSVG_out.svg"`.

### ตัวอย่างซอร์สโค้ดสำหรับ PDF เป็น SVG โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// โหลดเอกสาร PDF
Document doc = new Document(dataDir + "input.pdf");
// สร้างอินสแตนซ์วัตถุของ SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// อย่าบีบอัดรูปภาพ SVG ไปยังไฟล์ ZIP
saveOptions.CompressOutputToZipArchive = false;
// บันทึกเอาต์พุตเป็นไฟล์ SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงกระบวนการทีละขั้นตอนในการแปลงไฟล์ PDF เป็นรูปแบบ SVG โดยใช้ Aspose.PDF สำหรับ .NET เมื่อทำตามคำแนะนำที่อธิบายไว้ข้างต้น คุณจะสามารถแปลงไฟล์ PDF เป็นรูปแบบ SVG ได้แล้ว คุณสมบัตินี้มีประโยชน์เมื่อคุณต้องการรักษาคุณภาพกราฟิกและการปรับขนาดเมื่อแปลงเป็นภาพเวกเตอร์

### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถควบคุมความละเอียดหรือขนาดของไฟล์ SVG ที่ได้ระหว่างการแปลง PDF เป็น SVG ได้หรือไม่

 ตอบ: ได้ คุณสามารถควบคุมความละเอียดหรือขนาดของไฟล์ SVG ที่ได้ระหว่างการแปลง PDF เป็น SVG ได้โดยใช้ Aspose.PDF สำหรับ .NET ที่`SvgSaveOptions` class มีคุณสมบัติเช่น`PageSavingCallback` และ`SaveFormat` ที่ให้คุณตั้งค่าความละเอียด ขนาดหน้า หรือพารามิเตอร์อื่นๆ ที่เกี่ยวข้องกับเอาต์พุต SVG คุณสามารถปรับแต่งตัวเลือกเหล่านี้ได้ตามความต้องการของคุณเพื่อควบคุมคุณภาพและขนาดของไฟล์ SVG

#### ถาม: Aspose.PDF สำหรับ .NET รองรับการแปลง PDF ที่เข้ารหัสหรือป้องกันด้วยรหัสผ่านเป็น SVG หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET รองรับการแปลง PDF ที่เข้ารหัสหรือป้องกันด้วยรหัสผ่านเป็นรูปแบบ SVG เมื่อคุณโหลด PDF ที่มีการป้องกันด้วยรหัสผ่าน คุณสามารถระบุรหัสผ่านโดยใช้`Document` ตัวสร้างคลาสหรือโดยการตั้งค่า`Password` คุณสมบัติก่อนที่จะโหลด PDF Aspose.PDF สำหรับ .NET จะจัดการกับการถอดรหัสระหว่างกระบวนการแปลง PDF เป็น SVG

#### ถาม: ฉันสามารถแปลงเฉพาะหน้าเฉพาะของ PDF เป็น SVG แทนที่จะแปลงทั้งเอกสารได้หรือไม่

ตอบ: ได้ คุณสามารถแปลงเฉพาะหน้าที่เจาะจงของ PDF เป็น SVG แทนที่จะแปลงทั้งเอกสารโดยใช้ Aspose.PDF สำหรับ .NET ก่อนที่จะบันทึกเอาต์พุตเป็นไฟล์ SVG คุณสามารถเลือกหน้าที่คุณต้องการแปลงโดยระบุหมายเลขหน้าหรือช่วงของหน้าเหล่านั้น ด้วยวิธีนี้ คุณสามารถแยกและแปลงเฉพาะหน้าที่ต้องการจากรูปแบบ PDF เป็น SVG

#### ถาม: Aspose.PDF สำหรับ .NET เข้ากันได้กับ SVG ทุกเวอร์ชันหรือไม่

ตอบ: Aspose.PDF สำหรับ .NET ได้รับการออกแบบมาให้เข้ากันได้กับข้อกำหนด SVG 1.1 (Scalable Vector Graphics) รองรับการสร้างไฟล์ SVG ตามมาตรฐาน SVG 1.1 อย่างไรก็ตาม โปรดทราบว่า SVG 2.0 ได้รับการแนะนำเป็นเวอร์ชันล่าสุดของข้อกำหนด SVG แม้ว่า Aspose.PDF สำหรับ .NET อาจยังทำงานได้ดีกับ SVG 2.0 ในหลายกรณี ขอแนะนำให้ตรวจสอบความเข้ากันได้และข้อจำกัดที่อาจเกิดขึ้นกับคุณสมบัติ SVG เฉพาะที่คุณต้องการใช้