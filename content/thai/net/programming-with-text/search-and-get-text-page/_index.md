---
title: ค้นหาและรับหน้าข้อความในไฟล์ PDF
linktitle: ค้นหาและรับหน้าข้อความในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีค้นหาและรับข้อความจากหน้าเฉพาะในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 430
url: /th/net/programming-with-text/search-and-get-text-page/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อค้นหาและรับข้อความจากหน้าที่ระบุในไฟล์ PDF โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนต่างๆ ของกระบวนการนี้ทีละขั้นตอน

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: ค้นหาและดึงข้อความจากหน้า

 สร้าง`TextFragmentAbsorber`วัตถุในการค้นหาอินสแตนซ์ทั้งหมดของวลีการค้นหาอินพุตบนหน้าเฉพาะ:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 แทนที่`"Figure"` ด้วยข้อความจริงที่คุณต้องการค้นหา

## ขั้นตอนที่ 5: ค้นหาในหน้าเฉพาะ

ยอมรับตัวดูดซับสำหรับหน้าเฉพาะของเอกสาร:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## ขั้นตอนที่ 6: แยกชิ้นส่วนข้อความที่แยกออกมา

 รับชิ้นส่วนข้อความที่แยกออกมาโดยใช้`TextFragments` ทรัพย์สินของ`TextFragmentAbsorber` วัตถุ:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ขั้นตอนที่ 7: วนซ้ำผ่านชิ้นส่วนและส่วนต่างๆ ของข้อความ

วนซ้ำผ่านชิ้นส่วนข้อความที่ได้รับและส่วนต่างๆ ของมัน และเข้าถึงคุณสมบัติของมัน:

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

คุณสามารถปรับเปลี่ยนโค้ดภายในลูปเพื่อดำเนินการเพิ่มเติมกับข้อความแต่ละส่วนได้

### ตัวอย่างโค้ดต้นฉบับสำหรับการค้นหาและรับหน้าข้อความโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// สร้างวัตถุ TextAbsorber เพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีการค้นหาอินพุต
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// รับตัวดูดซับสำหรับทุกหน้า
pdfDocument.Pages.Accept(textFragmentAbsorber);
// รับชิ้นส่วนข้อความที่แยกออกมา
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

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีค้นหาและรับข้อความจากหน้าเฉพาะของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนตั้งแต่การโหลดเอกสารจนถึงการเข้าถึงส่วนข้อความที่แยกออกมา ตอนนี้คุณสามารถรวมไฟล์ PDF ได้แล้ว

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "ค้นหาและรับหน้าข้อความ" คืออะไร

A: บทช่วยสอน "Search And Get Text Page" ออกแบบมาเพื่อแสดงวิธีการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อค้นหาและดึงข้อความจากหน้าเฉพาะภายในไฟล์ PDF บทช่วยสอนมีคำแนะนำโดยละเอียดและตัวอย่างโค้ด C# เพื่อสาธิตกระบวนการ

#### ถาม: บทช่วยสอนนี้ช่วยในการแยกข้อความจากหน้าเฉพาะในเอกสาร PDF ได้อย่างไร

A: บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการแยกข้อความจากหน้าใดหน้าหนึ่งของเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF โดยจะอธิบายขั้นตอนที่จำเป็นและแสดงโค้ด C# เพื่อค้นหาข้อความที่ระบุในหน้าที่เลือกและดึงส่วนข้อความที่เกี่ยวข้อง

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการปฏิบัติตามบทช่วยสอนนี้คืออะไร

A: ก่อนเริ่มบทช่วยสอนนี้ คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# นอกจากนี้ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET คุณสามารถรับได้จากเว็บไซต์ Aspose หรือใช้ NuGet เพื่อรวมเข้ากับโครงการของคุณ

#### ถาม: ฉันจะตั้งค่าโครงการเพื่อทำตามบทช่วยสอนนี้ได้อย่างไร

A: ในการเริ่มต้น ให้สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET วิธีนี้จะช่วยให้คุณใช้ความสามารถของไลบรารีในโครงการของคุณได้

#### ถาม: ฉันสามารถค้นหาข้อความบนหน้าเฉพาะของเอกสาร PDF ได้หรือไม่

A: ใช่ บทช่วยสอนนี้สาธิตวิธีค้นหาข้อความในหน้าเฉพาะของเอกสาร PDF ซึ่งเกี่ยวข้องกับการใช้`TextFragmentAbsorber` คลาสเพื่อค้นหาตัวอย่างของวลีข้อความเฉพาะในหน้าที่เลือก

#### ถาม: ฉันจะเข้าถึงส่วนข้อความที่แยกออกมาจากหน้าที่ระบุได้อย่างไร

 ก: หลังจากค้นหาข้อความในหน้าที่กำหนดแล้ว คุณสามารถเข้าถึงส่วนข้อความที่แยกออกมาได้โดยใช้`TextSegments` ทรัพย์สินของ`TextFragment` วัตถุ คุณสมบัตินี้ให้การเข้าถึงคอลเลกชันของ`TextSegment` วัตถุที่ประกอบด้วยข้อความที่แยกออกมาและข้อมูลที่เกี่ยวข้อง

#### ถาม: ฉันสามารถดึงข้อมูลอะไรจากกลุ่มข้อความที่แยกออกมาได้บ้าง

A: คุณสามารถดึงรายละเอียดต่างๆ จากส่วนข้อความที่แยกออกมาได้ เช่น เนื้อหาข้อความ ตำแหน่ง (พิกัด X และ Y) ข้อมูลแบบอักษร (ชื่อ ขนาด สี เป็นต้น) และอื่นๆ อีกมากมาย โค้ดตัวอย่างของบทช่วยสอนจะสาธิตวิธีการเข้าถึงและพิมพ์รายละเอียดเหล่านี้สำหรับแต่ละส่วนข้อความ

#### ถาม: ฉันสามารถดำเนินการแบบกำหนดเองกับกลุ่มข้อความที่แยกออกมาได้หรือไม่

A: แน่นอน เมื่อคุณแยกส่วนข้อความที่ได้แล้ว คุณสามารถปรับแต่งโค้ดภายในลูปเพื่อดำเนินการเพิ่มเติมกับแต่ละส่วนได้ ซึ่งอาจรวมถึงการบันทึกข้อความที่แยกออกมา การวิเคราะห์รูปแบบข้อความ หรือการใช้การเปลี่ยนแปลงการจัดรูปแบบ