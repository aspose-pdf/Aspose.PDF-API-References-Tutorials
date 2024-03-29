---
title: รูปภาพเป็น PDF
linktitle: รูปภาพเป็น PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: แปลงรูปภาพเป็น PDF ได้อย่างง่ายดายโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 180
url: /th/net/programming-with-images/image-to-pdf/
---
Aspose.PDF สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงเอกสาร PDF โดยใช้ C# หรือภาษา .NET ใดๆ ได้ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการแปลงรูปภาพเป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.PDF สำหรับ .NET ไว้ในระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้งได้จากเว็บไซต์ Aspose อย่างเป็นทางการ เมื่อติดตั้งแล้ว ให้สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ

## ขั้นตอนที่ 2: การนำเข้าไลบรารีที่จำเป็น

หากต้องการใช้ Aspose.PDF สำหรับ .NET ในโปรเจ็กต์ของคุณ คุณจะต้องนำเข้าไลบรารีที่จำเป็น เพิ่มคำสั่งต่อไปนี้ที่จุดเริ่มต้นของไฟล์ C# ของคุณ:

```csharp
using Aspose.Pdf;
using System.IO;
using System.Drawing;
```

## ขั้นตอนที่ 3: การเริ่มต้นวัตถุเอกสาร

 ในโค้ด C# ขั้นตอนแรกคือการเริ่มต้นไฟล์`Document` วัตถุ. วัตถุนี้แสดงถึงเอกสาร PDF ที่เราจะสร้าง เพิ่มรหัสต่อไปนี้ในโครงการของคุณ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"`ด้วยเส้นทางจริงที่คุณต้องการบันทึกไฟล์ PDF

## ขั้นตอนที่ 4: การเพิ่มหน้าลงในเอกสาร

 ต่อไปเราต้องเพิ่มหน้าลงในเอกสาร เพจจะแสดงโดย`Page` ระดับ. ใช้รหัสต่อไปนี้เพื่อเพิ่มหน้าลงในเอกสาร:

```csharp
Page page = doc.Pages.Add();
```

 รหัสนี้จะสร้างหน้าใหม่และเพิ่มลงใน`Pages` การรวบรวมเอกสาร

## ขั้นตอนที่ 5: กำลังโหลดไฟล์รูปภาพ

 หากต้องการแปลงรูปภาพเป็น PDF เราต้องโหลดไฟล์รูปภาพต้นฉบับก่อน ในตัวอย่างนี้ เราถือว่าชื่อไฟล์รูปภาพนั้น`aspose-logo.jpg` และอยู่ในไดเรกทอรีเดียวกันกับไฟล์ C# ของคุณ ใช้รหัสต่อไปนี้เพื่อโหลดไฟล์รูปภาพ:

```csharp
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไฟล์ภาพ

## ขั้นตอนที่ 6: การตั้งค่าระยะขอบและกล่องครอบตัด

ก่อนที่จะเพิ่มรูปภาพลงในหน้า PDF เราสามารถปรับแต่งเค้าโครงหน้าได้ ตัวอย่างเช่น เราสามารถตั้งค่าระยะขอบและกล่องครอบตัดให้พอดีกับขนาดของภาพได้ ใช้รหัสต่อไปนี้เพื่อปรับการตั้งค่าหน้า:

```csharp
Bitmap b = new Bitmap(mystream);
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page

.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
```

การตั้งค่าเหล่านี้ช่วยให้แน่ใจว่ารูปภาพจะพอดีกับหน้าโดยไม่มีระยะขอบเพิ่มเติม

## ขั้นตอนที่ 7: การสร้างวัตถุรูปภาพ

ตอนนี้เรามาสร้าง`Aspose.Pdf.Image` วัตถุเพื่อเก็บข้อมูลภาพ เพิ่มรหัสต่อไปนี้ในโครงการของคุณ:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

วัตถุนี้จะแสดงภาพที่เราต้องการเพิ่มลงในหน้า PDF

## ขั้นตอนที่ 8: การเพิ่มรูปภาพลงในเพจ

 ในการเพิ่มรูปภาพลงในหน้า PDF เราจำเป็นต้องกำหนดข้อมูลรูปภาพให้กับ`ImageStream` ทรัพย์สินของ`Aspose.Pdf.Image` วัตถุ. ใช้รหัสต่อไปนี้เพื่อเพิ่มรูปภาพ:

```csharp
image1.ImageStream = mystream;
page.Paragraphs.Add(image1);
```

 ที่นี่ เรากำหนดสตรีมรูปภาพให้กับ`ImageStream` คุณสมบัติแล้วเพิ่มวัตถุรูปภาพลงใน`Paragraphs` คอลเลกชันของหน้า

## ขั้นตอนที่ 9: บันทึกไฟล์ PDF

เมื่อเราเพิ่มรูปภาพลงในหน้า PDF แล้ว เราก็สามารถบันทึกไฟล์ PDF ที่ได้ ใช้รหัสต่อไปนี้เพื่อบันทึกไฟล์:

```csharp
dataDir = dataDir + "ImageToPDF_out.pdf";
doc.Save(dataDir);
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมไดเร็กทอรีเอาต์พุตและชื่อไฟล์ที่ต้องการ

## ขั้นตอนที่ 10: ปิดสตรีมหน่วยความจำ

หลังจากบันทึกไฟล์ PDF แล้ว สิ่งสำคัญคือต้องปิดสตรีมหน่วยความจำเพื่อปล่อยทรัพยากรระบบ เพิ่มรหัสต่อไปนี้เพื่อปิดกระแสข้อมูลหน่วยความจำ:

```csharp
mystream. Close();
```

## การรันโค้ดและการตรวจสอบผลลัพธ์

ตอนนี้คุณได้ติดตั้งโค้ดเรียบร้อยแล้ว เรียกใช้โค้ดและตรวจสอบว่ารูปภาพได้รับการแปลงเป็น PDF สำเร็จแล้ว ไฟล์เอาต์พุตควรถูกบันทึกในไดเร็กทอรีที่ระบุ


### ตัวอย่างซอร์สโค้ดสำหรับรูปภาพเป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างอินสแตนซ์ของวัตถุเอกสาร
Document doc = new Document();
// เพิ่มหน้าไปยังคอลเลกชันหน้าของเอกสาร
Page page = doc.Pages.Add();
// โหลดไฟล์รูปภาพต้นฉบับไปยังออบเจ็กต์สตรีม
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
// สร้างอินสแตนซ์วัตถุ BitMap ด้วยสตรีมรูปภาพที่โหลด
Bitmap b = new Bitmap(mystream);
// ตั้งค่าระยะขอบเพื่อให้ภาพพอดี ฯลฯ
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
// สร้างวัตถุรูปภาพ
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// เพิ่มรูปภาพลงในคอลเลกชันย่อหน้าของส่วน
page.Paragraphs.Add(image1);
// ตั้งค่าสตรีมไฟล์รูปภาพ
image1.ImageStream = mystream;
dataDir = dataDir + "ImageToPDF_out.pdf";
// บันทึกไฟล์ PDF ที่เป็นผลลัพธ์
doc.Save(dataDir);
// ปิดวัตถุ memoryStream
mystream.Close();
Console.WriteLine("\nImage converted to pdf successfully.\nFile saved at " + dataDir); 
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแปลงรูปภาพเป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET เราครอบคลุมกระบวนการทีละขั้นตอน รวมถึงการตั้งค่าสภาพแวดล้อม การนำเข้าไลบรารี การเริ่มต้นวัตถุเอกสาร การโหลดไฟล์รูปภาพ การตั้งค่าระยะขอบและกล่องครอบตัด การเพิ่มรูปภาพลงในเพจ บันทึกไฟล์ PDF และการปิด สตรีมหน่วยความจำ ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถแปลงรูปภาพเป็น PDF ในแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย

### คำถามที่พบบ่อย

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร และช่วยในการทำงานกับเอกสาร PDF ได้อย่างไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงเอกสาร PDF โดยใช้ C# หรือภาษา .NET ใดๆ ได้ ช่วยให้งานที่เกี่ยวข้องกับการสร้าง การแก้ไข และการแปลง PDF ภายในแอปพลิเคชัน .NET ง่ายขึ้น

#### ถาม: วัตถุประสงค์ของการแปลงรูปภาพเป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: การแปลงรูปภาพเป็น PDF ช่วยให้คุณสามารถฝังรูปภาพลงในเอกสาร PDF ได้ ช่วยให้สามารถจัดการเอกสาร แบ่งปัน และพิมพ์ได้ดียิ่งขึ้น

####  ถาม: ทำไมจึงมี`using` statements necessary in the C# code?

 ตอบ:`using` คำสั่งนำเข้าเนมสเปซที่จำเป็น ทำให้คุณสามารถใช้คลาสและวิธีการจากเนมสเปซเหล่านั้นได้โดยไม่ต้องผ่านคุณสมบัติทั้งหมด สิ่งนี้ส่งเสริมโค้ดที่สะอาดและกระชับยิ่งขึ้น

####  Q5: บทบาทอะไรที่`Document` object play in the image-to-PDF conversion process?
 ตอบ:`Document` object แสดงถึงเอกสาร PDF ที่คุณจะสร้าง มันทำหน้าที่เป็นที่เก็บสำหรับหน้า ย่อหน้า และองค์ประกอบ PDF ต่างๆ

#### ถาม: รูปภาพถูกโหลดลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET อย่างไร

 ตอบ: รูปภาพจะถูกโหลดลงในเอกสาร PDF โดยการสร้างไฟล์`Aspose.Pdf.Image` วัตถุและกำหนดข้อมูลภาพให้กับมัน`ImageStream` คุณสมบัติ. วัตถุนี้จะถูกเพิ่มเข้าไปใน`Paragraphs` การรวบรวมหน้า PDF

#### ถาม: ขั้นตอนใดบ้างในการปรับเค้าโครงหน้าก่อนที่จะเพิ่มรูปภาพลงในหน้า PDF

ตอบ: โค้ดนี้ช่วยให้คุณสามารถกำหนดระยะขอบและขนาดกล่องครอบตัดเพื่อปรับแต่งเค้าโครงหน้าได้ เพื่อให้แน่ใจว่ารูปภาพจะพอดีกับหน้าโดยไม่มีระยะขอบเพิ่มเติม

#### ถาม: เหตุใดการปิดสตรีมหน่วยความจำหลังจากบันทึกไฟล์ PDF จึงมีความสำคัญ

ตอบ: การปิดสตรีมหน่วยความจำจะปล่อยทรัพยากรระบบที่เกี่ยวข้องกับข้อมูลรูปภาพ ป้องกันหน่วยความจำรั่วและเพิ่มประสิทธิภาพการใช้ทรัพยากร

#### ถาม: รหัสแปลงรูปภาพเป็น PDF นี้สามารถนำไปใช้กับรูปภาพหลายรูปภายในเอกสาร PDF เดียวได้หรือไม่

ตอบ: ได้ รหัสนี้สามารถปรับใช้เพื่อแปลงภาพหลายภาพให้เป็นเอกสาร PDF ไฟล์เดียวได้ คุณสามารถทำซ้ำขั้นตอนสำหรับแต่ละภาพ เพิ่มลงในหน้าแยกกัน หรือจัดเรียงได้ตามต้องการ

#### ถาม: นักพัฒนาจะได้รับประโยชน์จากการใช้ Aspose.PDF สำหรับ .NET เพื่อแปลงรูปภาพเป็น PDF ได้อย่างไร

ตอบ: นักพัฒนาสามารถปรับปรุงกระบวนการเพิ่มรูปภาพลงในเอกสาร PDF เพิ่มประสิทธิภาพการนำเสนอเอกสาร การแชร์ และความสามารถในการจัดเก็บถาวร ความสามารถนี้มีประโยชน์สำหรับการสร้างรายงาน การนำเสนอ และเอกสารประกอบที่มีรูปภาพมากมาย