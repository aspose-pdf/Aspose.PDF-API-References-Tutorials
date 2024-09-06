---
title: เพิ่มรูปภาพในไฟล์ PDF
linktitle: เพิ่มรูปภาพในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เพิ่มรูปภาพในไฟล์ PDF ได้อย่างง่ายดายโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-images/add-image/
---
คู่มือนี้จะแนะนำคุณทีละขั้นตอนเกี่ยวกับการเพิ่มรูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมของคุณแล้ว และทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอกสาร

ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไดเรกทอรีที่ถูกต้องสำหรับเอกสารแล้ว แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดพร้อมเส้นทางไปยังไดเร็กทอรีที่เอกสาร PDF ของคุณอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดเอกสาร

 ในขั้นตอนนี้เราจะเปิดเอกสาร PDF โดยใช้`Document` คลาสของ Aspose.PDF ใช้`Document` สร้างและส่งเส้นทางไปยังเอกสาร PDF

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## ขั้นตอนที่ 3: ตั้งค่าพิกัดภาพ

 ตั้งค่าพิกัดของภาพที่คุณต้องการเพิ่มตัวแปร`lowerLeftX`, `lowerLeftY`, `upperRightX` และ`upperRightY` แสดงพิกัดของมุมซ้ายล่างและมุมขวาบนของภาพตามลำดับ

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## ขั้นตอนที่ 4: รับหน้าที่จะเพิ่มรูปภาพ

หากต้องการเพิ่มรูปภาพลงในหน้าใดหน้าหนึ่งของเอกสาร PDF ก่อนอื่นเราต้องเรียกค้นหน้าดังกล่าว ในตัวอย่างนี้ เราจะเพิ่มรูปภาพลงในหน้าที่สอง (ดัชนี 1) ของเอกสาร

```csharp
Page page = pdfDocument.Pages[1];
```

## ขั้นตอนที่ 5: โหลดภาพจากสตรีม

 ตอนนี้เราจะโหลดรูปภาพที่เราต้องการเพิ่มลงในเอกสาร PDF ตัวอย่างนี้ถือว่าคุณมีไฟล์รูปภาพชื่อ`aspose-logo.jpg` ในไดเร็กทอรีเดียวกับเอกสารของคุณ เปลี่ยนชื่อไฟล์หากจำเป็น

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## ขั้นตอนที่ 6: เพิ่มรูปภาพลงในทรัพย์สินของหน้า

เพื่อใช้รูปภาพในเอกสาร PDF เราจำเป็นต้องเพิ่มรูปภาพนั้นลงในคอลเล็กชันรูปภาพทรัพยากรของหน้า

```csharp
page.Resources.Images.Add(imageStream);
```

## ขั้นตอนที่ 7: บันทึกสถานะกราฟิกปัจจุบัน

 ก่อนที่จะวาดภาพ เราจะต้องบันทึกสถานะกราฟิกปัจจุบันโดยใช้`GSave` ตัวดำเนินการ ซึ่งจะทำให้มั่นใจได้ว่าการเปลี่ยนแปลงสถานะกราฟิกสามารถย้อนกลับได้ในภายหลัง

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## ขั้นตอนที่ 8: สร้างวัตถุสี่เหลี่ยมผืนผ้าและเมทริกซ์

 ตอนนี้เราจะสร้าง`Rectangle` วัตถุและก`Matrix` วัตถุ สี่เหลี่ยมผืนผ้าแสดงตำแหน่งและขนาดของภาพ ในขณะที่เมทริกซ์จะกำหนดว่าควรวางภาพอย่างไร

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## ขั้นตอนที่ 9: เชื่อมโยงเมทริกซ์เพื่อวางภาพ

 เพื่อระบุว่าควรวางรูปภาพอย่างไรในสี่เหลี่ยมผืนผ้า เราใช้`ConcatenateMatrix` ตัวดำเนินการ ตัวดำเนินการนี้จะกำหนดเมทริกซ์การแปลงที่แมปพื้นที่พิกัดของภาพไปยังพื้นที่พิกัดของหน้า

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## ขั้นตอนที่ 10: วาดภาพ

 ในขั้นตอนนี้เราจะวาดภาพบนหน้าโดยใช้`Do` ผู้ดำเนินการ`Do`ผู้ดำเนินการนำชื่อภาพจากทรัพยากรและวาดลงบนหน้า

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## ขั้นตอนที่ 11: คืนค่าสถานะกราฟิก

 หลังจากวาดภาพแล้ว เราจะต้องคืนสถานะกราฟิกก่อนหน้าโดยใช้`GRestore` ผู้ดำเนินการ

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## ขั้นตอนที่ 12: บันทึกเอกสารที่อัพเดต

 สุดท้ายเราจะบันทึกเอกสารที่อัปเดตลงในไฟล์ใหม่ อัปเดต`dataDir` ตัวแปรที่มีไดเร็กทอรีเอาท์พุตและชื่อไฟล์ที่ต้องการ

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับ Add Image โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// ตั้งค่าพิกัด
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
// รับหน้าที่จำเป็นต้องเพิ่มรูปภาพ
Page page = pdfDocument.Pages[1];
// โหลดภาพเข้าสู่สตรีม
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// เพิ่มรูปภาพลงในคอลเล็กชันรูปภาพของทรัพยากรหน้า
page.Resources.Images.Add(imageStream);
// การใช้ตัวดำเนินการ GSave: ตัวดำเนินการนี้จะบันทึกสถานะกราฟิกปัจจุบัน
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// สร้างวัตถุสี่เหลี่ยมผืนผ้าและเมทริกซ์
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
// การใช้ตัวดำเนินการ ConcatenateMatrix (เมทริกซ์เชื่อม): กำหนดว่าจะต้องวางรูปภาพอย่างไร
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// การใช้ตัวดำเนินการ Do: ตัวดำเนินการนี้จะวาดภาพ
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// การใช้ตัวดำเนินการ GRestore: ตัวดำเนินการนี้จะคืนสถานะกราฟิก
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// บันทึกเอกสารอัพเดต
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการเพิ่มรูปภาพลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราได้อธิบายทุกขั้นตอนอย่างละเอียด ตั้งแต่การเปิดเอกสารจนถึงการบันทึกเวอร์ชันที่อัปเดต หากปฏิบัติตามคำแนะนำนี้ คุณจะสามารถฝังรูปภาพลงในไฟล์ PDF ของคุณโดยใช้โปรแกรม C# และ Aspose.PDF ได้แล้ว

### คำถามที่พบบ่อยสำหรับการเพิ่มรูปภาพในไฟล์ PDF

#### ถาม: เหตุใดฉันจึงต้องการเพิ่มรูปภาพลงในเอกสาร PDF

ตอบ: การเพิ่มรูปภาพลงในเอกสาร PDF สามารถเพิ่มเนื้อหาภาพ เพิ่มบริบทเพิ่มเติม หรือใส่โลโก้และกราฟิกในไฟล์ PDF ของคุณได้

#### ถาม: ฉันสามารถเพิ่มรูปภาพลงในหน้าเฉพาะภายในเอกสาร PDF ได้หรือไม่

A: ใช่ คุณสามารถระบุหน้าที่คุณต้องการเพิ่มรูปภาพได้ ในโค้ดที่ให้มา รูปภาพจะถูกเพิ่มไปที่หน้าที่สองของเอกสาร PDF

#### ถาม: ฉันจะปรับตำแหน่งและขนาดของรูปภาพที่เพิ่มได้อย่างไร

 A: คุณสามารถปรับเปลี่ยนได้`lowerLeftX`, `lowerLeftY`, `upperRightX` , และ`upperRightY` ตัวแปรในโค้ดเพื่อกำหนดพิกัดของรูปภาพและควบคุมขนาดและตำแหน่งบนหน้า

#### ถาม: ฉันสามารถเพิ่มรูปแบบภาพประเภทใดได้บ้างโดยใช้วิธีนี้?

A: ตัวอย่างโค้ดที่ให้มาจะถือว่าคุณกำลังโหลดรูปภาพ JPG (`aspose-logo.jpg`) Aspose.PDF สำหรับ .NET รองรับรูปแบบภาพต่างๆ รวมถึง PNG, BMP, GIF และอื่นๆ อีกมากมาย

#### ถาม: ฉันจะมั่นใจได้อย่างไรว่ารูปภาพที่เพิ่มเข้ามาจะพอดีกับพิกัดที่ระบุ

 ก. ตรวจสอบให้แน่ใจว่าได้ปรับพิกัดและขนาดของ`Rectangle` วัตถุ (`rectangle`) ให้ตรงกับขนาดของภาพและตำแหน่งที่ต้องการบนหน้า

#### ถาม: ฉันสามารถเพิ่มรูปภาพหลาย ๆ รูปลงในหน้า PDF เดียวได้หรือไม่

A: ใช่ คุณสามารถเพิ่มรูปภาพหลาย ๆ รูปภาพลงในหน้า PDF เดียวได้โดยทำซ้ำขั้นตอนเดียวกันสำหรับรูปภาพแต่ละภาพและปรับพิกัดและพารามิเตอร์อื่น ๆ ตามนั้น

####  ถาม: ทำอย่างไร`GSave` and `GRestore` operator work in the code?

 ก. การ`GSave` ตัวดำเนินการจะบันทึกสถานะกราฟิกปัจจุบัน ช่วยให้คุณสามารถทำการเปลี่ยนแปลงได้โดยไม่ส่งผลกระทบต่อบริบทกราฟิกโดยรวม`GRestore` ผู้ปฏิบัติงานจะคืนสถานะกราฟิกก่อนหน้าหลังจากมีการเปลี่ยนแปลง

#### ถาม: จะเกิดอะไรขึ้นหากไม่พบไฟล์รูปภาพในเส้นทางที่ระบุ?

A: หากไม่พบไฟล์ภาพในเส้นทางที่ระบุ โค้ดจะแสดงข้อยกเว้นเมื่อพยายามโหลดสตรีมภาพ ตรวจสอบให้แน่ใจว่าไฟล์ภาพอยู่ในไดเรกทอรีที่ถูกต้อง

#### ถาม: ฉันสามารถปรับแต่งตำแหน่งและลักษณะของภาพเพิ่มเติมได้หรือไม่

 A: ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏของภาพได้โดยการแก้ไข`Matrix` วัตถุและปรับตัวดำเนินการอื่น ๆ ภายในโค้ด ดูเอกสาร Aspose.PDF สำหรับการปรับแต่งขั้นสูง

#### ถาม: ฉันจะทดสอบได้อย่างไรว่าเพิ่มรูปภาพลงใน PDF สำเร็จหรือไม่

A: หลังจากใช้โค้ดที่ให้มาในการเพิ่มรูปภาพแล้ว ให้เปิดไฟล์ PDF ที่แก้ไขแล้ว และตรวจสอบว่ารูปภาพจะแสดงบนหน้าที่ระบุพร้อมตำแหน่งที่ถูกต้อง

#### ถาม: การเพิ่มรูปภาพจะส่งผลต่อเนื้อหาต้นฉบับของเอกสาร PDF หรือไม่

A: การเพิ่มรูปภาพไม่ส่งผลต่อเนื้อหาต้นฉบับของเอกสาร PDF แต่จะทำให้เอกสารดูดีขึ้นด้วยการเพิ่มองค์ประกอบภาพ