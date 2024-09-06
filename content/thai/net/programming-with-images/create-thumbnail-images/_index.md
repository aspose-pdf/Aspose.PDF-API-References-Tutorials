---
title: สร้างรูปภาพขนาดย่อในไฟล์ PDF
linktitle: สร้างรูปภาพขนาดย่อในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: สร้างรูปภาพย่อในไฟล์ PDF ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 100
url: /th/net/programming-with-images/create-thumbnail-images/
---
คู่มือนี้จะแนะนำคุณทีละขั้นตอนเกี่ยวกับวิธีสร้างรูปภาพขนาดย่อในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมของคุณเรียบร้อยแล้ว และทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอกสาร

ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไดเรกทอรีที่ถูกต้องสำหรับเอกสารแล้ว แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดพร้อมเส้นทางไปยังไดเร็กทอรีที่มีไฟล์ PDF ของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: รับชื่อไฟล์ PDF ทั้งหมดในไดเร็กทอรี

 ในขั้นตอนนี้เราจะดึงชื่อไฟล์ PDF ทั้งหมดที่มีอยู่ในไดเร็กทอรีที่ระบุโดยใช้ C#`Directory`คลาส ไฟล์จะถูกเก็บไว้ในอาร์เรย์ของสตริง

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## ขั้นตอนที่ 3: เรียกดูไฟล์ PDF ทั้งหมดและหน้าต่างๆ ของไฟล์เหล่านั้น

 ในขั้นตอนนี้ เราจะดูไฟล์ PDF ทั้งหมดและหน้าต่างๆ ของไฟล์เหล่านั้นเพื่อสร้างภาพขนาดย่อ เราจะใช้`for` วนซ้ำเพื่อทำซ้ำผ่านไฟล์ทั้งหมด

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // เปิดเอกสาร PDF
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // ตรวจสอบทุกหน้าของเอกสาร
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // สร้างสตรีมเพื่อบันทึกภาพขนาดย่อ
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             //สร้างวัตถุความละเอียด
             Resolution resolution = new Resolution(300);
            
             // สร้างอุปกรณ์ JPEG ที่มีคุณลักษณะที่ระบุ
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // แปลงหน้าเฉพาะและบันทึกภาพลงในสตรีม
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // ปิดลำธาร
             imageStream.Close();
         }
     }
}
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการสร้างภาพขนาดย่อโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// ดึงชื่อไฟล์ PDF ทั้งหมดในไดเร็กทอรีที่เฉพาะเจาะจง
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// วนซ้ำผ่านรายการไฟล์ทั้งหมดในอาร์เรย์
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
			//JpegDevice jpegDevice = new JpegDevice(500, 700, ความละเอียด, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//แปลงหน้าใดหน้าหนึ่งและบันทึกภาพลงในสตรีม
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//ปิดลำธาร
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## บทสรุป

ขอแสดงความยินดี! คุณได้สร้างภาพย่อจากไฟล์ PDF สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ภาพย่อจะถูกบันทึกไว้ในไดเร็กทอรีที่ระบุ ตอนนี้คุณสามารถใช้ภาพย่อเหล่านี้เพื่อแสดงภาพตัวอย่างไฟล์ PDF ของคุณ

### คำถามที่พบบ่อยสำหรับการสร้างรูปภาพย่อในไฟล์ PDF

#### ถาม: จุดประสงค์ในการสร้างภาพขนาดย่อจากไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

A: การสร้างภาพย่อจากไฟล์ PDF ช่วยให้คุณสามารถสร้างภาพตัวอย่างขนาดเล็กของแต่ละหน้าใน PDF ได้ ซึ่งจะมีประโยชน์ในการดูตัวอย่างและนำทางผ่านเนื้อหาได้อย่างรวดเร็ว

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยอำนวยความสะดวกในการสร้างภาพขนาดย่อจากไฟล์ PDF ได้อย่างไร

 A: Aspose.PDF สำหรับ .NET ให้กระบวนการทีละขั้นตอนในการเปิดเอกสาร PDF ดำเนินการซ้ำผ่านหน้าต่างๆ สร้างรูปภาพขนาดย่อ และบันทึกลงในไดเร็กทอรีที่ระบุโดยใช้`JpegDevice` ระดับ.

#### ถาม: เหตุใดการกำหนดไดเรกทอรีเอกสารก่อนเริ่มสร้างภาพขนาดย่อจึงมีความสำคัญ?

ก: การระบุไดเร็กทอรีเอกสารจะช่วยให้มั่นใจได้ว่าไฟล์ PDF ถูกระบุตำแหน่งอย่างถูกต้องและภาพขนาดย่อที่ได้จะถูกบันทึกไว้ในเส้นทางเอาต์พุตที่ต้องการ

####  ถาม: ทำอย่างไร`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 ก. การ`Document` คลาสนี้ช่วยให้คุณสามารถเปิดและจัดการเอกสาร PDF ได้ ในกรณีนี้ คลาสนี้จะใช้เพื่อโหลดไฟล์ PDF ที่จะใช้สร้างรูปภาพขนาดย่อ

####  ถาม: บทบาทหน้าที่คืออะไร`JpegDevice` class play in the creation of thumbnail images?

 ก. การ`JpegDevice` คลาสนี้มีหน้าที่แปลงไฟล์ PDF เป็นรูปภาพ JPEG ซึ่งใช้เป็นรูปภาพขนาดย่อ โดยคลาสนี้ช่วยให้คุณระบุแอตทริบิวต์ต่างๆ เช่น ความกว้าง ความสูง ความละเอียด และคุณภาพได้

#### ถาม: แต่ละหน้าของเอกสาร PDF จะถูกแปลงเป็นรูปภาพย่อแต่ละภาพได้อย่างไร

 ก. ซ้อนกัน`for` ลูปใช้เพื่อวนซ้ำผ่านไฟล์ PDF แต่ละไฟล์และหน้าต่างๆ ของแต่ละไฟล์ สำหรับแต่ละหน้า อุปกรณ์ JPEG จะถูกสร้างขึ้นด้วยแอตทริบิวต์ที่ระบุ และ`Process` วิธีนี้ใช้เพื่อแปลงหน้าเป็นรูปภาพขนาดย่อและบันทึกลงในสตรีม

#### ถาม: ฉันสามารถปรับความละเอียดหรือคุณภาพของภาพขนาดย่อที่ได้มาในระหว่างขั้นตอนการสร้างได้หรือไม่

A: ใช่ คุณสามารถปรับเปลี่ยนคุณลักษณะต่างๆ เช่น ความละเอียด ความกว้าง ความสูง และคุณภาพ โดยการกำหนดค่า`JpegDevice` วัตถุก่อนที่จะแปลงแต่ละหน้า

#### ถาม: ฉันจะใช้ภาพขนาดย่อที่สร้างขึ้นในโครงการหรือแอปพลิเคชันของฉันหลังจากกระบวนการสร้างได้อย่างไร

A: สามารถใช้รูปภาพขนาดย่อที่ได้เพื่อดูตัวอย่างไฟล์ PDF ได้ ช่วยให้ผู้ใช้สามารถระบุและนำทางผ่านเนื้อหาได้อย่างรวดเร็ว

#### มีข้อจำกัดเกี่ยวกับจำนวนรูปภาพขนาดย่อที่สามารถสร้างจากไฟล์ PDF โดยใช้กระบวนการสร้างนี้หรือไม่

A: จำนวนภาพย่อที่สร้างขึ้นจะขึ้นอยู่กับจำนวนหน้าในเอกสาร PDF แต่ละฉบับ โดยแต่ละหน้าจะถูกแปลงเป็นภาพย่อแยกกัน