---
title: แปลงขอบเขตของหน้าเป็น DOM
linktitle: แปลงขอบเขตของหน้าเป็น DOM
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: แปลงขอบเขตเฉพาะของหน้า PDF เป็น Document Object Model (DOM) ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 80
url: /th/net/programming-with-images/convert-page-region-to-dom/
---
คู่มือนี้จะแนะนำคุณทีละขั้นตอนในการแปลงขอบเขตเฉพาะของเพจเป็น Document Object Model (DOM) โดยใช้ Aspose.PDF สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมของคุณแล้ว และทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไดเร็กทอรีที่ถูกต้องสำหรับเอกสาร แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดพร้อมเส้นทางไปยังไดเร็กทอรีที่มีเอกสาร PDF ของคุณอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดเอกสาร

ในขั้นตอนนี้ เราจะเปิดเอกสาร PDF โดยใช้ไฟล์`Document` คลาสของ Aspose.PDF ใช้`Document` Constructor และส่งเส้นทางไปยังเอกสาร PDF

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## ขั้นตอนที่ 3: รับสี่เหลี่ยมผืนผ้าขอบเขตของหน้า

 ในขั้นตอนนี้ เราจะกำหนดสี่เหลี่ยมที่แสดงถึงขอบเขตเฉพาะของเพจที่เราต้องการแปลงเป็น DOM ใช้`Aspose.Pdf.Rectangle` คลาสเพื่อกำหนดพิกัดของสี่เหลี่ยม

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## ขั้นตอนที่ 4: กำหนดพื้นที่ครอบตัดของหน้า

 ใช้`CropBox` ทรัพย์สินของ`Page` วัตถุเพื่อตั้งค่ากล่องครอบตัดของหน้าให้เป็นสี่เหลี่ยมพื้นที่ที่ต้องการ

```csharp
document.Pages[1].CropBox = pageRect;
```

## ขั้นตอนที่ 5: บันทึกเอกสาร PDF ที่ครอบตัดลงในสตรีม

 ในขั้นตอนนี้ เราจะบันทึกเอกสาร PDF ที่ครอบตัดลงในสตรีมโดยใช้`MemoryStream` ระดับ.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## ขั้นตอนที่ 6: เปิดเอกสาร PDF ที่ครอบตัดแล้วแปลงเป็นรูปภาพ

 เปิดเอกสาร PDF ที่ครอบตัดโดยใช้ไฟล์`Document` class และแปลงเป็นรูปภาพ เราจะใช้ความละเอียด 300 dpi

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## ขั้นตอนที่ 7: แปลงหน้าเฉพาะให้เป็นรูปภาพ

 แปลงหน้าเฉพาะให้เป็นรูปภาพโดยใช้`Process` วิธีการของ`pngDevice`วัตถุ. ระบุเส้นทางเอาต์พุตรูปภาพ

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับการแปลงขอบเขตเพจเป็น DOM โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document document = new Document( dataDir + "AddImage.pdf");
// รับรูปสี่เหลี่ยมผืนผ้าของขอบเขตหน้าเฉพาะ
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
// ตั้งค่า CropBox ตามสี่เหลี่ยมของขอบเขตหน้าที่ต้องการ
document.Pages[1].CropBox = pageRect;
// บันทึกเอกสารที่ครอบตัดลงในสตรีม
MemoryStream ms = new MemoryStream();
document.Save(ms);
// เปิดเอกสาร PDF ที่ครอบตัดแล้วแปลงเป็นรูปภาพ
document = new Document(ms);
// สร้างวัตถุความละเอียด
Resolution resolution = new Resolution(300);
// สร้างอุปกรณ์ PNG ด้วยคุณสมบัติที่ระบุ
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
//แปลงหน้าเฉพาะและบันทึกภาพเพื่อสตรีม
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## บทสรุป

ขอแสดงความยินดี! คุณได้แปลงขอบเขตเฉพาะของเพจเป็น Document Object Model (DOM) สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET รูปภาพผลลัพธ์จะถูกบันทึกในไดเร็กทอรีที่ระบุ ตอนนี้คุณสามารถใช้รูปภาพนี้ในโครงการหรือแอปพลิเคชันของคุณได้แล้ว

## คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของการแปลงขอบเขตเฉพาะของเพจเป็น Document Object Model (DOM) โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: การแปลงขอบเขตเฉพาะของหน้า PDF เป็น Document Object Model (DOM) จะมีประโยชน์ในการแยกและจัดการเนื้อหาบางส่วนภายในเอกสาร PDF

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยให้การแปลงขอบเขตเพจเฉพาะเป็น DOM ได้อย่างไร

ตอบ: Aspose.PDF สำหรับ .NET มีกระบวนการทีละขั้นตอนเพื่อกำหนดขอบเขตของหน้าที่ต้องการ ตั้งค่าพื้นที่ครอบตัด บันทึกเอกสาร PDF ที่ครอบตัดลงในสตรีม และแปลงขอบเขตของหน้าที่ระบุเป็นรูปภาพ

#### ถาม: เหตุใดการกำหนดไดเร็กทอรีเอกสารก่อนเริ่มกระบวนการแปลงจึงเป็นสิ่งสำคัญ

ตอบ: การระบุไดเร็กทอรีเอกสารช่วยให้แน่ใจว่าเอกสาร PDF และรูปภาพที่ได้นั้นอยู่ในเส้นทางเอาต์พุตที่ต้องการอย่างถูกต้อง

####  ถาม: เป็นยังไงบ้าง`Document` class in Aspose.PDF for .NET help in the conversion process?

 ตอบ:`Document` class ช่วยให้คุณสามารถเปิด จัดการ และบันทึกเอกสาร PDF ได้ ในกรณีนี้ จะใช้ในการโหลดเอกสาร PDF และสร้างเวอร์ชันที่ครอบตัด

####  ถาม: จุดประสงค์ของ.`Rectangle` class in the page region conversion process?

 ตอบ:`Rectangle` คลาสกำหนดพิกัดของภูมิภาคเฉพาะบนหน้า PDF ที่คุณต้องการแปลงเป็น DOM ช่วยในการระบุพื้นที่เพาะปลูกได้อย่างแม่นยำ

#### ถาม: พื้นที่ครอบตัดของเพจถูกตั้งค่าเป็นภูมิภาคที่ต้องการในกระบวนการแปลงอย่างไร

 ตอบ:`CropBox` ทรัพย์สินของ`Page` วัตถุใช้เพื่อกำหนดพื้นที่ครอบตัดของหน้าให้เป็นสี่เหลี่ยมที่กำหนดซึ่งเป็นตัวแทนของภูมิภาคเฉพาะ

#### ถาม: เอกสาร PDF ที่ครอบตัดจะถูกบันทึกลงในสตรีมในระหว่างกระบวนการแปลงอย่างไร

 ตอบ: เอกสาร PDF ที่ครอบตัดจะถูกบันทึกลงใน`MemoryStream` วัตถุซึ่งช่วยให้สามารถจัดการเนื้อหา PDF ได้อย่างมีประสิทธิภาพ

####  ถาม: มีบทบาทอะไร`PngDevice` class play in the page region to DOM conversion process?

 ตอบ:`PngDevice` class ช่วยแปลงเอกสาร PDF ที่ครอบตัดเป็นรูปแบบรูปภาพ เช่น PNG ช่วยให้คุณเห็นภาพขอบเขตของหน้าเฉพาะ

#### ถาม: ฉันสามารถปรับความละเอียดหรือคุณสมบัติอื่นๆ ของภาพที่ได้ในระหว่างขั้นตอนการแปลงได้หรือไม่

 ตอบ: ได้ คุณสามารถแก้ไขความละเอียดและคุณลักษณะอื่นๆ ของภาพที่ได้โดยการกำหนดค่า`PngDevice` วัตถุก่อนที่จะแปลงเพจ