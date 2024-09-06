---
title: การจัดตำแหน่งข้อความสำหรับเนื้อหากล่องลอยในไฟล์ PDF
linktitle: การจัดตำแหน่งข้อความสำหรับเนื้อหากล่องลอยในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีจัดตำแหน่งข้อความภายในกล่องลอยในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 520
url: /th/net/programming-with-text/text-alignment-for-floating-box-contents/
---
บทช่วยสอนนี้จะอธิบายวิธีการจัดตำแหน่งข้อความภายในกล่องลอยในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนต่างๆ ทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะดำเนินการตามบทช่วยสอน โปรดแน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose หรือใช้ NuGet เพื่อติดตั้งในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

เริ่มต้นด้วยการสร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น

เพิ่มคำสั่ง using ต่อไปนี้ที่จุดเริ่มต้นของไฟล์ C# ของคุณเพื่อนำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าเส้นทางไปยังไดเรกทอรีเอกสาร

 ตั้งค่าเส้นทางไปยังไดเรกทอรีเอกสารของคุณโดยใช้`dataDir` ตัวแปร:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: สร้างเอกสารใหม่

 สร้างใหม่`Document` วัตถุ:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## ขั้นตอนที่ 5: สร้างกล่องลอยที่มีข้อความแยกส่วน

 สร้างหลาย ๆ`FloatingBox` วัตถุที่มีการวางแนวตั้งและแนวนอนต่างกัน:

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);

Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);

Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

 ปรับเปลี่ยนข้อความและรูปแบบของ`TextFragment` วัตถุตามที่ต้องการ

## ขั้นตอนที่ 6: บันทึกเอกสาร PDF

บันทึกเอกสาร PDF ที่แก้ไขแล้ว:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 อย่าลืมเปลี่ยน`"FloatingBox_alignment_review_out.pdf"` พร้อมชื่อไฟล์เอาท์พุตตามที่ต้องการ

### ตัวอย่างโค้ดต้นฉบับสำหรับการจัดตำแหน่งข้อความสำหรับเนื้อหากล่องลอยโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีการจัดตำแหน่งข้อความภายในกล่องลอยในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนตั้งแต่การตั้งค่าโครงการไปจนถึงการบันทึกเอกสารที่แก้ไขแล้ว ตอนนี้คุณสามารถนำโค้ดนี้ไปใช้กับโครงการ C# ของคุณเองเพื่อปรับแต่งการจัดตำแหน่งข้อความภายในกล่องลอยในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "การจัดตำแหน่งข้อความสำหรับเนื้อหากล่องลอยในไฟล์ PDF" คืออะไร

A: บทช่วยสอน "การจัดตำแหน่งข้อความสำหรับเนื้อหาในกล่องลอยในไฟล์ PDF" มีวัตถุประสงค์เพื่อแนะนำผู้ใช้เกี่ยวกับวิธีจัดตำแหน่งข้อความภายในกล่องลอยในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนและตัวอย่างโค้ด C# เพื่อสาธิตกระบวนการ

#### ถาม: บทช่วยสอนนี้ช่วยในการจัดตำแหน่งข้อความภายในกล่องลอยได้อย่างไร

A: บทช่วยสอนนี้จะช่วยให้ผู้ใช้เข้าใจถึงวิธีการใช้ Aspose.PDF สำหรับ .NET เพื่อจัดตำแหน่งข้อความภายในกล่องลอยในเอกสาร PDF โดยทำตามขั้นตอนและตัวอย่างโค้ดที่ให้มา ผู้ใช้สามารถปรับแต่งการจัดตำแหน่งข้อความในแนวตั้งและแนวนอนภายในกล่องลอยได้

#### ถาม: มีข้อกำหนดเบื้องต้นอะไรบ้างที่ต้องปฏิบัติตามบทช่วยสอนนี้?

A: ก่อนเริ่มบทช่วยสอน คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# นอกจากนี้ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET คุณสามารถรับได้จากเว็บไซต์ Aspose หรือติดตั้งในโปรเจ็กต์ของคุณโดยใช้ NuGet

#### ถาม: ฉันจะตั้งค่าโครงการเพื่อทำตามบทช่วยสอนนี้ได้อย่างไร

A: ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET วิธีนี้ช่วยให้คุณสามารถใช้ประโยชน์จากคุณลักษณะของไลบรารีสำหรับการทำงานกับเอกสาร PDF และจัดตำแหน่งข้อความภายในกล่องลอย

#### ถาม: ฉันสามารถใช้บทช่วยสอนนี้เพื่อจัดตำแหน่งข้อความภายในกล่องลอยทุกประเภทได้หรือไม่

A: ใช่ บทช่วยสอนนี้ให้คำแนะนำเกี่ยวกับวิธีการจัดตำแหน่งข้อความภายในกล่องลอยในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้ตัวอย่างโค้ดที่ให้มาเพื่อปรับแต่งการจัดตำแหน่งข้อความในแนวตั้งและแนวนอนภายในกล่องลอย

#### ถาม: ฉันจะระบุการจัดตำแหน่งของข้อความภายในกล่องลอยได้อย่างไร

 A: บทช่วยสอนนี้สาธิตวิธีการสร้าง`FloatingBox`วัตถุและตั้งค่าของพวกเขา`VerticalAlignment` และ`HorizontalAlignment` คุณสมบัติในการควบคุมการจัดตำแหน่งของข้อความที่บรรจุอยู่ คุณสามารถปรับคุณสมบัติเหล่านี้ได้ตามความต้องการของคุณ

#### ถาม: ฉันจะปรับแต่งรูปลักษณ์ของกล่องลอยได้อย่างไร

 A: คุณสามารถปรับแต่งลักษณะของกล่องลอยได้โดยการแก้ไขคุณสมบัติต่างๆ เช่น ขอบ ขนาด และเนื้อหาข้อความ บทช่วยสอนมีตัวอย่างโค้ดที่สาธิตวิธีการสร้างและกำหนดรูปแบบกล่องลอย`FloatingBox` วัตถุ

#### ถาม: ฉันสามารถเพิ่มกล่องลอยหลายกล่องที่มีการจัดตำแหน่งที่แตกต่างกันในเอกสาร PDF เดียวกันได้หรือไม่

 A: ใช่ บทช่วยสอนแสดงวิธีการสร้างหลายๆ`FloatingBox` วัตถุที่มีการจัดแนวแนวตั้งและแนวนอนต่างกันและเพิ่มวัตถุเหล่านั้นลงในเอกสาร PDF เดียวกัน วิธีนี้ช่วยให้คุณเห็นผลกระทบของการจัดแนวต่างๆ ภายในเอกสารเดียวกัน

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่แก้ไขแล้วได้อย่างไร

 A: หากต้องการบันทึกเอกสาร PDF ที่แก้ไขแล้ว คุณสามารถใช้`Save` วิธีการของ`Document` วัตถุ บทช่วยสอนมีตัวอย่างโค้ดที่สาธิตวิธีการบันทึกเอกสาร PDF ที่ได้