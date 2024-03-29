---
title: ลบบุ๊กมาร์กทั้งหมดในไฟล์ PDF
linktitle: ลบบุ๊กมาร์กทั้งหมดในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: ลบบุ๊กมาร์กทั้งหมดในไฟล์ PDF ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 30
url: /th/net/programming-with-bookmarks/delete-all-bookmarks/
---
# ลบบุ๊กมาร์กทั้งหมดด้วย Aspose.PDF สำหรับ .NET

การลบบุ๊กมาร์กในไฟล์ PDF อาจจำเป็นในบางกรณี ด้วย Aspose.PDF สำหรับ .NET คุณสามารถลบบุ๊กมาร์กทั้งหมดได้อย่างง่ายดายโดยทำตามซอร์สโค้ดต่อไปนี้:

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ก่อนที่คุณจะเริ่มต้น คุณต้องนำเข้าไลบรารีที่จำเป็นสำหรับโปรเจ็กต์ C# ของคุณ นี่คือคำสั่งการนำเข้าที่จำเป็น:

```csharp
using Aspose.Pdf;
```

## ขั้นตอนที่ 2: กำหนดเส้นทางไปยังโฟลเดอร์เอกสาร

 ในขั้นตอนนี้ คุณจะต้องระบุเส้นทางไปยังโฟลเดอร์ที่มีไฟล์ PDF ที่คุณต้องการลบบุ๊กมาร์ก แทนที่`"YOUR DOCUMENT DIRECTORY"`ในรหัสต่อไปนี้พร้อมเส้นทางจริงไปยังโฟลเดอร์เอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 3: เปิดเอกสาร PDF

ตอนนี้เรากำลังจะเปิดเอกสาร PDF ที่เราต้องการลบบุ๊กมาร์กโดยใช้รหัสต่อไปนี้:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

## ขั้นตอนที่ 4: ลบบุ๊กมาร์กทั้งหมด

 ในขั้นตอนนี้ เราจะลบบุ๊กมาร์กทั้งหมดออกจากเอกสารโดยใช้`Delete` วิธีการของ`Outlines` คุณสมบัติ. นี่คือรหัสที่เกี่ยวข้อง:

```csharp
pdfDocument.Outlines.Delete();
```

## ขั้นตอนที่ 5: บันทึกไฟล์ที่อัพเดต

 สุดท้าย เราจะบันทึกไฟล์ PDF ที่อัปเดตโดยใช้นามสกุลไฟล์`Save` วิธีการของ`pdfDocument` วัตถุ. นี่คือรหัสที่เกี่ยวข้อง:

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับการลบบุ๊กมาร์กทั้งหมดโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
// ลบบุ๊กมาร์กทั้งหมด
pdfDocument.Outlines.Delete();
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
// บันทึกไฟล์ที่อัพเดต
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll bookmarks deleted successfully.\nFile saved at " + dataDir);
```

## บทสรุป

ขอแสดงความยินดี! ตอนนี้ คุณมีคำแนะนำทีละขั้นตอนในการลบบุ๊กมาร์กทั้งหมดด้วย Aspose.PDF สำหรับ .NET คุณสามารถใช้รหัสนี้เพื่อล้างเอกสาร PDF ของคุณโดยการลบบุ๊กมาร์กที่มีอยู่ทั้งหมด

อย่าลืมตรวจสอบเอกสารอย่างเป็นทางการของ Aspose.PDF สำหรับข้อมูลเพิ่มเติมเกี่ยวกับคุณสมบัติการจัดการบุ๊กมาร์กขั้นสูง

### คำถามที่พบบ่อยสำหรับการลบบุ๊กมาร์กทั้งหมดในไฟล์ PDF

#### ถาม: บุ๊กมาร์กในไฟล์ PDF คืออะไร

ตอบ: บุ๊กมาร์กในไฟล์ PDF เป็นเครื่องมือช่วยนำทางที่ช่วยให้ผู้ใช้สามารถข้ามไปยังส่วนหรือหน้าเฉพาะภายในเอกสารได้อย่างรวดเร็ว ช่วยจัดระเบียบและปรับปรุงประสบการณ์ผู้ใช้เมื่อนำทางผ่านเนื้อหาที่มีความยาว

#### ถาม: เหตุใดฉันจึงต้องลบบุ๊กมาร์กทั้งหมดออกจากไฟล์ PDF

ตอบ: อาจมีกรณีที่คุณต้องการลบบุ๊กมาร์กทั้งหมดออกจากเอกสาร PDF เพื่อทำให้การนำทางง่ายขึ้น จัดระเบียบโครงสร้างใหม่ หรือจัดเตรียมเพื่อวัตถุประสงค์เฉพาะที่ไม่จำเป็นต้องใช้บุ๊กมาร์ก

#### ถาม: ฉันจะนำเข้าไลบรารีที่จำเป็นสำหรับโปรเจ็กต์ C# ของฉันได้อย่างไร

ตอบ: หากต้องการนำเข้าไลบรารีที่จำเป็นสำหรับโปรเจ็กต์ C# ของคุณ คุณสามารถใช้คำสั่งการนำเข้าต่อไปนี้:

```csharp
using Aspose.Pdf;
```

ไลบรารีนี้มีคลาสและวิธีการที่จำเป็นในการทำงานกับเอกสาร PDF

#### ถาม: ฉันจะระบุเส้นทางไปยังโฟลเดอร์เอกสารได้อย่างไร

 ตอบ: ในซอร์สโค้ดที่ให้มา คุณจะต้องแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังโฟลเดอร์ที่มีไฟล์ PDF ที่คุณต้องการลบบุ๊กมาร์ก เพื่อให้แน่ใจว่าโค้ดสามารถค้นหาไฟล์ PDF เป้าหมายได้

#### ถาม: ฉันจะเปิดเอกสาร PDF เพื่อลบบุ๊กมาร์กได้อย่างไร

ตอบ: หากต้องการเปิดเอกสาร PDF เพื่อลบบุ๊กมาร์ก ให้ใช้รหัสต่อไปนี้:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

 แทนที่`"DeleteAllBookmarks.pdf"` ด้วยชื่อไฟล์จริง

#### ถาม: ฉันจะลบบุ๊กมาร์กทั้งหมดออกจากเอกสาร PDF ได้อย่างไร

 ตอบ: หากต้องการลบบุ๊กมาร์กทั้งหมดออกจากเอกสาร PDF ให้ใช้`Delete` วิธีการของ`Outlines` คุณสมบัติ:

```csharp
pdfDocument.Outlines.Delete();
```

#### ถาม: จะเกิดอะไรขึ้นกับเนื้อหาที่เหลือเมื่อบุ๊กมาร์กถูกลบ

ตอบ: การลบบุ๊กมาร์กจะไม่ส่งผลต่อเนื้อหาหรือเค้าโครงของเอกสาร PDF เฉพาะบุ๊กมาร์กการนำทางเท่านั้นที่จะลบออก เหลือเนื้อหาจริงไว้ครบถ้วน

#### ถาม: ฉันจะบันทึกไฟล์ PDF ที่อัปเดตหลังจากลบบุ๊กมาร์กได้อย่างไร

ตอบ: หากต้องการบันทึกไฟล์ PDF ที่อัปเดตหลังจากลบบุ๊กมาร์กแล้ว ให้ใช้รหัสต่อไปนี้:

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

#### ถาม: ฉันสามารถเลือกที่จะลบบุ๊กมาร์กเฉพาะแทนที่จะลบทั้งหมดได้หรือไม่

ตอบ: ได้ คุณสามารถเลือกลบบุ๊กมาร์กที่ต้องการได้โดยการกำหนดเป้าหมายโดยใช้ดัชนีหรือคุณสมบัติอื่นๆ ซอร์สโค้ดที่ให้มาจะสาธิตวิธีการลบบุ๊กมาร์กทั้งหมด แต่คุณสามารถแก้ไขได้เพื่อให้เหมาะกับความต้องการของคุณ

#### ถาม: มีข้อควรระวังใดๆ ที่ฉันควรทำก่อนที่จะลบบุ๊กมาร์กหรือไม่

ตอบ: ก่อนที่จะลบบุ๊กมาร์ก โปรดตรวจสอบเอกสารเพื่อให้แน่ใจว่าการลบบุ๊กมาร์กจะไม่ส่งผลกระทบต่อการใช้งานหรือการนำทางของเอกสาร พิจารณาสำรองข้อมูลเอกสารต้นฉบับก่อนดำเนินการต่อ