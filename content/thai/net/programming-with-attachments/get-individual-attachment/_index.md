---
title: รับไฟล์แนบส่วนบุคคลในไฟล์ PDF
linktitle: รับไฟล์แนบส่วนบุคคลในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีรับไฟล์แนบแต่ละรายการในไฟล์ PDF ด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 60
url: /th/net/programming-with-attachments/get-individual-attachment/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# ต่อไปนี้ทีละขั้นตอนเพื่อรับไฟล์แนบแต่ละไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET

ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณก่อนที่จะเริ่มต้น มีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# ด้วย

### ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในซอร์สโค้ดที่ให้มา คุณจะต้องระบุไดเร็กทอรีที่มีไฟล์ PDF ที่คุณต้องการรับไฟล์แนบแต่ละรายการ เปลี่ยนตัวแปร "dataDir" เป็นไดเร็กทอรีที่ต้องการ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### ขั้นตอนที่ 2: เปิดเอกสาร PDF ที่มีอยู่

เราเปิดเอกสาร PDF ที่มีอยู่โดยใช้เส้นทางที่ระบุ

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
```

### ขั้นตอนที่ 3: การขอรับเอกสารแนบเฉพาะ

เราเรียกข้อมูลเอกสารแนบเฉพาะจากคอลเลกชันเอกสารแนบของเอกสาร ในตัวอย่างนี้ เราได้รับไฟล์แนบแรกโดยใช้ดัชนี 1

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### ขั้นตอนที่ 4: รับคุณสมบัติไฟล์

เราแสดงคุณสมบัติไฟล์แนบ เช่น ชื่อ คำอธิบาย ประเภท MIME แฮชควบคุม วันที่สร้าง วันที่แก้ไข และขนาด

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// ตรวจสอบว่าพารามิเตอร์วัตถุมีข้อมูลเพิ่มเติมหรือไม่
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### ขั้นตอนที่ 5: ดึงไฟล์แนบและบันทึกลงไฟล์

เราดึงเนื้อหาของไฟล์แนบและบันทึกลงในไฟล์ข้อความ ในตัวอย่างนี้ ไฟล์จะถูกบันทึกด้วยชื่อ "test_out.txt"

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### ตัวอย่างซอร์สโค้ดสำหรับรับไฟล์แนบส่วนบุคคลโดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
// รับไฟล์ฝังตัวโดยเฉพาะ
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// รับคุณสมบัติไฟล์
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
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
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายวิธีรับไฟล์แนบแต่ละรายการจากไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อแยกและบันทึกไฟล์แนบจากไฟล์ PDF ของคุณได้

### คำถามที่พบบ่อยในการรับไฟล์แนบเป็นไฟล์ PDF

#### ถาม: จุดประสงค์ในการรับไฟล์แนบแต่ละรายการจากเอกสาร PDF คืออะไร

ตอบ: การได้รับไฟล์แนบแต่ละรายการทำให้คุณสามารถแยกและบันทึกไฟล์ฝังตัวเฉพาะภายใน PDF ได้ ซึ่งอาจเป็นประโยชน์สำหรับการวิเคราะห์หรือการจัดการเพิ่มเติม

#### ถาม: ฉันจะได้รับประโยชน์จากบทช่วยสอนนี้ในงานที่เกี่ยวข้องกับ PDF ได้อย่างไร

ตอบ: บทช่วยสอนนี้จะให้คำแนะนำทีละขั้นตอนและซอร์สโค้ด C# เพื่อดึงและบันทึกไฟล์แนบเฉพาะจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET

#### ถาม: ฉันสามารถเข้าถึงคุณสมบัติไฟล์แนบใดบ้างโดยใช้บทช่วยสอนนี้

ตอบ: คุณสามารถเข้าถึงคุณสมบัติของไฟล์แนบได้ เช่น ชื่อ คำอธิบาย ประเภท MIME แฮชควบคุม วันที่สร้าง วันที่แก้ไข และขนาดของไฟล์แนบที่ระบุ

#### ถาม: ฉันสามารถแก้ไขโค้ดเพื่อรับไฟล์แนบอื่นนอกเหนือจากไฟล์แนบแรกได้หรือไม่

 ตอบ: แน่นอน คุณสามารถปรับดัชนีได้ (เช่น`pdfDocument.EmbeddedFiles[1]`) เพื่อดึงไฟล์แนบในดัชนีต่างๆ ภายใน PDF

#### ถาม: ฉันจะบันทึกไฟล์แนบที่ดึงมาลงในไฟล์ได้อย่างไร

ตอบ: บทช่วยสอนนี้มีโค้ดเพื่อดึงเนื้อหาของไฟล์แนบและบันทึกลงในไฟล์ข้อความที่มีชื่อที่ระบุ

#### ถาม: คุณสมบัติ "ตรวจสอบแฮช" ในข้อมูลไฟล์แนบมีความสำคัญอย่างไร

ตอบ: คุณสมบัติ "ตรวจสอบแฮช" แสดงถึงค่าแฮชควบคุมของไฟล์แนบ ซึ่งสามารถใช้เพื่อตรวจสอบความสมบูรณ์ของไฟล์แนบ

#### ถาม: ฉันสามารถขยายความรู้นี้เพื่อแยกไฟล์แนบที่มีเกณฑ์เฉพาะ เช่น ประเภทไฟล์ ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับปรุงโค้ดเพื่อกรองไฟล์แนบตามเกณฑ์เฉพาะ เช่น ประเภทไฟล์หรือคุณสมบัติอื่นๆ ได้

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยให้กระบวนการแตกไฟล์แนบแต่ละรายการง่ายขึ้นได้อย่างไร

ตอบ: Aspose.PDF สำหรับ .NET มี API ที่ใช้งานง่ายซึ่งอำนวยความสะดวกในการแยกและจัดการไฟล์แนบภายในเอกสาร PDF

#### ถาม: บทช่วยสอนนี้เกี่ยวข้องกับไฟล์ PDF ที่มีการป้องกันด้วยรหัสผ่านด้วยหรือไม่

ตอบ: ได้ คุณสามารถปรับใช้เทคนิคที่คล้ายกันเพื่อดึงไฟล์แนบแต่ละรายการจากไฟล์ PDF ที่มีการป้องกันด้วยรหัสผ่านโดยใช้ Aspose.PDF สำหรับ .NET
