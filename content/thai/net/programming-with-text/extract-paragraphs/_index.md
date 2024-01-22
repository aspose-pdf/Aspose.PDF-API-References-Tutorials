---
title: แยกย่อหน้าเป็นไฟล์ PDF
linktitle: แยกย่อหน้าเป็นไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีแยกย่อหน้าในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 160
url: /th/net/programming-with-text/extract-paragraphs/
---
บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการแยกย่อหน้าในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ที่ติดตั้งบนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose หรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการแยกย่อหน้า ให้เพิ่มคำสั่งต่อไปนี้ที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเร็กทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่เก็บเอกสารของคุณ

## ขั้นตอนที่ 4: เปิดเอกสาร PDF
 เปิดเอกสาร PDF ที่มีอยู่โดยใช้ไฟล์`Document`Constructor และส่งเส้นทางไปยังไฟล์ PDF อินพุต

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## ขั้นตอนที่ 5: แยกย่อหน้า
 ยกตัวอย่าง`ParagraphAbsorber` คลาสและใช้มัน`Visit` วิธีการแยกย่อหน้าออกจากเอกสาร

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## ขั้นตอนที่ 6: วนซ้ำผ่านย่อหน้า
วนซ้ำย่อหน้าที่แยกออกมาเพื่อเข้าถึงเนื้อหาข้อความ ใช้การวนซ้ำที่ซ้อนกันเพื่อสำรวจส่วนต่างๆ และบรรทัดภายในแต่ละย่อหน้า

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### ตัวอย่างซอร์สโค้ดสำหรับการแยกย่อหน้าโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
//เปิดไฟล์ PDF ที่มีอยู่
Document doc = new Document(dataDir + "input.pdf");
// ยกตัวอย่าง ParagraphAbsorber
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## บทสรุป
คุณได้แยกย่อหน้าจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว ย่อหน้าที่แยกออกมาแสดงอยู่ในหน้าต่างคอนโซล

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้คืออะไร?

ตอบ: บทช่วยสอนนี้มีจุดมุ่งหมายเพื่อแนะนำคุณตลอดกระบวนการแยกย่อหน้าจากไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาประกอบด้วยขั้นตอนการปฏิบัติเพื่อให้บรรลุภารกิจนี้

#### ถาม: ฉันควรนำเข้าเนมสเปซใด

ตอบ: ในไฟล์โค้ดที่คุณต้องการแยกย่อหน้า ให้รวมคำสั่งต่อไปนี้ไว้ที่ตอนต้นของไฟล์:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร

 ตอบ: ค้นหาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` ในโค้ดและแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะเปิดเอกสาร PDF ที่มีอยู่ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 4 คุณจะเปิดเอกสาร PDF ที่มีอยู่โดยใช้ไฟล์`Document` ตัวสร้างและจัดเตรียมเส้นทางไปยังไฟล์ PDF อินพุต

#### ถาม: ฉันจะแยกย่อหน้าออกจากเอกสารได้อย่างไร

 ตอบ: ขั้นตอนที่ 5 เกี่ยวข้องกับการสร้างอินสแตนซ์ของ`ParagraphAbsorber` คลาสและการใช้งานของมัน`Visit` วิธีการแยกย่อหน้าจากเอกสาร PDF

#### ถาม: ฉันจะวนซ้ำย่อหน้าที่แยกออกมาได้อย่างไร

ตอบ: ขั้นตอนที่ 6 จะแนะนำคุณเกี่ยวกับการวนซ้ำย่อหน้าที่แยกออกมา ลูปที่ซ้อนกันใช้เพื่อสำรวจส่วนและบรรทัดภายในแต่ละย่อหน้า เพื่อเข้าถึงและแสดงเนื้อหาข้อความในท้ายที่สุด

#### ถาม: สิ่งสำคัญที่ได้รับจากบทช่วยสอนนี้คืออะไร

ตอบ: เมื่อทำตามบทช่วยสอนนี้ คุณได้เรียนรู้วิธีแยกย่อหน้าจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ย่อหน้าที่แยกออกมาจะแสดงในหน้าต่างคอนโซล ซึ่งให้ข้อมูลเชิงลึกอันมีค่าเกี่ยวกับโครงสร้างเนื้อหาของเอกสาร