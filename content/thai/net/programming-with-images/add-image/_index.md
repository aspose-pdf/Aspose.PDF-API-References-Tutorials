---
title: เพิ่มรูปภาพในไฟล์ PDF
linktitle: เพิ่มรูปภาพในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เพิ่มรูปภาพในไฟล์ PDF ได้อย่างง่ายดายโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-images/add-image/
---
คู่มือนี้จะแนะนำคุณทีละขั้นตอนเกี่ยวกับวิธีเพิ่มรูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมของคุณแล้ว และทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไดเร็กทอรีที่ถูกต้องสำหรับเอกสาร แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดพร้อมเส้นทางไปยังไดเร็กทอรีที่มีเอกสาร PDF ของคุณอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดเอกสาร

ในขั้นตอนนี้ เราจะเปิดเอกสาร PDF โดยใช้ไฟล์`Document` คลาสของ Aspose.PDF ใช้`Document` Constructor และส่งเส้นทางไปยังเอกสาร PDF

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## ขั้นตอนที่ 3: ตั้งค่าพิกัดรูปภาพ

 กำหนดพิกัดของภาพที่คุณต้องการเพิ่ม ตัวแปรต่างๆ`lowerLeftX`, `lowerLeftY`, `upperRightX` และ`upperRightY` แสดงถึงพิกัดของมุมซ้ายล่างและมุมขวาบนของภาพตามลำดับ

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## ขั้นตอนที่ 4: รับหน้าที่ควรเพิ่มรูปภาพ

หากต้องการเพิ่มรูปภาพลงในหน้าเฉพาะของเอกสาร PDF เราต้องเรียกข้อมูลหน้านั้นก่อน ในตัวอย่างนี้ เราเพิ่มรูปภาพลงในหน้าที่ 2 (ดัชนี 1) ของเอกสาร

```csharp
Page page = pdfDocument.Pages[1];
```

## ขั้นตอนที่ 5: โหลดภาพจากสตรีม

 ตอนนี้เราจะโหลดภาพที่เราต้องการเพิ่มลงในเอกสาร PDF ตัวอย่างนี้ถือว่าคุณมีไฟล์รูปภาพชื่อ`aspose-logo.jpg` ในไดเร็กทอรีเดียวกันกับเอกสารของคุณ เปลี่ยนชื่อไฟล์หากจำเป็น

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## ขั้นตอนที่ 6: เพิ่มรูปภาพลงในเนื้อหาของเพจ

หากต้องการใช้รูปภาพในเอกสาร PDF เราจำเป็นต้องเพิ่มรูปภาพนั้นลงในคอลเลกชันรูปภาพของทรัพยากรของเพจ

```csharp
page.Resources.Images.Add(imageStream);
```

## ขั้นตอนที่ 7: บันทึกสถานะกราฟิกปัจจุบัน

 ก่อนที่จะวาดภาพ เราจำเป็นต้องบันทึกสถานะกราฟิกปัจจุบันโดยใช้`GSave` ตัวดำเนินการ เพื่อให้แน่ใจว่าการเปลี่ยนแปลงสถานะกราฟิกสามารถย้อนกลับได้ในภายหลัง

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## ขั้นตอนที่ 8: สร้างวัตถุสี่เหลี่ยมผืนผ้าและเมทริกซ์

 ตอนนี้เราจะสร้าง`Rectangle` วัตถุและก`Matrix`วัตถุ. สี่เหลี่ยมผืนผ้าแสดงถึงตำแหน่งและขนาดของรูปภาพ ในขณะที่เมทริกซ์จะกำหนดวิธีการวางรูปภาพ

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## ขั้นตอนที่ 9: เชื่อมต่อเมทริกซ์สำหรับการจัดวางรูปภาพ

 เพื่อระบุวิธีการวางรูปภาพในสี่เหลี่ยม เราใช้`ConcatenateMatrix` ตัวดำเนินการ โอเปอเรเตอร์นี้กำหนดเมทริกซ์การแปลงที่แมปพื้นที่พิกัดของรูปภาพกับพื้นที่พิกัดของเพจ

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## ขั้นตอนที่ 10: วาดภาพ

 ในขั้นตอนนี้ เราจะวาดภาพบนเพจโดยใช้`Do` ตัวดำเนินการ ที่`Do` โอเปอเรเตอร์ใช้ชื่อรูปภาพจากแหล่งข้อมูลและวาดลงบนเพจ

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## ขั้นตอนที่ 11: คืนค่าสถานะกราฟิก

 หลังจากวาดภาพแล้ว เราจำเป็นต้องคืนค่าสถานะกราฟิกก่อนหน้าโดยใช้`GRestore` ตัวดำเนินการ

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## ขั้นตอนที่ 12: บันทึกเอกสารที่อัพเดต

 สุดท้าย เราจะบันทึกเอกสารที่อัปเดตเป็นไฟล์ใหม่ อัพเดต`dataDir` ตัวแปรพร้อมไดเร็กทอรีเอาต์พุตและชื่อไฟล์ที่ต้องการ

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับเพิ่มรูปภาพโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// กำหนดพิกัด
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
//รับหน้าที่จำเป็นต้องเพิ่มรูปภาพ
Page page = pdfDocument.Pages[1];
// โหลดภาพเข้าสู่สตรีม
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// เพิ่มรูปภาพลงในคอลเลกชันรูปภาพของทรัพยากรหน้า
page.Resources.Images.Add(imageStream);
// การใช้ตัวดำเนินการ GSave: ตัวดำเนินการนี้จะบันทึกสถานะกราฟิกปัจจุบัน
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// สร้างวัตถุสี่เหลี่ยมผืนผ้าและเมทริกซ์
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
// การใช้ตัวดำเนินการ ConcatenateMatrix (concatenate matrix): กำหนดวิธีการวางรูปภาพ
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// การใช้ตัวดำเนินการ Do: ตัวดำเนินการนี้จะวาดภาพ
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// การใช้ตัวดำเนินการ GRestore: ตัวดำเนินการนี้จะกู้คืนสถานะกราฟิก
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// บันทึกเอกสารที่อัปเดต
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเพิ่มรูปภาพลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราได้ครอบคลุมทุกขั้นตอนโดยละเอียด ตั้งแต่การเปิดเอกสารไปจนถึงการบันทึกเวอร์ชันที่อัปเดต เมื่อปฏิบัติตามคำแนะนำนี้ ตอนนี้คุณควรจะสามารถฝังรูปภาพลงในไฟล์ PDF ของคุณโดยทางโปรแกรมโดยใช้ C# และ Aspose.PDF

### คำถามที่พบบ่อยสำหรับการเพิ่มรูปภาพในไฟล์ PDF

#### ถาม: เหตุใดฉันจึงต้องการเพิ่มรูปภาพลงในเอกสาร PDF

ตอบ: การเพิ่มรูปภาพลงในเอกสาร PDF สามารถปรับปรุงเนื้อหาภาพ ให้บริบทเพิ่มเติม หรือรวมโลโก้และกราฟิกในไฟล์ PDF ของคุณได้

#### ถาม: ฉันสามารถเพิ่มรูปภาพไปยังหน้าเฉพาะภายในเอกสาร PDF ได้หรือไม่

ตอบ: ได้ คุณสามารถระบุหน้าที่คุณต้องการเพิ่มรูปภาพได้ ในโค้ดที่ให้มา รูปภาพจะถูกเพิ่มไปยังหน้าที่สองของเอกสาร PDF

#### ถาม: ฉันจะปรับตำแหน่งและขนาดของภาพที่เพิ่มได้อย่างไร

 ตอบ: คุณสามารถแก้ไข`lowerLeftX`, `lowerLeftY`, `upperRightX` , และ`upperRightY` ตัวแปรในโค้ดเพื่อกำหนดพิกัดของรูปภาพและควบคุมขนาดและตำแหน่งบนเพจ

#### ถาม: ฉันสามารถเพิ่มรูปแบบรูปภาพประเภทใดได้บ้างโดยใช้วิธีนี้

ตอบ: ตัวอย่างโค้ดที่ให้มาจะถือว่าคุณกำลังโหลดรูปภาพ JPG (`aspose-logo.jpg`). Aspose.PDF สำหรับ .NET รองรับรูปแบบรูปภาพที่หลากหลาย รวมถึง PNG, BMP, GIF และอื่นๆ

#### ถาม: ฉันจะแน่ใจได้อย่างไรว่ารูปภาพที่เพิ่มเข้าไปพอดีภายในพิกัดที่ระบุ

 ตอบ: อย่าลืมปรับพิกัดและขนาดของไฟล์`Rectangle` วัตถุ (`rectangle`เพื่อให้ตรงกับขนาดของรูปภาพและตำแหน่งที่ต้องการบนหน้าเว็บ

#### ถาม: ฉันสามารถเพิ่มรูปภาพหลายรูปลงในหน้า PDF หน้าเดียวได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มรูปภาพหลายรูปลงในหน้า PDF หน้าเดียวได้โดยทำซ้ำขั้นตอนสำหรับแต่ละรูปภาพ และปรับพิกัดและพารามิเตอร์อื่นๆ ตามนั้น

####  ถาม: เป็นยังไงบ้าง`GSave` and `GRestore` operator work in the code?

 ตอบ:`GSave` โอเปอเรเตอร์จะบันทึกสถานะกราฟิกปัจจุบัน ช่วยให้คุณทำการเปลี่ยนแปลงได้โดยไม่กระทบต่อบริบทกราฟิกโดยรวม ที่`GRestore` โอเปอเรเตอร์จะคืนค่าสถานะกราฟิกก่อนหน้าหลังจากทำการเปลี่ยนแปลง

#### ถาม: จะเกิดอะไรขึ้นหากไม่พบไฟล์รูปภาพในเส้นทางที่ระบุ

ตอบ: หากไม่พบไฟล์รูปภาพในเส้นทางที่ระบุ โค้ดจะส่งข้อยกเว้นเมื่อพยายามโหลดสตรีมรูปภาพ ตรวจสอบให้แน่ใจว่าไฟล์รูปภาพอยู่ในไดเร็กทอรีที่ถูกต้อง

#### ถาม: ฉันสามารถปรับแต่งตำแหน่งและรูปลักษณ์ของรูปภาพเพิ่มเติมได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของภาพได้โดยการปรับเปลี่ยน`Matrix`คัดค้านและปรับโอเปอเรเตอร์อื่นๆ ภายในโค้ด โปรดดูเอกสารประกอบ Aspose.PDF สำหรับการปรับแต่งขั้นสูง

#### ถาม: ฉันจะทดสอบได้อย่างไรว่าเพิ่มรูปภาพลงใน PDF สำเร็จแล้ว

ตอบ: หลังจากใช้โค้ดที่ให้มาเพื่อเพิ่มรูปภาพ ให้เปิดไฟล์ PDF ที่แก้ไขแล้วและตรวจสอบว่ารูปภาพนั้นแสดงบนหน้าที่ระบุในตำแหน่งที่ถูกต้อง

#### ถาม: การเพิ่มรูปภาพส่งผลต่อเนื้อหาต้นฉบับของเอกสาร PDF หรือไม่

ตอบ: การเพิ่มรูปภาพจะไม่ส่งผลต่อเนื้อหาต้นฉบับของเอกสาร PDF ช่วยปรับปรุงเอกสารโดยรวมองค์ประกอบภาพ