---
title: ค้นหาและรับข้อความทั้งหมด
linktitle: ค้นหาและรับข้อความทั้งหมด
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีค้นหาและรับข้อความจากทุกหน้าของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 420
url: /th/net/programming-with-text/search-and-get-text-all/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อค้นหาและรับข้อความจากทุกหน้าของเอกสาร PDF ซอร์สโค้ด C# ที่ให้มาสาธิตกระบวนการทีละขั้นตอน

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: ค้นหาและแยกข้อความ

 สร้างก`TextFragmentAbsorber` วัตถุเพื่อค้นหาทุกกรณีของวลีค้นหาอินพุต:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 แทนที่`"text"` ด้วยข้อความจริงที่คุณต้องการค้นหา

## ขั้นตอนที่ 5: ค้นหาในทุกหน้า

ยอมรับตัวดูดซับสำหรับทุกหน้าของเอกสาร:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## ขั้นตอนที่ 6: รับส่วนของข้อความที่แยกออกมา

รับส่วนของข้อความที่แยกออกมาโดยใช้`TextFragments` ทรัพย์สินของ`TextFragmentAbsorber` วัตถุ:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ขั้นตอนที่ 7: วนซ้ำส่วนข้อความ

วนซ้ำส่วนข้อความที่ได้รับและเข้าถึงคุณสมบัติ:

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

### ตัวอย่างซอร์สโค้ดสำหรับการค้นหาและรับข้อความทั้งหมดโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// สร้างวัตถุ TextAbsorber เพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีค้นหาอินพุต
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
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

ยินดีด้วย! คุณได้เรียนรู้วิธีการค้นหาและรับข้อความจากทุกหน้าของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET แล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอน ตั้งแต่การโหลดเอกสารไปจนถึงการเข้าถึงส่วนย่อยของข้อความที่แยกออกมา ตอนนี้คุณสามารถรวมโค้ดนี้เข้ากับโปรเจ็กต์ C# ของคุณเองเพื่อวิเคราะห์และประมวลผลเนื้อหาข้อความในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "ค้นหาและรับข้อความทั้งหมด" คืออะไร

ตอบ: บทช่วยสอน "ค้นหาและรับข้อความทั้งหมด" สาธิตวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อค้นหาและแยกข้อความจากทุกหน้าของเอกสาร PDF บทช่วยสอนนี้จะให้คำแนะนำทีละขั้นตอนพร้อมกับตัวอย่างโค้ด C# เพื่อทำการค้นหาและเรียกค้นข้อความ

#### ถาม: บทช่วยสอนนี้ช่วยในการแยกข้อความจากเอกสาร PDF อย่างไร

ตอบ: บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการแยกข้อความจากทุกหน้าของเอกสาร PDF โดยจะใช้ไลบรารี Aspose.PDF เพื่อค้นหาวลีข้อความเฉพาะและดึงข้อมูลที่เกี่ยวข้อง เช่น ตำแหน่ง คุณสมบัติแบบอักษร และสี

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการติดตามบทช่วยสอนนี้มีอะไรบ้าง

ตอบ: ก่อนที่จะเริ่มบทช่วยสอนนี้ คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# นอกจากนี้ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET ด้วย คุณสามารถรับได้จากเว็บไซต์ Aspose หรือใช้ NuGet เพื่อรวมเข้ากับโปรเจ็กต์ของคุณ

#### ถาม: ฉันจะตั้งค่าโปรเจ็กต์ให้ปฏิบัติตามบทช่วยสอนนี้ได้อย่างไร

ตอบ: ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบรวม (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET สิ่งนี้จะทำให้คุณสามารถเข้าถึงฟังก์ชันการทำงานของห้องสมุดในโครงการของคุณได้

#### ถาม: ฉันจะค้นหาข้อความเฉพาะภายในเอกสาร PDF ได้อย่างไร

ตอบ: คุณสามารถใช้`TextFragmentAbsorber`คลาสเพื่อค้นหาอินสแตนซ์ของวลีค้นหาเฉพาะภายในเอกสาร PDF ด้วยการสร้างอินสแตนซ์ของคลาสนี้และระบุข้อความเป้าหมาย คุณสามารถบันทึกเหตุการณ์ทั้งหมดของข้อความนั้นได้

#### ถาม: ฉันสามารถค้นหาข้อความในทุกหน้าของเอกสาร PDF ได้หรือไม่

 ตอบ: ใช่ บทช่วยสอนสาธิตวิธีค้นหาข้อความในทุกหน้าของเอกสาร PDF ที่`pdfDocument.Pages.Accept(textFragmentAbsorber)` จะใช้วิธีรับหน้าดูดซับทุกหน้าทำให้สามารถค้นหาข้อความที่ต้องการได้ในทุกหน้า

#### ถาม: ฉันจะเข้าถึงส่วนย่อยของข้อความที่แยกออกมาได้อย่างไร

 ตอบ: หลังจากค้นหาข้อความแล้ว คุณสามารถเข้าถึงส่วนข้อความที่แยกออกมาได้โดยใช้`TextFragments` ทรัพย์สินของ`TextFragmentAbsorber` วัตถุ. สถานที่ให้บริการนี้ให้การเข้าถึงคอลเลกชันของ`TextFragment` วัตถุที่มีข้อความที่แยกออกมาและข้อมูลที่เกี่ยวข้อง

#### ถาม: ฉันสามารถดึงข้อมูลใดจากส่วนย่อยของข้อความที่แยกออกมาได้

ตอบ: คุณสามารถดึงรายละเอียดต่างๆ จากส่วนของข้อความที่แยกออกมา เช่น เนื้อหาข้อความจริง ตำแหน่ง (พิกัด X และ Y) ข้อมูลแบบอักษร (ชื่อ ขนาด สี ฯลฯ) และอื่นๆ โค้ดตัวอย่างของบทช่วยสอนสาธิตวิธีการเข้าถึงและพิมพ์รายละเอียดเหล่านี้

#### ถาม: ฉันสามารถดำเนินการเพิ่มเติมกับส่วนของข้อความที่แยกออกมาได้หรือไม่

ตอบ: อย่างแน่นอน เมื่อคุณมีส่วนของข้อความที่แยกออกมาแล้ว คุณสามารถแก้ไขโค้ดภายในลูปเพื่อดำเนินการแบบกำหนดเองกับแต่ละส่วนได้ ซึ่งอาจรวมถึงการบันทึกข้อความที่แยกออกมา การวิเคราะห์รูปแบบข้อความ หรือใช้การเปลี่ยนแปลงการจัดรูปแบบ