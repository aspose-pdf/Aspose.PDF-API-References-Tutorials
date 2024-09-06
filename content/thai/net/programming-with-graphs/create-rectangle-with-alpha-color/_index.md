---
title: สร้างสี่เหลี่ยมด้วยสีอัลฟ่า
linktitle: สร้างสี่เหลี่ยมด้วยสีอัลฟ่า
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีสร้างรูปสี่เหลี่ยมผืนผ้าที่มีสีโปร่งใสโดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนในการปรับแต่งความโปร่งใส
type: docs
weight: 60
url: /th/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
ในบทช่วยสอนนี้ เราจะพาคุณดูโค้ดต้นฉบับ C# ทีละขั้นตอนเพื่อสร้างสี่เหลี่ยมผืนผ้าที่มีสีอัลฟ่าโดยใช้ Aspose.PDF สำหรับ .NET

ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณก่อนเริ่มต้น นอกจากนี้ ควรมีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# ด้วย

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในซอร์สโค้ดที่ให้มา คุณต้องระบุไดเรกทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่ได้ เปลี่ยนตัวแปร "dataDir" เป็นไดเรกทอรีที่ต้องการ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างวัตถุเอกสารและการเพิ่มหน้า

เราสร้างอินสแตนซ์ของคลาส Document และเพิ่มหน้าลงในเอกสารนี้

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 3: การสร้างวัตถุกราฟและสี่เหลี่ยมผืนผ้า

เราสร้างวัตถุ Graph ที่มีมิติที่ระบุและสี่เหลี่ยมผืนผ้าที่มีมิติเฉพาะเจาะจง

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## ขั้นตอนที่ 4: ตั้งค่าสีอัลฟ่าสำหรับสี่เหลี่ยมผืนผ้า

เราสามารถระบุสีอัลฟ่าให้กับสี่เหลี่ยมได้โดยใช้เมธอด FromArgb ของคลาส System.Drawing.Color

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## ขั้นตอนที่ 5: การเพิ่มสี่เหลี่ยมผืนผ้าลงในวัตถุกราฟ

เราเพิ่มรูปสี่เหลี่ยมผืนผ้าลงในคอลเล็กชั่นรูปร่างของวัตถุ Graph

```csharp
canvas.Shapes.Add(rect);
```

## ขั้นตอนที่ 6: สร้างสี่เหลี่ยมผืนผ้าที่สองโดยใช้สีอัลฟ่าที่แตกต่างกัน

เราสร้างสี่เหลี่ยมผืนผ้าที่สองที่มีขนาดเฉพาะและสีอัลฟ่าอื่น

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## ขั้นตอนที่ 7: การเพิ่มวัตถุกราฟลงในหน้า

เราเพิ่มวัตถุ Graph ลงในคอลเล็กชั่นย่อหน้าของวัตถุ Page

```csharp
page.Paragraphs.Add(canvas);
```

## ขั้นตอนที่ 8: บันทึกไฟล์ PDF ที่ได้

ในที่สุด เราบันทึกไฟล์ PDF ผลลัพธ์ด้วยชื่อ "CreateRectangleWithAlphaColor_out.pdf" ในไดเร็กทอรีที่ระบุ

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการสร้างสี่เหลี่ยมผืนผ้าด้วยสีอัลฟ่าโดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างอินสแตนซ์เอกสาร
Document doc = new Document();
// เพิ่มหน้าเข้าไปยังคอลเลคชันไฟล์ PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// สร้างอินสแตนซ์กราฟ
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// สร้างวัตถุรูปสี่เหลี่ยมผืนผ้าที่มีขนาดเฉพาะเจาะจง
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// ตั้งค่าสีเติมกราฟจากโครงสร้าง System.Drawing.Color จากค่า ARGB 32 บิต
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// เพิ่มวัตถุสี่เหลี่ยมผืนผ้าลงในคอลเล็กชั่นรูปร่างของอินสแตนซ์กราฟ
canvas.Shapes.Add(rect);
// สร้างวัตถุสี่เหลี่ยมผืนผ้าที่สอง
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// เพิ่มอินสแตนซ์กราฟลงในคอลเล็กชั่นย่อหน้าของวัตถุหน้า
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// บันทึกไฟล์ PDF
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายวิธีการสร้างรูปสี่เหลี่ยมผืนผ้าด้วยสีอัลฟ่าโดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้ความรู้เหล่านี้เพื่อสร้างรูปทรงเรขาคณิตด้วยสีโปร่งใสในไฟล์ PDF ของคุณได้แล้ว

## คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้คืออะไร?

A: บทช่วยสอนนี้มีวัตถุประสงค์เพื่อแนะนำคุณตลอดขั้นตอนการสร้างรูปสี่เหลี่ยมผืนผ้าด้วยสีอัลฟ่าโดยใช้ Aspose.PDF สำหรับ .NET คุณจะได้เรียนรู้วิธีการเพิ่มรูปทรงเรขาคณิตด้วยสีโปร่งใสลงในไฟล์ PDF ของคุณ

#### ถาม: มีข้อกำหนดเบื้องต้นอะไรบ้างก่อนเริ่มต้น?

A: ก่อนเริ่มต้น ให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณแล้ว นอกจากนี้ ขอแนะนำให้มีความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

#### ถาม: ฉันจะระบุไดเร็กทอรีสำหรับบันทึกไฟล์ PDF ได้อย่างไร

A: ในโค้ดต้นฉบับที่ให้มา คุณสามารถปรับเปลี่ยนตัวแปร "dataDir" เพื่อระบุไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ผลลัพธ์

#### ถาม: วัตถุประสงค์ของวัตถุกราฟและสี่เหลี่ยมผืนผ้าคืออะไร

A: วัตถุ Graph ทำหน้าที่เป็นตัวบรรจุองค์ประกอบการวาด ในขณะที่สี่เหลี่ยมผืนผ้าแสดงถึงรูปทรงเรขาคณิตที่คุณจะเพิ่มลงใน PDF

#### ถาม: ฉันจะตั้งค่าสีอัลฟ่าให้กับสี่เหลี่ยมผืนผ้าได้อย่างไร

 A: คุณสามารถระบุสีอัลฟ่าสำหรับรูปสี่เหลี่ยมผืนผ้าได้โดยใช้`FillColor` ทรัพย์สินของ`GraphInfo` วัตถุและ`Color.FromRgb` วิธีการที่มีค่า ARGB

#### ถาม: ฉันสามารถสร้างสี่เหลี่ยมผืนผ้าหลายรูปที่มีสีอัลฟ่าที่ต่างกันได้หรือไม่

A: ใช่ คุณสามารถสร้างสี่เหลี่ยมผืนผ้าหลายรูปด้วยสีอัลฟ่าที่ต่างกันได้โดยทำตามขั้นตอนที่คล้ายกันตามที่สาธิตในบทช่วยสอน

#### ถาม: ฉันจะบันทึกไฟล์ PDF ผลลัพธ์หลังจากสร้างสี่เหลี่ยมผืนผ้าที่มีสีอัลฟ่าได้อย่างไร

 A: หลังจากสร้างรูปสี่เหลี่ยมด้วยสีอัลฟ่าแล้ว คุณสามารถบันทึกไฟล์ PDF ที่ได้โดยใช้`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` บรรทัดในโค้ดต้นฉบับที่ให้ไว้