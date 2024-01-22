---
title: เพิ่มองค์ประกอบโครงสร้างลงในองค์ประกอบ
linktitle: เพิ่มองค์ประกอบโครงสร้างลงในองค์ประกอบ
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการเพิ่มองค์ประกอบโครงสร้างให้กับองค์ประกอบในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 20
url: /th/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
ในบทช่วยสอนนี้ เราจะให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีเพิ่มองค์ประกอบโครงสร้างให้กับองค์ประกอบในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET Aspose.PDF เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณสามารถสร้าง จัดการ และแปลงเอกสาร PDF โดยทางโปรแกรม การใช้คุณสมบัติโครงสร้างเนื้อหาที่ทำเครื่องหมายไว้ของ Aspose.PDF คุณสามารถสร้างโครงสร้างแบบลำดับชั้นในเอกสาร PDF ของคุณได้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. Visual Studio ติดตั้งด้วย .NET framework
2. ไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ใหม่ใน Visual Studio และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET คุณสามารถดาวน์โหลดไลบรารีได้จากเว็บไซต์ทางการของ Aspose และติดตั้งลงในเครื่องของคุณ

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น

ในไฟล์โค้ด C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นในการเข้าถึงคลาสและวิธีการที่ได้รับจาก Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## ขั้นตอนที่ 3: การสร้างเอกสาร PDF และการกำหนดองค์ประกอบที่มีโครงสร้าง

ใช้รหัสต่อไปนี้เพื่อสร้างเอกสาร PDF และกำหนดองค์ประกอบที่มีโครงสร้าง:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

รหัสนี้จะสร้างเอกสาร PDF เปล่าและเพิ่มองค์ประกอบที่มีโครงสร้าง เช่น ย่อหน้าและช่วง แต่ละองค์ประกอบโครงสร้างถูกสร้างขึ้นโดยใช้วิธีการที่ Aspose.PDF ให้มา

## ขั้นตอนที่ 4: บันทึกเอกสาร PDF

ใช้รหัสต่อไปนี้เพื่อบันทึกเอกสาร PDF:

```csharp
document. Save(outFile);
```

รหัสนี้จะบันทึกเอกสาร PDF พร้อมองค์ประกอบที่มีโครงสร้างลงในไฟล์ที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับเพิ่มองค์ประกอบโครงสร้างลงในองค์ประกอบโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// การสร้างเอกสารและรับเนื้อหา Tagged Pdf
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// การตั้งชื่อเรื่องและภาษาธรรมชาติสำหรับเอกสาร
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// การรับองค์ประกอบโครงสร้างรูท (องค์ประกอบโครงสร้างเอกสาร)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// บันทึกเอกสาร PDF ที่ติดแท็ก
document.Save(outFile);
// ตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีเพิ่มองค์ประกอบโครงสร้างให้กับองค์ประกอบในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET การใช้คุณสมบัติโครงสร้างเนื้อหาที่ทำเครื่องหมายไว้ของ Aspose.PDF คุณสามารถสร้างโครงสร้างแบบลำดับชั้นในเอกสาร PDF ของคุณ ซึ่งทำให้ง่ายต่อการจัดการและนำทางผ่านเนื้อหา

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของการเพิ่มองค์ประกอบโครงสร้างให้กับองค์ประกอบในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: การเพิ่มองค์ประกอบโครงสร้างให้กับองค์ประกอบในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ช่วยให้คุณสามารถสร้างโครงสร้างแบบลำดับชั้นภายในเนื้อหาของเอกสารได้ โครงสร้างแบบลำดับชั้นนี้ปรับปรุงการจัดระเบียบและการนำทางของเนื้อหา ทำให้ง่ายต่อการจัดการและเข้าถึงองค์ประกอบเฉพาะ

#### ถาม: ไลบรารี Aspose.PDF ช่วยในการเพิ่มองค์ประกอบโครงสร้างลงในเอกสาร PDF ได้อย่างไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งมีความสามารถในการสร้าง จัดการ และแปลงเอกสาร PDF โดยทางโปรแกรม ในบทช่วยสอนนี้ คุณลักษณะโครงสร้างเนื้อหาที่ทำเครื่องหมายไว้ของไลบรารีจะถูกนำมาใช้เพื่อสร้างและผนวกองค์ประกอบโครงสร้างเข้ากับเนื้อหาของเอกสาร PDF

#### ถาม: ข้อกำหนดเบื้องต้นในการเพิ่มองค์ประกอบโครงสร้างให้กับเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET มีอะไรบ้าง

ตอบ: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio ด้วยเฟรมเวิร์ก .NET และมีไลบรารี Aspose.PDF สำหรับ .NET ที่อ้างอิงในโปรเจ็กต์ของคุณ

#### ถาม: รหัส C# ที่ให้มาจะสร้างและผนวกองค์ประกอบโครงสร้างเข้ากับเนื้อหาของเอกสาร PDF ได้อย่างไร

ตอบ: โค้ดสาธิตวิธีการสร้างเอกสาร PDF กำหนดองค์ประกอบโครงสร้างรูท และผนวกองค์ประกอบที่มีโครงสร้างต่างๆ เช่น ย่อหน้าและสแปนลงไป แต่ละองค์ประกอบที่มีโครงสร้างถูกสร้างขึ้นโดยใช้วิธีการของ Aspose.PDF ซึ่งช่วยให้คุณสามารถสร้างโครงสร้างแบบลำดับชั้นได้

#### ถาม: ฉันสามารถปรับแต่งประเภทขององค์ประกอบโครงสร้างที่ฉันผนวกเข้ากับเอกสาร PDF ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งประเภทขององค์ประกอบโครงสร้างได้โดยการสำรวจวิธีการต่างๆ ที่ไลบรารี Aspose.PDF มีให้ โค้ดจะแสดงย่อหน้าและช่วงเป็นตัวอย่าง แต่คุณสามารถสร้างและผนวกองค์ประกอบที่มีโครงสร้างประเภทอื่นๆ ได้ตามต้องการ

#### ถาม: ฉันจะกำหนดความสัมพันธ์แบบลำดับชั้นระหว่างองค์ประกอบโครงสร้างที่เพิ่มได้อย่างไร

 ตอบ: ความสัมพันธ์แบบลำดับชั้นระหว่างองค์ประกอบโครงสร้างถูกกำหนดโดยลำดับที่คุณผนวกองค์ประกอบเหล่านั้นเข้ากับองค์ประกอบหลัก ในโค้ด ความสัมพันธ์ระหว่างพ่อแม่และลูกจะถูกสร้างขึ้นโดยใช้`AppendChild` วิธี.

#### ถาม: การสร้างโครงสร้างแบบลำดับชั้นในเอกสาร PDF มีประโยชน์อย่างไร

ตอบ: การสร้างโครงสร้างแบบลำดับชั้นในเอกสาร PDF ช่วยเพิ่มความสามารถในการเข้าถึง การนำทาง และการจัดระเบียบ ช่วยให้เทคโนโลยีช่วยเหลือสามารถตีความและถ่ายทอดเนื้อหาของเอกสารได้ดีขึ้น ทำให้ผู้ทุพพลภาพใช้งานได้ง่ายขึ้น

#### ถาม: ฉันจะตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA หลังจากเพิ่มองค์ประกอบโครงสร้างได้อย่างไร

 ตอบ: รหัสที่ให้ไว้ในบทช่วยสอนสาธิตวิธีการตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA โดยใช้`Validate` วิธี. ด้วยการตรวจสอบความถูกต้องของเอกสารตามมาตรฐาน PDF/UA คุณสามารถมั่นใจได้ว่าองค์ประกอบโครงสร้างที่เพิ่มเข้ามานั้นสอดคล้องกับแนวทางการเข้าถึง

#### ถาม: ฉันสามารถใช้แนวทางนี้เพื่อเพิ่มองค์ประกอบโครงสร้างให้กับเอกสาร PDF ที่มีอยู่ได้หรือไม่

ตอบ: ได้ คุณสามารถแก้ไขแนวทางที่ให้มาเพื่อเพิ่มองค์ประกอบโครงสร้างให้กับเอกสาร PDF ที่มีอยู่ได้ แทนที่จะสร้างเอกสารใหม่ คุณจะโหลดเอกสารที่มีอยู่โดยใช้ Aspose.PDF จากนั้นทำตามขั้นตอนที่คล้ายกันเพื่อผนวกองค์ประกอบโครงสร้าง