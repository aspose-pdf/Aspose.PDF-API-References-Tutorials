---
title: เน้นตัวอักษรในไฟล์ PDF
linktitle: เน้นตัวอักษรในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีเน้นอักขระในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 240
url: /th/net/programming-with-text/highlight-character-in-pdf/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีเน้นตัวอักษรในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะอธิบายกระบวนการทีละขั้นตอนในการเน้นตัวอักษรใน PDF โดยใช้โค้ดต้นฉบับ C# ที่ให้มา

## ความต้องการ

ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

 ขั้นแรก คุณต้องตั้งค่าเส้นทางไปยังไดเร็กทอรีที่ไฟล์ PDF อินพุตของคุณตั้งอยู่ แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไฟล์ PDF ของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสาร PDF

 ต่อไปเราโหลดเอกสาร PDF อินพุตโดยใช้`Aspose.Pdf.Document` ระดับ.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## ขั้นตอนที่ 3: แปลง PDF เป็นรูปภาพ

 เพื่อเน้นอักขระ เราจะแปลงเอกสาร PDF เป็นรูปภาพโดยใช้`PdfConverter` คลาส เรากำหนดความละเอียดสำหรับการแปลงและดึงภาพออกมาเป็น`Bitmap` วัตถุ.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## ขั้นตอนที่ 4: เน้นตัวอักษร

 เราวนซ้ำผ่านแต่ละหน้าของเอกสาร PDF และใช้`TextFragmentAbsorber` วัตถุเพื่อค้นหาคำทั้งหมดในหน้า จากนั้นเราจะวนซ้ำผ่านส่วนข้อความ ส่วนย่อย และอักขระเพื่อเน้นข้อความเหล่านั้นโดยใช้รูปสี่เหลี่ยมผืนผ้า

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // ตั้งค่ามาตราส่วนและการแปลง
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // วนซ้ำผ่านหน้าต่างๆ
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //ค้นหาคำทั้งหมดในหน้านี้
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // วนซ้ำผ่านชิ้นส่วนข้อความ
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // เน้นตัวอักษร
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // ลูปผ่านส่วนต่างๆ
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // ไฮไลท์ส่วน
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // วนซ้ำผ่านตัวอักษร
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // ไฮไลท์ตัวละคร
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## ขั้นตอนที่ 5: บันทึกภาพผลลัพธ์

ในที่สุด เราจะบันทึกรูปภาพที่แก้ไขแล้วพร้อมอักขระที่ไฮไลต์ลงในไฟล์เอาต์พุตที่ระบุ

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### ตัวอย่างโค้ดที่มาสำหรับการเน้นอักขระใน PDF โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
try
{
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				// สร้างวัตถุ TextAbsorber เพื่อค้นหาคำทั้งหมด
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// รับชิ้นส่วนข้อความที่แยกออกมา
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// วนผ่านชิ้นส่วน
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx");
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีเน้นข้อความอักขระในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โดยปฏิบัติตามคำแนะนำทีละขั้นตอนและดำเนินการตามโค้ด C# ที่ให้มา คุณจะสามารถเน้นข้อความอักขระใน PDF และบันทึกผลลัพธ์เป็นรูปภาพได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "เน้นอักขระในไฟล์ PDF" คืออะไร

A: บทช่วยสอน "เน้นอักขระในไฟล์ PDF" อธิบายวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อเน้นอักขระภายในเอกสาร PDF บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนและโค้ดต้นฉบับ C# เพื่อให้บรรลุสิ่งนี้

#### ถาม: เหตุใดฉันจึงต้องเน้นอักขระในเอกสาร PDF

ตอบ การเน้นอักขระในเอกสาร PDF อาจเป็นประโยชน์สำหรับวัตถุประสงค์ต่างๆ เช่น การเน้นเนื้อหาเฉพาะหรือทำให้ข้อความบางอย่างมองเห็นได้ชัดเจนและแยกแยะได้ชัดเจนยิ่งขึ้น

#### ถาม: ฉันจะตั้งค่าไดเรกทอรีเอกสารได้อย่างไร?

ก: การตั้งค่าไดเรกทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไดเร็กทอรีซึ่งไฟล์ PDF อินพุตของคุณตั้งอยู่

#### ถาม: ฉันจะโหลดเอกสาร PDF และแปลงเป็นรูปภาพได้อย่างไร

 A: ในบทช่วยสอน`Aspose.Pdf.Document` คลาสนี้ใช้สำหรับโหลดเอกสาร PDF อินพุต จากนั้น`PdfConverter` คลาสนี้ใช้สำหรับแปลงเอกสาร PDF เป็นรูปภาพ ความละเอียดของรูปภาพถูกกำหนดไว้ และดึงรูปภาพออกมาเป็นไฟล์`Bitmap` วัตถุ.

#### ถาม: ฉันจะเน้นอักขระในภาพเอกสาร PDF ได้อย่างไร

A: บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการการวนซ้ำผ่านแต่ละหน้าของเอกสาร PDF เพื่อค้นหาคำโดยใช้`TextFragmentAbsorber`และการวนซ้ำผ่านชิ้นส่วนข้อความ ส่วนต่างๆ และอักขระ เพื่อเน้นข้อความเหล่านั้นโดยใช้สี่เหลี่ยมผืนผ้า

#### ถาม: ฉันสามารถปรับแต่งลักษณะของตัวละครและส่วนที่เน้นได้ไหม

A: ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏของตัวละครและส่วนที่เน้นได้โดยการปรับเปลี่ยนสีและรูปแบบที่ใช้ในการวาด

#### ถาม: ฉันจะบันทึกรูปภาพที่แก้ไขแล้วโดยมีอักขระที่ไฮไลต์อยู่ได้อย่างไร

 A: บทช่วยสอนสาธิตวิธีการบันทึกรูปภาพที่แก้ไขแล้วพร้อมอักขระที่เน้นไปยังไฟล์เอาท์พุตที่ระบุโดยใช้`Save` วิธีการของ`Bitmap` ระดับ.

#### ถาม: จำเป็นต้องมีใบอนุญาต Aspose ที่ถูกต้องสำหรับบทช่วยสอนนี้หรือไม่

A: ใช่ ต้องมีใบอนุญาต Aspose ที่ถูกต้องเพื่อให้บทช่วยสอนนี้ทำงานได้อย่างถูกต้อง คุณสามารถซื้อใบอนุญาตเต็มรูปแบบหรือรับใบอนุญาตชั่วคราว 30 วันได้จากเว็บไซต์ Aspose