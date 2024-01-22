---
title: ค้นหาหน้าส่วนข้อความในไฟล์ PDF
linktitle: ค้นหาหน้าส่วนข้อความในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีค้นหาส่วนของข้อความบนเพจในไฟล์ PDF และดึงคุณสมบัติโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 470
url: /th/net/programming-with-text/search-text-segments-page/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อค้นหาส่วนข้อความที่ต้องการบนหน้าของไฟล์ PDF และดึงคุณสมบัติเหล่านั้น ซอร์สโค้ด C# ที่ให้มาสาธิตกระบวนการทีละขั้นตอน

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

## ขั้นตอนที่ 4: โหลดเอกสาร PDF

 โหลดเอกสาร PDF โดยใช้ไฟล์`Document` ระดับ:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 แทนที่`"SearchTextSegmentsPage.pdf"` ด้วยชื่อจริงของไฟล์ PDF ของคุณ

## ขั้นตอนที่ 5: สร้าง TextFragmentAbsorber

 สร้างก`TextFragmentAbsorber` วัตถุเพื่อค้นหาทุกกรณีของวลีค้นหาอินพุต:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 แทนที่`"text"` ด้วยวลีค้นหาที่คุณต้องการ

## ขั้นตอนที่ 6: ยอมรับตัวดูดซับสำหรับหน้าเฉพาะ

ยอมรับตัวดูดซับสำหรับหน้าเอกสารที่ต้องการ:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 แทนที่`2` ด้วยหมายเลขหน้าที่ต้องการ (ดัชนีฐาน 1)

## ขั้นตอนที่ 7: ดึงส่วนข้อความที่แยกออกมา

 รับส่วนของข้อความที่แยกออกมาโดยใช้`TextFragments` ทรัพย์สินของ`TextFragmentAbsorber` วัตถุ:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ขั้นตอนที่ 8: วนซ้ำส่วนของข้อความ

วนซ้ำส่วนข้อความที่ดึงข้อมูลและเข้าถึงคุณสมบัติ:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

แก้ไขโค้ดภายในลูปเพื่อดำเนินการเพิ่มเติมกับแต่ละส่วนของข้อความ หากจำเป็น

### ตัวอย่างซอร์สโค้ดสำหรับหน้าส่วนข้อความค้นหาโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// สร้างวัตถุ TextAbsorber เพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีค้นหาอินพุต
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// รับซับทุกหน้า
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// รับส่วนของข้อความที่แยกออกมา
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// วนผ่านชิ้นส่วน
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีค้นหาส่วนข้อความเฉพาะบนหน้าเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอน ตั้งแต่การโหลดเอกสารไปจนถึงการเข้าถึงส่วนข้อความที่แยกออกมา ตอนนี้คุณสามารถรวมโค้ดนี้เข้ากับโปรเจ็กต์ C# ของคุณเองเพื่อทำการค้นหาส่วนข้อความขั้นสูงในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "ค้นหาส่วนข้อความในไฟล์ PDF" คืออะไร

ตอบ: บทช่วยสอน "ค้นหาหน้าเซ็กเมนต์ข้อความในไฟล์ PDF" ให้คำแนะนำที่ครอบคลุมเกี่ยวกับวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อค้นหาเซ็กเมนต์ข้อความเฉพาะในหน้าใดหน้าหนึ่งของเอกสาร PDF โดยครอบคลุมกระบวนการตั้งค่าโปรเจ็กต์ การโหลดเอกสาร PDF การค้นหาส่วนข้อความ และการดึงคุณสมบัติโดยใช้โค้ด C#

#### ถาม: บทช่วยสอนนี้ช่วยในการค้นหาส่วนข้อความเฉพาะในเอกสาร PDF อย่างไร

ตอบ: บทช่วยสอนนี้สาธิตกระบวนการค้นหาและแยกส่วนข้อความเฉพาะในหน้าใดหน้าหนึ่งของเอกสาร PDF ด้วยการทำตามขั้นตอนและตัวอย่างโค้ดที่ให้มา ผู้ใช้สามารถค้นหาส่วนของข้อความที่ต้องการและดึงข้อมูลเกี่ยวกับคุณสมบัติได้อย่างมีประสิทธิภาพ

#### ถาม: ข้อกำหนดเบื้องต้นใดบ้างที่จำเป็นในการปฏิบัติตามบทช่วยสอนนี้

ตอบ: ก่อนที่จะเริ่มบทช่วยสอน คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# นอกจากนี้ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET ด้วย คุณสามารถรับได้จากเว็บไซต์ Aspose หรือติดตั้งในโครงการของคุณโดยใช้ NuGet

#### ถาม: ฉันจะตั้งค่าโปรเจ็กต์ให้ปฏิบัติตามบทช่วยสอนนี้ได้อย่างไร

ตอบ: ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบรวม (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET ซึ่งจะทำให้คุณสามารถใช้คุณลักษณะของห้องสมุดในการค้นหาและทำงานกับเอกสาร PDF ได้

#### ถาม: ฉันสามารถใช้บทช่วยสอนนี้เพื่อค้นหาส่วนข้อความที่ต้องการในหน้าใดก็ได้ของ PDF ได้หรือไม่

ตอบ: ใช่ บทช่วยสอนนี้ให้คำแนะนำเกี่ยวกับวิธีการค้นหาส่วนข้อความเฉพาะบนหน้าที่เลือกของเอกสาร PDF โดยจะแนะนำผู้ใช้ในการตั้งค่าโปรเจ็กต์ การโหลด PDF และการใช้ไลบรารี Aspose.PDF เพื่อค้นหาและดึงคุณสมบัติของส่วนข้อความที่ต้องการ

#### ถาม: ฉันจะระบุข้อความที่ต้องการค้นหาในบทช่วยสอนนี้ได้อย่างไร

 ตอบ: หากต้องการระบุข้อความที่คุณต้องการค้นหา ให้สร้าง`TextFragmentAbsorber` object และตั้งค่าพารามิเตอร์การค้นหาโดยใช้`Text` คุณสมบัติ. แทนที่ค่าเริ่มต้น`"text"` ในโค้ดของบทช่วยสอนพร้อมวลีค้นหาที่คุณต้องการ

#### ถาม: ฉันจะดึงคุณสมบัติของส่วนข้อความที่แยกออกมาได้อย่างไร

หลังจากยอมรับ`TextFragmentAbsorber` สำหรับหน้าเฉพาะของ PDF คุณสามารถดึงส่วนข้อความที่แยกออกมาได้โดยใช้`TextFragments` คุณสมบัติของวัตถุดูดซับ ซึ่งจะทำให้สามารถเข้าถึงคอลเลกชันของส่วนของข้อความ ซึ่งแต่ละส่วนจะมีส่วนของข้อความหลายส่วน

#### ถาม: ฉันสามารถปรับแต่งโค้ดเพื่อดำเนินการเพิ่มเติมกับแต่ละส่วนของข้อความได้หรือไม่

ตอบ: อย่างแน่นอน โค้ดตัวอย่างของบทช่วยสอนจัดให้มีการวนซ้ำเพื่อวนซ้ำส่วนข้อความที่ดึงข้อมูล คุณสามารถปรับแต่งโค้ดภายในลูปนี้เพื่อดำเนินการเพิ่มเติมกับแต่ละส่วนของข้อความได้ตามความต้องการของโปรเจ็กต์ของคุณ

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่แก้ไขแล้วได้อย่างไรหลังจากแยกส่วนข้อความแล้ว

ตอบ: บทช่วยสอนนี้เน้นที่การค้นหาเซ็กเมนต์ข้อความและการดึงคุณสมบัติเป็นหลัก หากคุณต้องการแก้ไข PDF คุณสามารถดูเอกสารประกอบ Aspose.PDF อื่นๆ เพื่อเรียนรู้วิธีจัดการและบันทึกเอกสารตามความต้องการเฉพาะของคุณ