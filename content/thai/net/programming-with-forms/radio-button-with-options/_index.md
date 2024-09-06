---
title: ปุ่มตัวเลือกพร้อมตัวเลือก
linktitle: ปุ่มตัวเลือกพร้อมตัวเลือก
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เพิ่มปุ่มตัวเลือกที่มีตัวเลือกลงในเอกสาร PDF ได้อย่างง่ายดายโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 230
url: /th/net/programming-with-forms/radio-button-with-options/
---

ในบทช่วยสอนนี้ เราจะแสดงวิธีเพิ่มปุ่มตัวเลือกที่มีตัวเลือกในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายโค้ดต้นฉบับ C# ทีละขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการนี้

## ขั้นตอนที่ 1: การเตรียมพร้อม

ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าไลบรารีที่จำเป็นและตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณแล้ว:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุเอกสาร

สร้างอินสแตนซ์ของวัตถุเอกสารเพื่อสร้างเอกสาร PDF ใหม่:

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 3: เพิ่มหน้าและตาราง

เพิ่มหน้าลงในเอกสารและสร้างตารางเพื่อเก็บตัวเลือกปุ่มตัวเลือก:

```csharp
Page page = doc.Pages.Add();
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "120 120 120";
page.Paragraphs.Add(table);
```

## ขั้นตอนที่ 4: สร้างอินสแตนซ์ของวัตถุ RadioButtonField

สร้างอินสแตนซ์ของวัตถุ RadioButtonField เพื่อแสดงปุ่มตัวเลือก:

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf. PartialName = "radio";
doc.Form.Add(rf, 1);
```

## ขั้นตอนที่ 5: เพิ่มตัวเลือกปุ่มตัวเลือก

เพิ่มตัวเลือกปุ่มตัวเลือกลงในวัตถุ RadioButtonField:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
opt1.Width = 15;
opt1. Height = 15;
opt2.Width = 15;
opt2. Height = 15;
opt3.Width = 15;
opt3. Height = 15;
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

## ขั้นตอนที่ 6: ปรับแต่งตัวเลือกปุ่มตัวเลือก

ปรับแต่งตัวเลือกปุ่มตัวเลือกโดยการตั้งค่าแอตทริบิวต์เช่นเส้นขอบ สีข้อความ และข้อความคำบรรยาย:

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");

// ทำซ้ำขั้นตอนเดียวกันสำหรับ opt2 และ opt3

```

## ขั้นตอนที่ 7: เพิ่มตัวเลือกปุ่มตัวเลือกลงในตาราง

เพิ่มตัวเลือกปุ่มตัวเลือกลงในตารางเพื่อแสดง:

```csharp
Cell c1 = table.Rows.Add().Cells.Add();
Cell c2 = table.Rows[table.Rows.Count].Cells.Add();
Cell c3 = table.Rows[table.Rows.Count].Cells.Add();

c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

## ขั้นตอนที่ 8: บันทึกเอกสาร PDF

บันทึกเอกสาร PDF ที่สร้างขึ้น:

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
doc.Save(dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับปุ่มตัวเลือกโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
try
{
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	Page page = doc.Pages.Add();
	Aspose.Pdf.Table table = new Aspose.Pdf.Table();
	table.ColumnWidths = "120 120 120";
	page.Paragraphs.Add(table);
	Row r1 = table.Rows.Add();
	Cell c1 = r1.Cells.Add();
	Cell c2 = r1.Cells.Add();
	Cell c3 = r1.Cells.Add();
	RadioButtonField rf = new RadioButtonField(page);
	rf.PartialName = "radio";
	doc.Form.Add(rf, 1);
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt1.OptionName = "Item1";
	opt2.OptionName = "Item2";
	opt3.OptionName = "Item3";
	opt1.Width = 15;
	opt1.Height = 15;
	opt2.Width = 15;
	opt2.Height = 15;
	opt3.Width = 15;
	opt3.Height = 15;
	rf.Add(opt1);
	rf.Add(opt2);
	rf.Add(opt3);
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt1.Caption = new TextFragment("Item1");
	opt2.Border = new Border(opt1);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	opt2.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt2.Caption = new TextFragment("Item2");
	opt3.Border = new Border(opt1);
	opt3.Border.Width = 1;
	opt3.Border.Style = BorderStyle.Solid;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	opt3.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt3.Caption = new TextFragment("Item3");
	c1.Paragraphs.Add(opt1);
	c2.Paragraphs.Add(opt2);
	c3.Paragraphs.Add(opt3);
	dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
	// บันทึกไฟล์ PDF
	doc.Save(dataDir);
	Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## บทสรุป

ขอแสดงความยินดี ! คุณได้เพิ่มปุ่มตัวเลือกลงในเอกสาร PDF สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถใช้เมธอดนี้เพื่อสร้างแบบฟอร์มโต้ตอบในเอกสาร PDF ของคุณได้แล้ว