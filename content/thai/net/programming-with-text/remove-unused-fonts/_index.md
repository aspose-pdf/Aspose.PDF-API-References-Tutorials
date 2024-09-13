---
title: ลบแบบอักษรที่ไม่ได้ใช้งานออกจากไฟล์ PDF
linktitle: ลบแบบอักษรที่ไม่ได้ใช้งานออกจากไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการลบแบบอักษรที่ไม่ได้ใช้งานจากไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 300
url: /th/net/programming-with-text/remove-unused-fonts/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีลบแบบอักษรที่ไม่ได้ใช้งานออกจากไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะอธิบายกระบวนการทีละขั้นตอนในการโหลด PDF ระบุและลบแบบอักษรที่ไม่ได้ใช้งาน และบันทึก PDF ที่อัปเดตโดยใช้โค้ดต้นฉบับ C# ที่ให้มา

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
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## ขั้นตอนที่ 3: ระบุและลบแบบอักษรที่ไม่ได้ใช้

 เราสร้าง`TextFragmentAbsorber` วัตถุที่มี`TextEditOptions` ตั้งค่าพารามิเตอร์เป็น`TextEditOptions.FontReplace.RemoveUnusedFonts` ตัวเลือกนี้ช่วยให้เราสามารถระบุและลบแบบอักษรที่ไม่ได้ใช้ในเอกสาร PDF จากนั้นเราจะดำเนินการซ้ำผ่านแบบอักษรทั้งหมด`TextFragments` และตั้งค่าฟอนต์ให้เป็นฟอนต์ที่ต้องการ

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## ขั้นตอนที่ 4: บันทึก PDF ที่อัปเดต

ในที่สุด เราก็บันทึกเอกสาร PDF ที่อัปเดตไปยังไฟล์เอาท์พุตที่ระบุ

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการลบฟอนต์ที่ไม่ได้ใช้โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
try
{
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// โหลดไฟล์ PDF ต้นฉบับ
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// ทำซ้ำผ่าน TextFragments ทั้งหมด
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// บันทึกเอกสารอัพเดต
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx");
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีลบแบบอักษรที่ไม่ได้ใช้จากเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โดยปฏิบัติตามคำแนะนำทีละขั้นตอนและดำเนินการตามโค้ด C# ที่ให้มา คุณจะสามารถโหลด PDF ระบุและลบแบบอักษรที่ไม่ได้ใช้ และบันทึก PDF ที่อัปเดตแล้วได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "ลบแบบอักษรที่ไม่ได้ใช้ในไฟล์ PDF" คืออะไร

A: บทช่วยสอน "ลบแบบอักษรที่ไม่ได้ใช้ออกจากไฟล์ PDF" อธิบายวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อลบแบบอักษรที่ไม่ได้ใช้ออกจากเอกสาร PDF บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการโหลด PDF ระบุและลบแบบอักษรที่ไม่ได้ใช้ และบันทึก PDF ที่อัปเดต

#### ถาม: เหตุใดฉันจึงต้องการลบแบบอักษรที่ไม่ได้ใช้ออกจากเอกสาร PDF

A: การลบแบบอักษรที่ไม่ได้ใช้จากเอกสาร PDF จะช่วยลดขนาดไฟล์และเพิ่มประสิทธิภาพเอกสารให้มีประสิทธิภาพมากขึ้น ซึ่งมีประโยชน์อย่างยิ่งเมื่อต้องจัดการกับ PDF ที่มีแบบอักษรฝังอยู่ซึ่งไม่ได้ใช้งานจริงในเนื้อหาของเอกสาร

#### ถาม: ฉันจะตั้งค่าไดเรกทอรีเอกสารได้อย่างไร?

ก: การตั้งค่าไดเรกทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไดเร็กทอรีที่ไฟล์ PDF ของคุณอยู่

#### ถาม: ฉันจะลบแบบอักษรที่ไม่ได้ใช้ออกจากเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF ได้อย่างไร

A: บทช่วยสอนจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน:

1.  เปิดเอกสาร PDF โดยใช้`Document` ระดับ.
2.  สร้าง`TextFragmentAbsorber` วัตถุที่มี`TextEditOptions` ตั้งค่าเป็น`FontReplace.RemoveUnusedFonts`.
3. ยอมรับตัวดูดซับเพื่อระบุและลบแบบอักษรที่ไม่ได้ใช้จาก PDF
4.  ทำซ้ำผ่านทั้งหมด`TextFragments` และตั้งค่าฟอนต์ให้เป็นฟอนต์ที่ต้องการ
5. บันทึกเอกสาร PDF ที่ได้รับการอัพเดต

####  ถาม: จุดประสงค์ของการ`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 ก. การ`TextEditOptions.FontReplace.RemoveUnusedFonts` พารามิเตอร์สั่งให้`TextFragmentAbsorber`เพื่อระบุและลบแบบอักษรที่ไม่ได้ใช้จากเอกสาร PDF

#### ถาม: ฉันสามารถแทนที่แบบอักษรที่ไม่ได้ใช้ด้วยแบบอักษรที่ฉันเลือกได้หรือไม่

A: ใช่ คุณสามารถแก้ไขโค้ดเพื่อแทนที่แบบอักษรที่ไม่ได้ใช้ด้วยแบบอักษรที่คุณต้องการ ในโค้ดตัวอย่างที่ให้มา จะใช้แบบอักษร "Arial, Bold" แทน

#### ถาม: ทำอย่างไร`TextFragmentAbsorber` work to remove unused fonts?

 ก. การ`TextFragmentAbsorber` ได้รับการกำหนดค่าด้วย`TextEditOptions.FontReplace.RemoveUnusedFonts` พารามิเตอร์ซึ่งระบุแบบอักษรที่ไม่ได้ใช้ภายในส่วนข้อความของ PDF หลังจากดูดซับแล้ว คุณสามารถวนซ้ำผ่าน`TextFragments` และตั้งค่าแบบอักษรให้เป็นแบบอักษรทดแทนตามต้องการ

#### ถาม: ผลลัพธ์ที่คาดหวังจากการดำเนินการโค้ดที่ให้มาคืออะไร

A: เมื่อทำตามบทช่วยสอนและรันโค้ด C# ที่ให้มา คุณจะลบแบบอักษรที่ไม่ได้ใช้งานออกจากเอกสาร PDF อินพุต และบันทึกเวอร์ชันที่อัปเดตเป็นไฟล์ PDF เอาท์พุต

#### ถาม: ฉันสามารถแก้ไขโค้ดเพื่อลบแบบอักษรเฉพาะจากหน้าหรือพื้นที่เฉพาะได้หรือไม่

A: รหัสที่ให้มาจะเน้นไปที่การลบแบบอักษรที่ไม่ได้ใช้จากเอกสาร PDF ทั้งหมด หากคุณต้องการกำหนดเป้าหมายไปที่หน้าหรือภูมิภาคเฉพาะเพื่อลบแบบอักษร คุณจะต้องปรับเปลี่ยนแนวทางและใช้ตรรกะที่ซับซ้อนมากขึ้นเพื่อระบุแบบอักษรที่ไม่ได้ใช้ในพื้นที่เหล่านั้น