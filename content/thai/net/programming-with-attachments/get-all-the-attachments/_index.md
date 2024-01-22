---
title: รับไฟล์แนบทั้งหมดในไฟล์ PDF
linktitle: รับไฟล์แนบทั้งหมดในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีรับไฟล์แนบทั้งหมดในไฟล์ PDF ด้วย Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนเพื่อการจัดการที่ง่ายดาย
type: docs
weight: 40
url: /th/net/programming-with-attachments/get-all-the-attachments/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# ต่อไปนี้ทีละขั้นตอนเพื่อรับไฟล์แนบทั้งหมดในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET

ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณก่อนที่จะเริ่มต้น มีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# ด้วย

### ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในซอร์สโค้ดที่ให้มา คุณต้องระบุไดเร็กทอรีที่มีไฟล์ PDF ที่คุณต้องการรับไฟล์แนบ เปลี่ยนตัวแปร "dataDir" เป็นไดเร็กทอรีที่ต้องการ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### ขั้นตอนที่ 2: เปิดเอกสาร PDF ที่มีอยู่

เราเปิดเอกสาร PDF ที่มีอยู่โดยใช้เส้นทางที่ระบุ

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### ขั้นตอนที่ 3: การรับคอลเลกชันไฟล์แนบ

เราได้รับการรวบรวมเอกสารแนบจากเอกสาร

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### ขั้นตอนที่ 4: การดึงเอกสารแนบ

เราผ่านคอลเลกชันเพื่อรับไฟล์แนบทั้งหมดและแสดงข้อมูล เรายังบันทึกไฟล์แนบในแต่ละไฟล์ด้วย

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// ตรวจสอบว่าพารามิเตอร์วัตถุมีข้อมูลเพิ่มเติมหรือไม่
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// ดึงเอกสารแนบและบันทึกเป็นไฟล์
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### ตัวอย่างซอร์สโค้ดสำหรับรับไฟล์แนบทั้งหมดโดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// รับคอลเลกชันไฟล์ที่ฝังตัว
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// รับจำนวนไฟล์ที่ฝัง
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// วนซ้ำคอลเลกชันเพื่อรับไฟล์แนบทั้งหมด
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
	Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
	//ตรวจสอบว่าวัตถุพารามิเตอร์มีพารามิเตอร์หรือไม่
	if (fileSpecification.Params != null)
	{
		Console.WriteLine("CheckSum: {0}",
		fileSpecification.Params.CheckSum);
		Console.WriteLine("Creation Date: {0}",
		fileSpecification.Params.CreationDate);
		Console.WriteLine("Modification Date: {0}",
		fileSpecification.Params.ModDate);
		Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
	}
	// รับไฟล์แนบและเขียนลงไฟล์หรือสตรีม
	byte[] fileContent = new byte[fileSpecification.Contents.Length];
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายวิธีรับไฟล์แนบทั้งหมดจากไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อแยกและจัดการไฟล์แนบจากไฟล์ PDF ของคุณได้

## คำถามที่พบบ่อยสำหรับการรับไฟล์แนบทั้งหมดในรูปแบบไฟล์ PDF

#### ถาม: เหตุใดฉันจึงต้องดึงเอกสารแนบทั้งหมดจากเอกสาร PDF

ตอบ: การเรียกเอกสารแนบช่วยให้คุณสามารถเข้าถึงและจัดการไฟล์เพิ่มเติมที่ฝังอยู่ภายใน PDF ซึ่งอาจมีประโยชน์สำหรับการเก็บถาวร การแชร์ หรือการประมวลผลเพิ่มเติม

#### ถาม: ไฟล์ประเภทใดบ้างที่สามารถแนบไปกับเอกสาร PDF ได้

ตอบ: เอกสาร PDF สามารถมีไฟล์แนบได้หลายประเภท รวมถึงรูปภาพ เอกสาร สเปรดชีต ไฟล์เสียง และอื่นๆ

#### ถาม: บทช่วยสอนนี้ช่วยฉันดึงไฟล์แนบจาก PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนและซอร์สโค้ด C# เพื่อเข้าถึงและเรียกค้นไฟล์แนบทั้งหมดภายในเอกสาร PDF

#### ถาม: ฉันสามารถดึงไฟล์แนบเฉพาะแทนไฟล์แนบทั้งหมดโดยใช้บทช่วยสอนนี้ได้หรือไม่

ตอบ: ได้ คุณสามารถแก้ไขโค้ดที่ให้มาเพื่อเลือกรับไฟล์แนบได้ตามความต้องการของคุณ

#### ถาม: ฉันสามารถรับข้อมูลใดบ้างเกี่ยวกับไฟล์แนบแต่ละรายการโดยใช้บทช่วยสอนนี้

ตอบ: บทช่วยสอนนี้สาธิตวิธีการดึงและแสดงรายละเอียด เช่น ชื่อไฟล์แนบ คำอธิบาย ประเภท MIME วันที่สร้าง วันที่แก้ไข และขนาด

#### ถาม: ไฟล์แนบที่ได้รับจะถูกบันทึกโดยใช้บทช่วยสอนนี้อย่างไร

ตอบ: บทช่วยสอนจะแนะนำคุณเกี่ยวกับการบันทึกไฟล์แนบที่ดึงมาแต่ละไฟล์เป็นไฟล์แยกต่างหากในไดเร็กทอรีที่ระบุ

#### ถาม: ฉันสามารถใช้ความรู้นี้เพื่อแยกไฟล์แนบจากไฟล์ PDF ที่มีการป้องกันด้วยรหัสผ่านได้หรือไม่

ตอบ: ได้ คุณสามารถใช้หลักการที่คล้ายกันเพื่อดึงไฟล์แนบจากไฟล์ PDF ที่มีการป้องกันด้วยรหัสผ่านโดยใช้ Aspose.PDF สำหรับ .NET

#### ถาม: Aspose.PDF สำหรับ .NET อำนวยความสะดวกในการเรียกค้นไฟล์แนบอย่างไร

ตอบ: Aspose.PDF สำหรับ .NET มี API ที่ใช้งานง่ายซึ่งช่วยให้คุณเข้าถึงและจัดการไฟล์แนบในเอกสาร PDF ได้อย่างง่ายดาย

#### ถาม: มีสถานการณ์เฉพาะใดบ้างที่แนะนำให้เรียกข้อมูลไฟล์แนบ

ตอบ: การดึงไฟล์แนบมีประโยชน์เมื่อคุณต้องการเข้าถึงไฟล์ที่ฝังอยู่ภายใน PDF เช่น การแยกรูปภาพ ไฟล์เสียง หรือเอกสารเพิ่มเติม