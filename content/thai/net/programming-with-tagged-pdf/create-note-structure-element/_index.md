---
title: สร้างองค์ประกอบโครงสร้างบันทึก
linktitle: สร้างองค์ประกอบโครงสร้างบันทึก
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: คู่มือทีละขั้นตอนในการสร้างรายการบันทึกที่มีโครงสร้างในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 30
url: /th/net/programming-with-tagged-pdf/create-note-structure-element/
---
ในบทช่วยสอนนี้ เราจะให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการสร้างองค์ประกอบโครงสร้างหมายเหตุในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET Aspose.PDF เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้คุณสร้าง จัดการ และแปลงเอกสาร PDF ได้ด้วยโปรแกรม การใช้คุณสมบัติโครงสร้างเนื้อหาที่ทำเครื่องหมายไว้ของ Aspose.PDF ช่วยให้คุณสามารถเพิ่มหมายเหตุที่มีโครงสร้างลงในเอกสาร PDF ของคุณได้

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

## ขั้นตอนที่ 3: การสร้างเอกสาร PDF และองค์ประกอบโครงสร้างบันทึก

ใช้โค้ดต่อไปนี้เพื่อสร้างเอกสาร PDF และเพิ่มองค์ประกอบโครงสร้างบันทึก:

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

โค้ดนี้จะสร้างเอกสาร PDF เปล่าและเพิ่มองค์ประกอบบันทึกย่อแบบมีโครงสร้างลงในย่อหน้า บันทึกย่อแต่ละรายการจะถูกสร้างขึ้นโดยใช้เมธอดที่ Aspose.PDF จัดเตรียมไว้

## ขั้นตอนที่ 4: บันทึกเอกสาร PDF

ใช้โค้ดต่อไปนี้เพื่อบันทึกเอกสาร PDF:

```csharp
document. Save(outFile);
```

รหัสนี้จะบันทึกเอกสาร PDF ที่มีองค์ประกอบโครงสร้างหมายเหตุลงในไฟล์ที่ระบุ

### ตัวอย่างโค้ดต้นฉบับสำหรับการสร้างองค์ประกอบโครงสร้างบันทึกย่อโดยใช้ Aspose.PDF สำหรับ .NET 

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
// เพิ่มองค์ประกอบหมายเหตุ
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// เพิ่มองค์ประกอบหมายเหตุ
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// เพิ่มองค์ประกอบหมายเหตุ
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// ต้องโยนข้อยกเว้น - Aspose.Pdf.Tagged.TaggedException: องค์ประกอบโครงสร้างที่มี ID='note_002' มีอยู่แล้ว
//note3.SetId("note_002");
// เอกสารผลลัพธ์ไม่เป็นไปตาม PDF/UA หากใช้ ClearId() สำหรับองค์ประกอบโครงสร้างหมายเหตุ
//note3.ClearId();
// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(outFile);
// การตรวจสอบความสอดคล้องของ PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีสร้างองค์ประกอบโครงสร้างหมายเหตุในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET องค์ประกอบหมายเหตุที่มีโครงสร้างช่วยให้คุณสามารถเพิ่มข้อมูลที่มีโครงสร้างเพิ่มเติมลงในเอกสาร PDF ของคุณได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ในการสร้างองค์ประกอบโครงสร้างบันทึกย่อในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

A: การสร้างองค์ประกอบโครงสร้างหมายเหตุในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ช่วยให้คุณสามารถเพิ่มหมายเหตุที่มีโครงสร้างลงในเนื้อหาของเอกสารได้ หมายเหตุเหล่านี้สามารถให้บริบท คำอธิบาย หรือการอ้างอิงเพิ่มเติมสำหรับส่วนเฉพาะของเนื้อหาได้

#### ถาม: ไลบรารี Aspose.PDF ช่วยสร้างองค์ประกอบโครงสร้างบันทึกในเอกสาร PDF ได้อย่างไร

A: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งให้ฟังก์ชันต่างๆ สำหรับการสร้าง จัดการ และแปลงเอกสาร PDF ด้วยโปรแกรม ในบทช่วยสอนนี้ คุณลักษณะโครงสร้างเนื้อหาที่ทำเครื่องหมายไว้ของไลบรารีจะถูกใช้เพื่อสร้างองค์ประกอบบันทึกที่มีโครงสร้างภายในเนื้อหาของเอกสาร PDF

#### ถาม: ข้อกำหนดเบื้องต้นในการสร้างองค์ประกอบโครงสร้างบันทึกในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET มีอะไรบ้าง

ก: ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio พร้อมกับ .NET framework และมีการอ้างอิงไลบรารี Aspose.PDF สำหรับ .NET ในโครงการของคุณ

#### ถาม: โค้ด C# ที่ให้มาสร้างองค์ประกอบโครงสร้างบันทึกในเนื้อหาของเอกสาร PDF ได้อย่างไร

A: โค้ดนี้แสดงวิธีการสร้างเอกสาร PDF กำหนดองค์ประกอบที่มีโครงสร้างหมายเหตุ และเพิ่มองค์ประกอบเหล่านี้ลงในย่อหน้า โดยแต่ละหมายเหตุจะถูกสร้างขึ้นโดยใช้เมธอดที่ Aspose.PDF จัดเตรียมไว้ ซึ่งช่วยให้คุณสามารถรวมหมายเหตุที่มีโครงสร้างเข้ากับเนื้อหาได้

#### ถาม: ฉันสามารถปรับแต่งเนื้อหาและคุณสมบัติขององค์ประกอบโครงสร้างโน้ตที่ฉันสร้างได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งเนื้อหาและคุณสมบัติขององค์ประกอบโครงสร้างโน้ตได้โดยใช้เมธอดและคุณสมบัติที่จัดเตรียมไว้โดยไลบรารี Aspose.PDF โค้ดนี้แสดงวิธีการตั้งค่าข้อความและ ID ขององค์ประกอบโน้ต แต่คุณสามารถปรับแต่งเพิ่มเติมได้ตามต้องการ

#### ถาม: ความสัมพันธ์ลำดับชั้นระหว่างองค์ประกอบโครงสร้างบันทึกและเนื้อหาของเอกสารได้รับการจัดทำขึ้นอย่างไร

 A: ความสัมพันธ์ตามลำดับชั้นจะถูกสร้างขึ้นโดยการเพิ่มองค์ประกอบโครงสร้างโน้ตเป็นองค์ประกอบย่อยขององค์ประกอบโครงสร้างอื่นๆ เช่น ย่อหน้า ในโค้ด องค์ประกอบโน้ตจะถูกผนวกเข้ากับองค์ประกอบย่อหน้าโดยใช้`AppendChild` วิธี.

#### ถาม: ฉันสามารถกำหนด ID เฉพาะให้กับองค์ประกอบโครงสร้างหมายเหตุได้หรือไม่

A: ใช่ คุณสามารถกำหนด ID เฉพาะให้กับองค์ประกอบโครงสร้างหมายเหตุได้โดยใช้`SetId` วิธีการ รหัสนี้สาธิตวิธีการตั้งค่า ID ขององค์ประกอบบันทึกให้เป็นค่าเฉพาะ

#### ถาม: จะเกิดอะไรขึ้นหากฉันพยายามกำหนด ID ซ้ำให้กับองค์ประกอบโครงสร้างบันทึกย่อ

A: การพยายามกำหนด ID ซ้ำซ้อนให้กับองค์ประกอบโครงสร้างโน้ตจะส่งผลให้เกิดข้อยกเว้น โค้ดที่ให้ไว้ในบทช่วยสอนประกอบด้วยคำอธิบายประกอบเพื่ออธิบายสถานการณ์นี้

#### ถาม: ฉันจะมั่นใจได้อย่างไรว่าเป็นไปตามมาตรฐาน PDF/UA เมื่อสร้างองค์ประกอบโครงสร้างบันทึกย่อ

 A: รหัสที่ให้ไว้ในบทช่วยสอนสาธิตวิธีการตรวจสอบความสอดคล้องกับ PDF/UA โดยใช้`Validate` วิธีการ โดยการตรวจสอบเอกสารตามมาตรฐาน PDF/UA คุณสามารถมั่นใจได้ว่าองค์ประกอบโครงสร้างบันทึกที่เพิ่มเข้ามานั้นเป็นไปตามแนวทางการเข้าถึง

#### ถาม: ฉันสามารถใช้แนวทางนี้ในการเพิ่มองค์ประกอบโครงสร้างบันทึกลงในเอกสาร PDF ที่มีอยู่ได้หรือไม่

A: ใช่ คุณสามารถปรับเปลี่ยนแนวทางที่ให้มาเพื่อเพิ่มองค์ประกอบโครงสร้างบันทึกย่อลงในเอกสาร PDF ที่มีอยู่ได้ แทนที่จะสร้างเอกสารใหม่ คุณจะโหลดเอกสารที่มีอยู่โดยใช้ Aspose.PDF จากนั้นทำตามขั้นตอนที่คล้ายกันเพื่อผนวกองค์ประกอบบันทึกย่อ
