---
title: ข้อความเป็น PDF
linktitle: ข้อความเป็น PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: การแปลงไฟล์ข้อความเป็น PDF ได้ง่ายและมีประสิทธิภาพโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 300
url: /th/net/document-conversion/text-to-pdf/
---
บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนในการแปลงไฟล์ข้อความเป็นไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET Aspose.PDF นำเสนอโซลูชันที่ง่ายและมีประสิทธิภาพสำหรับการแปลงข้อความธรรมดาเป็น PDF ในขณะที่ยังคงรูปแบบข้อความและการนำเสนอไว้ ทำตามขั้นตอนด้านล่างเพื่อทำการแปลงนี้

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีคุณสมบัติตรงตามข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ไลบรารี Aspose.PDF สำหรับ .NET ที่ติดตั้งบนระบบของคุณ
- สภาพแวดล้อมการพัฒนาเช่น Visual Studio

## ขั้นตอนที่ 1: อ่านไฟล์ข้อความ
 ขั้นตอนแรกคือการอ่านเนื้อหาของไฟล์ข้อความโดยใช้ไฟล์`StreamReader` ระดับ. ใช้รหัสต่อไปนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// อ่านไฟล์ข้อความ
TextReader tr = new StreamReader(dataDir + "log.txt");
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENTS DIRECTORY"`ด้วยไดเร็กทอรีจริงที่มีไฟล์ข้อความของคุณอยู่

## ขั้นตอนที่ 2: การสร้างเอกสาร PDF
 ขั้นตอนที่สองคือการสร้าง`Document` วัตถุซึ่งจะแสดงเอกสาร PDF สุดท้าย ใช้รหัสต่อไปนี้:

```csharp
// สร้างวัตถุเอกสาร
Document doc = new Document();
```

## ขั้นตอนที่ 3: เพิ่มข้อความลงในเอกสาร
ขั้นตอนที่สามคือการเพิ่มข้อความที่อ่านแล้วในหน้าของเอกสาร PDF ใช้รหัสต่อไปนี้:

```csharp
//เพิ่มหน้าใหม่ให้กับเอกสาร
Page page = doc.Pages.Add();

// สร้างวัตถุ TextFragment และส่งข้อความที่อ่านเป็นอาร์กิวเมนต์
TextFragment text = new TextFragment(tr.ReadToEnd());

// เพิ่มย่อหน้าข้อความลงในหน้า
page.Paragraphs.Add(text);
```

## ขั้นตอนที่ 4: บันทึกไฟล์ PDF
สุดท้าย ให้บันทึกไฟล์ PDF ที่เป็นผลลัพธ์โดยระบุเส้นทางและชื่อไฟล์ที่ต้องการ ใช้รหัสต่อไปนี้:

```csharp
// บันทึกไฟล์ PDF ที่ได้
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ต้องการสำหรับไฟล์ PDF ที่ได้

### ตัวอย่างซอร์สโค้ดสำหรับข้อความเป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
try
{
	
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// อ่านไฟล์ข้อความต้นฉบับ
	TextReader tr = new StreamReader(dataDir + "log.txt");

	// สร้างอินสแตนซ์ของวัตถุ Document โดยการเรียก Constructor ว่าง
	Document doc = new Document();

	// เพิ่มหน้าใหม่ในคอลเลกชัน Pages ของเอกสาร
	Page page = doc.Pages.Add();

	// สร้างอินสแตนซ์ของ TextFragmet และส่งข้อความจากวัตถุตัวอ่านไปยังตัวสร้างเป็นอาร์กิวเมนต์
	TextFragment text = new TextFragment(tr.ReadToEnd());
	//Text.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

	// เพิ่มย่อหน้าข้อความใหม่ในคอลเลกชันย่อหน้าและส่งวัตถุ TextFragment
	page.Paragraphs.Add(text);

	// บันทึกไฟล์ PDF ที่เป็นผลลัพธ์
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแปลงไฟล์ข้อความเป็นไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET โดยทำตามขั้นตอนข้างต้น คุณสามารถทำการแปลงนี้ได้อย่างง่ายดาย ใช้วิธีนี้เพื่อแปลงไฟล์ข้อความของคุณเป็น PDF และเพลิดเพลินกับความยืดหยุ่นและคุณภาพของ Aspose.PDF

### คำถามที่พบบ่อย

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับเอกสาร PDF ในแอปพลิเคชัน C# ได้ มีฟังก์ชันการทำงานที่หลากหลาย รวมถึงการแปลงข้อความธรรมดาเป็น PDF

#### ถาม: เหตุใดฉันจึงต้องการแปลงไฟล์ข้อความเป็น PDF

ตอบ: การแปลงไฟล์ข้อความเป็นรูปแบบ PDF ช่วยให้สามารถจัดการเอกสาร แบ่งปัน และแจกจ่ายเอกสารได้ดียิ่งขึ้น ไฟล์ PDF มีการจัดรูปแบบที่สอดคล้องกันในอุปกรณ์และระบบปฏิบัติการต่างๆ

#### ถาม: ฉันจะโหลดไฟล์ข้อความและแปลงเป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการโหลดไฟล์ข้อความ คุณสามารถใช้ไฟล์`StreamReader` คลาสเพื่ออ่านเนื้อหาของไฟล์ จากนั้นให้สร้าง`Document` วัตถุเพื่อแสดงเอกสาร PDF เพิ่มหน้าใหม่และก`TextFragment` มีข้อความจากไฟล์ข้อความ สุดท้าย ให้บันทึก PDF ที่ได้โดยใช้ไฟล์`Save` วิธีการของ`Document` วัตถุ.

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของข้อความใน PDF ได้หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET มีตัวเลือกมากมายในการปรับแต่งลักษณะที่ปรากฏของข้อความใน PDF ที่เป็นผลลัพธ์ เช่น รูปแบบแบบอักษร ขนาด สี และการจัดแนว

#### ถาม: การจัดรูปแบบข้อความจะยังคงอยู่ใน PDF ที่เป็นผลลัพธ์หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET จะรักษาการจัดรูปแบบและเลย์เอาต์ข้อความระหว่างการแปลงข้อความเป็น PDF เพื่อให้มั่นใจว่าการแสดงเนื้อหาต้นฉบับมีความแม่นยำ