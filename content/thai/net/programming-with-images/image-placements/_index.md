---
title: การจัดวางภาพ
linktitle: การจัดวางภาพ
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการใช้ Aspose.PDF สำหรับ .NET เพื่อวางรูปภาพในเอกสาร PDF
type: docs
weight: 170
url: /th/net/programming-with-images/image-placements/
---
ในบทช่วยสอนนี้ เราจะใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อทำงานกับเอกสาร PDF และดำเนินการกับรูปภาพ เราจะโหลดเอกสาร PDF แยกข้อมูลการจัดวางรูปภาพ และเรียกค้นรูปภาพพร้อมขนาดที่มองเห็นได้

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วยสิ่งต่อไปนี้:
- Aspose.PDF สำหรับ .NET ติดตั้งอยู่บนเครื่องของคุณ
- โครงการ AC# พร้อมใช้งานแล้ว

## ขั้นตอนที่ 2: การโหลดเอกสาร PDF
ในการเริ่มต้น เราต้องโหลดเอกสาร PDF ที่เราต้องการประมวลผล ตรวจสอบให้แน่ใจว่าคุณมีเส้นทางที่ถูกต้องไปยังไดเร็กทอรีที่มีเอกสาร PDF

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// โหลดเอกสาร PDF ต้นฉบับ
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENTS DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณซึ่งมีไฟล์ PDF

## ขั้นตอนที่ 3: ดึงข้อมูลตำแหน่งจากรูปภาพ
 ตอนนี้เราได้โหลดเอกสาร PDF แล้ว เราสามารถดึงข้อมูลตำแหน่งจากรูปภาพได้ เราจะใช้`ImagePlacementAbsorber`เพื่อดูดซับตำแหน่งภาพตั้งแต่หน้าแรกของเอกสาร

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// โหลดเนื้อหาหน้าแรก
doc.Pages[1].Accept(abs);
```

ตอนนี้เราได้ดึงข้อมูลการวางภาพจากหน้าแรกของเอกสารแล้ว

## ขั้นตอนที่ 4: ดึงภาพที่มีขนาดที่มองเห็นได้
ขณะนี้เราจะดึงรูปภาพพร้อมขนาดที่มองเห็นได้จากข้อมูลตำแหน่งที่เราแยกออกมาก่อนหน้านี้

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // รับคุณสมบัติของภาพ
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     // ดึงภาพที่มีขนาดที่มองเห็นได้
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // รับภาพจากแหล่งข้อมูล
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // สร้างภาพที่มีขนาดตามจริง
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

ในลูปนี้ เราจะเรียกค้นคุณสมบัติของแต่ละภาพ เช่น ความกว้าง ความสูง พิกัด X และ Y ของมุมล่างซ้าย ความละเอียดแนวนอนและแนวตั้ง จากนั้น เราจะเรียกค้นแต่ละภาพพร้อมขนาดที่มองเห็นได้โดยใช้ข้อมูลการจัดวาง

### ตัวอย่างโค้ดต้นฉบับสำหรับการวางภาพโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// โหลดเอกสาร PDF ต้นฉบับ
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// โหลดเนื้อหาหน้าแรก
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// รับคุณสมบัติของภาพ
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	// ดึงภาพที่มีขนาดที่มองเห็นได้
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// ดึงภาพจากแหล่งข้อมูล
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//สร้างบิตแมปที่มีขนาดจริง
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## บทสรุป
ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อวางรูปภาพในเอกสาร PDF แล้ว เราได้อธิบายโค้ดต้นฉบับของ C# ที่ให้มา ซึ่งช่วยให้คุณโหลดเอกสาร PDF ดึงข้อมูลการวางตำแหน่งจากรูปภาพ และเรียกค้นรูปภาพพร้อมขนาดที่มองเห็นได้ อย่าลังเลที่จะทดลองใช้ Aspose.PDF เพิ่มเติมเพื่อสำรวจคุณสมบัติอื่นๆ อีกมากมาย

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ในการดึงข้อมูลการวางภาพจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

A: การแยกข้อมูลการจัดวางรูปภาพช่วยให้คุณเรียกค้นตำแหน่ง ขนาด และความละเอียดของรูปภาพภายในเอกสาร PDF ได้ ข้อมูลนี้มีความสำคัญต่อการจัดการและวิเคราะห์รูปภาพอย่างแม่นยำ

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยอำนวยความสะดวกในการแยกข้อมูลการวางภาพจากเอกสาร PDF ได้อย่างไร

 A: Aspose.PDF สำหรับ .NET มีไว้`ImagePlacementAbsorber`คลาสที่สามารถใช้เพื่อดูดซับรายละเอียดการวางภาพจากเอกสาร PDF โค้ดที่ให้มาจะสาธิตวิธีใช้คลาสนี้เพื่อดึงข้อมูลการวางภาพ

#### ถาม: ข้อมูลการวางภาพสามารถนำไปใช้ในสถานการณ์จริงได้อย่างไร?

A: ข้อมูลการจัดวางรูปภาพมีค่าสำหรับงานต่างๆ เช่น การรับรองการจัดตำแหน่งรูปภาพที่ถูกต้อง การคำนวณขนาดรูปภาพ การตรวจสอบคุณภาพของรูปภาพ และการสร้างรายงานเกี่ยวกับการใช้งานรูปภาพภายในเอกสาร PDF

#### ถาม: ตัวอย่างโค้ดช่วยให้มั่นใจได้อย่างไรว่าข้อมูลการวางภาพจะถูกดึงออกมาถูกต้อง

 A: ตัวอย่างโค้ดใช้`ImagePlacementAbsorber` คลาสที่ใช้ในการสำรวจเนื้อหาของหน้าที่ระบุ ระบุตำแหน่งของภาพ และดึงข้อมูลแอตทริบิวต์ เช่น ความกว้าง ความสูง พิกัด และความละเอียด

#### ถาม: สามารถขยายโค้ดเพื่อประมวลผลภาพข้ามหน้าหรือเอกสารหลายๆ หน้าได้หรือไม่

A: ใช่ สามารถขยายโค้ดได้โดยการวนซ้ำผ่านหลายหน้าหรือเอกสารเพื่อดึงข้อมูลการวางภาพและดำเนินการงานที่เกี่ยวข้องกับภาพ

#### ถาม: โค้ดดึงรูปภาพที่มีขนาดที่มองเห็นได้ตามข้อมูลตำแหน่งได้อย่างไร

A: ตัวอย่างโค้ดจะดึงข้อมูลภาพจากแหล่งข้อมูล สร้างภาพบิตแมปที่มีขนาดจริง และให้คุณสมบัติเช่น ความกว้าง ความสูง พิกัด และความละเอียด

#### ถาม: วิธีนี้มีประสิทธิภาพสำหรับเอกสาร PDF ขนาดใหญ่ที่มีรูปภาพจำนวนมากหรือไม่

A: ใช่ Aspose.PDF สำหรับ .NET ได้รับการปรับให้เหมาะสมสำหรับประสิทธิภาพและการใช้ทรัพยากร โดยสามารถดึงข้อมูลการวางรูปภาพจากเอกสาร PDF ขนาดใหญ่ได้อย่างมีประสิทธิภาพ

#### ถาม: นักพัฒนาสามารถได้รับประโยชน์จากการทำความเข้าใจและใช้ประโยชน์จากข้อมูลการจัดวางภาพได้อย่างไร

A: นักพัฒนาสามารถรับรองการจัดการภาพ การจัดตำแหน่ง และการวิเคราะห์ที่แม่นยำภายในเอกสาร PDF ข้อมูลนี้ช่วยให้พวกเขาสร้างแอปพลิเคชันสำหรับการประมวลผลภาพ การรายงาน และการรับรองคุณภาพ

#### ถาม: สามารถปรับแต่งโค้ดเพื่อดึงคุณลักษณะหรือข้อมูลเมตาที่เกี่ยวข้องกับรูปภาพเพิ่มเติมได้หรือไม่

A: แน่นอน คุณสามารถปรับปรุงโค้ดเพื่อดึงแอตทริบิวต์เพิ่มเติม เช่น ประเภทของรูปภาพ พื้นที่สี การบีบอัด และอื่นๆ ได้ด้วยการใช้คลาสและวิธีการที่เหมาะสมที่ Aspose.PDF จัดทำไว้สำหรับ .NET

#### ถาม: ข้อสรุปที่ให้ไว้ในบทช่วยสอนนี้มีความสำคัญอย่างไร

A: บทสรุปสรุปเนื้อหาของบทช่วยสอนและกระตุ้นให้สำรวจ Aspose.PDF สำหรับ .NET เพิ่มเติมเพื่อใช้ประโยชน์จากความสามารถที่มากกว่าแค่การจัดวางภาพ และเปิดประตูสู่การทำงานต่างๆ ที่เกี่ยวข้องกับ PDF