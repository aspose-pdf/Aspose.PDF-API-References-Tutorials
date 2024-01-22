---
title: แทนที่ข้อความทั้งหมดในไฟล์ PDF
linktitle: แทนที่ข้อความทั้งหมดในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีแทนที่ข้อความทั้งหมดในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 350
url: /th/net/programming-with-text/replace-text-all/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีแทนที่ข้อความทั้งหมดในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะให้คำแนะนำทีละขั้นตอนพร้อมกับซอร์สโค้ด C# ที่จำเป็น

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
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## ขั้นตอนที่ 3: ค้นหาและแทนที่ข้อความ

 สร้างก`TextFragmentAbsorber` วัตถุเพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีค้นหาอินพุต ยอมรับตัวดูดซับสำหรับทุกหน้าของเอกสาร PDF เพื่อแยกส่วนของข้อความ

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## ขั้นตอนที่ 4: แทนที่ข้อความ

วนซ้ำส่วนข้อความที่แยกออกมาและแทนที่ข้อความตามต้องการ อัปเดตข้อความและคุณสมบัติอื่นๆ เช่น แบบอักษร ขนาดแบบอักษร สีพื้นหน้า และสีพื้นหลัง

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "TEXT";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## ขั้นตอนที่ 5: บันทึก PDF ที่แก้ไขแล้ว

บันทึกเอกสาร PDF ที่แก้ไขแล้วลงในไฟล์เอาท์พุตที่ระบุ

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทนที่ข้อความทั้งหมดโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
// สร้างวัตถุ TextAbsorber เพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีค้นหาอินพุต
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// รับซับทุกหน้า
pdfDocument.Pages.Accept(textFragmentAbsorber);
// รับส่วนของข้อความที่แยกออกมา
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// วนผ่านชิ้นส่วน
foreach (TextFragment textFragment in textFragmentCollection)
{
	// อัปเดตข้อความและคุณสมบัติอื่นๆ
	textFragment.Text = "TEXT";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextAll_out.pdf";
// บันทึกเอกสาร PDF ที่ได้
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีแทนที่ข้อความทั้งหมดในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและดำเนินการโค้ด C# ที่ให้มา คุณสามารถโหลดเอกสาร PDF ค้นหาข้อความที่ต้องการ แทนที่ และบันทึก PDF ที่แก้ไขแล้ว

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "แทนที่ข้อความทั้งหมดในไฟล์ PDF" คืออะไร

ตอบ: บทช่วยสอน "แทนที่ข้อความทั้งหมดในไฟล์ PDF" มีวัตถุประสงค์เพื่อแนะนำคุณตลอดกระบวนการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อแทนที่อินสแตนซ์ทั้งหมดของข้อความเฉพาะในเอกสาร PDF โดยจะให้คำแนะนำทีละขั้นตอนพร้อมกับตัวอย่างโค้ด C#

#### ถาม: เหตุใดฉันจึงต้องแทนที่ข้อความทั้งหมดในเอกสาร PDF

ตอบ: การแทนที่ข้อความเฉพาะเจาะจงทั้งหมดในเอกสาร PDF อาจจำเป็นเมื่อคุณต้องการอัปเดตหรือสร้างมาตรฐานให้กับเนื้อหาทั่วทั้งเอกสาร กระบวนการนี้จะเป็นประโยชน์อย่างยิ่งในการรับประกันความสอดคล้องในเนื้อหาและการจัดรูปแบบของเอกสาร

#### ถาม: ฉันจะตั้งค่าไดเร็กทอรีเอกสารได้อย่างไร

ตอบ: หากต้องการตั้งค่าไดเร็กทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรพร้อมพาธไปยังไดเร็กทอรีที่มีไฟล์ PDF อินพุตของคุณอยู่

#### ถาม: ฉันจะแทนที่ข้อความทั้งหมดในเอกสาร PDF ได้อย่างไร

ตอบ: บทช่วยสอนจะแนะนำคุณตลอดขั้นตอนต่อไปนี้:

1.  โหลดเอกสาร PDF โดยใช้ไฟล์`Document` ระดับ.
2.  สร้างก`TextFragmentAbsorber` วัตถุเพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีค้นหาอินพุต ยอมรับตัวดูดซับสำหรับทุกหน้าของเอกสาร PDF เพื่อแยกส่วนของข้อความ
3. วนซ้ำส่วนข้อความที่แยกออกมาแล้วแทนที่ข้อความ อัปเดตคุณสมบัติอื่นๆ เช่น แบบอักษร ขนาดแบบอักษร สีพื้นหน้า และสีพื้นหลังตามต้องการ
4. บันทึกเอกสาร PDF ที่แก้ไข

#### ถาม: ฉันสามารถแทนที่ข้อความโดยอิงตามการค้นหาแบบคำนึงถึงตัวพิมพ์เล็กและตัวพิมพ์ใหญ่ได้หรือไม่

 ตอบ: ได้ คุณสามารถแก้ไข`TextFragmentAbsorber` ข้อความค้นหาเพื่อทำการค้นหาโดยคำนึงถึงตัวพิมพ์เล็กและตัวพิมพ์ใหญ่ เพียงระบุข้อความที่คุณต้องการค้นหา จากนั้นตัวดูดซับจะจับคู่ข้อความนั้นให้สอดคล้องกัน

#### ถาม: การเปลี่ยนแบบอักษรเป็นทางเลือกหรือไม่เมื่อแทนที่ข้อความ

ตอบ: ได้ การเปลี่ยนแบบอักษรเป็นทางเลือก หากคุณไม่ระบุแบบอักษรใหม่ ข้อความจะคงแบบอักษรของส่วนของข้อความต้นฉบับไว้

#### ถาม: ฉันจะแทนที่ข้อความในส่วนเฉพาะของเอกสาร PDF ได้อย่างไร

ตอบ: คุณสามารถปรับการวนซ้ำผ่านส่วนของข้อความเพื่อรวมคำสั่งแบบมีเงื่อนไขตามตำแหน่งของส่วนของข้อความ ด้วยวิธีนี้ คุณสามารถเลือกที่จะแทนที่ข้อความเฉพาะในส่วนเฉพาะของ PDF ได้

#### ถาม: ผลลัพธ์ที่คาดหวังจากการรันโค้ดที่ให้มาคืออะไร?

ตอบ: เมื่อปฏิบัติตามบทช่วยสอนและเรียกใช้โค้ด C# ที่ให้มา คุณจะแทนที่อินสแตนซ์ทั้งหมดของข้อความที่ระบุในเอกสาร PDF ข้อความที่ถูกแทนที่จะมีคุณสมบัติที่คุณระบุ เช่น แบบอักษร ขนาดแบบอักษร สีพื้นหน้า และสีพื้นหลัง

#### ถาม: ฉันสามารถใช้แนวทางนี้เพื่อแทนที่องค์ประกอบที่ไม่ใช่ข้อความ เช่น รูปภาพหรือคำอธิบายประกอบได้หรือไม่

ตอบ: ไม่ บทช่วยสอนนี้เน้นไปที่การแทนที่ข้อความในเอกสาร PDF โดยเฉพาะ หากคุณต้องการแทนที่องค์ประกอบที่ไม่ใช่ข้อความ คุณจะต้องทำตามขั้นตอนต่างๆ หรือใช้คุณสมบัติ Aspose.PDF อื่นๆ