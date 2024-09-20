---
title: ค้นหาและรับหน้าข้อความในไฟล์ PDF
linktitle: ค้นหาและรับหน้าข้อความในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีค้นหาและรับข้อความจากหน้าเฉพาะในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 430
url: /th/net/programming-with-text/search-and-get-text-page/
---
## การแนะนำ

คุณเคยพบว่าตัวเองจำเป็นต้องค้นหาข้อความเฉพาะภายในเอกสาร PDF และแยกข้อความนั้นออกมาเพื่อใช้ในภายหลังหรือไม่ บางทีคุณอาจกำลังสร้างแอปที่ประมวลผลเอกสารและต้องการการแยกข้อมูลที่แม่นยำ หรือบางทีคุณอาจต้องการเพียงแค่แยก PDF อย่างมีประสิทธิภาพ ไม่ว่ากรณีของคุณจะเป็นอย่างไร คุณมาถูกที่แล้ว! ในบทช่วยสอนนี้ เราจะเจาะลึกถึงวิธีค้นหาและรับข้อความจากหน้าในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ไม่ว่าคุณจะเป็นมือใหม่หรือผู้พัฒนาที่มีประสบการณ์ คู่มือนี้จะแนะนำคุณในแต่ละขั้นตอนในลักษณะที่เป็นกันเองและน่าสนใจ พร้อมเริ่มหรือยัง มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มเขียนโค้ด เรามาตรวจสอบกันก่อนว่าคุณมีทุกสิ่งที่คุณต้องการ:

1.  Aspose.PDF สำหรับไลบรารี .NET: คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/pdf/net/) หรือรับเวอร์ชันทดลองใช้งานฟรีจากลิงก์เดียวกัน สำหรับการสั่งซื้อ ให้ไปที่[ร้านอาสโพเซ่](https://purchase.aspose.com/buy).
2. .NET Framework: คุณจะต้องมีสภาพแวดล้อมการพัฒนา .NET ที่ใช้งานได้ เช่น Visual Studio
3. ไฟล์ PDF: คุณจะต้องมีไฟล์ PDF ตัวอย่างที่เราสามารถค้นหาและแยกข้อความได้ สำหรับบทช่วยสอนนี้ สมมติว่าไฟล์นี้มีชื่อว่า`SearchAndGetTextPage.pdf`.

## แพ็คเกจนำเข้า

สิ่งแรกที่ต้องทำคือนำเข้าเนมสเปซที่จำเป็นสำหรับการใช้งาน Aspose.PDF สำหรับ .NET ตรวจสอบให้แน่ใจว่ามีการรวมเนมสเปซเหล่านี้ไว้ที่ด้านบนของโค้ดของคุณ

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System
```

ตอนนี้เราได้ครอบคลุมข้อกำหนดเบื้องต้นแล้ว เรามาแบ่งโค้ดออกเป็นขั้นตอนต่างๆ กันทีละขั้นตอน แต่ละขั้นตอนได้รับการระบุไว้อย่างชัดเจนเพื่อให้ปฏิบัติตามได้ง่าย

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ

ก่อนที่จะโต้ตอบกับ PDF ของคุณ คุณจะต้องกำหนดเส้นทางที่จะเก็บเอกสาร PDF ของคุณ ซึ่งจะทำให้โปรแกรมสามารถเข้าถึงไฟล์ได้

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: นี่คือเส้นทางไปยังโฟลเดอร์ที่จัดเก็บไฟล์ PDF ของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงที่มีไฟล์ PDF ตั้งอยู่

## ขั้นตอนที่ 2: โหลดเอกสาร PDF

ขั้นตอนต่อไปคือการโหลดเอกสาร PDF ลงในหน่วยความจำเพื่อให้คุณสามารถทำงานกับเอกสารได้ ดังต่อไปนี้:

```csharp
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

- เอกสาร: นี่คือคลาส Aspose.PDF ที่โหลดไฟล์ PDF
- pdfDocument: ตัวแปรที่ใช้เก็บไฟล์ PDF หลังจากโหลดแล้ว

## ขั้นตอนที่ 3: สร้างวัตถุ Text Absorber

 การ`TextFragmentAbsorber`คลาสนี้ช่วยให้คุณค้นหาข้อความเฉพาะภายใน PDF ได้ มาสร้างอินสแตนซ์ของคลาสนี้เพื่อค้นหาอินสแตนซ์ทั้งหมดของวลีการค้นหาที่กำหนดกัน

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

- TextFragmentAbsorber: คลาสนี้รับผิดชอบการค้นหาและแยกข้อความจาก PDF
- "รูปภาพ": แทนที่ด้วยข้อความใดๆ ที่คุณต้องการค้นหาภายใน PDF

## ขั้นตอนที่ 4: ใช้ Text Absorber กับ PDF ทั้งหมด

เมื่อตั้งค่าตัวดูดซับข้อความแล้ว คุณต้องบอกโปรแกรมให้ค้นหาในทุกหน้าของ PDF

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- Accept() : วิธีนี้จะใช้ตัวดูดซับข้อความกับ PDF โดยสแกนทุกหน้าเพื่อค้นหาข้อความที่คุณระบุ

## ขั้นตอนที่ 5: ดึงข้อมูลและทำซ้ำผ่านข้อความที่แยกออกมา

ตอนนี้เราได้สแกน PDF เรียบร้อยแล้ว ถึงเวลาที่จะดึงผลลัพธ์ออกมาและแสดงผลลัพธ์ เราจะวนซ้ำผ่านส่วนข้อความที่แยกออกมา

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- TextFragmentCollection: คอลเลกชันนี้เก็บอินสแตนซ์ทั้งหมดของชิ้นส่วนข้อความที่พบโดยตัวดูดซับข้อความ

## ขั้นตอนที่ 6: วนซ้ำแต่ละส่วนและแยกข้อมูล

ตอนนี้เราจะวนผ่าน`textFragmentCollection` และแยกคุณสมบัติต่างๆ ของข้อความแต่ละส่วนออกมา เช่น ตำแหน่ง รายละเอียดแบบอักษร และสี

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

- TextFragment: แต่ละชิ้นส่วนประกอบด้วยข้อความบางส่วนที่พบ
- TextSegment: แต่ละส่วนสามารถมีได้หลายส่วน ซึ่งแสดงถึงส่วนต่างๆ ของข้อความ
- TextState: ให้ข้อมูลโดยละเอียดเกี่ยวกับแบบอักษร ขนาด และสีของข้อความ

ในลูปนี้ เราจะพิมพ์รายละเอียดต่างๆ เช่น ข้อความจริง ตำแหน่ง (พิกัด X และ Y) แบบอักษร แบบอักษรถูกฝังอยู่ใน PDF หรือไม่ และสีพื้นหน้าของข้อความ

## บทสรุป

และแล้วคุณก็พบมัน! ตอนนี้คุณได้ค้นหาและแยกข้อความจากไฟล์ PDF สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET เป็นเรื่องเหลือเชื่อที่คุณมีความยืดหยุ่นมากเพียงใดด้วยไลบรารีนี้ ไม่ว่าคุณจะต้องค้นหาข้อความเฉพาะในเอกสารขนาดใหญ่ แยกข้อความ หรือวิเคราะห์คุณสมบัติของข้อความ Aspose.PDF ก็ทำให้ทุกอย่างง่ายดาย นอกจากนี้ ด้วยโค้ดที่เราครอบคลุม คุณก็พร้อมที่จะปรับให้เหมาะกับความต้องการของคุณ 

## คำถามที่พบบ่อย

### ฉันสามารถค้นหาหลายวลีในครั้งเดียวได้ไหม  
 ใช่ คุณสามารถแก้ไขโค้ดเพื่อค้นหาหลายวลีได้โดยการสร้างหลาย ๆ วลี`TextFragmentAbsorber` วัตถุ

### ฉันจะดึงข้อความจากหน้าใดหน้าหนึ่งได้อย่างไร?  
 คุณสามารถกำหนดเป้าหมายหน้าเฉพาะได้โดยการใช้`TextFragmentAbsorber` ให้เป็นหน้าเดียวแทนที่จะเป็นทั้งเอกสาร ตัวอย่างเช่น:`pdfDocument.Pages[1].Accept(textFragmentAbsorber);`.

### Aspose.PDF สำหรับ .NET ฟรีหรือไม่?  
 Aspose.PDF เป็นผลิตภัณฑ์เชิงพาณิชย์ แต่คุณสามารถใช้ร่วมกับ[ทดลองใช้งานฟรี](https://releases.aspose.com/).

### ฉันสามารถดึงภาพจาก PDF โดยใช้ Aspose.PDF ได้หรือไม่  
 ใช่ Aspose.PDF ช่วยให้คุณแยกรูปภาพได้นอกเหนือจากข้อความ ตรวจสอบ[เอกสารประกอบ](https://reference.aspose.com/pdf/net/) สำหรับรายละเอียดเพิ่มเติม

### จะเกิดอะไรขึ้นหากฉันต้องการความช่วยเหลือหรือการสนับสนุนเพิ่มเติม?  
 คุณสามารถขอความช่วยเหลือจากเราได้เสมอ[ฟอรั่มสนับสนุน Aspose](https://forum.aspose.com/c/pdf/10).