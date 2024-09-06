---
title: หมุนข้อความโดยใช้ส่วนข้อความและย่อหน้า
linktitle: หมุนข้อความโดยใช้ส่วนข้อความและย่อหน้า
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีหมุนข้อความโดยใช้ส่วนข้อความและย่อหน้าในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 400
url: /th/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อหมุนข้อความโดยใช้ส่วนข้อความและย่อหน้า โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนต่างๆ ทีละขั้นตอน

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

## ขั้นตอนที่ 3: สร้างเอกสาร PDF

 เริ่มต้นการใช้งาน`Document` วัตถุที่จะสร้างเอกสาร PDF ใหม่:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: เพิ่มหน้า

 รับหน้าเฉพาะจากเอกสารโดยใช้`Pages.Add()` วิธี:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## ขั้นตอนที่ 5: สร้างชิ้นส่วนข้อความ

 สร้างหลาย ๆ`TextFragment` วัตถุ ตั้งค่าข้อความและคุณสมบัติ และระบุมุมการหมุน:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

ปรับแต่งข้อความ มุมการหมุน และคุณสมบัติอื่นตามต้องการ

## ขั้นตอนที่ 6: เพิ่มข้อความบางส่วนลงในหน้า

 เพิ่มชิ้นส่วนข้อความที่สร้างขึ้นลงในหน้าโดยการผนวกเข้าใน`Paragraphs` ของสะสม:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## ขั้นตอนที่ 7: บันทึกเอกสาร PDF

 บันทึกเอกสาร PDF ที่แก้ไขแล้วไปยังไฟล์โดยใช้`Save` วิธี:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 อย่าลืมเปลี่ยน`"TextFragmentTests_Rotated3_out.pdf"` พร้อมชื่อไฟล์เอาท์พุตตามที่ต้องการ

### ตัวอย่างโค้ดต้นฉบับสำหรับการหมุนข้อความโดยใช้ Text Fragment และ Paragraph โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// การเริ่มต้นวัตถุเอกสาร
Document pdfDocument = new Document();
// รับหน้าเฉพาะ
Page pdfPage = (Page)pdfDocument.Pages.Add();
// สร้างข้อความส่วนย่อย
TextFragment textFragment1 = new TextFragment("main text");
// ตั้งค่าคุณสมบัติข้อความ
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// สร้างข้อความส่วนย่อย
TextFragment textFragment2 = new TextFragment("rotated text");
// ตั้งค่าคุณสมบัติข้อความ
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// ตั้งค่าการหมุน
textFragment2.TextState.Rotation = 315;
// สร้างข้อความส่วนย่อย
TextFragment textFragment3 = new TextFragment("rotated text");
// ตั้งค่าคุณสมบัติข้อความ
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// ตั้งค่าการหมุน
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// บันทึกเอกสาร
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีหมุนข้อความโดยใช้ส่วนข้อความและย่อหน้าในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนตั้งแต่การสร้างเอกสารจนถึงการบันทึกเวอร์ชันที่แก้ไข ตอนนี้คุณสามารถนำโค้ดนี้ไปใช้กับโปรเจ็กต์ C# ของคุณเองเพื่อควบคุมการหมุนข้อความในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "หมุนข้อความโดยใช้ส่วนข้อความและย่อหน้า" คืออะไร

A: บทช่วยสอน "หมุนข้อความโดยใช้ส่วนข้อความและย่อหน้า" มีวัตถุประสงค์เพื่อแนะนำคุณตลอดกระบวนการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อหมุนข้อความโดยใช้ทั้งส่วนข้อความและย่อหน้าภายในเอกสาร PDF บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนและโค้ดตัวอย่างเพื่อให้บรรลุฟังก์ชันการทำงานนี้

#### ถาม: บทช่วยสอนนี้แตกต่างจากบทช่วยสอนการหมุนข้อความก่อนหน้านี้อย่างไร

A: บทช่วยสอนนี้ผสมผสานการใช้ข้อความและย่อหน้าเพื่อให้เกิดการหมุนข้อความในเอกสาร PDF โดยจะสาธิตวิธีหมุนข้อความทีละส่วนแล้วเพิ่มลงในหน้า`Paragraphs` การรวบรวมเพื่อให้ได้เอฟเฟกต์การหมุนข้อความที่ครอบคลุมมากยิ่งขึ้น

#### ถาม: การใช้ชิ้นส่วนข้อความและย่อหน้าเพื่อการหมุนข้อความมีข้อดีอะไรบ้าง

A: การใช้ข้อความและย่อหน้าร่วมกันทำให้การหมุนข้อความมีความยืดหยุ่นมากขึ้น ข้อความและย่อหน้าช่วยให้สามารถหมุนและจัดรูปแบบข้อความได้ตามความต้องการ ในขณะที่ย่อหน้าให้โครงสร้างสำหรับการจัดเรียงและจัดตำแหน่งข้อความและย่อหน้าภายในหน้า

#### ถาม: ฉันสามารถใช้มุมการหมุนที่แตกต่างกันกับส่วนข้อความที่แตกต่างกันภายในย่อหน้าเดียวกันได้หรือไม่

 A: ใช่ คุณสามารถปรับมุมการหมุนที่แตกต่างกันได้`TextFragment` วัตถุภายในย่อหน้าเดียวกัน ส่วนของข้อความแต่ละส่วนสามารถมีมุมการหมุนของตัวเองได้โดยใช้`TextState.Rotation` คุณสมบัติ.

#### ถาม: เป็นไปได้ไหมที่จะสร้างเอฟเฟ็กต์การหมุนข้อความที่ซับซ้อนด้วยวิธีนี้?

A: ใช่แล้ว คุณสามารถทำเอฟเฟกต์การหมุนข้อความที่ซับซ้อนและกำหนดเองได้ โดยการรวมส่วนข้อความที่มีมุมการหมุนต่างๆ และจัดเรียงภายในย่อหน้า เพื่อเพิ่มความสวยงามให้กับเอกสาร PDF ของคุณ

#### ถาม: มีขั้นตอนอะไรบ้างในการหมุนข้อความโดยใช้ชิ้นส่วนข้อความและย่อหน้า?

A: ขั้นตอนมีดังนี้:

1. การตั้งค่าโครงการโดยการสร้างโครงการ C# ใหม่และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET
2. การสร้างเอกสาร PDF และการเพิ่มหน้า
3. การสร้างชิ้นส่วนข้อความ ตั้งค่าคุณสมบัติ และระบุองศาการหมุน
4.  การเพิ่มชิ้นส่วนข้อความลงในหน้าโดยใช้`Paragraphs` ของสะสม.
5. บันทึกเอกสาร PDF ที่ถูกปรับเปลี่ยน

#### ถาม: ฉันสามารถใช้การหมุนไปทั่วทั้งย่อหน้าได้หรือไม่

 A: ใช่ คุณสามารถหมุนย่อหน้าทั้งหมดได้โดยการตั้งค่า`TextState.Rotation` คุณสมบัติของย่อหน้านั้นเอง ซึ่งจะหมุนส่วนข้อความทั้งหมดภายในย่อหน้านั้น