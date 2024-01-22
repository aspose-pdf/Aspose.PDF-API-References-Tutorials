---
title: อัลกอริทึมของแบรดลีย์
linktitle: อัลกอริทึมของแบรดลีย์
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: แปลงเอกสาร PDF โดยใช้อัลกอริทึมของ Bradley ด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 30
url: /th/net/programming-with-images/bradley-algorithm/
---
คำแนะนำทีละขั้นตอนนี้จะอธิบายวิธีใช้อัลกอริทึมของ Bradley กับ Aspose.PDF สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมของคุณแล้ว และทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไดเร็กทอรีที่ถูกต้องสำหรับเอกสาร แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดพร้อมเส้นทางไปยังไดเร็กทอรีที่มีเอกสาร PDF ของคุณอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดเอกสาร

ในขั้นตอนนี้ เราจะเปิดเอกสาร PDF โดยใช้ไฟล์`Document` คลาสของ Aspose.PDF ใช้`Document` Constructor และส่งเส้นทางไปยังเอกสาร PDF

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## ขั้นตอนที่ 3: กำหนดไฟล์เอาต์พุต

 กำหนดชื่อไฟล์เอาต์พุตสำหรับรูปภาพผลลัพธ์และรูปภาพไบนารี แทนที่`"resultant_out.tif"` และ`"37116-bin_out.tif"` พร้อมชื่อไฟล์เอาต์พุตที่ต้องการ

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## ขั้นตอนที่ 4: สร้างวัตถุความละเอียด

 สร้างก`Resolution`วัตถุเพื่อกำหนดความละเอียดของภาพ TIFF ในตัวอย่างนี้ เราใช้ความละเอียด 300 dpi

```csharp
Resolution resolution = new Resolution(300);
```

## ขั้นตอนที่ 5: สร้างวัตถุ TiffSettings

 สร้างก`TiffSettings`วัตถุเพื่อระบุการตั้งค่าสำหรับไฟล์ TIFF เอาต์พุต ในตัวอย่างนี้ เราใช้การบีบอัด LZW และความลึกของสี 1 บิตต่อพิกเซล (รูปแบบ 1 bpp)

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

## ขั้นตอนที่ 7: แปลงหน้าเฉพาะและบันทึกรูปภาพ

 ใช้`Process` วิธีการของอุปกรณ์ TIFF เพื่อแปลงหน้าเฉพาะของเอกสาร PDF และบันทึกภาพเป็นไฟล์ TIFF ระบุเส้นทางเอาต์พุตของไฟล์

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## ขั้นตอนที่ 8: ขยายภาพโดยใช้อัลกอริธึมของแบรดลีย์

 ใช้`BinarizeBradley` วิธีการของอุปกรณ์ TIFF เพื่อไบนาไรซ์ภาพโดยใช้อัลกอริธึมของแบรดลีย์ วิธีการนี้รับกระแสอินพุตของรูปภาพต้นฉบับและสตรีมเอาต์พุตสำหรับรูปภาพไบนารี ระบุขีดจำกัดไบนารี (0.1 ในตัวอย่างนี้)

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

### ตัวอย่างซอร์สโค้ดสำหรับอัลกอริทึมของแบรดลีย์โดยใช้ Aspose.PDF สำหรับ .NET 
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
//แปลงหน้าเฉพาะและบันทึกภาพเพื่อสตรีม
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

ขอแสดงความยินดี! คุณทำการแปลงเสร็จสมบูรณ์โดยใช้อัลกอริทึมของ Bradley กับ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้รูปภาพผลลัพธ์ในโครงการหรือแอปพลิเคชันของคุณได้แล้ว

### คำถามที่พบบ่อย

#### ถาม: Bradley Algorithm คืออะไร และเกี่ยวข้องกับ Aspose.PDF สำหรับ .NET อย่างไร

ตอบ: Bradley Algorithm เป็นเทคนิคการประมวลผลภาพที่ใช้เพื่อปรับปรุงคุณภาพของภาพและความคมชัด Aspose.PDF สำหรับ .NET มอบวิธีที่สะดวกในการนำอัลกอริทึมของแบรดลีย์ไปใช้กับเอกสาร PDF ส่งผลให้ได้ภาพที่ได้รับการปรับปรุง

#### ถาม: ฉันจะตั้งค่าสภาพแวดล้อมของฉันเพื่อใช้อัลกอริทึมของ Bradley กับ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.PDF สำหรับ .NET อย่างถูกต้อง และกำหนดค่าสภาพแวดล้อมการพัฒนาของคุณแล้ว

#### ถาม: การกำหนดไดเร็กทอรีเอกสารในกระบวนการอัลกอริทึมของแบรดลีย์มีความสำคัญอย่างไร

ตอบ: การระบุไดเร็กทอรีเอกสารที่ถูกต้องเป็นสิ่งสำคัญเพื่อให้แน่ใจว่าเอกสาร PDF อยู่ในเส้นทางที่ถูกต้องสำหรับการประมวลผล

#### ถาม: ฉันจะเปิดเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ในอัลกอริทึมของ Bradley ได้อย่างไร

 ตอบ: ใช้`Document` เพื่อเปิดเอกสาร PDF ซึ่งทำหน้าที่เป็นอินพุตสำหรับกระบวนการ Bradley Algorithm

#### ถาม: จุดประสงค์ของการกำหนดชื่อไฟล์เอาต์พุตสำหรับรูปภาพและรูปภาพไบนารีในกระบวนการอัลกอริทึมของแบรดลีย์คืออะไร

ตอบ: การกำหนดชื่อไฟล์เอาต์พุตทำให้คุณสามารถระบุตำแหน่งที่จะบันทึกรูปภาพผลลัพธ์และรูปภาพไบนารีหลังจากใช้อัลกอริทึมของแบรดลีย์

#### ถาม: การตั้งค่าความละเอียดส่งผลต่อคุณภาพของภาพ TIFF ในกระบวนการ Bradley Algorithm อย่างไร

ตอบ: การตั้งค่าความละเอียดจะกำหนดระดับรายละเอียดและความชัดเจนในภาพ TIFF ที่ได้หลังจากใช้อัลกอริทึมของ Bradley

#### ถาม: ฉันสามารถปรับแต่งการตั้งค่าใดสำหรับภาพ TIFF เอาท์พุตในกระบวนการอัลกอริทึมของแบรดลีย์ได้
ตอบ: คุณสามารถปรับแต่งการตั้งค่า เช่น ประเภทการบีบอัดและความลึกของสี เพื่อให้ได้ผลลัพธ์ที่ต้องการสำหรับภาพ TIFF

#### ถาม: อุปกรณ์ TIFF มีส่วนช่วยในกระบวนการอัลกอริทึมของ Bradley อย่างไร

ตอบ: อุปกรณ์ TIFF ทำหน้าที่เป็นเครื่องมือในการประมวลผลภาพและใช้อัลกอริทึมของแบรดลีย์ ส่งผลให้คุณภาพของภาพดีขึ้น

#### ถาม: ฉันจะแปลงหน้าเฉพาะของเอกสาร PDF เป็นรูปภาพ TIFF ในกระบวนการอัลกอริทึมของแบรดลีย์ได้อย่างไร

 ตอบ: ใช้`Process` วิธีการของอุปกรณ์ TIFF เพื่อแปลงหน้าเฉพาะของเอกสาร PDF เป็นภาพ TIFF ซึ่งสามารถประมวลผลเพิ่มเติมได้โดยใช้ Bradley Algorithm