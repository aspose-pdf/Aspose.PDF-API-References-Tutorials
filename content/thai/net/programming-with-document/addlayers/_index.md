---
title: เพิ่มเลเยอร์ลงในไฟล์ PDF
linktitle: เพิ่มเลเยอร์ลงในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มเลเยอร์ให้กับไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมบทช่วยสอนโค้ดสำหรับการสร้างและบันทึก PDF แบบเลเยอร์
type: docs
weight: 20
url: /th/net/programming-with-document/addlayers/
---
ในการเพิ่มเลเยอร์ให้กับไฟล์ PDF เราจะใช้ Aspose.PDF สำหรับ .NET ไลบรารีนี้ช่วยให้เราทำงานกับไฟล์ PDF ในแอปพลิเคชัน .NET ได้อย่างมีประสิทธิภาพ ทำตามคำแนะนำทีละขั้นตอนด้านล่างเพื่อเพิ่มเลเยอร์โดยใช้ Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 1: สร้างเอกสาร PDF ใหม่

 เริ่มต้นด้วยการสร้างอินสแตนซ์ใหม่ของ`Document` คลาสที่จัดทำโดย Aspose.PDF สำหรับ .NET ซึ่งจะทำหน้าที่เป็นเอกสาร PDF ที่เราจะเพิ่มเลเยอร์

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## ขั้นตอนที่ 2: เพิ่มหน้าลงในเอกสาร

 จากนั้นเพิ่มหน้าลงในเอกสารโดยใช้`Add` วิธีการของ`Pages` คอลเลกชันใน`Document` ระดับ.

```csharp
Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 3: สร้างและเพิ่มเลเยอร์ให้กับเพจ

 สร้างอินสแตนซ์ของ`Layer` สำหรับแต่ละเลเยอร์ที่คุณต้องการเพิ่มลงในไฟล์ PDF ระบุตัวระบุที่ไม่ซ้ำกันและชื่อสำหรับแต่ละเลเยอร์

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

ในบทช่วยสอนนี้ เราได้เพิ่มสามเลเยอร์ด้วยสีและชื่อที่แตกต่างกันให้กับเพจ

## ขั้นตอนที่ 4: บันทึกไฟล์ PDF

 บันทึกไฟล์ PDF ที่แก้ไขโดยใช้นามสกุล`Save` วิธีการของ`Document` ระดับ.

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

รหัสนี้จะบันทึกไฟล์ PDF ที่แก้ไขไปยังไดเร็กทอรีที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับการเพิ่มเลเยอร์ลงในหน้า PDF โดยใช้ Aspose.PDF สำหรับ .NET

```csharp            
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## บทสรุป

ในบทความนี้ เราได้ให้คำแนะนำทีละขั้นตอนในการเพิ่มเลเยอร์ให้กับไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำและใช้บทช่วยสอนโค้ดที่ให้มา คุณสามารถรวมเลเยอร์เข้ากับเอกสาร PDF ของคุณได้อย่างง่ายดาย เลเยอร์ช่วยให้คุณสามารถจัดระเบียบและควบคุมการเปิดเผยเนื้อหา มอบประสบการณ์เชิงโต้ตอบและปรับแต่งได้มากขึ้นสำหรับผู้ใช้ของคุณ


### คำถามที่พบบ่อยสำหรับการเพิ่มเลเยอร์ลงในไฟล์ PDF

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ PDF ในแอปพลิเคชัน .NET ได้อย่างมีประสิทธิภาพ มันมีคุณสมบัติที่หลากหลายสำหรับการสร้าง การแก้ไข และการจัดการเอกสาร PDF

#### ถาม: เลเยอร์ PDF คืออะไร

ตอบ: เลเยอร์ PDF หรือที่เรียกว่ากลุ่มเนื้อหาเสริม (OCG) ช่วยให้คุณสามารถควบคุมการมองเห็นและลักษณะของเนื้อหาเฉพาะภายในไฟล์ PDF ได้ มีประโยชน์สำหรับการจัดระเบียบเนื้อหาและการสร้างเอกสารเชิงโต้ตอบ

#### ถาม: ฉันสามารถเพิ่มหลายเลเยอร์ลงในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มหลายเลเยอร์ลงในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET แต่ละเลเยอร์สามารถมีตัวระบุและชื่อเฉพาะของตัวเองได้ ดังที่แสดงในบทช่วยสอน

#### ถาม: ฉันจะปรับแต่งลักษณะที่ปรากฏของเลเยอร์ได้อย่างไร

ตอบ: คุณสามารถปรับแต่งลักษณะที่ปรากฏของเลเยอร์ได้โดยการระบุคุณสมบัติต่างๆ เช่น สี ความทึบ และการมองเห็น Aspose.PDF สำหรับ .NET มีตัวเลือกมากมายเพื่อให้บรรลุเป้าหมายนี้

#### ถาม: Aspose.PDF สำหรับ .NET เหมาะสำหรับโครงการระดับมืออาชีพหรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET เป็นไลบรารีที่เชื่อถือได้และใช้กันอย่างแพร่หลายสำหรับการจัดการ PDF ในโครงการระดับมืออาชีพ มีฟังก์ชันการทำงานที่หลากหลายและประสิทธิภาพที่ยอดเยี่ยมสำหรับการทำงานกับไฟล์ PDF ในแอปพลิเคชัน .NET