---
title: ค้นหานิพจน์ทั่วไปในไฟล์ PDF
linktitle: ค้นหานิพจน์ทั่วไปในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีค้นหาและดึงข้อความโดยใช้นิพจน์ทั่วไปในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 440
url: /th/net/programming-with-text/search-regular-expression/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อค้นหาและดึงข้อความที่ตรงกับนิพจน์ทั่วไปในไฟล์ PDF ซอร์สโค้ด C# ที่ให้มาสาธิตกระบวนการทีละขั้นตอน

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

## ขั้นตอนที่ 3: โหลดเอกสาร PDF

 กำหนดเส้นทางไปยังไดเร็กทอรีเอกสาร PDF ของคุณและโหลดเอกสารโดยใช้`Document` ระดับ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: ค้นหาด้วยนิพจน์ทั่วไป

 สร้างก`TextFragmentAbsorber` object และตั้งค่ารูปแบบนิพจน์ทั่วไปเพื่อค้นหาวลีทั้งหมดที่ตรงกับรูปแบบ:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // เหมือนปี 1999-2000
```

 แทนที่`"\\d{4}-\\d{4}"` ด้วยรูปแบบนิพจน์ทั่วไปที่คุณต้องการ

## ขั้นตอนที่ 5: ตั้งค่าตัวเลือกการค้นหาข้อความ

 สร้างก`TextSearchOptions` วัตถุและตั้งค่าเป็น`TextSearchOptions` ทรัพย์สินของ`TextFragmentAbsorber` วัตถุเพื่อเปิดใช้งานการใช้งานนิพจน์ทั่วไป:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## ขั้นตอนที่ 6: ค้นหาในทุกหน้า

ยอมรับตัวดูดซับสำหรับทุกหน้าของเอกสาร:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## ขั้นตอนที่ 7: ดึงส่วนข้อความที่แยกออกมา

รับส่วนของข้อความที่แยกออกมาโดยใช้`TextFragments` ทรัพย์สินของ`TextFragmentAbsorber` วัตถุ:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ขั้นตอนที่ 8: วนซ้ำส่วนข้อความ

วนซ้ำส่วนข้อความที่ดึงมาและเข้าถึงคุณสมบัติ:

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

คุณสามารถแก้ไขโค้ดภายในลูปเพื่อดำเนินการเพิ่มเติมกับแต่ละส่วนของข้อความได้

### ตัวอย่างซอร์สโค้ดสำหรับการค้นหานิพจน์ทั่วไปโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// สร้างวัตถุ TextAbsorber เพื่อค้นหาวลีทั้งหมดที่ตรงกับนิพจน์ทั่วไป
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // เหมือนปี 1999-2000
// ตั้งค่าตัวเลือกการค้นหาข้อความเพื่อระบุการใช้นิพจน์ทั่วไป
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// รับซับทุกหน้า
pdfDocument.Pages.Accept(textFragmentAbsorber);
// รับส่วนของข้อความที่แยกออกมา
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

ยินดีด้วย! คุณได้เรียนรู้วิธีการค้นหาและดึงข้อความที่ตรงกับนิพจน์ทั่วไปในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอน ตั้งแต่การโหลดเอกสารไปจนถึงการเข้าถึงส่วนย่อยของข้อความที่แยกออกมา ตอนนี้คุณสามารถรวมโค้ดนี้เข้ากับโปรเจ็กต์ C# ของคุณเองเพื่อทำการค้นหาข้อความขั้นสูงในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "ค้นหานิพจน์ปกติในไฟล์ PDF" คืออะไร

ตอบ: บทช่วยสอน "ค้นหานิพจน์ปกติในไฟล์ PDF" มีวัตถุประสงค์เพื่อแสดงวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อค้นหาและแยกข้อความที่ตรงกับรูปแบบนิพจน์ทั่วไปที่ระบุภายในไฟล์ PDF บทช่วยสอนนี้จะให้คำแนะนำที่ครอบคลุมและตัวอย่างโค้ด C# เพื่อสาธิตกระบวนการ

#### ถาม: บทช่วยสอนนี้ช่วยในการค้นหาข้อความโดยใช้นิพจน์ทั่วไปในเอกสาร PDF อย่างไร

ตอบ: บทช่วยสอนนี้ให้แนวทางทีละขั้นตอนในการใช้ไลบรารี Aspose.PDF เพื่อค้นหาข้อความในเอกสาร PDF ตามรูปแบบนิพจน์ทั่วไป โดยให้รายละเอียดวิธีการตั้งค่าโปรเจ็กต์ โหลดเอกสาร PDF กำหนดรูปแบบนิพจน์ทั่วไป และดึงส่วนของข้อความที่ตรงกัน

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการติดตามบทช่วยสอนนี้มีอะไรบ้าง

ตอบ: ก่อนที่จะเริ่มบทช่วยสอนนี้ คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# นอกจากนี้ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET ด้วย คุณสามารถรับได้จากเว็บไซต์ Aspose หรือใช้ NuGet เพื่อรวมเข้ากับโปรเจ็กต์ของคุณ

#### ถาม: ฉันจะตั้งค่าโปรเจ็กต์ให้ปฏิบัติตามบทช่วยสอนนี้ได้อย่างไร

ตอบ: ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบรวม (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET สิ่งนี้จะช่วยให้คุณสามารถใช้ประโยชน์จากความสามารถของห้องสมุดภายในโครงการของคุณได้

#### ถาม: ฉันสามารถใช้นิพจน์ทั่วไปเพื่อค้นหาข้อความในเอกสาร PDF ได้หรือไม่

 ตอบ: ใช่ บทช่วยสอนนี้สาธิตวิธีใช้นิพจน์ทั่วไปเพื่อค้นหาและแยกข้อความจากเอกสาร PDF มันเกี่ยวข้องกับการใช้`TextFragmentAbsorber` และระบุรูปแบบนิพจน์ทั่วไปเพื่อค้นหาวลีที่ตรงกับรูปแบบที่กำหนด

#### ถาม: ฉันจะกำหนดรูปแบบนิพจน์ทั่วไปสำหรับการค้นหาข้อความได้อย่างไร

 ตอบ: หากต้องการกำหนดรูปแบบนิพจน์ทั่วไปสำหรับการค้นหาข้อความ ให้สร้าง a`TextFragmentAbsorber` วัตถุและกำหนดรูปแบบโดยใช้`Text` พารามิเตอร์. แทนที่รูปแบบเริ่มต้น`"\\d{4}-\\d{4}"` ในโค้ดของบทช่วยสอนด้วยรูปแบบนิพจน์ทั่วไปที่คุณต้องการ

#### ถาม: ฉันจะเปิดใช้งานการใช้นิพจน์ทั่วไปสำหรับการค้นหาข้อความได้อย่างไร

 ตอบ: การใช้งานนิพจน์ทั่วไปเปิดใช้งานได้โดยการสร้าง`TextSearchOptions` วัตถุและตั้งค่าเป็น`true` . กำหนดวัตถุนี้ให้กับ`TextSearchOptions` ทรัพย์สินของ`TextFragmentAbsorber` ตัวอย่าง. เพื่อให้แน่ใจว่ามีการใช้รูปแบบนิพจน์ทั่วไปในระหว่างการค้นหาข้อความ

#### ถาม: ฉันสามารถเรียกส่วนย่อยของข้อความที่ตรงกับรูปแบบนิพจน์ทั่วไปได้หรือไม่

 ตอบ: อย่างแน่นอน หลังจากใช้การค้นหานิพจน์ทั่วไปในเอกสาร PDF คุณสามารถดึงส่วนข้อความที่แยกออกมาได้โดยใช้`TextFragments` ทรัพย์สินของ`TextFragmentAbsorber` วัตถุ. ส่วนของข้อความเหล่านี้มีส่วนข้อความที่ตรงกับรูปแบบนิพจน์ทั่วไปที่ระบุ

#### ถาม: ฉันสามารถเข้าถึงอะไรได้บ้างจากส่วนย่อยของข้อความที่ดึงมา

ตอบ: จากส่วนของข้อความที่ดึงมา คุณสามารถเข้าถึงคุณสมบัติต่างๆ ได้ เช่น เนื้อหาข้อความที่ตรงกัน ตำแหน่ง (พิกัด X และ Y) ข้อมูลแบบอักษร (ชื่อ ขนาด สี) และอื่นๆ โค้ดตัวอย่างภายในลูปของบทช่วยสอนสาธิตวิธีการเข้าถึงและแสดงคุณสมบัติเหล่านี้

#### ถาม: ฉันจะปรับแต่งการดำเนินการในส่วนข้อความที่แยกออกมาได้อย่างไร

ตอบ: เมื่อคุณมีส่วนของข้อความที่แยกออกมาแล้ว คุณสามารถปรับแต่งโค้ดภายในลูปเพื่อดำเนินการเพิ่มเติมกับส่วนของข้อความแต่ละส่วนได้ ซึ่งอาจรวมถึงการบันทึกข้อความที่แยกออกมา การวิเคราะห์รูปแบบ หรือการนำการเปลี่ยนแปลงการจัดรูปแบบไปใช้ตามความต้องการของคุณ