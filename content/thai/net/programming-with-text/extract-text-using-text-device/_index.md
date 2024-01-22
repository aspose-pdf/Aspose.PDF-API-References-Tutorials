---
title: แยกข้อความโดยใช้อุปกรณ์ข้อความ
linktitle: แยกข้อความโดยใช้อุปกรณ์ข้อความ
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีแยกข้อความจากเอกสาร PDF โดยใช้อุปกรณ์ข้อความใน Aspose.PDF สำหรับ .NET
type: docs
weight: 210
url: /th/net/programming-with-text/extract-text-using-text-device/
---
บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการแยกข้อความจากเอกสาร PDF โดยใช้อุปกรณ์ข้อความใน Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ที่ติดตั้งบนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose หรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการแยกข้อความ ให้เพิ่มคำสั่งต่อไปนี้ที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเร็กทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่เก็บเอกสารของคุณ

## ขั้นตอนที่ 4: เปิดเอกสาร PDF
 เปิดเอกสาร PDF ที่มีอยู่โดยใช้ไฟล์`Document`Constructor และส่งเส้นทางไปยังไฟล์ PDF อินพุต

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## ขั้นตอนที่ 5: แยกข้อความโดยใช้อุปกรณ์ข้อความ
 สร้างก`StringBuilder` วัตถุเพื่อเก็บข้อความที่แยกออกมา วนซ้ำแต่ละหน้าของเอกสารและใช้`TextDevice` เพื่อแยกข้อความออกจากแต่ละหน้า

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
 ระบุเส้นทางของไฟล์เอาต์พุตและบันทึกข้อความที่แยกออกมาเป็นไฟล์ข้อความโดยใช้`File.WriteAllText` วิธี.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### ตัวอย่างซอร์สโค้ดสำหรับแยกข้อความโดยใช้อุปกรณ์ข้อความโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//สตริงเพื่อเก็บข้อความที่แยกออกมา
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// สร้างอุปกรณ์ข้อความ
		TextDevice textDevice = new TextDevice();
		// ตั้งค่าตัวเลือกการแยกข้อความ - ตั้งค่าโหมดการแยกข้อความ (ดิบหรือบริสุทธิ์)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// แปลงหน้าใดหน้าหนึ่งและบันทึกข้อความลงในสตรีม
		textDevice.Process(pdfPage, textStream);
		// แปลงหน้าใดหน้าหนึ่งและบันทึกข้อความลงในสตรีม
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// ปิดสตรีมหน่วยความจำ
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
คุณได้แยกข้อความจากเอกสาร PDF โดยใช้อุปกรณ์ข้อความใน Aspose.PDF สำหรับ .NET สำเร็จแล้ว ข้อความที่แยกออกมาได้รับการบันทึกลงในไฟล์เอาท์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้คืออะไร?

ตอบ: บทช่วยสอนนี้ให้คำแนะนำในการแยกข้อความจากเอกสาร PDF โดยใช้คุณสมบัติอุปกรณ์ข้อความใน Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่แนบมานี้สาธิตขั้นตอนที่จำเป็นเพื่อให้บรรลุภารกิจนี้

#### ถาม: ฉันควรนำเข้าเนมสเปซใด

ตอบ: ในไฟล์โค้ดที่คุณวางแผนจะแยกข้อความ ให้รวมคำสั่งต่อไปนี้ไว้ที่ตอนต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร

 ตอบ: ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะเปิดเอกสาร PDF ที่มีอยู่ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 4 คุณจะเปิดเอกสาร PDF ที่มีอยู่โดยใช้ไฟล์`Document` ตัวสร้างและจัดเตรียมเส้นทางไปยังไฟล์ PDF อินพุต

#### ถาม: ฉันจะแยกข้อความโดยใช้อุปกรณ์ข้อความได้อย่างไร

 ตอบ: ขั้นตอนที่ 5 เกี่ยวข้องกับการสร้าง`StringBuilder` วัตถุเพื่อเก็บข้อความที่แยกออกมา จากนั้นคุณจะวนซ้ำแต่ละหน้าของเอกสารและใช้`TextDevice` พร้อมด้วย`TextExtractionOptions` เพื่อแยกข้อความออกจากแต่ละหน้า

#### ถาม: ฉันจะบันทึกข้อความที่แยกออกมาเป็นไฟล์ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 6 คุณจะต้องระบุเส้นทางของไฟล์เอาต์พุตและใช้ไฟล์`File.WriteAllText`วิธีการบันทึกข้อความที่แยกออกมาเป็นไฟล์ข้อความ

#### ถาม: สิ่งสำคัญที่ได้รับจากบทช่วยสอนนี้คืออะไร

ตอบ: เมื่อทำตามบทช่วยสอนนี้ คุณได้เรียนรู้วิธีใช้ประโยชน์จากคุณสมบัติอุปกรณ์ข้อความใน Aspose.PDF สำหรับ .NET เพื่อแยกข้อความจากเอกสาร PDF ข้อความที่แยกออกมาได้รับการบันทึกลงในไฟล์เอาท์พุตที่ระบุ ทำให้คุณสามารถจัดการและใช้เนื้อหาที่แยกออกมาได้ตามต้องการ