---
title: ตั้งค่าคุณสมบัติสำหรับไดอะล็อกการพิมพ์
linktitle: ตั้งค่าคุณสมบัติสำหรับไดอะล็อกการพิมพ์
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีตั้งค่าคุณสมบัติสำหรับกล่องโต้ตอบการพิมพ์ใน Aspose.PDF สำหรับ .NET โดยใช้คำแนะนำทีละขั้นตอน
type: docs
weight: 320
url: /th/net/programming-with-document/setpropertiesforprintdialog/
---
ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนสำหรับการตั้งค่าคุณสมบัติสำหรับกล่องโต้ตอบการพิมพ์โดยใช้ Aspose.PDF สำหรับ .NET:


## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีที่มีเอกสาร PDF ของคุณอยู่:

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";
```
   
##  ขั้นตอนที่ 2: สร้างอินสแตนซ์ใหม่ของ`Document` class:

```csharp
using (Document doc = new Document())
{
  // รหัสที่นี่
}
```
   
## ขั้นตอนที่ 3: เพิ่มหน้าใหม่ให้กับเอกสาร:

```csharp
doc.Pages.Add();
```
   
##  ขั้นตอนที่ 4: ตั้งค่าคุณสมบัติดูเพล็กซ์เป็น`DuplexFlipLongEdge`:

```csharp
doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
```
   
## ขั้นตอนที่ 5: บันทึกเอกสารด้วยชื่อไฟล์และรูปแบบที่ระบุ:

```csharp
doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
```

### ตัวอย่างซอร์สโค้ดสำหรับ Set Properties For Print Dialog โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document doc = new Document())
{
	doc.Pages.Add();
	doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
	doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
}
```

## บทสรุป

Aspose.PDF สำหรับ .NET ทำให้การตั้งค่าคุณสมบัติสำหรับกล่องโต้ตอบการพิมพ์ในไฟล์ PDF ของคุณเป็นเรื่องง่าย ด้วยการทำตามคำแนะนำทีละขั้นตอนข้างต้น คุณสามารถเพิ่มประสิทธิภาพไฟล์ PDF ของคุณสำหรับการพิมพ์ได้อย่างรวดเร็ว

### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถตั้งค่าคุณสมบัติไดอะล็อกการพิมพ์อื่นๆ นอกเหนือจากโหมดดูเพล็กซ์โดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ: ได้ นอกจากการตั้งค่าโหมดดูเพล็กซ์แล้ว Aspose.PDF สำหรับ .NET ยังช่วยให้คุณตั้งค่าคุณสมบัติอื่นๆ มากมายสำหรับกล่องโต้ตอบการพิมพ์ได้ ตัวอย่างบางส่วนได้แก่ การตั้งค่าคุณภาพการพิมพ์ ช่วงหน้า จำนวนสำเนา ขนาดกระดาษ และอื่นๆ คุณสามารถดูเอกสารประกอบ Aspose.PDF สำหรับ .NET เพื่อสำรวจรายการคุณสมบัติทั้งหมดที่มีอยู่

#### ถาม: ฉันจะตั้งค่าคุณภาพการพิมพ์เมื่อพิมพ์เอกสาร PDF ได้อย่างไร

 ตอบ: หากต้องการตั้งค่าคุณภาพการพิมพ์ คุณสามารถใช้`PrintQuality` ทรัพย์สินของ`Document` คลาสใน Aspose.PDF สำหรับ .NET คุณสามารถเลือกจากตัวเลือกคุณภาพการพิมพ์ที่แตกต่างกัน เช่น สูง ปานกลาง หรือต่ำ ตามความต้องการของคุณ

#### ถาม: สามารถระบุการตั้งค่าการพิมพ์แบบกำหนดเองสำหรับหน้าต่างๆ ในเอกสาร PDF ได้หรือไม่

 ตอบ: ได้ คุณสามารถตั้งค่าการพิมพ์แบบกำหนดเองสำหรับหน้าต่างๆ ในเอกสาร PDF ได้โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถเข้าถึงแต่ละหน้าได้ผ่านทาง`doc.Pages` รวบรวมและตั้งค่าการพิมพ์เฉพาะสำหรับแต่ละหน้าแยกกัน