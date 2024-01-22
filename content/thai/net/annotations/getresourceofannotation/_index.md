---
title: รับทรัพยากรของคำอธิบายประกอบ
linktitle: รับทรัพยากรของคำอธิบายประกอบ
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีดึงทรัพยากรของคำอธิบายประกอบโดยใช้ Aspose.PDF สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนนี้
type: docs
weight: 90
url: /th/net/annotations/getresourceofannotation/
---
ตัวอย่างนี้แสดงวิธีการรับทรัพยากรของคำอธิบายประกอบด้วย Aspose.PDF สำหรับ .NET หากต้องการรับทรัพยากรของคำอธิบายประกอบโดยใช้ Aspose.PDF สำหรับ .NET ให้ทำตามขั้นตอนเหล่านี้:

## ขั้นตอนที่ 1: กำหนดเส้นทางของไดเร็กทอรีที่มีเอกสารอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดเอกสาร PDF ที่มีคำอธิบายประกอบซึ่งมีทรัพยากรที่คุณต้องการรับ

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## ขั้นตอนที่ 3: สร้างคำอธิบายประกอบ

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## ขั้นตอนที่ 4: เพิ่มคำอธิบายประกอบลงในหน้าในเอกสาร

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## ขั้นตอนที่ 5: บันทึกเอกสาร

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## ขั้นตอนที่ 6: เปิดเอกสารที่แก้ไข

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## ขั้นตอนที่ 7: รับการดำเนินการของคำอธิบายประกอบ

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## ขั้นตอนที่ 7: รับการกระทำของการกระทำ

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## ขั้นตอนที่ 8: รับคลิปสื่อ

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## ขั้นตอนที่ 9: รับข้อกำหนดคุณสมบัติไฟล์

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## ขั้นตอนที่ 10: อ่านข้อมูลของสื่อ

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## ขั้นตอนที่ 11: พิมพ์ชื่อของการเรนเดอร์และการดำเนินการเรนเดอร์

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถรับทรัพยากรของคำอธิบายประกอบในเอกสาร PDF ได้อย่างง่ายดายโดยใช้ Aspose.PDF สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับรับทรัพยากรของคำอธิบายประกอบโดยใช้ Aspose.PDF สำหรับ .NET:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// เปิดเอกสาร
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//สร้างคำอธิบายประกอบ
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// บันทึกเอกสาร
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// เปิดเอกสาร
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//รับการดำเนินการของคำอธิบายประกอบ
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//รับการกระทำของการกระทำการเรนเดอร์
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// คลิปสื่อ
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//ข้อมูลของสื่อสามารถเข้าถึงได้ใน FileSpecification.Contents
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีรับทรัพยากรของคำอธิบายประกอบเฉพาะจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ด C# ที่ให้มา นักพัฒนาจะสามารถเข้าถึงและจัดการคำอธิบายประกอบ รวมถึงคำอธิบายประกอบเวอร์ชันเรนเดอร์ในเอกสาร PDF ได้อย่างง่ายดาย

### คำถามที่พบบ่อย

#### ถาม: การแปลความหมายในบริบทของคำอธิบายประกอบ PDF คืออะไร

ตอบ: ในบริบทของคำอธิบายประกอบ PDF การแปลความหมายคือการนำเสนอเนื้อหามัลติมีเดีย ช่วยให้สามารถฝังมัลติมีเดีย เช่น เสียงหรือวิดีโอ ภายในเอกสาร PDF คำอธิบายประกอบการเรนเดอร์ระบุสื่อที่จะนำเสนอและวิธีการเล่น

#### ถาม: ฉันสามารถรับชื่อไฟล์มีเดียที่เกี่ยวข้องกับคำอธิบายประกอบการเรนดิชั่นได้หรือไม่

ตอบ: ได้ คุณสามารถรับชื่อไฟล์สื่อที่เกี่ยวข้องกับคำอธิบายประกอบการแปลความหมายได้โดยใช้ Aspose.PDF สำหรับ .NET ชื่อไฟล์มีเดียสามารถเข้าถึงได้ผ่านทาง`FileSpecification` ของ`MediaClip` วัตถุ.

#### ถาม: Aspose.PDF สำหรับ .NET สามารถแยกไฟล์มีเดียจากคำอธิบายประกอบเวอร์ชันได้หรือไม่

ตอบ: ได้ Aspose.PDF สำหรับ .NET สามารถแยกข้อมูลสื่อออกจากคำอธิบายประกอบเวอร์ชันเรนเดอร์ ซึ่งรวมถึงเนื้อหาเสียงหรือวิดีโอ และบันทึกเป็นไฟล์แยกต่างหาก

#### ถาม: ฉันจะเข้าถึงข้อมูลสื่อของคำอธิบายประกอบเวอร์ชันได้อย่างไร

 ตอบ: ข้อมูลสื่อของคำอธิบายประกอบการแปลสามารถเข้าถึงได้ผ่านทาง`FileSpecification.Contents` ทรัพย์สินของ`MediaClipData` วัตถุ.

#### ถาม: ฉันสามารถแก้ไขสื่อที่เกี่ยวข้องกับคำอธิบายประกอบการแสดงผลโดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ: Aspose.PDF สำหรับ .NET มีวิธีการเข้าถึงและแก้ไขข้อมูลสื่อที่เกี่ยวข้องกับคำอธิบายประกอบการแปลความหมาย คุณสามารถอัปเดตหรือแทนที่ไฟล์สื่อที่ใช้โดยคำอธิบายประกอบเวอร์ชันสื่อได้