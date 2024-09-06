---
title: จัดเรียงเนื้อหาใหม่โดยใช้การแทนที่ข้อความ
linktitle: จัดเรียงเนื้อหาใหม่โดยใช้การแทนที่ข้อความ
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีจัดเรียงเนื้อหาในเอกสาร PDF โดยใช้การแทนที่ข้อความด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 270
url: /th/net/programming-with-text/rearrange-contents-using-text-replacement/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการจัดเรียงเนื้อหาในเอกสาร PDF ใหม่โดยใช้การแทนที่ข้อความด้วยไลบรารี Aspose.PDF สำหรับ .NET เราจะอธิบายกระบวนการทีละขั้นตอนในการโหลด PDF ค้นหาส่วนข้อความเฉพาะ แทนที่ข้อความ และบันทึก PDF ที่แก้ไขแล้วโดยใช้โค้ดต้นฉบับ C# ที่ให้มา

## ความต้องการ

ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

 ขั้นแรก คุณต้องตั้งค่าเส้นทางไปยังไดเร็กทอรีที่ไฟล์ PDF ของคุณตั้งอยู่ แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไฟล์ PDF ของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลด PDF ต้นฉบับ

 ต่อไปเราโหลดเอกสาร PDF ต้นฉบับโดยใช้`Document` คลาสจากไลบรารี Aspose.PDF

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## ขั้นตอนที่ 3: ค้นหาและแทนที่ข้อความบางส่วน

 เราสร้าง`TextFragmentAbsorber` วัตถุที่มีนิพจน์ทั่วไปเพื่อค้นหาข้อความบางส่วนที่เจาะจง จากนั้นเราจะดำเนินการซ้ำผ่านข้อความบางส่วน ปรับแต่งแบบอักษร ขนาด สี และแทนที่ข้อความ

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
doc.Pages.Accept(textFragmentAbsorber);

foreach(TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial");
     textFragment.TextState.FontSize = 12;
     textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
     textFragment.Text = "This is a Larger String for the Testing of this issue";
}
```

## ขั้นตอนที่ 4: บันทึก PDF ที่แก้ไขแล้ว

ในที่สุด เราบันทึกเอกสาร PDF ที่แก้ไขแล้วไปยังไฟล์เอาท์พุตที่ระบุ

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการจัดเรียงเนื้อหาใหม่โดยใช้การแทนที่ข้อความโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
try
{
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// โหลดไฟล์ PDF ต้นฉบับ
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	// สร้างวัตถุ TextFragment Absorber ด้วยนิพจน์ทั่วไป
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// แทนที่ TextFragment แต่ละอัน
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// ตั้งค่าฟอนต์ของข้อความส่วนที่ถูกแทนที่
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// ตั้งค่าขนาดตัวอักษร
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// แทนที่ข้อความด้วยสตริงที่มีขนาดใหญ่กว่าตัวแทน
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// บันทึกผลลัพธ์ PDF
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx");
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการจัดเรียงเนื้อหาในเอกสาร PDF ใหม่โดยใช้การแทนที่ข้อความด้วยไลบรารี Aspose.PDF สำหรับ .NET โดยปฏิบัติตามคำแนะนำทีละขั้นตอนและดำเนินการตามโค้ด C# ที่ให้มา คุณสามารถค้นหาส่วนข้อความที่ต้องการ ปรับแต่งลักษณะที่ปรากฏ และแทนที่ข้อความในเอกสาร PDF ได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "จัดเรียงเนื้อหาใหม่โดยใช้การแทนที่ข้อความ" คืออะไร

A: บทช่วยสอน "จัดเรียงเนื้อหาใหม่โดยใช้การแทนที่ข้อความ" สาธิตวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อจัดเรียงเนื้อหาในเอกสาร PDF ใหม่โดยการแทนที่ข้อความ บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนและโค้ดต้นฉบับ C# เพื่อช่วยคุณโหลด PDF ค้นหาส่วนข้อความเฉพาะ แทนที่ข้อความ และบันทึก PDF ที่แก้ไขแล้ว

#### ถาม: เหตุใดฉันจึงต้องจัดเรียงเนื้อหาในเอกสาร PDF ใหม่

A: การจัดเรียงเนื้อหาในเอกสาร PDF ใหม่สามารถเป็นประโยชน์ได้หลายประการ เช่น การอัปเดตข้อความ การจัดรูปแบบเค้าโครงใหม่ หรือการแก้ไข เทคนิคนี้ช่วยให้คุณปรับเปลี่ยนเนื้อหา PDF ได้อย่างไดนามิกในขณะที่ยังคงโครงสร้างและรูปลักษณ์ของเอกสารไว้

#### ถาม: ฉันจะตั้งค่าไดเรกทอรีเอกสารได้อย่างไร?

ก: การตั้งค่าไดเรกทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไดเร็กทอรีที่ไฟล์ PDF ของคุณอยู่

#### ถาม: ฉันจะดำเนินการแทนที่ข้อความในเอกสาร PDF ได้อย่างไร

 A: บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการค้นหาข้อความบางส่วนที่เจาะจงใน PDF โดยใช้`TextFragmentAbsorber`คลาสนี้สาธิตวิธีการปรับแต่งลักษณะของส่วนข้อความและแทนที่เนื้อหาของส่วนเหล่านั้น

#### ถาม: ฉันสามารถปรับแต่งแบบอักษร ขนาดและสีของข้อความที่ถูกแทนที่ได้หรือไม่

 A: ใช่ คุณสามารถปรับแต่งแบบอักษร ขนาด และสีของข้อความที่แทนที่ได้โดยการแก้ไข`TextState` คุณสมบัติของ`TextFragment` วัตถุ บทช่วยสอนนี้มีตัวอย่างวิธีการตั้งค่าแบบอักษร ขนาดแบบอักษร และสีพื้นหน้าของข้อความ

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่แก้ไขแล้วได้อย่างไร

 A: หลังจากทำการแทนที่ข้อความและปรับแต่งส่วนข้อความแล้ว คุณสามารถบันทึกเอกสาร PDF ที่แก้ไขแล้วโดยใช้`Save` วิธีการของ`Document` คลาส ระบุเส้นทางไฟล์เอาท์พุตที่ต้องการเป็นอาร์กิวเมนต์ของ`Save` วิธี.

#### ถาม: ผลลัพธ์ที่คาดหวังจากบทช่วยสอนนี้คืออะไร?

A: โดยทำตามบทช่วยสอนและรันโค้ด C# ที่ให้มา คุณจะสร้างเอกสาร PDF ที่ปรับเปลี่ยนแล้ว โดยที่ส่วนข้อความบางส่วนได้รับการแทนที่และปรับแต่งตามข้อกำหนดของคุณ

#### ถาม: ฉันสามารถใช้นิพจน์ทั่วไปที่แตกต่างกันเพื่อค้นหาข้อความได้หรือไม่

 A: ใช่ คุณสามารถใช้นิพจน์ทั่วไปที่แตกต่างกันเพื่อค้นหาส่วนข้อความเฉพาะในเอกสาร PDF ตัวอย่างที่ให้ไว้ในบทช่วยสอนนี้สาธิตวิธีการสร้าง`TextFragmentAbsorber`วัตถุที่มีนิพจน์ปกติเฉพาะเพื่อค้นหาและแทนที่ข้อความ

#### ถาม: จำเป็นต้องมีใบอนุญาต Aspose ที่ถูกต้องสำหรับบทช่วยสอนนี้หรือไม่

A: ใช่ ต้องมีใบอนุญาต Aspose ที่ถูกต้องเพื่อให้บทช่วยสอนนี้ทำงานได้อย่างถูกต้อง คุณสามารถซื้อใบอนุญาตเต็มรูปแบบหรือรับใบอนุญาตชั่วคราว 30 วันได้จากเว็บไซต์ Aspose