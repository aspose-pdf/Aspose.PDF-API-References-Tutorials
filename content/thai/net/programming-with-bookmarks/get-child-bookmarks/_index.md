---
title: รับบุ๊กมาร์กเด็กในไฟล์ PDF
linktitle: รับบุ๊กมาร์กเด็กในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: รับบุ๊กมาร์กลูกในไฟล์ PDF ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 80
url: /th/net/programming-with-bookmarks/get-child-bookmarks/
---
การดึงบุ๊กมาร์กย่อยในไฟล์ PDF จะมีประโยชน์สำหรับการสำรวจโครงสร้างลำดับชั้นของบุ๊กมาร์ก ด้วย Aspose.PDF สำหรับ .NET คุณสามารถรับบุ๊กมาร์กลูกได้อย่างง่ายดายโดยทำตามซอร์สโค้ดต่อไปนี้:

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ก่อนที่คุณจะเริ่มต้น คุณต้องนำเข้าไลบรารีที่จำเป็นสำหรับโปรเจ็กต์ C# ของคุณ นี่คือคำสั่งการนำเข้าที่จำเป็น:

```csharp
using Aspose.Pdf;
```

## ขั้นตอนที่ 2: กำหนดเส้นทางไปยังโฟลเดอร์เอกสาร

 ในขั้นตอนนี้ คุณจะต้องระบุเส้นทางไปยังโฟลเดอร์ที่มีไฟล์ PDF ที่คุณต้องการแยกบุ๊กมาร์ก แทนที่`"YOUR DOCUMENT DIRECTORY"`ในรหัสต่อไปนี้พร้อมเส้นทางจริงไปยังโฟลเดอร์เอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 3: เปิดเอกสาร PDF

ตอนนี้เรากำลังจะเปิดเอกสาร PDF ที่เราต้องการแยกบุ๊กมาร์กโดยใช้รหัสต่อไปนี้:

```csharp
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

## ขั้นตอนที่ 4: เรียกดูบุ๊กมาร์กและบุ๊กมาร์กย่อย

 ในขั้นตอนนี้ เราจะวนซ้ำบุ๊กมาร์กทั้งหมดในเอกสารโดยใช้ a`foreach` วนซ้ำ สำหรับแต่ละบุ๊กมาร์ก เราจะแสดงข้อมูล เช่น ชื่อ รูปแบบตัวเอียง รูปแบบตัวหนา และสี หากบุ๊กมาร์กมีบุ๊กมาร์กย่อย เราจะแสดงบุ๊กมาร์กเหล่านั้นด้วย นี่คือรหัสที่เกี่ยวข้อง:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
    
     if (outlineItem.Count > 0)
     {
         Console.WriteLine("Child bookmarks");
        
         // เรียกดูบุ๊กมาร์กเด็กด้วย
         foreach(OutlineItemCollection childOutline in outlineItem)
         {
             Console.WriteLine(childOutline.Title);
             Console.WriteLine(childOutline.Italic);
             Console.WriteLine(childOutline.Bold);
             Console.WriteLine(childOutline.Color);
         }
     }
}
```

### ตัวอย่างซอร์สโค้ดสำหรับรับบุ๊กมาร์กลูกโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
// วนซ้ำบุ๊กมาร์กทั้งหมด
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
	if (outlineItem.Count > 0)
	{
		Console.WriteLine("Child Bookmarks");
		// มีบุ๊กมาร์กเด็กแล้ววนซ้ำเช่นกัน
		foreach (OutlineItemCollection childOutline in outlineItem)
		{
			Console.WriteLine(childOutline.Title);
			Console.WriteLine(childOutline.Italic);
			Console.WriteLine(childOutline.Bold);
			Console.WriteLine(childOutline.Color);
		}
	}
}
```

## บทสรุป

ขอแสดงความยินดี! ตอนนี้ คุณมีคำแนะนำทีละขั้นตอนในการรับบุ๊กมาร์กลูกด้วย Aspose.PDF สำหรับ .NET คุณสามารถใช้โค้ดนี้เพื่อสำรวจโครงสร้างลำดับชั้นของบุ๊กมาร์ก และรับข้อมูลโดยละเอียดเกี่ยวกับบุ๊กมาร์กแต่ละรายการและบุ๊กมาร์กย่อยในเอกสาร PDF ของคุณ

อย่าลืมตรวจสอบเอกสารอย่างเป็นทางการของ Aspose.PDF สำหรับข้อมูลเพิ่มเติมเกี่ยวกับคุณสมบัติการจัดการบุ๊กมาร์กขั้นสูง

### คำถามที่พบบ่อยสำหรับการรับบุ๊กมาร์กลูกในรูปแบบไฟล์ PDF

#### ถาม: บุ๊กมาร์กลูกในไฟล์ PDF คืออะไร

ตอบ: บุ๊กมาร์กย่อยคือบุ๊กมาร์กที่ซ้อนกันอยู่ใต้บุ๊กมาร์กหลัก สร้างโครงสร้างแบบลำดับชั้น ช่วยให้มีประสบการณ์การนำทางที่เป็นระเบียบและมีรายละเอียดมากขึ้นภายในเอกสาร PDF

#### ถาม: เหตุใดฉันจึงต้องดึงบุ๊กมาร์กลูกจากไฟล์ PDF

ตอบ: การเรียกบุ๊กมาร์กย่อยช่วยให้คุณเข้าใจความสัมพันธ์และลำดับชั้นระหว่างส่วนต่างๆ ของเอกสาร ข้อมูลนี้สามารถเป็นประโยชน์อย่างยิ่งสำหรับเอกสารที่มีโครงสร้างที่ซับซ้อนหรือองค์กรหลายระดับ

#### ถาม: ฉันจะนำเข้าไลบรารีที่จำเป็นสำหรับโปรเจ็กต์ C# ของฉันได้อย่างไร

ตอบ: หากต้องการนำเข้าไลบรารีที่จำเป็นสำหรับโครงการ C# ของคุณ ให้ใช้คำสั่งการนำเข้าต่อไปนี้:

```csharp
using Aspose.Pdf;
```

คำสั่งนี้ช่วยให้คุณเข้าถึงคลาสและวิธีการที่มีให้โดย Aspose.PDF สำหรับ .NET

#### ถาม: ฉันจะระบุเส้นทางไปยังโฟลเดอร์เอกสารได้อย่างไร

 ตอบ: ในซอร์สโค้ดที่ให้มา ให้แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังโฟลเดอร์ที่มีไฟล์ PDF ที่คุณต้องการแยกบุ๊กมาร์กย่อย เพื่อให้แน่ใจว่าโค้ดสามารถค้นหาไฟล์ PDF เป้าหมายได้

#### ถาม: ฉันจะเปิดเอกสาร PDF เพื่อแยกบุ๊กมาร์กย่อยได้อย่างไร

ตอบ: หากต้องการเปิดเอกสาร PDF เพื่อแยกบุ๊กมาร์ก ให้ใช้รหัสต่อไปนี้:

```csharp
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

 แทนที่`"GetChildBookmarks.pdf"` ด้วยชื่อไฟล์จริง

#### ถาม: ฉันจะวนซ้ำและแสดงข้อมูลบุ๊กมาร์กย่อยได้อย่างไร

 ตอบ: วนบุ๊กมาร์กทั้งหมดในเอกสารโดยใช้ a`foreach` วนซ้ำ สำหรับบุ๊กมาร์กแต่ละรายการ ให้แสดงข้อมูล เช่น ชื่อ รูปแบบตัวเอียง รูปแบบตัวหนา สี และหากมีบุ๊กมาร์กย่อย ให้ทำซ้ำเช่นกัน:

```csharp
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
    Console.WriteLine("Title: " + outlineItem.Title);
    Console.WriteLine("Italic: " + outlineItem.Italic);
    Console.WriteLine("Bold: " + outlineItem.Bold);
    Console.WriteLine("Color: " + outlineItem.Color);
    
    if (outlineItem.Count > 0)
    {
        Console.WriteLine("Child bookmarks");
        
        // เรียกดูบุ๊กมาร์กเด็กด้วย
        foreach (OutlineItemCollection childOutline in outlineItem)
        {
            Console.WriteLine(childOutline.Title);
            Console.WriteLine(childOutline.Italic);
            Console.WriteLine(childOutline.Bold);
            Console.WriteLine(childOutline.Color);
        }
    }
}
```

#### ถาม: ฉันสามารถแยกคุณสมบัติอื่น ๆ ของบุ๊กมาร์กย่อยโดยใช้วิธีการที่คล้ายกันได้หรือไม่

 ตอบ: ได้ คุณสามารถแยกคุณสมบัติต่างๆ ของบุ๊กมาร์กย่อยได้โดยใช้`OutlineItemCollection` วัตถุ. โปรดดูเอกสารประกอบของ Aspose.PDF สำหรับรายการคุณสมบัติที่มีอยู่อย่างครอบคลุม

#### ถาม: มีการจำกัดจำนวนบุ๊กมาร์กลูกที่ฉันสามารถเรียกดูได้หรือไม่

ตอบ: โดยทั่วไปไม่มีการจำกัดจำนวนบุ๊กมาร์กลูกที่คุณสามารถเรียกดูได้โดยใช้วิธีนี้ อย่างไรก็ตาม เอกสารที่มีขนาดใหญ่มากซึ่งมีบุ๊กมาร์กลูกมากเกินไปอาจต้องมีการจัดการหน่วยความจำที่มีประสิทธิภาพ

#### ถาม: จะเกิดอะไรขึ้นหากบุ๊กมาร์กลูกมีบุ๊กมาร์กลูกซ้อนกันอีก

ตอบ: โค้ดที่ให้มาจะวนซ้ำผ่านบุ๊กมาร์กลูกทุกระดับ ช่วยให้คุณสามารถดึงข้อมูลจากบุ๊กมาร์กลูกที่ซ้อนกันได้เช่นกัน

#### ถาม: ฉันจะใช้ข้อมูลบุ๊กมาร์กย่อยที่แยกออกมาได้อย่างไร

ตอบ: คุณสามารถใช้ข้อมูลบุ๊กมาร์กย่อยที่แยกออกมาเพื่อการวิเคราะห์ เอกสาร หรือสร้างอินเทอร์เฟซการนำทางแบบกำหนดเองภายในแอปพลิเคชันของคุณได้