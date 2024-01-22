---
title: กำหนดขนาดรูปภาพในไฟล์ PDF
linktitle: กำหนดขนาดรูปภาพในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการตั้งค่าขนาดของรูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 270
url: /th/net/programming-with-images/set-image-size/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีตั้งค่าขนาดของรูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ทำตามขั้นตอนเหล่านี้เพื่อดำเนินการนี้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือสภาพแวดล้อมการพัฒนาอื่น ๆ ที่ติดตั้งและกำหนดค่า
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose

## ขั้นตอนที่ 1: การสร้างเอกสาร PDF

ในการเริ่มต้น ให้ใช้โค้ดต่อไปนี้เพื่อสร้างเอกสาร PDF ใหม่:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// สร้างอินสแตนซ์วัตถุเอกสาร
Document doc = new Document();

// เพิ่มหน้าไปยังคอลเลกชันของหน้าของไฟล์ PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 2: เพิ่มรูปภาพ

ต่อไป เราจะเพิ่มรูปภาพในหน้าเอกสาร PDF ใช้รหัสต่อไปนี้:

```csharp
// สร้างอินสแตนซ์รูปภาพ
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// กำหนดความกว้างและความสูงของภาพเป็นจุด
img. FixWidth = 100;
img. FixHeight = 100;

// ตั้งค่าประเภทรูปภาพเป็นไม่ทราบ (ไม่ทราบ)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//เส้นทางไปยังไฟล์ต้นฉบับของรูปภาพ
img.File = dataDir + "aspose-logo.jpg";

// เพิ่มรูปภาพลงในคอลเลกชันย่อหน้าของหน้า
page.Paragraphs.Add(img);
```

ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางที่ถูกต้องไปยังไฟล์ต้นฉบับของรูปภาพ

## ขั้นตอนที่ 3: การตั้งค่าคุณสมบัติของหน้า

สุดท้าย เราจะตั้งค่าคุณสมบัติของหน้า รวมถึงความกว้างและความสูง ใช้รหัสต่อไปนี้:

```csharp
// ตั้งค่าคุณสมบัติของเพจ
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### ตัวอย่างซอร์สโค้ดสำหรับตั้งค่าขนาดรูปภาพโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างอินสแตนซ์วัตถุเอกสาร
Document doc = new Document();
// เพิ่มหน้าไปยังคอลเลกชันหน้าของไฟล์ PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// สร้างอินสแตนซ์รูปภาพ
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// ตั้งค่าความกว้างและความสูงของภาพเป็นจุด
img.FixWidth = 100;
img.FixHeight = 100;
// ตั้งค่าประเภทรูปภาพเป็น SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// เส้นทางสำหรับไฟล์ต้นฉบับ
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//ตั้งค่าคุณสมบัติของเพจ
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// บันทึกไฟล์ PDF ที่เป็นผลลัพธ์
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## บทสรุป

ขอแสดงความยินดี! คุณได้กำหนดขนาดของรูปภาพในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว ตอนนี้คุณสามารถใช้วิธีนี้กับโปรเจ็กต์ของคุณเองเพื่อปรับขนาดรูปภาพในไฟล์ PDF ได้

### คำถามที่พบบ่อยเกี่ยวกับการตั้งค่าขนาดภาพในไฟล์ PDF

#### ถาม: จุดประสงค์ของการตั้งค่าขนาดของรูปภาพในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: วัตถุประสงค์ของการตั้งค่าขนาดของรูปภาพในเอกสาร PDF คือเพื่อควบคุมขนาดของรูปภาพเมื่อเพิ่มลงใน PDF ช่วยให้คุณสามารถปรับรูปลักษณ์และเค้าโครงของรูปภาพภายในไฟล์ PDF ของคุณได้

#### ถาม: ขั้นตอนการตั้งค่าขนาดของรูปภาพในเอกสาร PDF เป็นอย่างไร

 ตอบ: กระบวนการนี้เกี่ยวข้องกับการสร้าง`Aspose.Pdf.Image` ตัวอย่าง ระบุความกว้างและความสูงโดยใช้`FixWidth` และ`FixHeight` คุณสมบัติ แล้วเพิ่มรูปภาพลงในเอกสาร PDF นอกจากนี้ คุณยังสามารถกำหนดขนาดของหน้าเพื่อรองรับรูปภาพได้

#### ถาม: ฉันสามารถกำหนดขนาดของรูปภาพเป็นเปอร์เซ็นต์เฉพาะของขนาดหน้าได้หรือไม่

ตอบ: รหัสที่ให้มาจะกำหนดความกว้างและความสูงของภาพเป็นจุด หากคุณต้องการกำหนดขนาดของรูปภาพตามเปอร์เซ็นต์ของขนาดหน้า คุณจะต้องคำนวณขนาดตามนั้นและปรับโค้ดตามนั้น

####  ถาม: อะไรคือสาระสำคัญของ`FileType` property when adding an image to the PDF document?

 ตอบ:`FileType`คุณสมบัติระบุประเภทของรูปภาพที่จะเพิ่มลงในเอกสาร PDF ในโค้ดที่ให้มาคือค่า`Unknown` บ่งชี้ว่าไม่ทราบประเภทของรูปภาพ และ Aspose.PDF จะพยายามกำหนดประเภทรูปภาพตามนามสกุลไฟล์

#### ถาม: ฉันสามารถเพิ่มรูปภาพหลายรูปในหน้าเดียวโดยใช้วิธีนี้ได้หรือไม่

 ตอบ: ได้ คุณสามารถเพิ่มรูปภาพหลายรูปในหน้าเดียวได้โดยสร้างหลายรูป`Aspose.Pdf.Image` และเพิ่มลงในคอลเลกชันย่อหน้าของหน้า ตรวจสอบให้แน่ใจว่าได้ปรับตำแหน่งและเค้าโครงของรูปภาพตามต้องการ

#### ถาม: ฉันจะควบคุมตำแหน่งและการจัดตำแหน่งของรูปภาพที่เพิ่มบนเพจได้อย่างไร

 ตอบ: สามารถควบคุมตำแหน่งและการจัดตำแหน่งของรูปภาพที่เพิ่มได้โดยการปรับพิกัดและเค้าโครงของรูปภาพโดยใช้คุณสมบัติ เช่น`img.Left`, `img.Top`และคุณสมบัติการจัดรูปแบบย่อหน้า

####  ถาม: จุดประสงค์ของการตั้งค่าคุณสมบัติของเพจคืออะไร`page.PageInfo.Width` and `page.PageInfo.Height`?

ตอบ: การตั้งค่าคุณสมบัติของเพจทำให้คุณสามารถกำหนดขนาดของเพจได้ เพื่อให้แน่ใจว่าขนาดหน้าจะรองรับรูปภาพที่เพิ่มและเนื้อหาอื่น ๆ ที่คุณอาจมีบนหน้า

#### ถาม: ฉันสามารถกำหนดขนาดที่แตกต่างกันสำหรับรูปภาพที่แตกต่างกันภายในเอกสาร PDF เดียวกันได้หรือไม่

 ตอบ: ได้ คุณสามารถกำหนดขนาดที่แตกต่างกันสำหรับรูปภาพต่างๆ ได้โดยสร้างแยกกัน`Aspose.Pdf.Image` กรณีและการปรับ`FixWidth`, `FixHeight`และคุณสมบัติการจัดวางสำหรับแต่ละภาพ

#### ถาม: ฉันจะรวมวิธีนี้เข้ากับโปรเจ็กต์ของฉันเองเพื่อกำหนดขนาดรูปภาพในไฟล์ PDF ได้อย่างไร

ตอบ: หากต้องการรวมวิธีการนี้เข้ากับโปรเจ็กต์ของคุณ ให้ทำตามขั้นตอนที่ระบุไว้และแก้ไขโค้ดตามต้องการ คุณสามารถใช้วิธีนี้เพื่อเพิ่มรูปภาพขนาดเฉพาะลงในเอกสาร PDF ของคุณตามความต้องการของแอปพลิเคชันของคุณ