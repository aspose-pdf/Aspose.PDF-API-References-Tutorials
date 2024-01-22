---
title: จัดเรียงเนื้อหาใหม่โดยใช้การแทนที่ข้อความ
linktitle: จัดเรียงเนื้อหาใหม่โดยใช้การแทนที่ข้อความ
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีจัดเรียงเนื้อหาใหม่ในเอกสาร PDF โดยใช้การแทนที่ข้อความด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 270
url: /th/net/programming-with-text/rearrange-contents-using-text-replacement/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการจัดเรียงเนื้อหาใหม่ในเอกสาร PDF โดยใช้การแทนที่ข้อความด้วยไลบรารี Aspose.PDF สำหรับ .NET เราจะดำเนินการตามกระบวนการทีละขั้นตอนในการโหลด PDF ค้นหาส่วนของข้อความที่ต้องการ แทนที่ข้อความ และบันทึก PDF ที่แก้ไขแล้วโดยใช้ซอร์สโค้ด C# ที่ให้มา

## ความต้องการ

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร

 ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีที่มีไฟล์ PDF ของคุณอยู่ แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรพร้อมเส้นทางไปยังไฟล์ PDF ของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดไฟล์ PDF ต้นฉบับ

 ต่อไปเราจะโหลดเอกสาร PDF ต้นฉบับโดยใช้ไฟล์`Document` คลาสจากไลบรารี Aspose.PDF

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## ขั้นตอนที่ 3: ค้นหาและแทนที่ส่วนของข้อความ

 เราสร้างก`TextFragmentAbsorber` วัตถุที่มีนิพจน์ทั่วไปเพื่อค้นหาส่วนของข้อความเฉพาะ จากนั้น เราวนซ้ำส่วนต่างๆ ของข้อความ ปรับแต่งแบบอักษร ขนาด สี และแทนที่ข้อความ

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

สุดท้าย เราจะบันทึกเอกสาร PDF ที่แก้ไขแล้วลงในไฟล์เอาต์พุตที่ระบุ

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับการจัดเรียงเนื้อหาใหม่โดยใช้การแทนที่ข้อความโดยใช้ Aspose.PDF สำหรับ .NET 
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
	// แทนที่ TextFragment แต่ละรายการ
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// ตั้งค่าแบบอักษรของส่วนข้อความที่ถูกแทนที่ด้วย
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// กำหนดขนาดตัวอักษร
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// แทนที่ข้อความด้วยสตริงที่ใหญ่กว่าตัวยึดตำแหน่ง
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// บันทึก PDF ผลลัพธ์
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx");
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีจัดเรียงเนื้อหาใหม่ในเอกสาร PDF โดยใช้การแทนที่ข้อความด้วยไลบรารี Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและดำเนินการโค้ด C# ที่ให้มา คุณสามารถค้นหาส่วนของข้อความที่ต้องการ ปรับแต่งลักษณะที่ปรากฏ และแทนที่ข้อความในเอกสาร PDF ได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "จัดเรียงเนื้อหาใหม่โดยใช้การแทนที่ข้อความ" คืออะไร

ตอบ: บทช่วยสอน "จัดเรียงเนื้อหาใหม่โดยใช้การแทนที่ข้อความ" สาธิตวิธีการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อจัดเรียงเนื้อหาใหม่ในเอกสาร PDF โดยดำเนินการแทนที่ข้อความ บทช่วยสอนนี้จะให้คำแนะนำทีละขั้นตอนและซอร์สโค้ด C# เพื่อช่วยคุณโหลด PDF ค้นหาส่วนของข้อความที่ต้องการ แทนที่ข้อความ และบันทึก PDF ที่แก้ไขแล้ว

#### ถาม: เหตุใดฉันจึงต้องจัดเรียงเนื้อหาในเอกสาร PDF ใหม่

ตอบ: การจัดเรียงเนื้อหาใหม่ในเอกสาร PDF อาจมีประโยชน์สำหรับวัตถุประสงค์ต่างๆ เช่น การอัปเดตข้อความ การจัดรูปแบบเค้าโครงใหม่ หรือการแก้ไข เทคนิคนี้ช่วยให้คุณสามารถแก้ไขเนื้อหาของ PDF แบบไดนามิกในขณะที่ยังคงรักษาโครงสร้างและรูปลักษณ์ไว้

#### ถาม: ฉันจะตั้งค่าไดเร็กทอรีเอกสารได้อย่างไร

ตอบ: หากต้องการตั้งค่าไดเร็กทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรพร้อมเส้นทางไปยังไดเร็กทอรีที่มีไฟล์ PDF ของคุณอยู่

#### ถาม: ฉันจะทำการแทนที่ข้อความในเอกสาร PDF ได้อย่างไร

 ตอบ: บทช่วยสอนจะแนะนำคุณตลอดกระบวนการค้นหาส่วนของข้อความที่ต้องการใน PDF โดยใช้`TextFragmentAbsorber`ระดับ. โดยสาธิตวิธีปรับแต่งลักษณะที่ปรากฏของส่วนข้อความและแทนที่เนื้อหา

#### ถาม: ฉันสามารถปรับแต่งแบบอักษร ขนาด และสีของข้อความที่ถูกแทนที่ได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งแบบอักษร ขนาด และสีของข้อความที่ถูกแทนที่ได้โดยการปรับเปลี่ยน`TextState` คุณสมบัติของ`TextFragment` วัตถุ. บทช่วยสอนนี้จะแสดงตัวอย่างวิธีการตั้งค่าแบบอักษร ขนาดแบบอักษร และสีพื้นหน้าของข้อความ

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่แก้ไขแล้วได้อย่างไร

 ตอบ: หลังจากดำเนินการแทนที่ข้อความและปรับแต่งส่วนของข้อความแล้ว คุณสามารถบันทึกเอกสาร PDF ที่แก้ไขแล้วได้โดยใช้`Save` วิธีการของ`Document` ระดับ. ระบุเส้นทางไฟล์เอาต์พุตที่ต้องการเป็นอาร์กิวเมนต์ของ`Save` วิธี.

#### ถาม: ผลลัพธ์ที่คาดหวังจากบทช่วยสอนนี้คืออะไร

ตอบ: เมื่อปฏิบัติตามบทช่วยสอนและดำเนินการโค้ด C# ที่ให้มา คุณจะสร้างเอกสาร PDF ที่ได้รับการแก้ไข โดยมีการแทนที่และปรับแต่งส่วนของข้อความเฉพาะตามข้อกำหนดเฉพาะของคุณ

#### ถาม: ฉันสามารถใช้นิพจน์ทั่วไปอื่นในการค้นหาข้อความได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้นิพจน์ทั่วไปที่แตกต่างกันเพื่อค้นหาส่วนของข้อความที่ต้องการในเอกสาร PDF ตัวอย่างที่ให้ไว้ในบทช่วยสอนสาธิตวิธีการสร้าง`TextFragmentAbsorber`วัตถุที่มีนิพจน์ทั่วไปเฉพาะเพื่อค้นหาและแทนที่ข้อความ

#### ถาม: จำเป็นต้องมี Aspose License ที่ถูกต้องสำหรับบทช่วยสอนนี้หรือไม่

ตอบ: ใช่ จำเป็นต้องมี Aspose License ที่ถูกต้องเพื่อให้บทช่วยสอนนี้ทำงานได้อย่างถูกต้อง คุณสามารถซื้อใบอนุญาตแบบเต็มหรือรับใบอนุญาตชั่วคราว 30 วันได้จากเว็บไซต์ Aspose