---
title: จัดเก็บภาพในคอลเลคชัน XImage
linktitle: จัดเก็บภาพในคอลเลคชัน XImage
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: คู่มือทีละขั้นตอนในการจัดเก็บรูปภาพในคอลเลคชัน XImage โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 290
url: /th/net/programming-with-images/store-image-in-ximage-collection/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับวิธีจัดเก็บรูปภาพในคอลเล็กชัน XImage โดยใช้ Aspose.PDF สำหรับ .NET ปฏิบัติตามขั้นตอนเหล่านี้เพื่อดำเนินการนี้ได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งและกำหนดค่า Visual Studio หรือสภาพแวดล้อมการพัฒนาอื่น ๆ
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose

## ขั้นตอนที่ 1: การเริ่มต้นเอกสาร PDF

ในการเริ่มต้น ให้ใช้โค้ดต่อไปนี้เพื่อเริ่มต้นเอกสาร PDF ใหม่:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//การเริ่มต้นเอกสาร
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## ขั้นตอนที่ 2: การเพิ่มรูปภาพลงในคอลเลคชัน XImage

ต่อไปเราจะเพิ่มรูปภาพลงในคอลเล็กชัน XImage ของเอกสาร PDF โดยใช้โค้ดต่อไปนี้:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

โปรดแน่ใจว่าระบุเส้นทางที่ถูกต้องไปยังไฟล์ต้นฉบับของรูปภาพ

## ขั้นตอนที่ 3: การวางรูปภาพบนหน้า

ต่อไปเราจะวางรูปภาพบนหน้าเอกสาร PDF โดยใช้โค้ดต่อไปนี้:

```csharp
page. Contents. Add(new GSave());

// ตั้งค่าพิกัด
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

การกระทำดังกล่าวจะวางรูปภาพตามพิกัดที่ระบุบนหน้า

## ขั้นตอนที่ 4: บันทึกเอกสาร PDF

สุดท้ายเราจะบันทึกเอกสาร PDF ที่อัปเดตแล้ว ใช้โค้ดต่อไปนี้:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ต้องการสำหรับเอกสาร PDF ขั้นสุดท้าย

### ตัวอย่างโค้ดต้นฉบับสำหรับ Store Image ใน XImage Collection โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// การเริ่มต้นเอกสาร
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
// ตั้งค่าพิกัด
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
// การใช้ตัวดำเนินการ ConcatenateMatrix (เมทริกซ์เชื่อม): กำหนดว่าจะต้องวางรูปภาพอย่างไร
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## บทสรุป

ขอแสดงความยินดี! คุณได้จัดเก็บรูปภาพในคอลเล็กชัน XImage โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว ตอนนี้คุณสามารถนำวิธีนี้ไปใช้กับโปรเจ็กต์ของคุณเองเพื่อจัดการและปรับแต่งรูปภาพในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของการจัดเก็บรูปภาพในคอลเลคชัน XImage โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

A: การจัดเก็บรูปภาพในคอลเล็กชัน XImage ช่วยให้คุณจัดการและใช้รูปภาพภายในเอกสาร PDF ได้อย่างมีประสิทธิภาพ วิธีนี้ช่วยให้คุณจัดการ ปรับแต่ง และปรับแต่งรูปภาพส่วนบุคคลก่อนวางลงในหน้าเฉพาะ

#### ถาม: การจัดเก็บรูปภาพในคอลเลคชัน XImage แตกต่างจากการวางรูปภาพลงบนหน้า PDF โดยตรงอย่างไร

A: การจัดเก็บภาพในคอลเลกชัน XImage ช่วยให้จัดการภาพได้เป็นระเบียบและนำกลับมาใช้ใหม่ได้ดีกว่า แทนที่จะวางภาพบนหน้าโดยตรง คุณสามารถจัดเก็บภาพในคอลเลกชันแล้วจึงอ้างอิงชื่อภาพได้เมื่อต้องการ ช่วยให้จัดการและปรับเปลี่ยนได้ง่ายขึ้น

#### ถาม: ฉันสามารถเพิ่มรูปภาพหลาย ๆ รูปลงในคอลเลคชัน XImage ภายในเอกสาร PDF เดียวได้หรือไม่

A: ใช่ คุณสามารถเพิ่มรูปภาพหลายภาพลงในคอลเลกชัน XImage ภายในเอกสาร PDF เดียวกันได้ รูปภาพแต่ละภาพจะได้รับการกำหนดชื่อเฉพาะในคอลเลกชัน ซึ่งสามารถนำไปใช้อ้างอิงและวางรูปภาพในหน้าต่างๆ ได้

#### ถาม: ฉันจะระบุตำแหน่งและขนาดของรูปภาพเมื่อวางไว้บนหน้า PDF จากคอลเลกชัน XImage ได้อย่างไร

ก: หากต้องการระบุตำแหน่งและขนาดของภาพ คุณต้องกำหนดรูปสี่เหลี่ยมผืนผ้าและการแปลงเมทริกซ์ รูปสี่เหลี่ยมผืนผ้าจะกำหนดขอบเขตของภาพ และการแปลงเมทริกซ์จะระบุว่าควรวางภาพภายในรูปสี่เหลี่ยมผืนผ้านั้นอย่างไร

####  ถาม: จุดประสงค์ของการ`GSave()` and `GRestore()` operators in the code for placing the image?

 ก. การ`GSave()` และ`GRestore()` ตัวดำเนินการใช้เพื่อบันทึกและกู้คืนสถานะกราฟิกของหน้า PDF วิธีนี้ช่วยให้มั่นใจว่าการดำเนินการที่ดำเนินการบนหน้า เช่น การวางรูปภาพ จะไม่ส่งผลกระทบต่อสถานะของหน้าหลังจากวางรูปภาพแล้ว

#### ถาม: ฉันสามารถใช้การปรับเปลี่ยนเพิ่มเติมหรือการแปลงรูปภาพที่เก็บไว้ในคอลเลกชัน XImage ได้หรือไม่

A: ใช่ คุณสามารถปรับเปลี่ยนและเปลี่ยนแปลงรูปภาพที่เก็บไว้ในคอลเลกชัน XImage ได้หลากหลายวิธี คุณสามารถหมุน ปรับขนาด ครอบตัด และเปลี่ยนแปลงอื่นๆ ได้โดยใช้การดำเนินการและเทคนิคที่เหมาะสมซึ่งจัดทำโดย Aspose.PDF สำหรับ .NET

#### ถาม: ฉันจะรวมวิธีนี้เข้ากับโปรเจ็กต์ของตัวเองเพื่อจัดเก็บและวางรูปภาพในคอลเล็กชัน XImage ของเอกสาร PDF ได้อย่างไร

A: หากต้องการรวมวิธีการนี้ ให้ทำตามขั้นตอนที่ระบุไว้และแก้ไขโค้ดเพื่อให้ตรงตามข้อกำหนดของโครงการของคุณ คุณสามารถใช้คอลเลกชัน XImage เพื่อจัดเก็บและจัดการรูปภาพ จากนั้นจึงวางไว้ในหน้าเฉพาะโดยใช้พิกัดและการแปลงที่ระบุ

#### ถาม: มีข้อควรพิจารณาหรือข้อจำกัดใดๆ หรือไม่เมื่อทำงานกับคอลเลกชัน XImage ใน Aspose.PDF สำหรับ .NET

A: แม้ว่าคอลเล็กชัน XImage จะเป็นวิธีที่มีประสิทธิภาพในการจัดการและปรับแต่งรูปภาพ แต่สิ่งสำคัญคือต้องพิจารณาปัจจัยต่างๆ เช่น การใช้หน่วยความจำและความซับซ้อนของการดำเนินการกับรูปภาพ ขอแนะนำให้จัดการคอลเล็กชันอย่างระมัดระวังและใช้ทรัพยากรอย่างมีประสิทธิภาพ

#### ถาม: ฉันสามารถนำรูปภาพที่เก็บไว้ในคอลเลคชัน XImage มาใช้ซ้ำกับเอกสาร PDF หลายฉบับได้หรือไม่

A: คอลเลกชัน XImage นั้นเฉพาะเจาะจงสำหรับเอกสาร PDF แต่ละฉบับและไม่ได้ออกแบบมาเพื่อการใช้งานซ้ำในเอกสารหลายฉบับ หากคุณจำเป็นต้องใช้งานรูปภาพซ้ำในเอกสารหลายฉบับ คุณจะต้องจัดเก็บและจัดการรูปภาพเหล่านี้แยกกันสำหรับเอกสารแต่ละฉบับ