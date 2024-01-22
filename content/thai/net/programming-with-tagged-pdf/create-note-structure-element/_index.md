---
title: สร้างองค์ประกอบโครงสร้างหมายเหตุ
linktitle: สร้างองค์ประกอบโครงสร้างหมายเหตุ
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการสร้างรายการบันทึกที่มีโครงสร้างในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 30
url: /th/net/programming-with-tagged-pdf/create-note-structure-element/
---
ในบทช่วยสอนนี้ เราจะให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีสร้างองค์ประกอบโครงสร้างบันทึกย่อในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET Aspose.PDF เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณสามารถสร้าง จัดการ และแปลงเอกสาร PDF โดยทางโปรแกรม การใช้คุณสมบัติโครงสร้างเนื้อหาที่ทำเครื่องหมายไว้ของ Aspose.PDF คุณสามารถเพิ่มบันทึกย่อที่มีโครงสร้างลงในเอกสาร PDF ของคุณได้

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

## ขั้นตอนที่ 3: การสร้างเอกสาร PDF และองค์ประกอบที่มีโครงสร้างหมายเหตุ

ใช้รหัสต่อไปนี้เพื่อสร้างเอกสาร PDF และเพิ่มองค์ประกอบที่มีโครงสร้างบันทึกย่อ:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

รหัสนี้จะสร้างเอกสาร PDF เปล่าและเพิ่มองค์ประกอบบันทึกที่มีโครงสร้างลงในย่อหน้า บันทึกแต่ละรายการจะถูกสร้างขึ้นโดยใช้วิธีการของ Aspose.PDF

## ขั้นตอนที่ 4: บันทึกเอกสาร PDF

ใช้รหัสต่อไปนี้เพื่อบันทึกเอกสาร PDF:

```csharp
document. Save(outFile);
```

รหัสนี้จะบันทึกเอกสาร PDF ที่มีองค์ประกอบที่มีโครงสร้างบันทึกย่อไปยังไฟล์ที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับองค์ประกอบโครงสร้างบันทึกย่อโดยใช้ Aspose.PDF สำหรับ .NET 

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// สร้างเอกสาร PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// เพิ่มองค์ประกอบย่อหน้า
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// เพิ่ม NoteElement
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// เพิ่ม NoteElement
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// เพิ่ม NoteElement
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// ต้องโยนข้อยกเว้น - Aspose.Pdf.Tagged.TaggedException : องค์ประกอบโครงสร้างที่มี ID='note_002' มีอยู่แล้ว
//note3.SetId("note_002");
// เอกสารผลลัพธ์ไม่สอดคล้องกับ PDF/UA If ClearId() ที่ใช้สำหรับองค์ประกอบโครงสร้างหมายเหตุ
//note3.ClearId();
// บันทึกเอกสาร PDF ที่ติดแท็ก
document.Save(outFile);
// ตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีสร้างองค์ประกอบโครงสร้างบันทึกย่อในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET องค์ประกอบบันทึกที่มีโครงสร้างช่วยให้คุณสามารถเพิ่มข้อมูลที่มีโครงสร้างเพิ่มเติมลงในเอกสาร PDF ของคุณได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของการสร้างองค์ประกอบโครงสร้างบันทึกย่อในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: การสร้างองค์ประกอบโครงสร้างบันทึกย่อในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ช่วยให้คุณสามารถเพิ่มบันทึกย่อที่มีโครงสร้างลงในเนื้อหาของเอกสารได้ หมายเหตุเหล่านี้สามารถให้บริบท คำอธิบาย หรือการอ้างอิงเพิ่มเติมไปยังส่วนใดส่วนหนึ่งของเนื้อหาได้

#### ถาม: ไลบรารี Aspose.PDF ช่วยในการสร้างองค์ประกอบโครงสร้างบันทึกย่อในเอกสาร PDF ได้อย่างไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งมีฟังก์ชันสำหรับการสร้าง จัดการ และแปลงเอกสาร PDF โดยทางโปรแกรม ในบทช่วยสอนนี้ คุณลักษณะโครงสร้างเนื้อหาที่ทำเครื่องหมายไว้ของไลบรารีจะใช้เพื่อสร้างองค์ประกอบบันทึกย่อที่มีโครงสร้างภายในเนื้อหาของเอกสาร PDF

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการสร้างองค์ประกอบโครงสร้างบันทึกย่อในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET มีอะไรบ้าง

ตอบ: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio ด้วยเฟรมเวิร์ก .NET และมีไลบรารี Aspose.PDF สำหรับ .NET ที่อ้างอิงในโปรเจ็กต์ของคุณ

#### ถาม: รหัส C# ที่ให้มาสร้างองค์ประกอบโครงสร้างบันทึกย่อในเนื้อหาของเอกสาร PDF ได้อย่างไร

ตอบ: โค้ดสาธิตวิธีการสร้างเอกสาร PDF กำหนดองค์ประกอบที่มีโครงสร้างบันทึกย่อ และเพิ่มลงในย่อหน้า บันทึกย่อแต่ละรายการถูกสร้างขึ้นโดยใช้วิธีการของ Aspose.PDF ซึ่งช่วยให้คุณสามารถรวมบันทึกที่มีโครงสร้างไว้ในเนื้อหาได้

#### ถาม: ฉันสามารถปรับแต่งเนื้อหาและคุณสมบัติขององค์ประกอบโครงสร้างบันทึกย่อที่ฉันสร้างได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งเนื้อหาและคุณสมบัติขององค์ประกอบโครงสร้างบันทึกย่อได้โดยใช้วิธีการและคุณสมบัติที่ได้รับจากไลบรารี Aspose.PDF โค้ดจะแสดงวิธีตั้งค่าข้อความและ ID ขององค์ประกอบโน้ต แต่คุณสามารถปรับแต่งเพิ่มเติมได้ตามต้องการ

#### ถาม: ความสัมพันธ์แบบลำดับชั้นถูกสร้างขึ้นระหว่างองค์ประกอบโครงสร้างบันทึกย่อและเนื้อหาของเอกสารอย่างไร

 ตอบ: ความสัมพันธ์แบบลำดับชั้นถูกสร้างขึ้นโดยการเพิ่มองค์ประกอบโครงสร้างบันทึกย่อเป็นรายการย่อยขององค์ประกอบที่มีโครงสร้างอื่นๆ เช่น ย่อหน้า ในโค้ด องค์ประกอบบันทึกย่อจะถูกผนวกเข้ากับองค์ประกอบย่อหน้าโดยใช้`AppendChild` วิธี.

#### ถาม: ฉันสามารถกำหนด ID เฉพาะให้กับองค์ประกอบโครงสร้างบันทึกได้หรือไม่

ตอบ: ได้ คุณสามารถกำหนด ID ที่ไม่ซ้ำกันเพื่อบันทึกองค์ประกอบโครงสร้างได้โดยใช้`SetId` วิธี. รหัสนี้สาธิตวิธีการตั้งค่า ID ขององค์ประกอบบันทึกย่อให้เป็นค่าที่ไม่ซ้ำ

#### ถาม: จะเกิดอะไรขึ้นหากฉันพยายามกำหนด ID ที่ซ้ำกันให้กับองค์ประกอบโครงสร้างบันทึกย่อ

ตอบ: การพยายามกำหนด ID ที่ซ้ำกันให้กับองค์ประกอบโครงสร้างบันทึกจะส่งผลให้เกิดข้อยกเว้น รหัสที่ให้ไว้ในบทช่วยสอนประกอบด้วยความคิดเห็นที่อธิบายสถานการณ์นี้

#### ถาม: ฉันจะมั่นใจได้อย่างไรว่าสอดคล้องกับ PDF/UA เมื่อสร้างองค์ประกอบโครงสร้างบันทึก

 ตอบ: รหัสที่ให้ไว้ในบทช่วยสอนสาธิตวิธีการตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA โดยใช้`Validate` วิธี. ด้วยการตรวจสอบความถูกต้องของเอกสารตามมาตรฐาน PDF/UA คุณสามารถมั่นใจได้ว่าองค์ประกอบโครงสร้างบันทึกย่อที่เพิ่มนั้นเป็นไปตามแนวทางการเข้าถึง

#### ถาม: ฉันสามารถใช้แนวทางนี้เพื่อเพิ่มองค์ประกอบโครงสร้างบันทึกย่อลงในเอกสาร PDF ที่มีอยู่ได้หรือไม่

ตอบ: ได้ คุณสามารถแก้ไขแนวทางที่ให้มาเพื่อเพิ่มองค์ประกอบโครงสร้างบันทึกลงในเอกสาร PDF ที่มีอยู่ได้ แทนที่จะสร้างเอกสารใหม่ คุณจะโหลดเอกสารที่มีอยู่โดยใช้ Aspose.PDF จากนั้นทำตามขั้นตอนที่คล้ายกันเพื่อผนวกองค์ประกอบบันทึกย่อ
