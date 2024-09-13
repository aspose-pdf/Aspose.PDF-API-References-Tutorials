---
title: แยกย่อหน้าในไฟล์ PDF
linktitle: แยกย่อหน้าในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการแยกย่อหน้าในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 160
url: /th/net/programming-with-text/extract-paragraphs/
---
บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับกระบวนการแยกย่อหน้าในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ติดตั้งอยู่บนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose อย่างเป็นทางการหรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการแยกย่อหน้า ให้เพิ่มคำสั่ง using ต่อไปนี้ที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเรกทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณเก็บเอกสารไว้

## ขั้นตอนที่ 4: เปิดเอกสาร PDF
 เปิดเอกสาร PDF ที่มีอยู่โดยใช้`Document`ตัวสร้างและส่งผ่านเส้นทางไปยังไฟล์ PDF อินพุต

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## ขั้นตอนที่ 5: แยกย่อหน้า
 สร้างตัวอย่าง`ParagraphAbsorber` ชั้นเรียนและการใช้ของมัน`Visit` วิธีการดึงย่อหน้าจากเอกสาร

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## ขั้นตอนที่ 6: ทำซ้ำผ่านย่อหน้า
วนซ้ำผ่านย่อหน้าที่แยกออกมาเพื่อเข้าถึงเนื้อหาข้อความ ใช้การวนซ้ำซ้อนกันเพื่อผ่านส่วนและบรรทัดภายในแต่ละย่อหน้า

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

### ตัวอย่างโค้ดต้นฉบับสำหรับการแยกย่อหน้าโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดไฟล์ PDF ที่มีอยู่
Document doc = new Document(dataDir + "input.pdf");
// สร้างตัวอย่างย่อหน้า
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
คุณได้แยกย่อหน้าจากเอกสาร PDF สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ย่อหน้าที่แยกออกมาจะแสดงในหน้าต่างคอนโซล

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้คืออะไร?

A: บทช่วยสอนนี้มีวัตถุประสงค์เพื่อแนะนำคุณตลอดกระบวนการแยกย่อหน้าจากไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่แนบมามีขั้นตอนปฏิบัติจริงสำหรับการบรรลุภารกิจนี้

#### ถาม: ฉันควรนำเข้าเนมสเปซอะไรบ้าง?

ก: ในไฟล์โค้ดที่คุณต้องการแยกย่อหน้า ให้ใส่คำสั่งต่อไปนี้โดยใช้คำสั่งที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร?

 ก. ค้นหาเส้น`string dataDir = "YOUR DOCUMENT DIRECTORY";` ในโค้ดและแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะเปิดเอกสาร PDF ที่มีอยู่ได้อย่างไร

 ก: ในขั้นตอนที่ 4 คุณจะเปิดเอกสาร PDF ที่มีอยู่โดยใช้`Document` ตัวสร้างและกำหนดเส้นทางไปยังไฟล์ PDF อินพุต

#### ถาม: ฉันจะแยกย่อหน้าจากเอกสารได้อย่างไร

 A: ขั้นตอนที่ 5 เกี่ยวข้องกับการสร้างอินสแตนซ์ของ`ParagraphAbsorber` ชั้นเรียนและการใช้ของมัน`Visit` วิธีการแยกย่อหน้าจากเอกสาร PDF

#### ถาม: ฉันจะทำซ้ำผ่านย่อหน้าที่แยกออกมาได้อย่างไร

ก: ขั้นตอนที่ 6 จะแนะนำคุณในการวนซ้ำย่อหน้าที่แยกออกมา การวนซ้ำแบบซ้อนกันจะใช้เพื่อข้ามส่วนและบรรทัดภายในย่อหน้าแต่ละย่อหน้า และสุดท้ายจะเข้าถึงและแสดงเนื้อหาข้อความ

#### ถาม: สิ่งสำคัญที่ได้จากบทช่วยสอนนี้คืออะไร?

A: เมื่อทำตามบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีแยกย่อหน้าจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ย่อหน้าที่แยกออกมาจะแสดงในหน้าต่างคอนโซล ซึ่งช่วยให้คุณเข้าใจโครงสร้างเนื้อหาของเอกสารได้อย่างล้ำลึก