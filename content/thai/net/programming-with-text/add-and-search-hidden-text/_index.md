---
title: เพิ่มและค้นหาข้อความที่ซ่อนอยู่ในไฟล์ PDF
linktitle: เพิ่มและค้นหาข้อความที่ซ่อนอยู่ในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการเพิ่มและค้นหาข้อความที่ซ่อนอยู่ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 20
url: /th/net/programming-with-text/add-and-search-hidden-text/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการเพิ่มและค้นหาข้อความที่ซ่อนอยู่ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ทำตามขั้นตอนเหล่านี้เพื่อดำเนินการนี้อย่างง่ายดาย

## 1. ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือสภาพแวดล้อมการพัฒนาอื่น ๆ ที่ติดตั้งและกำหนดค่า
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose

## 2. การสร้างเอกสาร PDF พร้อมข้อความที่ซ่อนอยู่

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

ต่อไป เราจะค้นหาข้อความที่ซ่อนอยู่ในเอกสาร PDF ใช้รหัสต่อไปนี้:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//ทำอะไรสักอย่างกับเศษชิ้นส่วน
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

วิธีนี้จะค้นหาข้อความที่ซ่อนอยู่ในหน้าสองของเอกสาร PDF และแสดงข้อมูลที่เกี่ยวข้อง

### ตัวอย่างซอร์สโค้ดสำหรับการเพิ่มและค้นหาข้อความที่ซ่อนโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
//สร้างเอกสารพร้อมข้อความที่ซ่อนอยู่
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
	//ทำอะไรสักอย่างด้วยเศษชิ้นส่วน
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## บทสรุป

ขอแสดงความยินดี! คุณได้เพิ่มและพบข้อความที่ซ่อนอยู่ในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว ตอนนี้คุณสามารถใช้วิธีนี้กับโปรเจ็กต์ของคุณเองเพื่อจัดการและค้นหาข้อความที่ซ่อนอยู่ในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงเอกสาร PDF ภายในแอปพลิเคชัน .NET

#### ถาม: ข้อความที่ซ่อนสามารถใช้เพื่อลายน้ำได้หรือไม่

ตอบ: แน่นอน! ข้อความที่ซ่อนไว้สามารถใช้เป็นวิธีการใส่ลายน้ำให้กับเอกสาร PDF ได้อย่างมีประสิทธิภาพ โดยเพิ่มระดับความปลอดภัยเพิ่มเติม

#### ถาม: เป็นไปได้หรือไม่ที่จะเปิดเผยข้อความที่ซ่อนอยู่ในเอกสาร PDF

ตอบ: ได้ กระบวนการค้นหาและเปิดเผยข้อความที่ซ่อนอยู่ในเอกสาร PDF สามารถทำได้โดยใช้เทคนิคที่อธิบายไว้ในบทช่วยสอนนี้

#### ถาม: Aspose.PDF สำหรับ .NET มีฟังก์ชันอื่นๆ อะไรบ้าง

ตอบ: นอกเหนือจากการจัดการข้อความที่ซ่อนอยู่แล้ว Aspose.PDF สำหรับ .NET ยังมีคุณสมบัติมากมาย รวมถึงการสร้าง PDF การแปลง การเข้ารหัส และอื่นๆ อีกมากมาย