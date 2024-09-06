---
title: ตั้งค่าข้อมูลไฟล์ในไฟล์ PDF
linktitle: ตั้งค่าข้อมูลไฟล์ในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อตั้งค่าข้อมูลไฟล์ในไฟล์ PDF ด้วยคู่มือทีละขั้นตอนนี้
type: docs
weight: 310
url: /th/net/programming-with-document/setfileinfo/
---
หากคุณกำลังทำงานในโปรเจ็กต์ที่ต้องจัดการไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET หนึ่งในฟีเจอร์ที่คุณอาจต้องการใช้ก็คือความสามารถในการตั้งค่าข้อมูลไฟล์สำหรับเอกสาร PDF ข้อมูลไฟล์ประกอบด้วยรายละเอียดต่างๆ เช่น ผู้เขียน วันที่สร้าง คำสำคัญ วันที่แก้ไข หัวเรื่อง และชื่อเรื่อง คู่มือนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการตั้งค่าข้อมูลไฟล์สำหรับเอกสาร PDF โดยใช้โค้ดต้นฉบับ C# กับ Aspose.PDF สำหรับ .NET

## คู่มือทีละขั้นตอนสำหรับการตั้งค่าข้อมูลไฟล์โดยใช้ Aspose.PDF สำหรับ .NET

1. สร้างโครงการ C# ใหม่ใน Visual Studio IDE ของคุณ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET ในโครงการของคุณ
3. สร้างอ็อบเจ็กต์เอกสาร PDF ใหม่โดยระบุเส้นทางไปยังไฟล์ PDF ที่คุณต้องการแก้ไขข้อมูลไฟล์

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสาร

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดเอกสาร PDF

```csharp
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## ขั้นตอนที่ 3: ใช้วัตถุ DocumentInfo เพื่อเข้าถึงข้อมูลไฟล์ของเอกสาร PDF

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## ขั้นตอนที่ 4: ตั้งค่าข้อมูลไฟล์ที่ต้องการโดยใช้คุณสมบัติของอ็อบเจ็กต์ DocumentInfo

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## ขั้นตอนที่ 5: บันทึกเอกสาร PDF ที่อัปเดตไปยังตำแหน่งที่ระบุ

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## ขั้นตอนที่ 6: ตรวจสอบว่าข้อมูลไฟล์ได้รับการอัปเดตเรียบร้อยแล้ว

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

คุณได้ตั้งค่าข้อมูลไฟล์สำหรับเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว

### ตัวอย่างโค้ดต้นฉบับสำหรับ Set File Info โดยใช้ Aspose.PDF สำหรับ .NET


```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// ระบุข้อมูลเอกสาร
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// บันทึกเอกสารผลลัพธ์
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## บทสรุป

โดยสรุป Aspose.PDF สำหรับ .NET เป็นวิธีง่ายๆ และมีประสิทธิภาพในการตั้งค่าข้อมูลไฟล์สำหรับเอกสาร PDF โดยทำตามขั้นตอนที่กล่าวข้างต้น คุณสามารถตั้งค่าข้อมูลไฟล์ที่ต้องการสำหรับเอกสาร PDF ได้อย่างง่ายดายโดยใช้โค้ดต้นฉบับของ C#

### คำถามที่พบบ่อยสำหรับข้อมูลไฟล์ชุดในไฟล์ PDF

#### ถาม: ฉันสามารถตั้งค่าคุณสมบัติข้อมูลไฟล์เพิ่มเติมที่ไม่ได้กล่าวถึงในตัวอย่างได้หรือไม่

 A: ใช่ คุณสามารถตั้งค่าคุณสมบัติข้อมูลไฟล์เพิ่มเติมได้โดยใช้`DocumentInfo` วัตถุใน Aspose.PDF สำหรับ .NET`DocumentInfo`คลาสมีคุณสมบัติต่าง ๆ ที่ช่วยให้คุณตั้งค่าข้อมูลเพิ่มเติม เช่น โปรดิวเซอร์ เวอร์ชัน และคุณสมบัติแบบกำหนดเอง

#### ถาม: สามารถดึงข้อมูลไฟล์จากเอกสาร PDF ที่มีอยู่ได้หรือไม่

 A: ใช่ คุณสามารถดึงข้อมูลไฟล์จากเอกสาร PDF ที่มีอยู่ได้โดยใช้ Aspose.PDF สำหรับ .NET หากต้องการทำเช่นนี้ คุณสามารถใช้`DocumentInfo` วัตถุเพื่อเข้าถึงคุณสมบัติข้อมูลไฟล์และอ่านข้อมูลที่เก็บไว้ในเอกสาร PDF

#### ถาม: การตั้งค่าข้อมูลไฟล์จะแก้ไขเอกสาร PDF ต้นฉบับหรือไม่?

ตอบ ไม่ การตั้งค่าข้อมูลไฟล์โดยใช้ Aspose.PDF สำหรับ .NET จะไม่แก้ไขเอกสาร PDF ต้นฉบับ แต่จะสร้างเอกสาร PDF ใหม่โดยใช้ข้อมูลไฟล์ที่อัปเดตแทน เอกสาร PDF ต้นฉบับจะยังคงไม่เปลี่ยนแปลง