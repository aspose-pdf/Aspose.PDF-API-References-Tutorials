---
title: XPS เป็น PDF
linktitle: XPS เป็น PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการแปลงไฟล์ XPS เป็น PDF ด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 350
url: /th/net/document-conversion/xps-to-pdf/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการแปลงไฟล์ XPS เป็น PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET ทีละขั้นตอน เราจะให้รายละเอียดซอร์สโค้ด C# ที่ให้มา และแสดงวิธีนำไปใช้ในโครงการของคุณเอง เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถแปลงไฟล์ XPS เป็นเอกสาร PDF ได้อย่างง่ายดาย

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 แทนที่`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางที่คุณบันทึกไฟล์ของคุณ

## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุ LoadOptions โดยใช้ตัวเลือกการโหลด XPS
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
สร้างอินสแตนซ์ของวัตถุ LoadOptions โดยใช้ตัวเลือกการโหลด XPS

## ขั้นตอนที่ 3: สร้างวัตถุเอกสาร
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
สร้างวัตถุเอกสารโดยระบุไฟล์ XPS อินพุตและตัวเลือกการโหลด

## ขั้นตอนที่ 4: บันทึกเอกสาร PDF ที่เป็นผลลัพธ์
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
บันทึกเอกสาร PDF ที่เป็นผลลัพธ์ไปยังไดเร็กทอรีที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับ XPS เป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
try
{
	
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//สร้างอินสแตนซ์วัตถุ LoadOption โดยใช้ตัวเลือกโหลด XPS
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// สร้างวัตถุเอกสาร
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// บันทึกเอกสาร PDF ที่เป็นผลลัพธ์
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแปลงไฟล์ XPS เป็น PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณสามารถทำการแปลงนี้ในแอปพลิเคชันของคุณเองได้อย่างง่ายดาย รับผลลัพธ์ที่แม่นยำและเป็นมืออาชีพเมื่อแปลงไฟล์ XPS เป็น PDF

### คำถามที่พบบ่อย

#### ถาม: XPS คืออะไร และเหตุใดฉันจึงต้องการแปลงเป็น PDF

ตอบ: XPS (XML Paper Specification) เป็นรูปแบบเอกสารที่มีเค้าโครงคงที่ซึ่งพัฒนาโดย Microsoft การแปลง XPS เป็น PDF ช่วยให้คุณสามารถทำให้เอกสารเข้าถึงได้มากขึ้นและเข้ากันได้อย่างกว้างขวาง เนื่องจาก PDF เป็นรูปแบบที่รองรับในระดับสากลในแพลตฟอร์มและอุปกรณ์ต่างๆ

#### ถาม: ไลบรารี Aspose.PDF รองรับไฟล์รูปแบบอื่นนอกเหนือจาก XPS หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET รองรับรูปแบบไฟล์อื่นๆ มากมายสำหรับการแปลง เช่น HTML, EPUB, SVG, XML และอื่นๆ นอกจากนี้ยังช่วยให้คุณสร้างและจัดการเอกสาร PDF โดยทางโปรแกรม

#### ถาม: ฉันสามารถปรับแต่งกระบวนการแปลง PDF เช่น การตั้งค่าขนาดหน้า ระยะขอบ หรือตัวเลือกอื่น ๆ ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งกระบวนการแปลง PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้ ไลบรารีมีตัวเลือกมากมายในการควบคุมขนาดหน้า ระยะขอบ การบีบอัดรูปภาพ การฝังแบบอักษร และการตั้งค่าอื่นๆ ที่เกี่ยวข้องกับ PDF เพื่อให้ตรงตามความต้องการเฉพาะของคุณ

#### ถาม: Aspose.PDF สำหรับ .NET เวอร์ชันทดลองใช้งานมีให้ทดสอบหรือไม่

ตอบ: ได้ คุณสามารถดาวน์โหลดและทดลองใช้ Aspose.PDF สำหรับ .NET เวอร์ชันทดลองได้จากเว็บไซต์ทางการของ Aspose เวอร์ชันทดลองใช้งานช่วยให้คุณสามารถสำรวจคุณลักษณะต่างๆ ของห้องสมุดได้ก่อนตัดสินใจซื้อ

#### ถาม: ฉันสามารถแปลงไฟล์ XPS หลายไฟล์เป็น PDF ในกระบวนการเป็นชุดได้หรือไม่

ตอบ: ได้ คุณสามารถแปลงไฟล์ XPS หลายไฟล์เป็น PDF ในกระบวนการเป็นชุดได้โดยใช้การวนซ้ำหรือวนซ้ำรายการไฟล์ XPS และแปลงแต่ละไฟล์เป็น PDF โดยใช้โค้ดที่ให้มา