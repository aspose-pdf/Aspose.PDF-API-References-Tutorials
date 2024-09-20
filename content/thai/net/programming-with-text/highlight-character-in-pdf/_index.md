---
title: เน้นตัวอักษรในไฟล์ PDF
linktitle: เน้นตัวอักษรในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้การเน้นอักขระใน PDF โดยใช้ Aspose.PDF สำหรับ .NET ในคู่มือทีละขั้นตอนที่ครอบคลุมนี้
type: docs
weight: 240
url: /th/net/programming-with-text/highlight-character-in-pdf/
---
## การแนะนำ

เมื่อต้องทำงานกับ PDF มักจะต้องเน้นข้อความหรืออักขระ ไม่ว่าจะเพื่อวัตถุประสงค์ทางวิชาการ การแก้ไข หรือเพียงแค่การปรับปรุงการอ่าน ลองนึกภาพว่าคุณมีเอกสารที่สวยงาม แต่คุณต้องการเน้นเฉพาะบางส่วน นั่นคือจุดที่การเน้นมีความสำคัญ! ในบทช่วยสอนนี้ เราจะเจาะลึกถึงวิธีการเน้นอักขระในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET ที่มีประสิทธิภาพ 

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้นเขียนโค้ด เรามาตรวจสอบให้แน่ใจก่อนว่าเรามีทุกอย่างที่จำเป็นแล้ว นี่คือสิ่งที่คุณต้องการ:

1. สภาพแวดล้อมการพัฒนา: บทช่วยสอนนี้ถือว่าคุณกำลังทำงานใน Visual Studio หรือ .NET IDE ที่คล้ายกัน
2.  Aspose.PDF สำหรับไลบรารี .NET: หากคุณยังไม่ได้ทำ คุณสามารถทำได้[ดาวน์โหลดได้ที่นี่](https://releases.aspose.com/pdf/net/) และเพิ่มมันลงในโครงการของคุณ 
3. ความรู้พื้นฐานเกี่ยวกับ C#: คู่มือเบื้องต้นในการเขียนโปรแกรม C# จะช่วยให้คุณเข้าใจการใช้งานได้อย่างง่ายดาย
4. เอกสาร PDF: คุณควรมีไฟล์ PDF ตัวอย่างพร้อมใช้งาน คุณสามารถสร้างไฟล์ขึ้นมาเองหรือใช้เอกสารที่มีอยู่แล้วก็ได้

## การนำเข้าแพ็คเกจ

ในการเริ่มต้น เราจำเป็นต้องนำเข้าเนมสเปซที่จำเป็น เมื่อต้องการทำเช่นนี้ คุณจะต้องรวมเนมสเปซเหล่านี้ไว้ที่ด้านบนของไฟล์ C#:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Devices;
using Aspose.Pdf.Text;
using System;
using System.Drawing;
```

แพ็คเกจเหล่านี้มีความจำเป็นสำหรับการสร้าง การจัดการ และการประมวลผลเอกสาร PDF โดยใช้ไลบรารี Aspose

ตอนนี้ มาแบ่งกระบวนการออกเป็นขั้นตอนย่อยๆ เพื่อเน้นอักขระใน PDF ของคุณ 

## ขั้นตอนที่ 1: เริ่มต้นเอกสาร PDF

ขั้นตอนแรกคือการเริ่มต้นเอกสาร PDF ของคุณ ซึ่งเกี่ยวข้องกับการโหลดไฟล์ PDF ที่คุณจะใช้งาน วิธีดำเนินการมีดังนี้:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // ตรวจสอบให้แน่ใจว่าคุณตั้งค่าเส้นทางที่ถูกต้อง
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```
ในสคริปท์นี้ ให้แทนที่`YOUR DOCUMENT DIRECTORY` ด้วยเส้นทางจริงบนเครื่องของคุณซึ่งไฟล์ PDF ที่คุณป้อนอยู่`Aspose.Pdf.Document` คลาสจะถูกสร้างตัวอย่างเพื่อโหลด PDF ของคุณ

## ขั้นตอนที่ 2: ตั้งค่ากระบวนการเรนเดอร์

ขั้นต่อไป เราต้องเตรียมกระบวนการเรนเดอร์เอกสาร ซึ่งเป็นสิ่งสำคัญสำหรับการเน้นตัวอักษรบนหน้าให้ถูกต้อง

```csharp
int resolution = 150; // ตั้งค่าความละเอียดในการจับภาพ
using (MemoryStream ms = new MemoryStream())
{
    PdfConverter conv = new PdfConverter(pdfDocument);
    conv.Resolution = new Resolution(resolution, resolution);
    conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```
 เรากำหนดความละเอียดเพื่อความชัดเจน ช่วยให้สามารถแสดงข้อความได้อย่างถูกต้อง`PdfConverter`เปลี่ยนหน้า PDF ให้เป็นรูปภาพเพื่อให้เราสามารถวาดบนนั้นได้

## ขั้นตอนที่ 3: สร้างวัตถุกราฟิกสำหรับการวาดภาพ

หลังจากตั้งค่ากระบวนการวาดภาพแล้ว เราต้องสร้างวัตถุภาพกราฟิกซึ่งเราจะใช้ในการเน้นข้อความ:

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
    float scale = resolution / 72f; // ปัจจัยมาตราส่วน
    gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
```
ที่นี่เราสร้างวัตถุกราฟิกจากภาพบิตแมป การแปลงจะช่วยปรับการเรนเดอร์ให้ตรงกับความละเอียดที่ต้องการได้อย่างถูกต้อง

## ขั้นตอนที่ 4: วนซ้ำในแต่ละหน้าและเน้นข้อความ

ตอนนี้ เรามาวนซ้ำผ่านแต่ละหน้าใน PDF และค้นหาส่วนของข้อความที่เราต้องการเน้น:

```csharp
for (int i = 0; i < pdfDocument.Pages.Count; i++)
{
    Page page = pdfDocument.Pages[i + 1]; // หน้ามีดัชนี 1 ใน Aspose
    TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
    textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
    page.Accept(textFragmentAbsorber);
```
 เราเข้าถึงแต่ละหน้าและค้นหาข้อความทั้งหมดโดยใช้`TextFragmentAbsorber` รูปแบบนิพจน์ปกติ`@"[\S]+"` จับอักขระที่ไม่ใช่ช่องว่างทั้งหมด

## ขั้นตอนที่ 5: แยกส่วนข้อความและเน้นข้อความ

ตอนนี้ถึงเวลาแยกข้อความบางส่วนและเน้นข้อความเหล่านั้น ขั้นตอนนี้เกี่ยวข้องกับการวาดรูปสี่เหลี่ยมผืนผ้ารอบตัวอักษรที่เราต้องการเน้น:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

foreach (TextFragment textFragment in textFragmentCollection)
{
    // เน้นตรรกะที่นี่
    for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
    {
        TextSegment segment = textFragment.Segments[segNum];
        for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
        {
            CharInfo characterInfo = segment.Characters[charNum];
            gr.DrawRectangle(Pens.Black, 
                (float)characterInfo.Rectangle.LLX, 
                (float)characterInfo.Rectangle.LLY, 
                (float)characterInfo.Rectangle.Width, 
                (float)characterInfo.Rectangle.Height);
        }
    }
}
```
เราวนซ้ำผ่านแต่ละส่วนของข้อความ ส่วนของข้อความ และอักขระแต่ละตัว โดยวาดรูปสี่เหลี่ยมผืนผ้ารอบๆ ข้อความโดยใช้กราฟิกวัตถุที่สร้างไว้ก่อนหน้านี้

## ขั้นตอนที่ 6: บันทึกภาพที่แก้ไขแล้ว

หลังจากไฮไลต์แล้ว คุณจะต้องบันทึกรูปภาพที่ได้เป็นไฟล์ PNG ใหม่:

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```
บรรทัดนี้จะบันทึกภาพบิตแมปที่คุณแก้ไขเป็นไฟล์ PNG ในไดเร็กทอรีที่กำหนด 

## ขั้นตอนที่ 7: สรุปด้วยการจัดการข้อยกเว้น

สุดท้ายนี้ การห่อโค้ดของคุณในบล็อก try-catch ถือเป็นแนวทางปฏิบัติที่ดี เพื่อให้แน่ใจว่าเราจะจัดการกับข้อผิดพลาดที่ไม่คาดคิดได้อย่างเหมาะสม:

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get a 30-day temporary license from [here](https://buy.aspose.com/temporary-license/)");
}
```

บล็อคนี้จะจับข้อยกเว้นใดๆ ที่อาจเกิดขึ้นในระหว่างกระบวนการ และให้ข้อมูลตอบกลับแก่ผู้ใช้

## บทสรุป

และแล้วคุณก็ทำได้! คุณได้เน้นตัวอักษรในไฟล์ PDF สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ไลบรารีอันทรงพลังนี้เปิดประตูสู่ความเป็นไปได้ที่ไม่มีที่สิ้นสุดในการจัดการ PDF ไม่ว่าคุณจะทำงานกับคำอธิบายประกอบ การกรอกแบบฟอร์ม หรือแม้แต่การแปลงเอกสาร เมื่อคุณดำเนินการกับ Aspose ต่อไป โปรดจำไว้ว่าการฝึกฝนเป็นสิ่งสำคัญ ทดลองใช้ฟีเจอร์ต่างๆ อย่างต่อเนื่อง แล้วคุณจะกลายเป็นผู้เชี่ยวชาญด้าน PDF อย่างรวดเร็ว!

## คำถามที่พบบ่อย

### Aspose.PDF สำหรับ .NET คืออะไร?
Aspose.PDF สำหรับ .NET เป็นไลบรารีที่ช่วยให้สามารถสร้าง จัดการ และแปลงเอกสาร PDF ได้ด้วยโปรแกรมในแอปพลิเคชัน .NET

### ฉันสามารถเน้นข้อความหลายส่วนพร้อมกันได้ไหม
ใช่ โค้ดที่ให้มาสามารถปรับใช้เพื่อเน้นส่วนต่างๆ ได้หลายส่วนโดยการวนซ้ำผ่านข้อความทั้งหมดภายใน PDF

### มี Aspose.PDF เวอร์ชันฟรีหรือไม่
ใช่ Aspose เสนอการทดลองใช้ฟรี ดังนั้นคุณจึงสามารถทดสอบไลบรารีได้ก่อนการซื้อ

### ฉันต้องมีใบอนุญาตเพื่อใช้ Aspose.PDF หรือไม่
ใช่ ต้องมีใบอนุญาตที่ถูกต้องสำหรับการใช้งานเชิงพาณิชย์ แต่คุณสามารถขอใบอนุญาตชั่วคราว 30 วันเพื่อการทดสอบได้

### ฉันสามารถหาเอกสารเพิ่มเติมได้ที่ไหน
 คุณสามารถอ้างอิงได้จาก[เอกสาร Aspose.PDF](https://reference.aspose.com/pdf/net/) เพื่อดูข้อมูลโดยละเอียดเพิ่มเติมเกี่ยวกับการใช้งานและคุณสมบัติ