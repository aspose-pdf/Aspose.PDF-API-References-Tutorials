---
title: เพิ่มวัตถุบรรทัดในไฟล์ PDF
linktitle: เพิ่มวัตถุบรรทัดในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มออบเจ็กต์บรรทัดแบบกำหนดเองในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 30
url: /th/net/programming-with-graphs/add-line-object/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# ต่อไปนี้ทีละขั้นตอนเพื่อเพิ่มอ็อบเจ็กต์บรรทัดโดยใช้ Aspose.PDF สำหรับ .NET

ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณก่อนที่จะเริ่มต้น มีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# ด้วย

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในซอร์สโค้ดที่ให้มา คุณจะต้องระบุไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่เป็นผลลัพธ์ เปลี่ยนตัวแปร "dataDir" เป็นไดเร็กทอรีที่ต้องการ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างอินสแตนซ์เอกสารและการเพิ่มหน้า

เราสร้างอินสแตนซ์ของคลาสเอกสารและเพิ่มหน้าให้กับเอกสารนี้

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 3: การสร้างวัตถุกราฟและเพิ่มลงในหน้า

เราสร้างออบเจ็กต์กราฟที่มีขนาดที่ระบุ และเพิ่มลงในคอลเลกชันย่อหน้าของหน้า

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## ขั้นตอนที่ 4: สร้างวัตถุเส้นและเพิ่มลงในแผนภูมิ

เราสร้างวัตถุเส้นด้วยพิกัดที่ระบุและเพิ่มลงในคอลเลกชันรูปร่างของแผนภูมิ

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## ขั้นตอนที่ 5: การตั้งค่าบรรทัด

เราสามารถระบุคุณสมบัติของเส้นได้ เช่น ประเภทเส้นประ และระยะเส้นประ

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## ขั้นตอนที่ 6: บันทึกไฟล์ PDF

สุดท้าย เราจะบันทึกไฟล์ PDF ที่เป็นผลลัพธ์ด้วยชื่อ "AddLineObject_out.pdf" ในไดเร็กทอรีที่ระบุ

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับ Add Line Object โดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างอินสแตนซ์เอกสาร
Document doc = new Document();
// เพิ่มหน้าไปยังคอลเลกชันหน้าของไฟล์ PDF
Page page = doc.Pages.Add();
// สร้างอินสแตนซ์กราฟ
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// เพิ่มวัตถุกราฟลงในคอลเลกชันย่อหน้าของอินสแตนซ์หน้า
page.Paragraphs.Add(graph);
// สร้างอินสแตนซ์สี่เหลี่ยมผืนผ้า
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// ระบุสีเติมสำหรับวัตถุกราฟ
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// เพิ่มวัตถุรูปสี่เหลี่ยมผืนผ้าลงในคอลเลกชันรูปร่างของวัตถุกราฟ
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// บันทึกไฟล์ PDF
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายทีละขั้นตอนวิธีการเพิ่มวัตถุบรรทัดโดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อสร้างเอกสาร PDF ด้วยบรรทัดที่กำหนดเองในแอปพลิเคชันของคุณ

### คำถามที่พบบ่อยสำหรับการเพิ่มวัตถุบรรทัดในไฟล์ PDF

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้คืออะไร?

ตอบ: บทช่วยสอนนี้มีจุดมุ่งหมายเพื่อแนะนำคุณตลอดขั้นตอนการเพิ่มออบเจ็กต์บรรทัดโดยใช้ Aspose.PDF สำหรับ .NET เพื่อปรับปรุงเอกสาร PDF ของคุณ

#### ถาม: มีข้อกำหนดเบื้องต้นอะไรบ้างก่อนที่จะเริ่ม?

ตอบ: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ นอกจากนี้ แนะนำให้มีความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

#### ถาม: ฉันจะระบุไดเร็กทอรีสำหรับบันทึกไฟล์ PDF ได้อย่างไร

ตอบ: ในซอร์สโค้ดที่ให้มา คุณสามารถแก้ไขตัวแปร "dataDir" เพื่อระบุไดเรกทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่ได้

#### ถาม: วัตถุประสงค์ของวัตถุกราฟคืออะไร?

ตอบ: วัตถุ Graph ทำหน้าที่เป็นคอนเทนเนอร์สำหรับองค์ประกอบการวาด สร้างขึ้นด้วยมิติข้อมูลที่ระบุและเพิ่มลงในคอลเลกชันย่อหน้าของเพจ

#### ถาม: ฉันจะเพิ่มวัตถุบรรทัดลงในเอกสาร PDF ได้อย่างไร

ตอบ: หากต้องการเพิ่มวัตถุเส้น ให้สร้างอินสแตนซ์ของคลาส Line ด้วยพิกัดที่ระบุ และเพิ่มลงในคอลเลกชันรูปร่างของกราฟ

#### ถาม: ฉันสามารถปรับแต่งรูปลักษณ์ของเส้นได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของเส้นได้โดยการตั้งค่าคุณสมบัติ เช่น ประเภทเส้นประและเฟสของเส้นประ โดยใช้คุณสมบัติ GraphInfo ของออบเจ็กต์ Line

#### ถาม: การระบุ Dash Array และ Dash Phase มีจุดประสงค์อะไร

ตอบ: คุณสมบัติแดชอาเรย์และเฟสแดชช่วยให้คุณสร้างเส้นประหรือเส้นประที่มีรูปแบบเฉพาะได้

#### ถาม: ฉันจะบันทึกไฟล์ PDF หลังจากเพิ่มวัตถุบรรทัดได้อย่างไร

 ตอบ: หลังจากเพิ่มวัตถุเส้นแล้ว คุณสามารถบันทึกไฟล์ PDF ที่ได้โดยใช้นามสกุลไฟล์`doc.Save(dataDir + "AddLineObject_out.pdf");` บรรทัดในซอร์สโค้ดที่ให้ไว้

#### ถาม: มีซอร์สโค้ดตัวอย่างหรือไม่

ตอบ: ใช่ บทช่วยสอนประกอบด้วยซอร์สโค้ดตัวอย่างที่คุณสามารถอ้างอิงถึงเพื่อดำเนินการตามขั้นตอนที่อธิบายไว้