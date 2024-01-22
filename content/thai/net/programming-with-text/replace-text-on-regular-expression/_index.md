---
title: แทนที่ข้อความในนิพจน์ปกติในไฟล์ PDF
linktitle: แทนที่ Texton Regular Expression ในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีแทนที่ข้อความตามนิพจน์ทั่วไปในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 360
url: /th/net/programming-with-text/replace-text-on-regular-expression/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการแทนที่ข้อความตามนิพจน์ทั่วไปในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะให้คำแนะนำทีละขั้นตอนพร้อมกับซอร์สโค้ด C# ที่จำเป็น

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.PDF สำหรับไลบรารี .NET แล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร

 กำหนดเส้นทางไปยังไดเร็กทอรีที่คุณมีไฟล์ PDF อินพุต แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรพร้อมเส้นทางไปยังไฟล์ PDF ของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสาร PDF

 โหลดเอกสาร PDF โดยใช้ไฟล์`Document` คลาสจากไลบรารี Aspose.PDF

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## ขั้นตอนที่ 3: ค้นหาและแทนที่ข้อความโดยใช้นิพจน์ทั่วไป

 สร้างก`TextFragmentAbsorber` object และระบุรูปแบบนิพจน์ทั่วไปเพื่อค้นหาวลีทั้งหมดที่ตรงกับรูปแบบ ตั้งค่าตัวเลือกการค้นหาข้อความเพื่อเปิดใช้งานการใช้นิพจน์ทั่วไป

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // เหมือนปี 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## ขั้นตอนที่ 4: แทนที่ข้อความ

วนซ้ำส่วนข้อความที่แยกออกมาและแทนที่ข้อความตามต้องการ อัปเดตข้อความและคุณสมบัติอื่นๆ เช่น แบบอักษร ขนาดแบบอักษร สีพื้นหน้า และสีพื้นหลัง

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

บันทึกเอกสาร PDF ที่แก้ไขแล้วลงในไฟล์เอาท์พุตที่ระบุ

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทนที่ Texton Regular Expression โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// สร้างวัตถุ TextAbsorber เพื่อค้นหาวลีทั้งหมดที่ตรงกับนิพจน์ทั่วไป
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // เหมือนปี 1999-2000
// ตั้งค่าตัวเลือกการค้นหาข้อความเพื่อระบุการใช้นิพจน์ทั่วไป
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// ยอมรับโช้คหน้าเดียว
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// รับส่วนของข้อความที่แยกออกมา
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// วนผ่านชิ้นส่วน
foreach (TextFragment textFragment in textFragmentCollection)
{
	// อัปเดตข้อความและคุณสมบัติอื่นๆ
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

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีแทนที่ข้อความตามนิพจน์ทั่วไปในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและดำเนินการโค้ด C# ที่ให้มา คุณสามารถโหลดเอกสาร PDF ค้นหาข้อความโดยใช้นิพจน์ทั่วไป แทนที่มัน และบันทึก PDF ที่แก้ไขแล้ว

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "แทนที่ข้อความในนิพจน์ปกติในไฟล์ PDF" คืออะไร

ตอบ: บทช่วยสอน "แทนที่ข้อความในนิพจน์ปกติในไฟล์ PDF" มีวัตถุประสงค์เพื่อแนะนำคุณตลอดกระบวนการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อค้นหาและแทนที่ข้อความในเอกสาร PDF ตามนิพจน์ทั่วไป โดยจะให้คำแนะนำทีละขั้นตอนพร้อมกับตัวอย่างโค้ด C#

#### ถาม: เหตุใดฉันจึงต้องการใช้นิพจน์ทั่วไปเพื่อแทนที่ข้อความในเอกสาร PDF

ตอบ: การใช้นิพจน์ทั่วไปทำให้คุณสามารถค้นหาและแทนที่รูปแบบข้อความที่เป็นไปตามรูปแบบเฉพาะได้ ทำให้เป็นวิธีที่มีประสิทธิภาพในการจัดการเนื้อหา วิธีการนี้มีประโยชน์อย่างยิ่งเมื่อคุณต้องการแทนที่ข้อความที่ตรงกับรูปแบบหรือโครงสร้างบางอย่างในเอกสาร PDF

#### ถาม: ฉันจะตั้งค่าไดเร็กทอรีเอกสารได้อย่างไร

ตอบ: หากต้องการตั้งค่าไดเร็กทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรพร้อมพาธไปยังไดเร็กทอรีที่มีไฟล์ PDF อินพุตของคุณอยู่

#### ถาม: ฉันจะแทนที่ข้อความตามนิพจน์ทั่วไปในเอกสาร PDF ได้อย่างไร

ตอบ: บทช่วยสอนจะแนะนำคุณตลอดขั้นตอนต่อไปนี้:

1.  โหลดเอกสาร PDF โดยใช้ไฟล์`Document` ระดับ.
2.  สร้างก`TextFragmentAbsorber` object และระบุรูปแบบนิพจน์ทั่วไปเพื่อค้นหาวลีที่ตรงกับรูปแบบ ตั้งค่าตัวเลือกการค้นหาข้อความเพื่อเปิดใช้งานการใช้นิพจน์ทั่วไป
3. วนซ้ำส่วนข้อความที่แยกออกมาแล้วแทนที่ข้อความ อัปเดตคุณสมบัติอื่นๆ เช่น แบบอักษร ขนาดแบบอักษร สีพื้นหน้า และสีพื้นหลังตามต้องการ
4. บันทึกเอกสาร PDF ที่แก้ไข

#### ถาม: ฉันสามารถแทนที่ข้อความโดยใช้นิพจน์ทั่วไปที่ซับซ้อนได้หรือไม่

ตอบ: ได้ คุณสามารถใช้นิพจน์ทั่วไปที่ซับซ้อนเพื่อจับคู่และแทนที่ข้อความในเอกสาร PDF นิพจน์ทั่วไปให้วิธีที่ยืดหยุ่นในการระบุรูปแบบหรือโครงสร้างเฉพาะในข้อความ

####  ถาม: จุดประสงค์ของ.`TextSearchOptions` class in the tutorial?

 ตอบ:`TextSearchOptions`คลาสอนุญาตให้คุณระบุตัวเลือกการค้นหาข้อความ เช่น การเปิดใช้งานการใช้นิพจน์ทั่วไปเมื่อค้นหาส่วนของข้อความ ในบทช่วยสอน ใช้เพื่อเปิดใช้งานโหมดนิพจน์ทั่วไปสำหรับ`TextFragmentAbsorber`.

#### ถาม: การเปลี่ยนแบบอักษรเป็นทางเลือกหรือไม่เมื่อใช้นิพจน์ทั่วไปเพื่อแทนที่ข้อความ

ตอบ: ได้ การแทนที่แบบอักษรเป็นทางเลือกเมื่อใช้นิพจน์ทั่วไปเพื่อแทนที่ข้อความ หากคุณไม่ระบุแบบอักษรใหม่ ข้อความจะคงแบบอักษรของส่วนของข้อความต้นฉบับไว้

#### ถาม: ฉันจะแทนที่ข้อความในหลายหน้าโดยใช้นิพจน์ทั่วไปได้อย่างไร

ตอบ: คุณสามารถแก้ไขการวนซ้ำผ่านส่วนข้อความเพื่อรวมทุกหน้าของเอกสาร PDF ได้ เช่นเดียวกับตัวอย่างการสอน ด้วยวิธีนี้ คุณสามารถแทนที่ข้อความในหลายหน้าตามรูปแบบนิพจน์ทั่วไปได้

#### ถาม: ผลลัพธ์ที่คาดหวังจากการรันโค้ดที่ให้มาคืออะไร?

ตอบ: เมื่อปฏิบัติตามบทช่วยสอนและเรียกใช้โค้ด C# ที่ให้มา คุณจะแทนที่ข้อความในเอกสาร PDF ที่ตรงกับรูปแบบนิพจน์ทั่วไปที่ระบุ ข้อความที่ถูกแทนที่จะมีคุณสมบัติที่คุณระบุ เช่น แบบอักษร ขนาดแบบอักษร สีพื้นหน้า และสีพื้นหลัง

#### ถาม: ฉันสามารถใช้วิธีนี้เพื่อแทนที่ข้อความด้วยการจัดรูปแบบที่ซับซ้อนได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งการจัดรูปแบบของข้อความที่ถูกแทนที่ได้โดยการอัปเดตคุณสมบัติ เช่น แบบอักษร ขนาดแบบอักษร สีพื้นหน้า และสีพื้นหลัง ซึ่งช่วยให้คุณสามารถรักษาหรือแก้ไขการจัดรูปแบบได้ตามต้องการ