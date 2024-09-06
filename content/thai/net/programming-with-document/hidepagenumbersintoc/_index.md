---
title: ซ่อนหมายเลขหน้าในสารบัญ
linktitle: ซ่อนหมายเลขหน้าในสารบัญ
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีซ่อนหมายเลขหน้าในสารบัญโดยใช้ Aspose.PDF สำหรับ .NET ด้วยคู่มือทีละขั้นตอนนี้
type: docs
weight: 220
url: /th/net/programming-with-document/hidepagenumbersintoc/
---
ในบทความนี้ เราจะพูดถึงการนำฟีเจอร์ Hide Page Numbers In TOC ของ Aspose.PDF สำหรับ .NET ไปใช้โดยใช้ C# เราจะเริ่มด้วยการแนะนำ Aspose.PDF สำหรับ .NET สั้นๆ จากนั้นจะเจาะลึกคู่มือทีละขั้นตอนในการนำฟีเจอร์นี้ไปใช้ 

## บทนำสู่ Aspose.PDF สำหรับ .NET

Aspose.PDF สำหรับ .NET เป็นส่วนประกอบการจัดการ PDF ที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และจัดการไฟล์ PDF ได้ด้วยโปรแกรม ส่วนประกอบนี้มีคุณสมบัติและฟังก์ชันมากมายที่ทำให้ทำงานกับเอกสาร PDF ได้ง่าย Aspose.PDF สำหรับ .NET รองรับระบบปฏิบัติการทั้งแบบ 32 บิตและ 64 บิต และสามารถใช้กับแพลตฟอร์ม .NET Framework, .NET Core และ Xamarin 

## คุณลักษณะซ่อนหมายเลขหน้าในสารบัญคืออะไร

สารบัญ (TOC) เป็นส่วนสำคัญของเอกสาร PDF ที่ให้ผู้ใช้ดูภาพรวมของเนื้อหาได้อย่างรวดเร็ว บางครั้งผู้ใช้ต้องการซ่อนหมายเลขหน้าในสารบัญเพื่อให้ใช้งานได้ง่ายขึ้น Aspose.PDF สำหรับ .NET มีฟีเจอร์ในตัวสำหรับซ่อนหมายเลขหน้าในสารบัญ ซึ่งสามารถใช้ฟีเจอร์นี้เพื่อสร้างเอกสาร PDF ที่ใช้งานง่ายยิ่งขึ้นได้ 

## ข้อกำหนดเบื้องต้น

หากต้องการทำตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- Visual Studio 2010 หรือใหม่กว่า
- Aspose.PDF สำหรับ .NET ติดตั้งบนระบบของคุณ
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#

## คำแนะนำทีละขั้นตอนในการนำฟีเจอร์ซ่อนหมายเลขหน้าใน TOC ไปใช้

ปฏิบัติตามขั้นตอนต่อไปนี้เพื่อใช้งานคุณลักษณะซ่อนหมายเลขหน้าใน TOC โดยใช้ Aspose.PDF สำหรับ .NET:

## ขั้นตอนที่ 1: สร้างแอปพลิเคชันคอนโซล C# ใหม่ใน Visual Studio

เปิด Visual Studio และสร้างแอปพลิเคชันคอนโซล C# ใหม่

## ขั้นตอนที่ 2: เพิ่มการอ้างอิงถึง Aspose.PDF สำหรับ .NET

คลิกขวาที่โฟลเดอร์ References ในโปรเจ็กต์ของคุณ และเลือก Add Reference ค้นหาตำแหน่งที่ติดตั้ง Aspose.PDF for .NET ไว้ในระบบของคุณ และเพิ่มการอ้างอิงลงไป

## ขั้นตอนที่ 1: สร้างเอกสาร PDF ใหม่

สร้างเอกสาร PDF ใหม่โดยใช้โค้ดดังต่อไปนี้:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## ขั้นตอนที่ 2: สร้างหน้า TOC

สร้างหน้าใหม่สำหรับ TOC และเพิ่มลงในเอกสาร PDF โดยใช้โค้ดต่อไปนี้:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## ขั้นตอนที่ 3: เพิ่มส่วนรายการลงในคอลเล็กชันส่วนของเอกสาร PDF

เพิ่มส่วนรายการลงในคอลเล็กชันส่วนของเอกสาร PDF โดยใช้โค้ดต่อไปนี้:

```csharp
tocPage.TocInfo = tocInfo;
```

## ขั้นตอนที่ 4: กำหนดรูปแบบของรายการทั้งสี่ระดับ

กำหนดรูปแบบของรายการทั้งสี่ระดับโดยกำหนดระยะขอบด้านซ้ายและการตั้งค่ารูปแบบข้อความของแต่ละระดับโดยใช้โค้ดต่อไปนี้:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 5: เพิ่มหัวข้อสี่หัวข้อในส่วน

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### ตัวอย่างโค้ดต้นฉบับสำหรับการซ่อนหมายเลขหน้าใน TOC โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//เพิ่มส่วนรายการลงในคอลเล็กชันส่วนของเอกสาร Pdf
tocPage.TocInfo = tocInfo;
//กำหนดรูปแบบของรายการสี่ระดับโดยตั้งค่าระยะขอบซ้ายและ
//การตั้งค่ารูปแบบข้อความของแต่ละระดับ

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//เพิ่มหัวข้อสี่หัวข้อในส่วน
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการทำงานกับข้อมูลเมตา XMP ในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ข้อมูลเมตา XMP ให้ข้อมูลอันมีค่าเกี่ยวกับเอกสาร PDF รวมถึงชื่อ ผู้แต่ง วันที่สร้าง และอื่นๆ อีกมากมาย Aspose.PDF สำหรับ .NET ช่วยให้นักพัฒนาเข้าถึงและจัดการข้อมูลเมตาเหล่านี้ได้ โดยให้ API ที่ยืดหยุ่นและทรงพลังสำหรับการทำงานกับเอกสาร PDF

### คำถามที่พบบ่อย

#### ถาม: เมตาข้อมูล XMP ในเอกสาร PDF คืออะไร

A: เมตาดาต้า XMP (Extensible Metadata Platform) ในเอกสาร PDF เป็นรูปแบบมาตรฐานสำหรับการจัดเก็บข้อมูลเมตาดาต้าเกี่ยวกับเอกสาร ซึ่งประกอบด้วยรายละเอียดต่างๆ เช่น ชื่อเอกสาร ผู้เขียน วันที่สร้าง คำสำคัญ และอื่นๆ เมตาดาต้า XMP มอบวิธีการจัดเก็บและแบ่งปันข้อมูลเกี่ยวกับเอกสาร PDF ที่มีโครงสร้างและเป็นมาตรฐาน

#### ถาม: ฉันสามารถปรับเปลี่ยนข้อมูลเมตา XMP ของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

 A: ใช่ คุณสามารถแก้ไขข้อมูลเมตา XMP ของเอกสาร PDF ได้ด้วยโปรแกรมโดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถเข้าถึง`Info` ทรัพย์สินของ`Document` อ็อบเจ็กต์ที่ให้คุณเข้าถึงคุณสมบัติเมตาข้อมูล XMP จากนั้นคุณสามารถอัปเดตค่าของคุณสมบัติเหล่านี้เพื่อปรับเปลี่ยนเมตาข้อมูล XMP ของเอกสาร PDF

#### ถาม: ฉันสามารถแยกคุณสมบัติเมตาข้อมูล XMP แบบกำหนดเองจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

 A: ใช่ คุณสามารถแยกคุณสมบัติเมตาข้อมูล XMP ที่กำหนดเองจากเอกสาร PDF ได้โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้`Metadata` ทรัพย์สินของ`Document`อ็อบเจ็กต์ซึ่งให้การเข้าถึงคุณสมบัติเมตาข้อมูล XMP ทั้งหมดของเอกสาร PDF จากนั้นคุณสามารถแยกคุณสมบัติที่กำหนดเองและใช้ค่าตามต้องการได้