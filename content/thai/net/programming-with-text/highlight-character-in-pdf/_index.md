---
title: ไฮไลท์ตัวละครในไฟล์ PDF
linktitle: ไฮไลท์ตัวละครในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเน้นอักขระในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 240
url: /th/net/programming-with-text/highlight-character-in-pdf/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีเน้นอักขระในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะดำเนินการทีละขั้นตอนในการเน้นอักขระใน PDF โดยใช้ซอร์สโค้ด C# ที่ให้มา

## ความต้องการ

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร

 ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีที่มีไฟล์ PDF อินพุตของคุณอยู่ แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรพร้อมเส้นทางไปยังไฟล์ PDF ของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสาร PDF

 ต่อไปเราจะโหลดเอกสาร PDF อินพุตโดยใช้ไฟล์`Aspose.Pdf.Document` ระดับ.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## ขั้นตอนที่ 3: แปลง PDF เป็นรูปภาพ

 เพื่อเน้นตัวอักษร เราจะแปลงเอกสาร PDF เป็นรูปภาพโดยใช้`PdfConverter` ระดับ. เราตั้งค่าความละเอียดสำหรับการแปลงและดึงภาพเป็น`Bitmap` วัตถุ.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## ขั้นตอนที่ 4: เน้นอักขระ

 เราวนซ้ำแต่ละหน้าของเอกสาร PDF และใช้`TextFragmentAbsorber` วัตถุเพื่อค้นหาคำทั้งหมดในหน้า จากนั้นเราจะวนซ้ำส่วนข้อความ ส่วนต่างๆ และอักขระเพื่อไฮไลต์โดยใช้สี่เหลี่ยม

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //กำหนดขนาดและการแปลง
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // วนซ้ำหน้าต่างๆ
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         // ค้นหาคำทั้งหมดในหน้า
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // วนซ้ำส่วนของข้อความ
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

                 // วนซ้ำส่วนต่างๆ
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // ส่วนไฮไลท์
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // วนซ้ำตัวอักษร
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

## ขั้นตอนที่ 5: บันทึกภาพที่ส่งออก

สุดท้าย เราจะบันทึกรูปภาพที่แก้ไขด้วยอักขระที่ไฮไลต์ลงในไฟล์เอาต์พุตที่ระบุ

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### ตัวอย่างซอร์สโค้ดสำหรับอักขระเน้นในรูปแบบ PDF โดยใช้ Aspose.PDF สำหรับ .NET 
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
				// รับส่วนของข้อความที่แยกออกมา
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

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีเน้นอักขระในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและดำเนินการโค้ด C# ที่ให้มา คุณสามารถเน้นอักขระใน PDF และบันทึกเอาต์พุตเป็นรูปภาพได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "เน้นอักขระในไฟล์ PDF" คืออะไร

ตอบ: บทช่วยสอน "เน้นอักขระในไฟล์ PDF" จะอธิบายวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อเน้นอักขระภายในเอกสาร PDF บทช่วยสอนนี้จะให้คำแนะนำทีละขั้นตอนและซอร์สโค้ด C# เพื่อให้บรรลุเป้าหมายนี้

#### ถาม: เหตุใดฉันจึงต้องเน้นอักขระในเอกสาร PDF

ตอบ: การเน้นอักขระในเอกสาร PDF อาจมีประโยชน์สำหรับวัตถุประสงค์ต่างๆ เช่น การเน้นเนื้อหาเฉพาะเจาะจง หรือทำให้ข้อความบางส่วนมองเห็นและแยกแยะได้ชัดเจนยิ่งขึ้น

#### ถาม: ฉันจะตั้งค่าไดเร็กทอรีเอกสารได้อย่างไร

ตอบ: หากต้องการตั้งค่าไดเร็กทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรพร้อมพาธไปยังไดเร็กทอรีที่มีไฟล์ PDF อินพุตของคุณอยู่

#### ถาม: ฉันจะโหลดเอกสาร PDF และแปลงเป็นรูปภาพได้อย่างไร

 ตอบ: ในบทช่วยสอนนั้น`Aspose.Pdf.Document` คลาสใช้ในการโหลดเอกสาร PDF อินพุต จากนั้น`PdfConverter` คลาสใช้ในการแปลงเอกสาร PDF เป็นรูปภาพ ความละเอียดของภาพถูกตั้งค่าไว้ และภาพจะถูกดึงออกมาเป็น a`Bitmap` วัตถุ.

#### ถาม: ฉันจะเน้นอักขระในภาพเอกสาร PDF ได้อย่างไร

ตอบ: บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการวนซ้ำแต่ละหน้าของเอกสาร PDF โดยค้นหาคำโดยใช้ a`TextFragmentAbsorber`และวนซ้ำส่วนของข้อความ ส่วนต่างๆ และอักขระเพื่อไฮไลต์โดยใช้สี่เหลี่ยม

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของตัวละครและส่วนที่ไฮไลต์ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของอักขระและส่วนที่ไฮไลต์ได้โดยการปรับเปลี่ยนสีและสไตล์ที่ใช้ในการดำเนินการวาดภาพ

#### ถาม: ฉันจะบันทึกรูปภาพที่แก้ไขด้วยอักขระที่ไฮไลต์ได้อย่างไร

 ตอบ: บทช่วยสอนสาธิตวิธีการบันทึกภาพที่แก้ไขด้วยอักขระที่ไฮไลต์ไปยังไฟล์เอาต์พุตที่ระบุโดยใช้`Save` วิธีการของ`Bitmap` ระดับ.

#### ถาม: จำเป็นต้องมี Aspose License ที่ถูกต้องสำหรับบทช่วยสอนนี้หรือไม่

ตอบ: ใช่ จำเป็นต้องมี Aspose License ที่ถูกต้องเพื่อให้บทช่วยสอนนี้ทำงานได้อย่างถูกต้อง คุณสามารถซื้อใบอนุญาตแบบเต็มหรือรับใบอนุญาตชั่วคราว 30 วันได้จากเว็บไซต์ Aspose