---
title: รับคุณสมบัติ PDF
linktitle: รับคุณสมบัติ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนเพื่อรับคุณสมบัติ PDF เช่น ขนาดกล่องและการหมุนโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 100
url: /th/net/programming-with-pdf-pages/get-properties/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อรับคุณสมบัติของ PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีเข้าถึงคุณสมบัติต่างๆ ของหน้า PDF เช่น กล่องศิลปะ กล่องครอบตัด กล่องครอบตัด ฯลฯ โดยใช้ Aspose.PDF สำหรับ .NET

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Aspose.PDF สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่คือตำแหน่งของไฟล์ PDF ที่มีคุณสมบัติที่คุณต้องการรับ แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางที่เหมาะสม

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดเอกสาร PDF
 ถัดไปคุณต้องเปิดเอกสาร PDF โดยใช้ไฟล์`Document` คลาสของ Aspose.PDF อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไฟล์ PDF

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## ขั้นตอนที่ 3: เข้าถึงคอลเลกชันหน้า
 ตอนนี้คุณสามารถเข้าถึงคอลเลกชันหน้าของเอกสารโดยใช้`Pages` ทรัพย์สินของ`pdfDocument` วัตถุ.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## ขั้นตอนที่ 4: ไปที่หน้าเฉพาะ
จากนั้นคุณสามารถข้ามไปยังหน้าใดหน้าหนึ่งได้โดยใช้ดัชนีของหน้าในคอลเลกชัน ในตัวอย่างด้านล่าง เราเข้าถึงหน้าที่สอง (ดัชนี 1)

```csharp
Page pdfPage = pageCollection[1];
```

## ขั้นตอนที่ 5: รับคุณสมบัติของเพจ
 ตอนนี้คุณสามารถรับคุณสมบัติต่างๆ ของหน้า PDF ได้ เช่น กล่องอาร์ต กล่องครอบตัด กล่องครอบตัด ฯลฯ โดยใช้คุณสมบัติที่สอดคล้องกันของ`pdfPage` วัตถุ.

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

### ตัวอย่างซอร์สโค้ดสำหรับรับคุณสมบัติโดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// รับคอลเลกชันเพจ
PageCollection pageCollection = pdfDocument.Pages;
// รับเฉพาะหน้า
Page pdfPage = pageCollection[1];
// รับคุณสมบัติหน้า
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
ขอแสดงความยินดี! คุณได้รับคุณสมบัติของ PDF โดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว คุณได้เรียนรู้วิธีเปิดเอกสาร PDF นำทางไปยังหน้าใดหน้าหนึ่ง และรับคุณสมบัติของหน้าต่างๆ เช่น กล่องมิติและการหมุน ตอนนี้คุณสามารถใช้ข้อมูลนี้เพื่อปรับแต่งการจัดการไฟล์ PDF ของคุณตามคุณสมบัติได้

อย่าลืมตรวจสอบเอกสารอย่างเป็นทางการของ Aspose.PDF สำหรับ .NET เพื่อดูข้อมูลเพิ่มเติมเกี่ยวกับคุณสมบัติขั้นสูงและความเป็นไปได้ในการปรับแต่ง

### คำถามที่พบบ่อย

#### ถาม: ฉันจะรับคุณสมบัติของ PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการรับคุณสมบัติของ PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถทำตามขั้นตอนเหล่านี้:

1. ตั้งค่าไดเร็กทอรีเอกสารโดยระบุเส้นทางไปยังไฟล์ PDF ที่มีคุณสมบัติที่คุณต้องการดึงข้อมูล
2.  เปิดเอกสาร PDF โดยใช้ไฟล์`Document` คลาสของ Aspose.PDF ซึ่งจัดเตรียมเส้นทางที่ถูกต้องไปยังไฟล์ PDF
3.  เข้าถึงคอลเลกชันหน้าของเอกสารโดยใช้`Pages` ทรัพย์สินของ`pdfDocument` วัตถุ.
4. ข้ามไปยังหน้าใดหน้าหนึ่งโดยใช้ดัชนีของหน้าในคอลเลกชัน (การจัดทำดัชนีเริ่มต้นจาก 1)
5.  รับคุณสมบัติต่างๆ ของหน้า PDF เช่น ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number และ Rotation โดยใช้คุณสมบัติที่เกี่ยวข้องของ`pdfPage` วัตถุ.

#### ถาม: คุณสมบัติต่างๆ ของหน้า PDF ที่ฉันสามารถดึงข้อมูลโดยใช้ Aspose.PDF สำหรับ .NET มีอะไรบ้าง

ตอบ: คุณสามารถดึงคุณสมบัติต่างๆ ของหน้า PDF ได้โดยใช้ Aspose.PDF สำหรับ .NET เช่น:

- ArtBox: แสดงถึงขนาดของอาร์ตเวิร์กของเพจ
- BleedBox: แสดงถึงขนาดของการตัดตกของหน้า
- CropBox: แสดงขนาดของเนื้อหาที่มองเห็นได้ของหน้าหลังจากการครอบตัด
- MediaBox: แสดงถึงขนาดของสื่อทางกายภาพของเพจ
- TrimBox: แสดงขนาดของเนื้อหาที่ถูกตัดแต่งของหน้า
- Rect: แสดงขนาดของกรอบขอบของหน้า
- หมายเลขหน้า: หมายถึงหมายเลขหน้าในเอกสาร
- หมุน: แสดงถึงมุมการหมุนของหน้า

#### ถาม: ฉันจะเข้าถึงหน้าเฉพาะในเอกสาร PDF เพื่อดึงคุณสมบัติได้อย่างไร

 ตอบ: หากต้องการเข้าถึงหน้าใดหน้าหนึ่งในเอกสาร PDF และดึงข้อมูลคุณสมบัติของหน้านั้น คุณสามารถใช้`Pages` ทรัพย์สินของ`pdfDocument` วัตถุเพื่อเข้าถึงคอลเลกชันหน้าของเอกสาร จากนั้น คุณสามารถใช้ดัชนีของเพจในคอลเลกชันเพื่อข้ามไปยังเพจที่ต้องการได้ ตัวอย่างเช่นหากต้องการเข้าถึงหน้าที่สองคุณสามารถใช้`pdfDocument.Pages[1]` (การจัดทำดัชนีเริ่มต้นจาก 1)

#### ถาม: ฉันสามารถดำเนินการกับคุณสมบัติที่ดึงมา เช่น การแก้ไขหรือปรับขนาดกล่องเพจได้หรือไม่

ตอบ: ได้ เมื่อคุณดึงข้อมูลคุณสมบัติของหน้า PDF โดยใช้ Aspose.PDF สำหรับ .NET แล้ว คุณสามารถดำเนินการต่างๆ กับคุณสมบัติเหล่านั้นได้ ตัวอย่างเช่น คุณสามารถแก้ไขขนาดของกล่องหน้า หมุนหน้า หรือใช้ข้อมูลที่ดึงมาเพื่อการประมวลผลและการจัดการเอกสาร PDF แบบกำหนดเองได้

#### ถาม: Aspose.PDF สำหรับ .NET รองรับการแยกคุณสมบัติออกจากไฟล์ PDF ที่เข้ารหัสหรือป้องกันด้วยรหัสผ่านหรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET รองรับการแยกคุณสมบัติออกจากไฟล์ PDF ที่เข้ารหัสหรือป้องกันด้วยรหัสผ่าน ตราบใดที่คุณระบุรหัสผ่านที่ถูกต้องเพื่อเปิดเอกสาร PDF คุณสามารถเข้าถึงและดึงคุณสมบัติของมันได้โดยใช้วิธีการเดียวกันกับที่แสดงไว้ในบทช่วยสอน