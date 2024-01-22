---
title: ปิดการใช้งานการบีบอัดไฟล์ในไฟล์ PDF
linktitle: ปิดการใช้งานการบีบอัดไฟล์ในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีปิดใช้งานการบีบอัดไฟล์ในไฟล์ PDF ด้วย Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนเพื่อการจัดการที่ง่ายดาย
type: docs
weight: 30
url: /th/net/programming-with-attachments/disable-files-compression/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# ต่อไปนี้ทีละขั้นตอนเพื่อปิดใช้งานการบีบอัดไฟล์ในรูปแบบ PDF โดยใช้ Aspose.PDF สำหรับ .NET

ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณก่อนที่จะเริ่มต้น มีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# ด้วย

### ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในซอร์สโค้ดที่ให้มา คุณจะต้องระบุไดเร็กทอรีที่มีไฟล์ PDF ที่คุณต้องการปิดใช้งานการบีบอัดไฟล์ เปลี่ยนตัวแปร "dataDir" เป็นไดเร็กทอรีที่ต้องการ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### ขั้นตอนที่ 2: เปิดเอกสาร PDF ที่มีอยู่

เราเปิดเอกสาร PDF ที่มีอยู่โดยใช้เส้นทางที่ระบุ

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### ขั้นตอนที่ 3: การตั้งค่าไฟล์ใหม่เพื่อเพิ่มเป็นไฟล์แนบ

เรากำหนดค่าไฟล์ใหม่ที่เราต้องการเพิ่มเป็นไฟล์แนบ ในตัวอย่างนี้ เราเพิ่มไฟล์ข้อความชื่อ "test_out.txt" และคำอธิบาย "ไฟล์ข้อความตัวอย่าง"

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### ขั้นตอนที่ 4: ปิดใช้งานการบีบอัดไฟล์

เราปิดใช้งานการบีบอัดไฟล์โดยการตั้งค่าคุณสมบัติการเข้ารหัสของออบเจ็กต์ FileSpecification เป็น FileEncoding.None

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### ขั้นตอนที่ 5: การเพิ่มไฟล์แนบลงในคอลเลกชันไฟล์แนบของเอกสาร

เราเพิ่มไฟล์แนบลงในคอลเล็กชันไฟล์แนบของเอกสาร

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### ขั้นตอนที่ 6: บันทึกไฟล์เอาต์พุตใหม่

สุดท้าย เราจะบันทึกไฟล์ PDF ใหม่ที่เป็นผลลัพธ์โดยใช้ชื่อ "DisableFilesCompression_out.pdf" ในไดเร็กทอรีที่ระบุ

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### ตัวอย่างซอร์สโค้ดสำหรับการปิดใช้งานการบีบอัดไฟล์โดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// ตั้งค่าไฟล์ใหม่เพื่อเพิ่มเป็นไฟล์แนบ
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
// ระบุการเข้ารหัส proparty โดยตั้งค่าเป็น FileEncoding.None
fileSpecification.Encoding = FileEncoding.None;
//เพิ่มไฟล์แนบในคอลเลกชันไฟล์แนบของเอกสาร
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
// บันทึกเอาต์พุตใหม่
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายวิธีปิดใช้งานการบีบอัดไฟล์ในรูปแบบ PDF โดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อรักษาความสมบูรณ์ของไฟล์ที่แนบมาโดยไม่ต้องบีบอัด

## คำถามที่พบบ่อยสำหรับการปิดการใช้งานการบีบอัดไฟล์ในรูปแบบไฟล์ PDF

#### ถาม: เหตุใดฉันจึงต้องปิดการใช้งานการบีบอัดไฟล์ในเอกสาร PDF

ตอบ: การปิดใช้งานการบีบอัดไฟล์ช่วยให้มั่นใจได้ว่าไฟล์ที่แนบมาภายในเอกสาร PDF จะไม่ถูกบีบอัด โดยคงคุณภาพและเนื้อหาต้นฉบับไว้

#### ถาม: การปิดใช้งานการบีบอัดไฟล์มีประโยชน์ต่อไฟล์แนบ PDF อย่างไร

ตอบ: การปิดใช้งานการบีบอัดจะป้องกันการสูญเสียข้อมูลหรือคุณภาพที่อาจเกิดขึ้นในระหว่างกระบวนการบีบอัด เพื่อให้มั่นใจว่าไฟล์ที่แนบมาจะถูกนำเสนอตามที่เป็นอยู่

#### ถาม: ฉันสามารถเลือกที่จะปิดใช้งานการบีบอัดไฟล์แนบเฉพาะโดยใช้บทช่วยสอนนี้ได้หรือไม่

ตอบ: ใช่ บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการปิดใช้งานการบีบอัดไฟล์สำหรับไฟล์แนบแต่ละรายการในเอกสาร PDF ซึ่งให้การควบคุมที่ละเอียด

#### ถาม: ฉันสามารถปิดใช้งานการบีบอัดไฟล์แนบประเภทใดได้บ้าง

ตอบ: คุณสามารถปิดใช้งานการบีบอัดไฟล์แนบประเภทใดก็ได้ เช่น รูปภาพ เอกสาร สเปรดชีต และอื่นๆ เพื่อให้มั่นใจว่าไฟล์แนบจะมีความสมบูรณ์

#### ถาม: การปิดใช้งานการบีบอัดจะส่งผลต่อขนาดไฟล์โดยรวมของเอกสาร PDF หรือไม่

ตอบ: การปิดใช้งานการบีบอัดไฟล์แนบอาจทำให้ขนาดไฟล์โดยรวมของเอกสาร PDF เพิ่มขึ้นเล็กน้อย เนื่องจากไฟล์ที่ไม่บีบอัดจะใช้พื้นที่มากขึ้น

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยอำนวยความสะดวกในกระบวนการปิดใช้งานการบีบอัดไฟล์ได้อย่างไร

ตอบ: Aspose.PDF สำหรับ .NET มี API ที่ใช้งานง่ายซึ่งช่วยให้คุณสามารถปิดใช้งานการบีบอัดไฟล์สำหรับสิ่งที่แนบมาได้ ดังที่แสดงในซอร์สโค้ดที่ให้มา

#### ถาม: ฉันสามารถเปิดใช้งานการบีบอัดไฟล์แนบอีกครั้งในภายหลังได้หรือไม่ หากจำเป็น

ตอบ: ได้ คุณสามารถแก้ไขการตั้งค่าของไฟล์แนบเพื่อเปิดใช้งานการบีบอัดอีกครั้งได้หากจำเป็น

#### ถาม: จะเกิดอะไรขึ้นหากฉันเปิด PDF บนอุปกรณ์หรือซอฟต์แวร์ที่รองรับการบีบอัด

ตอบ: หากคุณเปิด PDF บนอุปกรณ์หรือซอฟต์แวร์ที่รองรับการบีบอัด ไฟล์แนบอาจถูกแสดงโดยไม่มีการบีบอัด ซึ่งอาจส่งผลต่อขนาดไฟล์และประสิทธิภาพการเรนเดอร์

#### ถาม: มีสถานการณ์เฉพาะใดบ้างที่แนะนำให้ปิดใช้งานการบีบอัด

ตอบ: แนะนำให้ปิดใช้การบีบอัดสำหรับไฟล์แนบที่ยังคงรักษาคุณภาพต้นฉบับและความสมบูรณ์ของข้อมูลเป็นสำคัญ เช่น รูปภาพที่มีความละเอียดสูงหรือเอกสารที่ละเอียดอ่อน