---
title: ซ่อนหมายเลขหน้าใน TOC
linktitle: ซ่อนหมายเลขหน้าใน TOC
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีซ่อนหมายเลขหน้าในสารบัญโดยใช้ Aspose.PDF สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนนี้
type: docs
weight: 220
url: /th/net/programming-with-document/hidepagenumbersintoc/
---
ในบทความนี้ เราจะหารือเกี่ยวกับการใช้งานคุณลักษณะซ่อนหมายเลขหน้าใน TOC ของ Aspose.PDF สำหรับ .NET โดยใช้ C# เราจะเริ่มต้นด้วยการแนะนำสั้นๆ เกี่ยวกับ Aspose.PDF สำหรับ .NET จากนั้นเจาะลึกคำแนะนำทีละขั้นตอนเพื่อใช้งานฟีเจอร์นี้ 

## ข้อมูลเบื้องต้นเกี่ยวกับ Aspose.PDF สำหรับ .NET

Aspose.PDF สำหรับ .NET เป็นส่วนประกอบการจัดการ PDF ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และจัดการไฟล์ PDF โดยทางโปรแกรม มีคุณสมบัติและฟังก์ชันการทำงานที่หลากหลายซึ่งทำให้ง่ายต่อการทำงานกับเอกสาร PDF Aspose.PDF สำหรับ .NET รองรับระบบปฏิบัติการทั้ง 32 บิตและ 64 บิต และสามารถใช้ได้กับแพลตฟอร์ม .NET Framework, .NET Core และ Xamarin 

## คุณสมบัติซ่อนหมายเลขหน้าใน TOC คืออะไร

สารบัญ (TOC) เป็นส่วนสำคัญของเอกสาร PDF ที่ให้ผู้ใช้เห็นภาพรวมของเนื้อหาโดยย่อ บางครั้งผู้ใช้อาจต้องการซ่อนหมายเลขหน้าใน TOC เพื่อให้ใช้งานง่ายยิ่งขึ้น Aspose.PDF สำหรับ .NET มีคุณสมบัติในตัวเพื่อซ่อนหมายเลขหน้าใน TOC คุณสมบัตินี้สามารถใช้เพื่อสร้างเอกสาร PDF ที่เป็นมิตรต่อผู้ใช้มากขึ้น 

## ข้อกำหนดเบื้องต้น

หากต้องการปฏิบัติตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- Visual Studio 2010 หรือใหม่กว่า
- ติดตั้ง Aspose.PDF สำหรับ .NET ในระบบของคุณ
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#

## คำแนะนำทีละขั้นตอนในการใช้ฟีเจอร์ซ่อนหมายเลขหน้าใน TOC

ทำตามขั้นตอนด้านล่างเพื่อใช้ฟีเจอร์ซ่อนหมายเลขหน้าใน TOC โดยใช้ Aspose.PDF สำหรับ .NET:

## ขั้นตอนที่ 1: สร้างแอปพลิเคชันคอนโซล C# ใหม่ใน Visual Studio

เปิด Visual Studio และสร้างแอปพลิเคชันคอนโซล C# ใหม่

## ขั้นตอนที่ 2: เพิ่มการอ้างอิงถึง Aspose.PDF สำหรับ .NET

คลิกขวาที่โฟลเดอร์ References ในโครงการของคุณ และเลือก Add Reference เรียกดูตำแหน่งที่ติดตั้ง Aspose.PDF สำหรับ .NET บนระบบของคุณ และเพิ่มข้อมูลอ้างอิงลงไป

## ขั้นตอนที่ 1: สร้างเอกสาร PDF ใหม่

สร้างเอกสาร PDF ใหม่โดยใช้รหัสต่อไปนี้:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## ขั้นตอนที่ 2: สร้างหน้า TOC

สร้างหน้าใหม่สำหรับ TOC และเพิ่มลงในเอกสาร PDF โดยใช้รหัสต่อไปนี้:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## ขั้นตอนที่ 3: เพิ่มส่วนรายการลงในคอลเลกชันส่วนของเอกสาร PDF

เพิ่มส่วนรายการลงในคอลเลกชันส่วนของเอกสาร PDF โดยใช้รหัสต่อไปนี้:

```csharp
tocPage.TocInfo = tocInfo;
```

## ขั้นตอนที่ 4: กำหนดรูปแบบของรายการสี่ระดับ

กำหนดรูปแบบของรายการสี่ระดับโดยการตั้งค่าระยะขอบซ้ายและรูปแบบข้อความของแต่ละระดับโดยใช้รหัสต่อไปนี้:

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

## ขั้นตอนที่ 5: เพิ่มสี่หัวข้อในส่วนนี้

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

### ตัวอย่างซอร์สโค้ดสำหรับการซ่อนหมายเลขหน้าใน TOC โดยใช้ Aspose.PDF สำหรับ .NET

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
//เพิ่มส่วนรายการลงในคอลเลกชันส่วนของเอกสาร Pdf
tocPage.TocInfo = tocInfo;
//กำหนดรูปแบบของรายการสี่ระดับโดยการตั้งค่าระยะขอบด้านซ้ายและ
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
//เพิ่มสี่หัวข้อในส่วนนี้
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

ในบทช่วยสอนนี้ เราได้ศึกษาวิธีทำงานกับข้อมูลเมตา XMP ในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ข้อมูลเมตา XMP ให้ข้อมูลที่เป็นประโยชน์เกี่ยวกับเอกสาร PDF รวมถึงชื่อเรื่อง ผู้แต่ง วันที่สร้าง และอื่นๆ Aspose.PDF สำหรับ .NET ช่วยให้นักพัฒนาสามารถเข้าถึงและจัดการข้อมูลเมตานี้ โดยให้ API ที่ยืดหยุ่นและมีประสิทธิภาพสำหรับการทำงานกับเอกสาร PDF

### คำถามที่พบบ่อย

#### ถาม: เมตาดาต้า XMP ในเอกสาร PDF คืออะไร

ตอบ: ข้อมูลเมตา XMP (Extensible Metadata Platform) ในเอกสาร PDF เป็นรูปแบบมาตรฐานสำหรับการจัดเก็บข้อมูลเมตาดาต้าเกี่ยวกับเอกสาร ประกอบด้วยรายละเอียดต่างๆ เช่น ชื่อเอกสาร ผู้แต่ง วันที่สร้าง คำสำคัญ และอื่นๆ ข้อมูลเมตา XMP มีวิธีการจัดเก็บและแบ่งปันข้อมูลเกี่ยวกับเอกสาร PDF ที่มีโครงสร้างและเป็นมาตรฐาน

#### ถาม: ฉันสามารถแก้ไขข้อมูลเมตา XMP ของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

 ตอบ: ได้ คุณสามารถแก้ไขข้อมูลเมตา XMP ของเอกสาร PDF โดยทางโปรแกรมโดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถเข้าถึง`Info` ทรัพย์สินของ`Document` วัตถุซึ่งช่วยให้คุณเข้าถึงคุณสมบัติข้อมูลเมตา XMP จากนั้น คุณสามารถอัปเดตค่าของคุณสมบัติเหล่านี้เพื่อแก้ไขข้อมูลเมตา XMP ของเอกสาร PDF

#### ถาม: ฉันสามารถแยกคุณสมบัติเมตาดาต้า XMP แบบกำหนดเองจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

 ตอบ: ได้ คุณสามารถแยกคุณสมบัติเมตาดาต้า XMP แบบกำหนดเองจากเอกสาร PDF ได้โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้`Metadata` ทรัพย์สินของ`Document`วัตถุซึ่งให้การเข้าถึงคุณสมบัติข้อมูลเมตา XMP ทั้งหมดของเอกสาร PDF จากนั้นคุณสามารถแยกคุณสมบัติแบบกำหนดเองและใช้ค่าได้ตามต้องการ