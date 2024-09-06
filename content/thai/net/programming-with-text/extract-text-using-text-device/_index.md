---
title: การแยกข้อความโดยใช้ Text Device
linktitle: การแยกข้อความโดยใช้ Text Device
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีแยกข้อความจากเอกสาร PDF โดยใช้ Text Device ใน Aspose.PDF สำหรับ .NET
type: docs
weight: 210
url: /th/net/programming-with-text/extract-text-using-text-device/
---
บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการแยกข้อความจากเอกสาร PDF โดยใช้ Text Device ใน Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ติดตั้งอยู่บนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose อย่างเป็นทางการหรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการแยกข้อความ ให้เพิ่มคำสั่ง using ต่อไปนี้ที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเรกทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณเก็บเอกสารไว้

## ขั้นตอนที่ 4: เปิดเอกสาร PDF
 เปิดเอกสาร PDF ที่มีอยู่โดยใช้`Document` ตัวสร้างและส่งผ่านเส้นทางไปยังไฟล์ PDF อินพุต

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## ขั้นตอนที่ 5: ดึงข้อความโดยใช้ Text Device
 สร้าง`StringBuilder` วัตถุที่จะเก็บข้อความที่แยกออกมา ทำซ้ำผ่านแต่ละหน้าของเอกสารและใช้`TextDevice` เพื่อดึงข้อความจากแต่ละหน้า

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## ขั้นตอนที่ 6: บันทึกข้อความที่แยกออกมา
 ระบุเส้นทางไฟล์เอาท์พุตและบันทึกข้อความที่แยกออกมาลงในไฟล์ข้อความโดยใช้`File.WriteAllText` วิธี.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการสกัดข้อความโดยใช้ Text Device โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//สตริงที่จะเก็บข้อความที่แยกออกมา
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// สร้างอุปกรณ์ข้อความ
		TextDevice textDevice = new TextDevice();
		// ตั้งค่าตัวเลือกการแยกข้อความ - ตั้งค่าโหมดการแยกข้อความ (แบบดิบหรือแบบบริสุทธิ์)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// แปลงหน้าใดหน้าหนึ่งและบันทึกข้อความลงในสตรีม
		textDevice.Process(pdfPage, textStream);
		// แปลงหน้าใดหน้าหนึ่งและบันทึกข้อความลงในสตรีม
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// ปิดกระแสความจำ
		textStream.Close();
		// รับข้อความจากสตรีมหน่วยความจำ
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// บันทึกข้อความที่แยกออกมาในไฟล์ข้อความ
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## บทสรุป
คุณได้แยกข้อความจากเอกสาร PDF สำเร็จแล้วโดยใช้ Text Device ใน Aspose.PDF สำหรับ .NET ข้อความที่แยกออกมาได้รับการบันทึกลงในไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้คืออะไร?

A: บทช่วยสอนนี้ให้คำแนะนำในการแยกข้อความจากเอกสาร PDF โดยใช้ฟีเจอร์ Text Device ใน Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่แนบมาจะสาธิตขั้นตอนที่จำเป็นในการบรรลุภารกิจนี้

#### ถาม: ฉันควรนำเข้าเนมสเปซอะไรบ้าง?

ก: ในไฟล์โค้ดที่คุณวางแผนจะแยกข้อความ ให้ใส่คำสั่ง using ต่อไปนี้ไว้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร?

 ก. ในโค้ด ให้ค้นหาบรรทัดที่เขียนว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะเปิดเอกสาร PDF ที่มีอยู่ได้อย่างไร

 ก: ในขั้นตอนที่ 4 คุณจะเปิดเอกสาร PDF ที่มีอยู่โดยใช้`Document` ตัวสร้างและกำหนดเส้นทางไปยังไฟล์ PDF อินพุต

#### ถาม: ฉันจะดึงข้อความออกมาโดยใช้ Text Device ได้อย่างไร

 A: ขั้นตอนที่ 5 เกี่ยวข้องกับการสร้าง`StringBuilder` วัตถุที่จะเก็บข้อความที่แยกออกมา จากนั้นคุณจะวนซ้ำผ่านแต่ละหน้าของเอกสารและใช้`TextDevice` พร้อมด้วย`TextExtractionOptions` เพื่อดึงข้อความจากแต่ละหน้า

#### ถาม: ฉันจะบันทึกข้อความที่แยกออกมาลงในไฟล์ได้อย่างไร

 ก: ในขั้นตอนที่ 6 คุณจะระบุเส้นทางไฟล์เอาท์พุตและใช้`File.WriteAllText`วิธีการบันทึกข้อความที่แยกออกมาลงในไฟล์ข้อความ

#### ถาม: สิ่งสำคัญที่ได้จากบทช่วยสอนนี้คืออะไร?

A: เมื่อทำตามบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีใช้ฟีเจอร์ Text Device ใน Aspose.PDF สำหรับ .NET เพื่อแยกข้อความจากเอกสาร PDF ข้อความที่แยกออกมาจะถูกบันทึกไว้ในไฟล์เอาต์พุตที่ระบุ ช่วยให้คุณสามารถจัดการและใช้เนื้อหาที่แยกออกมาได้ตามต้องการ