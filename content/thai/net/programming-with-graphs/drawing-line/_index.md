---
title: การวาดเส้น
linktitle: การวาดเส้น
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีวาดเส้นข้ามหน้าโดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนในการสร้างเส้นที่กำหนดเอง
type: docs
weight: 80
url: /th/net/programming-with-graphs/drawing-line/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# ต่อไปนี้ทีละขั้นตอนเพื่อวาดเส้นโดยใช้ Aspose.PDF สำหรับ .NET

ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณก่อนที่จะเริ่มต้น มีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# ด้วย

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในซอร์สโค้ดที่ให้มา คุณจะต้องระบุไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่เป็นผลลัพธ์ เปลี่ยนตัวแปร "dataDir" เป็นไดเร็กทอรีที่ต้องการ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างอินสแตนซ์เอกสารและการเพิ่มหน้า

เราสร้างอินสแตนซ์ของคลาสเอกสารและเพิ่มหน้าให้กับเอกสารนี้

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## ขั้นตอนที่ 3: การตั้งค่าระยะขอบของหน้า

เราตั้งค่าระยะขอบหน้าเป็น 0 ในทุกด้าน

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## ขั้นตอนที่ 4: การสร้างวัตถุกราฟและบรรทัดแรก

เราสร้างวัตถุกราฟที่มีขนาดเท่ากับขนาดของหน้า และวาดบรรทัดแรกจากมุมซ้ายล่างไปยังมุมขวาบนของหน้า

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## ขั้นตอนที่ 5: วาดเส้นที่สอง

เราวาดบรรทัดที่สองจากมุมซ้ายบนไปยังมุมขวาล่างของหน้า

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## ขั้นตอนที่ 6: การเพิ่มวัตถุกราฟลงในเพจ

เราเพิ่มวัตถุกราฟไปยังคอลเลกชันย่อหน้าของหน้า

```csharp
pg.Paragraphs.Add(graph);
```

## ขั้นตอนที่ 7: บันทึกไฟล์ PDF ที่ได้

สุดท้าย เราจะบันทึกไฟล์ PDF ที่ได้ซึ่งมีชื่อ " DrawingLine_out.pdf " ลงในไดเร็กทอรีที่ระบุ

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับการวาดเส้นโดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างอินสแตนซ์เอกสาร
Document pDoc = new Document();
// เพิ่มหน้าไปยังคอลเลกชันหน้าของเอกสาร PDF
Page pg = pDoc.Pages.Add();
// ตั้งค่าระยะขอบของหน้าทุกด้านเป็น 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// สร้างวัตถุกราฟที่มีความกว้างและความสูงเท่ากับขนาดหน้า
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// สร้างออบเจ็กต์บรรทัดแรกโดยเริ่มจากมุมล่างซ้ายไปจนถึงมุมบนขวาของหน้า
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// เพิ่มเส้นลงในคอลเลกชันรูปร่างของวัตถุกราฟ
graph.Shapes.Add(line);
// ลากเส้นจากมุมซ้ายบนของหน้าไปยังมุมล่างขวาของหน้า
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// เพิ่มเส้นลงในคอลเลกชันรูปร่างของวัตถุกราฟ
graph.Shapes.Add(line2);
// เพิ่มวัตถุกราฟไปยังคอลเลกชันย่อหน้าของหน้า
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// บันทึกไฟล์ PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายวิธีการวาดเส้นโดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อสร้างรูปทรงเรขาคณิตด้วยเส้นที่กำหนดเองในไฟล์ PDF ของคุณ

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้คืออะไร?

ตอบ: จุดประสงค์ของบทช่วยสอนนี้คือเพื่อแนะนำคุณตลอดกระบวนการวาดเส้นโดยใช้ Aspose.PDF สำหรับ .NET คุณจะได้เรียนรู้วิธีสร้างเส้นบนหน้า PDF และปรับแต่งลักษณะที่ปรากฏ

#### ถาม: มีข้อกำหนดเบื้องต้นอะไรบ้างก่อนที่จะเริ่ม?

ตอบ: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ แนะนำให้มีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# ด้วย

#### ถาม: ฉันจะระบุไดเร็กทอรีสำหรับบันทึกไฟล์ PDF ได้อย่างไร

ตอบ: แก้ไขตัวแปร "dataDir" ในซอร์สโค้ดที่ให้มาเพื่อระบุไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่เป็นผลลัพธ์

#### ถาม: ฉันจะสร้างบรรทัดบนหน้า PDF ได้อย่างไร

ตอบ: บทช่วยสอนสาธิตการสร้างออบเจ็กต์กราฟที่มีขนาดของหน้า จากนั้นจึงเพิ่มออบเจ็กต์เส้นเข้าไป แก้ไขพิกัดและคุณสมบัติของออบเจ็กต์ Line เพื่อสร้างเส้นที่ต้องการ

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของเส้นได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของเส้นได้โดยการปรับเปลี่ยนคุณสมบัติของออบเจ็กต์ Line ซึ่งรวมถึงการเปลี่ยนพิกัด สี ความหนา และคุณลักษณะกราฟิกอื่นๆ

#### ถาม: ฉันจะบันทึกเอกสาร PDF หลังจากวาดเส้นได้อย่างไร

ตอบ: หลังจากเพิ่มวัตถุ Graph ที่มีวัตถุ Line ลงในเพจแล้ว คุณสามารถบันทึกเอกสาร PDF ที่เป็นผลลัพธ์ได้โดยใช้`pDoc.Save(dataDir + "DrawingLine_out.pdf");` บรรทัดในซอร์สโค้ดที่ให้ไว้

#### ถาม: ฉันสามารถวาดเส้นด้วยมุมและทิศทางที่ต่างกันได้หรือไม่

ตอบ: ได้ คุณสามารถวาดเส้นด้วยมุมและทิศทางที่แตกต่างกันได้โดยการปรับพิกัดและคุณสมบัติของวัตถุเส้นภายในกราฟ