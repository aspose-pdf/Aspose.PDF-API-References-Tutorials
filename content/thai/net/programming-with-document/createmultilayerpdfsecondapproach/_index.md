---
title: สร้างไฟล์ PDF หลายชั้นแนวทางที่สอง
linktitle: สร้างไฟล์ PDF หลายชั้นแนวทางที่สอง
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีสร้างไฟล์ PDF แบบหลายเลเยอร์โดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดสำหรับการสร้าง PDF แบบไดนามิกพร้อมข้อความและรูปภาพ
type: docs
weight: 80
url: /th/net/programming-with-document/createmultilayerpdfsecondapproach/
---
ในบทช่วยสอนนี้ เราจะสำรวจวิธีสร้างไฟล์ PDF หลายชั้นโดยใช้แนวทางที่สองใน Aspose.PDF สำหรับ .NET เราจะให้คำแนะนำทีละขั้นตอนพร้อมคำอธิบายโดยละเอียดและรวมซอร์สโค้ดแบบเต็ม เมื่อทำตามบทช่วยสอนนี้ คุณจะสามารถสร้างเอกสาร PDF ที่มีหลายเลเยอร์ได้โดยใช้ไลบรารี Aspose.PDF ในแอปพลิเคชัน .NET ของคุณ

ตอนนี้ เรามาเริ่มด้วยคำแนะนำทีละขั้นตอนกันดีกว่า

## ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อม

ขั้นแรก ให้เปิด Visual Studio และสร้างโปรเจ็กต์ C# ใหม่ ตรวจสอบให้แน่ใจว่าคุณได้อ้างอิงไลบรารี Aspose.PDF ในโปรเจ็กต์ของคุณ เมื่อคุณตั้งค่าสภาพแวดล้อมแล้ว คุณก็พร้อมที่จะดำเนินการขั้นตอนต่อไป

## ขั้นตอนที่ 2: เริ่มต้นตัวแปร

ในขั้นตอนนี้ เราจะเริ่มต้นตัวแปรที่จำเป็น เราจำเป็นต้องกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารและกำหนดตัวแปรสีสำหรับเลเยอร์ PDF นี่คือข้อมูลโค้ด:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
```

## ขั้นตอนที่ 3: สร้างเอกสาร PDF

ต่อไป เราจะสร้างอินสแตนซ์ใหม่ของคลาส Aspose.Pdf.Document ซึ่งแสดงถึงเอกสาร PDF นี่คือข้อมูลโค้ด:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## ขั้นตอนที่ 4: เพิ่มหน้าลงในเอกสาร

ในขั้นตอนนี้ เราจะเพิ่มหน้าใหม่ให้กับเอกสาร PDF นี่คือข้อมูลโค้ด:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 5: เพิ่มข้อความลงในเพจ

ตอนนี้ เราจะเพิ่มส่วนของข้อความลงในหน้า ข้อความจะแสดงเป็นส่วนของย่อหน้าที่ 3 โดยมีสีแดง นี่คือข้อมูลโค้ด:

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;

Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
```

## ขั้นตอนที่ 6: เพิ่มรูปภาพลงในเพจ

ในขั้นตอนนี้ เราจะเพิ่มรูปภาพลงในเพจ รูปภาพจะถูกวางตำแหน่งเป็นกล่องลอยที่มีขนาดเฉพาะ นี่คือข้อมูลโค้ด:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);
ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);
```

## ขั้นตอนที่ 7: บันทึก PDF

ในขั้นตอนนี้ เราจะบันทึก PDF เป็นไฟล์

```
doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับการสร้างวิธีที่สองแบบหลายเลเยอร์ PDF โดยใช้ Aspose.PDF สำหรับ .NET

```csharp   
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

Aspose.Pdf.Page page = doc.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;
Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);

ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);

doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

## บทสรุป

ในบทความนี้ เราได้เรียนรู้วิธีสร้าง PDF หลายชั้นโดยใช้แนวทางที่สองของ Aspose.PDF สำหรับ .NET เราได้ให้คำแนะนำทีละขั้นตอนและซอร์สโค้ดแบบเต็มที่จำเป็นสำหรับการสร้าง PDF แบบหลายเลเยอร์

### คำถามที่พบบ่อย

#### ถาม: วิธีที่สองในการสร้าง PDF หลายชั้นโดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: แนวทางที่สองสำหรับการสร้าง PDF หลายเลเยอร์โดยใช้ Aspose.PDF สำหรับ .NET เกี่ยวข้องกับการใช้กล่องลอยเพื่อวางตำแหน่งและเพิ่มองค์ประกอบเนื้อหา เช่น ข้อความและรูปภาพ ลงในเลเยอร์ต่างๆ ภายในเอกสาร PDF

#### ถาม: ฉันสามารถเพิ่มมากกว่าสองชั้นลงในเอกสาร PDF โดยใช้แนวทางที่สองได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มหลายเลเยอร์ลงในเอกสาร PDF ได้โดยใช้แนวทางที่สองโดยเพิ่มกล่องแบบลอยตัวและจัดตำแหน่งตามนั้น กล่องลอยแต่ละกล่องแสดงถึงเลเยอร์ที่แยกจากกัน และคุณสามารถเพิ่มองค์ประกอบเนื้อหาลงในแต่ละกล่องเพื่อสร้างหลายเลเยอร์ได้

#### ถาม: การใช้แนวทางที่สองในการสร้าง PDF แบบหลายชั้นมีประโยชน์อย่างไร

ตอบ: แนวทางที่สองช่วยให้สามารถควบคุมตำแหน่งและการมองเห็นองค์ประกอบเนื้อหาในเอกสาร PDF ได้อย่างแม่นยำ โดยให้ความยืดหยุ่นมากขึ้นในการจัดการเลเยอร์และการจัดเรียงเนื้อหา ทำให้ง่ายต่อการสร้างเอกสารที่ซับซ้อนและโต้ตอบได้

#### ถาม: Aspose.PDF สำหรับ .NET เหมาะสำหรับการสร้างเอกสาร PDF แบบโต้ตอบและซับซ้อนหรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งมีคุณสมบัติมากมายสำหรับการสร้างเอกสาร PDF ที่ซับซ้อนและโต้ตอบได้ มีฟังก์ชันการทำงานที่หลากหลาย เช่น การเพิ่มข้อความ รูปภาพ ตาราง ไฮเปอร์ลิงก์ และฟิลด์แบบฟอร์ม ตลอดจนรองรับการดำเนินการ PDF ขั้นสูง

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏและคุณสมบัติของกล่องลอยในแนวทางที่สองได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะและคุณสมบัติของกล่องแบบลอยได้ เช่น ขนาด ตำแหน่ง สีพื้นหลัง และความทึบ Aspose.PDF สำหรับ .NET มีตัวเลือกต่างๆ สำหรับการจัดรูปแบบและการวางตำแหน่งกล่องลอย