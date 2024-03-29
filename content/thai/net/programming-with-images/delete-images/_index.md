---
title: ลบรูปภาพออกจากไฟล์ PDF
linktitle: ลบรูปภาพออกจากไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: ลบรูปภาพออกจากไฟล์ PDF ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 110
url: /th/net/programming-with-images/delete-images/
---
คู่มือนี้จะแนะนำวิธีการลบรูปภาพออกจากไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ทีละขั้นตอน ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมของคุณแล้ว และทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไดเร็กทอรีที่ถูกต้องสำหรับเอกสาร แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดพร้อมเส้นทางไปยังไดเร็กทอรีที่มีเอกสาร PDF ของคุณอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดเอกสาร PDF

ในขั้นตอนนี้ เราจะเปิดเอกสาร PDF โดยใช้ไฟล์`Document` คลาสของ Aspose.PDF ใช้`Document` Constructor และส่งเส้นทางไปยังเอกสาร PDF

```csharp
Document pdfDocument = new Document(dataDir + "DeleteImages.pdf");

```

## ขั้นตอนที่ 3: ลบรูปภาพที่ต้องการ

 ในขั้นตอนนี้ เราจะลบรูปภาพเฉพาะออกจากหน้าใดหน้าหนึ่ง ใช้`Delete` วิธีการทรัพยากรหน้า`Images` วัตถุที่จะลบภาพ ในตัวอย่างด้านล่าง เราจะลบรูปภาพที่มีดัชนี 1 ออกจากหน้าแรก

```csharp
pdfDocument.Pages[1].Resources.Images.Delete(1);
```

## ขั้นตอนที่ 4: บันทึกไฟล์ PDF ที่อัปเดต

 บันทึกไฟล์ PDF ที่อัปเดตโดยใช้นามสกุล`Save` วิธีการของ`pdfDocument` วัตถุ. ระบุเส้นทางเอาต์พุตสำหรับไฟล์ PDF

```csharp
dataDir = dataDir + "DeleteImages_out.pdf";
pdfDocument.Save(dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับการลบรูปภาพโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir+ "DeleteImages.pdf");
// ลบภาพใดภาพหนึ่ง
pdfDocument.Pages[1].Resources.Images.Delete(1);
dataDir = dataDir + "DeleteImages_out.pdf";
// บันทึกไฟล์ PDF ที่อัปเดต
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages deleted successfully.\nFile saved at " + dataDir); 
```

## บทสรุป

ขอแสดงความยินดี! คุณได้ลบรูปภาพออกจากไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว ไฟล์ PDF ที่อัปเดตจะถูกบันทึกในไดเร็กทอรีที่ระบุ ตอนนี้คุณสามารถใช้ไฟล์ PDF นี้ได้โดยไม่ต้องลบรูปภาพ

### คำถามที่พบบ่อยสำหรับการลบภาพออกจากไฟล์ PDF

#### ถาม: จุดประสงค์ของการลบรูปภาพออกจากไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: การลบรูปภาพออกจากไฟล์ PDF สามารถช่วยให้คุณลบเนื้อหาภาพที่เฉพาะเจาะจงออกจากเอกสารได้ ไม่ว่าจะเพื่อการแก้ไข การเขียน หรือวัตถุประสงค์อื่น ๆ

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยในการลบรูปภาพออกจากเอกสาร PDF ได้อย่างไร

ตอบ: Aspose.PDF สำหรับ .NET มีกระบวนการทีละขั้นตอนในการเปิดเอกสาร PDF ระบุและลบรูปภาพที่ต้องการจากเอกสาร และบันทึกเอกสาร PDF ที่แก้ไขแล้ว

#### ถาม: เหตุใดการกำหนดไดเร็กทอรีเอกสารก่อนเริ่มการลบภาพจึงเป็นสิ่งสำคัญ

ตอบ: การกำหนดไดเร็กทอรีเอกสารช่วยให้แน่ใจว่าเอกสาร PDF อยู่ในตำแหน่งที่ถูกต้อง และไฟล์ PDF ที่แก้ไขแล้วจะถูกบันทึกในเส้นทางเอาต์พุตที่ต้องการ

####  ถาม: เป็นยังไงบ้าง`Document` class in Aspose.PDF for .NET help in deleting images from a PDF file?

 ตอบ:`Document`class ช่วยให้คุณสามารถเปิดและจัดการเอกสาร PDF ในกรณีนี้ ใช้สำหรับโหลดไฟล์ PDF ที่จะลบรูปภาพ

#### ถาม: ฉันจะเลือกรูปภาพที่ต้องการลบออกจากเอกสาร PDF ได้อย่างไร

ตอบ: คุณสามารถใช้`Delete` วิธีการของ`Images` วัตถุภายใน`Resources` ของหน้าใดหน้าหนึ่งเพื่อลบภาพใดภาพหนึ่งตามดัชนี

#### ถาม: ฉันสามารถลบรูปภาพออกจากหน้าใดก็ได้ในเอกสาร PDF ได้หรือไม่

ตอบ: ได้ คุณสามารถลบรูปภาพออกจากหน้าใดก็ได้ในเอกสาร PDF โดยระบุดัชนีหน้าที่ต้องการและดัชนีของรูปภาพที่จะลบ

#### ถาม: เป็นไปได้หรือไม่ที่จะลบภาพหลายภาพจากหน้าต่างๆ ในกระบวนการเดียว

 ตอบ: ได้ คุณสามารถใช้`Delete` วิธีการหลายหน้าเพื่อลบภาพออกจากหน้าต่างๆ ในกระบวนการเดียวกัน

#### ถาม: จะเกิดอะไรขึ้นกับเค้าโครงและการจัดรูปแบบของเอกสาร PDF หลังจากลบรูปภาพแล้ว

ตอบ: การลบรูปภาพอาจส่งผลต่อเค้าโครงและการจัดรูปแบบของเอกสาร PDF โดยเฉพาะอย่างยิ่งหากรูปภาพที่ถูกลบเป็นส่วนหนึ่งของเค้าโครงเนื้อหา