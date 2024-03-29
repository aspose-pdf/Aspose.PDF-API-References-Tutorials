---
title: MHT เป็น PDF
linktitle: MHT เป็น PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการแปลง MHT เป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 70
url: /th/net/document-conversion/mht-to-pdf/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการแปลงไฟล์ MHT เป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET MHT (MIME HTML) เป็นรูปแบบที่ใช้ในการบันทึกหน้าเว็บที่สมบูรณ์ รวมถึงรูปภาพและเนื้อหาที่เกี่ยวข้อง เมื่อทำตามขั้นตอนด้านล่าง คุณจะสามารถแปลงไฟล์ MHT เป็นรูปแบบ PDF ได้

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีคุณสมบัติตรงตามข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ไลบรารี Aspose.PDF สำหรับ .NET ที่ติดตั้งบนระบบของคุณ
- สภาพแวดล้อมการพัฒนาเช่น Visual Studio

## ขั้นตอนที่ 1: กำลังโหลดไฟล์ MHT
ในขั้นตอนนี้ เราจะโหลดไฟล์ MHT โดยใช้ Aspose.PDF สำหรับ .NET ทำตามรหัสด้านล่าง:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// โหลดเอกสาร
Document document = new Document(dataDir + "test.mht", options);
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENTS DIRECTORY"` ด้วยไดเร็กทอรีจริงที่มีไฟล์ MHT ของคุณอยู่

## ขั้นตอนที่ 2: การแปลง MHT เป็น PDF
หลังจากโหลดไฟล์ MHT แล้ว เราสามารถดำเนินการแปลงเป็น PDF ได้ ใช้รหัสต่อไปนี้:

```csharp
// บันทึกผลลัพธ์เป็นเอกสาร PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 โค้ดด้านบนแปลงไฟล์ MHT เป็นรูปแบบ PDF และบันทึกเป็นชื่อไฟล์`"MHTToPDF_out.pdf"`.

### ตัวอย่างซอร์สโค้ดสำหรับ MHT เป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// โหลดเอกสาร
Document document = new Document(dataDir  + "test.mht", options);
// บันทึกผลลัพธ์เป็นเอกสาร PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงกระบวนการทีละขั้นตอนในการแปลงไฟล์ MHT เป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET เมื่อทำตามคำแนะนำที่อธิบายไว้ข้างต้น คุณจะสามารถแปลงไฟล์ MHT เป็นรูปแบบ PDF ได้แล้ว คุณสมบัตินี้จะมีประโยชน์เมื่อคุณต้องการแปลงหน้าเว็บทั้งหมดเป็นเอกสาร PDF

### คำถามที่พบบ่อย

#### ถาม: Aspose.PDF สำหรับ .NET รองรับการแปลงไฟล์ MHT ที่มีรูปภาพที่ฝังไว้เป็น PDF หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET รองรับการแปลงไฟล์ MHT ด้วยรูปภาพที่ฝังไว้เป็น PDF ไลบรารีสามารถจัดการเนื้อหาหน้าเว็บที่สมบูรณ์ รวมถึงรูปภาพและทรัพยากรที่เกี่ยวข้อง และแปลงเป็นเอกสาร PDF

#### ถาม: ฉันสามารถปรับแต่งเอาต์พุต PDF ในระหว่างกระบวนการแปลง MHT เป็น PDF ได้หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET มีตัวเลือกมากมายในการปรับแต่งเอาต์พุต PDF ในระหว่างกระบวนการแปลง MHT เป็น PDF คุณสามารถตั้งค่าคุณสมบัติ เช่น ขนาดหน้า การวางแนว ระยะขอบ และอื่นๆ เพื่อควบคุมลักษณะที่ปรากฏของเอกสาร PDF ที่เป็นผลลัพธ์

#### ถาม: Aspose.PDF สำหรับ .NET จะรักษาไฮเปอร์ลิงก์และการจัดรูปแบบจากไฟล์ MHT ต้นฉบับในเอาต์พุต PDF หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET จะรักษาไฮเปอร์ลิงก์และการจัดรูปแบบจากไฟล์ MHT ต้นฉบับในเอาต์พุต PDF ไลบรารีช่วยให้แน่ใจว่า PDF ที่แปลงแล้วยังคงมีเค้าโครงและเนื้อหาเหมือนกับไฟล์ MHT ต้นฉบับ

#### ถาม: ฉันสามารถแปลงไฟล์ MHT หลายไฟล์เพื่อแยกเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ: ได้ คุณสามารถแปลงไฟล์ MHT หลายไฟล์เพื่อแยกเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เพียงโหลดไฟล์ MHT แต่ละไฟล์แล้วบันทึกเป็นเอกสาร PDF แยกต่างหากพร้อมชื่อไฟล์ที่ไม่ซ้ำกัน