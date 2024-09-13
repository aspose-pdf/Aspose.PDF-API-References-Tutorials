---
title: นำรูปแบบตัวเลขมาใช้ในไฟล์ PDF
linktitle: นำรูปแบบตัวเลขมาใช้ในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการใช้รูปแบบตัวเลขต่างๆ (เลขโรมัน ตัวอักษร) กับหัวเรื่องใน PDF โดยใช้ Aspose.PDF สำหรับ .NET ด้วยคู่มือทีละขั้นตอนนี้
type: docs
weight: 10
url: /th/net/programming-with-headings/apply-number-style/
---
## การแนะนำ

คุณเคยพบว่าคุณจำเป็นต้องเพิ่มรายการที่มีหมายเลขกำกับไว้อย่างสวยงามในเอกสาร PDF ของคุณหรือไม่ ไม่ว่าคุณจะจัดรูปแบบเอกสารทางกฎหมาย รายงาน หรือการนำเสนอ รูปแบบหมายเลขกำกับที่ถูกต้องถือเป็นสิ่งสำคัญสำหรับการจัดระเบียบข้อมูล ด้วย Aspose.PDF สำหรับ .NET คุณสามารถใช้รูปแบบหมายเลขกำกับต่างๆ กับหัวข้อของไฟล์ PDF เพื่อสร้างเอกสารที่มีโครงสร้างที่ดีและเป็นมืออาชีพ 

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเริ่มเขียนโค้ด มาดูสิ่งที่คุณต้องการกันก่อน:

1. Aspose.PDF สำหรับ .NET: ดาวน์โหลด Aspose.PDF เวอร์ชันล่าสุดจาก[ที่นี่](https://releases.aspose.com/pdf/net/).
2. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณมี Visual Studio หรือ IDE อื่น ๆ ที่เข้ากันได้กับ .NET
3. .NET Framework: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework 4.0 ขึ้นไป
4.  ใบอนุญาต: คุณสามารถใช้ใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/) หรือสำรวจ[ทดลองใช้งานฟรี](https://releases.aspose.com/) ตัวเลือก

## แพ็คเกจนำเข้า

ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้นำเนมสเปซต่อไปนี้เข้าสู่โปรเจ็กต์ของคุณแล้ว:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 1: การตั้งค่าเอกสาร

เริ่มต้นด้วยการสร้างเอกสาร PDF ใหม่และกำหนดค่าการตั้งค่าหน้ากระดาษ เราจะกำหนดขนาดหน้ากระดาษและระยะขอบเพื่อควบคุมเค้าโครงของเนื้อหา

คำอธิบาย: ในขั้นตอนนี้ เราจะกำหนดโครงสร้างพื้นฐานของ PDF ซึ่งรวมถึงการกำหนดขนาดหน้า ความสูง และระยะขอบสำหรับการจัดรูปแบบที่สอดคล้องกัน

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// ตั้งค่าขนาดหน้าและระยะขอบ
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

การดำเนินการนี้ จะทำให้เอกสารของคุณมีขนาดหน้ามาตรฐานเทียบเท่ากับหน้ากระดาษขนาด 8.5 x 11 นิ้ว และมีระยะขอบ 72 จุด (หรือ 1 นิ้ว) ทุกด้าน

## ขั้นตอนที่ 2: เพิ่มหน้าลงใน PDF

ต่อไปเราจะเพิ่มหน้าใหม่ลงในเอกสาร PDF ซึ่งเราจะนำรูปแบบการกำหนดหมายเลขมาใช้ในภายหลัง

คำอธิบาย: PDF ทุกฉบับต้องมีหน้า! ขั้นตอนนี้จะเพิ่มหน้าว่างใน PDF และกำหนดระยะขอบให้ตรงกับการตั้งค่าระดับเอกสาร

```csharp
// เพิ่มหน้าใหม่ลงในเอกสาร PDF
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
```

## ขั้นตอนที่ 3: สร้างกล่องลอย

FloatingBox ช่วยให้คุณวางเนื้อหา (เช่น ข้อความหรือหัวเรื่อง) ไว้ในกล่องที่มีลักษณะการทำงานเป็นอิสระจากการไหลของหน้า ซึ่งมีประโยชน์เมื่อคุณต้องการควบคุมเค้าโครงของเนื้อหาทั้งหมด

คำอธิบาย: ที่นี่ เรากำลังตั้งค่า FloatingBox เพื่อบรรจุหัวเรื่องที่จะมีการนำรูปแบบตัวเลขไปใช้

```csharp
// สร้าง FloatingBox สำหรับเนื้อหาที่มีโครงสร้าง
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

## ขั้นตอนที่ 4: เพิ่มหัวข้อแรกด้วยตัวเลขโรมัน

ตอนนี้มาถึงส่วนที่น่าตื่นเต้นแล้ว มาเพิ่มหัวข้อแรกด้วยการใช้ตัวเลขโรมันตัวเล็กกัน

คำอธิบาย: เรากำลังนำรูปแบบ NumberingStyle.NumeralsRomanLowercase มาใช้กับหัวเรื่อง ซึ่งจะแสดงการนับเลขเป็นเลขโรมัน (i, ii, iii เป็นต้น)

```csharp
// สร้างหัวข้อแรกด้วยตัวเลขโรมัน
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
```

## ขั้นตอนที่ 5: เพิ่มหัวข้อตัวเลขโรมันตัวที่สอง

เพื่อจุดประสงค์ในการสาธิต เราจะเพิ่มหัวข้อตัวเลขโรมันตัวที่สอง แต่คราวนี้เราจะเริ่มที่ 13

คำอธิบาย: คุณสมบัติ StartNumber ช่วยให้คุณเริ่มต้นการนับเลขจากตัวเลขที่กำหนดเอง ในกรณีนี้ เราจะเริ่มจาก 13

```csharp
// สร้างหัวข้อที่สองโดยเริ่มจากเลขโรมัน 13
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
```

## ขั้นตอนที่ 6: เพิ่มหัวข้อพร้อมการเรียงลำดับตามตัวอักษร

เพื่อความหลากหลาย เราจะเพิ่มหัวข้อที่สาม แต่คราวนี้เราจะใช้การนับตัวอักษรแบบตัวพิมพ์เล็ก (a, b, c เป็นต้น)

คำอธิบาย: การเปลี่ยน NumberingStyle ให้เป็น LettersLowercase ช่วยให้เราสามารถใช้การนับเลขตัวอักษรกับหัวเรื่องของเราได้

```csharp
// สร้างหัวข้อด้วยการนับเลขตามตัวอักษร
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

## ขั้นตอนที่ 7: บันทึก PDF

สุดท้ายหลังจากใช้หัวเรื่องและรูปแบบตัวเลขทั้งหมดแล้ว มาบันทึกไฟล์ PDF ไปยังไดเร็กทอรีที่คุณต้องการ

คำอธิบาย: ขั้นตอนนี้จะบันทึกไฟล์ PDF ที่มีหัวเรื่องที่ได้รับการจัดรูปแบบพร้อมทั้งใช้รูปแบบการนับหมายเลขแล้ว

```csharp
// บันทึกเอกสาร PDF
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);
```

## บทสรุป

และแล้วคุณก็จะมีมัน! คุณได้นำรูปแบบการนับเลข—ตัวเลขโรมันและตัวอักษร—ไปใช้กับหัวเรื่องในไฟล์ PDF ได้สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ความยืดหยุ่นที่ Aspose.PDF มอบให้สำหรับการควบคุมเค้าโครงหน้า รูปแบบการนับเลข และการจัดวางเนื้อหา ช่วยให้คุณมีชุดเครื่องมืออันทรงพลังในการสร้างเอกสาร PDF ที่จัดระบบอย่างดีและเป็นมืออาชีพ

## คำถามที่พบบ่อย

### ฉันสามารถใช้รูปแบบตัวเลขที่แตกต่างกันกับเอกสาร PDF เดียวกันได้หรือไม่  
ใช่ Aspose.PDF สำหรับ .NET ช่วยให้คุณผสมผสานรูปแบบการนับเลขที่แตกต่างกัน เช่น เลขโรมัน เลขอาหรับ และการนับเลขตามตัวอักษรภายในเอกสารเดียวกันได้

### ฉันจะปรับแต่งหมายเลขเริ่มต้นสำหรับหัวเรื่องได้อย่างไร  
 คุณสามารถตั้งค่าหมายเลขเริ่มต้นสำหรับหัวข้อใดๆ ได้โดยใช้`StartNumber` คุณสมบัติ.

### มีวิธีรีเซ็ตลำดับการนับเลขหรือไม่  
ใช่ คุณสามารถรีเซ็ตการนับเลขได้โดยการปรับ`StartNumber` คุณสมบัติของแต่ละหัวข้อ

### ฉันสามารถใช้รูปแบบตัวหนาหรือตัวเอียงกับหัวเรื่องนอกเหนือจากการกำหนดหมายเลขได้หรือไม่  
 แน่นอน! คุณสามารถปรับแต่งรูปแบบหัวเรื่องได้โดยการแก้ไขคุณสมบัติ เช่น แบบอักษร ขนาด ตัวหนา และตัวเอียง โดยใช้`TextState` วัตถุ.

### ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ Aspose.PDF ได้อย่างไร  
 คุณสามารถขอใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อทดสอบ Aspose.PDF โดยไม่มีข้อจำกัด