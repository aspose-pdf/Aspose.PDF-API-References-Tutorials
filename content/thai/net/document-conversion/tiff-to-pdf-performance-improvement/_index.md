---
title: การปรับปรุงประสิทธิภาพ TIFF เป็น PDF
linktitle: การปรับปรุงประสิทธิภาพ TIFF เป็น PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนเพื่อปรับปรุงประสิทธิภาพการแปลง TIFF เป็น PDF ด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 310
url: /th/net/document-conversion/tiff-to-pdf-performance-improvement/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณทีละขั้นตอนในการปรับปรุงประสิทธิภาพการแปลงไฟล์ TIFF เป็น PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะให้รายละเอียดซอร์สโค้ด C# ที่ให้มา และแสดงวิธีนำไปใช้ในโครงการของคุณเอง เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถแปลงไฟล์ TIFF เป็น PDF ได้อย่างรวดเร็วและมีประสิทธิภาพยิ่งขึ้น

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 แทนที่`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางที่คุณบันทึกไฟล์ของคุณ

## ขั้นตอนที่ 2: รับรายการไฟล์ TIFF
```csharp
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");
```
รับรายการไฟล์ TIFF ที่มีอยู่ในไดเร็กทอรีที่ระบุ

## ขั้นตอนที่ 3: สร้างอินสแตนซ์วัตถุเอกสาร
```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```
สร้างอินสแตนซ์ของวัตถุเอกสาร

## ขั้นตอนที่ 4: เรียกดูไฟล์และเพิ่มลงในเอกสาร PDF
```csharp
foreach (string myFile in files)
{
     FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
     byte[] tmpBytes = new byte[fs.Length];
     fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

     MemoryStream mystream = new MemoryStream(tmpBytes);
     Bitmap b = new Bitmap(mystream);
     Aspose.Pdf.Page currpage = doc.Pages.Add();

     currpage.PageInfo.Margin.Top = 5;
     currpage.PageInfo.Margin.Bottom = 5;
     currpage.PageInfo.Margin.Left = 5;
     currpage.PageInfo.Margin.Right = 5;

     currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
     currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

     Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

     currpage.Paragraphs.Add(image1);

     image1.IsBlackWhite = true;
     image1.ImageStream = mystream;
     image1.ImageScale = 0.95F;
}
```
 เข้าไปดูไฟล์ TIFF แต่ละไฟล์ แล้วโหลดเป็นไฟล์`Bitmap` วัตถุ จากนั้นเพิ่มลงในเอกสาร PDF พารามิเตอร์ต่างๆ เช่น ระยะขอบ ความละเอียด และขนาดของภาพก็ได้รับการกำหนดค่าเช่นกัน

## ขั้นตอนที่ 5: บันทึกไฟล์ PDF ที่ได้
```csharp
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```
บันทึกเอกสาร PDF ที่เป็นผลลัพธ์ไปยังไดเร็กทอรีที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับการปรับปรุงประสิทธิภาพ TIFF เป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// รับรายการไฟล์ภาพ TIFF
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");

// สร้างอินสแตนซ์วัตถุเอกสาร
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// นำทางผ่านไฟล์ต่างๆ และไฟล์เหล่านั้นในไฟล์ pdf
foreach (string myFile in files)
{

	// โหลดไฟล์ TIFF ทั้งหมดในอาร์เรย์ไบต์
	FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
	byte[] tmpBytes = new byte[fs.Length];
	fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

	MemoryStream mystream = new MemoryStream(tmpBytes);
	Bitmap b = new Bitmap(mystream);
	// สร้างหน้าใหม่ในเอกสาร Pdf
	Aspose.Pdf.Page currpage = doc.Pages.Add();

	// ตั้งค่าระยะขอบเพื่อให้ภาพพอดี ฯลฯ
	currpage.PageInfo.Margin.Top = 5;
	currpage.PageInfo.Margin.Bottom = 5;
	currpage.PageInfo.Margin.Left = 5;
	currpage.PageInfo.Margin.Right = 5;

	currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
	currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

	// สร้างวัตถุรูปภาพ
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

	// เพิ่มรูปภาพลงในคอลเลกชันย่อหน้าของหน้า
	currpage.Paragraphs.Add(image1);

	// ตั้งค่าคุณสมบัติ IsBlackWhite เป็นจริงเพื่อปรับปรุงประสิทธิภาพ
	image1.IsBlackWhite = true;
	// ตั้งค่า ImageStream เป็นวัตถุ MemoryStream
	image1.ImageStream = mystream;
	// กำหนดขนาดภาพที่ต้องการ
	image1.ImageScale = 0.95F;
}

// บันทึก PDF
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีปรับปรุงประสิทธิภาพของการแปลงไฟล์ TIFF เป็น PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เมื่อทำตามขั้นตอนที่ให้ไว้ คุณจะสามารถแปลงไฟล์ TIFF เป็น PDF ได้อย่างรวดเร็วและมีประสิทธิภาพยิ่งขึ้น รับผลลัพธ์ที่แม่นยำและเป็นมืออาชีพพร้อมทั้งเพิ่มประสิทธิภาพการใช้งานของคุณ

### คำถามที่พบบ่อย

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับเอกสาร PDF ในแอปพลิเคชัน C# ได้ มีฟังก์ชันการทำงานที่หลากหลาย รวมถึงการแปลงไฟล์ TIFF เป็น PDF

#### ถาม: เหตุใดฉันจึงต้องการปรับปรุงประสิทธิภาพของการแปลง TIFF เป็น PDF

ตอบ: การปรับปรุงประสิทธิภาพของการแปลง TIFF เป็น PDF สามารถเพิ่มประสิทธิภาพให้กับแอปพลิเคชันของคุณได้อย่างมาก โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการกับไฟล์ TIFF จำนวนมาก การแปลงที่เร็วขึ้นส่งผลให้ประสบการณ์ผู้ใช้ดีขึ้นและลดเวลาการประมวลผล

#### ถาม: ฉันจะตั้งค่าไดเร็กทอรีสำหรับไฟล์ TIFF ได้อย่างไร

 ตอบ: คุณสามารถตั้งค่าไดเร็กทอรีสำหรับไฟล์ TIFF ได้โดยการแทนที่ไฟล์`"YOUR DOCUMENTS DIRECTORY"` ตัวยึดตำแหน่งในโค้ดพร้อมเส้นทางจริงที่มีไฟล์ TIFF ของคุณอยู่

#### ถาม: มีการเพิ่มประสิทธิภาพอะไรบ้างในข้อมูลโค้ดเพื่อปรับปรุงประสิทธิภาพ

 ตอบ: ข้อมูลโค้ดใช้เทคนิคต่างๆ เพื่อปรับปรุงประสิทธิภาพการแปลง เช่น การตั้งค่าระยะขอบ การกำหนดค่าความละเอียดและขนาดของภาพ และการตั้งค่า`IsBlackWhite`ทรัพย์สินให้เป็นจริง การเพิ่มประสิทธิภาพเหล่านี้ช่วยปรับปรุงกระบวนการแปลง

#### ถาม: ฉันสามารถปรับแต่งคุณสมบัติของรูปภาพใน PDF ที่ได้ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งคุณสมบัติของรูปภาพใน PDF ที่ได้ เช่น ขนาด ความละเอียด และระยะขอบ เพื่อให้ได้เค้าโครงและรูปลักษณ์ที่ต้องการ