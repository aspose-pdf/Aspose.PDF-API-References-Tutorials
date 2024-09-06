---
title: แทนที่การเกิดขึ้นครั้งแรก
linktitle: แทนที่การเกิดขึ้นครั้งแรก
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการแทนที่ข้อความแรกที่เกิดขึ้นในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 330
url: /th/net/programming-with-text/replace-first-occurrence/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการแทนที่ข้อความที่ระบุครั้งแรกในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะอธิบายกระบวนการทีละขั้นตอนในการเปิดเอกสาร PDF ค้นหาวลีการค้นหาครั้งแรก แทนที่ข้อความ อัปเดตคุณสมบัติ และบันทึก PDF ที่แก้ไขแล้วโดยใช้โค้ดต้นฉบับ C# ที่ให้มา

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

 ขั้นแรก คุณต้องตั้งค่าเส้นทางไปยังไดเร็กทอรีที่คุณมีไฟล์ PDF อินพุต แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไฟล์ PDF ของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดเอกสาร PDF

 ต่อไปเราเปิดเอกสาร PDF โดยใช้`Document` คลาสจากไลบรารี Aspose.PDF

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## ขั้นตอนที่ 3: ค้นหาการเกิดขึ้นครั้งแรกของวลีการค้นหา

 เราสร้าง`TextFragmentAbsorber` วัตถุและยอมรับมันสำหรับทุกหน้าของเอกสาร PDF เพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีการค้นหา

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## ขั้นตอนที่ 4: แทนที่ข้อความ

หากพบวลีการค้นหาในเอกสาร PDF เราจะดึงข้อมูลการเกิดขึ้นครั้งแรกของชิ้นส่วนข้อความและอัปเดตคุณสมบัติด้วยข้อความและการจัดรูปแบบใหม่

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
    TextFragment textFragment = textFragmentCollection[1];
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
}
```

## ขั้นตอนที่ 5: บันทึก PDF ที่แก้ไขแล้ว

ในที่สุด เราบันทึกเอกสาร PDF ที่แก้ไขแล้วไปยังไฟล์เอาท์พุตที่ระบุ

```csharp
dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการแทนที่การเกิดขึ้นครั้งแรกโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
// สร้างวัตถุ TextAbsorber เพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีการค้นหาอินพุต
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// รับตัวดูดซับสำหรับทุกหน้า
pdfDocument.Pages.Accept(textFragmentAbsorber);
// รับชิ้นส่วนข้อความที่แยกออกมา
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
	// รับการเกิดขึ้นครั้งแรกของข้อความและแทนที่
	TextFragment textFragment = textFragmentCollection[1];
	// อัปเดตข้อความและคุณสมบัติอื่น ๆ
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
	pdfDocument.Save(dataDir);                 
	Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการแทนที่ข้อความที่ระบุครั้งแรกในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โดยปฏิบัติตามคำแนะนำทีละขั้นตอนและดำเนินการตามโค้ด C# ที่ให้มา คุณสามารถเปิดเอกสาร PDF ค้นหาวลีการค้นหาครั้งแรก แทนที่ข้อความ อัปเดตคุณสมบัติ และบันทึก PDF ที่แก้ไขแล้ว

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "แทนที่การเกิดขึ้นครั้งแรก" คืออะไร

A: บทช่วยสอน "แทนที่การเกิดขึ้นครั้งแรก" สาธิตวิธีการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อแทนที่การเกิดขึ้นครั้งแรกของข้อความที่ระบุในเอกสาร PDF บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการเปิดเอกสาร PDF ค้นหาอินสแตนซ์แรกของวลีการค้นหา แทนที่ข้อความ อัปเดตคุณสมบัติ และบันทึก PDF ที่แก้ไขแล้ว

#### ถาม: เหตุใดฉันจึงต้องการแทนที่ข้อความแรกที่เกิดขึ้นในเอกสาร PDF

A: การแทนที่ข้อความที่ปรากฏครั้งแรกในเอกสาร PDF มีประโยชน์เมื่อคุณจำเป็นต้องทำการเปลี่ยนแปลงเฉพาะจุดกับวลีบางวลีในขณะที่ปล่อยให้วลีอื่นๆ ปรากฏขึ้นตามปกติ วิธีนี้มักใช้เพื่ออัปเดตหรือแก้ไขข้อความในลักษณะที่ควบคุมได้

#### ถาม: ฉันจะตั้งค่าไดเรกทอรีเอกสารได้อย่างไร?

ก: การตั้งค่าไดเรกทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไดเร็กทอรีซึ่งไฟล์ PDF อินพุตของคุณตั้งอยู่

#### ถาม: ฉันจะแทนที่ข้อความที่ระบุครั้งแรกในเอกสาร PDF ได้อย่างไร

A: บทช่วยสอนจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน:

1.  เปิดเอกสาร PDF โดยใช้`Document` ระดับ.
2.  สร้าง`TextFragmentAbsorber` วัตถุและยอมรับมันสำหรับทุกหน้าเพื่อค้นหาตัวอย่างของวลีการค้นหา
3. หากพบวลีที่ค้นหา ให้ดึงข้อมูลการเกิดขึ้นครั้งแรกของชิ้นส่วนข้อความและอัพเดตคุณสมบัติด้วยข้อความและการจัดรูปแบบใหม่
4. บันทึกเอกสาร PDF ที่แก้ไขแล้ว

####  ถาม: จุดประสงค์ในการใช้คืออะไร`TextFragmentAbsorber` to find the first occurrence of the search phrase?

 ก. การ`TextFragmentAbsorber` ใช้เพื่อค้นหาอินสแตนซ์ของวลีการค้นหาภายในเอกสาร PDF ในบทช่วยสอนนี้ จะช่วยระบุตำแหน่งการปรากฏครั้งแรกของข้อความที่ต้องแทนที่

#### ถาม: ฉันจะอัพเดตคุณสมบัติของชิ้นส่วนข้อความได้อย่างไร

A: เมื่อพบข้อความส่วนแรกแล้ว คุณสามารถอัปเดตคุณสมบัติต่างๆ เช่น ข้อความ แบบอักษร ขนาดแบบอักษร และสีของข้อความได้ ซึ่งจะช่วยให้คุณปรับแต่งลักษณะของข้อความที่จะแทนที่ได้

#### ถาม: มีข้อจำกัดในการแทนที่เฉพาะข้อความที่เกิดขึ้นครั้งแรกเท่านั้นหรือไม่

 A: ใช่ บทช่วยสอนนี้มุ่งเน้นที่การแทนที่ข้อความที่เกิดขึ้นครั้งแรกโดยเฉพาะ หากคุณจำเป็นต้องแทนที่ข้อความเดียวกันหลายครั้ง คุณสามารถขยายแนวทางนี้ได้โดยวนซ้ำผ่าน`TextFragmentCollection` เพื่อระบุและอัปเดตแต่ละอินสแตนซ์

#### ถาม: ผลลัพธ์ที่คาดหวังจากการดำเนินการโค้ดที่ให้มาคืออะไร

A: หากทำตามบทช่วยสอนและรันโค้ด C# ที่ให้มา คุณจะแทนที่ข้อความที่ระบุครั้งแรกในเอกสาร PDF ได้ ข้อความที่แทนที่นั้นจะมีคุณสมบัติที่อัปเดต เช่น แบบอักษร ขนาดแบบอักษร และสีข้อความ

#### ถาม: ฉันสามารถใช้แนวทางนี้เพื่อแทนที่ข้อความเดียวกันที่เกิดขึ้นครั้งอื่นๆ ได้หรือไม่

 A: ใช่ คุณสามารถแก้ไขโค้ดเพื่อวนซ้ำผ่านได้`TextFragmentCollection` เพื่อแทนที่ข้อความเดียวกันซ้ำๆ กัน เพียงแค่ขยายตรรกะเพื่อระบุและอัปเดตแต่ละอินสแตนซ์ตามต้องการ