---
title: ระบุระยะห่างบรรทัดในไฟล์ PDF
linktitle: ระบุระยะห่างบรรทัดในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีระบุระยะห่างบรรทัดในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 510
url: /th/net/programming-with-text/specify-line-spacing/
---
บทช่วยสอนนี้จะอธิบายวิธีระบุระยะห่างบรรทัดในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาสาธิตกระบวนการทีละขั้นตอน

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
using System.IO;
```

## ขั้นตอนที่ 3: กำหนดเส้นทางไปยังไดเร็กทอรีเอกสาร

 กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณโดยใช้ไฟล์`dataDir` ตัวแปร:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: โหลดไฟล์ PDF อินพุต

 โหลดไฟล์ PDF อินพุตโดยใช้ไฟล์`Document` ระดับ:

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 5: สร้าง TextFormattingOptions

 สร้างก`TextFormattingOptions` object และตั้งค่าโหมดระยะห่างระหว่างบรรทัดเป็น`FullSize`: :

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## ขั้นตอนที่ 6: สร้าง TextFragment

 สร้างก`TextFragment` วัตถุและระบุเนื้อหาข้อความ:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## ขั้นตอนที่ 7: โหลดไฟล์ฟอนต์ (ไม่บังคับ)

 หากคุณต้องการใช้แบบอักษรเฉพาะสำหรับข้อความ ให้โหลดไฟล์แบบอักษร TrueType ลงในไฟล์`FileStream` วัตถุ:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 แทนที่`"HPSimplified.TTF"` ด้วยชื่อไฟล์ฟอนต์จริง

## ขั้นตอนที่ 8: ระบุตำแหน่งข้อความและระยะห่างระหว่างบรรทัด

 กำหนดตำแหน่งสำหรับส่วนของข้อความและกำหนด`TextFormattingOptions` ไปที่`TextState.FormattingOptions` คุณสมบัติ:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## ขั้นตอนที่ 9: เพิ่มข้อความลงในเอกสาร

 เพิ่มส่วนของข้อความลงในเอกสาร โดยผนวกเข้ากับ a`TextBuilder` หรือโดยตรงไปยังเพจ`Paragraphs` ของสะสม:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## ขั้นตอนที่ 10: บันทึกเอกสาร PDF ที่เป็นผลลัพธ์

บันทึกเอกสาร PDF ที่แก้ไข:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"SpecifyLineSpacing_out.pdf"` ด้วยชื่อไฟล์เอาต์พุตที่ต้องการ

### ตัวอย่างซอร์สโค้ดสำหรับระบุระยะห่างบรรทัดโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// โหลดไฟล์ PDF อินพุต
Document doc = new Document();
//สร้าง TextFormattingOptions ด้วย LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// สร้างวัตถุตัวสร้างข้อความสำหรับหน้าแรกของเอกสาร
//TextBuilder textBuilder = TextBuilder ใหม่ (doc.Pages[1]);
// สร้างส่วนของข้อความด้วยสตริงตัวอย่าง
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// โหลดแบบอักษร TrueType ลงในวัตถุสตรีม
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		//ตั้งชื่อแบบอักษรสำหรับสตริงข้อความ
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// ระบุตำแหน่งสำหรับ Text Fragment
		textFragment.Position = new Position(100, 600);
		//ตั้งค่า TextFormattingOptions ของแฟรกเมนต์ปัจจุบันเป็นที่กำหนดไว้ล่วงหน้า (ซึ่งชี้ไปที่ LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// เพิ่มข้อความลงใน TextBuilder เพื่อให้สามารถวางทับไฟล์ PDF ได้
		//textBuilder.AppendText (textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// บันทึกเอกสาร PDF ที่ได้
	doc.Save(dataDir);
}
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีระบุระยะห่างบรรทัดในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอน ตั้งแต่การตั้งค่าโปรเจ็กต์ไปจนถึงการบันทึกเอกสารที่แก้ไข ตอนนี้คุณสามารถรวมโค้ดนี้เข้ากับโปรเจ็กต์ C# ของคุณเองเพื่อปรับแต่งระยะห่างระหว่างบรรทัดของข้อความในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "ระบุระยะห่างบรรทัดในไฟล์ PDF" คืออะไร

ตอบ: บทช่วยสอน "ระบุระยะห่างบรรทัดในไฟล์ PDF" มีวัตถุประสงค์เพื่อแนะนำผู้ใช้เกี่ยวกับวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อปรับแต่งระยะห่างบรรทัดของข้อความภายในเอกสาร PDF บทช่วยสอนให้คำแนะนำทีละขั้นตอนและตัวอย่างโค้ด C# เพื่อสาธิตกระบวนการ

#### ถาม: บทช่วยสอนนี้ช่วยในการระบุระยะห่างบรรทัดภายในเอกสาร PDF อย่างไร

ตอบ: บทช่วยสอนนี้ช่วยให้ผู้ใช้เข้าใจวิธีใช้ความสามารถของ Aspose.PDF สำหรับ .NET เพื่อระบุระยะห่างบรรทัดสำหรับข้อความในเอกสาร PDF โดยทำตามขั้นตอนและตัวอย่างโค้ดที่ให้มา ผู้ใช้สามารถปรับระยะห่างระหว่างบรรทัดตามความต้องการได้

#### ถาม: ข้อกำหนดเบื้องต้นใดบ้างที่จำเป็นในการปฏิบัติตามบทช่วยสอนนี้

ตอบ: ก่อนที่จะเริ่มบทช่วยสอน คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# นอกจากนี้ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET ด้วย คุณสามารถรับได้จากเว็บไซต์ Aspose หรือติดตั้งในโครงการของคุณโดยใช้ NuGet

#### ถาม: ฉันจะตั้งค่าโปรเจ็กต์ให้ปฏิบัติตามบทช่วยสอนนี้ได้อย่างไร

ตอบ: ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบรวม (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET สิ่งนี้ช่วยให้คุณสามารถใช้ประโยชน์จากคุณสมบัติของไลบรารีสำหรับการทำงานกับเอกสาร PDF และปรับแต่งระยะห่างระหว่างบรรทัด

#### ถาม: ฉันสามารถใช้บทช่วยสอนนี้เพื่อระบุระยะห่างบรรทัดสำหรับข้อความประเภทใดก็ได้หรือไม่

ตอบ: ใช่ บทช่วยสอนนี้ให้คำแนะนำเกี่ยวกับวิธีระบุระยะห่างบรรทัดสำหรับเนื้อหาข้อความภายในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้ตัวอย่างโค้ดที่ให้มาเพื่อปรับระยะห่างบรรทัดของข้อความตามความต้องการของคุณ

#### ถาม: ฉันจะระบุโหมดระยะห่างระหว่างบรรทัดในบทช่วยสอนได้อย่างไร

 ตอบ: บทช่วยสอนสาธิตวิธีการสร้าง`TextFormattingOptions` วัตถุและตั้งค่า`LineSpacing` ทรัพย์สินเพื่อ`TextFormattingOptions.LineSpacingMode.FullSize`. โหมดนี้ระบุระยะห่างบรรทัดเต็มสำหรับเนื้อหาข้อความ

#### ถาม: ฉันจะโหลดแบบอักษรเฉพาะสำหรับข้อความได้อย่างไร

 ตอบ: หากคุณต้องการใช้แบบอักษรเฉพาะสำหรับเนื้อหาข้อความ บทช่วยสอนจะให้คำแนะนำเกี่ยวกับวิธีการโหลดไฟล์แบบอักษร TrueType ลงใน`FileStream` object และตั้งเป็นฟอนต์สำหรับ`TextFragment`. ซึ่งช่วยให้คุณสามารถปรับแต่งแบบอักษรของข้อความพร้อมกับระยะห่างระหว่างบรรทัดได้

#### ถาม: ฉันจะปรับแต่งตำแหน่งของข้อความภายในเอกสาร PDF ได้อย่างไร

 ตอบ: หากต้องการปรับแต่งตำแหน่งของข้อความ ให้สร้าง`TextFragment` วัตถุและตั้งค่า`Position`คุณสมบัติไปยังพิกัดที่ต้องการ (X และ Y) ช่วยให้คุณสามารถควบคุมตำแหน่งที่จะวางข้อความภายในเอกสาร PDF ได้

#### ถาม: ฉันสามารถใช้การแก้ไขระยะห่างบรรทัดเหล่านี้กับเอกสาร PDF ที่มีอยู่ได้หรือไม่

 ตอบ: ได้ คุณสามารถแก้ไขระยะห่างระหว่างบรรทัดสำหรับข้อความในเอกสาร PDF ที่มีอยู่ได้ บทช่วยสอนสาธิตวิธีการสร้าง`TextFragment` ด้วยระยะห่างบรรทัดและตำแหน่งที่ระบุ จากนั้นจึงเพิ่มลงในหน้า`Paragraphs` ของสะสม.