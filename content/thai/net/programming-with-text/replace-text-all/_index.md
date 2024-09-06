---
title: แทนที่ข้อความทั้งหมดในไฟล์ PDF
linktitle: แทนที่ข้อความทั้งหมดในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการแทนที่ข้อความทั้งหมดในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 350
url: /th/net/programming-with-text/replace-text-all/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการแทนที่ข้อความทั้งหมดในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะให้คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับ C# ที่จำเป็น

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
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## ขั้นตอนที่ 3: ค้นหาและแทนที่ข้อความ

 สร้าง`TextFragmentAbsorber` วัตถุเพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีการค้นหาอินพุต ยอมรับตัวดูดซับสำหรับทุกหน้าของเอกสาร PDF เพื่อแยกชิ้นส่วนข้อความ

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## ขั้นตอนที่ 4: แทนที่ข้อความ

วนซ้ำผ่านส่วนข้อความที่แยกออกมาและแทนที่ข้อความตามต้องการ อัปเดตข้อความและคุณสมบัติอื่นๆ เช่น แบบอักษร ขนาดแบบอักษร สีพื้นหน้า และสีพื้นหลัง

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

บันทึกเอกสาร PDF ที่แก้ไขแล้วไปยังไฟล์เอาท์พุตที่ระบุ

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการแทนที่ข้อความทั้งหมดโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
// สร้างวัตถุ TextAbsorber เพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีการค้นหาอินพุต
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// รับตัวดูดซับสำหรับทุกหน้า
pdfDocument.Pages.Accept(textFragmentAbsorber);
// รับชิ้นส่วนข้อความที่แยกออกมา
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// วนผ่านชิ้นส่วน
foreach (TextFragment textFragment in textFragmentCollection)
{
	// อัปเดตข้อความและคุณสมบัติอื่น ๆ
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

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการแทนที่ข้อความทั้งหมดในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โดยปฏิบัติตามคำแนะนำทีละขั้นตอนและดำเนินการตามโค้ด C# ที่ให้มา คุณสามารถโหลดเอกสาร PDF ค้นหาข้อความที่ต้องการ แทนที่ และบันทึก PDF ที่แก้ไขแล้วได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "แทนที่ข้อความทั้งหมดในไฟล์ PDF" คืออะไร

A: บทช่วยสอน "แทนที่ข้อความทั้งหมดในไฟล์ PDF" มีวัตถุประสงค์เพื่อแนะนำคุณตลอดขั้นตอนการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อแทนที่ข้อความเฉพาะทั้งหมดในเอกสาร PDF โดยจะให้คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ด C#

#### ถาม: เหตุใดฉันจึงต้องการแทนที่ข้อความทั้งหมดในเอกสาร PDF

A: การแทนที่ข้อความเฉพาะทั้งหมดในเอกสาร PDF อาจจำเป็นเมื่อคุณต้องอัปเดตหรือทำให้เนื้อหาในเอกสารเป็นมาตรฐาน กระบวนการนี้อาจมีประโยชน์อย่างยิ่งในการรับรองความสอดคล้องในเนื้อหาและการจัดรูปแบบของเอกสาร

#### ถาม: ฉันจะตั้งค่าไดเรกทอรีเอกสารได้อย่างไร?

ก: การตั้งค่าไดเรกทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไดเร็กทอรีซึ่งไฟล์ PDF อินพุตของคุณตั้งอยู่

#### ถาม: ฉันจะแทนที่ข้อความทั้งหมดในเอกสาร PDF ได้อย่างไร

A: บทช่วยสอนจะแนะนำคุณตามขั้นตอนต่อไปนี้:

1.  โหลดเอกสาร PDF โดยใช้`Document` ระดับ.
2.  สร้าง`TextFragmentAbsorber` วัตถุเพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีการค้นหาอินพุต ยอมรับตัวดูดซับสำหรับทุกหน้าของเอกสาร PDF เพื่อแยกชิ้นส่วนข้อความ
3. วนซ้ำผ่านข้อความที่ถูกแยกออกมาและแทนที่ข้อความ อัปเดตคุณสมบัติอื่นๆ เช่น แบบอักษร ขนาดแบบอักษร สีพื้นหน้า และสีพื้นหลังตามต้องการ
4. บันทึกเอกสาร PDF ที่แก้ไขแล้ว

#### ถาม: ฉันสามารถแทนที่ข้อความโดยอิงจากการค้นหาแบบแยกแยะตัวพิมพ์ใหญ่-เล็กได้หรือไม่

 A: ใช่ คุณสามารถปรับเปลี่ยนได้`TextFragmentAbsorber` ค้นหาข้อความเพื่อค้นหาโดยคำนึงถึงตัวพิมพ์ใหญ่และเล็ก เพียงระบุข้อความที่ต้องการค้นหา จากนั้นตัวดูดซับจะจับคู่ข้อความนั้นให้เหมาะสม

#### ถาม: การแทนที่แบบอักษรเป็นทางเลือกเมื่อแทนที่ข้อความหรือไม่?

A: ใช่ การเปลี่ยนแบบอักษรเป็นทางเลือก หากคุณไม่ระบุแบบอักษรใหม่ ข้อความจะยังคงใช้แบบอักษรของส่วนข้อความเดิม

#### ถาม: ฉันจะแทนที่ข้อความในส่วนเฉพาะของเอกสาร PDF ได้อย่างไร

A: คุณสามารถปรับเปลี่ยนลูปผ่านส่วนข้อความเพื่อรวมคำสั่งเงื่อนไขตามตำแหน่งของส่วนข้อความได้ วิธีนี้ช่วยให้คุณเลือกแทนที่ข้อความเฉพาะในส่วนที่เจาะจงของ PDF ได้

#### ถาม: ผลลัพธ์ที่คาดหวังจากการดำเนินการโค้ดที่ให้มาคืออะไร

A: หากทำตามบทช่วยสอนและรันโค้ด C# ที่ให้มา คุณจะแทนที่ข้อความทั้งหมดที่ระบุไว้ในเอกสาร PDF ได้ ข้อความที่แทนที่จะมีคุณสมบัติตามที่คุณระบุ เช่น แบบอักษร ขนาดแบบอักษร สีพื้นหน้า และสีพื้นหลัง

#### ถาม: ฉันสามารถใช้แนวทางนี้เพื่อแทนที่องค์ประกอบที่ไม่ใช่ข้อความ เช่น รูปภาพหรือคำอธิบายประกอบ ได้หรือไม่

ตอบ: ไม่ บทช่วยสอนนี้มุ่งเน้นที่การแทนที่ข้อความในเอกสาร PDF โดยเฉพาะ หากคุณต้องการแทนที่องค์ประกอบที่ไม่ใช่ข้อความ คุณจะต้องทำตามขั้นตอนอื่นหรือใช้ฟีเจอร์ Aspose.PDF อื่นๆ