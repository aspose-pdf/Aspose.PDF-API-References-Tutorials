---
title: เพิ่มข้อความโปร่งใสในไฟล์ PDF
linktitle: เพิ่มข้อความโปร่งใสในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการเพิ่มข้อความโปร่งใสในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 100
url: /th/net/programming-with-text/add-transparent-text/
---
บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับกระบวนการเพิ่มข้อความโปร่งใสลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ติดตั้งอยู่บนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose อย่างเป็นทางการหรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการเพิ่มข้อความโปร่งใส ให้เพิ่มคำสั่ง using ต่อไปนี้ที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเรกทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณเก็บเอกสารไว้

## ขั้นตอนที่ 4: สร้างอินสแตนซ์เอกสารใหม่
 สร้างอินสแตนซ์ใหม่`Document` วัตถุโดยการเพิ่มบรรทัดโค้ดดังต่อไปนี้:

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 5: เพิ่มหน้าลงในเอกสาร
 เพิ่มหน้าใหม่ลงในเอกสารโดยใช้`Add` วิธีการของ`Pages`คอลเลกชัน ในโค้ดที่ให้มา หน้าใหม่จะถูกกำหนดให้กับตัวแปร`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 6: สร้างวัตถุกราฟ
 สร้างใหม่`Graph` วัตถุที่มีความกว้างและความสูงที่กำหนด

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## ขั้นตอนที่ 7: สร้างสี่เหลี่ยมผืนผ้าที่มีความโปร่งใส
 สร้างสี่เหลี่ยมผืนผ้าที่มีขนาดเฉพาะและตั้งค่าสีเติมให้เป็นสีโปร่งใสโดยใช้`Color.FromRgb` วิธี.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## ขั้นตอนที่ 8: เพิ่มวัตถุกราฟลงในหน้า
 เพิ่ม`Graph` คัดค้านการรวบรวมย่อหน้าของหน้า

```csharp
page.Paragraphs.Add(canvas);
```

## ขั้นตอนที่ 9: กำหนดตำแหน่งสำหรับวัตถุ Graph
 ตั้งค่า`IsChangePosition` ทรัพย์สินของ`Graph` คัดค้าน`false` เพื่อป้องกันไม่ให้เปลี่ยนตำแหน่ง

```csharp
canvas. IsChangePosition = false;
```

## ขั้นตอนที่ 10: สร้าง TextFragment ด้วยความโปร่งใส
 สร้าง`TextFragment` วัตถุและกำหนดเนื้อหาให้เป็นข้อความที่ต้องการ ตั้งค่า`ForegroundColor` ทรัพย์สินของ`TextState` ให้เป็นสีที่มีความโปร่งใสโดยใช้`Color.FromArgb` วิธี.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## ขั้นตอนที่ 11: บันทึกเอกสาร PDF
 บันทึกเอกสาร PDF โดยใช้`Save` วิธีการของ`Document` วัตถุ.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการเพิ่มข้อความโปร่งใสโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างอินสแตนซ์เอกสาร
Document doc = new Document();
// สร้างคอลเลกชันหน้าต่อหน้าของไฟล์ PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// สร้างวัตถุกราฟ
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// สร้างอินสแตนซ์รูปสี่เหลี่ยมผืนผ้าที่มีขนาดที่กำหนด
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// สร้างวัตถุสีจากช่องสีอัลฟ่า
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// เพิ่มรูปสี่เหลี่ยมผืนผ้าลงในคอลเล็กชันรูปร่างของวัตถุ Graph
canvas.Shapes.Add(rect);
//เพิ่มวัตถุกราฟลงในคอลเล็กชั่นย่อหน้าของวัตถุหน้า
page.Paragraphs.Add(canvas);
// ตั้งค่าไม่ให้เปลี่ยนตำแหน่งสำหรับวัตถุกราฟ
canvas.IsChangePosition = false;
// สร้างอินสแตนซ์ TextFragment ด้วยค่าตัวอย่าง
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// สร้างวัตถุสีจากช่องอัลฟา
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// ตั้งค่าข้อมูลสีสำหรับอินสแตนซ์ข้อความ
text.TextState.ForegroundColor = color;
// เพิ่มข้อความลงในคอลเลกชันย่อหน้าของอินสแตนซ์หน้า
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## บทสรุป
คุณได้เพิ่มข้อความโปร่งใสลงในเอกสาร PDF สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้สามารถค้นหาไฟล์ PDF ที่ได้ในเส้นทางไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: บทช่วยสอนนี้เน้นอะไร?

A: บทช่วยสอนนี้เน้นที่การเพิ่มข้อความโปร่งใสลงในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็นในการบรรลุผลดังกล่าว

#### ถาม: จำเป็นต้องนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

ก: ในไฟล์โค้ดที่คุณต้องการเพิ่มข้อความโปร่งใส นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร?

 ก: ในโค้ด ให้หาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างอินสแตนซ์เอกสารใหม่ได้อย่างไร

 ก: ในขั้นตอนที่ 4 คุณจะสร้างอินสแตนซ์ใหม่`Document` วัตถุโดยใช้โค้ดที่ให้มา

#### ถาม: ฉันจะเพิ่มหน้าลงในเอกสารได้อย่างไร

 ก: ในขั้นตอนที่ 5 คุณจะเพิ่มหน้าใหม่ลงในเอกสารโดยใช้`Add` วิธีการของ`Pages` ของสะสม.

#### ถาม: ฉันจะสร้างวัตถุ Graph ได้อย่างไร

 A: ในขั้นตอนที่ 6 คุณจะสร้างใหม่`Graph` วัตถุที่มีความกว้างและความสูงที่กำหนด

#### ถาม: ฉันจะสร้างสี่เหลี่ยมผืนผ้าที่มีความโปร่งใสได้อย่างไร

ก: ในขั้นตอนที่ 7 คุณจะสร้างสี่เหลี่ยมผืนผ้าที่มีขนาดเฉพาะ และตั้งค่าสีเติมให้เป็นสีโปร่งใสโดยใช้`Color.FromRgb` วิธี.

#### ถาม: ฉันจะเพิ่มวัตถุ Graph ลงในหน้าได้อย่างไร

 A: ในขั้นตอนที่ 8 คุณจะเพิ่ม`Graph` คัดค้านการรวบรวมย่อหน้าของหน้า

#### ถาม: ฉันจะตั้งค่าตำแหน่งสำหรับวัตถุ Graph ได้อย่างไร

 A: ในขั้นตอนที่ 9 คุณจะตั้งค่า`IsChangePosition` ทรัพย์สินของ`Graph` คัดค้าน`false` เพื่อป้องกันไม่ให้เปลี่ยนตำแหน่ง

#### ถาม: ฉันจะสร้าง TextFragment ที่มีความโปร่งใสได้อย่างไร

 A: ในขั้นตอนที่ 10 คุณจะสร้าง`TextFragment` วัตถุและกำหนดเนื้อหาและ`ForegroundColor` คุณสมบัติในการบรรลุข้อความโปร่งใส

#### ถาม: ฉันจะบันทึกเอกสาร PDF ได้อย่างไร

 ก: ในขั้นตอนที่ 11 คุณจะบันทึกเอกสาร PDF โดยใช้`Save` วิธีการของ`Document` วัตถุ.

#### ถาม: สิ่งสำคัญที่สุดที่ได้จากบทช่วยสอนนี้คืออะไร?

A: เมื่อทำตามบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการเพิ่มข้อความโปร่งใสลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ซึ่งสามารถเป็นประโยชน์ในการสร้างเอกสาร PDF ที่น่าสนใจและสร้างสรรค์