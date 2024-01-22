---
title: ใช้สไตล์ตัวเลขในไฟล์ PDF
linktitle: ใช้สไตล์ตัวเลขในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีใช้รูปแบบการกำหนดหมายเลขกับส่วนหัวในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/programming-with-headings/apply-number-style/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# ต่อไปนี้ทีละขั้นตอนเพื่อใช้รูปแบบการกำหนดหมายเลขในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET

ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณก่อนที่จะเริ่มต้น มีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# ด้วย

### ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในซอร์สโค้ดที่ให้มา คุณจะต้องระบุไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น เปลี่ยนตัวแปร "dataDir" เป็นไดเร็กทอรีที่ต้องการ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### ขั้นตอนที่ 2: การสร้างเอกสาร PDF

เราสร้างเอกสาร PDF ใหม่โดยระบุขนาดและระยะขอบ

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### ขั้นตอนที่ 3: การสร้างเพจและคอนเทนเนอร์แบบลอย

เราเพิ่มหน้าลงในเอกสารและสร้างคอนเทนเนอร์แบบลอยเพื่อจัดระเบียบเนื้อหา

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### ขั้นตอนที่ 4: เพิ่มหัวข้อด้วยการกำหนดหมายเลข

เราสร้างส่วนหัวที่มีหมายเลขที่ระบุและเพิ่มลงในคอนเทนเนอร์แบบลอย

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### ขั้นตอนที่ 5: บันทึกเอกสาร PDF

เราบันทึกเอกสาร PDF ที่สร้างขึ้นในไดเร็กทอรีที่ระบุ

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับ Apply Number Style โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายวิธีใช้รูปแบบการกำหนดหมายเลขกับส่วนหัวในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อสร้างเอกสาร PDF พร้อมการกำหนดหมายเลขสำหรับส่วนหัวแบบกำหนดเองได้

### คำถามที่พบบ่อยเกี่ยวกับการใช้รูปแบบตัวเลขในไฟล์ PDF

#### ถาม: รูปแบบการกำหนดหมายเลขในเอกสาร PDF คืออะไร

ตอบ: รูปแบบการกำหนดหมายเลขหมายถึงรูปแบบที่ส่วนหัวหรือส่วนต่างๆ ถูกกำหนดหมายเลขในเอกสาร PDF ซึ่งอาจรวมถึงตัวเลข ตัวอักษร หรืออักขระอื่นๆ เพื่อให้มีโครงสร้างแบบลำดับชั้น

#### ถาม: เหตุใดฉันจึงต้องใช้รูปแบบการกำหนดหมายเลขกับส่วนหัวในเอกสาร PDF

ตอบ: การใช้รูปแบบการกำหนดหมายเลขกับส่วนหัวจะช่วยเพิ่มความสามารถในการอ่านและการจัดระเบียบเอกสาร PDF ของคุณ ช่วยให้ผู้อ่านนำทางและเข้าใจโครงสร้างลำดับชั้นของเนื้อหาได้อย่างง่ายดาย

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ PDF โดยทางโปรแกรมในแอปพลิเคชัน .NET มีคุณสมบัติมากมายสำหรับการสร้าง แก้ไข แปลง และจัดการเอกสาร PDF

#### ถาม: ฉันจะนำเข้าไลบรารีที่จำเป็นสำหรับโปรเจ็กต์ C# ของฉันได้อย่างไร

ตอบ: หากต้องการนำเข้าไลบรารีที่จำเป็นสำหรับโครงการ C# ของคุณ ให้รวมคำสั่งการนำเข้าต่อไปนี้:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

คำสั่งเหล่านี้ช่วยให้คุณเข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการทำงานกับเอกสาร PDF และการใช้สไตล์การกำหนดหมายเลข

#### ถาม: ฉันจะระบุไดเร็กทอรีสำหรับบันทึกไฟล์ PDF ที่สร้างขึ้นได้อย่างไร

ตอบ: ในซอร์สโค้ดที่ให้มา ให้แก้ไขตัวแปร "dataDir" เพื่อระบุไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 แทนที่`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางไดเร็กทอรีจริง

#### ถาม: ฉันจะสร้างเอกสาร PDF โดยระบุขนาดและระยะขอบได้อย่างไร

ตอบ: หากต้องการสร้างเอกสาร PDF ที่มีขนาดและระยะขอบที่ระบุ ให้ใช้รหัสต่อไปนี้:

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### ถาม: ฉันจะเพิ่มส่วนหัวที่มีรูปแบบการกำหนดหมายเลขลงในเอกสาร PDF ได้อย่างไร

ตอบ: หากต้องการเพิ่มส่วนหัวที่มีรูปแบบการกำหนดหมายเลขให้กับเอกสาร PDF ให้ใช้ตัวอย่างโค้ดที่ให้มาเพื่อสร้างส่วนหัวและกำหนดรูปแบบการกำหนดหมายเลขเอง ปรับคุณสมบัติ เช่น ข้อความ รูปแบบการกำหนดหมายเลข หมายเลขเริ่มต้น และลำดับอัตโนมัติตามต้องการ

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่สร้างขึ้นได้อย่างไร

 ตอบ: หากต้องการบันทึกเอกสาร PDF ที่สร้างขึ้น ให้ใช้ไฟล์`Save` วิธีการของ`pdfDoc` วัตถุ:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### ถาม: ฉันจะยืนยันได้อย่างไรว่ามีการใช้รูปแบบการกำหนดหมายเลขแล้ว

ตอบ: เปิดไฟล์ PDF ที่สร้างขึ้นเพื่อตรวจสอบว่ามีการใช้รูปแบบการกำหนดหมายเลขที่ระบุกับส่วนหัวแล้ว

#### ถาม: ฉันสามารถปรับแต่งรูปแบบการกำหนดหมายเลขเพิ่มเติมได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งรูปแบบการกำหนดหมายเลขเพิ่มเติมได้โดยการปรับคุณสมบัติของ`Heading` ออบเจ็กต์ เช่น ประเภทสไตล์การกำหนดหมายเลข หมายเลขเริ่มต้น และลำดับอัตโนมัติ

#### ถาม: ฉันสามารถใช้รูปแบบการกำหนดหมายเลขที่แตกต่างกันกับส่วนต่างๆ ของเอกสารได้หรือไม่

ตอบ: ได้ คุณสามารถใช้รูปแบบการกำหนดหมายเลขที่แตกต่างกันกับส่วนต่างๆ ของเอกสารได้โดยการสร้างหลายรูปแบบ`Heading` วัตถุที่มีรูปแบบและลำดับต่างกัน