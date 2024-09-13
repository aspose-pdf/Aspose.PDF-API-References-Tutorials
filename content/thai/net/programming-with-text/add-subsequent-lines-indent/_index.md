---
title: เพิ่มบรรทัดถัดไปในไฟล์ PDF
linktitle: เพิ่มบรรทัดถัดไปในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีเพิ่มบรรทัดถัดไปในการเยื้องข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 60
url: /th/net/programming-with-text/add-subsequent-lines-indent/
---
บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการเพิ่มบรรทัดย่อหน้าในข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ติดตั้งอยู่บนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose อย่างเป็นทางการหรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการเพิ่มบรรทัดต่อๆ ไป ให้เพิ่มคำสั่ง using ต่อไปนี้ที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเรกทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณเก็บเอกสารไว้

## ขั้นตอนที่ 4: สร้างวัตถุเอกสารใหม่
 สร้างอินสแตนซ์ใหม่`Document` วัตถุโดยการเพิ่มบรรทัดโค้ดดังต่อไปนี้:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## ขั้นตอนที่ 5: เพิ่มหน้าลงในเอกสาร
 เพิ่มหน้าใหม่ลงในเอกสารโดยใช้`Add` วิธีการของ`Pages` คอลเลกชัน ในโค้ดที่ให้มา หน้าใหม่จะถูกกำหนดให้กับตัวแปร`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## ขั้นตอนที่ 6: สร้าง TextFragment พร้อมย่อบรรทัดถัดไป
 สร้างตัวอย่าง`TextFragment` วัตถุและระบุข้อความที่ต้องการ ในโค้ดที่ให้มา ข้อความจะถูกกำหนดให้กับตัวแปร`text` . จากนั้นทำการเริ่มระบบ`TextFormattingOptions` สำหรับ`TextFragment` และระบุ`SubsequentLinesIndent` ค่า.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## ขั้นตอนที่ 7: เพิ่ม TextFragment ลงในหน้า
 เพิ่ม`TextFragment` คัดค้านการรวบรวมย่อหน้าของหน้า

```csharp
page.Paragraphs.Add(text);
```

## ขั้นตอนที่ 8: ทำซ้ำขั้นตอนที่ 6 และ 7 สำหรับบรรทัดเพิ่มเติม
หากต้องการเพิ่มบรรทัดถัดไปด้วยการเยื้องย่อหน้าเท่ากัน ให้ทำซ้ำขั้นตอน 6 และ 7 สำหรับแต่ละบรรทัด อัปเดตเนื้อหาข้อความตามต้องการ

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## ขั้นตอนที่ 9: บันทึกเอกสาร PDF
 บันทึกเอกสาร PDF โดยใช้`Save` วิธีการของ`Document` วัตถุ ระบุเส้นทางไฟล์เอาท์พุต

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการเพิ่มบรรทัดถัดไปด้วยการย่อหน้าโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างวัตถุเอกสารใหม่
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
//เริ่มต้น TextFormattingOptions สำหรับส่วนข้อความและระบุค่า SubsequentLinesIndent
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## บทสรุป
คุณได้เพิ่มบรรทัดถัดไปในข้อความโดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว ตอนนี้สามารถพบไฟล์ PDF ที่ได้ในเส้นทางไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: บทช่วยสอนนี้เน้นอะไร?

A: บทช่วยสอนนี้ให้คำแนะนำที่ครอบคลุมเกี่ยวกับวิธีการเพิ่มบรรทัดถัดไปในข้อความในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET บทช่วยสอนนี้มีตัวอย่างโค้ดต้นฉบับของ C# เพื่ออธิบายขั้นตอนที่จำเป็นในการบรรลุผลดังกล่าว

#### ถาม: ฉันต้องนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

ก: ในไฟล์โค้ดที่คุณต้องการเพิ่มบรรทัดต่อๆ ไป ให้แทรกเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร?

 ก: ในโค้ด ให้ระบุตำแหน่งบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างวัตถุเอกสารได้อย่างไร

 ก: ในขั้นตอนที่ 4 คุณจะสร้างอินสแตนซ์ใหม่`Document` วัตถุที่ใช้บรรทัดโค้ดต่อไปนี้:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### ถาม: ฉันจะเพิ่มหน้าลงในเอกสารได้อย่างไร

 ก: ในขั้นตอนที่ 5 คุณจะเพิ่มหน้าใหม่ลงในเอกสารโดยใช้`Add` วิธีการของ`Pages` ของสะสม:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### ถาม: ฉันจะเพิ่มบรรทัดถัดไปในการเยื้องข้อความได้อย่างไร

 A: ในขั้นตอนที่ 6 คุณจะสร้าง`TextFragment` วัตถุและกำหนดข้อความที่ต้องการให้กับวัตถุนั้น จากนั้นคุณจะเริ่มต้น`TextFormattingOptions` สำหรับ`TextFragment` และระบุ`SubsequentLinesIndent` ค่า:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### ถาม: ฉันจะเพิ่ม TextFragment ลงในเอกสาร PDF ได้อย่างไร

 A: ในขั้นตอนที่ 7 คุณจะเพิ่ม`TextFragment` วัตถุ (`text`) ไปยังคอลเลกชันย่อหน้าของหน้า:

```csharp
page.Paragraphs.Add(text);
```

#### ถาม: ฉันสามารถทำซ้ำขั้นตอนกับบรรทัดเพิ่มเติมได้ไหม

A: ใช่ ในขั้นตอนที่ 8 คุณสามารถทำซ้ำขั้นตอนสำหรับบรรทัดเพิ่มเติมที่มีการเยื้องเท่ากันโดยสร้างบรรทัดใหม่`TextFragment` วัตถุและเพิ่มเข้าในคอลเล็กชั่นย่อหน้าของหน้า

#### ถาม: ฉันจะบันทึกเอกสาร PDF ผลลัพธ์ได้อย่างไร

 ก: หลังจากเพิ่มข้อความด้วยการย่อบรรทัดถัดไป ให้ใช้`Save` วิธีการของ`Document` วัตถุที่จะบันทึกเอกสาร PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### ถาม: สิ่งสำคัญที่ได้จากบทช่วยสอนนี้คืออะไร?

A: เมื่อทำตามบทช่วยสอนนี้แล้ว คุณจะเรียนรู้วิธีการปรับปรุงการอ่านข้อความในเอกสาร PDF ให้ดีขึ้นได้สำเร็จโดยเพิ่มบรรทัดย่อหน้าถัดไปโดยใช้ Aspose.PDF สำหรับ .NET เทคนิคนี้สามารถใช้กับเอกสารและรายงานประเภทต่างๆ ได้