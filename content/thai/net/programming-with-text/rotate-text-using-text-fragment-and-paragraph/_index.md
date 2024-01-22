---
title: หมุนข้อความโดยใช้ส่วนของข้อความและย่อหน้า
linktitle: หมุนข้อความโดยใช้ส่วนของข้อความและย่อหน้า
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีหมุนข้อความโดยใช้ส่วนของข้อความและย่อหน้าในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 400
url: /th/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อหมุนข้อความโดยใช้ส่วนของข้อความและย่อหน้า ซอร์สโค้ด C# ที่ให้มาสาธิตกระบวนการทีละขั้นตอน

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

## ขั้นตอนที่ 3: สร้างเอกสาร PDF

 เริ่มต้น`Document` วัตถุเพื่อสร้างเอกสาร PDF ใหม่:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: เพิ่มหน้า

 รับหน้าใดหน้าหนึ่งจากเอกสารโดยใช้`Pages.Add()` วิธี:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## ขั้นตอนที่ 5: สร้างส่วนของข้อความ

 สร้างหลายรายการ`TextFragment` วัตถุ ตั้งค่าข้อความและคุณสมบัติ และระบุมุมการหมุน:

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

ปรับข้อความ มุมการหมุน และคุณสมบัติอื่นๆ ตามต้องการ

## ขั้นตอนที่ 6: เพิ่มส่วนของข้อความลงในหน้า

 เพิ่มส่วนของข้อความที่สร้างขึ้นลงในเพจโดยผนวกเข้ากับ`Paragraphs` ของสะสม:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## ขั้นตอนที่ 7: บันทึกเอกสาร PDF

 บันทึกเอกสาร PDF ที่แก้ไขแล้วลงในไฟล์โดยใช้นามสกุล`Save` วิธี:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"TextFragmentTests_Rotated3_out.pdf"` ด้วยชื่อไฟล์เอาต์พุตที่ต้องการ

### ซอร์สโค้ดตัวอย่างสำหรับการหมุนข้อความโดยใช้ส่วนข้อความและย่อหน้าโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เริ่มต้นวัตถุเอกสาร
Document pdfDocument = new Document();
// รับเฉพาะหน้า
Page pdfPage = (Page)pdfDocument.Pages.Add();
// สร้างส่วนของข้อความ
TextFragment textFragment1 = new TextFragment("main text");
// ตั้งค่าคุณสมบัติข้อความ
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// สร้างส่วนของข้อความ
TextFragment textFragment2 = new TextFragment("rotated text");
// ตั้งค่าคุณสมบัติข้อความ
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// ตั้งค่าการหมุน
textFragment2.TextState.Rotation = 315;
// สร้างส่วนของข้อความ
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

ยินดีด้วย! คุณได้เรียนรู้วิธีการหมุนข้อความโดยใช้ส่วนของข้อความและย่อหน้าในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอน ตั้งแต่การสร้างเอกสารไปจนถึงการบันทึกเวอร์ชันที่แก้ไข ตอนนี้คุณสามารถรวมโค้ดนี้เข้ากับโปรเจ็กต์ C# ของคุณเองเพื่อจัดการการหมุนข้อความในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "หมุนข้อความโดยใช้ส่วนข้อความและย่อหน้า" คืออะไร

ตอบ: บทช่วยสอน "หมุนข้อความโดยใช้ส่วนข้อความและย่อหน้า" มีวัตถุประสงค์เพื่อแนะนำคุณตลอดกระบวนการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อหมุนข้อความโดยใช้ทั้งส่วนข้อความและย่อหน้าภายในเอกสาร PDF บทช่วยสอนให้คำแนะนำทีละขั้นตอนและโค้ดตัวอย่างเพื่อให้บรรลุฟังก์ชันนี้

#### ถาม: บทช่วยสอนนี้แตกต่างจากบทช่วยสอนการหมุนข้อความก่อนหน้าอย่างไร

ตอบ: บทช่วยสอนนี้เป็นการรวมการใช้ส่วนของข้อความและย่อหน้าเพื่อให้สามารถหมุนเวียนข้อความภายในเอกสาร PDF ได้ โดยจะสาธิตวิธีการหมุนส่วนของข้อความทีละส่วนแล้วเพิ่มลงในหน้า`Paragraphs` คอลเลกชันเพื่อให้ได้เอฟเฟกต์การหมุนข้อความที่ครอบคลุมมากขึ้น

#### ถาม: ข้อดีของการใช้ส่วนย่อยของข้อความและย่อหน้าสำหรับการหมุนข้อความมีอะไรบ้าง

ตอบ: การใช้ส่วนของข้อความและย่อหน้าร่วมกันจะช่วยให้การหมุนข้อความมีความยืดหยุ่นมากขึ้น ส่วนของข้อความเปิดใช้งานการตั้งค่าการหมุนและการจัดรูปแบบแต่ละรายการ ในขณะที่ย่อหน้าจะมีโครงสร้างสำหรับการจัดเรียงและการวางตำแหน่งส่วนของข้อความภายในหน้า

#### ถาม: ฉันสามารถใช้มุมการหมุนที่แตกต่างกันกับส่วนของข้อความที่แตกต่างกันภายในย่อหน้าเดียวกันได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้มุมการหมุนที่แตกต่างกันกับมุมต่างๆ ได้`TextFragment` วัตถุที่อยู่ในย่อหน้าเดียวกัน ส่วนของข้อความแต่ละส่วนสามารถระบุมุมการหมุนของตัวเองได้โดยใช้`TextState.Rotation` คุณสมบัติ.

#### ถาม: เป็นไปได้หรือไม่ที่จะได้เอฟเฟกต์การหมุนข้อความที่ซับซ้อนโดยใช้วิธีนี้

ตอบ: ได้ ด้วยการรวมส่วนของข้อความเข้ากับมุมการหมุนต่างๆ แล้วจัดเรียงไว้ภายในย่อหน้า คุณสามารถสร้างเอฟเฟกต์การหมุนข้อความที่ซับซ้อนและปรับแต่งเองได้ ซึ่งจะช่วยเพิ่มความดึงดูดสายตาให้กับเอกสาร PDF ของคุณ

#### ถาม: ขั้นตอนใดบ้างที่เกี่ยวข้องกับการหมุนข้อความโดยใช้ส่วนของข้อความและย่อหน้า

ตอบ: ขั้นตอนประกอบด้วย:

1. การตั้งค่าโปรเจ็กต์โดยการสร้างโปรเจ็กต์ C# ใหม่และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET
2. การสร้างเอกสาร PDF และเพิ่มหน้า
3. การสร้างส่วนของข้อความ การตั้งค่าคุณสมบัติ และการระบุมุมการหมุน
4.  การเพิ่มส่วนของข้อความลงในเพจโดยใช้`Paragraphs` ของสะสม.
5. บันทึกเอกสาร PDF ที่แก้ไข

#### ถาม: ฉันสามารถใช้การหมุนกับทั้งย่อหน้าได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้การหมุนกับทั้งย่อหน้าได้โดยการตั้งค่า`TextState.Rotation` ทรัพย์สินของวรรคนั้นเอง วิธีนี้จะหมุนส่วนของข้อความทั้งหมดภายในย่อหน้านั้น