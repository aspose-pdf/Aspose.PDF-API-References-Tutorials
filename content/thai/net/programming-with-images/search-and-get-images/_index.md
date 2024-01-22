---
title: ค้นหาและรับรูปภาพในไฟล์ PDF
linktitle: ค้นหาและรับรูปภาพในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการค้นหาและรับรูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 260
url: /th/net/programming-with-images/search-and-get-images/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการค้นหาและรับรูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ทำตามขั้นตอนเหล่านี้เพื่อดำเนินการนี้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือสภาพแวดล้อมการพัฒนาอื่น ๆ ที่ติดตั้งและกำหนดค่า
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร PDF

ในการเริ่มต้น ให้ใช้โค้ดต่อไปนี้เพื่อโหลดเอกสาร PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// เปิดเอกสาร
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางที่ถูกต้องไปยังเอกสาร PDF ของคุณ

## ขั้นตอนที่ 2: ค้นหาตำแหน่งรูปภาพ

หากต้องการค้นหาตำแหน่งของรูปภาพในเอกสาร PDF ให้ใช้รหัสต่อไปนี้:

```csharp
// สร้างวัตถุ ImagePlacementAbsorber เพื่อค้นหาตำแหน่งของรูปภาพ
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// ยอมรับตัวดูดซับสำหรับทุกหน้าของเอกสาร
doc.Pages.Accept(abs);
```

ซึ่งจะรวบรวมตำแหน่งของภาพในตัวดูดซับ

## ขั้นตอนที่ 3: เรียกดูตำแหน่งรูปภาพและรับรูปภาพและคุณสมบัติ

ต่อไป เราจะเรียกดูตำแหน่งภาพที่รวบรวมและรับภาพและคุณสมบัติต่างๆ ใช้รหัสต่อไปนี้:

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // รับภาพโดยใช้วัตถุ ImagePlacement
     XImage image = imagePlacement.Image;

     // แสดงคุณสมบัติตำแหน่งของภาพ
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

การดำเนินการนี้จะเรียกดูตำแหน่งรูปภาพทั้งหมด รับภาพที่ตรงกัน และแสดงคุณสมบัติต่างๆ

### ตัวอย่างซอร์สโค้ดสำหรับการค้นหาและรับรูปภาพโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// สร้างวัตถุ ImagePlacementAbsorber เพื่อทำการค้นหาตำแหน่งรูปภาพ
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// รับซับทุกหน้า
doc.Pages.Accept(abs);
// วนซ้ำ ImagePlacements ทั้งหมด รับรูปภาพและคุณสมบัติ ImagePlacement
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// รับภาพโดยใช้วัตถุ ImagePlacement
	XImage image = imagePlacement.Image;
	// แสดงคุณสมบัติการจัดวางรูปภาพสำหรับตำแหน่งทั้งหมด
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## บทสรุป

ขอแสดงความยินดี! คุณค้นหาและรับรูปภาพในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว ตอนนี้คุณสามารถใช้วิธีนี้กับโปรเจ็กต์ของคุณเองเพื่อแยกรูปภาพและรับคุณสมบัติจากไฟล์ PDF

### คำถามที่พบบ่อยสำหรับการค้นหาและรับภาพในรูปแบบไฟล์ PDF

#### ถาม: จุดประสงค์ของการค้นหาและรับรูปภาพในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: การค้นหาและรับรูปภาพในเอกสาร PDF ช่วยให้คุณสามารถค้นหาและแยกรูปภาพภายในไฟล์ PDF ได้ สิ่งนี้มีประโยชน์สำหรับวัตถุประสงค์ต่างๆ เช่น การวิเคราะห์เนื้อหา การตรวจสอบคุณสมบัติของรูปภาพ หรือการประมวลผลรูปภาพเพิ่มเติม

#### ถาม: กระบวนการค้นหารูปภาพในเอกสาร PDF ทำงานอย่างไร

 ตอบ: กระบวนการนี้เกี่ยวข้องกับการใช้`ImagePlacementAbsorber` วัตถุเพื่อค้นหาตำแหน่งรูปภาพในทุกหน้าของเอกสาร PDF ตัวดูดซับจะรวบรวมข้อมูลเกี่ยวกับตำแหน่ง ขนาด และความละเอียดของแต่ละภาพภายในเอกสาร

####  ถาม: จุดประสงค์ของ.`ImagePlacement` object in the code?

 ตอบ:`ImagePlacement`object แสดงถึงตำแหน่งของรูปภาพภายในเอกสาร PDF โดยมีคุณสมบัติที่ช่วยให้คุณเข้าถึงรายละเอียดต่างๆ เช่น ขนาดของรูปภาพ พิกัด และความละเอียด

#### ถาม: ฉันสามารถกรองภาพที่ค้นหาและรับตามเกณฑ์ที่กำหนดได้หรือไม่

ตอบ: รหัสที่ให้มาจะรวบรวมข้อมูลเกี่ยวกับรูปภาพทั้งหมดภายในเอกสาร PDF หากคุณต้องการกรองรูปภาพตามเกณฑ์เฉพาะ (เช่น ประเภทรูปภาพ ขนาด ความละเอียด) คุณอาจต้องแก้ไขโค้ดเพื่อรวมเงื่อนไขการกรองที่เหมาะสม

#### ถาม: ฉันจะเข้าถึงเนื้อหารูปภาพจริงได้อย่างไรหลังจากได้รับข้อมูลตำแหน่งแล้ว

 ตอบ:`XImage` วัตถุที่ได้รับจาก`ImagePlacement` object แสดงถึงเนื้อหารูปภาพจริง คุณสามารถดำเนินการต่อไปได้`XImage` วัตถุ เช่น การบันทึกลงในไฟล์หรือแสดงในแอปพลิเคชันของคุณ

#### ถาม: ฉันจะทำอย่างไรกับคุณสมบัติรูปภาพที่ได้รับ

ตอบ: คุณสมบัติรูปภาพที่ได้รับ เช่น ความกว้าง ความสูง พิกัด และความละเอียด สามารถใช้เพื่อวัตถุประสงค์ต่างๆ ได้ คุณสามารถวิเคราะห์คุณสมบัติ แสดงให้ผู้ใช้เห็น หรือใช้เป็นอินพุตสำหรับการประมวลผลต่อไป

#### ถาม: ฉันสามารถแก้ไขหรือแก้ไขรูปภาพภายในเอกสาร PDF โดยใช้วิธีนี้ได้หรือไม่

ตอบ: โค้ดที่ให้มาจะเน้นที่การค้นหาและรับข้อมูลตำแหน่งรูปภาพ หากต้องการแก้ไขหรือแก้ไขรูปภาพ คุณอาจต้องรวมฟังก์ชันเพิ่มเติม เช่น การปรับแต่งรูปภาพ โดยใช้ไลบรารี Aspose.PDF

#### ถาม: ฉันจะรวมวิธีนี้เข้ากับโปรเจ็กต์ของตัวเองได้อย่างไร

ตอบ: หากต้องการรวมวิธีการนี้เข้ากับโปรเจ็กต์ของคุณ ให้ทำตามขั้นตอนที่ระบุไว้และแก้ไขโค้ดตามต้องการ คุณสามารถใช้ข้อมูลตำแหน่งรูปภาพและคุณสมบัติที่ได้รับได้ตามความต้องการของแอปพลิเคชันของคุณ

#### ถาม: Aspose.PDF สำหรับ .NET มีคุณสมบัติอื่นๆ ที่เกี่ยวข้องกับการจัดการรูปภาพในเอกสาร PDF หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET มีคุณสมบัติมากมายสำหรับการทำงานกับรูปภาพในเอกสาร PDF รวมถึงการแทรกรูปภาพ การปรับขนาด การหมุน การแยก และอื่นๆ คุณสามารถสำรวจเอกสารและตัวอย่างของห้องสมุดเพื่อค้นพบความสามารถเต็มรูปแบบของห้องสมุด