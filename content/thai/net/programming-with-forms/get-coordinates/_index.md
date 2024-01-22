---
title: รับพิกัดฟิลด์แบบฟอร์ม PDF
linktitle: รับพิกัดฟิลด์แบบฟอร์ม PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: รับพิกัดฟิลด์แบบฟอร์ม PDF ในเอกสาร PDF ของคุณได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 120
url: /th/net/programming-with-forms/get-coordinates/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีรับพิกัดฟิลด์ของแบบฟอร์ม PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ทีละขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการนี้

## ขั้นตอนที่ 1: การเตรียมการ

ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าไลบรารีที่จำเป็นและกำหนดเส้นทางไปยังไดเร็กทอรีเอกสาร:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: ใส่เอกสารเอาต์พุต

โหลดเอกสาร PDF เอาต์พุต:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## ขั้นตอนที่ 3: ค้นหาช่องที่เพิ่ม

ค้นหาฟิลด์แบบฟอร์มที่เพิ่ม (ในตัวอย่างนี้ เราใช้ฟิลด์ "Item1", "Item2" และ "Item3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## ขั้นตอนที่ 4: แสดงตำแหน่งรายการย่อยสำหรับแต่ละฟิลด์

วนไปตามตัวเลือกสำหรับแต่ละฟิลด์และดูพิกัดสำหรับแต่ละรายการย่อย:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### ตัวอย่างซอร์สโค้ดสำหรับรับพิกัดโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
try
{
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// โหลดเอกสารขาออก
	Document doc1 = new Document( dataDir + "input.pdf");
	// ค้นหาช่องที่เพิ่ม
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// และแสดงตำแหน่งของรายการย่อยแต่ละรายการ
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีรับพิกัดฟิลด์ของแบบฟอร์มโดยใช้ Aspose.PDF สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถดึงข้อมูลพิกัดขององค์ประกอบย่อยของช่องแบบฟอร์มในเอกสาร PDF ของคุณได้อย่างง่ายดายโดยใช้ Aspose.PDF

### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถใช้วิธีนี้เพื่อรับพิกัดสำหรับฟิลด์แบบฟอร์มประเภทใดก็ได้ใน Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ: ได้ คุณสามารถใช้วิธีนี้เพื่อรับพิกัดสำหรับฟิลด์แบบฟอร์มประเภทต่างๆ ใน Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาสาธิตวิธีรับพิกัดสำหรับฟิลด์ RadioButton แต่คุณสามารถปรับแนวทางเดียวกันสำหรับฟิลด์แบบฟอร์มอื่นๆ ได้ เช่น กล่องข้อความ กล่องกาเครื่องหมาย กล่องรายการ และอื่นๆ

#### ถาม: ฉันจะแก้ไขหรือปรับพิกัดฟิลด์แบบฟอร์มได้อย่างไร

ตอบ: พิกัดของฟิลด์แบบฟอร์มจะขึ้นอยู่กับระบบพิกัดของเอกสาร PDF โดยที่จุดเริ่มต้น (0,0) อยู่ที่มุมซ้ายล่างของหน้า หากต้องการแก้ไขหรือปรับพิกัดฟิลด์แบบฟอร์ม คุณสามารถอัปเดตได้`Rect` คุณสมบัติของฟิลด์ฟอร์มที่เกี่ยวข้องหรือรายการย่อย เช่น RadioButtonOptionField

#### ถาม: ฉันจะรับพิกัดของช่องแบบฟอร์มที่เพิ่มลงในเอกสาร PDF โดยทางโปรแกรมได้หรือไม่

ตอบ: ได้ คุณสามารถรับพิกัดของช่องแบบฟอร์มที่เพิ่มลงในเอกสาร PDF โดยทางโปรแกรมได้ Aspose.PDF สำหรับ .NET ช่วยให้คุณสามารถเพิ่มฟิลด์แบบฟอร์มแบบไดนามิก และเมื่อเพิ่มแล้ว คุณสามารถดึงพิกัดของฟิลด์เหล่านั้นได้โดยใช้วิธีการที่แสดงในบทช่วยสอนนี้

#### ถาม: จุดประสงค์ในการดึงข้อมูลพิกัดฟิลด์แบบฟอร์มคืออะไร

ตอบ: การเรียกพิกัดฟิลด์แบบฟอร์มจะมีประโยชน์เมื่อคุณต้องการดำเนินการที่เกี่ยวข้องกับเค้าโครงเฉพาะหรือการตรวจสอบความถูกต้องของฟิลด์ฟอร์มภายในเอกสาร PDF ช่วยให้คุณสามารถวางตำแหน่งและจัดแนวฟิลด์แบบฟอร์มตามพิกัดได้อย่างแม่นยำ ทำให้มั่นใจได้ว่าฟิลด์เหล่านี้จะปรากฏในเอกสารอย่างถูกต้อง และมอบประสบการณ์ผู้ใช้ที่ราบรื่น

#### ถาม: พิกัดฟิลด์แบบฟอร์มแสดงเป็นจุดหรือหน่วยอื่นหรือไม่

ตอบ: พิกัดฟิลด์แบบฟอร์มใน Aspose.PDF สำหรับ .NET จะแสดงเป็นจุด จุดหนึ่งเทียบเท่ากับ 1/72 นิ้ว ทำให้เป็นหน่วยวัดมาตรฐานในรูปแบบ PDF