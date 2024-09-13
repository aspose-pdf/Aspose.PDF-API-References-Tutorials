---
title: เพิ่มข้อความพร้อมสีแรเงาในไฟล์ PDF
linktitle: เพิ่มข้อความพร้อมสีแรเงาในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการเพิ่มข้อความพร้อมสีแรเงาในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 80
url: /th/net/programming-with-text/add-text-with-shading-colors/
---
บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการเพิ่มข้อความพร้อมสีแรเงาในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ติดตั้งอยู่บนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose อย่างเป็นทางการหรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการเพิ่มข้อความพร้อมสีแรเงา ให้เพิ่มคำสั่ง using ต่อไปนี้ที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเรกทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณเก็บเอกสารไว้

## ขั้นตอนที่ 4: โหลดเอกสาร PDF
 โหลดเอกสาร PDF ที่มีอยู่โดยใช้`Document` ผู้สร้างและระบุเส้นทางไปยังไฟล์เอกสาร

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // โค้ดอยู่ที่นี่...
}
```

## ขั้นตอนที่ 5: ค้นหาข้อความที่ต้องการแก้ไข
ใช้`TextFragmentAbsorber` เพื่อค้นหาข้อความที่ต้องการภายในเอกสาร ในโค้ดที่ให้มา จะค้นหาข้อความ "Lorem ipsum"

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## ขั้นตอนที่ 6: ตั้งค่าสีแรเงาสำหรับข้อความ
 สร้างใหม่`Color` วัตถุที่มีรูปแบบสีและระบุสีแรเงาแบบไล่ระดับ กำหนดสีนี้ให้กับ`ForegroundColor` ทรัพย์สินของ`TextState` ของ`TextFragment` วัตถุ.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## ขั้นตอนที่ 7: ใช้การจัดรูปแบบข้อความเพิ่มเติม (ทางเลือก)
 คุณสามารถใช้การจัดรูปแบบเพิ่มเติมกับส่วนข้อความ เช่น การขีดเส้นใต้ โดยการแก้ไขคุณสมบัติของ`TextState` วัตถุ.

```csharp
textFragment.TextState.Underline = true;
```

## ขั้นตอนที่ 8: บันทึกเอกสาร PDF ที่แก้ไขแล้ว
 บันทึกเอกสาร PDF ที่แก้ไขแล้วโดยใช้`Save` วิธีการของ`Document` วัตถุ.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการเพิ่มข้อความพร้อมแรเงาสีโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// สร้างสีสันใหม่ด้วยรูปแบบสี
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## บทสรุป
คุณได้เพิ่มข้อความพร้อมสีแรเงาลงในเอกสาร PDF สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้สามารถค้นหาไฟล์ PDF ที่ได้ในเส้นทางไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: บทช่วยสอนนี้เน้นอะไรเป็นหลัก?

A: บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการเพิ่มข้อความพร้อมสีแรเงาลงในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็นในการบรรลุขั้นตอนนี้

#### ถาม: ฉันต้องนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

ตอบ: ในไฟล์โค้ดที่คุณต้องการเพิ่มข้อความพร้อมสีแรเงา นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร?

 ก: ในโค้ด ให้ระบุตำแหน่งบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะโหลดเอกสาร PDF ที่มีอยู่ได้อย่างไร

 ก: ในขั้นตอนที่ 4 คุณจะโหลดเอกสาร PDF ที่มีอยู่โดยใช้`Document` ผู้สร้างและระบุเส้นทางไปยังไฟล์เอกสาร:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // โค้ดอยู่ที่นี่...
}
```

#### ถาม: ฉันจะค้นหาและแก้ไขข้อความเฉพาะภายในเอกสาร PDF ได้อย่างไร

 A: ในขั้นตอนที่ 5 คุณจะใช้`TextFragmentAbsorber` เพื่อค้นหาข้อความที่ต้องการภายในเอกสาร จากนั้นคุณสามารถปรับเปลี่ยนคุณสมบัติของข้อความได้ดังนี้:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### ถาม: ฉันจะตั้งค่าสีแรเงาสำหรับข้อความได้อย่างไร

 A: ในขั้นตอนที่ 6 คุณจะสร้างใหม่`Color` วัตถุที่มีรูปแบบสีและระบุสีแรเงาแบบไล่ระดับ กำหนดสีนี้ให้กับ`ForegroundColor` ทรัพย์สินของ`TextState` ของ`TextFragment` วัตถุ:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### ถาม: ฉันสามารถใช้การจัดรูปแบบข้อความเพิ่มเติมกับข้อความที่แก้ไขแล้วได้หรือไม่

A: ใช่ ในขั้นตอนที่ 7 คุณสามารถใช้การจัดรูปแบบข้อความเพิ่มเติม เช่น การขีดเส้นใต้ โดยการแก้ไขคุณสมบัติของ`TextState` วัตถุ:

```csharp
textFragment.TextState.Underline = true;
```

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่แก้ไขแล้วได้อย่างไร

 ก: ในขั้นตอนที่ 8 คุณจะบันทึกเอกสาร PDF ที่แก้ไขแล้วโดยใช้`Save` วิธีการของ`Document` วัตถุ:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### ถาม: สิ่งสำคัญที่สุดที่ได้จากบทช่วยสอนนี้คืออะไร?

A: เมื่อทำตามบทช่วยสอนนี้แล้ว คุณจะเรียนรู้วิธีการปรับปรุงเอกสาร PDF ของคุณโดยการเพิ่มข้อความด้วยสีแรเงาโดยใช้ Aspose.PDF สำหรับ .NET ได้แล้ว วิธีนี้มีประโยชน์อย่างยิ่งในการเน้นข้อความเฉพาะในไฟล์ PDF ของคุณ