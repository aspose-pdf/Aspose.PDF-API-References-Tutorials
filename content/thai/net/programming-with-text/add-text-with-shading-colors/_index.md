---
title: เพิ่มข้อความด้วยการแรเงาสีในไฟล์ PDF
linktitle: เพิ่มข้อความด้วยการแรเงาสีในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มข้อความที่มีการแรเงาในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 80
url: /th/net/programming-with-text/add-text-with-shading-colors/
---
บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนการเพิ่มข้อความด้วยสีแรเงาในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ที่ติดตั้งบนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose หรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการเพิ่มข้อความที่มีสีแรเงา ให้เพิ่มคำสั่งต่อไปนี้โดยใช้คำสั่งที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเร็กทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่เก็บเอกสารของคุณ

## ขั้นตอนที่ 4: โหลดเอกสาร PDF
 โหลดเอกสาร PDF ที่มีอยู่โดยใช้ไฟล์`Document` Constructor และระบุเส้นทางไปยังไฟล์เอกสาร

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // รหัสไปที่นี่...
}
```

## ขั้นตอนที่ 5: ค้นหาข้อความที่จะแก้ไข
 ใช้`TextFragmentAbsorber` เพื่อค้นหาข้อความที่ต้องการภายในเอกสาร ในโค้ดที่ให้มา จะมองหาข้อความ "Lorem ipsum"

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## ขั้นตอนที่ 6: ตั้งค่าสีแรเงาสำหรับข้อความ
 สร้างใหม่`Color` วัตถุที่มีพื้นที่สีรูปแบบและระบุสีแรเงาแบบไล่ระดับสี กำหนดสีนี้ให้กับ`ForegroundColor` ทรัพย์สินของ`TextState` ของ`TextFragment` วัตถุ.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## ขั้นตอนที่ 7: ใช้การจัดรูปแบบข้อความเพิ่มเติม (ไม่บังคับ)
 คุณสามารถใช้การจัดรูปแบบเพิ่มเติมกับส่วนของข้อความ เช่น การขีดเส้นใต้ โดยการแก้ไขคุณสมบัติของ`TextState` วัตถุ.

```csharp
textFragment.TextState.Underline = true;
```

## ขั้นตอนที่ 8: บันทึกเอกสาร PDF ที่แก้ไข
 บันทึกเอกสาร PDF ที่แก้ไขโดยใช้ไฟล์`Save` วิธีการของ`Document` วัตถุ.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับเพิ่มข้อความด้วยการแรเงาสีโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// สร้างสีใหม่ด้วยปริภูมิสีลวดลาย
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## บทสรุป
คุณได้เพิ่มข้อความที่มีการแรเงาลงในเอกสาร PDF ของคุณสำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ขณะนี้ไฟล์ PDF ที่เป็นผลลัพธ์สามารถพบได้ที่เส้นทางไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: อะไรคือจุดสนใจหลักของบทช่วยสอนนี้

ตอบ: บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการเพิ่มข้อความที่มีการแรเงาสีให้กับไฟล์ PDF โดยใช้ Aspose.PDF สำหรับไลบรารี .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็นเพื่อให้บรรลุเป้าหมายนี้

#### ถาม: ฉันจำเป็นต้องนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

ตอบ: ในไฟล์โค้ดที่คุณต้องการเพิ่มข้อความที่มีสีแรเงา ให้นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร

 ตอบ: ในโค้ด ให้ค้นหาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะโหลดเอกสาร PDF ที่มีอยู่ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 4 คุณจะโหลดเอกสาร PDF ที่มีอยู่โดยใช้ไฟล์`Document` Constructor และจัดเตรียมเส้นทางไปยังไฟล์เอกสาร:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // รหัสไปที่นี่...
}
```

#### ถาม: ฉันจะค้นหาและแก้ไขข้อความเฉพาะภายในเอกสาร PDF ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 5 คุณจะใช้`TextFragmentAbsorber`เพื่อค้นหาข้อความที่ต้องการภายในเอกสาร จากนั้น คุณสามารถแก้ไขคุณสมบัติได้:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### ถาม: ฉันจะตั้งค่าสีแรเงาให้กับข้อความได้อย่างไร

 ตอบ: ในขั้นตอนที่ 6 คุณจะสร้างใหม่`Color` วัตถุที่มีพื้นที่สีรูปแบบและระบุสีแรเงาแบบไล่ระดับสี กำหนดสีนี้ให้กับ`ForegroundColor` ทรัพย์สินของ`TextState` ของ`TextFragment` วัตถุ:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### ถาม: ฉันสามารถใช้การจัดรูปแบบข้อความเพิ่มเติมกับข้อความที่แก้ไขได้หรือไม่

 ตอบ: ได้ ในขั้นตอนที่ 7 คุณสามารถใช้การจัดรูปแบบข้อความเพิ่มเติม เช่น การขีดเส้นใต้ โดยการปรับเปลี่ยนคุณสมบัติของ`TextState` วัตถุ:

```csharp
textFragment.TextState.Underline = true;
```

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่แก้ไขแล้วได้อย่างไร

 ตอบ: ในขั้นตอนที่ 8 คุณจะบันทึกเอกสาร PDF ที่แก้ไขแล้วโดยใช้นามสกุลไฟล์`Save` วิธีการของ`Document` วัตถุ:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### ถาม: สิ่งสำคัญที่ได้รับจากบทช่วยสอนนี้คืออะไร

ตอบ: เมื่อทำตามบทช่วยสอนนี้ คุณได้เรียนรู้วิธีปรับปรุงเอกสาร PDF ของคุณสำเร็จแล้วโดยการเพิ่มข้อความที่มีสีแรเงาโดยใช้ Aspose.PDF สำหรับ .NET สิ่งนี้มีประโยชน์อย่างยิ่งสำหรับการเน้นและเน้นเนื้อหาข้อความเฉพาะภายในไฟล์ PDF ของคุณ