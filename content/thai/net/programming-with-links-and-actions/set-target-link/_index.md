---
title: ตั้งค่าลิงค์เป้าหมายในไฟล์ PDF
linktitle: ตั้งค่าลิงค์เป้าหมายในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีตั้งค่าลิงก์เป้าหมายในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 100
url: /th/net/programming-with-links-and-actions/set-target-link/
---
เรียนรู้วิธีตั้งค่าลิงก์เป้าหมายในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนนี้

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วยโปรเจ็กต์ C# และการอ้างอิง Aspose.PDF ที่เหมาะสม

## ขั้นตอนที่ 2: กำลังโหลดไฟล์ PDF

กำหนดเส้นทางไดเรกทอรีของเอกสารของคุณและอัปโหลดไฟล์ PDF โดยใช้รหัสต่อไปนี้:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// โหลดไฟล์ PDF
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## ขั้นตอนที่ 3: การแก้ไขลิงก์เป้าหมาย

รับคำอธิบายประกอบลิงก์เพื่อแก้ไขโดยใช้โค้ดต่อไปนี้:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

 คุณสามารถปรับ`[1]` ดัชนีเพื่อเลือกหน้าหรือคำอธิบายประกอบเฉพาะ

ถัดไป อัปเดตปลายทางโดยไม่ต้องอัปเดตไฟล์:

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

และหากคุณต้องการอัปเดตไฟล์ด้วย:

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## ขั้นตอนที่ 4: บันทึกเอกสารด้วยลิงก์ที่อัปเดต

 บันทึกเอกสารด้วยลิงก์ที่อัปเดตโดยใช้`Save` วิธี:

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## ขั้นตอนที่ 5: การแสดงผลลัพธ์

แสดงข้อความระบุว่าลิงก์เป้าหมายได้รับการกำหนดค่าเรียบร้อยแล้ว และระบุตำแหน่งของไฟล์ที่บันทึกไว้:

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับ Set Target Link โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
try
{
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// โหลดไฟล์ PDF
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	// ปลายทางการอัปเดตบรรทัดถัดไป ห้ามอัปเดตไฟล์
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	// ไฟล์อัพเดตบรรทัดถัดไป
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	// บันทึกเอกสารพร้อมลิงก์ที่อัปเดต
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## บทสรุป

ขอแสดงความยินดี! ตอนนี้คุณรู้วิธีตั้งค่าลิงก์เป้าหมายในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET แล้ว ใช้ความรู้นี้เพื่อปรับแต่งลิงก์ในเอกสาร PDF ของคุณ และสร้างประสบการณ์เชิงโต้ตอบสำหรับผู้ใช้

เมื่อคุณได้อ่านคู่มือนี้เสร็จสิ้นแล้ว คุณสามารถนำแนวคิดเหล่านี้ไปใช้กับโครงการของคุณเอง และสำรวจคุณลักษณะเพิ่มเติมที่ Aspose.PDF สำหรับ .NET นำเสนอได้

### คำถามที่พบบ่อยสำหรับการตั้งลิงค์เป้าหมายในไฟล์ PDF

#### ถาม: ลิงก์เป้าหมายในไฟล์ PDF คืออะไร

ตอบ: ลิงก์เป้าหมายในไฟล์ PDF คือลิงก์ที่คลิกได้ซึ่งจะนำผู้อ่านไปยังปลายทางเฉพาะภายในเอกสารเดียวกันหรือไปยังไฟล์ PDF อื่น

#### ถาม: เหตุใดฉันจึงต้องการตั้งค่าลิงก์เป้าหมายในไฟล์ PDF

ตอบ: การตั้งค่าลิงก์เป้าหมายช่วยให้คุณสร้างประสบการณ์การนำทางที่ราบรื่นภายในเอกสาร PDF หรือลิงก์ไปยังส่วนหรือหน้าเฉพาะภายในไฟล์ PDF อื่น ๆ

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยในการตั้งค่าลิงก์เป้าหมายอย่างไร

ตอบ: Aspose.PDF สำหรับ .NET มี API เพื่อจัดการแง่มุมต่างๆ ของไฟล์ PDF รวมถึงการสร้างและแก้ไขลิงก์ บทช่วยสอนนี้สาธิตวิธีการตั้งค่าลิงก์เป้าหมายโดยใช้โค้ด C#

#### ถาม: ฉันสามารถตั้งค่าลิงก์เป้าหมายเพื่อนำทางไปยังหน้าใดหน้าหนึ่งภายในเอกสารเดียวกันได้หรือไม่

ตอบ: ได้ Aspose.PDF สำหรับ .NET ช่วยให้คุณสามารถตั้งค่าลิงก์เป้าหมายเพื่อนำทางไปยังหน้าเฉพาะภายในเอกสารเดียวกันได้

#### ถาม: ฉันสามารถตั้งค่าลิงก์เป้าหมายเพื่อนำทางไปยังหน้าใดหน้าหนึ่งในไฟล์ PDF อื่นได้หรือไม่

ตอบ: ได้ คุณสามารถตั้งค่าลิงก์เป้าหมายเพื่อนำทางไปยังหน้าเฉพาะภายในไฟล์ PDF อื่นได้โดยใช้ Aspose.PDF สำหรับ .NET

#### ถาม: มีข้อจำกัดในการตั้งค่าลิงก์เป้าหมายหรือไม่

ตอบ: ลิงก์เป้าหมายสามารถนำทางได้เฉพาะภายในเอกสารเดียวกันหรือไปยังหน้าเฉพาะภายในไฟล์ PDF อื่น ๆ ไม่สามารถเชื่อมโยงไปยังเนื้อหาเฉพาะเจาะจงภายในเอกสารอื่นได้โดยตรง

#### ถาม: ฉันจะปรับแต่งรูปลักษณ์ของลิงก์เป้าหมายได้อย่างไร

ตอบ: รูปลักษณ์ของลิงก์เป้าหมาย เช่น สีและสไตล์ สามารถปรับแต่งได้โดยใช้คุณสมบัติที่ Aspose.PDF สำหรับ .NET มอบให้

#### ถาม: ฉันสามารถตั้งค่าลิงก์เป้าหมายหลายรายการในเอกสาร PDF เดียวกันได้หรือไม่

ตอบ: ได้ คุณสามารถตั้งค่าลิงก์เป้าหมายได้หลายลิงก์ในเอกสาร PDF เดียวกัน เพียงทำขั้นตอนนี้ซ้ำสำหรับแต่ละลิงก์ที่คุณต้องการสร้าง

#### ถาม: ฉันสามารถตั้งค่าลิงก์เป้าหมายโดยใช้รูปร่างหรือข้อความเฉพาะได้หรือไม่

ตอบ: ได้ คุณสามารถแนบลิงก์เป้าหมายไปยังรูปร่างหรือข้อความเฉพาะภายในเอกสาร PDF ได้โดยใช้คุณสมบัติและวิธีการที่เหมาะสมที่ Aspose.PDF สำหรับ .NET มอบให้

#### ถาม: ฉันจะทดสอบได้อย่างไรว่าลิงก์เป้าหมายทำงานตามที่ตั้งใจไว้หรือไม่

ตอบ: หลังจากตั้งค่าลิงก์เป้าหมายโดยใช้โค้ดที่ให้มา ให้เปิด PDF ที่แก้ไขแล้วคลิกลิงก์เพื่อให้แน่ใจว่าลิงก์จะนำทางไปยังปลายทางที่ต้องการ

#### ถาม: ฉันสามารถตั้งค่าลิงก์เป้าหมายใน PDF ที่มีการป้องกันด้วยรหัสผ่านได้หรือไม่

ตอบ: ได้ คุณสามารถตั้งค่าลิงก์เป้าหมายใน PDF ที่มีการป้องกันด้วยรหัสผ่านได้ ตราบใดที่คุณให้ข้อมูลประจำตัวที่เหมาะสมเพื่อเข้าถึงและแก้ไขเอกสาร