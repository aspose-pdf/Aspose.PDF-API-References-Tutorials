---
title: สร้างไฟล์ PDF หลายชั้นแนวทางแรก
linktitle: สร้างแนวทางแรกในรูปแบบ PDF หลายชั้น
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีสร้างไฟล์ PDF หลายชั้นโดยใช้ First Approach ด้วย Aspose.PDF สำหรับ .NET เพิ่มข้อความ รูปภาพ และอื่นๆ เพื่อปรับปรุง PDF ของคุณ
type: docs
weight: 70
url: /th/net/programming-with-document/createmultilayerpdffirstapproach/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้างไฟล์ PDF หลายชั้นโดยใช้แนวทางแรกด้วย Aspose.PDF สำหรับ .NET วิธีนี้ช่วยให้คุณเพิ่มหลายเลเยอร์ลงในไฟล์ PDF ของคุณได้ ทำตามคำแนะนำทีละขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: เริ่มต้นเอกสาร PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```

## ขั้นตอนที่ 2: เพิ่มหน้าใหม่ลงในเอกสาร

```csharp
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
```

## ขั้นตอนที่ 3: เพิ่มส่วนของข้อความลงในหน้า

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);
```

## ขั้นตอนที่ 4: ปรับแต่งส่วนของข้อความ

```csharp
t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;
```

## ขั้นตอนที่ 5: เพิ่มรูปภาพลงในเพจ

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
```

## ขั้นตอนที่ 6: เพิ่มกล่องลอยลงในเพจ

```csharp
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);
```

## ขั้นตอนที่ 7: บันทึกเอกสาร PDF ที่เป็นผลลัพธ์

```csharp
pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

ยินดีด้วย! คุณสร้างเอกสาร PDF หลายชั้นได้สำเร็จโดยใช้แนวทางแรกด้วย Aspose.PDF สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับการสร้าง Multilayer PDF First Approach โดยใช้ Aspose.PDF สำหรับ .NET:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);

t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;

Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);

pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

ตอนนี้คุณสามารถสร้างเอกสาร PDF หลายชั้นโดยใช้แนวทางแรกด้วย Aspose.PDF สำหรับ .NET

## บทสรุป

ในบทช่วยสอนนี้ เราได้สาธิตวิธีสร้างเอกสาร PDF หลายชั้นโดยใช้แนวทางแรกด้วย Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ด C# ที่ให้มา คุณสามารถเพิ่มหลายเลเยอร์ลงในเอกสาร PDF ของคุณได้อย่างง่ายดาย เลเยอร์ในเอกสาร PDF มอบความยืดหยุ่นและการโต้ตอบที่ดีขึ้น ช่วยให้คุณสร้างเนื้อหาแบบไดนามิกและปรับแต่งได้ Aspose.PDF สำหรับ .NET มอบโซลูชันที่เชื่อถือได้และมีประสิทธิภาพสำหรับการทำงานกับ PDF ในแอปพลิเคชัน .NET ทำให้คุณสามารถสร้างเอกสาร PDF ที่ซับซ้อนและโต้ตอบได้อย่างง่ายดาย

### คำถามที่พบบ่อยสำหรับการสร้างไฟล์ PDF หลายชั้นแนวทางแรก

#### ถาม: เอกสาร PDF หลายชั้นคืออะไร

ตอบ: เอกสาร PDF แบบหลายเลเยอร์หรือที่เรียกว่า PDF แบบหลายเลเยอร์ประกอบด้วยเนื้อหาหลายเลเยอร์ที่สามารถควบคุมแยกกันเพื่อให้มองเห็นและความทึบได้ เลเยอร์ในเอกสาร PDF ช่วยให้ผู้ใช้สามารถเลือกแสดงหรือซ่อนองค์ประกอบเนื้อหาที่ต้องการได้

#### ถาม: ฉันจะเพิ่มเลเยอร์ลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: คุณสามารถเพิ่มเลเยอร์ลงในเอกสาร PDF ได้โดยใช้ Aspose.PDF สำหรับ .NET โดยการสร้างกล่องแบบลอยและเพิ่มองค์ประกอบเนื้อหา เช่น ข้อความและรูปภาพ ลงในกล่องเหล่านี้ กล่องลอยแต่ละกล่องสามารถแสดงเลเยอร์ที่แยกจากกัน และคุณสามารถควบคุมการมองเห็นและการวางตำแหน่งบนเพจได้

#### ถาม: การสร้าง PDF หลายชั้นให้ประโยชน์อะไรบ้าง

ตอบ: การสร้าง PDF หลายชั้นช่วยเพิ่มความยืดหยุ่นและการโต้ตอบกับเอกสาร เลเยอร์ช่วยให้คุณจัดระเบียบและจัดการองค์ประกอบเนื้อหาได้อย่างมีประสิทธิภาพ ทำให้ควบคุมการแสดงผลและสร้างเอกสารเชิงโต้ตอบได้ง่ายขึ้น

#### ถาม: ฉันสามารถเพิ่มหลายเลเยอร์ในหน้าเดียวในเอกสาร PDF ได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มหลายเลเยอร์ในหน้าเดียวในเอกสาร PDF ได้โดยการสร้างและวางตำแหน่งกล่องลอยหลายกล่อง กล่องลอยแต่ละกล่องสามารถแสดงถึงเลเยอร์ที่แยกจากกัน และคุณสามารถเพิ่มองค์ประกอบเนื้อหาลงในแต่ละกล่องได้

#### ถาม: Aspose.PDF สำหรับ .NET เหมาะสำหรับโครงการระดับมืออาชีพที่เกี่ยวข้องกับ PDF หลายชั้นหรือไม่

ตอบ: แน่นอนว่า Aspose.PDF สำหรับ .NET เป็นไลบรารี่ที่แข็งแกร่งและเต็มไปด้วยฟีเจอร์ที่ใช้กันอย่างแพร่หลายในโครงการระดับมืออาชีพสำหรับการจัดการ PDF รวมถึงการสร้าง PDF หลายชั้น มีฟังก์ชันการทำงานที่ครอบคลุมสำหรับการทำงานกับเอกสาร PDF ในแอปพลิเคชัน .NET