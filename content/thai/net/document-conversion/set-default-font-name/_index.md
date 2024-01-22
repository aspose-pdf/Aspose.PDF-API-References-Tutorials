---
title: ตั้งชื่อแบบอักษรเริ่มต้น
linktitle: ตั้งชื่อแบบอักษรเริ่มต้น
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการตั้งชื่อแบบอักษรเริ่มต้นในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 270
url: /th/net/document-conversion/set-default-font-name/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีตั้งชื่อแบบอักษรเริ่มต้นในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET บางครั้งเมื่อคุณแยกรูปภาพออกจากไฟล์ PDF คุณอาจประสบปัญหาแบบอักษรที่หายไป ด้วยการระบุชื่อแบบอักษรเริ่มต้น คุณสามารถมั่นใจได้ว่าข้อความที่แยกออกมาจะแสดงอย่างถูกต้อง ทำตามขั้นตอนด้านล่างเพื่อตั้งชื่อแบบอักษรเริ่มต้นในไฟล์ PDF

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีคุณสมบัติตรงตามข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ไลบรารี Aspose.PDF สำหรับ .NET ที่ติดตั้งบนระบบของคุณ
- สภาพแวดล้อมการพัฒนาเช่น Visual Studio

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร PDF
 ขั้นตอนแรกคือการโหลดเอกสาร PDF ลงในไฟล์`Document` วัตถุ. ใช้รหัสต่อไปนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // รหัสที่จะเพิ่ม
}
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENTS DIRECTORY"` ด้วยไดเร็กทอรีจริงที่มีไฟล์ PDF ของคุณอยู่

## ขั้นตอนที่ 2: ตั้งชื่อแบบอักษรเริ่มต้น
 ต่อไปเราจะตั้งชื่อแบบอักษรเริ่มต้นโดยใช้`DefaultFontName` ตัวเลือกของ`RenderingOptions` วัตถุ. ใช้รหัสต่อไปนี้:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // รหัสที่จะเพิ่ม
     }
}
```

 อย่าลืมเปลี่ยน`"Arial"` พร้อมชื่อฟอนต์ที่ต้องการ

## ขั้นตอนที่ 3: การแยกรูปภาพ
ต่อไปเราจะแยกรูปภาพออกจากหน้าที่ระบุของเอกสาร PDF ใช้รหัสต่อไปนี้:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 อย่าลืมระบุหมายเลขหน้าที่ถูกต้อง`pdfDocument.Pages[1]`.

### ตัวอย่างซอร์สโค้ดสำหรับการตั้งชื่อแบบอักษรเริ่มต้นโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งชื่อแบบอักษรเริ่มต้นในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ด้วยการระบุชื่อแบบอักษรเริ่มต้น คุณสามารถมั่นใจได้ว่าข้อความที่แยกออกมาจะแสดงอย่างถูกต้อง ใช้วิธีนี้เพื่อแก้ไขปัญหาแบบอักษรที่หายไปเมื่อแยกรูปภาพจากไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับเอกสาร PDF ในแอปพลิเคชัน C# ได้ มีฟังก์ชันการทำงานที่หลากหลาย รวมถึงการตั้งชื่อแบบอักษรเริ่มต้นในไฟล์ PDF

#### ถาม: เหตุใดฉันจึงต้องตั้งชื่อแบบอักษรเริ่มต้นในไฟล์ PDF

ตอบ: การตั้งชื่อแบบอักษรเริ่มต้นมีประโยชน์เมื่อแยกข้อความจากเอกสาร PDF หาก PDF มีข้อความที่มีแบบอักษรที่ไม่มีอยู่ในเครื่องแยกข้อมูล การระบุชื่อแบบอักษรเริ่มต้นจะช่วยให้มั่นใจได้ว่าการแสดงข้อความถูกต้อง

#### ถาม: ฉันจะโหลดเอกสาร PDF และตั้งชื่อแบบอักษรเริ่มต้นโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการโหลดเอกสาร PDF และตั้งชื่อแบบอักษรเริ่มต้น คุณสามารถใช้ไฟล์`Document`คลาสเพื่อโหลดไฟล์ PDF และไฟล์`RenderingOptions.DefaultFontName` คุณสมบัติเพื่อระบุชื่อแบบอักษรเริ่มต้นที่ต้องการ

#### ถาม: ฉันสามารถเลือกแบบอักษรใดก็ได้เป็นชื่อแบบอักษรเริ่มต้นได้หรือไม่

ตอบ:ได้ คุณสามารถเลือกแบบอักษรใดๆ ที่มีอยู่ในเครื่องแยกเป็นชื่อแบบอักษรเริ่มต้นได้ ใช้แบบอักษรที่ตรงกับแบบอักษรที่หายไปใน PDF ต้นฉบับอย่างใกล้ชิดเพื่อให้แน่ใจว่าการแสดงข้อความมีความแม่นยำ

#### ถาม: การตั้งชื่อแบบอักษรเริ่มต้นเป็นการเปลี่ยนแปลงไฟล์ PDF อย่างถาวรหรือไม่

ตอบ: ไม่ การตั้งชื่อฟอนต์เริ่มต้นโดยใช้ Aspose.PDF สำหรับ .NET เป็นการเปลี่ยนแปลงชั่วคราวที่เกิดขึ้นระหว่างการแยกข้อความ มันไม่ได้แก้ไขไฟล์ PDF ต้นฉบับ