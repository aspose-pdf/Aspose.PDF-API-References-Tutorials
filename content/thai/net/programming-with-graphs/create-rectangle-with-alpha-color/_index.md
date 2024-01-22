---
title: สร้างสี่เหลี่ยมผืนผ้าด้วยสีอัลฟ่า
linktitle: สร้างสี่เหลี่ยมผืนผ้าด้วยสีอัลฟ่า
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีสร้างสี่เหลี่ยมที่มีสีโปร่งใสโดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนเพื่อปรับแต่งความโปร่งใส
type: docs
weight: 60
url: /th/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# ต่อไปนี้ทีละขั้นตอนเพื่อสร้างสี่เหลี่ยมที่มีสีอัลฟ่าโดยใช้ Aspose.PDF สำหรับ .NET

ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณก่อนที่จะเริ่มต้น มีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# ด้วย

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในซอร์สโค้ดที่ให้มา คุณจะต้องระบุไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่เป็นผลลัพธ์ เปลี่ยนตัวแปร "dataDir" เป็นไดเร็กทอรีที่ต้องการ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างอินสแตนซ์วัตถุเอกสารและการเพิ่มหน้า

เราสร้างอินสแตนซ์ของคลาสเอกสารและเพิ่มหน้าให้กับเอกสารนี้

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 3: การสร้างวัตถุกราฟและสี่เหลี่ยมผืนผ้า

เราสร้างวัตถุกราฟที่มีขนาดที่ระบุและสี่เหลี่ยมผืนผ้าที่มีขนาดเฉพาะ

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## ขั้นตอนที่ 4: การตั้งค่าสีอัลฟ่าสำหรับสี่เหลี่ยมผืนผ้า

เราสามารถระบุสีอัลฟ่าสำหรับสี่เหลี่ยมผืนผ้าโดยใช้วิธี FromArgb ของคลาส System. Drawing.Color

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## ขั้นตอนที่ 5: การเพิ่มสี่เหลี่ยมผืนผ้าให้กับวัตถุกราฟ

เราเพิ่มสี่เหลี่ยมให้กับคอลเลกชันรูปร่างของวัตถุกราฟ

```csharp
canvas.Shapes.Add(rect);
```

## ขั้นตอนที่ 6: การสร้างสี่เหลี่ยมที่สองด้วยสีอัลฟ่าที่แตกต่างกัน

เราสร้างสี่เหลี่ยมผืนผ้าที่สองโดยมีขนาดเฉพาะและสีอัลฟ่าอื่น

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## ขั้นตอนที่ 7: การเพิ่มวัตถุกราฟลงในเพจ

เราเพิ่มวัตถุกราฟไปยังคอลเลกชันย่อหน้าของวัตถุหน้า

```csharp
page.Paragraphs.Add(canvas);
```

## ขั้นตอนที่ 8: บันทึกไฟล์ PDF ที่ได้

สุดท้าย เราจะบันทึกไฟล์ PDF ที่เป็นผลลัพธ์โดยใช้ชื่อ "CreateRectangleWithAlphaColor_out.pdf" ในไดเร็กทอรีที่ระบุ

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับสร้างสี่เหลี่ยมผืนผ้าด้วยสีอัลฟ่าโดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างอินสแตนซ์เอกสาร
Document doc = new Document();
// เพิ่มหน้าไปยังคอลเลกชันหน้าของไฟล์ PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// สร้างอินสแตนซ์กราฟ
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// สร้างวัตถุสี่เหลี่ยมที่มีขนาดเฉพาะ
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//ตั้งค่าสีเติมกราฟจากโครงสร้าง System. Drawing.Color จากค่า ARGB 32 บิต
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// เพิ่มวัตถุรูปสี่เหลี่ยมผืนผ้าลงในคอลเลกชันรูปร่างของอินสแตนซ์กราฟ
canvas.Shapes.Add(rect);
// สร้างวัตถุสี่เหลี่ยมผืนผ้าที่สอง
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// เพิ่มอินสแตนซ์กราฟให้กับคอลเลกชันย่อหน้าของออบเจ็กต์หน้า
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// บันทึกไฟล์ PDF
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายวิธีสร้างสี่เหลี่ยมที่มีสีอัลฟ่าโดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อสร้างรูปทรงเรขาคณิตที่มีสีโปร่งใสในไฟล์ PDF ของคุณได้

## คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้คืออะไร?

ตอบ: บทช่วยสอนนี้มีจุดมุ่งหมายเพื่อแนะนำคุณตลอดกระบวนการสร้างสี่เหลี่ยมที่มีสีอัลฟ่าโดยใช้ Aspose.PDF สำหรับ .NET คุณจะได้เรียนรู้วิธีเพิ่มรูปทรงเรขาคณิตที่มีสีโปร่งใสให้กับไฟล์ PDF ของคุณ

#### ถาม: มีข้อกำหนดเบื้องต้นอะไรบ้างก่อนที่จะเริ่ม?

ตอบ: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ นอกจากนี้ แนะนำให้มีความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

#### ถาม: ฉันจะระบุไดเร็กทอรีสำหรับบันทึกไฟล์ PDF ได้อย่างไร

ตอบ: ในซอร์สโค้ดที่ให้มา คุณสามารถแก้ไขตัวแปร "dataDir" เพื่อระบุไดเรกทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่ได้

#### ถาม: วัตถุประสงค์ของวัตถุกราฟและสี่เหลี่ยมผืนผ้าคืออะไร?

ตอบ: วัตถุกราฟทำหน้าที่เป็นที่เก็บสำหรับองค์ประกอบการวาด ในขณะที่สี่เหลี่ยมผืนผ้าแสดงถึงรูปทรงเรขาคณิตที่คุณจะเพิ่มลงใน PDF

#### ถาม: ฉันจะตั้งค่าสีอัลฟ่าสำหรับสี่เหลี่ยมผืนผ้าได้อย่างไร

ตอบ: คุณสามารถระบุสีอัลฟ่าสำหรับสี่เหลี่ยมผืนผ้าได้โดยใช้`FillColor` ทรัพย์สินของ`GraphInfo` วัตถุและ`Color.FromRgb` วิธีการที่มีค่า ARGB

#### ถาม: ฉันสามารถสร้างสี่เหลี่ยมหลายอันที่มีสีอัลฟ่าต่างกันได้หรือไม่

ตอบ: ได้ คุณสามารถสร้างสี่เหลี่ยมหลายอันด้วยสีอัลฟ่าที่แตกต่างกันได้โดยทำตามขั้นตอนที่คล้ายกันดังที่แสดงในบทช่วยสอน

#### ถาม: ฉันจะบันทึกไฟล์ PDF ที่ได้หลังจากสร้างสี่เหลี่ยมที่มีสีอัลฟ่าได้อย่างไร

 ตอบ: หลังจากสร้างสี่เหลี่ยมด้วยสีอัลฟ่าแล้ว คุณสามารถบันทึกไฟล์ PDF ที่ได้โดยใช้นามสกุลไฟล์`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` บรรทัดในซอร์สโค้ดที่ให้ไว้