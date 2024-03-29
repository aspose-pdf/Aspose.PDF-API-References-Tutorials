---
title: เพิ่มบุ๊กมาร์กในไฟล์ PDF
linktitle: เพิ่มบุ๊กมาร์กในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เพิ่มบุ๊กมาร์กในไฟล์ PDF ได้อย่างง่ายดายเพื่อปรับปรุงการนำทางด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-bookmarks/add-bookmark/
---
การเพิ่มบุ๊กมาร์กในไฟล์ PDF ช่วยให้การนำทางง่ายและรวดเร็ว ด้วย Aspose.PDF สำหรับ .NET คุณสามารถเพิ่มบุ๊กมาร์กในไฟล์ PDF ได้อย่างง่ายดายโดยทำตามซอร์สโค้ดต่อไปนี้:

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ก่อนที่คุณจะเริ่มต้น คุณต้องนำเข้าไลบรารีที่จำเป็นสำหรับโปรเจ็กต์ C# ของคุณ นี่คือคำสั่งการนำเข้าที่จำเป็น:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## ขั้นตอนที่ 2: กำหนดเส้นทางไปยังโฟลเดอร์เอกสาร

 ในขั้นตอนนี้ คุณจะต้องระบุเส้นทางไปยังโฟลเดอร์ที่มีไฟล์ PDF ที่คุณต้องการเพิ่มบุ๊กมาร์ก แทนที่`"YOUR DOCUMENT DIRECTORY"`ในรหัสต่อไปนี้พร้อมเส้นทางจริงไปยังโฟลเดอร์เอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 3: เปิดเอกสาร PDF

ตอนนี้เราจะเปิดเอกสาร PDF ที่เราต้องการเพิ่มบุ๊กมาร์กโดยใช้รหัสต่อไปนี้:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## ขั้นตอนที่ 4: สร้างวัตถุบุ๊กมาร์ก

 ในขั้นตอนนี้ เราจะสร้างวัตถุบุ๊กมาร์กโดยใช้`OutlineItemCollection` และตั้งค่าคุณสมบัติ เช่น ชื่อ คุณลักษณะตัวเอียง คุณลักษณะตัวหนา และการกระทำที่จะดำเนินการเมื่อคลิก นี่คือรหัสที่เกี่ยวข้อง:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## ขั้นตอนที่ 5: เพิ่มบุ๊กมาร์กลงในเอกสาร

 สุดท้าย เราเพิ่มบุ๊กมาร์กที่สร้างขึ้นลงในคอลเลกชันบุ๊กมาร์กของเอกสารโดยใช้`Add` วิธีการของ`Outlines` คุณสมบัติ. นี่คือรหัสที่เกี่ยวข้อง:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### ตัวอย่างซอร์สโค้ดสำหรับเพิ่มบุ๊กมาร์กโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// สร้างวัตถุบุ๊กมาร์ก
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// กำหนดหมายเลขหน้าปลายทาง
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// เพิ่มบุ๊กมาร์กในคอลเลกชันโครงร่างของเอกสาร
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// บันทึกเอาท์พุท
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## บทสรุป

ขอแสดงความยินดี! ตอนนี้ คุณมีคำแนะนำทีละขั้นตอนในการเพิ่มบุ๊กมาร์กโดยใช้ Aspose.PDF สำหรับ .NET แล้ว คุณสามารถใช้รหัสนี้เพื่อปรับปรุงการนำทางในเอกสาร PDF ของคุณโดยการเพิ่มบุ๊กมาร์กที่กำหนดเอง

อย่าลืมตรวจสอบเอกสารอย่างเป็นทางการของ Aspose.PDF สำหรับข้อมูลเพิ่มเติมเกี่ยวกับคุณสมบัติการจัดการบุ๊กมาร์กขั้นสูง


### คำถามที่พบบ่อยสำหรับการเพิ่มบุ๊กมาร์กในไฟล์ PDF

#### ถาม: บุ๊กมาร์กในไฟล์ PDF คืออะไร

ตอบ: บุ๊กมาร์กหรือที่เรียกว่าโครงร่างเป็นองค์ประกอบแบบโต้ตอบที่ให้การนำทางและโครงสร้างภายในเอกสาร PDF ช่วยให้ผู้ใช้สามารถข้ามไปยังส่วนหรือหน้าที่ต้องการได้อย่างรวดเร็ว

#### ถาม: เหตุใดฉันจึงต้องเพิ่มบุ๊กมาร์กลงในไฟล์ PDF

ตอบ: การเพิ่มบุ๊กมาร์กลงในไฟล์ PDF จะช่วยปรับปรุงประสบการณ์ผู้ใช้ และทำให้ผู้อ่านสามารถเลื่อนดูเนื้อหาของเอกสารได้ง่ายขึ้น บุ๊กมาร์กสามารถใช้เป็นสารบัญหรือช่วยให้เข้าถึงส่วนสำคัญได้อย่างรวดเร็ว

#### ถาม: ฉันจะนำเข้าไลบรารีที่จำเป็นสำหรับโปรเจ็กต์ C# ของฉันได้อย่างไร

ตอบ: หากต้องการนำเข้าไลบรารีที่จำเป็นสำหรับโครงการ C# ของคุณ ให้รวมคำสั่งการนำเข้าต่อไปนี้:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

คำสั่งเหล่านี้ช่วยให้คุณเข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการทำงานกับเอกสาร PDF และบุ๊กมาร์ก

#### ถาม: ฉันจะระบุเส้นทางไปยังโฟลเดอร์เอกสารได้อย่างไร

 ตอบ: แทนที่`"YOUR DOCUMENT DIRECTORY"` ในซอร์สโค้ดที่ให้มาพร้อมเส้นทางจริงไปยังโฟลเดอร์ที่มีไฟล์ PDF ที่คุณต้องการเพิ่มบุ๊กมาร์ก

#### ถาม: ฉันจะเปิดเอกสาร PDF เพื่อเพิ่มบุ๊กมาร์กได้อย่างไร

ตอบ: หากต้องการเปิดเอกสาร PDF เพื่อเพิ่มบุ๊กมาร์ก ให้ใช้รหัสต่อไปนี้:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 แทนที่`"AddBookmark.pdf"` ด้วยชื่อไฟล์จริง

#### ถาม: ฉันจะสร้างวัตถุบุ๊กมาร์กได้อย่างไร

 ตอบ: หากต้องการสร้างวัตถุบุ๊กมาร์ก ให้ใช้`OutlineItemCollection` ระดับ. ปรับแต่งคุณสมบัติต่างๆ เช่น ชื่อ รูปแบบตัวเอียง รูปแบบตัวหนา และการดำเนินการเมื่อคลิก

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

####  ถาม: จุดประสงค์ของ.`Action` property in a bookmark?

 ตอบ:`Action` คุณสมบัติระบุการกระทำที่จะดำเนินการเมื่อมีการคลิกบุ๊กมาร์ก ในตัวอย่างนี้ เราใช้`GoToAction`คลาสเพื่อนำทางไปยังหน้าเฉพาะ (หน้า 2 ในกรณีนี้)

#### ถาม: ฉันจะเพิ่มบุ๊กมาร์กลงในเอกสารได้อย่างไร

 ตอบ: ใช้`Add` วิธีการของ`Outlines` คุณสมบัติเพื่อเพิ่มบุ๊กมาร์กที่สร้างขึ้นไปยังคอลเลกชันบุ๊กมาร์กของเอกสาร

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### ถาม: ฉันสามารถเพิ่มบุ๊กมาร์กหลายรายการโดยใช้วิธีนี้ได้หรือไม่

ตอบ: ได้ คุณสามารถทำซ้ำขั้นตอนที่ 4 ถึง 8 เพื่อเพิ่มบุ๊กมาร์กหลายรายการลงในเอกสารได้ ปรับแต่งคุณสมบัติและการดำเนินการของบุ๊กมาร์กแต่ละรายการตามต้องการ

#### ถาม: ฉันจะบันทึกไฟล์ PDF ที่อัปเดตได้อย่างไร

 ตอบ: บันทึกไฟล์ PDF ที่อัปเดตโดยใช้นามสกุล`Save` วิธีการของ`pdfDocument` วัตถุ:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### ถาม: ฉันจะยืนยันได้อย่างไรว่าเพิ่มบุ๊กมาร์กแล้ว

ตอบ: เปิดไฟล์ PDF ที่สร้างขึ้นเพื่อตรวจสอบว่าได้เพิ่มบุ๊กมาร์กที่ระบุลงในเอกสารแล้ว

#### ถาม: มีการจำกัดจำนวนบุ๊กมาร์กที่ฉันสามารถเพิ่มได้หรือไม่

ตอบ: โดยทั่วไปไม่มีการจำกัดจำนวนบุ๊กมาร์กที่คุณสามารถเพิ่มได้ แต่ให้พิจารณาขนาดและความซับซ้อนของเอกสารเพื่อประสิทธิภาพสูงสุด

#### ถาม: ฉันสามารถปรับแต่งรูปลักษณ์ของบุ๊กมาร์กได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะบุ๊กมาร์ก สี สไตล์ และคุณลักษณะอื่นๆ เพิ่มเติมได้โดยใช้คุณสมบัติ Aspose.PDF