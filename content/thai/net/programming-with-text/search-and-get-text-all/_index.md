---
title: ค้นหาและรับข้อความทั้งหมด
linktitle: ค้นหาและรับข้อความทั้งหมด
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีค้นหาและรับข้อความจากทุกหน้าของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 420
url: /th/net/programming-with-text/search-and-get-text-all/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อค้นหาและรับข้อความจากทุกหน้าของเอกสาร PDF โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนต่างๆ ของกระบวนการ

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: ค้นหาและแยกข้อความ

 สร้าง`TextFragmentAbsorber` วัตถุที่จะค้นหาอินสแตนซ์ทั้งหมดของวลีการค้นหาอินพุต:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 แทนที่`"text"` ด้วยข้อความจริงที่คุณต้องการค้นหา

## ขั้นตอนที่ 5: ค้นหาในทุกหน้า

รับตัวดูดซับสำหรับทุกหน้าของเอกสาร:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## ขั้นตอนที่ 6: แยกชิ้นส่วนข้อความที่แยกออกมา

 รับชิ้นส่วนข้อความที่แยกออกมาโดยใช้`TextFragments` ทรัพย์สินของ`TextFragmentAbsorber` วัตถุ:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## ขั้นตอนที่ 7: วนซ้ำผ่านชิ้นส่วนข้อความ

วนซ้ำผ่านชิ้นส่วนข้อความที่ได้รับและเข้าถึงคุณสมบัติของมัน:

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

### ตัวอย่างโค้ดต้นฉบับสำหรับการค้นหาและรับข้อความทั้งหมดโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// สร้างวัตถุ TextAbsorber เพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีการค้นหาอินพุต
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
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

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีค้นหาและรับข้อความจากทุกหน้าของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนตั้งแต่การโหลดเอกสารไปจนถึงการเข้าถึงส่วนข้อความที่แยกออกมา ตอนนี้คุณสามารถนำโค้ดนี้ไปใช้กับโปรเจ็กต์ C# ของคุณเองเพื่อวิเคราะห์และประมวลผลเนื้อหาข้อความในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "ค้นหาและรับข้อความทั้งหมด" คืออะไร

A: บทช่วยสอน "ค้นหาและรับข้อความทั้งหมด" สาธิตวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อค้นหาและดึงข้อความจากทุกหน้าของเอกสาร PDF บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ด C# เพื่อค้นหาและดึงข้อความ

#### ถาม: บทช่วยสอนนี้ช่วยในการแยกข้อความจากเอกสาร PDF ได้อย่างไร

A: บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการแยกข้อความจากทุกหน้าของเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF เพื่อค้นหาข้อความเฉพาะและดึงข้อมูลที่เกี่ยวข้อง เช่น ตำแหน่ง คุณสมบัติของแบบอักษร และสี

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการปฏิบัติตามบทช่วยสอนนี้คืออะไร

A: ก่อนเริ่มบทช่วยสอนนี้ คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# นอกจากนี้ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET คุณสามารถรับได้จากเว็บไซต์ Aspose หรือใช้ NuGet เพื่อรวมเข้ากับโครงการของคุณ

#### ถาม: ฉันจะตั้งค่าโครงการเพื่อทำตามบทช่วยสอนนี้ได้อย่างไร

A: ในการเริ่มต้น ให้สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET ซึ่งจะช่วยให้คุณสามารถเข้าถึงฟังก์ชันการทำงานของไลบรารีในโครงการของคุณได้

#### ถาม: ฉันจะค้นหาข้อความเฉพาะภายในเอกสาร PDF ได้อย่างไร

 A: คุณสามารถใช้`TextFragmentAbsorber`คลาสนี้ใช้ค้นหาอินสแตนซ์ของวลีการค้นหาเฉพาะภายในเอกสาร PDF โดยการสร้างอินสแตนซ์ของคลาสนี้และระบุข้อความเป้าหมาย คุณสามารถบันทึกการเกิดขึ้นทั้งหมดของข้อความนั้นได้

#### ถาม: ฉันสามารถค้นหาข้อความในทุกหน้าของเอกสาร PDF ได้หรือไม่

 A: ใช่ บทช่วยสอนนี้สาธิตวิธีการค้นหาข้อความในทุกหน้าของเอกสาร PDF`pdfDocument.Pages.Accept(textFragmentAbsorber)` วิธีนี้ใช้ในการยอมรับตัวดูดซับสำหรับทุกหน้า ช่วยให้คุณค้นหาข้อความที่ต้องการในทุกๆ หน้าได้

#### ถาม: ฉันจะเข้าถึงชิ้นส่วนข้อความที่แยกออกมาได้อย่างไร

 A: หลังจากค้นหาข้อความแล้ว คุณสามารถเข้าถึงชิ้นส่วนข้อความที่แยกออกมาได้โดยใช้`TextFragments` ทรัพย์สินของ`TextFragmentAbsorber` วัตถุ คุณสมบัตินี้ให้การเข้าถึงคอลเลกชันของ`TextFragment` วัตถุที่ประกอบด้วยข้อความที่แยกออกมาและข้อมูลที่เกี่ยวข้อง

#### ถาม: ฉันสามารถดึงข้อมูลอะไรจากชิ้นส่วนข้อความที่แยกออกมาได้บ้าง

A: คุณสามารถดึงรายละเอียดต่างๆ จากชิ้นส่วนข้อความที่แยกออกมาได้ เช่น เนื้อหาข้อความจริง ตำแหน่ง (พิกัด X และ Y) ข้อมูลแบบอักษร (ชื่อ ขนาด สี เป็นต้น) และอื่นๆ อีกมากมาย โค้ดตัวอย่างของบทช่วยสอนจะสาธิตวิธีการเข้าถึงและพิมพ์รายละเอียดเหล่านี้

#### ถาม: ฉันสามารถดำเนินการเพิ่มเติมกับชิ้นส่วนข้อความที่แยกออกมาได้หรือไม่

A: แน่นอน เมื่อคุณแยกข้อความออกมาแล้ว คุณสามารถแก้ไขโค้ดภายในลูปเพื่อดำเนินการที่กำหนดเองกับแต่ละข้อความได้ ซึ่งอาจรวมถึงการบันทึกข้อความที่แยกออกมา การวิเคราะห์รูปแบบข้อความ หรือการใช้การเปลี่ยนแปลงการจัดรูปแบบ