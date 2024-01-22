---
title: ให้ข้อมูลรับรองระหว่าง HTML เป็น PDF
linktitle: ให้ข้อมูลรับรองระหว่าง HTML เป็น PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการแปลง HTML เป็น PDF โดยการให้ข้อมูลประจำตัวด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 240
url: /th/net/document-conversion/provide-credentials-during-html-to-pdf/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการแปลงไฟล์ HTML เป็น PDF พร้อมทั้งให้ข้อมูลประจำตัวเมื่อเข้าถึง URL ที่ปลอดภัยโดยใช้ Aspose.PDF สำหรับ .NET เมื่อทำตามขั้นตอนด้านล่าง คุณจะสามารถแปลงเนื้อหา HTML เป็น PDF โดยใช้ข้อมูลประจำตัวที่เหมาะสม

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีคุณสมบัติตรงตามข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ไลบรารี Aspose.PDF สำหรับ .NET ที่ติดตั้งบนระบบของคุณ
- สภาพแวดล้อมการพัฒนาเช่น Visual Studio

## ขั้นตอนที่ 1: ดึงข้อมูลเนื้อหา HTML ที่ปลอดภัย
ในขั้นตอนนี้ เราจะดึงเนื้อหา HTML ที่ปลอดภัยจาก URL โดยใช้ข้อมูลประจำตัวที่เหมาะสม ใช้รหัสต่อไปนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างคำขอสำหรับ URL
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// หากจำเป็นสำหรับเซิร์ฟเวอร์ ให้ตั้งค่าข้อมูลรับรอง
request.Credentials = CredentialCache.DefaultCredentials;
// รับการตอบกลับ
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// รับสตรีมที่มีเนื้อหาที่ส่งคืนโดยเซิร์ฟเวอร์
Stream dataStream = response. GetResponseStream();
// เปิดสตรีมโดยใช้ StreamReader เพื่อให้เข้าถึงได้ง่าย
StreamReader reader = new StreamReader(dataStream);
// อ่านเนื้อหา
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENTS DIRECTORY"` ด้วยไดเร็กทอรีจริงที่คุณต้องการบันทึกไฟล์ PDF ที่เป็นผลลัพธ์

## ขั้นตอนที่ 2: แปลง HTML เป็น PDF โดยให้ข้อมูลประจำตัว
ตอนนี้เราจะโหลดเนื้อหา HTML ที่ดึงมาและแปลงเป็นรูปแบบ PDF พร้อมกับให้ข้อมูลประจำตัวที่เหมาะสม ใช้รหัสต่อไปนี้:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// โหลดไฟล์ HTML
Document pdfDocument = new Document(stream, options);
```

## ขั้นตอนที่ 3: บันทึกไฟล์ PDF ที่ได้
สุดท้ายเราจะบันทึกไฟล์ PDF ที่ได้ ใช้รหัสต่อไปนี้:

```csharp
// บันทึกไฟล์ PDF ที่ได้
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 โค้ดด้านบนจะบันทึกไฟล์ PDF ที่เป็นผลลัพธ์พร้อมชื่อไฟล์`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### ตัวอย่างซอร์สโค้ดสำหรับการให้ข้อมูลประจำตัวระหว่าง HTML เป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
try
{
	
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// สร้างคำขอสำหรับ URL
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// หากเซิร์ฟเวอร์ต้องการ ให้ตั้งค่าข้อมูลรับรอง
	request.Credentials = CredentialCache.DefaultCredentials;
	// รับการตอบกลับ
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// รับสตรีมที่มีเนื้อหาที่ส่งคืนโดยเซิร์ฟเวอร์
	Stream dataStream = response.GetResponseStream();
	// เปิดสตรีมโดยใช้ StreamReader เพื่อให้เข้าถึงได้ง่าย
	StreamReader reader = new StreamReader(dataStream);
	// อ่านเนื้อหา
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// โหลดไฟล์ HTML
	Document pdfDocument = new Document(stream, options);
	// บันทึกไฟล์ผลลัพธ์
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงกระบวนการทีละขั้นตอนในการแปลงไฟล์ HTML เป็น PDF พร้อมทั้งให้ข้อมูลประจำตัวเมื่อเข้าถึง URL ที่ปลอดภัยโดยใช้ Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำที่สรุปไว้ข้างต้น คุณจะสามารถแปลงเนื้อหา HTML เป็น PDF ได้สำเร็จพร้อมทั้งให้ข้อมูลประจำตัวที่ถูกต้อง

### คำถามที่พบบ่อย

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับเอกสาร PDF ในแอปพลิเคชัน C# ได้ มีฟังก์ชันการทำงานที่หลากหลาย รวมถึงการแปลง HTML เป็น PDF

#### ถาม: ฉันจะดึงเนื้อหา HTML ที่ปลอดภัยจาก URL ได้อย่างไร

 ตอบ: หากต้องการดึงเนื้อหา HTML ที่ปลอดภัยจาก URL คุณสามารถใช้ไฟล์`WebRequest` คลาสใน C # ตรวจสอบให้แน่ใจว่าได้ตั้งค่าข้อมูลประจำตัวที่เหมาะสมโดยใช้`Credentials` คุณสมบัติ.

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับบทช่วยสอนนี้มีอะไรบ้าง

ตอบ: ก่อนที่จะดำเนินการบทช่วยสอนต่อ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ไลบรารี Aspose.PDF สำหรับ .NET ที่ติดตั้งบนระบบของคุณ
- สภาพแวดล้อมการพัฒนาเช่น Visual Studio

#### ถาม: Aspose.PDF สำหรับ .NET จัดการกับทรัพยากรภายนอกขณะแปลง HTML เป็น PDF อย่างไร

 ตอบ: Aspose.PDF สำหรับ .NET มี`HtmlLoadOptions`คลาสเพื่อจัดการทรัพยากรภายนอกระหว่างการแปลง HTML เป็น PDF คุณสามารถตั้งค่าข้อมูลรับรองทรัพยากรภายนอกได้โดยใช้`ExternalResourcesCredentials` คุณสมบัติ.

#### ถาม: ฉันสามารถปรับแต่งชื่อไฟล์สำหรับไฟล์ PDF ที่ได้ได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งชื่อไฟล์สำหรับไฟล์ PDF ที่ได้ โดยการแก้ไขโค้ดที่บันทึกเอกสาร PDF เพียงเปลี่ยนชื่อไฟล์ที่ต้องการในไฟล์`pdfDocument.Save()` วิธี.