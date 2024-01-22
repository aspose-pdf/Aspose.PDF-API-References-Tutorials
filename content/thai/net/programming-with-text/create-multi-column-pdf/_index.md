---
title: สร้าง PDF แบบหลายคอลัมน์
linktitle: สร้าง PDF แบบหลายคอลัมน์
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีสร้าง PDF แบบหลายคอลัมน์โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 110
url: /th/net/programming-with-text/create-multi-column-pdf/
---
บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการสร้าง PDF แบบหลายคอลัมน์โดยใช้ Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ที่ติดตั้งบนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose หรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการสร้าง PDF แบบหลายคอลัมน์ ให้เพิ่มคำสั่งต่อไปนี้โดยใช้คำสั่งที่ด้านบนของไฟล์:

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

## ขั้นตอนที่ 5: ตั้งค่าระยะขอบของหน้า
 ระบุข้อมูลระยะขอบซ้ายและขวาสำหรับไฟล์ PDF โดยใช้`PageInfo.Margin` ทรัพย์สินของ`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## ขั้นตอนที่ 6: เพิ่มหน้าลงในเอกสาร
 เพิ่มหน้าใหม่ให้กับเอกสารโดยใช้`Add` วิธีการของ`Pages`ของสะสม. ในโค้ดที่ให้มา หน้าใหม่จะถูกกำหนดให้กับตัวแปร`page`.

```csharp
Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 7: สร้างวัตถุกราฟและเพิ่มเส้น
 สร้างใหม่`Graph` วัตถุที่มีมิติเฉพาะและเพิ่มเส้นลงไป จากนั้นจึงเพิ่ม`Graph` คัดค้านการ`Paragraphs` คอลเลกชันของหน้า

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## ขั้นตอนที่ 8: เพิ่มข้อความส่วนหัวด้วยการจัดรูปแบบ HTML
 สร้าง`HtmlFragment` object และตั้งค่าเนื้อหาเป็นข้อความ HTML ที่ต้องการ จากนั้นจึงเพิ่มส่วนย่อยลงใน`Paragraphs` คอลเลกชันของหน้า

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## ขั้นตอนที่ 9: สร้าง FloatingBox ที่มีหลายคอลัมน์
 สร้างก`FloatingBox` object และกำหนดจำนวนคอลัมน์และระยะห่างระหว่างคอลัมน์ จากนั้นเพิ่มส่วนของข้อความและบรรทัดลงใน`Paragraphs` คอลเลกชันของ`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## ขั้นตอนที่ 10: บันทึกเอกสาร PDF
 บันทึกเอกสาร PDF โดยใช้ไฟล์`Save` วิธีการของ`Document` วัตถุ.

```csharp
doc.Save(dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับสร้าง Pdf หลายคอลัมน์โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// ระบุข้อมูลระยะขอบด้านซ้ายสำหรับไฟล์ PDF
doc.PageInfo.Margin.Left = 40;
//ระบุข้อมูลระยะขอบขวาสำหรับไฟล์ PDF
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// เพิ่มบรรทัดลงในคอลเลกชันถอดความของวัตถุส่วน
page.Paragraphs.Add(graph1);
// ระบุพิกัดของเส้น
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// สร้างตัวแปรสตริงด้วยข้อความที่มีแท็ก html
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// สร้างย่อหน้าข้อความที่มีข้อความ HTML
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// เพิ่มสี่คอลัมน์ในส่วนนี้
box.ColumnInfo.ColumnCount = 2;
// กำหนดระยะห่างระหว่างคอลัมน์
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// สร้างวัตถุกราฟเพื่อวาดเส้น
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// ระบุพิกัดของเส้น
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// เพิ่มบรรทัดลงในคอลเลกชันย่อหน้าของวัตถุส่วน
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// บันทึกไฟล์ PDF
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## บทสรุป
คุณสร้าง PDF แบบหลายคอลัมน์สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ขณะนี้ไฟล์ PDF ที่เป็นผลลัพธ์สามารถพบได้ที่เส้นทางไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: บทช่วยสอนนี้เน้นอะไร

บทช่วยสอนนี้เน้นที่การแนะนำคุณตลอดกระบวนการสร้าง PDF แบบหลายคอลัมน์โดยใช้ Aspose.PDF สำหรับไลบรารี .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็นเพื่อให้บรรลุเป้าหมายนี้

#### ถาม: ฉันควรนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

ตอบ: ในไฟล์โค้ดที่คุณต้องการสร้าง PDF แบบหลายคอลัมน์ ให้นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร

 ตอบ: ในโค้ด ให้ค้นหาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างอินสแตนซ์เอกสารใหม่ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 4 คุณจะสร้างอินสแตนซ์ใหม่`Document` วัตถุโดยใช้รหัสที่ให้มา

#### ถาม: ฉันจะตั้งค่าระยะขอบของหน้าได้อย่างไร

 ตอบ: ในขั้นตอนที่ 5 คุณจะใช้`PageInfo.Margin` ทรัพย์สินของ`Document` เพื่อระบุข้อมูลระยะขอบซ้ายและขวาสำหรับไฟล์ PDF

#### ถาม: ฉันจะเพิ่มหน้าลงในเอกสารได้อย่างไร

 ตอบ: ในขั้นตอนที่ 6 คุณจะต้องเพิ่มหน้าใหม่ให้กับเอกสารโดยใช้`Add` วิธีการของ`Pages` ของสะสม.

#### ถาม: ฉันจะสร้างวัตถุกราฟและเพิ่มเส้นได้อย่างไร

 ตอบ: ในขั้นตอนที่ 7 คุณจะสร้างใหม่`Graph` วัตถุ เพิ่มบรรทัดเข้าไป แล้วเพิ่ม`Graph` คัดค้านการ`Paragraphs` คอลเลกชันของหน้า

#### ถาม: ฉันจะเพิ่มข้อความส่วนหัวด้วยการจัดรูปแบบ HTML ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 8 คุณจะสร้างไฟล์`HtmlFragment` object และตั้งค่าเนื้อหาเป็นข้อความ HTML ที่ต้องการ จากนั้นเพิ่มส่วนย่อยลงใน`Paragraphs` คอลเลกชันของหน้า

#### ถาม: ฉันจะสร้าง FloatingBox ที่มีหลายคอลัมน์ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 9 คุณจะสร้างไฟล์`FloatingBox` วัตถุที่มีหลายคอลัมน์และระยะห่างคอลัมน์ จากนั้นเพิ่มส่วนของข้อความและบรรทัดลงใน`Paragraphs` คอลเลกชันของ`FloatingBox`.

#### ถาม: ฉันจะบันทึกเอกสาร PDF ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 10 คุณจะต้องบันทึกเอกสาร PDF โดยใช้นามสกุลไฟล์`Save` วิธีการของ`Document` วัตถุ.

#### ถาม: สิ่งสำคัญที่ได้รับจากบทช่วยสอนนี้คืออะไร

ตอบ: เมื่อทำตามบทช่วยสอนนี้ คุณได้เรียนรู้วิธีสร้างเอกสาร PDF แบบหลายคอลัมน์โดยใช้ Aspose.PDF สำหรับ .NET สิ่งนี้มีประโยชน์สำหรับการแสดงเนื้อหาในรูปแบบที่มีโครงสร้างและเป็นระเบียบ