---
title: การแยกเส้นขอบออกจากไฟล์ PDF
linktitle: การแยกเส้นขอบออกจากไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการแยกเส้นขอบจากไฟล์ PDF และบันทึกเป็นรูปภาพโดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดและเคล็ดลับเพื่อความสำเร็จ
type: docs
weight: 80
url: /th/net/programming-with-tables/extract-border/
---
## การแนะนำ

เมื่อทำงานกับ PDF การแยกองค์ประกอบเฉพาะ เช่น ขอบหรือเส้นทางกราฟิกอาจดูเป็นงานที่น่าปวดหัว แต่ด้วย Aspose.PDF สำหรับ .NET คุณสามารถแยกขอบหรือรูปร่างจากไฟล์ PDF และบันทึกเป็นรูปภาพได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการแยกขอบจาก PDF และบันทึกเป็นรูปภาพ PNG เตรียมพร้อมที่จะควบคุมเนื้อหากราฟิกใน PDF ของคุณ!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด โปรดตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าทุกอย่างเรียบร้อยแล้ว:

1.  Aspose.PDF สำหรับ .NET: หากคุณยังไม่ได้ติดตั้งไลบรารี Aspose.PDF คุณสามารถ[ดาวน์โหลดได้ที่นี่](https://releases.aspose.com/pdf/net/)คุณจะต้องสมัครใบอนุญาตด้วย ไม่ว่าจะเป็นแบบทดลองใช้งานฟรีหรือใบอนุญาตที่ซื้อมา
2. การตั้งค่า IDE: ตั้งค่าโปรเจ็กต์ C# ใน Visual Studio หรือ IDE .NET อื่นๆ ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มการอ้างอิงที่จำเป็นลงในไลบรารี Aspose.PDF แล้ว
3. อินพุตไฟล์ PDF: เตรียมไฟล์ PDF ที่คุณจะแยกเส้นขอบออกมา บทช่วยสอนนี้จะอ้างอิงไฟล์ชื่อ`input.pdf`.

## การนำเข้าแพ็คเกจที่จำเป็น

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็น แพ็คเกจเหล่านี้มีเครื่องมือที่จำเป็นในการจัดการเนื้อหา PDF

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

ตอนนี้เราได้ครอบคลุมพื้นฐานแล้ว มาดูคำแนะนำทีละขั้นตอนกันซึ่งเราจะแบ่งแต่ละส่วนของโค้ดออกเป็นรายละเอียดเพื่ออธิบาย


## ขั้นตอนที่ 1: การโหลดเอกสาร PDF

ขั้นตอนแรกคือโหลดเอกสาร PDF ที่มีเส้นขอบที่คุณต้องการแยกออกมา ลองนึกภาพว่าเหมือนกับการเปิดหนังสือก่อนเริ่มอ่าน — คุณต้องเข้าถึงเนื้อหาได้!

 เราจะเริ่มต้นด้วยการระบุไดเรกทอรีที่จัดเก็บไฟล์ PDF ของคุณและโหลดเอกสารโดยใช้`Aspose.Pdf.Document` ระดับ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 โค้ดนี้โหลด`input.pdf` ไฟล์จากไดเร็กทอรีที่คุณระบุ ตรวจสอบให้แน่ใจว่าเส้นทางของไฟล์ถูกต้อง มิฉะนั้น คุณอาจได้รับข้อผิดพลาดไม่พบไฟล์

## ขั้นตอนที่ 2: การตั้งค่ากราฟิกและบิตแมป

ก่อนที่เราจะเริ่มแยกข้อมูล เราต้องสร้างผืนผ้าใบสำหรับวาดภาพเสียก่อน ในโลกของ .NET เราต้องตั้งค่าวัตถุบิตแมปและกราฟิกก่อน บิตแมปแสดงถึงรูปภาพ และวัตถุกราฟิกจะช่วยให้เราสามารถวาดรูปร่าง เช่น ขอบ ที่แยกออกมาจาก PDF ได้

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

นี่คือรายละเอียด:
- เราสร้างภาพบิตแมปที่มีขนาดเท่ากับหน้าแรกของ PDF
- GraphicsPath ใช้เพื่อกำหนดรูปร่าง (ในกรณีนี้คือเส้นขอบ)
- เมทริกซ์จะกำหนดว่ากราฟิกจะถูกแปลงอย่างไร เราจำเป็นต้องมีเมทริกซ์การผกผัน เนื่องจาก PDF และ .NET มีระบบพิกัดที่แตกต่างกัน

## ขั้นตอนที่ 3: การประมวลผลเนื้อหา PDF


ไฟล์ PDF เป็นชุดคำสั่งการวาดภาพ และเราจำเป็นต้องประมวลผลคำสั่งแต่ละคำสั่งเหล่านี้เพื่อระบุและแยกข้อมูลเส้นขอบ

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // การประมวลผลคำสั่งต่างๆ เช่น การบันทึก/เรียกคืนสถานะ การวาดเส้น การเติมรูปทรง ฯลฯ
}
```

โค้ดจะวนซ้ำผ่านตัวดำเนินการวาดภาพทุกตัวในสตรีมเนื้อหาของ PDF ตัวดำเนินการแต่ละตัวอาจแสดงเส้น สี่เหลี่ยมผืนผ้า หรือคำสั่งกราฟิกอื่นๆ

## ขั้นตอนที่ 4: การจัดการผู้ดำเนินการ PDF

ตัวดำเนินการแต่ละตัวในไฟล์ PDF จะควบคุมการดำเนินการต่างๆ หากต้องการแยกเส้นขอบ เราต้องระบุคำสั่งต่างๆ เช่น "ย้ายไปที่" "เส้นไป" และ "วาดสี่เหลี่ยม" ตัวดำเนินการต่อไปนี้จะจัดการการดำเนินการเหล่านี้:

- ย้ายไปที่: ย้ายเคอร์เซอร์ไปยังจุดเริ่มต้น
- LineTo: วาดเส้นจากจุดปัจจุบันไปยังจุดใหม่
- Re: วาดรูปสี่เหลี่ยมผืนผ้า (อาจเป็นส่วนหนึ่งของเส้นขอบ)

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

ในขั้นตอนนี้:
- เราจับจุดของแต่ละเส้นหรือแต่ละรูปร่างที่วาด
- สำหรับรูปสี่เหลี่ยมผืนผ้า (`opRe` ) เราเพิ่มมันโดยตรงไปที่`graphicsPath`ที่เราจะใช้วาดเส้นขอบในภายหลัง

## ขั้นตอนที่ 5: การวาดเส้นขอบ

เมื่อเราระบุเส้นและสี่เหลี่ยมที่สร้างเส้นขอบได้แล้ว เราก็ต้องวาดเส้นและสี่เหลี่ยมเหล่านี้ลงบนวัตถุบิตแมป นี่คือจุดที่วัตถุกราฟิกเข้ามามีบทบาท

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- เราสร้างวัตถุกราฟิกโดยอิงจากบิตแมป
- SmoothingMode.HighQuality ช่วยให้มั่นใจว่าเราได้ภาพที่เรียบเนียนสวยงาม
- สุดท้ายเราใช้ DrawPath เพื่อวาดเส้นขอบ

## ขั้นตอนที่ 6: บันทึกเส้นขอบที่แยกออกมา

ตอนนี้เราได้แยกเส้นขอบออกมาแล้ว ถึงเวลาที่จะบันทึกเป็นไฟล์รูปภาพ ซึ่งจะบันทึกเส้นขอบเป็นไฟล์ PNG

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- บิตแมปจะถูกบันทึกเป็นภาพ PNG
- ตอนนี้คุณสามารถเปิดภาพนี้เพื่อดูเส้นขอบที่แยกออกมาได้

## บทสรุป

การแยกเส้นขอบออกจากไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET อาจดูยุ่งยากในตอนแรก แต่เมื่อคุณแยกออกแล้ว ทุกอย่างก็จะง่ายขึ้น ด้วยการทำความเข้าใจตัวดำเนินการวาดภาพใน PDF และใช้ไลบรารี .NET ที่มีประสิทธิภาพ คุณจะสามารถจัดการและแยกเนื้อหากราฟิกได้อย่างมีประสิทธิภาพ คู่มือนี้จะช่วยให้คุณมีพื้นฐานที่มั่นคงเพื่อเริ่มต้นใช้งานการจัดการ PDF!

## คำถามที่พบบ่อย

### ฉันจะจัดการหลายหน้าใน PDF ได้อย่างไร  
 คุณสามารถวนซ้ำผ่านแต่ละหน้าในเอกสารได้โดยการวนซ้ำ`doc.Pages` แทนการเขียนโค้ดแบบฮาร์ดโค้ด`doc.Pages[1]`.

### ฉันสามารถแยกองค์ประกอบอื่น เช่น ข้อความ โดยใช้แนวทางเดียวกันได้หรือไม่  
ใช่ Aspose.PDF มี API ที่หลากหลายสำหรับแยกข้อความ รูปภาพ และเนื้อหาอื่นๆ จากไฟล์ PDF

### ฉันจะสมัครใบอนุญาตเพื่อหลีกเลี่ยงข้อจำกัดได้อย่างไร  
 คุณสามารถทำได้[ยื่นขอใบอนุญาต](https://purchase.aspose.com/temporary-license/) โดยการโหลดมันผ่าน`License` ชั้นเรียนที่จัดให้โดย Aspose

### จะเกิดอะไรขึ้นหาก PDF ของฉันไม่มีขอบ?  
หาก PDF ของคุณไม่มีเส้นขอบที่มองเห็นได้ กระบวนการแยกกราฟิกอาจไม่ให้ผลลัพธ์ใดๆ ตรวจสอบให้แน่ใจว่าเนื้อหา PDF มีเส้นขอบที่วาดได้

### ฉันสามารถบันทึกผลลัพธ์เป็นรูปแบบอื่นนอกเหนือจาก PNG ได้หรือไม่  
 ใช่ เพียงแค่เปลี่ยน`ImageFormat.Png` เป็นรูปแบบอื่นที่รองรับ เช่น`ImageFormat.Jpeg`.