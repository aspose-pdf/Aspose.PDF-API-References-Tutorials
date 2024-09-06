---
title: แทนที่ข้อความในนิพจน์ทั่วไปในไฟล์ PDF
linktitle: แทนที่นิพจน์ปกติของ Texton ในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการแทนที่ข้อความตามนิพจน์ทั่วไปในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 360
url: /th/net/programming-with-text/replace-text-on-regular-expression/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการแทนที่ข้อความตามนิพจน์ทั่วไปในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะให้คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับ C# ที่จำเป็น

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
- ความเข้าใจพื้นฐานในการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

 ตั้งค่าเส้นทางไปยังไดเร็กทอรีที่คุณมีไฟล์ PDF อินพุต แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไฟล์ PDF ของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสาร PDF

 โหลดเอกสาร PDF โดยใช้`Document` คลาสจากไลบรารี Aspose.PDF

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## ขั้นตอนที่ 3: ค้นหาและแทนที่ข้อความโดยใช้นิพจน์ทั่วไป

 สร้าง`TextFragmentAbsorber` วัตถุและระบุรูปแบบนิพจน์ทั่วไปเพื่อค้นหาคำวลีทั้งหมดที่ตรงกับรูปแบบ ตั้งค่าตัวเลือกการค้นหาข้อความเพื่อเปิดใช้งานการใช้นิพจน์ทั่วไป

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // ประมาณปี 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## ขั้นตอนที่ 4: แทนที่ข้อความ

วนซ้ำผ่านส่วนข้อความที่แยกออกมาและแทนที่ข้อความตามต้องการ อัปเดตข้อความและคุณสมบัติอื่นๆ เช่น แบบอักษร ขนาดแบบอักษร สีพื้นหน้า และสีพื้นหลัง

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## ขั้นตอนที่ 5: บันทึก PDF ที่แก้ไขแล้ว

บันทึกเอกสาร PDF ที่แก้ไขแล้วไปยังไฟล์เอาท์พุตที่ระบุ

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### ตัวอย่างโค้ดที่มาสำหรับการแทนที่ Texton Regular Expression โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// สร้างวัตถุ TextAbsorber เพื่อค้นหาวลีทั้งหมดที่ตรงกับนิพจน์ทั่วไป
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // ประมาณปี 1999-2000
// ตั้งค่าตัวเลือกการค้นหาข้อความเพื่อระบุการใช้งานนิพจน์ปกติ
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// รับตัวดูดซับสำหรับหน้าเดียว
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// รับชิ้นส่วนข้อความที่แยกออกมา
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// วนผ่านชิ้นส่วน
foreach (TextFragment textFragment in textFragmentCollection)
{
	// อัปเดตข้อความและคุณสมบัติอื่น ๆ
	textFragment.Text = "New Phrase";
	// ตั้งค่าเป็นอินสแตนซ์ของวัตถุ
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการแทนที่ข้อความตามนิพจน์ทั่วไปในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โดยปฏิบัติตามคำแนะนำทีละขั้นตอนและดำเนินการตามโค้ด C# ที่ให้มา คุณสามารถโหลดเอกสาร PDF ค้นหาข้อความโดยใช้นิพจน์ทั่วไป แทนที่ข้อความ และบันทึก PDF ที่แก้ไขแล้วได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "แทนที่ข้อความบนนิพจน์ทั่วไปในไฟล์ PDF" คืออะไร

A: บทช่วยสอน "แทนที่ข้อความในนิพจน์ทั่วไปในไฟล์ PDF" มีวัตถุประสงค์เพื่อแนะนำคุณตลอดขั้นตอนการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อค้นหาและแทนที่ข้อความในเอกสาร PDF โดยอิงตามนิพจน์ทั่วไป โดยจะให้คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ด C#

#### ถาม: เหตุใดฉันจึงต้องการใช้นิพจน์ทั่วไปเพื่อแทนที่ข้อความในเอกสาร PDF

A: การใช้นิพจน์ทั่วไปช่วยให้คุณค้นหาและแทนที่รูปแบบข้อความที่เป็นไปตามรูปแบบเฉพาะ ทำให้เป็นวิธีที่มีประสิทธิภาพในการจัดการเนื้อหา แนวทางนี้มีประโยชน์อย่างยิ่งเมื่อคุณจำเป็นต้องแทนที่ข้อความที่ตรงกับรูปแบบหรือโครงสร้างบางอย่างในเอกสาร PDF

#### ถาม: ฉันจะตั้งค่าไดเรกทอรีเอกสารได้อย่างไร?

ก: การตั้งค่าไดเรกทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไดเร็กทอรีซึ่งไฟล์ PDF อินพุตของคุณตั้งอยู่

#### ถาม: ฉันจะแทนที่ข้อความตามนิพจน์ทั่วไปในเอกสาร PDF ได้อย่างไร

A: บทช่วยสอนจะแนะนำคุณตามขั้นตอนต่อไปนี้:

1.  โหลดเอกสาร PDF โดยใช้`Document` ระดับ.
2.  สร้าง`TextFragmentAbsorber` วัตถุและระบุรูปแบบนิพจน์ทั่วไปเพื่อค้นหาคำวลีที่ตรงกับรูปแบบ ตั้งค่าตัวเลือกการค้นหาข้อความเพื่อเปิดใช้งานการใช้นิพจน์ทั่วไป
3. วนซ้ำผ่านข้อความที่ถูกแยกออกมาและแทนที่ข้อความ อัปเดตคุณสมบัติอื่นๆ เช่น แบบอักษร ขนาดแบบอักษร สีพื้นหน้า และสีพื้นหลังตามต้องการ
4. บันทึกเอกสาร PDF ที่แก้ไขแล้ว

#### ถาม: ฉันสามารถแทนที่ข้อความโดยใช้นิพจน์ทั่วไปที่ซับซ้อนได้หรือไม่

A: ใช่ คุณสามารถใช้นิพจน์ทั่วไปที่ซับซ้อนเพื่อจับคู่และแทนที่ข้อความในเอกสาร PDF ได้ นิพจน์ทั่วไปเป็นวิธีที่ยืดหยุ่นในการระบุรูปแบบหรือโครงสร้างเฉพาะในข้อความ

####  ถาม: จุดประสงค์ของการ`TextSearchOptions` class in the tutorial?

 ก. การ`TextSearchOptions`คลาสนี้ช่วยให้คุณระบุตัวเลือกการค้นหาข้อความได้ เช่น การเปิดใช้งานการใช้นิพจน์ทั่วไปเมื่อค้นหาชิ้นส่วนข้อความ ในบทช่วยสอน คลาสนี้ใช้เพื่อเปิดใช้งานโหมดนิพจน์ทั่วไปสำหรับ`TextFragmentAbsorber`.

#### ถาม: การแทนที่แบบอักษรเป็นทางเลือกหรือไม่เมื่อใช้นิพจน์ทั่วไปเพื่อแทนที่ข้อความ

A: ใช่ การแทนที่แบบอักษรเป็นทางเลือกเมื่อใช้นิพจน์ทั่วไปเพื่อแทนที่ข้อความ หากคุณไม่ระบุแบบอักษรใหม่ ข้อความจะยังคงใช้แบบอักษรของส่วนข้อความเดิม

#### ถาม: ฉันจะแทนที่ข้อความในหลายหน้าโดยใช้นิพจน์ทั่วไปได้อย่างไร

A: คุณสามารถปรับเปลี่ยนลูปผ่านส่วนข้อความเพื่อรวมหน้าทั้งหมดของเอกสาร PDF ได้ ซึ่งคล้ายกับตัวอย่างบทช่วยสอน วิธีนี้ทำให้คุณสามารถแทนที่ข้อความบนหลายหน้าตามรูปแบบนิพจน์ทั่วไปได้

#### ถาม: ผลลัพธ์ที่คาดหวังจากการดำเนินการโค้ดที่ให้มาคืออะไร

A: หากทำตามบทช่วยสอนและรันโค้ด C# ที่ให้มา คุณจะแทนที่ข้อความในเอกสาร PDF ที่ตรงกับรูปแบบนิพจน์ทั่วไปที่ระบุได้ ข้อความที่แทนที่จะมีคุณสมบัติตามที่คุณระบุ เช่น แบบอักษร ขนาดแบบอักษร สีพื้นหน้า และสีพื้นหลัง

#### ถาม: ฉันสามารถใช้แนวทางนี้เพื่อแทนที่ข้อความที่มีการจัดรูปแบบที่ซับซ้อนได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งการจัดรูปแบบของข้อความที่ถูกแทนที่ได้โดยการอัปเดตคุณสมบัติต่างๆ เช่น แบบอักษร ขนาดแบบอักษร สีพื้นหน้า และสีพื้นหลัง วิธีนี้ช่วยให้คุณรักษาหรือปรับเปลี่ยนการจัดรูปแบบตามต้องการ