---
title: เพิ่ม TOC ลงในไฟล์ PDF
linktitle: เพิ่ม TOC ลงในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มสารบัญลงในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดตัวอย่าง เพิ่มการนำทางเอกสาร!
type: docs
weight: 40
url: /th/net/programming-with-document/addtoc/
---
ในบทช่วยสอนนี้ เราจะสำรวจวิธีใช้คุณสมบัติเพิ่ม TOC (สารบัญ) ลงในไฟล์ PDF ของ Aspose.PDF สำหรับ .NET เพื่อเพิ่มสารบัญลงในเอกสาร PDF เราจะให้คำแนะนำทีละขั้นตอนและอธิบายซอร์สโค้ด C# ที่จำเป็นเพื่อให้บรรลุเป้าหมายนี้ เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถสร้างเอกสาร PDF พร้อมสารบัญโดยใช้ Aspose.PDF สำหรับ .NET ได้


## ขั้นตอนที่ 1: โหลดไฟล์ PDF ที่มีอยู่

 ในการเริ่มต้น เราต้องโหลดไฟล์ PDF ที่มีอยู่ แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดต่อไปนี้พร้อมเส้นทางจริงไปยังไฟล์ PDF ของคุณ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## ขั้นตอนที่ 2: สร้างหน้าใหม่สำหรับสารบัญ

เราจะสร้างหน้าใหม่เพื่อเก็บสารบัญ รหัสต่อไปนี้แทรกหน้าใหม่ที่ดัชนี 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## ขั้นตอนที่ 3: กำหนดข้อมูลสารบัญ

ต่อไปเราจะต้องกำหนดข้อมูลสารบัญ เราจะตั้งชื่อและคุณสมบัติอื่นๆ ของสารบัญ เพิ่มรหัสต่อไปนี้:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## ขั้นตอนที่ 4: สร้างองค์ประกอบ TOC

ตอนนี้เราจะสร้างองค์ประกอบของสารบัญ ในบทช่วยสอนนี้ เราจะสร้างองค์ประกอบ TOC สี่องค์ประกอบที่สอดคล้องกับหน้าต่างๆ แก้ไขรหัสต่อไปนี้ตามความต้องการของคุณ:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## ขั้นตอนที่ 5: บันทึกเอกสารที่อัปเดต

 สุดท้ายเราจำเป็นต้องบันทึกเอกสารที่แก้ไขพร้อมกับสารบัญ แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดด้านล่างพร้อมเส้นทางไฟล์เอาต์พุตที่ต้องการ:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับการเพิ่ม TOC ลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// โหลดไฟล์ PDF ที่มีอยู่
Document doc = new Document(dataDir + "AddTOC.pdf");

// เข้าถึงหน้าแรกของไฟล์ PDF
Page tocPage = doc.Pages.Insert(1);

// สร้างวัตถุเพื่อแสดงข้อมูล TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// ตั้งชื่อเรื่อง TOC
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//สร้างวัตถุสตริงที่จะใช้เป็นองค์ประกอบ TOC
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// สร้างวัตถุหัวเรื่อง
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// ระบุหน้าปลายทางสำหรับวัตถุหัวเรื่อง
	heading2.DestinationPage = doc.Pages[i + 2];

	// หน้าปลายทาง
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// พิกัดปลายทาง
	segment2.Text = titles[i];

	// เพิ่มส่วนหัวไปยังหน้าที่มี TOC
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// บันทึกเอกสารที่อัพเดต
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีเพิ่มสารบัญ (TOC) ลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ด C# ที่ให้มา คุณสามารถสร้างเอกสาร PDF พร้อมสารบัญได้อย่างง่ายดาย TOC ช่วยเพิ่มความสามารถในการใช้งานของเอกสาร ทำให้ผู้ใช้สามารถนำทางไปยังส่วนหรือหน้าเฉพาะได้อย่างมีประสิทธิภาพมากขึ้น Aspose.PDF สำหรับ .NET มอบโซลูชันที่มีประสิทธิภาพและเป็นมิตรต่อผู้ใช้สำหรับการทำงานกับไฟล์ PDF ในแอปพลิเคชัน .NET ทำให้คุณสามารถสร้างเอกสาร PDF แบบไดนามิกและโต้ตอบได้อย่างง่ายดาย

### คำถามที่พบบ่อยสำหรับการเพิ่ม TOC ลงในไฟล์ PDF

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ PDF ในแอปพลิเคชัน .NET ได้อย่างมีประสิทธิภาพ โดยมีคุณสมบัติที่หลากหลายสำหรับการสร้าง จัดการ และจัดการเอกสาร PDF โดยทางโปรแกรม

#### ถาม: การเพิ่มสารบัญ (TOC) ลงในเอกสาร PDF มีวัตถุประสงค์อะไร

ตอบ: สารบัญ (TOC) ให้ความช่วยเหลือในการนำทางสำหรับผู้ใช้ ช่วยให้ผู้ใช้สามารถข้ามไปยังส่วนหรือหน้าเฉพาะภายในเอกสาร PDF ได้อย่างรวดเร็ว ช่วยปรับปรุงการใช้งานและประสบการณ์ผู้ใช้ของเอกสาร

#### ถาม: ฉันจะเพิ่มสารบัญลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการเพิ่มสารบัญลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณต้องสร้างเพจใหม่เพื่อเก็บ TOC กำหนดข้อมูลสารบัญ จากนั้นสร้างองค์ประกอบ TOC ที่สอดคล้องกับเพจเฉพาะหรือ ส่วนต่างๆ ในเอกสาร

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของสารบัญได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของสารบัญได้โดยการตั้งค่าคุณสมบัติต่างๆ ขององค์ประกอบ TOC เช่น ขนาดตัวอักษร ลักษณะแบบอักษร และการจัดตำแหน่ง Aspose.PDF สำหรับ .NET ให้ความยืดหยุ่นในการออกแบบ TOC เพื่อให้ตรงกับรูปลักษณ์ที่คุณต้องการ

#### ถาม: Aspose.PDF สำหรับ .NET เหมาะสำหรับการเพิ่มคุณสมบัติขั้นสูงให้กับเอกสาร PDF หรือไม่

ตอบ: แน่นอนว่า Aspose.PDF สำหรับ .NET เป็นไลบรารี่ที่มีฟีเจอร์มากมายที่ช่วยให้คุณสามารถเพิ่มฟังก์ชันการทำงานขั้นสูงให้กับเอกสาร PDF ได้ รวมถึงองค์ประกอบเชิงโต้ตอบ ฟิลด์แบบฟอร์ม ลายเซ็นดิจิทัล และอื่นๆ อีกมากมาย