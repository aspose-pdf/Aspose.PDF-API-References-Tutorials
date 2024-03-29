---
title: ระบุหน้าเมื่อดู
linktitle: ระบุหน้าเมื่อดู
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีระบุหน้าเมื่อดู PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 110
url: /th/net/programming-with-links-and-actions/specify-page-when-viewing/
---
เรียนรู้วิธีระบุหน้าเมื่อดูไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนนี้

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วยโปรเจ็กต์ C# และการอ้างอิง Aspose.PDF ที่เหมาะสม

## ขั้นตอนที่ 2: กำลังโหลดไฟล์ PDF

กำหนดเส้นทางไดเรกทอรีของเอกสารของคุณและอัปโหลดไฟล์ PDF โดยใช้รหัสต่อไปนี้:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// โหลดไฟล์ PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## ขั้นตอนที่ 3: การระบุหน้าเป้าหมาย

รับอินสแตนซ์ของหน้าเป้าหมายโดยใช้รหัสต่อไปนี้:

```csharp
Page page2 = doc.Pages[2];
```

 คุณสามารถปรับดัชนีได้`[2]` เพื่อเลือกหน้าที่ต้องการ

## ขั้นตอนที่ 4: การกำหนดการตั้งค่าการซูม

สร้างตัวแปรเพื่อตั้งค่าปัจจัยการซูมหน้าเป้าหมาย:

```csharp
double zoom = 1;
```

คุณสามารถปรับค่าการซูมได้ตามความต้องการของคุณ

## ขั้นตอนที่ 5: สร้างการดำเนินการนำทาง

สร้างอินสแตนซ์ของการดำเนินการนำทางโดยใช้เพจเป้าหมายที่ระบุ:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## ขั้นตอนที่ 6: การตั้งค่าปลายทาง

ตั้งค่าปลายทางเพื่อไปที่หน้าเป้าหมายโดยใช้พิกัดและซูม:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## ขั้นตอนที่ 7: การกำหนดค่าการดำเนินการเปิดเอกสาร

ตั้งค่าการดำเนินการเปิดเอกสารด้วยการดำเนินการนำทางที่สร้างขึ้น:

```csharp
doc. OpenAction = action;
```

## ขั้นตอนที่ 8: บันทึกเอกสารที่อัพเดต

 บันทึกเอกสารที่อัพเดตโดยใช้`Save` วิธี:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับระบุเพจเมื่อดูโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// โหลดไฟล์ PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// รับอินสแตนซ์ของหน้าที่สองของเอกสาร
Page page2 = doc.Pages[2];
// สร้างตัวแปรเพื่อตั้งค่าปัจจัยการซูมของหน้าเป้าหมาย
double zoom = 1;
// สร้างอินสแตนซ์ GoToAction
GoToAction action = new GoToAction(doc.Pages[2]);
// ไป 2 หน้า
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// ตั้งค่าการดำเนินการเปิดเอกสาร
doc.OpenAction = action;
// บันทึกเอกสารที่อัปเดต
doc.Save(dataDir + "goto2page_out.pdf");
```

## บทสรุป

ขอแสดงความยินดี! ตอนนี้คุณรู้วิธีระบุหน้าเมื่อดู PDF โดยใช้ Aspose.PDF สำหรับ .NET ใช้ความรู้นี้เพื่อปรับแต่งประสบการณ์การรับชมของผู้ใช้ในเอกสาร PDF ของคุณ

เมื่อคุณได้อ่านคู่มือนี้เสร็จสิ้นแล้ว คุณสามารถนำแนวคิดเหล่านี้ไปใช้กับโครงการของคุณเอง และสำรวจคุณลักษณะเพิ่มเติมที่ Aspose.PDF สำหรับ .NET นำเสนอได้

### คำถามที่พบบ่อย 

#### ถาม: การระบุเพจเป้าหมายเมื่อดูไฟล์ PDF มีจุดประสงค์อะไร

ตอบ: การระบุหน้าเป้าหมายช่วยให้คุณควบคุมได้ว่าจะให้แสดงหน้าใดของเอกสาร PDF เมื่อเปิดไฟล์ สิ่งนี้สามารถปรับปรุงประสบการณ์ผู้ใช้โดยนำพวกเขาไปยังหน้าเฉพาะที่สนใจ

#### ถาม: การระบุหน้าเป้าหมายจะมีประโยชน์ในเอกสาร PDF ได้อย่างไร

ตอบ: การระบุเพจเป้าหมายมีประโยชน์เมื่อคุณต้องการแนะนำผู้ใช้ไปยังส่วนหรือเนื้อหาเฉพาะภายในเอกสาร PDF โดยไม่ต้องให้พวกเขานำทางผ่านหน้าต่างๆ ด้วยตนเอง

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยให้ระบุเพจเป้าหมายสำหรับการดูได้อย่างไร

ตอบ: Aspose.PDF สำหรับ .NET มี API ที่ช่วยให้คุณสามารถตั้งค่ามุมมองเริ่มต้นของเอกสาร PDF รวมถึงหน้าเป้าหมาย ระดับการซูม และคุณสมบัติการแสดงผลอื่นๆ

#### ถาม: ฉันสามารถระบุหน้าใด ๆ ให้เป็นหน้าเป้าหมายได้หรือไม่?

ตอบ: ได้ คุณสามารถระบุหน้าใดก็ได้ภายในเอกสาร PDF เป็นหน้าเป้าหมายในการดู เพียงใช้ดัชนีที่เหมาะสมเพื่อเลือกหน้าที่ต้องการ

#### ถาม: ปัจจัยการซูมมีความสำคัญอย่างไรเมื่อระบุหน้าเป้าหมาย

ตอบ: ปัจจัยการซูมจะกำหนดระดับการขยายที่ใช้กับหน้าเป้าหมายเมื่อเปิดเอกสาร PDF ควบคุมจำนวนเนื้อหาที่จะแสดงภายในวิวพอร์ต

#### ถาม: ฉันสามารถตั้งค่าปัจจัยการซูมที่แตกต่างกันสำหรับหน้าเป้าหมายที่แตกต่างกันได้หรือไม่

ตอบ: ได้ คุณสามารถตั้งค่าปัจจัยการซูมที่แตกต่างกันสำหรับหน้าเป้าหมายที่แตกต่างกันได้โดยสร้างแยกต่างหาก`GoToAction` อินสแตนซ์และการกำหนดค่าปลายทางตามลำดับ

#### ถาม: มีข้อจำกัดในการระบุเพจเป้าหมายหรือไม่?

ตอบ: การระบุเพจเป้าหมายนั้นจำกัดอยู่ที่การควบคุมมุมมองเริ่มต้นเมื่อเปิด PDF ไม่ส่งผลกระทบต่อการโต้ตอบหรือการนำทางของผู้ใช้เมื่อ PDF แสดงขึ้น

#### ถาม: ฉันสามารถใช้คุณสมบัตินี้เพื่อสร้างงานนำเสนอภายในเอกสาร PDF ได้หรือไม่

ตอบ: ได้ คุณสามารถใช้ฟีเจอร์นี้เพื่อสร้างประสบการณ์เหมือนการนำเสนอภายในเอกสาร PDF โดยแนะนำผู้ใช้ผ่านส่วนหรือหัวข้อต่างๆ

#### ถาม: ฉันสามารถปรับแต่งมุมมองเริ่มต้นด้านอื่นๆ เช่น เค้าโครงหน้าได้หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET มีคุณสมบัติในการปรับแต่งแง่มุมอื่นๆ ของมุมมองเริ่มต้น รวมถึงเค้าโครงเพจ โหมดเพจ และอื่นๆ

#### ถาม: ฉันจะทดสอบได้อย่างไรว่าหน้าเป้าหมายและปัจจัยการซูมที่ระบุทำงานตามที่ตั้งใจไว้หรือไม่

ตอบ: หลังจากใช้โค้ดที่ให้มาเพื่อระบุหน้าเป้าหมายและปัจจัยการซูม ให้เปิดไฟล์ PDF ที่แก้ไขแล้วและตรวจสอบว่าเปิดด้วยหน้าและระดับการซูมที่ถูกต้อง