---
title: ระบุรูปภาพในไฟล์ PDF
linktitle: ระบุรูปภาพในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: ระบุรูปภาพในไฟล์ PDF ได้อย่างง่ายดายและกำหนดประเภทสีด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 150
url: /th/net/programming-with-images/identify-images/
---
คู่มือนี้จะแนะนำคุณทีละขั้นตอนในการระบุรูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมของคุณแล้ว และทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร

 ตรวจสอบให้แน่ใจว่าได้ตั้งค่าไดเร็กทอรีเอกสารที่ถูกต้อง แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดพร้อมเส้นทางไปยังไดเร็กทอรีที่มีเอกสาร PDF ของคุณอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: เริ่มต้นตัวนับ

ในขั้นตอนนี้ เราจะเริ่มต้นตัวนับสำหรับภาพระดับสีเทาและภาพ RGB

```csharp
int grayscaled = 0; // ตัวนับสำหรับภาพระดับสีเทา
int rdg = 0; // ตัวนับสำหรับภาพ RGB
```

## ขั้นตอนที่ 3: เปิดเอกสาร PDF

ในขั้นตอนนี้ เราจะเปิดเอกสาร PDF โดยใช้ไฟล์`Document` คลาสของ Aspose.PDF ใช้`Document` Constructor และส่งเส้นทางไปยังเอกสาร PDF

```csharp
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
```

## ขั้นตอนที่ 4: เรียกดูหน้าเอกสาร

ในขั้นตอนนี้ เราจะดูทุกหน้าของเอกสาร PDF และระบุรูปภาพในแต่ละหน้า

```csharp
foreach(Page page in document.Pages)
{
```

## ขั้นตอนที่ 5: ดึงข้อมูลตำแหน่งรูปภาพ

 ในขั้นตอนนี้เราจะใช้`ImagePlacementAbsorber` เพื่อดึงข้อมูลตำแหน่งรูปภาพในแต่ละหน้า

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
page. Accept(abs);
```

## ขั้นตอนที่ 6: นับภาพและระบุประเภทสี

ในขั้นตอนนี้ เราจะนับจำนวนภาพในแต่ละหน้าและระบุประเภทสี (ระดับสีเทาหรือ RGB)

```csharp
Console.WriteLine("Total Images = {0} on page number {1}", abs.ImagePlacements.Count, page.Number);
int image_counter = 1;
foreach(ImagePlacement ia in abs.ImagePlacements)
{
     ColorType colorType = ia.Image.GetColorType();
     switch (colorType)
     {
         ColorType.Grayscale box:
             ++grayscaled;
             Console.WriteLine("Image {0} is grayscale...", image_counter);
             break;
         box ColorType.Rgb:
             ++rgd;
             Console.WriteLine("Image {0} is RGB...", image_counter);
             break;
     }
     image_counter += 1;
}
```

### ตัวอย่างซอร์สโค้ดสำหรับระบุรูปภาพโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// ตัวนับสำหรับภาพระดับสีเทา
int grayscaled = 0;
// ตัวนับสำหรับภาพ RGB
int rgd = 0;
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
	foreach (Page page in document.Pages)
	{
		Console.WriteLine("--------------------------------");
		ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
		page.Accept(abs);
		// รับจำนวนรูปภาพในหน้าเฉพาะ
		Console.WriteLine("Total Images = {0} over page number {1}", abs.ImagePlacements.Count, page.Number);
		// Document.Pages[29].ยอมรับ(abs);
		int image_counter = 1;
		foreach (ImagePlacement ia in abs.ImagePlacements)
		{
			ColorType colorType = ia.Image.GetColorType();
			switch (colorType)
			{
				case ColorType.Grayscale:
					++grayscaled;
					Console.WriteLine("Image {0} is GrayScale...", image_counter);
					break;
				case ColorType.Rgb:
					++rgd;
					Console.WriteLine("Image {0} is RGB...", image_counter);
					break;
			}
			image_counter += 1;
		}
	}
}
```

## บทสรุป

ขอแสดงความยินดี! คุณระบุรูปภาพในรูปแบบ PDF ได้สำเร็จโดยใช้ Aspose.PDF สำหรับ .NET รูปภาพถูกนับและระบุประเภทสี (ระดับสีเทาหรือ RGB) ตอนนี้คุณสามารถใช้ข้อมูลนี้ตามความต้องการเฉพาะของคุณได้

### คำถามที่พบบ่อยสำหรับการระบุภาพในไฟล์ PDF

#### ถาม: การระบุรูปภาพในเอกสาร PDF มีจุดประสงค์อะไร

ตอบ: การระบุรูปภาพในเอกสาร PDF จะช่วยให้ผู้ใช้วิเคราะห์และจัดหมวดหมู่รูปภาพตามประเภทสี (ระดับสีเทาหรือ RGB) ข้อมูลนี้อาจมีประโยชน์สำหรับวัตถุประสงค์ต่างๆ เช่น การประมวลผลภาพ การวิเคราะห์ข้อมูล หรือการควบคุมคุณภาพ

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยในการระบุรูปภาพภายในเอกสาร PDF ได้อย่างไร

 ตอบ: Aspose.PDF สำหรับ .NET ให้กระบวนการที่ตรงไปตรงมาในการเปิดเอกสาร PDF วนซ้ำหน้าต่างๆ และระบุรูปภาพโดยใช้`ImagePlacementAbsorber` ระดับ.

#### ถาม: ความแตกต่างระหว่างภาพระดับสีเทาและภาพ RGB มีความสำคัญอย่างไร

ตอบ: การแยกความแตกต่างระหว่างรูปภาพระดับสีเทาและ RGB ช่วยในการทำความเข้าใจองค์ประกอบสีของรูปภาพภายในเอกสาร PDF ภาพระดับสีเทามีเพียงเฉดสีเทา ในขณะที่ภาพ RGB ประกอบด้วยช่องสีแดง เขียว และน้ำเงิน

#### ถาม: รูปภาพระดับสีเทาและ RGB จะนับและระบุโดยใช้ Aspose.PDF สำหรับ .NET อย่างไร

 ตอบ:`ImagePlacementAbsorber` class ใช้เพื่อดึงข้อมูลตำแหน่งรูปภาพในแต่ละหน้า ที่`GetColorType()` จากนั้นจะใช้วิธีการนี้กับแต่ละตำแหน่งภาพเพื่อพิจารณาว่าเป็นระดับสีเทาหรือ RGB

#### ถาม: ฉันสามารถแก้ไขโค้ดเพื่อดำเนินการเพิ่มเติมตามประเภทสีของภาพได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งโค้ดเพื่อดำเนินการเฉพาะตามประเภทสีของภาพได้ ตัวอย่างเช่น คุณสามารถแยกภาพระดับสีเทาเพื่อการประมวลผลเพิ่มเติม หรือใช้เทคนิคการปรับให้เหมาะสมที่แตกต่างกันตามประเภทสี

####  ถาม: เป็นยังไงบ้าง`ImagePlacementAbsorber` class contribute to identifying images?

 ตอบ:`ImagePlacementAbsorber` class จะสแกนหน้าเพื่อหาตำแหน่งรูปภาพ ซึ่งช่วยให้คุณสามารถดึงข้อมูลเกี่ยวกับรูปภาพ รวมถึงประเภทสีของรูปภาพเหล่านั้นได้

#### ถาม: จำนวนรูปภาพที่ระบุจะสะสมในทุกหน้าของเอกสาร PDF หรือไม่

ตอบ: ใช่ จำนวนรูปภาพจะสะสมในทุกหน้า โค้ดจะวนซ้ำแต่ละหน้าของเอกสาร PDF และนับรูปภาพในแต่ละหน้า

#### ถาม: ฉันสามารถใช้การระบุรูปภาพนี้เพื่อทำให้งานที่เกี่ยวข้องกับรูปภาพในเอกสาร PDF เป็นไปโดยอัตโนมัติได้หรือไม่

ตอบ: ได้ การระบุรูปภาพในเอกสาร PDF จะมีประโยชน์ในการทำงานอัตโนมัติ เช่น การแยกรูปภาพ การแปลง หรือการจัดการตามประเภทสี

#### ถาม: กระบวนการระบุรูปภาพนี้มีประโยชน์ต่อการประมวลผลเอกสาร PDF อย่างไร

ตอบ: การระบุรูปภาพให้ข้อมูลเชิงลึกอันมีค่าเกี่ยวกับองค์ประกอบสีของรูปภาพ ช่วยให้เข้าใจและประมวลผลเอกสาร PDF ที่มีรูปภาพได้ดีขึ้น