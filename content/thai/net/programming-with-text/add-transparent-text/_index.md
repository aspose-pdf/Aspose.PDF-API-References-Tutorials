---
title: เพิ่มข้อความโปร่งใสในไฟล์ PDF
linktitle: เพิ่มข้อความโปร่งใสในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มข้อความโปร่งใสในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 100
url: /th/net/programming-with-text/add-transparent-text/
---
บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการเพิ่มข้อความโปร่งใสลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ที่ติดตั้งบนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose หรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการเพิ่มข้อความโปร่งใส ให้เพิ่มคำสั่งต่อไปนี้โดยใช้คำสั่งที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเร็กทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่เก็บเอกสารของคุณ

## ขั้นตอนที่ 4: สร้างอินสแตนซ์เอกสารใหม่
 สร้างอินสแตนซ์ใหม่`Document` object โดยการเพิ่มบรรทัดโค้ดต่อไปนี้:

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 5: เพิ่มหน้าลงในเอกสาร
 เพิ่มหน้าใหม่ให้กับเอกสารโดยใช้`Add` วิธีการของ`Pages`ของสะสม. ในโค้ดที่ให้มา หน้าใหม่จะถูกกำหนดให้กับตัวแปร`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 6: สร้างวัตถุกราฟ
 สร้างใหม่`Graph` วัตถุที่มีความกว้างและความสูงเฉพาะ

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## ขั้นตอนที่ 7: สร้างสี่เหลี่ยมที่มีความโปร่งใส
 สร้างสี่เหลี่ยมที่มีขนาดเฉพาะและตั้งค่าสีเติมให้เป็นสีโปร่งใสโดยใช้`Color.FromRgb` วิธี.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## ขั้นตอนที่ 8: เพิ่มวัตถุกราฟลงในหน้า
 เพิ่ม`Graph` คัดค้านการรวบรวมย่อหน้าของเพจ

```csharp
page.Paragraphs.Add(canvas);
```

## ขั้นตอนที่ 9: กำหนดตำแหน่งสำหรับวัตถุกราฟ
 ตั้ง`IsChangePosition` ทรัพย์สินของ`Graph` วัตถุประสงค์`false` เพื่อป้องกันไม่ให้เปลี่ยนตำแหน่ง

```csharp
canvas. IsChangePosition = false;
```

## ขั้นตอนที่ 10: สร้าง TextFragment ด้วยความโปร่งใส
 สร้างก`TextFragment` วัตถุและตั้งค่าเนื้อหาเป็นข้อความที่ต้องการ ตั้ง`ForegroundColor` ทรัพย์สินของ`TextState` ให้เป็นสีที่มีความโปร่งใสโดยใช้`Color.FromArgb` วิธี.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## ขั้นตอนที่ 11: บันทึกเอกสาร PDF
 บันทึกเอกสาร PDF โดยใช้ไฟล์`Save` วิธีการของ`Document` วัตถุ.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับเพิ่มข้อความโปร่งใสโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างอินสแตนซ์เอกสาร
Document doc = new Document();
// สร้างคอลเลกชันหน้าต่อหน้าของไฟล์ PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// สร้างวัตถุกราฟ
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// สร้างอินสแตนซ์สี่เหลี่ยมผืนผ้าที่มีขนาดที่แน่นอน
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// สร้างวัตถุสีจากช่องสีอัลฟ่า
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// เพิ่มรูปสี่เหลี่ยมผืนผ้าให้กับคอลเลกชันรูปร่างของวัตถุกราฟ
canvas.Shapes.Add(rect);
//เพิ่มวัตถุกราฟลงในคอลเลกชันย่อหน้าของวัตถุหน้า
page.Paragraphs.Add(canvas);
// ตั้งค่าไม่ให้เปลี่ยนตำแหน่งของวัตถุกราฟ
canvas.IsChangePosition = false;
// สร้างอินสแตนซ์ TextFragment ด้วยค่าตัวอย่าง
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// สร้างวัตถุสีจากช่องอัลฟ่า
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
คุณได้เพิ่มข้อความโปร่งใสลงในเอกสาร PDF ของคุณสำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ขณะนี้ไฟล์ PDF ที่เป็นผลลัพธ์สามารถพบได้ที่เส้นทางไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: บทช่วยสอนนี้เน้นอะไร

ตอบ: บทช่วยสอนนี้เน้นที่การเพิ่มข้อความโปร่งใสลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับไลบรารี .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็นเพื่อให้บรรลุผลนี้

#### ถาม: เนมสเปซใดบ้างที่ต้องนำเข้าสำหรับบทช่วยสอนนี้

ตอบ: ในไฟล์โค้ดที่คุณต้องการเพิ่มข้อความโปร่งใส ให้นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร

 ตอบ: ในโค้ด ให้ค้นหาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างอินสแตนซ์เอกสารใหม่ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 4 คุณจะสร้างอินสแตนซ์ใหม่`Document` วัตถุโดยใช้รหัสที่ให้มา

#### ถาม: ฉันจะเพิ่มหน้าลงในเอกสารได้อย่างไร

 ตอบ: ในขั้นตอนที่ 5 คุณจะต้องเพิ่มหน้าใหม่ให้กับเอกสารโดยใช้`Add` วิธีการของ`Pages` ของสะสม.

#### ถาม: ฉันจะสร้างวัตถุกราฟได้อย่างไร

 ตอบ: ในขั้นตอนที่ 6 คุณจะสร้างใหม่`Graph` วัตถุที่มีความกว้างและความสูงเฉพาะ

#### ถาม: ฉันจะสร้างสี่เหลี่ยมที่มีความโปร่งใสได้อย่างไร

ตอบ: ในขั้นตอนที่ 7 คุณจะต้องสร้างสี่เหลี่ยมผืนผ้าที่มีขนาดเฉพาะและตั้งค่าสีเติมให้เป็นสีโปร่งใสโดยใช้`Color.FromRgb` วิธี.

#### ถาม: ฉันจะเพิ่มวัตถุ Graph ลงในเพจได้อย่างไร

 ตอบ: ในขั้นตอนที่ 8 คุณจะต้องเพิ่มไฟล์`Graph` คัดค้านการรวบรวมย่อหน้าของเพจ

#### ถาม: ฉันจะกำหนดตำแหน่งของวัตถุกราฟได้อย่างไร

 ตอบ: ในขั้นตอนที่ 9 คุณจะต้องตั้งค่า`IsChangePosition` ทรัพย์สินของ`Graph` วัตถุประสงค์`false` เพื่อป้องกันไม่ให้เปลี่ยนตำแหน่ง

#### ถาม: ฉันจะสร้าง TextFragment ที่มีความโปร่งใสได้อย่างไร

 ตอบ: ในขั้นตอนที่ 10 คุณจะสร้าง`TextFragment` วัตถุและตั้งค่าเนื้อหาและ`ForegroundColor` คุณสมบัติเพื่อให้ได้ข้อความที่โปร่งใส

#### ถาม: ฉันจะบันทึกเอกสาร PDF ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 11 คุณจะต้องบันทึกเอกสาร PDF โดยใช้นามสกุลไฟล์`Save` วิธีการของ`Document` วัตถุ.

#### ถาม: สิ่งสำคัญที่ได้รับจากบทช่วยสอนนี้คืออะไร

ตอบ: เมื่อทำตามบทช่วยสอนนี้ คุณได้เรียนรู้วิธีเพิ่มข้อความโปร่งใสลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET สิ่งนี้มีประโยชน์สำหรับการสร้างเอกสาร PDF ที่ดึงดูดสายตาและสร้างสรรค์