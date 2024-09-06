---
title: เพิ่มและค้นหาข้อความที่ซ่อนอยู่ในไฟล์ PDF
linktitle: เพิ่มและค้นหาข้อความที่ซ่อนอยู่ในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: คู่มือทีละขั้นตอนในการเพิ่มและค้นหาข้อความที่ซ่อนอยู่ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 20
url: /th/net/programming-with-text/add-and-search-hidden-text/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับการเพิ่มและค้นหาข้อความที่ซ่อนอยู่ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ปฏิบัติตามขั้นตอนเหล่านี้เพื่อดำเนินการนี้ได้อย่างง่ายดาย

## 1. ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งและกำหนดค่า Visual Studio หรือสภาพแวดล้อมการพัฒนาอื่น ๆ
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose

## 2. การสร้างเอกสาร PDF ที่มีข้อความที่ซ่อนอยู่

ในการเริ่มต้น ให้ใช้โค้ดต่อไปนี้เพื่อสร้างเอกสาร PDF ใหม่ที่มีข้อความที่ซ่อนอยู่:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// สร้างเอกสาร
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// ตั้งค่าคุณสมบัติข้อความ - มองไม่เห็น
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ต้องการสำหรับเอกสาร PDF

## 3. ค้นหาข้อความในเอกสาร

ต่อไปเราจะค้นหาข้อความที่ซ่อนอยู่ในเอกสาร PDF โดยใช้โค้ดต่อไปนี้:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//ทำบางอย่างกับชิ้นส่วนเหล่านี้
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

นี่จะค้นหาข้อความที่ซ่อนอยู่ในหน้าที่สองของเอกสาร PDF และแสดงข้อมูลที่เกี่ยวข้อง

### ตัวอย่างโค้ดต้นฉบับสำหรับการเพิ่มและค้นหาข้อความที่ซ่อนไว้โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
//สร้างเอกสารที่มีข้อความที่ซ่อนอยู่
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//ตั้งค่าคุณสมบัติข้อความ - มองไม่เห็น
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//ค้นหาข้อความในเอกสาร
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//ทำบางอย่างกับชิ้นส่วน
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## บทสรุป

ขอแสดงความยินดี! คุณได้เพิ่มและค้นหาข้อความที่ซ่อนอยู่ในเอกสาร PDF สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้เมธอดนี้กับโปรเจ็กต์ของคุณเองเพื่อจัดการและค้นหาข้อความที่ซ่อนอยู่ในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร?

A: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่แข็งแกร่งที่ช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงเอกสาร PDF ภายในแอปพลิเคชัน .NET ได้

#### ถาม: ข้อความที่ซ่อนไว้สามารถใช้เพื่อการใส่ลายน้ำได้หรือไม่

A: แน่นอน! ข้อความที่ซ่อนไว้สามารถใช้เป็นวิธีใส่ลายน้ำในเอกสาร PDF ได้อย่างมีประสิทธิภาพ ซึ่งช่วยเพิ่มระดับความปลอดภัยอีกชั้นหนึ่ง

#### ถาม: สามารถเปิดเผยข้อความที่ซ่อนอยู่ในเอกสาร PDF ได้หรือไม่

ตอบ: ใช่ การค้นหาและเปิดเผยข้อความที่ซ่อนอยู่ภายในเอกสาร PDF สามารถทำได้โดยใช้เทคนิคที่ระบุไว้ในบทช่วยสอนนี้

#### ถาม: Aspose.PDF สำหรับ .NET มีฟังก์ชันอื่นๆ อะไรอีกบ้าง

A: นอกเหนือจากการจัดการข้อความที่ซ่อนไว้แล้ว Aspose.PDF สำหรับ .NET ยังมีฟีเจอร์ต่างๆ มากมาย เช่น การสร้าง PDF การแปลง การเข้ารหัส และอื่นๆ อีกมากมาย