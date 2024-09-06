---
title: ค้นหาและรับรูปภาพในไฟล์ PDF
linktitle: ค้นหาและรับรูปภาพในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: คู่มือทีละขั้นตอนในการค้นหาและรับรูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 260
url: /th/net/programming-with-images/search-and-get-images/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับการค้นหาและรับรูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ปฏิบัติตามขั้นตอนเหล่านี้เพื่อดำเนินการนี้ได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งและกำหนดค่า Visual Studio หรือสภาพแวดล้อมการพัฒนาอื่น ๆ
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose

## ขั้นตอนที่ 1: การโหลดเอกสาร PDF

ในการเริ่มต้น ให้ใช้โค้ดต่อไปนี้เพื่อโหลดเอกสาร PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// เปิดเอกสาร
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

โปรดแน่ใจว่าระบุเส้นทางที่ถูกต้องไปยังเอกสาร PDF ของคุณ

## ขั้นตอนที่ 2: การค้นหาตำแหน่งรูปภาพ

ในการค้นหาตำแหน่งของรูปภาพในเอกสาร PDF ให้ใช้โค้ดดังต่อไปนี้:

```csharp
// สร้างวัตถุ ImagePlacementAbsorber เพื่อค้นหาตำแหน่งของภาพ
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// รับตัวดูดซับสำหรับทุกหน้าของเอกสาร
doc.Pages.Accept(abs);
```

นี่จะเป็นการรวบรวมตำแหน่งของภาพในตัวดูดซับ

## ขั้นตอนที่ 3: เรียกดูตำแหน่งรูปภาพและรับรูปภาพและคุณสมบัติของรูปภาพเหล่านั้น

ต่อไปเราจะเรียกดูตำแหน่งภาพที่รวบรวมไว้และรับภาพพร้อมคุณสมบัติของภาพเหล่านั้น ใช้โค้ดต่อไปนี้:

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // รับภาพโดยใช้ ImagePlacement object
     XImage image = imagePlacement.Image;

     // แสดงคุณสมบัติของตำแหน่งภาพ
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

การดำเนินการนี้จะเรียกดูตำแหน่งรูปภาพทั้งหมด รับรูปภาพที่ตรงกัน และแสดงคุณสมบัติของรูปภาพเหล่านั้น

### ตัวอย่างโค้ดต้นฉบับสำหรับการค้นหาและรับภาพโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// สร้างวัตถุ ImagePlacementAbsorber เพื่อดำเนินการค้นหาการวางตำแหน่งรูปภาพ
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// รับตัวดูดซับสำหรับทุกหน้า
doc.Pages.Accept(abs);
// วนซ้ำผ่าน ImagePlacements ทั้งหมด รับคุณสมบัติรูปภาพและ ImagePlacement
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// รับภาพโดยใช้ ImagePlacement object
	XImage image = imagePlacement.Image;
	// แสดงคุณสมบัติการวางภาพสำหรับการวางทุกตำแหน่ง
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## บทสรุป

ขอแสดงความยินดี ! คุณค้นหาและรับรูปภาพในเอกสาร PDF สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้เมธอดนี้กับโปรเจ็กต์ของคุณเองเพื่อแยกรูปภาพและรับคุณสมบัติของรูปภาพจากไฟล์ PDF

### คำถามที่พบบ่อยสำหรับการค้นหาและรับรูปภาพในไฟล์ PDF

#### ถาม: จุดประสงค์ในการค้นหาและรับรูปภาพในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

A: การค้นหาและรับรูปภาพในเอกสาร PDF ช่วยให้คุณค้นหาและแยกรูปภาพภายในไฟล์ PDF ได้ ซึ่งอาจมีประโยชน์สำหรับวัตถุประสงค์ต่างๆ เช่น การวิเคราะห์เนื้อหา การตรวจสอบคุณสมบัติของรูปภาพ หรือการประมวลผลรูปภาพเพิ่มเติม

#### ถาม: กระบวนการค้นหารูปภาพในเอกสาร PDF ทำงานอย่างไร?

 A: กระบวนการนี้เกี่ยวข้องกับการใช้`ImagePlacementAbsorber` วัตถุที่จะดำเนินการค้นหาตำแหน่งของภาพในทุกหน้าของเอกสาร PDF ตัวดูดซับจะรวบรวมข้อมูลเกี่ยวกับตำแหน่ง ขนาด และความละเอียดของภาพแต่ละภาพภายในเอกสาร

####  ถาม: จุดประสงค์ของการ`ImagePlacement` object in the code?

 ก. การ`ImagePlacement`วัตถุแสดงถึงตำแหน่งของภาพภายในเอกสาร PDF โดยมีคุณสมบัติที่ให้คุณเข้าถึงรายละเอียดต่างๆ เช่น ขนาด พิกัด และความละเอียดของภาพได้

#### ถาม: ฉันสามารถกรองภาพที่ค้นหาและได้รับตามเกณฑ์ที่กำหนดได้หรือไม่

A: รหัสที่ให้มาจะรวบรวมข้อมูลเกี่ยวกับรูปภาพทั้งหมดในเอกสาร PDF หากคุณต้องการกรองรูปภาพตามเกณฑ์เฉพาะ (เช่น ประเภทของรูปภาพ ขนาด ความละเอียด) คุณอาจต้องแก้ไขรหัสเพื่อรวมเงื่อนไขการกรองที่เหมาะสม

#### ถาม: ฉันสามารถเข้าถึงเนื้อหาของภาพจริงได้อย่างไรหลังจากได้รับข้อมูลการจัดวางแล้ว

 ก. การ`XImage` วัตถุที่ได้รับจาก`ImagePlacement` วัตถุแสดงเนื้อหาของภาพจริง คุณสามารถประมวลผลเพิ่มเติมได้`XImage` วัตถุ เช่น การบันทึกไปยังไฟล์หรือแสดงในแอปพลิเคชันของคุณ

#### ถาม: ฉันสามารถทำอะไรได้บ้างกับคุณสมบัติของภาพที่ได้รับ

A: คุณสมบัติของภาพที่ได้ เช่น ความกว้าง ความสูง พิกัด และความละเอียด สามารถนำไปใช้เพื่อจุดประสงค์ต่างๆ ได้ คุณสามารถวิเคราะห์คุณสมบัติ แสดงให้ผู้ใช้ดู หรือใช้เป็นอินพุตสำหรับการประมวลผลเพิ่มเติม

#### ถาม: ฉันสามารถแก้ไขหรือปรับแต่งรูปภาพภายในเอกสาร PDF ด้วยวิธีนี้ได้หรือไม่

A: โค้ดที่ให้มาจะเน้นไปที่การค้นหาและรับข้อมูลการจัดวางรูปภาพ หากต้องการปรับเปลี่ยนหรือแก้ไขรูปภาพ คุณอาจต้องรวมฟังก์ชันเพิ่มเติม เช่น การปรับแต่งรูปภาพ โดยใช้ไลบรารี Aspose.PDF

#### ถาม: ฉันจะรวมวิธีการนี้เข้ากับโครงการของฉันเองได้อย่างไร

A: หากต้องการรวมวิธีการนี้เข้ากับโครงการของคุณ ให้ทำตามขั้นตอนที่ระบุไว้และแก้ไขโค้ดตามต้องการ คุณสามารถใช้ข้อมูลและคุณสมบัติของตำแหน่งภาพที่ได้ตามความต้องการของแอปพลิเคชันของคุณ

#### ถาม: Aspose.PDF สำหรับ .NET มีฟีเจอร์อื่นๆ ที่เกี่ยวข้องกับการจัดการรูปภาพในเอกสาร PDF หรือไม่

A: ใช่ Aspose.PDF สำหรับ .NET มีฟีเจอร์ต่างๆ มากมายสำหรับการทำงานกับรูปภาพในเอกสาร PDF รวมถึงการแทรกรูปภาพ การปรับขนาด การหมุน การแยกภาพ และอื่นๆ คุณสามารถสำรวจเอกสารและตัวอย่างของไลบรารีเพื่อค้นพบความสามารถทั้งหมดได้