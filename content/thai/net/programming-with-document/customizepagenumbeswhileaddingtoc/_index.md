---
title: ปรับแต่ง Page Numbes ในขณะที่เพิ่ม TOC
linktitle: ปรับแต่ง Page Numbes ในขณะที่เพิ่ม TOC
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีปรับแต่งหมายเลขหน้าในขณะที่เพิ่มสารบัญ (TOC) โดยใช้ Aspose.PDF สำหรับ .NET พร้อมคำแนะนำและตัวอย่างโค้ดทีละขั้นตอนนี้
type: docs
weight: 100
url: /th/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
ในบทช่วยสอนนี้ เราจะสำรวจวิธีปรับแต่งหมายเลขหน้าในขณะที่เพิ่มสารบัญ (TOC) โดยใช้ Aspose.PDF สำหรับ .NET เราจะให้คำแนะนำทีละขั้นตอนพร้อมกับตัวอย่างโค้ดเพื่อช่วยให้คุณบรรลุเป้าหมายนี้

## ขั้นตอนที่ 1: กำลังโหลดไฟล์ PDF ที่มีอยู่

ก่อนอื่น เราต้องโหลดไฟล์ PDF ที่มีอยู่ก่อน สำหรับบทช่วยสอนนี้ เราจะใช้ไฟล์ "42824.pdf" ที่อยู่ในไดเรกทอรี "ไดเรกทอรีเอกสารของคุณ" แทนที่เส้นทางไดเรกทอรีนี้ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## ขั้นตอนที่ 2: การเพิ่มหน้า TOC

 ต่อไปเราต้องเพิ่มหน้าใหม่ที่จุดเริ่มต้นของเอกสารเพื่อใช้เป็นหน้า TOC เราสามารถทำได้โดยใช้`Insert()` วิธีการของ`Pages` คอลเลกชันของ`Document` วัตถุ.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## ขั้นตอนที่ 3: การสร้างวัตถุ TOC

 ในการสร้างวัตถุ TOC ก่อนอื่นเราต้องสร้าง`TocInfo` วัตถุและกำหนดคุณสมบัติของมัน ในบทช่วยสอนนี้ เราจะตั้งชื่อ TOC เป็น "สารบัญ" และคำนำหน้าหมายเลขหน้าเป็น "P"

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## ขั้นตอนที่ 4: การสร้างรายการ TOC

ในการสร้างรายการ TOC เราจำเป็นต้องวนซ้ำทุกหน้าของเอกสาร ยกเว้นหน้า TOC และสร้างออบเจ็กต์ส่วนหัวสำหรับแต่ละหน้า จากนั้นเราสามารถเพิ่มออบเจ็กต์ส่วนหัวลงในหน้า TOC และระบุหน้าปลายทางได้

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // สร้างวัตถุหัวเรื่อง
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // ระบุหน้าปลายทางสำหรับวัตถุหัวเรื่อง
    heading2.DestinationPage = doc.Pages[i + 1];
    // หน้าปลายทาง
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // พิกัดปลายทาง
    segment2.Text = "Page " + i.ToString();
    // เพิ่มส่วนหัวไปยังหน้าที่มี TOC
    tocPage.Paragraphs.Add(heading2);
}
```

## ขั้นตอนที่ 5: บันทึกเอกสารที่อัพเดต

สุดท้ายนี้ เราจำเป็นต้องบันทึกเอกสารที่อัปเดตเป็นไฟล์ใหม่ เราสามารถทำได้โดยใช้`Save()` วิธีการของ`Document` วัตถุ.

```csharp
doc.Save(outFile);
```

### ตัวอย่างซอร์สโค้ดสำหรับปรับแต่งหมายเลขหน้าขณะเพิ่ม TOC โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// โหลดไฟล์ PDF ที่มีอยู่
Document doc = new Document(inFile);
// เข้าถึงหน้าแรกของไฟล์ PDF
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// สร้างวัตถุเพื่อแสดงข้อมูล TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// ตั้งชื่อเรื่อง TOC
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// สร้างวัตถุหัวเรื่อง
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// ระบุหน้าปลายทางสำหรับวัตถุหัวเรื่อง
	heading2.DestinationPage = doc.Pages[i + 1];
	// หน้าปลายทาง
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// พิกัดปลายทาง
	segment2.Text = "Page " + i.ToString();
	// เพิ่มส่วนหัวไปยังหน้าที่มี TOC
	tocPage.Paragraphs.Add(heading2);
}

// บันทึกเอกสารที่อัพเดต
doc.Save(outFile);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้ให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีปรับแต่งหมายเลขหน้าในขณะที่เพิ่ม TOC โดยใช้ Aspose.PDF สำหรับ .NET นอกจากนี้เรายังได้จัดเตรียมตัวอย่างโค้ดที่คุณสามารถใช้เป็นข้อมูลอ้างอิงเมื่อใช้งานคุณลักษณะนี้ในของคุณ

### คำถามที่พบบ่อย

#### ถาม: สารบัญ (TOC) ในเอกสาร PDF คืออะไร

ตอบ: สารบัญ (TOC) ในเอกสาร PDF เป็นตัวช่วยการนำทางที่จัดเตรียมรายการส่วนหรือบทของเอกสารที่จัดระเบียบพร้อมกับหมายเลขหน้าที่เกี่ยวข้อง ช่วยให้ผู้อ่านนำทางไปยังส่วนเฉพาะภายในเอกสารได้อย่างรวดเร็ว

#### ถาม:เหตุใดฉันจึงต้องการปรับแต่งหมายเลขหน้าใน TOC

ตอบ: การปรับแต่งหมายเลขหน้าใน TOC จะมีประโยชน์เมื่อคุณต้องการใช้รูปแบบการกำหนดหมายเลขหน้าเฉพาะ หรือรวมข้อมูลเพิ่มเติมพร้อมกับหมายเลขหน้า ช่วยให้คุณสร้างสารบัญที่เป็นส่วนตัวและให้ข้อมูลมากขึ้น

#### ถาม: ฉันสามารถใส่ไฮเปอร์ลิงก์ใน TOC เพื่อเชื่อมโยงไปยังส่วนหรือหน้าเฉพาะภายในเอกสาร PDF ได้หรือไม่

ตอบ: ได้ Aspose.PDF สำหรับ .NET ช่วยให้คุณสร้างไฮเปอร์ลิงก์ใน TOC ที่ลิงก์ไปยังส่วนหรือหน้าเฉพาะภายในเอกสาร PDF สิ่งนี้ช่วยเพิ่มการโต้ตอบและการนำทางของเอกสาร PDF

#### ถาม: Aspose.PDF สำหรับ .NET เข้ากันได้กับมาตรฐาน PDF/A หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET รองรับมาตรฐาน PDF/A รวมถึง PDF/A-1, PDF/A-2 และ PDF/A-3 ช่วยให้คุณสร้างเอกสาร PDF ที่สอดคล้องกับข้อกำหนดในการเก็บถาวรและการเก็บรักษาในระยะยาว

#### ถาม: ฉันสามารถเพิ่มการจัดรูปแบบเพิ่มเติมให้กับรายการ TOC เช่น ลักษณะแบบอักษรหรือสีได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มการจัดรูปแบบเพิ่มเติมในรายการ TOC ได้ เช่น ลักษณะแบบอักษร สี และขนาดแบบอักษร โดยใช้ Aspose.PDF สำหรับ .NET สิ่งนี้ช่วยให้คุณปรับแต่งรูปลักษณ์ของ TOC ได้ตามความต้องการของคุณ
