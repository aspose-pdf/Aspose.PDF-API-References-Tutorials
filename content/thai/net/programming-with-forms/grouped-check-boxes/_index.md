---
title: กล่องกาเครื่องหมายที่จัดกลุ่มในเอกสาร PDF
linktitle: กล่องกาเครื่องหมายที่จัดกลุ่มในเอกสาร PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: สร้างช่องทำเครื่องหมายที่จัดกลุ่มในเอกสาร PDF ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 170
url: /th/net/programming-with-forms/grouped-check-boxes/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีสร้างช่องทำเครื่องหมายที่จัดกลุ่มในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ทีละขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการนี้

## ขั้นตอนที่ 1: การเตรียมการ

ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าไลบรารีที่จำเป็นและกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุเอกสาร

สร้างอินสแตนซ์วัตถุเอกสาร:

```csharp
Document pdfDocument = new Document();
```

## ขั้นตอนที่ 3: เพิ่มหน้าลงในเอกสาร PDF

เพิ่มหน้าลงในเอกสาร PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## ขั้นตอนที่ 4: สร้างอินสแตนซ์ของวัตถุ RadioButtonField

สร้างอินสแตนซ์วัตถุ RadioButtonField ด้วยหมายเลขหน้าเป็นอาร์กิวเมนต์:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## ขั้นตอนที่ 5: เพิ่มตัวเลือกปุ่มตัวเลือก

เพิ่มตัวเลือกปุ่มตัวเลือกโดยใช้วัตถุ RadioButtonOptionField และระบุตำแหน่งโดยใช้วัตถุสี่เหลี่ยมผืนผ้า:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## ขั้นตอนที่ 6: ปรับแต่งตัวเลือกปุ่มตัวเลือก

ปรับแต่งตัวเลือกปุ่มตัวเลือกโดยการตั้งค่าสไตล์ เส้นขอบ และรูปลักษณ์:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## ขั้นตอนที่ 7: เพิ่มปุ่มตัวเลือกลงในแบบฟอร์ม

เพิ่มปุ่มตัวเลือกให้กับวัตถุในรูปแบบเอกสาร:

```csharp
pdfDocument.Form.Add(radio);
```

## ขั้นตอนที่ 8: บันทึกเอกสาร

บันทึกเอกสาร PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับกล่องกาเครื่องหมายแบบกลุ่มโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
try
{
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// สร้างอินสแตนซ์วัตถุเอกสาร
	Document pdfDocument = new Document();
	// เพิ่มหน้าลงในไฟล์ PDF
	Page page = pdfDocument.Pages.Add();
	// สร้างอินสแตนซ์วัตถุ RadioButtonField ด้วยหมายเลขหน้าเป็นอาร์กิวเมนต์
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// เพิ่มตัวเลือกปุ่มตัวเลือกแรกและระบุที่มาโดยใช้วัตถุสี่เหลี่ยมผืนผ้า
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// เพิ่มปุ่มตัวเลือกเพื่อสร้างวัตถุของวัตถุเอกสาร
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// บันทึกเอกสาร PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้างกล่องกาเครื่องหมายที่จัดกลุ่มในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถเพิ่มตัวเลือกปุ่มตัวเลือกแบบกำหนดเองและรวมกลุ่มไว้ในเอกสาร PDF ของคุณโดยใช้ Aspose.PDF ได้อย่างง่ายดาย

### คำถามที่พบบ่อย

#### ถาม: กล่องกาเครื่องหมายที่จัดกลุ่มในเอกสาร PDF คืออะไร

ตอบ: กล่องกาเครื่องหมายที่จัดกลุ่มในเอกสาร PDF หมายถึงชุดตัวเลือกปุ่มตัวเลือกที่จัดกลุ่มไว้ด้วยกัน ปุ่มตัวเลือกอนุญาตให้ผู้ใช้เลือกเพียงตัวเลือกเดียวจากกลุ่มตัวเลือกที่ไม่เกิดร่วมกัน เมื่อเลือกปุ่มตัวเลือกปุ่มเดียว ปุ่มอื่นๆ ในกลุ่มเดียวกันจะถูกยกเลิกการเลือกโดยอัตโนมัติ ลักษณะการจัดกลุ่มนี้มีประโยชน์เมื่อคุณต้องการนำเสนอผู้ใช้ด้วยหลายตัวเลือก แต่จำกัดการเลือกไว้เพียงตัวเลือกเดียวเท่านั้น

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของช่องทำเครื่องหมายที่จัดกลุ่มใน Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของช่องทำเครื่องหมายที่จัดกลุ่มใน Aspose.PDF สำหรับ .NET ได้ API มีตัวเลือกต่างๆ เพื่อกำหนดสไตล์ เส้นขอบ และรูปลักษณ์ของตัวเลือกปุ่มตัวเลือก คุณสามารถกำหนดตำแหน่งของแต่ละตัวเลือก เลือกระหว่างสไตล์กล่องที่แตกต่างกัน (เช่น สี่เหลี่ยม วงกลม กากบาท) และปรับคุณสมบัติเส้นขอบเพื่อให้ได้ภาพที่ต้องการ

#### ถาม: ฉันจะเพิ่มช่องทำเครื่องหมายที่จัดกลุ่มลงในหน้าเฉพาะในเอกสาร PDF ได้อย่างไร

ตอบ: หากต้องการเพิ่มช่องทำเครื่องหมายที่จัดกลุ่มลงในหน้าใดหน้าหนึ่งในเอกสาร PDF คุณจะต้องสร้างอินสแตนซ์ a`RadioButtonField` วัตถุที่มีหมายเลขหน้าที่ต้องการเป็นอาร์กิวเมนต์ จากนั้นจึงสร้าง`RadioButtonOptionField` วัตถุที่แสดงถึงตัวเลือกปุ่มตัวเลือกแต่ละตัวและระบุตำแหน่งโดยใช้`Rectangle` วัตถุ. สุดท้าย เพิ่มตัวเลือกเหล่านี้ลงใน`RadioButtonField` และปรับแต่งรูปลักษณ์ตามต้องการก่อนที่จะเพิ่ม`RadioButtonField` มาที่แบบฟอร์มเอกสาร

#### ถาม: ฉันสามารถเพิ่มช่องทำเครื่องหมายหลายกลุ่มลงในเอกสาร PDF เดียวได้หรือไม่

 ตอบ: ได้ คุณสามารถเพิ่มช่องทำเครื่องหมายหลายกลุ่มลงในเอกสาร PDF เดียวได้ แต่ละกลุ่มควรมีเอกลักษณ์เฉพาะตัว`RadioButtonField` วัตถุและ`RadioButtonOptionField` ออบเจ็กต์ภายในแต่ละกลุ่มควรใช้หน้าเดียวกันและชื่อเฉพาะสำหรับตัวเลือกต่างๆ เพื่อให้แน่ใจว่าปุ่มตัวเลือกภายในแต่ละกลุ่มทำงานได้อย่างถูกต้อง และการเลือกจะแยกจากกัน

#### ถาม: กล่องกาเครื่องหมายที่จัดกลุ่มได้รับการสนับสนุนในโปรแกรมดู PDF และแอปพลิเคชันทั้งหมดหรือไม่

ตอบ: ใช่ ช่องทำเครื่องหมายที่จัดกลุ่มได้รับการสนับสนุนในโปรแกรมดู PDF และแอปพลิเคชันที่ตรงตามมาตรฐานทั้งหมด ข้อกำหนด PDF กำหนดปุ่มตัวเลือกและพฤติกรรมการจัดกลุ่ม ทำให้ปุ่มเหล่านี้เป็นที่รู้จักในระดับสากลในรูปแบบ PDF อย่างไรก็ตาม การทดสอบฟังก์ชันการทำงานในโปรแกรมดู PDF ต่างๆ เป็นสิ่งสำคัญเพื่อให้แน่ใจว่ามีพฤติกรรมที่สอดคล้องกันในแพลตฟอร์มต่างๆ