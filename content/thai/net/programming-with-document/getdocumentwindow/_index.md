---
title: รับหน้าต่างเอกสาร
linktitle: รับหน้าต่างเอกสาร
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีใช้ฟีเจอร์ GetDocumentWindow ของ Aspose.PDF สำหรับ .NET เพื่อดึงข้อมูลเกี่ยวกับคุณสมบัติหน้าต่างของเอกสาร PDF
type: docs
weight: 170
url: /th/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF สำหรับ .NET เป็นไลบรารีการจัดการ PDF ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และแปลงไฟล์ PDF ในแอปพลิเคชัน .NET ของตนได้ หนึ่งในคุณสมบัติที่นำเสนอโดยไลบรารีนี้คือความสามารถในการดึงข้อมูลเกี่ยวกับคุณสมบัติหน้าต่างของเอกสาร บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนการใช้งาน`GetDocumentWindow` คุณสมบัติของ Aspose.PDF สำหรับ .NET เพื่อดึงข้อมูลเกี่ยวกับคุณสมบัติหน้าต่างของเอกสาร PDF

## ขั้นตอนที่ 1: ติดตั้ง Aspose.PDF สำหรับ .NET

 หากต้องการใช้ Aspose.PDF สำหรับ .NET ในแอปพลิเคชัน .NET ของคุณ คุณต้องติดตั้งไลบรารีก่อน คุณสามารถดาวน์โหลดไลบรารีเวอร์ชันล่าสุดได้จาก[Aspose.PDF สำหรับหน้าดาวน์โหลด .NET](https://releases.aspose.com/pdf/net).

เมื่อคุณดาวน์โหลดไลบรารีแล้ว ให้แยกเนื้อหาของไฟล์ ZIP ไปยังโฟลเดอร์บนคอมพิวเตอร์ของคุณ จากนั้นคุณจะต้องเพิ่มการอ้างอิงถึง Aspose.PDF สำหรับ .NET DLL ในโปรเจ็กต์ .NET ของคุณ

## ขั้นตอนที่ 2: โหลดเอกสาร PDF

เมื่อคุณติดตั้ง Aspose.PDF สำหรับ .NET และเพิ่มการอ้างอิงไปยัง DLL ในโปรเจ็กต์ .NET ของคุณแล้ว คุณสามารถเริ่มใช้`GetDocumentWindow` คุณสมบัติในการดึงข้อมูลเกี่ยวกับคุณสมบัติหน้าต่างของเอกสาร PDF

ขั้นตอนแรกในการใช้คุณสมบัตินี้คือการโหลดเอกสาร PDF ที่คุณต้องการดึงข้อมูล เมื่อต้องการทำเช่นนี้ คุณสามารถใช้รหัสต่อไปนี้:

```csharp
// เส้นทางไปยังเอกสาร PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//เปิดเอกสาร PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 ในโค้ดข้างต้น ให้แทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่มีเอกสาร PDF ของคุณอยู่ รหัสนี้จะโหลดเอกสาร PDF ลงในไฟล์`Document` วัตถุซึ่งคุณสามารถใช้เพื่อดึงข้อมูลเกี่ยวกับคุณสมบัติหน้าต่างของเอกสารได้

## ขั้นตอนที่ 3: ดึงคุณสมบัติหน้าต่างของเอกสาร

หากต้องการดึงข้อมูลเกี่ยวกับคุณสมบัติหน้าต่างของเอกสาร PDF คุณสามารถใช้รหัสต่อไปนี้:

```csharp
// ดึงคุณสมบัติหน้าต่างของเอกสาร
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

ในโค้ดข้างต้น แต่ละบรรทัดจะดึงคุณสมบัติหน้าต่างที่แตกต่างกันของเอกสาร PDF และส่งออกไปยังคอนโซล คุณสามารถปรับแต่งโค้ดนี้เพื่อดึงข้อมูลเฉพาะคุณสมบัติที่คุณสนใจได้

### ตัวอย่างซอร์สโค้ดสำหรับรับหน้าต่างเอกสารของไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET 

 นี่คือซอร์สโค้ดแบบเต็มสำหรับการดึงคุณสมบัติหน้าต่างของเอกสาร PDF โดยใช้`GetDocumentWindow` คุณสมบัติของ Aspose.PDF สำหรับ .NET:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// รับคุณสมบัติของเอกสารที่แตกต่างกัน
// ตำแหน่งของหน้าต่างเอกสาร - ค่าเริ่มต้น: เท็จ
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// ลำดับการอ่านที่โดดเด่น กำหนดตำแหน่งของหน้า
// เมื่อแสดงแบบเคียงข้างกัน - ค่าเริ่มต้น: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// แถบชื่อเรื่องของหน้าต่างควรแสดงชื่อเอกสารหรือไม่
// หากเป็นเท็จ แถบหัวเรื่องจะแสดงชื่อไฟล์ PDF - ค่าเริ่มต้น: เท็จ
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// ว่าจะปรับขนาดหน้าต่างเอกสารให้พอดีกับขนาดของหรือไม่
// หน้าที่แสดงหน้าแรก - ค่าเริ่มต้น: เท็จ
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// ว่าจะซ่อนแถบเมนูของแอปพลิเคชันตัวแสดงหรือไม่ - ค่าเริ่มต้น: เท็จ
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//ว่าจะซ่อนแถบเครื่องมือของแอปพลิเคชันตัวแสดงหรือไม่ - ค่าเริ่มต้น: เท็จ
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// ว่าจะซ่อนองค์ประกอบ UI เช่นแถบเลื่อนหรือไม่
// และเหลือเพียงเนื้อหาของหน้าที่แสดง - ค่าเริ่มต้น: เท็จ
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// โหมดหน้าเอกสาร วิธีแสดงเอกสารเมื่อออกจากโหมดเต็มหน้าจอ
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// การจัดวางหน้ากระดาษ เช่น หน้าเดียว หนึ่งคอลัมน์
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// เอกสารควรแสดงอย่างไรเมื่อเปิด
// เช่น แสดงภาพขนาดย่อ, เต็มหน้าจอ, แสดงแผงไฟล์แนบ
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อดึงข้อมูลเกี่ยวกับคุณสมบัติหน้าต่างของเอกสาร PDF ด้วยการโหลดเอกสาร PDF และการเข้าถึงคุณสมบัติหน้าต่าง คุณสามารถรวบรวมข้อมูลเกี่ยวกับวิธีการแสดงเอกสารเมื่อเปิดในแอปพลิเคชันตัวแสดง Aspose.PDF สำหรับ .NET มอบชุดคุณลักษณะอันทรงพลังสำหรับการทำงานกับไฟล์ PDF โดยทางโปรแกรม ทำให้เป็นเครื่องมืออันมีค่าสำหรับการจัดการ PDF ในแอปพลิเคชัน .NET

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ในการเรียกคุณสมบัติหน้าต่างของเอกสาร PDF คืออะไร

ตอบ: การเรียกคุณสมบัติหน้าต่างของเอกสาร PDF ช่วยให้คุณสามารถรวบรวมข้อมูลเกี่ยวกับวิธีการแสดงเอกสาร PDF เมื่อเปิดในแอปพลิเคชันตัวแสดง คุณสมบัติเหล่านี้ควบคุมแง่มุมต่างๆ เช่น ตำแหน่งหน้าต่าง โหมดการแสดงผล และการมองเห็นองค์ประกอบ UI

#### ถาม: ฉันจะติดตั้ง Aspose.PDF สำหรับ .NET ในโปรเจ็กต์ .NET ของฉันได้อย่างไร

 ตอบ: หากต้องการติดตั้ง Aspose.PDF สำหรับ .NET คุณต้องดาวน์โหลดไลบรารีจากไฟล์[Aspose.PDF สำหรับหน้าดาวน์โหลด .NET](https://releases.aspose.com/pdf/net). หลังจากดาวน์โหลด ให้แยกเนื้อหาของไฟล์ ZIP และเพิ่มการอ้างอิงไปยัง Aspose.PDF สำหรับ .NET DLL ในโปรเจ็กต์ .NET ของคุณ

#### ถาม: ฉันสามารถปรับแต่งโค้ดเพื่อดึงคุณสมบัติหน้าต่างเฉพาะเจาะจงได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งโค้ดเพื่อดึงคุณสมบัติหน้าต่างเฉพาะได้โดยการใส่ความคิดเห็นในบรรทัดที่คุณไม่ต้องการ แต่ละบรรทัดในโค้ดสอดคล้องกับคุณสมบัติหน้าต่างเฉพาะ ดังนั้นคุณจึงสามารถรวมหรือยกเว้นคุณสมบัติตามความต้องการของคุณได้

#### ถาม: ฉันสามารถดึงคุณสมบัติหน้าต่างประเภทใดบ้างโดยใช้ Aspose.PDF สำหรับ .NET

ตอบ: เมื่อใช้ Aspose.PDF สำหรับ .NET คุณสามารถดึงคุณสมบัติหน้าต่างต่างๆ ของเอกสาร PDF ได้ รวมถึงการจัดกึ่งกลางหน้าต่าง การตั้งค่าเค้าโครงหน้า การควบคุมการแสดงแถบเครื่องมือและแถบเมนู และอื่นๆ