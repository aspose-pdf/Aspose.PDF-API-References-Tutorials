---
title: สร้างภาพขนาดย่อในไฟล์ PDF
linktitle: สร้างภาพขนาดย่อในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: สร้างภาพขนาดย่อในไฟล์ PDF ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 100
url: /th/net/programming-with-images/create-thumbnail-images/
---
คู่มือนี้จะแนะนำคุณทีละขั้นตอนเกี่ยวกับวิธีสร้างภาพขนาดย่อในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมของคุณแล้ว และทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไดเร็กทอรีที่ถูกต้องสำหรับเอกสาร แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดพร้อมเส้นทางไปยังไดเร็กทอรีที่มีไฟล์ PDF ของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: รับชื่อของไฟล์ PDF ทั้งหมดในไดเร็กทอรี

 ในขั้นตอนนี้ เราจะดึงชื่อของไฟล์ PDF ทั้งหมดที่มีอยู่ในไดเร็กทอรีที่ระบุโดยใช้ C#`Directory` ระดับ. ไฟล์จะถูกจัดเก็บไว้ในอาร์เรย์ของสตริง

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## ขั้นตอนที่ 3: เรียกดูไฟล์ PDF ทั้งหมดและหน้าของพวกเขา

 ในขั้นตอนนี้ เราจะดูไฟล์ PDF ทั้งหมดและหน้าต่างๆ เพื่อสร้างภาพขนาดย่อของรูปภาพ เราจะใช้ก`for` วนซ้ำเพื่อวนซ้ำไฟล์ทั้งหมด

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     //เปิดเอกสาร PDF
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // ไล่อ่านทุกหน้าของเอกสาร
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // สร้างกระแสเพื่อบันทึกภาพขนาดย่อ
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // สร้างวัตถุความละเอียด
             Resolution resolution = new Resolution(300);
            
             // สร้างอุปกรณ์ JPEG ด้วยคุณสมบัติที่ระบุ
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // แปลงหน้าเฉพาะและบันทึกภาพลงในสตรีม
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // ปิดสตรีม
             imageStream.Close();
         }
     }
}
```

### ตัวอย่างซอร์สโค้ดสำหรับสร้างภาพขนาดย่อโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ดึงข้อมูลชื่อของไฟล์ PDF ทั้งหมดในไดเร็กทอรีเฉพาะ
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// วนซ้ำรายการไฟล์ทั้งหมดในอาร์เรย์
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//เปิดเอกสาร
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//สร้างวัตถุความละเอียด
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = JpegDevice ใหม่ (500, 700, ความละเอียด, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//แปลงหน้าเฉพาะและบันทึกภาพเพื่อสตรีม
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//ปิดสตรีม
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## บทสรุป

ขอแสดงความยินดี! คุณสร้างภาพขนาดย่อของรูปภาพจากไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว ภาพขนาดย่อของรูปภาพจะถูกบันทึกไว้ในไดเร็กทอรีที่ระบุ ตอนนี้คุณสามารถใช้ภาพขนาดย่อเหล่านี้เพื่อแสดงตัวอย่างภาพไฟล์ PDF ของคุณได้

### คำถามที่พบบ่อยสำหรับการสร้างภาพขนาดย่อในไฟล์ PDF

#### ถาม: จุดประสงค์ของการสร้างภาพขนาดย่อจากไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: การสร้างภาพขนาดย่อจากไฟล์ PDF ช่วยให้คุณสร้างภาพตัวอย่างเล็กๆ น้อยๆ ของแต่ละหน้าใน PDF ได้ ซึ่งมีประโยชน์สำหรับการดูตัวอย่างและเลื่อนดูเนื้อหาอย่างรวดเร็ว

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยอำนวยความสะดวกในการสร้างภาพขนาดย่อจากไฟล์ PDF ได้อย่างไร

ตอบ: Aspose.PDF สำหรับ .NET มีกระบวนการทีละขั้นตอนในการเปิดเอกสาร PDF วนซ้ำหน้าต่างๆ สร้างภาพขนาดย่อ และบันทึกลงในไดเร็กทอรีที่ระบุโดยใช้`JpegDevice` ระดับ.

#### ถาม: เหตุใดการกำหนดไดเร็กทอรีเอกสารก่อนเริ่มสร้างภาพขนาดย่อจึงเป็นสิ่งสำคัญ

ตอบ: การระบุไดเร็กทอรีเอกสารช่วยให้มั่นใจว่าไฟล์ PDF อยู่ในตำแหน่งที่ถูกต้อง และภาพขนาดย่อที่ได้จะถูกบันทึกในเส้นทางเอาต์พุตที่ต้องการ

####  ถาม: เป็นยังไงบ้าง`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 ตอบ:`Document` class ช่วยให้คุณสามารถเปิดและจัดการเอกสาร PDF ในกรณีนี้ ใช้เพื่อโหลดไฟล์ PDF ที่จะใช้สร้างภาพขนาดย่อ

####  ถาม: มีบทบาทอะไร`JpegDevice` class play in the creation of thumbnail images?

 ตอบ:`JpegDevice` class รับผิดชอบในการแปลงหน้า PDF เป็นภาพ JPEG ซึ่งใช้เป็นภาพขนาดย่อ ช่วยให้คุณสามารถระบุคุณลักษณะต่างๆ เช่น ความกว้าง ความสูง ความละเอียด และคุณภาพ

#### ถาม: แต่ละหน้าของเอกสาร PDF ถูกแปลงเป็นภาพย่อแต่ละภาพอย่างไร

 A: ซ้อนกัน`for`loop ใช้เพื่อวนซ้ำไฟล์ PDF แต่ละไฟล์และหน้าต่างๆ สำหรับแต่ละหน้า อุปกรณ์ JPEG จะถูกสร้างขึ้นพร้อมกับแอตทริบิวต์ที่ระบุ และ`Process` วิธีการแปลงหน้าเป็นภาพขนาดย่อและบันทึกลงในสตรีม

#### ถาม: ฉันสามารถปรับความละเอียดหรือคุณภาพของภาพขนาดย่อที่ได้ในระหว่างกระบวนการสร้างได้หรือไม่

 ตอบ: ได้ คุณสามารถแก้ไขคุณลักษณะต่างๆ เช่น ความละเอียด ความกว้าง ความสูง และคุณภาพ ได้โดยการกำหนดค่า`JpegDevice` วัตถุก่อนที่จะแปลงแต่ละหน้า

#### ถาม: ฉันจะใช้ภาพขนาดย่อที่สร้างขึ้นในโปรเจ็กต์หรือแอปพลิเคชันของฉันหลังจากกระบวนการสร้างได้อย่างไร

ตอบ: ภาพขนาดย่อที่ได้สามารถนำมาใช้เพื่อแสดงตัวอย่างไฟล์ PDF ได้ ช่วยให้ผู้ใช้ระบุและนำทางไปยังเนื้อหาได้อย่างรวดเร็ว

#### : มีการจำกัดจำนวนภาพขนาดย่อที่สามารถสร้างจากไฟล์ PDF โดยใช้กระบวนการสร้างนี้หรือไม่?

ตอบ: จำนวนภาพขนาดย่อที่สร้างขึ้นขึ้นอยู่กับจำนวนหน้าในเอกสาร PDF แต่ละฉบับ แต่ละหน้าจะถูกแปลงเป็นภาพขนาดย่อที่แยกจากกัน