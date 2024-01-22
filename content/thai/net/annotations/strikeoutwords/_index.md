---
title: ขีดฆ่าคำ
linktitle: ขีดฆ่าคำ
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: บทความนี้ให้คำแนะนำทีละขั้นตอนในการใช้ Aspose.PDF สำหรับฟีเจอร์ Strike Out Words ของ .NET รวมถึงคำแนะนำทีละขั้นตอนและคำอธิบาย
type: docs
weight: 150
url: /th/net/annotations/strikeoutwords/
---
Aspose.PDF สำหรับ .NET คือไลบรารีการจัดการและประมวลผลเอกสาร PDF ที่มีคุณสมบัติต่างๆ ในการสร้าง แก้ไข และแปลงไฟล์ PDF หนึ่งในคุณสมบัติที่มีประโยชน์ที่ Aspose.PDF มอบให้คือความสามารถในการขีดทับคำหรือวลีในเอกสาร PDF โดยใช้ซอร์สโค้ด C# ในบทความนี้ เราจะให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการขีดฆ่าคำโดยใช้ Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร PDF
ขั้นตอนแรกคือการโหลดเอกสาร PDF ที่คุณต้องการแก้ไข ในบทช่วยสอนนี้ เราจะโหลดเอกสาร PDF ชื่อ "input.pdf" จากโฟลเดอร์ "ไดเรกทอรีเอกสารของคุณ" 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## ขั้นตอนที่ 2: ค้นหาส่วนของข้อความ
หากต้องการขีดฆ่าคำหรือวลีที่เฉพาะเจาะจงในเอกสาร PDF คุณต้องค้นหาคำหรือวลีเหล่านั้นก่อน Aspose.PDF มีคลาส TextFragmentAbsorber ที่สามารถใช้เพื่อค้นหาส่วนของข้อความเฉพาะในเอกสาร PDF

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

ในโค้ดด้านบน เรากำลังค้นหาส่วนของข้อความ "Estoque" ในเอกสาร PDF คุณสามารถแก้ไขเพื่อค้นหาคำหรือวลีอื่นๆ ที่คุณต้องการขีดทับได้

## ขั้นตอนที่ 3: ขีดฆ่าส่วนข้อความ
หลังจากค้นหาส่วนของข้อความแล้ว ขั้นตอนต่อไปคือการขีดฆ่าส่วนต่างๆ ของข้อความ Aspose.PDF มีคลาส StrikeOutAnnotation ที่สามารถใช้ในการสร้างคำอธิบายประกอบแบบขีดฆ่าสำหรับส่วนของข้อความ 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

ในโค้ดข้างต้น เรากำลังสร้างคำอธิบายประกอบแบบขีดฆ่าสำหรับแต่ละส่วนของข้อความที่เราพบ เรากำลังตั้งค่าความทึบ เส้นขอบ และสีของคำอธิบายประกอบที่ขีดฆ่าด้วยเช่นกัน

## ขั้นตอนที่ 4: บันทึกเอกสาร PDF ที่แก้ไข
หลังจากขีดฆ่าส่วนข้อความแล้ว ให้บันทึกเอกสารที่แก้ไข

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับ Strike Out Words โดยใช้ Aspose.PDF สำหรับ .NET


```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// เปิดเอกสาร
Document document = new Document(dataDir + "input.pdf");

// สร้างอินสแตนซ์ TextFragment Absorber เพื่อค้นหาส่วนของข้อความที่ต้องการ
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// วนซ้ำหน้าต่างๆ ของเอกสาร PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
	// รับหน้าแรกของเอกสาร PDF
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// สร้างคอลเลกชันของข้อความที่ดูดซับ
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//ทำซ้ำในคอลเลกชันด้านบน
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// รับขนาดสี่เหลี่ยมของวัตถุ TextFragment
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// สร้างอินสแตนซ์คำอธิบายประกอบ StrikeOut
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// ตั้งค่าความทึบสำหรับคำอธิบายประกอบ
	strikeOut.Opacity = .80f;
	// กำหนดเส้นขอบสำหรับอินสแตนซ์คำอธิบายประกอบ
	strikeOut.Border = new Border(strikeOut);
	// กำหนดสีของคำอธิบายประกอบ
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// เพิ่มคำอธิบายประกอบให้กับคอลเลกชันคำอธิบายประกอบของ TextFragment
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อขีดทับคำเฉพาะในเอกสาร PDF ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ด C# ที่ให้มา คุณสามารถโหลดเอกสาร PDF ค้นหาส่วนของข้อความที่ต้องการ และสร้างคำอธิบายประกอบแบบขีดฆ่าเพื่อทำเครื่องหมายและขีดทับคำเหล่านั้นด้วยสายตา Aspose.PDF สำหรับ .NET มอบวิธีที่ง่ายและมีประสิทธิภาพในการจัดการเอกสาร PDF ด้วยการเขียนโปรแกรม ทำให้เป็นเครื่องมืออันมีค่าสำหรับนักพัฒนาที่ทำงานกับไฟล์ PDF ในแอปพลิเคชัน .NET

### คำถามที่พบบ่อย

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และจัดการเอกสาร PDF โดยทางโปรแกรมในแอปพลิเคชัน .NET มันมีคุณสมบัติมากมายในการทำงานกับไฟล์ PDF รวมถึงการแยกข้อความ การจัดการคำอธิบายประกอบ การกรอกแบบฟอร์ม และอื่นๆ อีกมากมาย

#### ถาม: ฉันสามารถใช้ Aspose.PDF สำหรับ .NET เพื่อขีดทับคำเฉพาะในเอกสาร PDF ได้หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET มีฟังก์ชันการค้นหาส่วนย่อยของข้อความเฉพาะในเอกสาร PDF จากนั้นสร้างคำอธิบายประกอบแบบขีดทับเพื่อทำเครื่องหมายและขีดทับคำเหล่านั้นด้วยสายตา

#### ถาม: ฉันจะระบุข้อความที่ต้องการขีดฆ่าในเอกสาร PDF ได้อย่างไร

 ตอบ: หากต้องการระบุข้อความที่คุณต้องการขีดฆ่า คุณสามารถใช้`TextFragmentAbsorber` คลาสที่จัดทำโดย Aspose.PDF สำหรับ .NET ช่วยให้คุณสามารถค้นหาส่วนของข้อความเฉพาะในเอกสาร PDF ตามเกณฑ์ที่คุณต้องการ

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของคำอธิบายประกอบที่ขีดฆ่าได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งคุณสมบัติต่างๆ ของคำอธิบายประกอบที่ขีดฆ่าได้ เช่น ความทึบ รูปแบบเส้นขอบ และสี วิธีนี้ช่วยให้คุณปรับแต่งลักษณะของคำอธิบายประกอบที่ขีดฆ่าให้ตรงกับความต้องการเฉพาะของคุณได้