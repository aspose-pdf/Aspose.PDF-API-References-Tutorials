---
title: ค้นหานิพจน์ทั่วไปในไฟล์ PDF
linktitle: ค้นหานิพจน์ทั่วไปในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีค้นหาและดึงข้อความโดยใช้นิพจน์ทั่วไปในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 440
url: /th/net/programming-with-text/search-regular-expression/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อค้นหาและดึงข้อความที่ตรงกับนิพจน์ทั่วไปในไฟล์ PDF โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนต่างๆ ของกระบวนการทีละขั้นตอน

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

## ขั้นตอนที่ 3: โหลดเอกสาร PDF

 ตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสาร PDF ของคุณและโหลดเอกสารโดยใช้`Document` ระดับ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: ค้นหาด้วยนิพจน์ทั่วไป

 สร้าง`TextFragmentAbsorber` วัตถุและกำหนดรูปแบบนิพจน์ทั่วไปเพื่อค้นหาวลีทั้งหมดที่ตรงกับรูปแบบ:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // ประมาณปี 1999-2000
```

 แทนที่`"\\d{4}-\\d{4}"` ด้วยรูปแบบนิพจน์ปกติของคุณตามที่ต้องการ

## ขั้นตอนที่ 5: ตั้งค่าตัวเลือกการค้นหาข้อความ

 สร้าง`TextSearchOptions` วัตถุและตั้งมันไว้เป็น`TextSearchOptions` ทรัพย์สินของ`TextFragmentAbsorber` วัตถุที่จะเปิดใช้งานการใช้นิพจน์ปกติ:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## ขั้นตอนที่ 6: ค้นหาในทุกหน้า

รับตัวดูดซับสำหรับทุกหน้าของเอกสาร:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## ขั้นตอนที่ 7: ดึงข้อมูลข้อความที่แยกออกมา

 รับชิ้นส่วนข้อความที่แยกออกมาโดยใช้`TextFragments` ทรัพย์สินของ`TextFragmentAbsorber` วัตถุ:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ขั้นตอนที่ 8: วนซ้ำผ่านชิ้นส่วนข้อความ

วนซ้ำผ่านชิ้นส่วนข้อความที่เรียกค้นและเข้าถึงคุณสมบัติของมัน:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text: {0} ", textFragment.Text);
	Console.WriteLine("Position: {0} ", textFragment.Position);
	Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

คุณสามารถปรับเปลี่ยนโค้ดภายในลูปเพื่อดำเนินการเพิ่มเติมกับส่วนข้อความแต่ละส่วนได้

### ตัวอย่างโค้ดต้นฉบับสำหรับการค้นหานิพจน์ทั่วไปโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
//สร้างวัตถุ TextAbsorber เพื่อค้นหาวลีทั้งหมดที่ตรงกับนิพจน์ทั่วไป
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // ประมาณปี 1999-2000
// ตั้งค่าตัวเลือกการค้นหาข้อความเพื่อระบุการใช้งานนิพจน์ปกติ
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// รับตัวดูดซับสำหรับทุกหน้า
pdfDocument.Pages.Accept(textFragmentAbsorber);
// รับชิ้นส่วนข้อความที่แยกออกมา
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// วนผ่านชิ้นส่วน
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีค้นหาและดึงข้อความที่ตรงกับนิพจน์ทั่วไปในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนตั้งแต่การโหลดเอกสารไปจนถึงการเข้าถึงส่วนข้อความที่แยกออกมา ตอนนี้คุณสามารถนำโค้ดนี้ไปใช้กับโปรเจ็กต์ C# ของคุณเองเพื่อค้นหาข้อความขั้นสูงในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "ค้นหานิพจน์ทั่วไปในไฟล์ PDF" คืออะไร

A: บทช่วยสอน "ค้นหานิพจน์ทั่วไปในไฟล์ PDF" มีวัตถุประสงค์เพื่อแสดงวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อค้นหาและแยกข้อความที่ตรงกับรูปแบบนิพจน์ทั่วไปที่ระบุภายในไฟล์ PDF บทช่วยสอนนี้ให้คำแนะนำที่ครอบคลุมและตัวอย่างโค้ด C# เพื่อสาธิตกระบวนการ

#### ถาม: บทช่วยสอนนี้ช่วยในการค้นหาข้อความโดยใช้นิพจน์ทั่วไปในเอกสาร PDF ได้อย่างไร

A: บทช่วยสอนนี้อธิบายวิธีการใช้งานไลบรารี Aspose.PDF เพื่อค้นหาข้อความในเอกสาร PDF โดยอิงตามรูปแบบนิพจน์ทั่วไป โดยจะอธิบายรายละเอียดเกี่ยวกับการตั้งค่าโครงการ การโหลดเอกสาร PDF การกำหนดรูปแบบนิพจน์ทั่วไป และการดึงข้อมูลส่วนที่ตรงกัน

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการปฏิบัติตามบทช่วยสอนนี้คืออะไร

A: ก่อนเริ่มบทช่วยสอนนี้ คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# นอกจากนี้ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET คุณสามารถรับได้จากเว็บไซต์ Aspose หรือใช้ NuGet เพื่อรวมเข้ากับโครงการของคุณ

#### ถาม: ฉันจะตั้งค่าโครงการเพื่อทำตามบทช่วยสอนนี้ได้อย่างไร

A: ในการเริ่มต้น ให้สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET วิธีนี้จะช่วยให้คุณใช้ประโยชน์จากความสามารถของไลบรารีภายในโครงการของคุณได้

#### ถาม: ฉันสามารถใช้นิพจน์ทั่วไปเพื่อค้นหาข้อความในเอกสาร PDF ได้หรือไม่

 A: ใช่ บทช่วยสอนนี้สาธิตวิธีใช้นิพจน์ทั่วไปเพื่อค้นหาและแยกข้อความจากเอกสาร PDF ซึ่งเกี่ยวข้องกับการใช้`TextFragmentAbsorber` คลาสและระบุรูปแบบนิพจน์ทั่วไปเพื่อค้นหาวลีที่ตรงกับรูปแบบที่ให้ไว้

#### ถาม: ฉันจะกำหนดรูปแบบนิพจน์ทั่วไปสำหรับการค้นหาข้อความได้อย่างไร

 ก: เพื่อกำหนดรูปแบบนิพจน์ทั่วไปสำหรับการค้นหาข้อความ ให้สร้าง`TextFragmentAbsorber` วัตถุและกำหนดรูปแบบโดยใช้`Text` พารามิเตอร์ แทนที่รูปแบบเริ่มต้น`"\\d{4}-\\d{4}"` ในโค้ดของบทช่วยสอนพร้อมรูปแบบนิพจน์ปกติที่คุณต้องการ

#### ถาม: ฉันจะเปิดใช้งานการใช้นิพจน์ปกติสำหรับการค้นหาข้อความได้อย่างไร

 A: การใช้งานนิพจน์ทั่วไปจะเปิดใช้งานได้โดยการสร้าง`TextSearchOptions` วัตถุและการตั้งค่าเป็น`true` . กำหนดวัตถุนี้ให้กับ`TextSearchOptions` ทรัพย์สินของ`TextFragmentAbsorber` อินสแตนซ์ การดำเนินการนี้จะช่วยให้แน่ใจว่ารูปแบบนิพจน์ทั่วไปจะถูกใช้ในระหว่างการค้นหาข้อความ

#### ถาม: ฉันสามารถดึงข้อมูลข้อความที่ตรงกับรูปแบบนิพจน์ปกติได้หรือไม่

 A: แน่นอน หลังจากใช้การค้นหานิพจน์ทั่วไปในเอกสาร PDF แล้ว คุณสามารถดึงข้อมูลส่วนที่แยกออกมาโดยใช้`TextFragments` ทรัพย์สินของ`TextFragmentAbsorber` วัตถุ เศษข้อความเหล่านี้ประกอบด้วยกลุ่มข้อความที่ตรงกับรูปแบบนิพจน์ปกติที่ระบุ

#### ถาม: ฉันสามารถเข้าถึงอะไรได้บ้างจากชิ้นส่วนข้อความที่เรียกค้นได้

A: จากชิ้นส่วนข้อความที่เรียกค้นมา คุณสามารถเข้าถึงคุณสมบัติต่างๆ เช่น เนื้อหาข้อความที่ตรงกัน ตำแหน่ง (พิกัด X และ Y) ข้อมูลแบบอักษร (ชื่อ ขนาด สี) และอื่นๆ อีกมากมาย โค้ดตัวอย่างภายในลูปของบทช่วยสอนจะสาธิตวิธีการเข้าถึงและแสดงคุณสมบัติเหล่านี้

#### ถาม: ฉันจะปรับแต่งการกระทำกับชิ้นส่วนข้อความที่แยกออกมาได้อย่างไร

A: เมื่อคุณแยกส่วนข้อความที่ได้แล้ว คุณสามารถปรับแต่งโค้ดภายในลูปเพื่อดำเนินการเพิ่มเติมกับส่วนข้อความแต่ละส่วนได้ ซึ่งอาจรวมถึงการบันทึกข้อความที่แยกออกมา การวิเคราะห์รูปแบบ หรือการนำการเปลี่ยนแปลงการจัดรูปแบบไปใช้ตามความต้องการของคุณ