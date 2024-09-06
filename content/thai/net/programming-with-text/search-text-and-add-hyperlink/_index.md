---
title: ค้นหาข้อความและเพิ่มไฮเปอร์ลิงก์
linktitle: ค้นหาข้อความและเพิ่มไฮเปอร์ลิงก์
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีค้นหาข้อความใน PDF เพิ่มไฮเปอร์ลิงก์ลงในข้อความที่พบ และบันทึกเอกสารที่แก้ไขโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 450
url: /th/net/programming-with-text/search-text-and-add-hyperlink/
---
บทช่วยสอนนี้จะอธิบายวิธีการใช้ Aspose.PDF สำหรับ .NET เพื่อค้นหาข้อความเฉพาะในเอกสาร PDF เพิ่มไฮเปอร์ลิงก์ไปยังข้อความที่พบ และบันทึกเอกสารที่แก้ไขแล้ว โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนต่างๆ ของกระบวนการทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะดำเนินการตามบทช่วยสอน โปรดแน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose หรือใช้ NuGet เพื่อติดตั้งในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

เริ่มต้นด้วยการสร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น

เพิ่มคำสั่ง using ต่อไปนี้ที่จุดเริ่มต้นของไฟล์ C# ของคุณเพื่อนำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าเส้นทางไปยังไดเรกทอรีเอกสาร

 ตั้งค่าเส้นทางไปยังไดเรกทอรีเอกสารของคุณโดยใช้`dataDir` ตัวแปร:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: สร้าง TextFragmentAbsorber

 สร้าง`TextFragmentAbsorber` วัตถุที่จะค้นหาอินสแตนซ์ทั้งหมดของวลีการค้นหาอินพุต:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 แทนที่`"\\d{4}-\\d{4}"` ด้วยรูปแบบนิพจน์ปกติของคุณตามที่ต้องการ

## ขั้นตอนที่ 5: เปิดใช้งานการค้นหาด้วยนิพจน์ปกติ

 เปิดใช้งานการค้นหานิพจน์ปกติโดยตั้งค่า`TextSearchOptions` คุณสมบัติของตัวดูดซับ:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## ขั้นตอนที่ 6: เปิดและผูกเอกสาร PDF

 สร้าง`PdfContentEditor` วัตถุและผูกเข้ากับไฟล์ PDF ต้นฉบับ:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 แทนที่`"SearchRegularExpressionPage.pdf"` ด้วยชื่อจริงของไฟล์ PDF ของคุณ

## ขั้นตอนที่ 7: ยอมรับตัวดูดซับสำหรับหน้า

ยอมรับตัวดูดซับสำหรับหน้าที่ต้องการของเอกสาร:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 แทนที่`1` พร้อมหมายเลขหน้าที่ต้องการ

## ขั้นตอนที่ 8: เพิ่มไฮเปอร์ลิงก์ลงในข้อความที่พบ

วนซ้ำผ่านชิ้นส่วนข้อความที่เรียกค้นและเพิ่มไฮเปอร์ลิงก์ให้กับมัน:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // สร้างสี่เหลี่ยมผืนผ้าโดยอิงตามตำแหน่งของชิ้นส่วนข้อความ
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //เพิ่มลิงค์เว็บลงในสี่เหลี่ยมผืนผ้า
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System. Drawing.Color.Blue);
}
```

 แทนที่`"http://www.aspose.com"` ด้วย URL ไฮเปอร์ลิงก์ที่ต้องการ

## ขั้นตอนที่ 9: บันทึกและปิดเอกสารที่แก้ไข

บันทึกเอกสารที่แก้ไขแล้วและปิดตัวแก้ไข:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 อย่าลืมเปลี่ยน`"SearchTextAndAddHyperlink_out.pdf"` พร้อมชื่อไฟล์เอาท์พุตตามที่ต้องการ

### ตัวอย่างโค้ดต้นฉบับสำหรับการค้นหาข้อความและเพิ่มไฮเปอร์ลิงก์โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างวัตถุตัวดูดซับเพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีการค้นหาอินพุต
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// เปิดใช้งานการค้นหาด้วยนิพจน์ปกติ
absorber.TextSearchOptions = new TextSearchOptions(true);
// เปิดเอกสาร
PdfContentEditor editor = new PdfContentEditor();
// เชื่อมโยงไฟล์ PDF ต้นฉบับ
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// รับตัวดูดซับสำหรับหน้า
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// วนผ่านชิ้นส่วน
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, สีน้ำเงิน, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีค้นหาข้อความเฉพาะในเอกสาร PDF เพิ่มไฮเปอร์ลิงก์ในข้อความที่พบ และบันทึกเอกสารที่แก้ไขโดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนตั้งแต่การตั้งค่าโครงการไปจนถึงการดำเนินการที่จำเป็น ตอนนี้คุณสามารถนำโค้ดนี้ไปใช้กับโครงการ C# ของคุณเองเพื่อจัดการข้อความและเพิ่มไฮเปอร์ลิงก์ในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "ค้นหาข้อความและเพิ่มไฮเปอร์ลิงก์" คืออะไร

A: บทช่วยสอน "ค้นหาข้อความและเพิ่มไฮเปอร์ลิงก์" มีวัตถุประสงค์เพื่อสาธิตวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อค้นหาข้อความเฉพาะภายในเอกสาร PDF เพิ่มไฮเปอร์ลิงก์ไปยังข้อความที่พบ จากนั้นบันทึกเอกสารที่แก้ไข บทช่วยสอนนี้ให้คำแนะนำที่ครอบคลุมและตัวอย่างโค้ด C# เพื่อแสดงขั้นตอนทีละขั้นตอน

#### ถาม: บทช่วยสอนนี้ช่วยในการเพิ่มไฮเปอร์ลิงก์ไปยังข้อความเฉพาะในเอกสาร PDF ได้อย่างไร

A: บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการใช้ไลบรารี Aspose.PDF เพื่อค้นหาข้อความเฉพาะในเอกสาร PDF ใส่ไฮเปอร์ลิงก์ให้กับข้อความที่ระบุ และบันทึก PDF ที่แก้ไขแล้ว บทช่วยสอนนี้ครอบคลุมขั้นตอนสำคัญต่างๆ เช่น การตั้งค่าโครงการ การโหลดเอกสาร การเปิดใช้งานการค้นหาด้วยนิพจน์ทั่วไป และการเพิ่มไฮเปอร์ลิงก์ให้กับข้อความที่พบ

#### ถาม: ต้องมีข้อกำหนดเบื้องต้นอะไรบ้างในการปฏิบัติตามบทช่วยสอนนี้?

A: ก่อนที่คุณจะเริ่มต้น คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# นอกจากนี้ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET ซึ่งสามารถหาได้จากเว็บไซต์ Aspose หรือติดตั้งโดยใช้ NuGet ในโปรเจ็กต์ของคุณ

#### ถาม: ฉันจะตั้งค่าโครงการเพื่อทำตามบทช่วยสอนนี้ได้อย่างไร

A: เริ่มต้นด้วยการสร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่คุณต้องการ จากนั้นเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET ซึ่งจะทำให้คุณสามารถใช้ความสามารถของไลบรารีในโปรเจ็กต์ของคุณได้

#### ถาม: ฉันสามารถเพิ่มไฮเปอร์ลิงก์ไปยังข้อความเฉพาะโดยใช้บทช่วยสอนนี้ได้หรือไม่

A: ใช่ บทช่วยสอนนี้มุ่งเน้นที่การเพิ่มไฮเปอร์ลิงก์ไปยังข้อความเฉพาะในเอกสาร PDF โดยเฉพาะ โดยจะสาธิตวิธีการค้นหาและแยกข้อความที่ต้องการโดยใช้นิพจน์ทั่วไป การสร้างไฮเปอร์ลิงก์ที่เชื่อมโยงกับส่วนข้อความ และการบันทึก PDF ที่แก้ไขแล้ว

#### ถาม: ฉันจะกำหนดข้อความที่ฉันต้องการค้นหาและเพิ่มไฮเปอร์ลิงก์ได้อย่างไร

 ก: เพื่อระบุข้อความที่คุณต้องการค้นหาและเพิ่มไฮเปอร์ลิงก์ ให้สร้าง`TextFragmentAbsorber` วัตถุและกำหนดรูปแบบโดยใช้`Text` พารามิเตอร์ แทนที่รูปแบบเริ่มต้น`"\\d{4}-\\d{4}"` ในโค้ดของบทช่วยสอนพร้อมรูปแบบนิพจน์ปกติที่คุณต้องการ

#### ถาม: ฉันจะเปิดใช้งานการค้นหานิพจน์ปกติสำหรับข้อความได้อย่างไร

 A: การค้นหาด้วยนิพจน์ปกติจะเปิดใช้งานได้โดยการสร้าง`TextSearchOptions` วัตถุและการตั้งค่าเป็น`true` . กำหนดวัตถุนี้ให้กับ`TextSearchOptions` ทรัพย์สินของ`TextFragmentAbsorber` อินสแตนซ์ การดำเนินการนี้จะช่วยให้แน่ใจว่ารูปแบบนิพจน์ทั่วไปจะถูกใช้ในระหว่างการค้นหาข้อความ

#### ถาม: ฉันจะเพิ่มไฮเปอร์ลิงก์ลงในข้อความที่พบได้อย่างไร

 ก: หลังจากระบุชิ้นส่วนข้อความโดยใช้`TextFragmentAbsorber` บทช่วยสอนนี้ให้ลูปเพื่อวนซ้ำผ่านส่วนต่างๆ เหล่านี้ สำหรับส่วนข้อความแต่ละส่วน บทช่วยสอนนี้จะสาธิตวิธีตั้งค่าสีข้อความเป็นสีน้ำเงินและสร้างไฮเปอร์ลิงก์โดยใช้`CreateWebLink` วิธี.

#### ถาม: ขั้นตอนการบันทึก PDF ที่แก้ไขแล้วด้วยไฮเปอร์ลิงก์มีอะไรบ้าง

 ก: หลังจากเพิ่มไฮเปอร์ลิงก์ลงในส่วนข้อความที่ต้องการแล้ว ให้ใช้`PdfContentEditor` คลาสสำหรับบันทึกเอกสารที่แก้ไขแล้ว โค้ดตัวอย่างของบทช่วยสอนนี้จะแสดงวิธีการบันทึก PDF ที่แก้ไขแล้ว ปิดตัวแก้ไข และแสดงข้อความแจ้งว่าสำเร็จ