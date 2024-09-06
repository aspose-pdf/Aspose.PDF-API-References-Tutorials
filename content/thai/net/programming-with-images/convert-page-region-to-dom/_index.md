---
title: แปลงภูมิภาคหน้าเป็น DOM
linktitle: แปลงภูมิภาคหน้าเป็น DOM
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: แปลงพื้นที่เฉพาะของหน้า PDF เป็น Document Object Model (DOM) ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 80
url: /th/net/programming-with-images/convert-page-region-to-dom/
---
คู่มือนี้จะแนะนำคุณทีละขั้นตอนเกี่ยวกับการแปลงพื้นที่เฉพาะของหน้าเป็น Document Object Model (DOM) โดยใช้ Aspose.PDF สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมของคุณแล้ว และทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอกสาร

ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไดเรกทอรีที่ถูกต้องสำหรับเอกสารแล้ว แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดพร้อมเส้นทางไปยังไดเร็กทอรีที่เอกสาร PDF ของคุณอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดเอกสาร

 ในขั้นตอนนี้เราจะเปิดเอกสาร PDF โดยใช้`Document` คลาสของ Aspose.PDF ใช้`Document` สร้างและส่งเส้นทางไปยังเอกสาร PDF

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## ขั้นตอนที่ 3: รับสี่เหลี่ยมผืนผ้าภูมิภาคหน้า

 ในขั้นตอนนี้ เราจะกำหนดสี่เหลี่ยมผืนผ้าที่แสดงพื้นที่เฉพาะของเพจที่เราต้องการแปลงเป็น DOM ใช้`Aspose.Pdf.Rectangle` คลาสเพื่อกำหนดพิกัดของรูปสี่เหลี่ยมผืนผ้า

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## ขั้นตอนที่ 4: กำหนดพื้นที่ครอบตัดของหน้า

 ใช้`CropBox` ทรัพย์สินของ`Page` วัตถุที่จะตั้งค่ากล่องครอบตัดของหน้าให้อยู่ในรูปสี่เหลี่ยมผืนผ้าตามภูมิภาคที่ต้องการ

```csharp
document.Pages[1].CropBox = pageRect;
```

## ขั้นตอนที่ 5: บันทึกเอกสาร PDF ที่ครอบตัดลงในสตรีม

 ในขั้นตอนนี้เราจะบันทึกเอกสาร PDF ที่ถูกครอบตัดลงในสตรีมโดยใช้`MemoryStream` ระดับ.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## ขั้นตอนที่ 6: เปิดเอกสาร PDF ที่ครอบตัดแล้วและแปลงเป็นรูปภาพ

 เปิดเอกสาร PDF ที่ครอบตัดโดยใช้`Document`แล้วแปลงเป็นรูปภาพ โดยเราจะใช้ความละเอียด 300 dpi

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## ขั้นตอนที่ 7: แปลงหน้าเฉพาะเป็นรูปภาพ

 แปลงหน้าเฉพาะเป็นรูปภาพโดยใช้`Process` วิธีการของ`pngDevice` วัตถุ ระบุเส้นทางเอาท์พุตของภาพ

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการแปลงภูมิภาคหน้าเป็น DOM โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document document = new Document( dataDir + "AddImage.pdf");
// รับสี่เหลี่ยมของพื้นที่หน้าเฉพาะ
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
// ตั้งค่า CropBox ตามสี่เหลี่ยมผืนผ้าของพื้นที่หน้าที่ต้องการ
document.Pages[1].CropBox = pageRect;
// บันทึกเอกสารที่ครอบตัดลงในสตรีม
MemoryStream ms = new MemoryStream();
document.Save(ms);
// เปิดเอกสาร PDF ที่ครอบตัดแล้วและแปลงเป็นรูปภาพ
document = new Document(ms);
// สร้างวัตถุความละเอียด
Resolution resolution = new Resolution(300);
// สร้างอุปกรณ์ PNG ที่มีคุณลักษณะที่ระบุ
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// แปลงหน้าใดหน้าหนึ่งและบันทึกภาพลงในสตรีม
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## บทสรุป

ขอแสดงความยินดี! คุณได้แปลงพื้นที่เฉพาะของหน้าเป็น Document Object Model (DOM) สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET รูปภาพที่ได้จะถูกบันทึกไว้ในไดเร็กทอรีที่ระบุ ตอนนี้คุณสามารถใช้รูปภาพนี้ในโครงการหรือแอปพลิเคชันของคุณได้แล้ว

## คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของการแปลงภูมิภาคเฉพาะของหน้าให้เป็น Document Object Model (DOM) โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ การแปลงพื้นที่เฉพาะของหน้า PDF ให้เป็น Document Object Model (DOM) อาจเป็นประโยชน์ในการแยกและจัดการเนื้อหาส่วนใดส่วนหนึ่งในเอกสาร PDF

#### ถาม: Aspose.PDF สำหรับ .NET อำนวยความสะดวกในการแปลงภูมิภาคหน้าเฉพาะไปเป็น DOM ได้อย่างไร

A: Aspose.PDF สำหรับ .NET ให้กระบวนการทีละขั้นตอนในการกำหนดขอบเขตหน้าที่ต้องการ ตั้งค่าพื้นที่ครอป บันทึกเอกสาร PDF ที่ถูกครอบตัดไปยังสตรีม และแปลงขอบเขตหน้าที่ระบุเป็นรูปภาพ

#### ถาม: เหตุใดการกำหนดไดเรกทอรีเอกสารจึงสำคัญก่อนที่จะเริ่มกระบวนการแปลง?

A: การระบุไดเร็กทอรีเอกสารจะช่วยให้มั่นใจได้ว่าเอกสาร PDF และรูปภาพผลลัพธ์จะอยู่ในเส้นทางเอาต์พุตที่ต้องการอย่างถูกต้อง

####  ถาม: ทำอย่างไร`Document` class in Aspose.PDF for .NET help in the conversion process?

 ก. การ`Document` คลาสนี้ช่วยให้คุณสามารถเปิด จัดการ และบันทึกเอกสาร PDF ได้ ในกรณีนี้ คลาสนี้จะใช้เพื่อโหลดเอกสาร PDF และสร้างเวอร์ชันที่ครอบตัดของเอกสารนั้น

####  ถาม: จุดประสงค์ของการ`Rectangle` class in the page region conversion process?

 ก. การ`Rectangle`คลาสจะกำหนดพิกัดของพื้นที่เฉพาะบนหน้า PDF ที่คุณต้องการแปลงเป็น DOM ช่วยในการระบุพื้นที่ครอปได้อย่างแม่นยำ

#### ถาม: พื้นที่ครอบตัดของหน้าจะถูกตั้งค่าให้เป็นพื้นที่ที่ต้องการในกระบวนการแปลงอย่างไร

 ก. การ`CropBox` ทรัพย์สินของ`Page` วัตถุนี้ใช้ในการตั้งค่าพื้นที่ครอบตัดของหน้าให้เป็นรูปสี่เหลี่ยมผืนผ้าที่กำหนดซึ่งแสดงถึงพื้นที่เฉพาะ

#### ถาม: เอกสาร PDF ที่ถูกครอบตัดจะถูกบันทึกไปยังสตรีมในระหว่างกระบวนการแปลงอย่างไร

 A: เอกสาร PDF ที่ครอบตัดจะถูกบันทึกไว้ใน`MemoryStream` วัตถุซึ่งช่วยให้สามารถจัดการเนื้อหา PDF ได้อย่างมีประสิทธิภาพ

####  ถาม: บทบาทหน้าที่คืออะไร`PngDevice` class play in the page region to DOM conversion process?

 ก. การ`PngDevice` คลาสช่วยแปลงเอกสาร PDF ที่ถูกครอบตัดให้เป็นรูปแบบรูปภาพ เช่น PNG ช่วยให้คุณมองเห็นพื้นที่หน้าเฉพาะได้

#### ถาม: ฉันสามารถปรับความละเอียดหรือคุณลักษณะอื่น ๆ ของรูปภาพผลลัพธ์ระหว่างกระบวนการแปลงได้หรือไม่

 A: ใช่ คุณสามารถปรับเปลี่ยนความละเอียดและคุณลักษณะอื่น ๆ ของภาพที่ได้ โดยการกำหนดค่า`PngDevice` วัตถุก่อนที่จะแปลงหน้า