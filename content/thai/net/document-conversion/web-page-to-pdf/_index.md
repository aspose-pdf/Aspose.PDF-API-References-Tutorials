---
title: หน้าเว็บเป็น PDF
linktitle: หน้าเว็บเป็น PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการแปลงหน้าเว็บเป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 320
url: /th/net/document-conversion/web-page-to-pdf/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณทีละขั้นตอนเกี่ยวกับวิธีแปลงเว็บเพจเป็น PDF โดยใช้ Aspose.PDF สำหรับไลบรารี .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มา และแสดงวิธีนำไปใช้ในโครงการของคุณเอง เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถแปลงหน้าเว็บเป็นเอกสาร PDF ได้อย่างง่ายดาย

## การแนะนำ
การแปลงหน้าเว็บเป็นรูปแบบ PDF เป็นข้อกำหนดทั่วไปในหลายแอปพลิเคชัน ด้วยการแปลงเนื้อหาเว็บเป็น PDF คุณสามารถรักษาเค้าโครง การจัดรูปแบบ และรูปภาพของหน้าเว็บต้นฉบับได้อย่างง่ายดาย Aspose.PDF สำหรับ .NET เป็นไลบรารีที่ทรงพลังที่ช่วยให้คุณทำการแปลงได้อย่างมีประสิทธิภาพและแม่นยำ

## ความต้องการ
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว
- Aspose.PDF สำหรับไลบรารี .NET (คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose อย่างเป็นทางการ)
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C#


## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น

## ขั้นตอนที่ 2: สร้างคำขอเว็บ
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
สร้างออบเจ็กต์คำขอเว็บและระบุ URL ของหน้าเว็บที่คุณต้องการแปลง คุณสามารถแทนที่ URL ด้วยหน้าเว็บที่ต้องการได้

## ขั้นตอนที่ 3: รับการตอบกลับทางเว็บ
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
ส่งคำขอเว็บและรับการตอบกลับจากเซิร์ฟเวอร์

## ขั้นตอนที่ 4: อ่านเนื้อหาเว็บ
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
 อ่านเนื้อหาของหน้าเว็บโดยใช้ก`StreamReader`และเก็บไว้ใน.`responseFromServer` ตัวแปร.

## ขั้นตอนที่ 5: แปลง HTML เป็น PDF
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
 สร้างก`MemoryStream` วัตถุเพื่อโหลดเนื้อหาหน้าเว็บ จากนั้นสร้างอินสแตนซ์ของ`HtmlLoadOptions` และส่ง URL ฐานของหน้าเว็บ ต่อไปสร้างก`Document` วัตถุโดยใช้สตรีมที่โหลดและตัวเลือกการโหลด HTML ตั้ง`IsLandscape` ทรัพย์สินเพื่อ`true` หากคุณต้องการให้ PDF อยู่ในแนวนอน สุดท้าย ให้บันทึกเอกสาร PDF ลงในไดเร็กทอรีที่ระบุ

.

## ขั้นตอนที่ 6: จัดการกับข้อยกเว้น
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
ตรวจจับข้อยกเว้นใดๆ ที่อาจเกิดขึ้นระหว่างกระบวนการแปลงและแสดงข้อความแสดงข้อผิดพลาด

### ตัวอย่างซอร์สโค้ดสำหรับเว็บเพจเป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
try
{
	
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// สร้างคำขอสำหรับ URL
	WebRequest request = WebRequest.Create("https:// En.wikipedia.org/wiki/Main_Page");
	// หากเซิร์ฟเวอร์ต้องการ ให้ตั้งค่าข้อมูลรับรอง
	request.Credentials = CredentialCache.DefaultCredentials;
	// หมดเวลาเป็นมิลลิวินาทีก่อนที่คำขอจะหมดเวลา
	// คำขอหมดเวลา = 100;

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
	HtmlLoadOptions options = new HtmlLoadOptions("https:// En.wikipedia.org/wiki/");


	// โหลดไฟล์ HTML
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	// บันทึกเอาต์พุตเป็นรูปแบบ PDF
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแปลงเว็บเพจเป็น PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราอ่านคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ที่ให้มา ด้วยการทำตามคำแนะนำเหล่านี้ คุณสามารถรวมหน้าเว็บเข้ากับฟังก์ชันการแปลง PDF เข้ากับแอปพลิเคชัน .NET ของคุณเองได้อย่างง่ายดาย

### คำถามที่พบบ่อย

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับเอกสาร PDF ในแอปพลิเคชัน C# ได้ มีฟังก์ชันการทำงานที่หลากหลาย รวมถึงการแปลงหน้าเว็บเป็น PDF

#### ถาม: เหตุใดฉันจึงต้องการแปลงหน้าเว็บเป็น PDF

ตอบ: การแปลงหน้าเว็บเป็น PDF มีประโยชน์ในการรักษาเค้าโครง การจัดรูปแบบ และรูปภาพของเนื้อหาเว็บต้นฉบับ ช่วยให้คุณสร้างภาพรวมของหน้าเว็บสำหรับการดูหรือแชร์กับผู้อื่นแบบออฟไลน์

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับบทช่วยสอนนี้มีอะไรบ้าง

ตอบ: หากต้องการปฏิบัติตามบทช่วยสอนนี้ คุณจะต้องติดตั้ง Visual Studio บนเครื่องของคุณ ไลบรารี Aspose.PDF สำหรับ .NET และความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

#### ถาม: ฉันสามารถแปลงหน้าเว็บใดๆ ให้เป็น PDF ได้หรือไม่

ตอบ: ได้ คุณสามารถแปลงหน้าเว็บใดๆ ให้เป็น PDF ได้โดยระบุ URL ของหน้าเว็บในโค้ด Aspose.PDF สำหรับ .NET จะดึงเนื้อหาเว็บและแปลงเป็นรูปแบบ PDF

#### ถาม: ฉันจะปรับแต่งเอาต์พุต PDF เช่น การวางแนวหน้าได้อย่างไร

 ตอบ: คุณสามารถปรับแต่งเอาต์พุต PDF ได้โดยใช้ตัวเลือกเช่น`IsLandscape` เพื่อตั้งค่าการวางแนวหน้า ในรหัสที่ให้มา`options.PageInfo.IsLandscape = true` ใช้เพื่อสร้าง PDF ในแนวนอน