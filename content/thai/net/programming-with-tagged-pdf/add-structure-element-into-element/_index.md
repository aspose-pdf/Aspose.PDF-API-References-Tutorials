---
title: เพิ่มองค์ประกอบโครงสร้างลงในองค์ประกอบ
linktitle: เพิ่มองค์ประกอบโครงสร้างลงในองค์ประกอบ
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: คู่มือทีละขั้นตอนในการเพิ่มองค์ประกอบโครงสร้างให้กับองค์ประกอบในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 20
url: /th/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
ในบทช่วยสอนนี้ เราจะให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการเพิ่มองค์ประกอบโครงสร้างให้กับองค์ประกอบในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET Aspose.PDF เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้คุณสร้าง จัดการ และแปลงเอกสาร PDF ได้ด้วยโปรแกรม ด้วยการใช้คุณลักษณะโครงสร้างเนื้อหาที่ทำเครื่องหมายไว้ของ Aspose.PDF คุณสามารถสร้างโครงสร้างแบบลำดับชั้นในเอกสาร PDF ของคุณได้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. ติดตั้ง Visual Studio ด้วย .NET framework
2. ไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ใหม่ใน Visual Studio และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET คุณสามารถดาวน์โหลดไลบรารีจากเว็บไซต์อย่างเป็นทางการของ Aspose และติดตั้งบนเครื่องของคุณได้

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น

ในไฟล์โค้ด C# ของคุณ นำเข้าเนมสเปซที่จำเป็นในการเข้าถึงคลาสและวิธีการที่ Aspose.PDF จัดเตรียมไว้:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## ขั้นตอนที่ 3: สร้างเอกสาร PDF และกำหนดองค์ประกอบที่มีโครงสร้าง

ใช้โค้ดต่อไปนี้เพื่อสร้างเอกสาร PDF และกำหนดองค์ประกอบที่มีโครงสร้าง:

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

โค้ดนี้จะสร้างเอกสาร PDF เปล่าและเพิ่มองค์ประกอบที่มีโครงสร้าง เช่น ย่อหน้าและช่วง โดยองค์ประกอบโครงสร้างแต่ละองค์ประกอบจะถูกสร้างขึ้นโดยใช้เมธอดที่ Aspose.PDF จัดเตรียมไว้ให้

## ขั้นตอนที่ 4: บันทึกเอกสาร PDF

ใช้โค้ดต่อไปนี้เพื่อบันทึกเอกสาร PDF:

```csharp
document. Save(outFile);
```

รหัสนี้จะบันทึกเอกสาร PDF ที่มีองค์ประกอบที่มีโครงสร้างลงในไฟล์ที่ระบุ

### ตัวอย่างโค้ดต้นฉบับสำหรับการเพิ่มองค์ประกอบโครงสร้างลงในองค์ประกอบโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// การสร้างเอกสารและการรับเนื้อหา PDF ที่ถูกแท็ก
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// การตั้งชื่อเรื่องและภาษาธรรมชาติของเอกสาร
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// การรับองค์ประกอบโครงสร้างราก (องค์ประกอบโครงสร้างเอกสาร)
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
// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(outFile);
// การตรวจสอบความสอดคล้องของ PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการเพิ่มองค์ประกอบโครงสร้างให้กับองค์ประกอบในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET การใช้คุณลักษณะโครงสร้างเนื้อหาที่ทำเครื่องหมายไว้ของ Aspose.PDF ช่วยให้คุณสร้างโครงสร้างแบบลำดับชั้นในเอกสาร PDF ของคุณได้ ซึ่งจะทำให้การจัดการและการนำทางเนื้อหาต่างๆ ง่ายขึ้น

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของการเพิ่มองค์ประกอบโครงสร้างให้กับองค์ประกอบในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

A: การเพิ่มองค์ประกอบโครงสร้างให้กับองค์ประกอบในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ช่วยให้คุณสามารถสร้างโครงสร้างแบบลำดับชั้นภายในเนื้อหาของเอกสารได้ โครงสร้างแบบลำดับชั้นนี้ช่วยปรับปรุงการจัดระเบียบและการนำทางของเนื้อหา ทำให้จัดการและเข้าถึงองค์ประกอบเฉพาะต่างๆ ได้ง่ายขึ้น

#### ถาม: ไลบรารี Aspose.PDF ช่วยในการเพิ่มองค์ประกอบโครงสร้างลงในเอกสาร PDF ได้อย่างไร

A: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งให้ความสามารถในการสร้าง จัดการ และแปลงเอกสาร PDF ด้วยโปรแกรม ในบทช่วยสอนนี้ ฟีเจอร์โครงสร้างเนื้อหาที่ทำเครื่องหมายไว้ของไลบรารีจะถูกนำมาใช้เพื่อสร้างและผนวกองค์ประกอบโครงสร้างเข้ากับเนื้อหาของเอกสาร PDF

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการเพิ่มองค์ประกอบโครงสร้างลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ก: ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio พร้อมกับ .NET framework และมีการอ้างอิงไลบรารี Aspose.PDF สำหรับ .NET ในโครงการของคุณ

#### ถาม: โค้ด C# ที่ให้มาสร้างและผนวกองค์ประกอบโครงสร้างลงในเนื้อหาของเอกสาร PDF ได้อย่างไร

A: โค้ดนี้แสดงวิธีการสร้างเอกสาร PDF กำหนดองค์ประกอบโครงสร้างราก และผนวกองค์ประกอบโครงสร้างต่างๆ เช่น ย่อหน้าและช่วงต่างๆ ลงไป องค์ประกอบโครงสร้างแต่ละองค์ประกอบจะถูกสร้างขึ้นโดยใช้เมธอดที่ Aspose.PDF จัดเตรียมไว้ให้ ช่วยให้คุณสร้างโครงสร้างแบบลำดับชั้นได้

#### ถาม: ฉันสามารถปรับแต่งประเภทขององค์ประกอบโครงสร้างที่ฉันผนวกลงในเอกสาร PDF ได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งประเภทขององค์ประกอบโครงสร้างได้โดยสำรวจวิธีการต่างๆ ที่ไลบรารี Aspose.PDF จัดเตรียมไว้ โค้ดจะแสดงย่อหน้าและช่วงต่างๆ เป็นตัวอย่าง แต่คุณสามารถสร้างและผนวกองค์ประกอบโครงสร้างประเภทอื่นๆ ได้ตามต้องการ

#### ถาม: ฉันจะกำหนดความสัมพันธ์ลำดับชั้นระหว่างองค์ประกอบโครงสร้างที่เพิ่มเข้ามาได้อย่างไร

 A: ความสัมพันธ์ตามลำดับชั้นระหว่างองค์ประกอบโครงสร้างถูกกำหนดโดยลำดับที่คุณผนวกองค์ประกอบเหล่านี้เข้ากับองค์ประกอบหลัก ในโค้ด ความสัมพันธ์ระหว่างผู้ปกครองและลูกจะถูกสร้างขึ้นโดยใช้`AppendChild` วิธี.

#### ถาม: ประโยชน์ในการสร้างโครงสร้างลำดับชั้นในเอกสาร PDF มีอะไรบ้าง

A: การสร้างโครงสร้างแบบลำดับชั้นในเอกสาร PDF จะช่วยให้เข้าถึง นำทาง และจัดระเบียบเอกสารได้ดีขึ้น นอกจากนี้ เทคโนโลยีช่วยเหลือยังช่วยให้ตีความและถ่ายทอดเนื้อหาของเอกสารได้ดีขึ้น ทำให้ผู้พิการสามารถใช้งานได้ง่ายขึ้น

#### ถาม: ฉันจะตรวจสอบการปฏิบัติตาม PDF/UA ได้อย่างไร หลังจากเพิ่มองค์ประกอบโครงสร้าง

 A: รหัสที่ให้ไว้ในบทช่วยสอนสาธิตวิธีการตรวจสอบความสอดคล้องกับ PDF/UA โดยใช้`Validate` วิธีการ โดยการตรวจสอบเอกสารตามมาตรฐาน PDF/UA คุณสามารถมั่นใจได้ว่าองค์ประกอบโครงสร้างที่เพิ่มเข้ามานั้นสอดคล้องกับแนวทางการเข้าถึง

#### ถาม: ฉันสามารถใช้แนวทางนี้ในการเพิ่มองค์ประกอบโครงสร้างให้กับเอกสาร PDF ที่มีอยู่ได้หรือไม่

A: ใช่ คุณสามารถปรับเปลี่ยนแนวทางที่ให้มาเพื่อเพิ่มองค์ประกอบโครงสร้างลงในเอกสาร PDF ที่มีอยู่ได้ แทนที่จะสร้างเอกสารใหม่ คุณจะโหลดเอกสารที่มีอยู่โดยใช้ Aspose.PDF จากนั้นทำตามขั้นตอนที่คล้ายกันเพื่อผนวกองค์ประกอบโครงสร้าง