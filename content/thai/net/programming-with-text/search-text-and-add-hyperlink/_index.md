---
title: ค้นหาข้อความและเพิ่มไฮเปอร์ลิงก์
linktitle: ค้นหาข้อความและเพิ่มไฮเปอร์ลิงก์
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีค้นหาข้อความใน PDF เพิ่มไฮเปอร์ลิงก์ไปยังข้อความที่พบ และบันทึกเอกสารที่แก้ไขโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 450
url: /th/net/programming-with-text/search-text-and-add-hyperlink/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อค้นหาข้อความที่ต้องการในเอกสาร PDF เพิ่มไฮเปอร์ลิงก์ไปยังข้อความที่พบ และบันทึกเอกสารที่แก้ไข ซอร์สโค้ด C# ที่ให้มาสาธิตกระบวนการทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะดำเนินการบทแนะนำต่อ โปรดแน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Aspose.PDF สำหรับไลบรารี .NET แล้ว คุณสามารถรับได้จากเว็บไซต์ Aspose หรือใช้ NuGet เพื่อติดตั้งในโครงการของคุณ

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

เริ่มต้นด้วยการสร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบรวม (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น

เพิ่มคำสั่งต่อไปนี้ที่จุดเริ่มต้นของไฟล์ C# ของคุณเพื่อนำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 3: กำหนดเส้นทางไปยังไดเร็กทอรีเอกสาร

 กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณโดยใช้ไฟล์`dataDir` ตัวแปร:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: สร้าง TextFragmentAbsorber

 สร้างก`TextFragmentAbsorber` วัตถุเพื่อค้นหาทุกกรณีของวลีค้นหาอินพุต:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 แทนที่`"\\d{4}-\\d{4}"` ด้วยรูปแบบนิพจน์ทั่วไปที่คุณต้องการ

## ขั้นตอนที่ 5: เปิดใช้งานการค้นหานิพจน์ทั่วไป

 เปิดใช้งานการค้นหานิพจน์ทั่วไปโดยการตั้งค่า`TextSearchOptions` คุณสมบัติตัวดูดซับ:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## ขั้นตอนที่ 6: เปิดและผูกเอกสาร PDF

 สร้างก`PdfContentEditor` object และผูกเข้ากับไฟล์ PDF ต้นฉบับ:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 แทนที่`"SearchRegularExpressionPage.pdf"` ด้วยชื่อจริงของไฟล์ PDF ของคุณ

## ขั้นตอนที่ 7: ยอมรับตัวดูดซับสำหรับเพจ

ยอมรับตัวดูดซับสำหรับหน้าเอกสารที่ต้องการ:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 แทนที่`1` พร้อมเลขหน้าที่ต้องการ

## ขั้นตอนที่ 8: เพิ่มไฮเปอร์ลิงก์ไปยังข้อความที่พบ

วนซ้ำส่วนข้อความที่ดึงมาและเพิ่มไฮเปอร์ลิงก์:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // สร้างสี่เหลี่ยมผืนผ้าตามตำแหน่งของส่วนของข้อความ
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //เพิ่มลิงค์เว็บให้กับสี่เหลี่ยม
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System. Drawing.Color.Blue);
}
```

 แทนที่`"http://www.aspose.com"` ด้วย URL ไฮเปอร์ลิงก์ที่ต้องการ

## ขั้นตอนที่ 9: บันทึกและปิดเอกสารที่แก้ไข

บันทึกเอกสารที่แก้ไขแล้วปิดเอดิเตอร์:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"SearchTextAndAddHyperlink_out.pdf"` ด้วยชื่อไฟล์เอาต์พุตที่ต้องการ

### ตัวอย่างซอร์สโค้ดสำหรับค้นหาข้อความและเพิ่มไฮเปอร์ลิงก์โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างวัตถุตัวดูดซับเพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีค้นหาอินพุต
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// เปิดใช้งานการค้นหานิพจน์ทั่วไป
absorber.TextSearchOptions = new TextSearchOptions(true);
// เปิดเอกสาร
PdfContentEditor editor = new PdfContentEditor();
// ผูกไฟล์ PDF ต้นฉบับ
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// ยอมรับโช้คหน้า
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

ยินดีด้วย! คุณได้เรียนรู้วิธีการค้นหาข้อความเฉพาะในเอกสาร PDF เพิ่มไฮเปอร์ลิงก์ไปยังข้อความที่พบ และบันทึกเอกสารที่แก้ไขโดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอน ตั้งแต่การตั้งค่าโปรเจ็กต์ไปจนถึงการดำเนินการที่จำเป็น ตอนนี้คุณสามารถรวมโค้ดนี้เข้ากับโปรเจ็กต์ C# ของคุณเองเพื่อจัดการข้อความและเพิ่มไฮเปอร์ลิงก์ในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "ค้นหาข้อความและเพิ่มไฮเปอร์ลิงก์" คืออะไร

ตอบ: บทช่วยสอน "ค้นหาข้อความและเพิ่มไฮเปอร์ลิงก์" มีวัตถุประสงค์เพื่อสาธิตวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อค้นหาข้อความเฉพาะภายในเอกสาร PDF เพิ่มไฮเปอร์ลิงก์ไปยังข้อความที่พบ จากนั้นบันทึกเอกสารที่แก้ไข บทช่วยสอนนี้จะให้คำแนะนำที่ครอบคลุมและตัวอย่างโค้ด C# เพื่ออธิบายกระบวนการทีละขั้นตอน

#### ถาม: บทช่วยสอนนี้ช่วยในการเพิ่มไฮเปอร์ลิงก์ไปยังข้อความเฉพาะในเอกสาร PDF ได้อย่างไร

ตอบ: บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้ไลบรารี Aspose.PDF เพื่อค้นหาข้อความเฉพาะในเอกสาร PDF ใช้ไฮเปอร์ลิงก์กับข้อความที่ระบุ และบันทึก PDF ที่แก้ไขแล้ว โดยครอบคลุมขั้นตอนที่สำคัญ เช่น การตั้งค่าโปรเจ็กต์ การโหลดเอกสาร การเปิดใช้งานการค้นหานิพจน์ทั่วไป และการเพิ่มไฮเปอร์ลิงก์ไปยังข้อความที่พบ

#### ถาม: จำเป็นต้องมีข้อกำหนดเบื้องต้นอะไรบ้างเพื่อปฏิบัติตามบทช่วยสอนนี้

ตอบ: ก่อนที่คุณจะเริ่มต้น คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# นอกจากนี้ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET ซึ่งสามารถรับได้จากเว็บไซต์ Aspose หรือติดตั้งโดยใช้ NuGet ในโปรเจ็กต์ของคุณ

#### ถาม: ฉันจะตั้งค่าโปรเจ็กต์ให้ปฏิบัติตามบทช่วยสอนนี้ได้อย่างไร

ตอบ: เริ่มต้นด้วยการสร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบรวม (IDE) ที่คุณต้องการ จากนั้น เพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET ซึ่งจะช่วยให้คุณสามารถใช้ความสามารถของไลบรารีในโครงการของคุณได้

#### ถาม: ฉันสามารถเพิ่มไฮเปอร์ลิงก์ไปยังข้อความเฉพาะโดยใช้บทช่วยสอนนี้ได้หรือไม่

ตอบ: ใช่ บทช่วยสอนนี้เน้นที่การเพิ่มไฮเปอร์ลิงก์ไปยังข้อความเฉพาะในเอกสาร PDF โดยเฉพาะ โดยสาธิตวิธีการค้นหาและแยกข้อความที่ต้องการโดยใช้นิพจน์ทั่วไป สร้างไฮเปอร์ลิงก์ที่เกี่ยวข้องกับส่วนของข้อความ และบันทึก PDF ที่แก้ไข

#### ถาม: ฉันจะกำหนดข้อความที่ต้องการค้นหาและเพิ่มไฮเปอร์ลิงก์ได้อย่างไร

 ตอบ: หากต้องการระบุข้อความที่คุณต้องการค้นหาและเพิ่มไฮเปอร์ลิงก์ ให้สร้าง`TextFragmentAbsorber` วัตถุและกำหนดรูปแบบโดยใช้`Text` พารามิเตอร์. แทนที่รูปแบบเริ่มต้น`"\\d{4}-\\d{4}"` ในโค้ดของบทช่วยสอนด้วยรูปแบบนิพจน์ทั่วไปที่คุณต้องการ

#### ถาม: ฉันจะเปิดใช้งานการค้นหาข้อความด้วยนิพจน์ทั่วไปได้อย่างไร

 ตอบ: การค้นหานิพจน์ทั่วไปเปิดใช้งานได้โดยการสร้าง`TextSearchOptions` วัตถุและตั้งค่าเป็น`true` . กำหนดวัตถุนี้ให้กับ`TextSearchOptions` ทรัพย์สินของ`TextFragmentAbsorber` ตัวอย่าง. เพื่อให้แน่ใจว่ามีการใช้รูปแบบนิพจน์ทั่วไปในระหว่างการค้นหาข้อความ

#### ถาม: ฉันจะเพิ่มไฮเปอร์ลิงก์ไปยังข้อความที่พบได้อย่างไร

 ตอบ: หลังจากระบุส่วนของข้อความโดยใช้ไฟล์`TextFragmentAbsorber` บทช่วยสอนจะให้การวนซ้ำเพื่อวนซ้ำส่วนต่างๆ เหล่านี้ สำหรับแต่ละส่วนของข้อความ บทช่วยสอนจะสาธิตวิธีตั้งค่าสีข้อความเป็นสีน้ำเงินและสร้างไฮเปอร์ลิงก์โดยใช้`CreateWebLink` วิธี.

#### ถาม: ขั้นตอนในการบันทึก PDF ที่แก้ไขแล้วพร้อมไฮเปอร์ลิงก์มีอะไรบ้าง

 ตอบ: หลังจากเพิ่มไฮเปอร์ลิงก์ไปยังส่วนของข้อความที่ต้องการแล้ว ให้ใช้ไฟล์`PdfContentEditor` คลาสเพื่อบันทึกเอกสารที่ถูกแก้ไข โค้ดตัวอย่างของบทช่วยสอนจะแสดงวิธีการบันทึก PDF ที่แก้ไขแล้ว ปิดตัวแก้ไข และแสดงข้อความแสดงความสำเร็จ