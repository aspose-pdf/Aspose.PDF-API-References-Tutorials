---
title: กล่องกาเครื่องหมายแบบกลุ่มในเอกสาร PDF
linktitle: กล่องกาเครื่องหมายแบบกลุ่มในเอกสาร PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: สร้างกล่องกาเครื่องหมายแบบกลุ่มในเอกสาร PDF ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 170
url: /th/net/programming-with-forms/grouped-check-boxes/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีสร้างกล่องกาเครื่องหมายแบบกลุ่มในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายโค้ดต้นฉบับ C# ทีละขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการนี้

## ขั้นตอนที่ 1: การเตรียมพร้อม

ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าไลบรารีที่จำเป็นและตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณแล้ว:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุเอกสาร

สร้างอินสแตนซ์ของวัตถุเอกสาร:

```csharp
Document pdfDocument = new Document();
```

## ขั้นตอนที่ 3: เพิ่มหน้าลงในเอกสาร PDF

เพิ่มหน้าลงในเอกสาร PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## ขั้นตอนที่ 4: สร้างอินสแตนซ์ของวัตถุ RadioButtonField

สร้างอินสแตนซ์ของวัตถุ RadioButtonField โดยใช้หมายเลขหน้าเป็นอาร์กิวเมนต์:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## ขั้นตอนที่ 5: เพิ่มตัวเลือกปุ่มตัวเลือก

เพิ่มตัวเลือกปุ่มตัวเลือกโดยใช้ RadioButtonOptionField และระบุตำแหน่งโดยใช้ Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## ขั้นตอนที่ 6: ปรับแต่งตัวเลือกปุ่มตัวเลือก

ปรับแต่งตัวเลือกปุ่มตัวเลือกโดยการตั้งค่ารูปแบบ ขอบ และลักษณะที่ปรากฏ:

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

เพิ่มปุ่มตัวเลือกลงในวัตถุแบบฟอร์มเอกสาร:

```csharp
pdfDocument.Form.Add(radio);
```

## ขั้นตอนที่ 8: บันทึกเอกสาร

บันทึกเอกสาร PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับกล่องกาเครื่องหมายแบบกลุ่มโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
try
{
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// สร้างอินสแตนซ์ของวัตถุเอกสาร
	Document pdfDocument = new Document();
	// เพิ่มหน้าลงในไฟล์ PDF
	Page page = pdfDocument.Pages.Add();
	// สร้างวัตถุ RadioButtonField โดยใช้หมายเลขหน้าเป็นอาร์กิวเมนต์
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// เพิ่มตัวเลือกปุ่มตัวเลือกแรกและระบุแหล่งที่มาโดยใช้ Rectangle object
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

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการสร้างกล่องกาเครื่องหมายแบบกลุ่มในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้แล้ว คุณก็สามารถเพิ่มตัวเลือกปุ่มตัวเลือกแบบกำหนดเองและรวมไว้ในเอกสาร PDF ของคุณได้อย่างง่ายดายโดยใช้ Aspose.PDF

### คำถามที่พบบ่อย

#### ถาม: กล่องกาเครื่องหมายแบบกลุ่มในเอกสาร PDF คืออะไร

A: ช่องกาเครื่องหมายแบบกลุ่มในเอกสาร PDF หมายถึงชุดตัวเลือกปุ่มตัวเลือกที่จัดกลุ่มเข้าด้วยกัน ปุ่มตัวเลือกช่วยให้ผู้ใช้เลือกได้เพียงตัวเลือกเดียวจากกลุ่มตัวเลือกที่แยกจากกัน เมื่อเลือกปุ่มตัวเลือกหนึ่ง ปุ่มตัวเลือกอื่นๆ ในกลุ่มเดียวกันจะถูกยกเลิกการเลือกโดยอัตโนมัติ พฤติกรรมการจัดกลุ่มนี้มีประโยชน์เมื่อคุณต้องการให้ผู้ใช้มีตัวเลือกหลายตัวเลือกแต่จำกัดการเลือกให้เหลือเพียงตัวเลือกเดียวเท่านั้น

#### ถาม: ฉันสามารถปรับแต่งลักษณะของกล่องกาเครื่องหมายแบบกลุ่มใน Aspose.PDF สำหรับ .NET ได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งลักษณะของกล่องกาเครื่องหมายที่จัดกลุ่มใน Aspose.PDF สำหรับ .NET ได้ API มีตัวเลือกต่างๆ สำหรับการตั้งค่ารูปแบบ ขอบ และลักษณะของตัวเลือกปุ่มตัวเลือก คุณสามารถกำหนดตำแหน่งของแต่ละตัวเลือก เลือกรูปแบบกล่องต่างๆ (เช่น สี่เหลี่ยม วงกลม ไม้กางเขน) และปรับคุณสมบัติของขอบเพื่อให้ได้การแสดงผลภาพตามต้องการ

#### ถาม: ฉันจะเพิ่มกล่องกาเครื่องหมายแบบกลุ่มลงในหน้าเฉพาะในเอกสาร PDF ได้อย่างไร

ก: หากต้องการเพิ่มกล่องกาเครื่องหมายแบบกลุ่มลงในหน้าเฉพาะในเอกสาร PDF คุณจำเป็นต้องสร้างอินสแตนซ์`RadioButtonField` วัตถุที่มีหมายเลขหน้าที่ต้องการเป็นอาร์กิวเมนต์ จากนั้นสร้าง`RadioButtonOptionField` วัตถุที่แสดงตัวเลือกปุ่มตัวเลือกแต่ละปุ่มและระบุตำแหน่งโดยใช้`Rectangle` วัตถุ สุดท้ายให้เพิ่มตัวเลือกเหล่านี้ลงใน`RadioButtonField` และปรับแต่งรูปลักษณ์ตามต้องการก่อนที่จะเพิ่ม`RadioButtonField` เข้าสู่แบบฟอร์มเอกสาร

#### ถาม: ฉันสามารถเพิ่มกลุ่มกล่องกาเครื่องหมายหลายกลุ่มลงในเอกสาร PDF เดียวได้หรือไม่

 A: ใช่ คุณสามารถเพิ่มกลุ่มกล่องกาเครื่องหมายหลายกลุ่มลงในเอกสาร PDF เดียวได้ แต่ละกลุ่มควรมีกล่องกาเครื่องหมายเฉพาะ`RadioButtonField` วัตถุ และ`RadioButtonOptionField` วัตถุภายในแต่ละกลุ่มควรมีหน้าเดียวกันและมีชื่อเฉพาะสำหรับตัวเลือกของวัตถุนั้นๆ วิธีนี้จะช่วยให้ปุ่มตัวเลือกภายในแต่ละกลุ่มทำงานได้อย่างถูกต้อง และการเลือกจะไม่รวมกัน

#### ถาม: กล่องกาเครื่องหมายแบบกลุ่มได้รับการสนับสนุนในโปรแกรมดู PDF และแอปพลิเคชันทั้งหมดหรือไม่

A: ใช่ กล่องกาเครื่องหมายแบบกลุ่มได้รับการรองรับในโปรแกรมอ่าน PDF และแอปพลิเคชันที่สอดคล้องกับมาตรฐานทั้งหมด ข้อกำหนด PDF กำหนดปุ่มตัวเลือกและพฤติกรรมการจัดกลุ่มของปุ่มเหล่านี้ ทำให้ปุ่มเหล่านี้สามารถจดจำได้ในรูปแบบ PDF อย่างไรก็ตาม การทดสอบฟังก์ชันการทำงานในโปรแกรมอ่าน PDF ต่างๆ ถือเป็นสิ่งสำคัญเพื่อให้แน่ใจว่ามีพฤติกรรมที่สอดคล้องกันในแพลตฟอร์มต่างๆ