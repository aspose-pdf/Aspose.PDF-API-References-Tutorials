---
title: อัลกอริธึมแบรดลีย์
linktitle: อัลกอริธึมแบรดลีย์
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: แปลงเอกสาร PDF โดยใช้อัลกอริทึม Bradley ด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 30
url: /th/net/programming-with-images/bradley-algorithm/
---
คู่มือทีละขั้นตอนนี้จะอธิบายวิธีใช้ Bradley Algorithm กับ Aspose.PDF สำหรับ .NET โปรดตรวจสอบว่าคุณได้ตั้งค่าสภาพแวดล้อมของคุณเรียบร้อยแล้ว และทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอกสาร

ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไดเรกทอรีที่ถูกต้องสำหรับเอกสารแล้ว แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดพร้อมเส้นทางไปยังไดเร็กทอรีที่เอกสาร PDF ของคุณอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดเอกสาร

 ในขั้นตอนนี้เราจะเปิดเอกสาร PDF โดยใช้`Document` คลาสของ Aspose.PDF ใช้`Document` สร้างและส่งเส้นทางไปยังเอกสาร PDF

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## ขั้นตอนที่ 3: กำหนดไฟล์เอาท์พุต

 กำหนดชื่อไฟล์เอาต์พุตสำหรับภาพผลลัพธ์และภาพไบนารี แทนที่`"resultant_out.tif"` และ`"37116-bin_out.tif"` พร้อมชื่อที่ต้องการให้กับไฟล์เอาท์พุต

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## ขั้นตอนที่ 4: สร้างวัตถุ Resolution

 สร้าง`Resolution` วัตถุสำหรับตั้งค่าความละเอียดของภาพ TIFF ในตัวอย่างนี้ เราใช้ความละเอียด 300 dpi

```csharp
Resolution resolution = new Resolution(300);
```

## ขั้นตอนที่ 5: สร้างวัตถุ TiffSettings

 สร้าง`TiffSettings` วัตถุเพื่อระบุการตั้งค่าสำหรับไฟล์ TIFF เอาต์พุต ในตัวอย่างนี้ เราใช้การบีบอัด LZW และความลึกของสี 1 บิตต่อพิกเซล (รูปแบบ 1 bpp)

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## ขั้นตอนที่ 6: สร้างอุปกรณ์ TIFF

 สร้างอุปกรณ์ TIFF โดยใช้`TiffDevice` วัตถุ โดยระบุความละเอียดและการตั้งค่า TIFF

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## ขั้นตอนที่ 7: แปลงหน้าเฉพาะและบันทึกภาพ

 ใช้`Process` วิธีการของอุปกรณ์ TIFF เพื่อแปลงหน้าเฉพาะของเอกสาร PDF และบันทึกภาพลงในไฟล์ TIFF ระบุเส้นทางเอาต์พุตของไฟล์

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## ขั้นตอนที่ 8: แปลงภาพเป็นไบนารีโดยใช้อัลกอริทึมแบรดลีย์

 ใช้`BinarizeBradley`วิธีการของอุปกรณ์ TIFF เพื่อแปลงภาพเป็นไบนารีโดยใช้อัลกอริทึม Bradley วิธีนี้ใช้สตรีมอินพุตของภาพต้นฉบับและสตรีมเอาท์พุตสำหรับภาพไบนารี ระบุเกณฑ์การแปลงเป็นไบนารี (0.1 ในตัวอย่างนี้)

```csharp
using (FileStream

  inStream = new FileStream(outputImageFile, FileMode.Open))
{
using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
{
tiffDevice. Binarize Bradley(inStream, outStream, 0.1);
}
}
```

### ตัวอย่างโค้ดต้นฉบับสำหรับ Bradley Algorithm โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// สร้างวัตถุความละเอียด
Resolution resolution = new Resolution(300);
// สร้างวัตถุ TiffSettings
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// สร้างอุปกรณ์ TIFF
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// แปลงหน้าใดหน้าหนึ่งและบันทึกภาพลงในสตรีม
tiffDevice.Process(pdfDocument, outputImageFile);
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
	using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
	{
		tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
	}
}
System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```

## บทสรุป

ขอแสดงความยินดี! คุณได้ดำเนินการแปลงไฟล์โดยใช้อัลกอริทึม Bradley กับ Aspose.PDF สำหรับ .NET สำเร็จแล้ว ตอนนี้คุณสามารถใช้รูปภาพที่ได้ในโครงการหรือแอปพลิเคชันของคุณได้แล้ว

### คำถามที่พบบ่อย

#### ถาม: อัลกอริทึม Bradley คืออะไรและเกี่ยวข้องกับ Aspose.PDF สำหรับ .NET อย่างไร

A: อัลกอริธึม Bradley เป็นเทคนิคการประมวลผลภาพที่ใช้เพื่อปรับปรุงคุณภาพและความชัดเจนของภาพ Aspose.PDF สำหรับ .NET มอบวิธีที่สะดวกในการนำอัลกอริธึม Bradley ไปใช้กับเอกสาร PDF ส่งผลให้ภาพมีการปรับปรุงดีขึ้น

#### ถาม: ฉันจะตั้งค่าสภาพแวดล้อมสำหรับการใช้ Bradley Algorithm กับ Aspose.PDF สำหรับ .NET ได้อย่างไร

ก: ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณได้ติดตั้ง Aspose.PDF สำหรับ .NET อย่างถูกต้อง และมีการกำหนดค่าสภาพแวดล้อมการพัฒนาของคุณแล้ว

#### ถาม: ความสำคัญของการกำหนดไดเรกทอรีเอกสารในกระบวนการ Bradley Algorithm คืออะไร

A: การระบุไดเรกทอรีเอกสารที่ถูกต้องเป็นสิ่งสำคัญเพื่อให้แน่ใจว่าเอกสาร PDF อยู่ในเส้นทางที่ถูกต้องสำหรับการประมวลผล

#### ถาม: ฉันจะเปิดเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ในอัลกอริทึม Bradley ได้อย่างไร

 ก. ใช้`Document` คลาสเพื่อเปิดเอกสาร PDF ซึ่งทำหน้าที่เป็นอินพุตสำหรับกระบวนการอัลกอริทึม Bradley

#### ถาม: จุดประสงค์ของการกำหนดชื่อไฟล์เอาต์พุตสำหรับรูปภาพและรูปภาพไบนารีในกระบวนการ Bradley Algorithm คืออะไร

A: การกำหนดชื่อไฟล์เอาต์พุตช่วยให้คุณระบุได้ว่าจะบันทึกรูปภาพผลลัพธ์และรูปภาพไบนารีไว้ที่ใดหลังจากใช้อัลกอริทึม Bradley แล้ว

#### ถาม: การตั้งค่าความละเอียดส่งผลต่อคุณภาพของภาพ TIFF ในกระบวนการ Bradley Algorithm อย่างไร

A: การตั้งค่าความละเอียดจะกำหนดระดับรายละเอียดและความชัดเจนในภาพ TIFF ที่ได้หลังจากใช้อัลกอริทึม Bradley

#### ถาม: ฉันสามารถปรับแต่งการตั้งค่าใดให้กับภาพ TIFF เอาต์พุตในกระบวนการ Bradley Algorithm ได้บ้าง
A: คุณสามารถปรับแต่งการตั้งค่าต่างๆ เช่น ประเภทการบีบอัดและความลึกของสี เพื่อให้ได้เอาต์พุตภาพ TIFF ตามต้องการ

#### ถาม: อุปกรณ์ TIFF มีส่วนสนับสนุนกระบวนการ Bradley Algorithm อย่างไร

A: อุปกรณ์ TIFF ทำหน้าที่เป็นเครื่องมือในการประมวลผลภาพและใช้อัลกอริทึม Bradley ส่งผลให้คุณภาพของภาพดีขึ้น

#### ถาม: ฉันจะแปลงหน้าเฉพาะของเอกสาร PDF เป็นภาพ TIFF ในกระบวนการอัลกอริทึม Bradley ได้อย่างไร

 ก. ใช้ประโยชน์ของ`Process` วิธีการของอุปกรณ์ TIFF เพื่อแปลงหน้าเฉพาะของเอกสาร PDF ให้เป็นภาพ TIFF ซึ่งสามารถประมวลผลเพิ่มเติมได้โดยใช้อัลกอริทึม Bradley