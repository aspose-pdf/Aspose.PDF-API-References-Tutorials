---
title: รับหน้าต่างเอกสาร
linktitle: รับหน้าต่างเอกสาร
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีใช้คุณลักษณะ GetDocumentWindow ของ Aspose.PDF สำหรับ .NET เพื่อรับข้อมูลเกี่ยวกับคุณสมบัติหน้าต่างเอกสาร PDF
type: docs
weight: 170
url: /th/net/programming-with-document/getdocumentwindow/
---
Aspose.PDF สำหรับ .NET เป็นไลบรารีการจัดการ PDF ที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และแปลงไฟล์ PDF ในแอปพลิเคชัน .NET ได้ หนึ่งในฟีเจอร์ที่ไลบรารีนี้นำเสนอคือความสามารถในการเรียกค้นข้อมูลเกี่ยวกับคุณสมบัติของหน้าต่างเอกสาร บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนต่างๆ ในการใช้`GetDocumentWindow` คุณลักษณะของ Aspose.PDF สำหรับ .NET ในการดึงข้อมูลเกี่ยวกับคุณสมบัติของหน้าต่างเอกสาร PDF

## ขั้นตอนที่ 1: ติดตั้ง Aspose.PDF สำหรับ .NET

 หากต้องการใช้ Aspose.PDF สำหรับ .NET ในแอปพลิเคชัน .NET คุณต้องติดตั้งไลบรารีก่อน คุณสามารถดาวน์โหลดไลบรารีเวอร์ชันล่าสุดได้จาก[หน้าดาวน์โหลด Aspose.PDF สำหรับ .NET](https://releases.aspose.com/pdf/net).

เมื่อคุณดาวน์โหลดไลบรารีแล้ว ให้แตกเนื้อหาของไฟล์ ZIP ไปยังโฟลเดอร์บนคอมพิวเตอร์ของคุณ จากนั้นคุณจะต้องเพิ่มการอ้างอิงไปยังไฟล์ Aspose.PDF สำหรับ DLL ของ .NET ในโปรเจ็กต์ .NET ของคุณ

## ขั้นตอนที่ 2: โหลดเอกสาร PDF

 เมื่อคุณติดตั้ง Aspose.PDF สำหรับ .NET และเพิ่มการอ้างอิงไปยัง DLL ในโครงการ .NET แล้ว คุณก็สามารถเริ่มใช้`GetDocumentWindow`คุณสมบัติในการรับข้อมูลเกี่ยวกับคุณสมบัติของหน้าต่างเอกสาร PDF

ขั้นตอนแรกในการใช้ฟีเจอร์นี้คือโหลดเอกสาร PDF ที่คุณต้องการดึงข้อมูล หากต้องการทำเช่นนี้ คุณสามารถใช้โค้ดต่อไปนี้:

```csharp
// เส้นทางไปยังเอกสาร PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// เปิดเอกสาร PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 ในโค้ดด้านบนให้แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางไปยังไดเรกทอรีที่เอกสาร PDF ของคุณตั้งอยู่ รหัสนี้จะโหลดเอกสาร PDF ลงใน`Document` วัตถุที่คุณสามารถใช้เรียกค้นข้อมูลเกี่ยวกับคุณสมบัติของหน้าต่างเอกสารได้

## ขั้นตอนที่ 3: ดึงข้อมูลคุณสมบัติของหน้าต่างเอกสาร

หากต้องการรับข้อมูลเกี่ยวกับคุณสมบัติหน้าต่างเอกสาร PDF คุณสามารถใช้โค้ดดังต่อไปนี้:

```csharp
// ดึงข้อมูลคุณสมบัติของหน้าต่างเอกสาร
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

ในโค้ดด้านบน แต่ละบรรทัดจะเรียกค้นคุณสมบัติหน้าต่างที่แตกต่างกันของเอกสาร PDF และส่งออกไปยังคอนโซล คุณสามารถปรับแต่งโค้ดนี้เพื่อเรียกค้นเฉพาะคุณสมบัติที่คุณสนใจเท่านั้น

### ตัวอย่างซอร์สโค้ดสำหรับรับหน้าต่างเอกสารของไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET 

 นี่คือซอร์สโค้ดฉบับเต็มสำหรับการดึงคุณสมบัติหน้าต่างเอกสาร PDF โดยใช้`GetDocumentWindow` คุณสมบัติของ Aspose.PDF สำหรับ .NET:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// รับคุณสมบัติเอกสารที่แตกต่างกัน
// ตำแหน่งของหน้าต่างเอกสาร - ค่าเริ่มต้น: เท็จ
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// ลำดับการอ่านที่โดดเด่น กำหนดตำแหน่งของหน้า
// เมื่อแสดงเคียงข้างกัน - ค่าเริ่มต้น: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// ว่าแถบชื่อเรื่องของหน้าต่างควรแสดงชื่อเอกสารหรือไม่
// หากเป็นเท็จ แถบชื่อเรื่องจะแสดงชื่อไฟล์ PDF - ค่าเริ่มต้น: เท็จ
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// จะปรับขนาดหน้าต่างเอกสารให้พอดีกับขนาด
// หน้าที่แสดงครั้งแรก - เริ่มต้น: เท็จ
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// ว่าจะซ่อนแถบเมนูของแอพพลิเคชั่นตัวแสดงหรือไม่ - ค่าเริ่มต้น: เท็จ
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

// ว่าจะซ่อนแถบเครื่องมือของแอพพลิเคชั่นดูหรือไม่ - ค่าเริ่มต้น: เท็จ
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// ไม่ว่าจะซ่อนองค์ประกอบ UI เช่นแถบเลื่อน
// และเหลือไว้เพียงแสดงเนื้อหาหน้า - ค่าเริ่มต้น: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

//โหมดหน้าเอกสาร วิธีการแสดงเอกสารเมื่อออกจากโหมดเต็มหน้าจอ
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// เค้าโครงหน้า คือ หน้าเดียว หนึ่งคอลัมน์
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// เอกสารควรแสดงอย่างไรเมื่อเปิด
// เช่น แสดงภาพขนาดย่อ เต็มจอ แสดงแผงแนบ
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อค้นหาข้อมูลเกี่ยวกับคุณสมบัติของหน้าต่างเอกสาร PDF คุณสามารถรวบรวมข้อมูลเกี่ยวกับวิธีการแสดงเอกสารเมื่อเปิดในแอปพลิเคชันสำหรับดูเอกสารได้โดยการโหลดเอกสาร PDF และเข้าถึงคุณสมบัติของหน้าต่าง Aspose.PDF สำหรับ .NET มอบชุดคุณลักษณะอันทรงพลังสำหรับการทำงานกับไฟล์ PDF ด้วยโปรแกรม ทำให้เป็นเครื่องมือที่มีประโยชน์สำหรับการจัดการ PDF ในแอปพลิเคชัน .NET

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ในการดึงคุณสมบัติหน้าต่างเอกสาร PDF คืออะไร

A: การเรียกค้นคุณสมบัติของหน้าต่างเอกสาร PDF ช่วยให้คุณรวบรวมข้อมูลเกี่ยวกับวิธีการแสดงเอกสาร PDF เมื่อเปิดในแอปพลิเคชันโปรแกรมดู คุณสมบัติเหล่านี้ควบคุมด้านต่างๆ เช่น ตำแหน่งของหน้าต่าง โหมดการแสดงผล และการมองเห็นองค์ประกอบ UI

#### ถาม: ฉันจะติดตั้ง Aspose.PDF สำหรับ .NET ในโครงการ .NET ของฉันได้อย่างไร

 A: หากต้องการติดตั้ง Aspose.PDF สำหรับ .NET คุณจะต้องดาวน์โหลดไลบรารีจาก[หน้าดาวน์โหลด Aspose.PDF สำหรับ .NET](https://releases.aspose.com/pdf/net)หลังจากดาวน์โหลดแล้ว ให้แตกเนื้อหาของไฟล์ ZIP และเพิ่มการอ้างอิงไปยัง Aspose.PDF สำหรับ .NET DLL ในโครงการ .NET ของคุณ

#### ถาม: ฉันสามารถปรับแต่งรหัสเพื่อดึงเฉพาะคุณสมบัติหน้าต่างที่เจาะจงได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งโค้ดเพื่อเรียกค้นคุณสมบัติหน้าต่างเฉพาะได้โดยการใส่เครื่องหมายแสดงความคิดเห็นในบรรทัดที่คุณไม่ต้องการ แต่ละบรรทัดในโค้ดจะสอดคล้องกับคุณสมบัติหน้าต่างเฉพาะ ดังนั้นคุณจึงรวมหรือไม่รวมคุณสมบัติต่างๆ ตามความต้องการของคุณได้

#### ถาม: ฉันสามารถเรียกคุณสมบัติหน้าต่างประเภทใดได้บ้างโดยใช้ Aspose.PDF สำหรับ .NET

A: การใช้ Aspose.PDF สำหรับ .NET ช่วยให้คุณสามารถเรียกค้นคุณสมบัติหน้าต่างต่างๆ ของเอกสาร PDF ได้ รวมถึงการจัดตำแหน่งหน้าต่างให้ตรงกลาง การตั้งค่าเค้าโครงหน้า การควบคุมการแสดงแถบเครื่องมือและแถบเมนู และอื่นๆ อีกมากมาย