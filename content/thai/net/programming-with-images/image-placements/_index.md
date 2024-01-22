---
title: ตำแหน่งรูปภาพ
linktitle: ตำแหน่งรูปภาพ
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อวางรูปภาพในเอกสาร PDF
type: docs
weight: 170
url: /th/net/programming-with-images/image-placements/
---
ในบทช่วยสอนนี้ เราจะใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อทำงานกับเอกสาร PDF และดำเนินการกับรูปภาพ เราจะโหลดเอกสาร PDF แยกข้อมูลตำแหน่งรูปภาพ และดึงรูปภาพที่มีขนาดที่มองเห็นได้

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วยสิ่งต่อไปนี้:
- ติดตั้ง Aspose.PDF สำหรับ .NET บนเครื่องของคุณแล้ว
- โครงการ AC# พร้อมใช้งาน

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร PDF
ในการเริ่มต้น เราต้องโหลดเอกสาร PDF ที่เราต้องการประมวลผล ตรวจสอบให้แน่ใจว่าคุณมีเส้นทางที่ถูกต้องไปยังไดเร็กทอรีที่มีเอกสาร PDF

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// โหลดเอกสาร PDF ต้นฉบับ
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณที่มีไฟล์ PDF

## ขั้นตอนที่ 3: แยกข้อมูลตำแหน่งออกจากรูปภาพ
 ตอนนี้เราได้โหลดเอกสาร PDF แล้ว เราก็สามารถดึงข้อมูลตำแหน่งออกจากรูปภาพได้ เราจะใช้`ImagePlacementAbsorber`เพื่อดูดซับตำแหน่งรูปภาพตั้งแต่หน้าแรกของเอกสาร

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// โหลดเนื้อหาของหน้าแรก
doc.Pages[1].Accept(abs);
```

ขณะนี้เราได้ดึงข้อมูลตำแหน่งรูปภาพออกจากหน้าแรกของเอกสารแล้ว

## ขั้นตอนที่ 4: การดึงภาพที่มีขนาดที่มองเห็นได้
ตอนนี้เราจะดึงภาพที่มีขนาดที่มองเห็นได้จากข้อมูลตำแหน่งที่เราดึงมาก่อนหน้านี้

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

     // ดึงภาพที่มีมิติที่มองเห็นได้
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

ในลูปนี้ เราจะดึงคุณสมบัติของแต่ละภาพ เช่น ความกว้าง ความสูง พิกัด X และ Y ของมุมซ้ายล่าง และความละเอียดแนวนอนและแนวตั้ง จากนั้นเราจะดึงภาพแต่ละภาพที่มีขนาดที่มองเห็นได้โดยใช้ข้อมูลตำแหน่ง

### ตัวอย่างซอร์สโค้ดสำหรับการจัดตำแหน่งรูปภาพโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// โหลดเอกสาร PDF ต้นฉบับ
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// โหลดเนื้อหาของหน้าแรก
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
		//สร้างบิตแมปด้วยขนาดจริง
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## บทสรุป
ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อจัดตำแหน่งรูปภาพในเอกสาร PDF แล้ว เราได้อธิบายซอร์สโค้ด C# ที่ให้มา ซึ่งช่วยให้คุณสามารถโหลดเอกสาร PDF แยกข้อมูลตำแหน่งออกจากรูปภาพ และดึงรูปภาพที่มีขนาดที่มองเห็นได้ รู้สึกอิสระที่จะทดลองเพิ่มเติมกับ Aspose.PDF เพื่อสำรวจคุณสมบัติอื่นๆ มากมาย

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ในการแยกข้อมูลตำแหน่งรูปภาพจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: การแยกข้อมูลการจัดวางรูปภาพทำให้คุณสามารถดึงข้อมูลตำแหน่ง ขนาด และความละเอียดของรูปภาพภายในเอกสาร PDF ได้ ข้อมูลนี้จำเป็นสำหรับการจัดการและวิเคราะห์ภาพที่แม่นยำ

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยให้ดึงข้อมูลตำแหน่งรูปภาพจากเอกสาร PDF ได้อย่างไร

 ตอบ: Aspose.PDF สำหรับ .NET มี`ImagePlacementAbsorber`คลาสซึ่งสามารถใช้เพื่อดูดซับรายละเอียดการวางตำแหน่งรูปภาพจากเอกสาร PDF รหัสที่ให้มาสาธิตวิธีการใช้คลาสนี้เพื่อดึงข้อมูลตำแหน่งรูปภาพ

#### ถาม: ข้อมูลการจัดวางรูปภาพสามารถนำไปใช้ในสถานการณ์จริงได้อย่างไร

ตอบ: ข้อมูลการจัดวางรูปภาพมีประโยชน์สำหรับงานต่างๆ เช่น การจัดตำแหน่งรูปภาพให้ถูกต้อง การคำนวณขนาดรูปภาพ การตรวจสอบคุณภาพของรูปภาพ และการสร้างรายงานเกี่ยวกับการใช้รูปภาพภายในเอกสาร PDF

#### ถาม: ตัวอย่างโค้ดช่วยให้ดึงข้อมูลตำแหน่งรูปภาพได้อย่างแม่นยำได้อย่างไร

 ตอบ: ตัวอย่างโค้ดใช้`ImagePlacementAbsorber` คลาสเพื่อสำรวจเนื้อหาของเพจที่ระบุ ระบุตำแหน่งรูปภาพ และดึงข้อมูลแอตทริบิวต์ เช่น ความกว้าง ความสูง พิกัด และความละเอียด

#### ถาม: สามารถขยายโค้ดเพื่อประมวลผลรูปภาพไปยังหลายหน้าหรือเอกสารได้หรือไม่

ตอบ: ได้ สามารถขยายโค้ดได้โดยการวนซ้ำหลายหน้าหรือเอกสารเพื่อแยกข้อมูลตำแหน่งรูปภาพและทำงานที่เกี่ยวข้องกับรูปภาพ

#### ถาม: โค้ดดึงภาพที่มีขนาดที่มองเห็นได้โดยพิจารณาจากข้อมูลตำแหน่งอย่างไร

ตอบ: ตัวอย่างโค้ดจะแยกข้อมูลรูปภาพจากทรัพยากร สร้างรูปภาพบิตแมปที่มีขนาดตามจริง และจัดเตรียมคุณสมบัติต่างๆ เช่น ความกว้าง ความสูง พิกัด และความละเอียด

#### ถาม: วิธีการนี้มีประสิทธิภาพกับเอกสาร PDF ขนาดใหญ่ที่มีรูปภาพจำนวนมากหรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET ได้รับการปรับให้เหมาะสมกับประสิทธิภาพและการใช้ทรัพยากร ดึงข้อมูลตำแหน่งภาพได้อย่างมีประสิทธิภาพแม้กระทั่งจากเอกสาร PDF ขนาดใหญ่

#### ถาม: นักพัฒนาจะได้รับประโยชน์จากการทำความเข้าใจและใช้ประโยชน์จากข้อมูลตำแหน่งรูปภาพได้อย่างไร

ตอบ: นักพัฒนาสามารถรับประกันการจัดการรูปภาพ การจัดตำแหน่ง และการวิเคราะห์ภายในเอกสาร PDF ได้อย่างแม่นยำ ข้อมูลนี้ช่วยให้พวกเขาสร้างแอปพลิเคชันสำหรับการประมวลผลภาพ การรายงาน และการประกันคุณภาพ

#### ถาม: สามารถปรับแต่งโค้ดเพื่อแยกแอตทริบิวต์หรือข้อมูลเมตาที่เกี่ยวข้องกับรูปภาพเพิ่มเติมได้หรือไม่

ตอบ: แน่นอน โค้ดสามารถปรับปรุงเพื่อแยกคุณลักษณะเพิ่มเติม เช่น ประเภทรูปภาพ พื้นที่สี การบีบอัด และอื่นๆ โดยใช้คลาสและวิธีการที่เหมาะสมที่ Aspose.PDF สำหรับ .NET มอบให้

#### ถาม: ข้อสรุปที่ให้ไว้ในบทช่วยสอนนี้มีความสำคัญอย่างไร

ตอบ: บทสรุปจะสรุปเนื้อหาของบทช่วยสอนและสนับสนุนให้มีการสำรวจ Aspose.PDF สำหรับ .NET เพิ่มเติมเพื่อใช้ประโยชน์จากความสามารถที่นอกเหนือไปจากการจัดวางรูปภาพ ซึ่งเป็นการเปิดประตูสู่งานต่างๆ ที่เกี่ยวข้องกับ PDF