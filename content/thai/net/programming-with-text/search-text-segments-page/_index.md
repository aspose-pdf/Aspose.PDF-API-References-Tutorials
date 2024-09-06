---
title: ค้นหาหน้าส่วนข้อความในไฟล์ PDF
linktitle: ค้นหาหน้าส่วนข้อความในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีค้นหากลุ่มข้อความบนหน้าในไฟล์ PDF และดึงคุณสมบัติเหล่านั้นโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 470
url: /th/net/programming-with-text/search-text-segments-page/
---
บทช่วยสอนนี้จะอธิบายวิธีการใช้ Aspose.PDF สำหรับ .NET เพื่อค้นหากลุ่มข้อความเฉพาะในหน้าไฟล์ PDF และเรียกค้นคุณสมบัติของกลุ่มข้อความเหล่านั้น โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนต่างๆ ของกระบวนการนี้ทีละขั้นตอน

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

## ขั้นตอนที่ 4: โหลดเอกสาร PDF

 โหลดเอกสาร PDF โดยใช้`Document` ระดับ:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 แทนที่`"SearchTextSegmentsPage.pdf"` ด้วยชื่อจริงของไฟล์ PDF ของคุณ

## ขั้นตอนที่ 5: สร้าง TextFragmentAbsorber

 สร้าง`TextFragmentAbsorber` วัตถุที่จะค้นหาอินสแตนซ์ทั้งหมดของวลีการค้นหาอินพุต:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 แทนที่`"text"` พร้อมคำค้นที่คุณต้องการ

## ขั้นตอนที่ 6: ยอมรับตัวดูดซับสำหรับหน้าเฉพาะ

ยอมรับตัวดูดซับสำหรับหน้าที่ต้องการของเอกสาร:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 แทนที่`2` พร้อมระบุหมายเลขหน้าที่ต้องการ (ดัชนีแบบ 1)

## ขั้นตอนที่ 7: ดึงข้อมูลส่วนที่แยกออกมา

 รับส่วนข้อความที่แยกออกมาโดยใช้`TextFragments` ทรัพย์สินของ`TextFragmentAbsorber` วัตถุ:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ขั้นตอนที่ 8: วนซ้ำผ่านส่วนของข้อความ

วนซ้ำผ่านกลุ่มข้อความที่เรียกค้นและเข้าถึงคุณสมบัติของกลุ่มข้อความเหล่านั้น:

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

แก้ไขโค้ดภายในลูปเพื่อดำเนินการเพิ่มเติมกับส่วนข้อความแต่ละส่วนหากจำเป็น

### ตัวอย่างโค้ดต้นฉบับสำหรับหน้า Search Text Segments โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// สร้างวัตถุ TextAbsorber เพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีการค้นหาอินพุต
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// รับตัวดูดซับสำหรับทุกหน้า
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// รับชิ้นส่วนข้อความที่แยกออกมา
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

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีค้นหาข้อความส่วนต่างๆ บนหน้าเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนตั้งแต่การโหลดเอกสารไปจนถึงการเข้าถึงข้อความส่วนต่างๆ ที่แยกออกมา ตอนนี้คุณสามารถนำโค้ดนี้ไปใช้กับโปรเจ็กต์ C# ของคุณเองเพื่อค้นหาข้อความส่วนต่างๆ ขั้นสูงในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "ค้นหาหน้าส่วนข้อความในไฟล์ PDF" คืออะไร

A: บทช่วยสอน "ค้นหาหน้ากลุ่มข้อความในไฟล์ PDF" ให้คำแนะนำที่ครอบคลุมเกี่ยวกับวิธีการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อค้นหากลุ่มข้อความเฉพาะในหน้าใดหน้าหนึ่งของเอกสาร PDF บทช่วยสอนนี้ครอบคลุมถึงขั้นตอนการตั้งค่าโครงการ การโหลดเอกสาร PDF การค้นหากลุ่มข้อความ และการดึงคุณสมบัติของกลุ่มข้อความโดยใช้โค้ด C#

#### ถาม: บทช่วยสอนนี้ช่วยในการค้นหาส่วนข้อความที่เจาะจงในเอกสาร PDF ได้อย่างไร

A: บทช่วยสอนนี้สาธิตขั้นตอนการค้นหาและแยกส่วนข้อความที่ต้องการบนหน้าใดหน้าหนึ่งของเอกสาร PDF โดยทำตามขั้นตอนและตัวอย่างโค้ดที่ให้ไว้ ผู้ใช้สามารถค้นหาส่วนข้อความที่ต้องการและดึงข้อมูลเกี่ยวกับคุณสมบัติของส่วนข้อความได้อย่างมีประสิทธิภาพ

#### ถาม: มีข้อกำหนดเบื้องต้นอะไรบ้างที่ต้องปฏิบัติตามบทช่วยสอนนี้?

A: ก่อนเริ่มบทช่วยสอน คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# นอกจากนี้ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET คุณสามารถรับได้จากเว็บไซต์ Aspose หรือติดตั้งในโปรเจ็กต์ของคุณโดยใช้ NuGet

#### ถาม: ฉันจะตั้งค่าโครงการเพื่อทำตามบทช่วยสอนนี้ได้อย่างไร

A: ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET วิธีนี้จะช่วยให้คุณใช้คุณลักษณะของไลบรารีในการค้นหาและทำงานกับเอกสาร PDF ได้

#### ถาม: ฉันสามารถใช้บทช่วยสอนนี้เพื่อค้นหาส่วนข้อความที่เจาะจงบนทุกหน้าของ PDF ได้หรือไม่

A: ใช่ บทช่วยสอนนี้ให้คำแนะนำเกี่ยวกับวิธีการค้นหาข้อความบางส่วนในหน้าที่เลือกของเอกสาร PDF โดยจะแนะนำผู้ใช้เกี่ยวกับการตั้งค่าโครงการ การโหลด PDF และการใช้ไลบรารี Aspose.PDF เพื่อค้นหาและดึงคุณสมบัติของข้อความบางส่วนที่ต้องการ

#### ถาม: ฉันจะระบุข้อความที่ฉันต้องการค้นหาในบทช่วยสอนนี้ได้อย่างไร

 ก: เพื่อระบุข้อความที่คุณต้องการค้นหา ให้สร้าง`TextFragmentAbsorber` วัตถุและตั้งค่าพารามิเตอร์การค้นหาโดยใช้`Text` คุณสมบัติ. แทนที่ค่าเริ่มต้น`"text"` ในโค้ดของบทช่วยสอนพร้อมวลีการค้นหาที่คุณต้องการ

#### ถาม: ฉันจะดึงคุณสมบัติของส่วนที่แยกออกมาได้อย่างไร

หลังจากยอมรับ`TextFragmentAbsorber` สำหรับหน้าเฉพาะของ PDF คุณสามารถดึงส่วนข้อความที่แยกออกมาได้โดยใช้`TextFragments` คุณสมบัติของวัตถุตัวดูดซับ ซึ่งให้การเข้าถึงคอลเล็กชั่นของข้อความย่อย ซึ่งแต่ละส่วนประกอบด้วยข้อความย่อยหลายส่วน

#### ถาม: ฉันสามารถปรับแต่งโค้ดเพื่อดำเนินการเพิ่มเติมในแต่ละส่วนของข้อความได้หรือไม่

A: แน่นอน โค้ดตัวอย่างของบทช่วยสอนมีลูปสำหรับวนซ้ำผ่านข้อความส่วนที่ดึงออกมา คุณสามารถปรับแต่งโค้ดภายในลูปนี้เพื่อดำเนินการเพิ่มเติมกับข้อความแต่ละส่วนได้ตามความต้องการของโครงการของคุณ

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่แก้ไขแล้วหลังจากการแยกส่วนข้อความออกได้อย่างไร

A: บทช่วยสอนนี้มุ่งเน้นไปที่การค้นหาเซกเมนต์ข้อความและการดึงคุณสมบัติของเซกเมนต์เหล่านั้นเป็นหลัก หากคุณต้องการปรับเปลี่ยน PDF คุณสามารถดูเอกสาร Aspose.PDF อื่นๆ เพื่อเรียนรู้วิธีการจัดการและบันทึกเอกสารตามความต้องการเฉพาะของคุณ