---
title: เก็บรูปภาพไว้ในคอลเลกชัน XImage
linktitle: เก็บรูปภาพไว้ในคอลเลกชัน XImage
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการจัดเก็บรูปภาพในคอลเลกชัน XImage โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 290
url: /th/net/programming-with-images/store-image-in-ximage-collection/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีจัดเก็บรูปภาพในคอลเลกชัน XImage โดยใช้ Aspose.PDF สำหรับ .NET ทำตามขั้นตอนเหล่านี้เพื่อดำเนินการนี้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือสภาพแวดล้อมการพัฒนาอื่น ๆ ที่ติดตั้งและกำหนดค่า
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose

## ขั้นตอนที่ 1: การเริ่มต้นเอกสาร PDF

ในการเริ่มต้น ให้ใช้โค้ดต่อไปนี้เพื่อเริ่มต้นเอกสาร PDF ใหม่:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//เริ่มต้นเอกสาร
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## ขั้นตอนที่ 2: การเพิ่มรูปภาพลงในคอลเลกชัน XImage

ต่อไป เราจะเพิ่มรูปภาพลงในคอลเลกชัน XImage ของเอกสาร PDF ใช้รหัสต่อไปนี้:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางที่ถูกต้องไปยังไฟล์ต้นฉบับของรูปภาพ

## ขั้นตอนที่ 3: การวางตำแหน่งรูปภาพบนหน้า

ตอนนี้เรามาวางรูปภาพบนหน้าของเอกสาร PDF ใช้รหัสต่อไปนี้:

```csharp
page. Contents. Add(new GSave());

// กำหนดพิกัด
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

// การใช้ตัวดำเนินการ ConcatenateMatrix: กำหนดวิธีการวางรูปภาพ
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

ซึ่งจะวางรูปภาพตามพิกัดที่ระบุบนหน้า

## ขั้นตอนที่ 4: บันทึกเอกสาร PDF

สุดท้ายนี้ เราจะบันทึกเอกสาร PDF ที่อัปเดตแล้ว ใช้รหัสต่อไปนี้:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ต้องการสำหรับเอกสาร PDF สุดท้าย

### ตัวอย่างซอร์สโค้ดสำหรับ Store Image ใน XImage Collection โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เริ่มต้นเอกสาร
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
// กำหนดพิกัด
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
// การใช้ตัวดำเนินการ ConcatenateMatrix (concatenate matrix): กำหนดวิธีการวางรูปภาพ
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## บทสรุป

ขอแสดงความยินดี! คุณได้จัดเก็บรูปภาพในคอลเลกชัน XImage โดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว ตอนนี้คุณสามารถใช้วิธีนี้กับโปรเจ็กต์ของคุณเองเพื่อจัดการและปรับแต่งรูปภาพในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของการจัดเก็บภาพในคอลเลกชัน XImage โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: การจัดเก็บรูปภาพในคอลเลกชัน XImage ช่วยให้คุณสามารถจัดการและใช้รูปภาพภายในเอกสาร PDF ได้อย่างมีประสิทธิภาพ แนวทางนี้ช่วยให้คุณสามารถจัดการ ปรับแต่ง และปรับแต่งรูปภาพก่อนที่จะวางลงในหน้าใดหน้าหนึ่งได้

#### ถาม: การจัดเก็บรูปภาพในคอลเลกชัน XImage แตกต่างจากการวางรูปภาพโดยตรงบนหน้า PDF อย่างไร

ตอบ: การจัดเก็บรูปภาพในคอลเลกชัน XImage ช่วยให้จัดการรูปภาพได้อย่างเป็นระเบียบและสามารถนำมาใช้ซ้ำได้ แทนที่จะวางรูปภาพบนเพจโดยตรง คุณจะจัดเก็บไว้ในคอลเลกชันและสามารถอ้างอิงตามชื่อได้เมื่อจำเป็น ช่วยให้การจัดการและการแก้ไขทำได้ง่ายขึ้น

#### ถาม: ฉันสามารถเพิ่มรูปภาพหลายรูปลงในคอลเลกชัน XImage ภายในเอกสาร PDF เดียวได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มรูปภาพหลายรูปลงในคอลเลกชัน XImage ภายในเอกสาร PDF เดียวกันได้ รูปภาพแต่ละรูปจะได้รับการกำหนดชื่อที่ไม่ซ้ำกันในคอลเลกชัน ซึ่งสามารถใช้เพื่ออ้างอิงและวางรูปภาพในหน้าต่างๆ

#### ถาม: ฉันจะระบุตำแหน่งและขนาดของรูปภาพเมื่อวางลงบนหน้า PDF จากคอลเลกชัน XImage ได้อย่างไร

ตอบ: หากต้องการระบุตำแหน่งและขนาดของรูปภาพ คุณต้องกำหนดการแปลงรูปสี่เหลี่ยมผืนผ้าและเมทริกซ์ สี่เหลี่ยมผืนผ้าจะกำหนดขอบเขตของรูปภาพ และการแปลงเมทริกซ์จะระบุว่าควรวางรูปภาพไว้ภายในสี่เหลี่ยมผืนผ้านั้นอย่างไร

####  ถาม: จุดประสงค์ของ.`GSave()` and `GRestore()` operators in the code for placing the image?

 ตอบ:`GSave()` และ`GRestore()` โอเปอเรเตอร์ใช้ในการบันทึกและกู้คืนสถานะกราฟิกของหน้า PDF เพื่อให้แน่ใจว่าการดำเนินการที่ทำบนเพจ เช่น การวางรูปภาพ จะไม่ส่งผลกระทบต่อสถานะของเพจหลังจากวางรูปภาพแล้ว

#### ถาม: ฉันสามารถใช้การแก้ไขหรือการแปลงเพิ่มเติมกับรูปภาพที่เก็บไว้ในคอลเลกชัน XImage ได้หรือไม่

ตอบ: ได้ คุณสามารถใช้การแก้ไขและการแปลงภาพต่างๆ ที่เก็บไว้ในคอลเลกชัน XImage ได้ คุณสามารถหมุน ปรับขนาด ครอบตัด และดำเนินการแปลงอื่นๆ ได้โดยใช้การดำเนินการและเทคนิคที่เหมาะสมที่ Aspose.PDF สำหรับ .NET มอบให้

#### ถาม: ฉันจะรวมวิธีการนี้เข้ากับโปรเจ็กต์ของฉันเองเพื่อจัดเก็บและวางรูปภาพในคอลเลกชัน XImage ของเอกสาร PDF ได้อย่างไร

ตอบ: หากต้องการผสานรวมวิธีนี้ ให้ทำตามขั้นตอนที่ระบุไว้และแก้ไขโค้ดเพื่อให้ตรงตามข้อกำหนดของโปรเจ็กต์ของคุณ คุณสามารถใช้คอลเลกชัน XImage เพื่อจัดเก็บและจัดการรูปภาพ จากนั้นวางรูปภาพเหล่านั้นบนเพจเฉพาะโดยใช้พิกัดและการแปลงที่ระบุ

#### ถาม: มีข้อควรพิจารณาหรือข้อจำกัดเมื่อทำงานกับคอลเลกชัน XImage ใน Aspose.PDF สำหรับ .NET หรือไม่

ตอบ: แม้ว่าคอลเลกชัน XImage จะให้วิธีที่มีประสิทธิภาพในการจัดการและจัดการรูปภาพ แต่สิ่งสำคัญคือต้องพิจารณาปัจจัยต่างๆ เช่น การใช้หน่วยความจำ และความซับซ้อนของการดำเนินการที่ทำกับรูปภาพ แนะนำให้มีการจัดการการรวบรวมอย่างระมัดระวังและการใช้ทรัพยากรอย่างมีประสิทธิภาพ

#### ถาม: ฉันสามารถนำรูปภาพที่เก็บไว้ในคอลเลกชัน XImage มาใช้ซ้ำกับเอกสาร PDF หลายฉบับได้หรือไม่

ตอบ: คอลเลกชัน XImage มีไว้สำหรับเอกสาร PDF แต่ละฉบับโดยเฉพาะ และไม่ได้ออกแบบมาเพื่อการนำข้ามเอกสารไปใช้ซ้ำ หากคุณต้องการนำรูปภาพไปใช้ซ้ำในเอกสารหลายฉบับ คุณจะต้องจัดเก็บและจัดการรูปภาพแยกกันสำหรับเอกสารแต่ละฉบับ