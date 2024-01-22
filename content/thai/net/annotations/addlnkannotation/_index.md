---
title: เพิ่มคำอธิบายประกอบ lnk
linktitle: เพิ่มคำอธิบายประกอบ lnk
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มคุณสมบัติ Ink Annotation ให้กับเอกสาร PDF ใน C# โดยใช้ Aspose.PDF สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนและซอร์สโค้ดแบบเต็ม
type: docs
weight: 20
url: /th/net/annotations/addlnkannotation/
---
Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้นักพัฒนาสามารถดำเนินการ PDF ต่างๆ ได้ การดำเนินการอย่างหนึ่งคือการเพิ่ม Ink Annotation ลงในเอกสาร PDF ในบทความนี้ เราจะให้คำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# สำหรับการเพิ่ม Ink Annotation โดยใช้ Aspose.PDF สำหรับ .NET มาเริ่มกันเลย!

## ทำความเข้าใจคุณสมบัติ Ink Annotation ของ Aspose.PDF สำหรับ .NET

ก่อนที่จะเจาะลึกซอร์สโค้ด C# เรามาทำความเข้าใจก่อนว่า Ink Annotation คืออะไรและใช้งานอย่างไร

Ink Annotation เป็นวิธีหนึ่งในการวาดคำอธิบายประกอบด้วยหมึกรูปแบบอิสระบนเอกสาร PDF ช่วยให้คุณสร้างคำอธิบายประกอบด้วยสไตลัสหรือเมาส์ คุณสมบัตินี้มีประโยชน์ในสถานการณ์ที่คุณต้องการวาดไดอะแกรม สเก็ตช์ หรือคำอธิบายประกอบประเภทอื่นๆ

## ขั้นตอนที่ 1: การสร้างเอกสารใหม่

ขั้นตอนแรกในการเพิ่ม Ink Annotation ให้กับเอกสาร PDF คือการสร้างอินสแตนซ์ใหม่ของคลาส Document สามารถทำได้โดยใช้ข้อมูลโค้ดต่อไปนี้:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

ที่นี่ เราสร้างอินสแตนซ์ใหม่ของคลาส Document และเพิ่มหน้าใหม่ลงไป

## ขั้นตอนที่ 2: การสร้างคำอธิบายประกอบแบบหมึก

ขั้นตอนต่อไปคือการสร้างอินสแตนซ์ของคลาส InkAnnotation ทำได้โดยใช้ข้อมูลโค้ดต่อไปนี้:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(จังหวะ.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

ที่นี่ ขั้นแรกเราสร้างสี่เหลี่ยมผืนผ้าโดยใช้คลาส System. Drawing.Rectangle และแปลงเป็น Aspose.Pdf.Rectangle โดยใช้เมธอด FromRect จากนั้นเราจะสร้างอินสแตนซ์ของคลาส InkAnnotation โดยใช้สี่เหลี่ยม รายการจุด และหน้าที่เพิ่มคำอธิบายประกอบ

จากนั้นเราตั้งค่าคุณสมบัติต่างๆ ของ InkAnnotation เช่น ชื่อ สี รูปแบบหมวก เส้นขอบ และความทึบ สุดท้ายนี้ เราเพิ่มคำอธิบายประกอบลงในเพจโดยใช้วิธี Annotations.Add

## ขั้นตอนที่ 3: บันทึกเอกสาร

ขั้นตอนสุดท้ายคือการบันทึกเอกสาร PDF โดยเพิ่ม Ink Annotation สามารถทำได้โดยใช้ข้อมูลโค้ดต่อไปนี้:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

ที่นี่ เราเชื่อมชื่อไฟล์เอาต์พุตเข้ากับไดเร็กทอรีข้อมูล และบันทึกเอกสารโดยใช้วิธีบันทึก

### ตัวอย่างซอร์สโค้ดสำหรับการเพิ่ม Ink Annotation โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(จังหวะ.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// บันทึกไฟล์เอาต์พุต
doc.Save(dataDir);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีการเพิ่มคำอธิบายประกอบแบบหมึกลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและซอร์สโค้ด C# ที่ให้มา นักพัฒนาจึงสามารถใช้ฟังก์ชัน Ink Annotation ในแอปพลิเคชันประมวลผล PDF ของตนได้อย่างง่ายดาย

### คำถามที่พบบ่อย

#### ถาม: Ink Annotation ในเอกสาร PDF คืออะไร

ตอบ: Ink Annotation ในเอกสาร PDF ช่วยให้ผู้ใช้สามารถวาดคำอธิบายประกอบที่เป็นหมึกรูปแบบอิสระได้โดยใช้สไตลัสหรือเมาส์ โดยทั่วไปจะใช้เพื่อเพิ่มภาพร่างที่วาดด้วยมือ ไดอะแกรม หรือคำอธิบายประกอบด้วยมือเปล่าอื่นๆ ลงใน PDF

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของ Ink Annotation ได้หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET มีคุณสมบัติต่างๆ เพื่อปรับแต่งลักษณะที่ปรากฏของ Ink Annotation เช่น สี ความทึบ รูปแบบหมวก ความกว้างของเส้นขอบ และอื่นๆ นักพัฒนาซอฟต์แวร์สามารถปรับคุณสมบัติเหล่านี้ให้ตรงตามความต้องการเฉพาะของตนได้

#### ถาม: เป็นไปได้หรือไม่ที่จะเพิ่ม Ink Annotation หลายรายการลงในหน้า PDF หน้าเดียว

ตอบ: ได้ คุณสามารถเพิ่ม Ink Annotation หลายรายการลงในหน้า PDF หน้าเดียวได้โดยใช้ Aspose.PDF สำหรับ .NET คำอธิบายประกอบแบบหมึกแต่ละรายการสามารถมีชุดจุดและรูปลักษณ์ที่กำหนดเองได้

#### ถาม: ฉันสามารถเพิ่ม Ink Annotations ให้กับเอกสาร PDF ที่มีอยู่ได้หรือไม่

ตอบ: ได้ Aspose.PDF สำหรับ .NET อนุญาตให้คุณเพิ่ม Ink Annotations ให้กับทั้งเอกสาร PDF ที่สร้างขึ้นใหม่และไฟล์ PDF ที่มีอยู่ คุณสามารถเปิด PDF ที่มีอยู่ เพิ่ม Ink Annotations และบันทึกเอกสารที่อัพเดตได้

#### ถาม: กรณีการใช้งานทั่วไปสำหรับ Ink Annotation ในเอกสาร PDF มีอะไรบ้าง

ตอบ: คำอธิบายประกอบแบบหมึกมีประโยชน์สำหรับการใช้งานที่หลากหลาย รวมถึงการเพิ่มลายเซ็นหรือบันทึกย่อที่เขียนด้วยลายมือลงในแบบฟอร์ม PDF การใส่คำอธิบายประกอบแบบพิมพ์เขียวทางสถาปัตยกรรมหรือแบบวิศวกรรม และการทำเครื่องหมายเอกสารสำหรับการตรวจสอบร่วมกัน