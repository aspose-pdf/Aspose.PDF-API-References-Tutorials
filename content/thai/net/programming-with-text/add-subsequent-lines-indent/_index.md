---
title: เพิ่มการเยื้องบรรทัดถัดไปในไฟล์ PDF
linktitle: เพิ่มการเยื้องบรรทัดถัดไปในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มการเยื้องบรรทัดถัดไปให้กับข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 60
url: /th/net/programming-with-text/add-subsequent-lines-indent/
---
บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการเพิ่มการเยื้องบรรทัดถัดไปให้กับข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ที่ติดตั้งบนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose หรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการเพิ่มการเยื้องบรรทัดถัดไป ให้เพิ่มคำสั่งต่อไปนี้โดยใช้คำสั่งที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเร็กทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่เก็บเอกสารของคุณ

## ขั้นตอนที่ 4: สร้างวัตถุเอกสารใหม่
 สร้างอินสแตนซ์ใหม่`Document` object โดยการเพิ่มบรรทัดโค้ดต่อไปนี้:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## ขั้นตอนที่ 5: เพิ่มหน้าลงในเอกสาร
 เพิ่มหน้าใหม่ให้กับเอกสารโดยใช้`Add` วิธีการของ`Pages`ของสะสม. ในโค้ดที่ให้มา หน้าใหม่จะถูกกำหนดให้กับตัวแปร`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## ขั้นตอนที่ 6: สร้าง TextFragment โดยมีการเยื้องบรรทัดตามมา
 ยกตัวอย่าง`TextFragment` วัตถุและระบุข้อความที่ต้องการ ในโค้ดที่ให้มา ข้อความจะถูกกำหนดให้กับตัวแปร`text` . จากนั้นเริ่มต้น`TextFormattingOptions` สำหรับ`TextFragment`และระบุ`SubsequentLinesIndent` ค่า.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## ขั้นตอนที่ 7: เพิ่ม TextFragment ลงในเพจ
 เพิ่ม`TextFragment` คัดค้านการรวบรวมย่อหน้าของเพจ

```csharp
page.Paragraphs.Add(text);
```

## ขั้นตอนที่ 8: ทำซ้ำขั้นตอนที่ 6 และ 7 สำหรับบรรทัดเพิ่มเติม
หากต้องการเพิ่มบรรทัดถัดไปด้วยการเยื้องเดียวกัน ให้ทำซ้ำขั้นตอนที่ 6 และ 7 สำหรับแต่ละบรรทัด อัปเดตเนื้อหาข้อความตามความจำเป็น

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
 บันทึกเอกสาร PDF โดยใช้ไฟล์`Save` วิธีการของ`Document` วัตถุ. ระบุเส้นทางไฟล์เอาต์พุต

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### ตัวอย่างซอร์สโค้ดสำหรับเพิ่มการเยื้องบรรทัดที่ตามมาโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างวัตถุเอกสารใหม่
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// เริ่มต้น TextFormattingOptions สำหรับส่วนของข้อความและระบุค่า SubsequentLinesIndent
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
คุณได้เพิ่มการเยื้องบรรทัดต่อมาให้กับข้อความโดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว ขณะนี้ไฟล์ PDF ที่เป็นผลลัพธ์สามารถพบได้ที่เส้นทางไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: บทช่วยสอนนี้เน้นอะไร

ตอบ: บทช่วยสอนนี้ให้คำแนะนำที่ครอบคลุมเกี่ยวกับวิธีเพิ่มการเยื้องบรรทัดถัดไปให้กับข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับไลบรารี .NET ประกอบด้วยตัวอย่างซอร์สโค้ด C# เพื่อแสดงขั้นตอนที่จำเป็นสำหรับการบรรลุเป้าหมายนี้

#### ถาม: ฉันจำเป็นต้องนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

ตอบ: ในไฟล์โค้ดที่คุณต้องการเพิ่มการเยื้องบรรทัดถัดไป ให้นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร

 ตอบ: ในโค้ด ให้ค้นหาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างออบเจ็กต์ Document ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 4 คุณจะสร้างอินสแตนซ์ใหม่`Document` วัตถุโดยใช้บรรทัดโค้ดต่อไปนี้:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### ถาม: ฉันจะเพิ่มหน้าลงในเอกสารได้อย่างไร

 ตอบ: ในขั้นตอนที่ 5 คุณจะต้องเพิ่มหน้าใหม่ให้กับเอกสารโดยใช้`Add` วิธีการของ`Pages` ของสะสม:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### ถาม: ฉันจะเพิ่มการเยื้องบรรทัดถัดไปลงในข้อความได้อย่างไร

 ตอบ: ในขั้นตอนที่ 6 คุณจะสร้างไฟล์`TextFragment` วัตถุและกำหนดข้อความที่ต้องการ จากนั้นคุณจะเริ่มต้น`TextFormattingOptions` สำหรับ`TextFragment`และระบุ`SubsequentLinesIndent` ค่า:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### ถาม: ฉันจะเพิ่ม TextFragment ลงในเอกสาร PDF ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 7 คุณจะต้องเพิ่มไฟล์`TextFragment` วัตถุ (`text`) ไปยังคอลเลกชันย่อหน้าของหน้า:

```csharp
page.Paragraphs.Add(text);
```

#### ถาม: ฉันสามารถทำซ้ำขั้นตอนนี้กับบรรทัดเพิ่มเติมได้หรือไม่

 ตอบ: ได้ ในขั้นตอนที่ 8 คุณสามารถทำซ้ำขั้นตอนสำหรับบรรทัดเพิ่มเติมที่มีการเยื้องเดียวกันได้โดยการสร้างใหม่`TextFragment` วัตถุและเพิ่มลงในคอลเลกชันย่อหน้าของหน้า

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่ได้ได้อย่างไร

 ตอบ: หลังจากเพิ่มข้อความโดยมีการเยื้องบรรทัดถัดๆ ไป ให้ใช้`Save` วิธีการของ`Document` วัตถุเพื่อบันทึกเอกสาร PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### ถาม: สิ่งสำคัญที่ได้รับจากบทช่วยสอนนี้คืออะไร

ตอบ: เมื่อทำตามบทช่วยสอนนี้ คุณได้เรียนรู้วิธีปรับปรุงความสามารถในการอ่านข้อความในเอกสาร PDF สำเร็จแล้วโดยการเพิ่มการเยื้องบรรทัดตามมาโดยใช้ Aspose.PDF สำหรับ .NET เทคนิคนี้สามารถเป็นประโยชน์กับเอกสารและรายงานประเภทต่างๆ