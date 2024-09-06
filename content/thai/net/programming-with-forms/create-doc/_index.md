---
title: สร้างเอกสาร
linktitle: สร้างเอกสาร
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: สร้างเอกสารด้วยปุ่มตัวเลือกได้อย่างง่ายดายโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 40
url: /th/net/programming-with-forms/create-doc/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีสร้างเอกสารที่มีปุ่มตัวเลือกโดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายโค้ดต้นฉบับ C# ทีละขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการนี้

##ขั้นตอนที่ 1: การเตรียมตัว

ก่อนอื่น ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าไลบรารีที่จำเป็นและตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสาร:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารใหม่

สร้างวัตถุเอกสารใหม่เพื่อเก็บเอกสาร PDF:

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 3: เพิ่มหน้า

เพิ่มหน้าใหม่ลงในเอกสาร:

```csharp
Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 4: เพิ่มฟิลด์ปุ่มตัวเลือก

สร้างฟิลด์ปุ่มตัวเลือกและกำหนดตำแหน่งและขนาดของมัน:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## ขั้นตอนที่ 5: เพิ่มตัวเลือกปุ่มตัวเลือก

เพิ่มตัวเลือกที่ต้องการลงในช่องปุ่มตัวเลือก คุณสามารถตั้งค่าพิกัดและขนาดของแต่ละตัวเลือกได้ตามต้องการ:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## ขั้นตอนที่ 6: เพิ่มช่องปุ่มตัวเลือกลงในแบบฟอร์ม

เพิ่มฟิลด์ปุ่มตัวเลือกลงในคอลเลกชันฟิลด์ฟอร์มเอกสาร:

```csharp
doc.Form.Add(field);
```

## ขั้นตอนที่ 7: บันทึกเอกสาร

บันทึกเอกสาร PDF:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับสร้างเอกสารโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
try
{
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// สร้างเอกสารใหม่
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// เพิ่มช่องปุ่มตัวเลือก
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// เพิ่มตัวเลือกปุ่มตัวเลือก โปรดทราบว่าตัวเลือกเหล่านี้ตั้งอยู่
	// ทั้งแนวนอนและแนวตั้ง
	// คุณสามารถลองตั้งค่าพิกัดใดๆ (และแม้แต่ขนาด) ให้กับพวกมันได้
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// บันทึกเอกสาร PDF
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการสร้างเอกสารที่มีปุ่มตัวเลือกโดยใช้ Aspose.PDF สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้แล้ว คุณก็สามารถเพิ่มปุ่มตัวเลือกลงในเอกสาร PDF ของคุณได้อย่างง่ายดายโดยใช้ Aspose.PDF

### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของปุ่มตัวเลือกในเอกสารโดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งรูปลักษณ์ของปุ่มตัวเลือกในเอกสารได้โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถตั้งค่าคุณสมบัติต่างๆ เช่น ขนาด สี สไตล์เส้นขอบ และอื่นๆ เพื่อปรับแต่งรูปลักษณ์ของปุ่มตัวเลือกได้

#### ถาม: ฉันจะเพิ่มกลุ่มปุ่มตัวเลือกที่แยกจากกันได้อย่างไร

A: เพื่อสร้างตัวเลือกที่แยกจากกัน คุณสามารถเพิ่มฟิลด์ปุ่มตัวเลือกหลายรายการที่มีชื่อเดียวกันได้ วิธีนี้จะช่วยให้มั่นใจว่าเมื่อเลือกตัวเลือกหนึ่ง ตัวเลือกอื่นๆ ที่มีชื่อเดียวกันจะถูกยกเลิกการเลือกโดยอัตโนมัติ

#### ถาม: สามารถตั้งค่าตัวเลือกเริ่มต้นที่เลือกไว้สำหรับปุ่มตัวเลือกได้หรือไม่

A: ใช่ คุณสามารถตั้งค่าตัวเลือกเริ่มต้นที่เลือกไว้สำหรับปุ่มตัวเลือกโดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้`Selected` ทรัพย์สินของ`RadioButtonOptionField` วัตถุที่จะทำเครื่องหมายว่าตัวเลือกถูกเลือกไว้ตามค่าเริ่มต้น

#### ถาม: ฉันสามารถเพิ่มตัวจัดการเหตุการณ์ให้กับปุ่มตัวเลือกได้หรือไม่

 A: ใช่ คุณสามารถเพิ่มตัวจัดการเหตุการณ์ลงในปุ่มตัวเลือกได้โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถเชื่อมโยงการดำเนินการ JavaScript เช่น`OnValueChanged`ไปยังปุ่มตัวเลือกเพื่อดำเนินการเฉพาะเมื่อผู้ใช้เลือกตัวเลือก

#### ถาม: ฉันจะดึงตัวเลือกที่เลือกจากกลุ่มปุ่มตัวเลือกหลังจากที่ผู้ใช้เลือกแล้วได้อย่างไร

 A: คุณสามารถดึงตัวเลือกที่เลือกจากกลุ่มปุ่มตัวเลือกโดยใช้ Aspose.PDF สำหรับ .NET หลังจากที่ผู้ใช้เลือกแล้ว คุณสามารถเข้าถึง`Selected` ทรัพย์สินของ`RadioButtonOptionField` วัตถุที่จะตรวจสอบว่ามีการเลือกตัวเลือกใด