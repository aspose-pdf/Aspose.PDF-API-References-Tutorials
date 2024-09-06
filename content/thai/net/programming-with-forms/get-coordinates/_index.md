---
title: รับพิกัดฟิลด์ฟอร์ม PDF
linktitle: รับพิกัดฟิลด์ฟอร์ม PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: รับพิกัดฟิลด์ฟอร์ม PDF ในเอกสาร PDF ของคุณได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 120
url: /th/net/programming-with-forms/get-coordinates/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีรับพิกัดฟิลด์ฟอร์ม PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายโค้ดต้นฉบับ C# ทีละขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการนี้

## ขั้นตอนที่ 1: การเตรียมพร้อม

ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าไลบรารีที่จำเป็นและตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสาร:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารผลลัพธ์

โหลดเอกสาร PDF เอาท์พุต:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## ขั้นตอนที่ 3: ค้นหาฟิลด์ที่เพิ่มเข้ามา

ค้นหาฟิลด์ฟอร์มที่เพิ่ม (ในตัวอย่างนี้ เราใช้ฟิลด์ "Item1", "Item2" และ "Item3")

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## ขั้นตอนที่ 4: แสดงตำแหน่งรายการย่อยสำหรับแต่ละฟิลด์

หมุนเวียนตัวเลือกสำหรับแต่ละฟิลด์และดูพิกัดสำหรับแต่ละรายการย่อย:

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

### ตัวอย่างโค้ดที่มาสำหรับรับพิกัดโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
try
{
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// โหลดเอกสารเอาท์พุต
	Document doc1 = new Document( dataDir + "input.pdf");
	// ค้นหาฟิลด์เพิ่มเติม
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// และแสดงตำแหน่งของรายการย่อยของแต่ละรายการ
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

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการรับพิกัดของฟิลด์ฟอร์มโดยใช้ Aspose.PDF สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้แล้ว คุณจะสามารถดึงพิกัดขององค์ประกอบย่อยของฟิลด์ฟอร์มในเอกสาร PDF ของคุณได้อย่างง่ายดายโดยใช้ Aspose.PDF

### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถใช้วิธีนี้เพื่อรับพิกัดสำหรับฟิลด์ฟอร์มประเภทใดก็ได้ใน Aspose.PDF สำหรับ .NET ได้หรือไม่

A: ใช่ คุณสามารถใช้เมธอดนี้เพื่อรับพิกัดสำหรับฟิลด์ฟอร์มประเภทต่างๆ ใน Aspose.PDF สำหรับ .NET ได้ โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตวิธีการรับพิกัดสำหรับฟิลด์ RadioButton แต่คุณสามารถปรับใช้แนวทางเดียวกันนี้กับฟิลด์ฟอร์มประเภทอื่นๆ เช่น TextBox, CheckBox, ListBox และอื่นๆ

#### ถาม: ฉันจะแก้ไขหรือปรับเปลี่ยนพิกัดฟิลด์แบบฟอร์มได้อย่างไร

A: พิกัดของฟิลด์ฟอร์มนั้นอิงตามระบบพิกัดของเอกสาร PDF โดยที่จุดกำเนิด (0,0) อยู่ที่มุมซ้ายล่างของหน้า หากต้องการแก้ไขหรือปรับพิกัดของฟิลด์ฟอร์ม คุณสามารถอัปเดต`Rect` คุณสมบัติของฟิลด์ฟอร์มที่เกี่ยวข้องหรือรายการย่อย เช่น RadioButtonOptionField

#### ถาม: ฉันสามารถรับพิกัดของฟิลด์ฟอร์มที่เพิ่มลงในเอกสาร PDF โดยใช้โปรแกรมได้หรือไม่

A: ใช่ คุณสามารถรับพิกัดของฟิลด์ฟอร์มที่ถูกเพิ่มลงในเอกสาร PDF ด้วยโปรแกรมได้ Aspose.PDF สำหรับ .NET ช่วยให้คุณสามารถเพิ่มฟิลด์ฟอร์มแบบไดนามิก และเมื่อเพิ่มแล้ว คุณสามารถดึงพิกัดของฟิลด์ฟอร์มได้โดยใช้แนวทางที่แสดงในบทช่วยสอนนี้

#### ถาม: จุดประสงค์ของการดึงพิกัดฟิลด์ฟอร์มคืออะไร

A: การดึงพิกัดของฟิลด์ฟอร์มอาจมีประโยชน์เมื่อคุณต้องดำเนินการที่เกี่ยวข้องกับเค้าโครงหรือตรวจสอบฟิลด์ฟอร์มในเอกสาร PDF ช่วยให้คุณวางตำแหน่งและปรับแนวฟิลด์ฟอร์มตามพิกัดได้อย่างแม่นยำ ทำให้แน่ใจได้ว่าฟิลด์ฟอร์มจะปรากฏอย่างถูกต้องในเอกสารและมอบประสบการณ์การใช้งานที่ราบรื่นให้กับผู้ใช้

#### ถาม: พิกัดของฟิลด์แบบฟอร์มแสดงเป็นจุดหรือหน่วยอื่นหรือไม่?

A: พิกัดของฟิลด์ฟอร์มใน Aspose.PDF สำหรับ .NET แสดงเป็นจุด โดยจุดหนึ่งเทียบเท่ากับ 1/72 นิ้ว ทำให้เป็นหน่วยวัดมาตรฐานในรูปแบบ PDF