---
title: นำรูปแบบตัวเลขมาใช้ในไฟล์ PDF
linktitle: นำรูปแบบตัวเลขมาใช้ในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีใช้รูปแบบการนับหมายเลขกับหัวเรื่องในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/programming-with-headings/apply-number-style/
---
ในบทช่วยสอนนี้ เราจะพาคุณเรียนรู้โค้ดต้นฉบับ C# ทีละขั้นตอนเพื่อใช้รูปแบบการนับหมายเลขในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET

ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณก่อนเริ่มต้น นอกจากนี้ ควรมีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# ด้วย

### ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในซอร์สโค้ดที่ให้มา คุณต้องระบุไดเรกทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น เปลี่ยนตัวแปร "dataDir" เป็นไดเรกทอรีที่ต้องการ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### ขั้นตอนที่ 2: การสร้างเอกสาร PDF

เราสร้างเอกสาร PDF ใหม่โดยมีขนาดและระยะขอบที่กำหนด

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

### ขั้นตอนที่ 4: เพิ่มหัวข้อพร้อมการใส่หมายเลข

เราสร้างส่วนหัวพร้อมการกำหนดหมายเลขที่กำหนดและเพิ่มลงในคอนเทนเนอร์แบบลอยตัว

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

เราบันทึกเอกสาร PDF ที่สร้างขึ้นลงในไดเร็กทอรีที่ระบุ

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการนำรูปแบบตัวเลขไปใช้โดยใช้ Aspose.PDF สำหรับ .NET 
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

ในบทช่วยสอนนี้ เราได้อธิบายวิธีการใช้รูปแบบการนับหมายเลขกับหัวเรื่องในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้ความรู้เหล่านี้เพื่อสร้างเอกสาร PDF ที่มีการกำหนดหมายเลขสำหรับหัวเรื่องแบบกำหนดเองได้แล้ว

### คำถามที่พบบ่อยสำหรับการใช้รูปแบบตัวเลขในไฟล์ PDF

#### ถาม: รูปแบบการนับหมายเลขในเอกสาร PDF คืออะไร

A: รูปแบบการนับเลขหมายถึงรูปแบบที่ใช้กำหนดหมายเลขหัวข้อหรือส่วนต่างๆ ในเอกสาร PDF ซึ่งอาจรวมถึงตัวเลข ตัวอักษร หรืออักขระอื่นๆ เพื่อให้มีโครงสร้างแบบลำดับชั้น

#### ถาม: เหตุใดฉันจึงต้องใช้รูปแบบการนับหมายเลขกับหัวเรื่องในเอกสาร PDF

ก: การใช้รูปแบบการนับเลขกับหัวเรื่องจะช่วยให้เอกสาร PDF ของคุณอ่านง่ายขึ้นและจัดระเบียบง่ายขึ้น นอกจากนี้ยังช่วยให้ผู้อ่านสามารถนำทางและเข้าใจโครงสร้างลำดับชั้นของเนื้อหาได้อย่างง่ายดาย

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร?

A: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ PDF ในแอปพลิเคชัน .NET ได้ด้วยโปรแกรม โดยไลบรารีนี้มีคุณสมบัติมากมายสำหรับการสร้าง แก้ไข แปลง และจัดการเอกสาร PDF

#### ถาม: ฉันจะนำเข้าไลบรารีที่จำเป็นสำหรับโครงการ C# ของฉันได้อย่างไร

ก: หากต้องการนำเข้าไลบรารีที่จำเป็นสำหรับโครงการ C# ของคุณ โปรดรวมคำสั่งนำเข้าต่อไปนี้:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

คำสั่งเหล่านี้ช่วยให้คุณสามารถเข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการทำงานกับเอกสาร PDF และการใช้รูปแบบการนับหมายเลข

#### ถาม: ฉันจะระบุไดเร็กทอรีสำหรับบันทึกไฟล์ PDF ที่สร้างขึ้นได้อย่างไร

ตอบ: ในโค้ดต้นฉบับที่ให้มา ให้แก้ไขตัวแปร "dataDir" เพื่อระบุไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 แทนที่`"YOUR DOCUMENTS DIRECTORY"` พร้อมด้วยเส้นทางไดเร็กทอรีที่แท้จริง

#### ถาม: ฉันจะสร้างเอกสาร PDF ที่มีขนาดและระยะขอบที่กำหนดได้อย่างไร

A: หากต้องการสร้างเอกสาร PDF ที่มีขนาดและระยะขอบที่กำหนด ให้ใช้โค้ดต่อไปนี้:

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

#### ถาม: ฉันจะเพิ่มหัวเรื่องพร้อมรูปแบบการนับหมายเลขลงในเอกสาร PDF ได้อย่างไร

A: หากต้องการเพิ่มหัวเรื่องพร้อมรูปแบบการนับเลขในเอกสาร PDF ให้ใช้ตัวอย่างโค้ดที่ให้มาเพื่อสร้างหัวเรื่องและกำหนดรูปแบบการนับเลขเอง ปรับแต่งคุณสมบัติต่างๆ เช่น ข้อความ รูปแบบการนับเลข หมายเลขเริ่มต้น และลำดับอัตโนมัติตามต้องการ

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่สร้างขึ้นได้อย่างไร

 ก: หากต้องการบันทึกเอกสาร PDF ที่สร้างขึ้น ให้ใช้`Save` วิธีการของ`pdfDoc` วัตถุ:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### ถาม: ฉันจะยืนยันได้อย่างไรว่ารูปแบบการนับเลขได้รับการใช้แล้ว

ก: เปิดไฟล์ PDF ที่สร้างขึ้นเพื่อตรวจสอบว่ารูปแบบการนับหมายเลขที่ระบุได้รับการใช้กับหัวเรื่องแล้ว

#### ถาม: ฉันสามารถปรับแต่งรูปแบบการนับหมายเลขเพิ่มเติมได้หรือไม่

 A: ใช่ คุณสามารถปรับแต่งรูปแบบการนับเพิ่มเติมได้โดยการปรับคุณสมบัติของ`Heading` วัตถุ เช่น ประเภทรูปแบบการนับ หมายเลขเริ่มต้น และลำดับอัตโนมัติ

#### ถาม: ฉันสามารถใช้รูปแบบการกำหนดหมายเลขที่แตกต่างกันกับส่วนต่างๆ ของเอกสารได้หรือไม่

 A: ใช่ คุณสามารถใช้รูปแบบการกำหนดหมายเลขที่แตกต่างกันกับส่วนต่างๆ ของเอกสารได้โดยการสร้างหลายๆ`Heading` วัตถุที่มีรูปแบบและลำดับที่แตกต่างกัน