---
title: ลบแบบอักษรที่ไม่ได้ใช้ออกจากไฟล์ PDF
linktitle: ลบแบบอักษรที่ไม่ได้ใช้ออกจากไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีลบแบบอักษรที่ไม่ได้ใช้ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 300
url: /th/net/programming-with-text/remove-unused-fonts/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีลบฟอนต์ที่ไม่ได้ใช้ในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะดำเนินการตามกระบวนการทีละขั้นตอนในการโหลด PDF ระบุและลบแบบอักษรที่ไม่ได้ใช้ และบันทึก PDF ที่อัปเดตโดยใช้ซอร์สโค้ด C# ที่ให้มา

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
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## ขั้นตอนที่ 3: ระบุและลบแบบอักษรที่ไม่ได้ใช้

 เราสร้างก`TextFragmentAbsorber` คัดค้านด้วย`TextEditOptions` ตั้งค่าพารามิเตอร์เป็น`TextEditOptions.FontReplace.RemoveUnusedFonts` . ตัวเลือกนี้ช่วยให้เราสามารถระบุและลบแบบอักษรที่ไม่ได้ใช้ในเอกสาร PDF จากนั้นเราก็วนซ้ำทั้งหมด`TextFragments` และกำหนดฟอนต์ให้เป็นฟอนต์ที่ต้องการ

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## ขั้นตอนที่ 4: บันทึก PDF ที่อัปเดต

สุดท้าย เราจะบันทึกเอกสาร PDF ที่อัปเดตไปยังไฟล์เอาท์พุตที่ระบุ

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับการลบแบบอักษรที่ไม่ได้ใช้โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
try
{
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// โหลดไฟล์ PDF ต้นฉบับ
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// วนซ้ำ TextFragments ทั้งหมด
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// บันทึกเอกสารที่อัปเดต
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx");
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีลบแบบอักษรที่ไม่ได้ใช้ออกจากเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและดำเนินการโค้ด C# ที่ให้มา คุณสามารถโหลด PDF ระบุและลบแบบอักษรที่ไม่ได้ใช้ และบันทึก PDF ที่อัปเดตได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "ลบแบบอักษรที่ไม่ได้ใช้ในไฟล์ PDF" คืออะไร

ตอบ: บทช่วยสอน "ลบแบบอักษรที่ไม่ได้ใช้ในไฟล์ PDF" อธิบายวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อลบแบบอักษรที่ไม่ได้ใช้ออกจากเอกสาร PDF บทช่วยสอนจะแนะนำคุณตลอดกระบวนการโหลด PDF การระบุและลบแบบอักษรที่ไม่ได้ใช้ และการบันทึก PDF ที่อัปเดต

#### ถาม: เหตุใดฉันจึงต้องการลบแบบอักษรที่ไม่ได้ใช้ออกจากเอกสาร PDF

ตอบ: การลบแบบอักษรที่ไม่ได้ใช้ออกจากเอกสาร PDF สามารถช่วยลดขนาดไฟล์และปรับเอกสารให้เหมาะสมเพื่อประสิทธิภาพที่ดีขึ้น สิ่งนี้มีประโยชน์อย่างยิ่งเมื่อต้องจัดการกับ PDF ที่มีฟอนต์ฝังตัวซึ่งไม่ได้ใช้จริงในเนื้อหาของเอกสาร

#### ถาม: ฉันจะตั้งค่าไดเร็กทอรีเอกสารได้อย่างไร

ตอบ: หากต้องการตั้งค่าไดเร็กทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรพร้อมเส้นทางไปยังไดเร็กทอรีที่มีไฟล์ PDF ของคุณอยู่

#### ถาม: ฉันจะลบแบบอักษรที่ไม่ได้ใช้ออกจากเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF ได้อย่างไร

ตอบ: บทช่วยสอนจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน:

1.  เปิดเอกสาร PDF โดยใช้ไฟล์`Document` ระดับ.
2.  สร้างก`TextFragmentAbsorber` วัตถุด้วย`TextEditOptions` ตั้งค่าให้`FontReplace.RemoveUnusedFonts`.
3. ยอมรับตัวดูดซับเพื่อระบุและลบแบบอักษรที่ไม่ได้ใช้ออกจาก PDF
4.  ย้ำตลอด`TextFragments` และกำหนดฟอนต์ให้เป็นฟอนต์ที่ต้องการ
5. บันทึกเอกสาร PDF ที่อัปเดต

####  ถาม: จุดประสงค์ของ.`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 ตอบ:`TextEditOptions.FontReplace.RemoveUnusedFonts` พารามิเตอร์สั่งให้`TextFragmentAbsorber` เพื่อระบุและลบแบบอักษรที่ไม่ได้ใช้ออกจากเอกสาร PDF

#### ถาม: ฉันสามารถแทนที่แบบอักษรที่ไม่ได้ใช้ด้วยแบบอักษรที่ฉันเลือกได้หรือไม่

ตอบ: ได้ คุณสามารถแก้ไขโค้ดเพื่อแทนที่ฟอนต์ที่ไม่ได้ใช้ด้วยฟอนต์ที่คุณเลือกได้ ในโค้ดตัวอย่างที่ให้มา จะใช้แบบอักษร "Arial, Bold" แทน

####  ถาม: เป็นยังไงบ้าง`TextFragmentAbsorber` work to remove unused fonts?

 ตอบ:`TextFragmentAbsorber` ได้รับการกำหนดค่าด้วย`TextEditOptions.FontReplace.RemoveUnusedFonts` พารามิเตอร์ซึ่งระบุแบบอักษรที่ไม่ได้ใช้ภายในส่วนข้อความของ PDF หลังจากการดูดซึม คุณสามารถทำซ้ำได้`TextFragments` และตั้งค่าแบบอักษรเป็นแบบอักษรทดแทนที่ต้องการ

#### ถาม: ผลลัพธ์ที่คาดหวังจากการรันโค้ดที่ให้มาคืออะไร?

ตอบ: โดยการปฏิบัติตามบทช่วยสอนและเรียกใช้โค้ด C# ที่ให้มา คุณจะลบแบบอักษรที่ไม่ได้ใช้ออกจากเอกสาร PDF ที่ป้อนเข้า และบันทึกเวอร์ชันที่อัปเดตเป็นไฟล์ PDF เอาต์พุต

#### ถาม: ฉันสามารถแก้ไขโค้ดเพื่อลบแบบอักษรออกจากหน้าหรือพื้นที่เฉพาะได้หรือไม่

ตอบ: โค้ดที่ให้มาเน้นไปที่การลบแบบอักษรที่ไม่ได้ใช้ออกจากเอกสาร PDF ทั้งหมด หากคุณต้องการกำหนดเป้าหมายหน้าหรือภูมิภาคเฉพาะเพื่อลบแบบอักษร คุณจะต้องปรับเปลี่ยนวิธีการและใช้ตรรกะที่ซับซ้อนมากขึ้นเพื่อระบุแบบอักษรที่ไม่ได้ใช้ในพื้นที่เหล่านั้น