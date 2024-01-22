---
title: การจัดตำแหน่งข้อความสำหรับเนื้อหากล่องลอยในไฟล์ PDF
linktitle: การจัดตำแหน่งข้อความสำหรับเนื้อหากล่องลอยในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีจัดแนวข้อความภายในกล่องลอยในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 520
url: /th/net/programming-with-text/text-alignment-for-floating-box-contents/
---
บทช่วยสอนนี้จะอธิบายวิธีจัดแนวข้อความภายในกล่องลอยในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาสาธิตกระบวนการทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะดำเนินการบทแนะนำต่อ โปรดแน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Aspose.PDF สำหรับไลบรารี .NET แล้ว คุณสามารถรับได้จากเว็บไซต์ Aspose หรือใช้ NuGet เพื่อติดตั้งในโครงการของคุณ

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

เริ่มต้นด้วยการสร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบรวม (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น

เพิ่มคำสั่งต่อไปนี้ที่จุดเริ่มต้นของไฟล์ C# ของคุณเพื่อนำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 3: กำหนดเส้นทางไปยังไดเร็กทอรีเอกสาร

 กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณโดยใช้ไฟล์`dataDir` ตัวแปร:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: สร้างเอกสารใหม่

 สร้างใหม่`Document` วัตถุ:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## ขั้นตอนที่ 5: สร้างกล่องลอยพร้อมส่วนของข้อความ

 สร้างหลายรายการ`FloatingBox` วัตถุที่มีการจัดแนวแนวตั้งและแนวนอนต่างกัน:

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

 แก้ไขข้อความและสไตล์ของ`TextFragment` วัตถุได้ตามต้องการ

## ขั้นตอนที่ 6: บันทึกเอกสาร PDF

บันทึกเอกสาร PDF ที่แก้ไข:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"FloatingBox_alignment_review_out.pdf"` ด้วยชื่อไฟล์เอาต์พุตที่ต้องการ

### ตัวอย่างซอร์สโค้ดสำหรับการจัดตำแหน่งข้อความสำหรับเนื้อหากล่องลอยโดยใช้ Aspose.PDF สำหรับ .NET 
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

ยินดีด้วย! คุณได้เรียนรู้วิธีการจัดแนวข้อความภายในกล่องลอยในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอน ตั้งแต่การตั้งค่าโปรเจ็กต์ไปจนถึงการบันทึกเอกสารที่แก้ไข ตอนนี้คุณสามารถรวมโค้ดนี้เข้ากับโปรเจ็กต์ C# ของคุณเองเพื่อปรับแต่งการจัดแนวข้อความภายในกล่องลอยในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "การจัดตำแหน่งข้อความสำหรับเนื้อหากล่องแบบลอยในไฟล์ PDF" คืออะไร

ตอบ: บทช่วยสอน "การจัดตำแหน่งข้อความสำหรับเนื้อหากล่องลอยในไฟล์ PDF" มีวัตถุประสงค์เพื่อแนะนำผู้ใช้เกี่ยวกับวิธีจัดแนวข้อความภายในกล่องลอยในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET บทช่วยสอนให้คำแนะนำทีละขั้นตอนและตัวอย่างโค้ด C# เพื่อสาธิตกระบวนการ

#### ถาม: บทช่วยสอนนี้ช่วยในการจัดแนวข้อความภายในกล่องลอยได้อย่างไร

ตอบ: บทช่วยสอนนี้ช่วยให้ผู้ใช้เข้าใจวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อจัดแนวข้อความภายในกล่องลอยในเอกสาร PDF โดยการทำตามขั้นตอนและตัวอย่างโค้ดที่ให้มา ผู้ใช้สามารถปรับแต่งการจัดแนวข้อความในแนวตั้งและแนวนอนภายในกล่องลอยได้

#### ถาม: ข้อกำหนดเบื้องต้นใดบ้างที่จำเป็นในการปฏิบัติตามบทช่วยสอนนี้

ตอบ: ก่อนที่จะเริ่มบทช่วยสอน คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# นอกจากนี้ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET ด้วย คุณสามารถรับได้จากเว็บไซต์ Aspose หรือติดตั้งในโครงการของคุณโดยใช้ NuGet

#### ถาม: ฉันจะตั้งค่าโปรเจ็กต์ให้ปฏิบัติตามบทช่วยสอนนี้ได้อย่างไร

ตอบ: ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบรวม (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET สิ่งนี้ช่วยให้คุณสามารถใช้ประโยชน์จากคุณสมบัติของไลบรารีสำหรับการทำงานกับเอกสาร PDF และการจัดแนวข้อความภายในกล่องลอย

#### ถาม: ฉันสามารถใช้บทช่วยสอนนี้เพื่อจัดแนวข้อความภายในกล่องลอยประเภทใดก็ได้หรือไม่

ตอบ: ใช่ บทช่วยสอนนี้จะให้คำแนะนำเกี่ยวกับวิธีจัดแนวข้อความภายในกล่องลอยในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้ตัวอย่างโค้ดที่ให้มาเพื่อปรับแต่งการจัดแนวข้อความในแนวตั้งและแนวนอนภายในกล่องแบบลอยได้

#### ถาม: ฉันจะระบุการจัดแนวข้อความภายในกล่องแบบลอยได้อย่างไร

 ตอบ: บทช่วยสอนสาธิตวิธีการสร้าง`FloatingBox`วัตถุและตั้งค่า`VerticalAlignment` และ`HorizontalAlignment` คุณสมบัติในการควบคุมการจัดตำแหน่งของข้อความที่มีอยู่ คุณสามารถปรับคุณสมบัติเหล่านี้ได้ตามความต้องการของคุณ

#### ถาม: ฉันจะปรับแต่งรูปลักษณ์ของกล่องแบบลอยได้อย่างไร

 ตอบ: คุณสามารถปรับแต่งลักษณะที่ปรากฏของกล่องแบบลอยได้โดยการแก้ไขคุณสมบัติ เช่น เส้นขอบ ขนาด และเนื้อหาข้อความ บทช่วยสอนให้ตัวอย่างโค้ดที่สาธิตวิธีการสร้างและจัดรูปแบบ`FloatingBox` วัตถุ

#### ถาม: ฉันสามารถเพิ่มกล่องลอยหลายกล่องที่มีการจัดแนวต่างกันในเอกสาร PDF เดียวกันได้หรือไม่

 ตอบ: ใช่ บทช่วยสอนจะสาธิตวิธีสร้างหลายรายการ`FloatingBox` วัตถุที่มีการจัดแนวแนวตั้งและแนวนอนต่างกัน และเพิ่มลงในเอกสาร PDF เดียวกัน ซึ่งช่วยให้คุณเห็นผลกระทบของการจัดแนวต่างๆ ภายในเอกสารเดียวกัน

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่แก้ไขแล้วได้อย่างไร

 ตอบ: หากต้องการบันทึกเอกสาร PDF ที่แก้ไข คุณสามารถใช้ไฟล์`Save` วิธีการของ`Document` วัตถุ. บทช่วยสอนนี้ให้ตัวอย่างโค้ดที่สาธิตวิธีการบันทึกเอกสาร PDF ที่ได้