---
title: ระบุระยะห่างระหว่างบรรทัดในไฟล์ PDF
linktitle: ระบุระยะห่างระหว่างบรรทัดในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีระบุระยะห่างระหว่างบรรทัดในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 510
url: /th/net/programming-with-text/specify-line-spacing/
---
บทช่วยสอนนี้จะอธิบายวิธีการระบุระยะห่างระหว่างบรรทัดในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนต่างๆ ของกระบวนการ

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
using System.IO;
```

## ขั้นตอนที่ 3: ตั้งค่าเส้นทางไปยังไดเรกทอรีเอกสาร

 ตั้งค่าเส้นทางไปยังไดเรกทอรีเอกสารของคุณโดยใช้`dataDir` ตัวแปร:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: โหลดไฟล์ PDF อินพุต

 โหลดไฟล์ PDF อินพุตโดยใช้`Document` ระดับ:

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 5: สร้าง TextFormattingOptions

 สร้าง`TextFormattingOptions` วัตถุและตั้งค่าโหมดระยะห่างระหว่างบรรทัดเป็น`FullSize`-

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## ขั้นตอนที่ 6: สร้าง TextFragment

 สร้าง`TextFragment` วัตถุและระบุเนื้อหาข้อความ:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## ขั้นตอนที่ 7: โหลดไฟล์ฟอนต์ (ทางเลือก)

 หากคุณต้องการใช้แบบอักษรเฉพาะสำหรับข้อความ ให้โหลดไฟล์แบบอักษร TrueType ลงใน`FileStream` วัตถุ:

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

 เพิ่มส่วนข้อความลงในเอกสารโดยผนวกเข้ากับ`TextBuilder` หรือตรงไปที่หน้า`Paragraphs` ของสะสม:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## ขั้นตอนที่ 10: บันทึกเอกสาร PDF ที่ได้

บันทึกเอกสาร PDF ที่แก้ไขแล้ว:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 อย่าลืมเปลี่ยน`"SpecifyLineSpacing_out.pdf"` พร้อมชื่อไฟล์เอาท์พุตตามที่ต้องการ

### ตัวอย่างโค้ดต้นฉบับสำหรับการระบุระยะห่างระหว่างบรรทัดโดยใช้ Aspose.PDF สำหรับ .NET 
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
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// สร้างส่วนข้อความด้วยสตริงตัวอย่าง
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// โหลดแบบอักษร TrueType ลงในวัตถุสตรีม
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// ตั้งชื่อแบบอักษรสำหรับสตริงข้อความ
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		//ระบุตำแหน่งสำหรับ Text Fragment
		textFragment.Position = new Position(100, 600);
		//ตั้งค่า TextFormattingOptions ของส่วนปัจจุบันให้กำหนดไว้ล่วงหน้า (ซึ่งชี้ไปที่ LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// เพิ่มข้อความลงใน TextBuilder เพื่อให้สามารถวางทับไฟล์ PDF ได้
		//textBuilder.AppendText(ข้อความFragment)
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// บันทึกเอกสาร PDF ที่ได้
	doc.Save(dataDir);
}
```

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีระบุระยะห่างระหว่างบรรทัดในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนตั้งแต่การตั้งค่าโครงการไปจนถึงการบันทึกเอกสารที่แก้ไขแล้ว ตอนนี้คุณสามารถนำโค้ดนี้ไปใช้กับโครงการ C# ของคุณเองเพื่อกำหนดระยะห่างระหว่างบรรทัดของข้อความในไฟล์ PDF ได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "ระบุระยะห่างบรรทัดในไฟล์ PDF" คืออะไร

A: บทช่วยสอน "ระบุระยะห่างระหว่างบรรทัดในไฟล์ PDF" มีวัตถุประสงค์เพื่อแนะนำผู้ใช้เกี่ยวกับวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อกำหนดระยะห่างระหว่างบรรทัดของข้อความภายในเอกสาร PDF บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนและตัวอย่างโค้ด C# เพื่อสาธิตกระบวนการ

#### ถาม: บทช่วยสอนนี้ช่วยในการระบุระยะห่างระหว่างบรรทัดในเอกสาร PDF ได้อย่างไร

A: บทช่วยสอนนี้จะช่วยให้ผู้ใช้เข้าใจถึงวิธีใช้ความสามารถของ Aspose.PDF สำหรับ .NET เพื่อกำหนดระยะห่างระหว่างบรรทัดสำหรับข้อความในเอกสาร PDF โดยทำตามขั้นตอนและตัวอย่างโค้ดที่ให้มา ผู้ใช้สามารถปรับระยะห่างระหว่างบรรทัดตามความต้องการได้

#### ถาม: มีข้อกำหนดเบื้องต้นอะไรบ้างที่ต้องปฏิบัติตามบทช่วยสอนนี้?

A: ก่อนเริ่มบทช่วยสอน คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# นอกจากนี้ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET คุณสามารถรับได้จากเว็บไซต์ Aspose หรือติดตั้งในโปรเจ็กต์ของคุณโดยใช้ NuGet

#### ถาม: ฉันจะตั้งค่าโครงการเพื่อทำตามบทช่วยสอนนี้ได้อย่างไร

A: ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET วิธีนี้ช่วยให้คุณสามารถใช้ประโยชน์จากคุณลักษณะของไลบรารีสำหรับการทำงานกับเอกสาร PDF และกำหนดระยะห่างระหว่างบรรทัดเองได้

#### ถาม: ฉันสามารถใช้บทช่วยสอนนี้เพื่อระบุระยะห่างระหว่างบรรทัดสำหรับข้อความทุกประเภทได้หรือไม่

A: ใช่ บทช่วยสอนนี้ให้คำแนะนำเกี่ยวกับวิธีการกำหนดระยะห่างระหว่างบรรทัดสำหรับเนื้อหาข้อความใดๆ ในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้ตัวอย่างโค้ดที่ให้มาเพื่อปรับระยะห่างระหว่างบรรทัดของข้อความตามความต้องการของคุณ

#### ถาม: ฉันจะระบุโหมดระยะห่างระหว่างบรรทัดในบทช่วยสอนได้อย่างไร

 A: บทช่วยสอนนี้สาธิตวิธีการสร้าง`TextFormattingOptions` วัตถุและตั้งค่าของมัน`LineSpacing` ทรัพย์สินที่จะ`TextFormattingOptions.LineSpacingMode.FullSize`โหมดนี้จะระบุระยะห่างระหว่างบรรทัดแบบเต็มสำหรับเนื้อหาข้อความ

#### ถาม: ฉันจะโหลดแบบอักษรเฉพาะสำหรับข้อความได้อย่างไร

 A: หากคุณต้องการใช้แบบอักษรเฉพาะสำหรับเนื้อหาข้อความ บทช่วยสอนจะให้คำแนะนำเกี่ยวกับวิธีการโหลดไฟล์แบบอักษร TrueType ลงใน`FileStream` วัตถุและตั้งเป็นแบบอักษรสำหรับ`TextFragment`ซึ่งจะทำให้คุณปรับแต่งแบบอักษรของข้อความและระยะห่างระหว่างบรรทัดได้

#### ถาม: ฉันจะกำหนดตำแหน่งข้อความภายในเอกสาร PDF ได้อย่างไร

 ก: เพื่อปรับแต่งตำแหน่งของข้อความ ให้สร้าง`TextFragment` วัตถุและตั้งค่าของมัน`Position`คุณสมบัติเป็นพิกัดที่ต้องการ (X และ Y) ซึ่งจะช่วยให้คุณควบคุมตำแหน่งที่จะวางข้อความภายในเอกสาร PDF ได้

#### ถาม: ฉันสามารถใช้การปรับเปลี่ยนระยะห่างระหว่างบรรทัดนี้กับเอกสาร PDF ที่มีอยู่ได้หรือไม่

 A: ใช่ คุณสามารถปรับเปลี่ยนระยะห่างระหว่างบรรทัดสำหรับข้อความในเอกสาร PDF ที่มีอยู่ได้ บทช่วยสอนจะสาธิตวิธีการสร้าง`TextFragment` ด้วยระยะห่างบรรทัดและตำแหน่งที่กำหนด แล้วเพิ่มลงในหน้า`Paragraphs` ของสะสม.