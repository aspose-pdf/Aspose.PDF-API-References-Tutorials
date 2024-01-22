---
title: ค้นหาและรับหน้าข้อความในไฟล์ PDF
linktitle: ค้นหาและรับหน้าข้อความในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีค้นหาและรับข้อความจากหน้าใดหน้าหนึ่งในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 430
url: /th/net/programming-with-text/search-and-get-text-page/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อค้นหาและรับข้อความจากหน้าใดหน้าหนึ่งเป็นไฟล์ PDF ซอร์สโค้ด C# ที่ให้มาสาธิตกระบวนการทีละขั้นตอน

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: ค้นหาและแยกข้อความจากหน้า

 สร้างก`TextFragmentAbsorber`วัตถุเพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีค้นหาที่ป้อนในหน้าใดหน้าหนึ่ง:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 แทนที่`"Figure"` ด้วยข้อความจริงที่คุณต้องการค้นหา

## ขั้นตอนที่ 5: ค้นหาในหน้าใดหน้าหนึ่ง

ยอมรับตัวดูดซับสำหรับหน้าเฉพาะของเอกสาร:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## ขั้นตอนที่ 6: รับส่วนของข้อความที่แยกออกมา

รับส่วนของข้อความที่แยกออกมาโดยใช้`TextFragments` ทรัพย์สินของ`TextFragmentAbsorber` วัตถุ:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ขั้นตอนที่ 7: วนซ้ำส่วนข้อความและเซ็กเมนต์

วนซ้ำส่วนข้อความที่ได้รับและเซ็กเมนต์ และเข้าถึงคุณสมบัติ:

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

คุณสามารถแก้ไขโค้ดภายในลูปเพื่อดำเนินการเพิ่มเติมกับแต่ละส่วนของข้อความได้

### ตัวอย่างซอร์สโค้ดสำหรับการค้นหาและรับหน้าข้อความโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// สร้างวัตถุ TextAbsorber เพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีค้นหาอินพุต
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// รับซับทุกหน้า
pdfDocument.Pages.Accept(textFragmentAbsorber);
// รับส่วนของข้อความที่แยกออกมา
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// วนผ่านชิ้นส่วน
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีการค้นหาและรับข้อความจากหน้าเฉพาะของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอน ตั้งแต่การโหลดเอกสารไปจนถึงการเข้าถึงส่วนข้อความที่แยกออกมา ตอนนี้คุณสามารถรวมเข้าด้วยกัน

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "ค้นหาและรับหน้าข้อความ" คืออะไร

ตอบ: บทช่วยสอน "ค้นหาและรับหน้าข้อความ" ได้รับการออกแบบมาเพื่อแสดงวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อค้นหาและดึงข้อความจากหน้าใดหน้าหนึ่งภายในไฟล์ PDF บทช่วยสอนให้คำแนะนำโดยละเอียดและโค้ด C# ตัวอย่างเพื่อสาธิตกระบวนการ

#### ถาม: บทช่วยสอนนี้ช่วยในการแยกข้อความจากหน้าใดหน้าหนึ่งในเอกสาร PDF ได้อย่างไร

ตอบ: บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการแยกข้อความจากหน้าใดหน้าหนึ่งของเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF โดยสรุปขั้นตอนที่จำเป็นและให้รหัส C# เพื่อค้นหาวลีข้อความที่ระบุบนหน้าที่เลือกและดึงส่วนข้อความที่เกี่ยวข้อง

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการติดตามบทช่วยสอนนี้มีอะไรบ้าง

ตอบ: ก่อนที่จะเริ่มบทช่วยสอนนี้ คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# นอกจากนี้ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET ด้วย คุณสามารถรับได้จากเว็บไซต์ Aspose หรือใช้ NuGet เพื่อรวมเข้ากับโปรเจ็กต์ของคุณ

#### ถาม: ฉันจะตั้งค่าโปรเจ็กต์ให้ปฏิบัติตามบทช่วยสอนนี้ได้อย่างไร

ตอบ: ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบรวม (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET สิ่งนี้จะช่วยให้คุณใช้ความสามารถของห้องสมุดในโครงการของคุณได้

#### ถาม: ฉันสามารถค้นหาข้อความในหน้าใดหน้าหนึ่งของเอกสาร PDF ได้หรือไม่

ตอบ: ใช่ บทช่วยสอนนี้สาธิตวิธีการค้นหาข้อความในหน้าเฉพาะของเอกสาร PDF มันเกี่ยวข้องกับการใช้`TextFragmentAbsorber` คลาสเพื่อค้นหาอินสแตนซ์ของวลีข้อความเฉพาะบนหน้าที่เลือก

#### ถาม: ฉันจะเข้าถึงส่วนข้อความที่แยกออกมาจากหน้าใดหน้าหนึ่งได้อย่างไร

 ตอบ: หลังจากค้นหาข้อความในหน้าที่กำหนดแล้ว คุณสามารถเข้าถึงส่วนของข้อความที่แยกออกมาได้โดยใช้`TextSegments` ทรัพย์สินของ`TextFragment` วัตถุ. สถานที่ให้บริการนี้ให้การเข้าถึงคอลเลกชันของ`TextSegment` วัตถุที่มีข้อความที่แยกออกมาและข้อมูลที่เกี่ยวข้อง

#### ถาม: ฉันสามารถดึงข้อมูลใดจากส่วนข้อความที่แยกออกมาได้

ตอบ: คุณสามารถดึงรายละเอียดต่างๆ จากส่วนของข้อความที่แยกออกมา รวมถึงเนื้อหาข้อความ ตำแหน่ง (พิกัด X และ Y) ข้อมูลแบบอักษร (ชื่อ ขนาด สี ฯลฯ) และอื่นๆ โค้ดตัวอย่างของบทช่วยสอนสาธิตวิธีการเข้าถึงและพิมพ์รายละเอียดเหล่านี้สำหรับส่วนของข้อความแต่ละส่วน

#### ถาม: ฉันสามารถดำเนินการแบบกำหนดเองกับส่วนข้อความที่แยกออกมาได้หรือไม่

ตอบ: แน่นอน เมื่อคุณมีส่วนของข้อความที่แยกออกมาแล้ว คุณสามารถปรับแต่งโค้ดภายในลูปเพื่อดำเนินการเพิ่มเติมในแต่ละส่วนได้ ซึ่งอาจรวมถึงการบันทึกข้อความที่แยกออกมา การวิเคราะห์รูปแบบข้อความ หรือใช้การเปลี่ยนแปลงการจัดรูปแบบ