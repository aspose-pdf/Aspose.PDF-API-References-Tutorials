---
title: การวาดเส้น
linktitle: การวาดเส้น
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการวาดเส้นขวางหน้าโดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนในการสร้างเส้นที่กำหนดเอง
type: docs
weight: 80
url: /th/net/programming-with-graphs/drawing-line/
---
ในบทช่วยสอนนี้ เราจะพาคุณอ่านโค้ดต้นฉบับ C# ทีละขั้นตอนในการวาดเส้นโดยใช้ Aspose.PDF สำหรับ .NET

ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณก่อนเริ่มต้น นอกจากนี้ ควรมีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# ด้วย

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในซอร์สโค้ดที่ให้มา คุณต้องระบุไดเรกทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่ได้ เปลี่ยนตัวแปร "dataDir" เป็นไดเรกทอรีที่ต้องการ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างอินสแตนซ์เอกสารและเพิ่มหน้า

เราสร้างอินสแตนซ์ของคลาส Document และเพิ่มหน้าลงในเอกสารนี้

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## ขั้นตอนที่ 3: การตั้งค่าระยะขอบหน้า

เราตั้งค่าระยะขอบหน้าเป็น 0 ทุกด้าน

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## ขั้นตอนที่ 4: การสร้างวัตถุกราฟและบรรทัดแรก

เราสร้างวัตถุ Graph ที่มีมิติเท่ากับของเพจและวาดบรรทัดแรกจากมุมล่างซ้ายไปยังมุมขวาบนของเพจ

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## ขั้นตอนที่ 5: การวาดเส้นที่ 2

เราวาดเส้นที่ 2 จากมุมซ้ายบนไปยังมุมขวาล่างของหน้า

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## ขั้นตอนที่ 6: การเพิ่มวัตถุกราฟลงในหน้า

เราเพิ่มวัตถุ Graph ลงในคอลเล็กชั่นย่อหน้าของหน้า

```csharp
pg.Paragraphs.Add(graph);
```

## ขั้นตอนที่ 7: บันทึกไฟล์ PDF ที่ได้

ในที่สุด เราจะบันทึกไฟล์ PDF ผลลัพธ์ด้วยชื่อ "DrawingLine_out.pdf" ในไดเร็กทอรีที่ระบุ

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการวาดเส้นโดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างอินสแตนซ์เอกสาร
Document pDoc = new Document();
// เพิ่มหน้าเข้าในคอลเลคชันเอกสาร PDF
Page pg = pDoc.Pages.Add();
// ตั้งค่าระยะขอบหน้าทั้งสี่ด้านเป็น 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// สร้างวัตถุกราฟที่มีความกว้างและความสูงเท่ากับขนาดของหน้า
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// สร้างวัตถุบรรทัดแรกโดยเริ่มจากมุมล่างซ้ายไปจนถึงมุมบนขวาของหน้า
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// เพิ่มเส้นลงในคอลเล็กชั่นรูปร่างของวัตถุกราฟ
graph.Shapes.Add(line);
// วาดเส้นจากมุมซ้ายบนของหน้าไปยังมุมล่างขวาของหน้า
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// เพิ่มเส้นลงในคอลเล็กชั่นรูปร่างของวัตถุกราฟ
graph.Shapes.Add(line2);
// เพิ่มวัตถุกราฟลงในคอลเล็กชั่นย่อหน้าของหน้า
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// บันทึกไฟล์ PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายวิธีการวาดเส้นโดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้ความรู้เหล่านี้เพื่อสร้างรูปทรงเรขาคณิตด้วยเส้นแบบกำหนดเองในไฟล์ PDF ของคุณได้แล้ว

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้คืออะไร?

A: วัตถุประสงค์ของบทช่วยสอนนี้คือเพื่อแนะนำคุณเกี่ยวกับขั้นตอนการวาดเส้นโดยใช้ Aspose.PDF สำหรับ .NET คุณจะได้เรียนรู้วิธีสร้างเส้นบนหน้า PDF และปรับแต่งลักษณะที่ปรากฏของเส้นเหล่านั้น

#### ถาม: มีข้อกำหนดเบื้องต้นอะไรบ้างก่อนเริ่มต้น?

A: ก่อนเริ่มต้น ให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณแล้ว นอกจากนี้ ขอแนะนำให้มีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# ด้วย

#### ถาม: ฉันจะระบุไดเร็กทอรีสำหรับบันทึกไฟล์ PDF ได้อย่างไร

ก: แก้ไขตัวแปร "dataDir" ในโค้ดต้นฉบับที่ให้มาเพื่อระบุไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ผลลัพธ์

#### ถาม: ฉันจะสร้างบรรทัดบนหน้า PDF ได้อย่างไร

A: บทช่วยสอนนี้สาธิตการสร้างอ็อบเจ็กต์ Graph ที่มีขนาดของหน้า จากนั้นจึงเพิ่มอ็อบเจ็กต์ Line ลงไป แก้ไขพิกัดและคุณสมบัติของอ็อบเจ็กต์ Line เพื่อสร้างเส้นตามต้องการ

#### ถาม: ฉันสามารถปรับแต่งลักษณะของเส้นได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งลักษณะของเส้นได้โดยแก้ไขคุณสมบัติของวัตถุเส้น ซึ่งรวมถึงการเปลี่ยนพิกัด สี ความหนา และคุณลักษณะกราฟิกอื่นๆ

#### ถาม: ฉันจะบันทึกเอกสาร PDF หลังจากวาดเส้นแล้วได้อย่างไร

 A: หลังจากเพิ่มวัตถุ Graph พร้อมกับวัตถุ Line ลงในหน้าแล้ว คุณสามารถบันทึกเอกสาร PDF ที่ได้โดยใช้`pDoc.Save(dataDir + "DrawingLine_out.pdf");` บรรทัดในโค้ดต้นฉบับที่ให้ไว้

#### ถาม: ฉันสามารถวาดเส้นที่มีมุมและทิศทางที่แตกต่างกันได้หรือไม่

A: ใช่ คุณสามารถวาดเส้นที่มีมุมและทิศทางที่แตกต่างกันได้โดยการปรับพิกัดและคุณสมบัติของวัตถุเส้นภายในกราฟ