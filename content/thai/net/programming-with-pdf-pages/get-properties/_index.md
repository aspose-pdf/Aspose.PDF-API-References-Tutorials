---
title: รับคุณสมบัติ PDF
linktitle: รับคุณสมบัติ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: คู่มือทีละขั้นตอนในการรับคุณสมบัติ PDF เช่น ขนาดกล่องและการหมุนโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 100
url: /th/net/programming-with-pdf-pages/get-properties/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณทีละขั้นตอนในการรับคุณสมบัติของ PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายโค้ดต้นฉบับ C# ที่รวมมา และให้คำแนะนำที่ครอบคลุมแก่คุณเพื่อช่วยให้คุณเข้าใจและนำฟีเจอร์นี้ไปใช้ในโครงการของคุณเอง เมื่อจบบทช่วยสอนนี้ คุณจะทราบวิธีการเข้าถึงคุณสมบัติต่างๆ ของหน้า PDF เช่น กล่องงานศิลป์ กล่องครอป กล่องครอป ฯลฯ โดยใช้ Aspose.PDF สำหรับ .NET

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- Aspose.PDF สำหรับ .NET ติดตั้งอยู่ในสภาพแวดล้อมการพัฒนาของคุณ

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่คือตำแหน่งของไฟล์ PDF ที่คุณต้องการรับคุณสมบัติ แทนที่ "YOUR DOCUMENTS DIRECTORY" ด้วยเส้นทางที่เหมาะสม

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดเอกสาร PDF
 ขั้นต่อไปคุณต้องเปิดเอกสาร PDF โดยใช้`Document` คลาสของ Aspose.PDF โปรดระบุเส้นทางที่ถูกต้องไปยังไฟล์ PDF

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## ขั้นตอนที่ 3: เข้าถึงคอลเลกชันหน้า
 ตอนนี้คุณสามารถเข้าถึงคอลเลกชันหน้าเอกสารได้โดยใช้`Pages` ทรัพย์สินของ`pdfDocument` วัตถุ.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## ขั้นตอนที่ 4: ไปที่หน้าเฉพาะ
จากนั้นคุณสามารถข้ามไปยังหน้าที่ต้องการโดยใช้ดัชนีของหน้าในคอลเล็กชัน ในตัวอย่างด้านล่าง เราจะเข้าถึงหน้าที่สอง (ดัชนี 1)

```csharp
Page pdfPage = pageCollection[1];
```

## ขั้นตอนที่ 5: รับคุณสมบัติของหน้า
 ตอนนี้คุณสามารถรับคุณสมบัติต่างๆ ของหน้า PDF เช่น กล่องศิลปะ กล่องครอป กล่องครอป ฯลฯ ได้โดยใช้คุณสมบัติที่สอดคล้องกันของ`pdfPage` วัตถุ.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### ตัวอย่างโค้ดที่มาสำหรับรับคุณสมบัติโดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// รับรวบรวมหน้าเพจ
PageCollection pageCollection = pdfDocument.Pages;
// รับหน้าเฉพาะ
Page pdfPage = pageCollection[1];
// รับคุณสมบัติของหน้า
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## บทสรุป
ขอแสดงความยินดี! คุณได้รับคุณสมบัติของ PDF สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET คุณได้เรียนรู้วิธีเปิดเอกสาร PDF นำทางไปยังหน้าเฉพาะ และรับคุณสมบัติต่างๆ ของหน้า เช่น กล่องมิติและการหมุน ตอนนี้คุณสามารถใช้ข้อมูลนี้เพื่อปรับแต่งการจัดการไฟล์ PDF ของคุณตามคุณสมบัติของไฟล์ได้แล้ว

อย่าลืมตรวจดูเอกสาร Aspose.PDF อย่างเป็นทางการสำหรับ .NET เพื่อดูข้อมูลเพิ่มเติมเกี่ยวกับคุณลักษณะขั้นสูงและความเป็นไปได้ในการปรับแต่ง

### คำถามที่พบบ่อย

#### ถาม: ฉันจะรับคุณสมบัติของ PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการรับคุณสมบัติของ PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถทำตามขั้นตอนเหล่านี้:

1. ตั้งค่าไดเรกทอรีเอกสารโดยระบุเส้นทางไปยังไฟล์ PDF ที่มีคุณสมบัติที่คุณต้องการดึงข้อมูล
2.  เปิดเอกสาร PDF โดยใช้`Document` คลาสของ Aspose.PDF ซึ่งให้เส้นทางที่ถูกต้องไปยังไฟล์ PDF
3.  เข้าถึงคอลเลกชันหน้าเอกสารโดยใช้`Pages` ทรัพย์สินของ`pdfDocument` วัตถุ.
4. ข้ามไปยังหน้าที่ระบุโดยใช้ดัชนีของหน้าในคอลเล็กชั่น (การสร้างดัชนีเริ่มจาก 1)
5.  รับคุณสมบัติต่างๆ ของหน้า PDF เช่น ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number และ Rotation โดยใช้คุณสมบัติที่สอดคล้องกันของ`pdfPage` วัตถุ.

#### ถาม: คุณสมบัติที่แตกต่างกันของหน้า PDF ที่ฉันสามารถเรียกค้นโดยใช้ Aspose.PDF สำหรับ .NET มีอะไรบ้าง

A: คุณสามารถดึงคุณสมบัติต่างๆ ของหน้า PDF ได้โดยใช้ Aspose.PDF สำหรับ .NET เช่น:

- ArtBox: แสดงขนาดของงานศิลปะของหน้า
- BleedBox: แสดงขนาดของขอบตกของหน้า
- CropBox: แสดงขนาดของเนื้อหาที่มองเห็นได้ของหน้าหลังจากการครอบตัด
- MediaBox: แสดงขนาดของสื่อทางกายภาพของหน้า
- TrimBox: แสดงขนาดของเนื้อหาที่ถูกตัดของหน้า
- สี่เหลี่ยม: แสดงขนาดของกรอบขอบเขตของหน้า
- หมายเลขหน้า: หมายถึงหมายเลขหน้าในเอกสาร
- หมุน: หมายถึงมุมการหมุนของหน้า

#### ถาม: ฉันจะเข้าถึงหน้าเฉพาะในเอกสาร PDF เพื่อดึงคุณสมบัติของมันได้อย่างไร

 ก: หากต้องการเข้าถึงหน้าเฉพาะในเอกสาร PDF และดึงคุณสมบัติของหน้านั้น คุณสามารถใช้`Pages` ทรัพย์สินของ`pdfDocument` วัตถุเพื่อเข้าถึงคอลเลกชันหน้าของเอกสาร จากนั้นคุณสามารถใช้ดัชนีของหน้าในคอลเลกชันเพื่อข้ามไปยังหน้าที่ต้องการ ตัวอย่างเช่น หากต้องการเข้าถึงหน้าที่สอง คุณสามารถใช้`pdfDocument.Pages[1]` (การจัดทำดัชนีเริ่มจาก 1)

#### ถาม: ฉันสามารถดำเนินการกับคุณสมบัติที่เรียกค้นได้ เช่น การแก้ไขหรือปรับขนาดกล่องหน้าได้หรือไม่

A: ใช่ เมื่อคุณเรียกค้นคุณสมบัติของหน้า PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถดำเนินการต่างๆ กับคุณสมบัติเหล่านั้นได้ ตัวอย่างเช่น คุณสามารถปรับเปลี่ยนขนาดของกล่องหน้า หมุนหน้า หรือใช้ข้อมูลที่เรียกค้นมาเพื่อประมวลผลและจัดการเอกสาร PDF แบบกำหนดเอง

#### ถาม: Aspose.PDF สำหรับ .NET รองรับการแยกคุณสมบัติจากไฟล์ PDF ที่เข้ารหัสหรือมีการป้องกันด้วยรหัสผ่านหรือไม่

A: ใช่ Aspose.PDF สำหรับ .NET รองรับการแยกคุณสมบัติจากไฟล์ PDF ที่เข้ารหัสหรือป้องกันด้วยรหัสผ่าน ตราบใดที่คุณระบุรหัสผ่านที่ถูกต้องเพื่อเปิดเอกสาร PDF คุณสามารถเข้าถึงและดึงคุณสมบัติโดยใช้แนวทางเดียวกับที่สาธิตในบทช่วยสอน