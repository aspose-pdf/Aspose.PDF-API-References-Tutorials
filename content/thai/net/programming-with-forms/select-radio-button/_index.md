---
title: เลือกปุ่มตัวเลือกในเอกสาร PDF
linktitle: เลือกปุ่มตัวเลือกในเอกสาร PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการเลือกปุ่มตัวเลือกในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 250
url: /th/net/programming-with-forms/select-radio-button/
---
นี่คือบทช่วยสอนโดยละเอียดเกี่ยวกับวิธีการเลือกปุ่มตัวเลือกโดยใช้ Aspose.PDF สำหรับ .NET ทำตามขั้นตอนเหล่านี้:

##  ขั้นตอนที่ 1: เริ่มต้นด้วยการกำหนดไดเรกทอรีของเอกสารของคุณโดยระบุเส้นทางใน`dataDir` variable.

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  ขั้นตอนที่ 2: เปิดเอกสาร PDF โดยใช้`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## ขั้นตอนที่ 3: รับฟิลด์ปุ่มตัวเลือกจากแบบฟอร์มเอกสาร

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## ขั้นตอนที่ 4: ระบุดัชนีของปุ่มตัวเลือกที่จะเลือกจากกลุ่ม

```csharp
radioField. Selected = 2;
```

## ขั้นตอนที่ 5: ตั้งค่าเส้นทางเอาต์พุตสำหรับไฟล์ PDF ที่แก้ไข

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## ขั้นตอนที่ 6: บันทึกไฟล์ PDF ที่ถูกแก้ไข

```csharp
pdfDocument.Save(dataDir);
```

## ขั้นตอนที่ 7: แสดงข้อความยืนยันและตำแหน่งของไฟล์ที่บันทึก

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับปุ่มเลือกวิทยุโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
try
{
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// เปิดเอกสาร
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// รับสนาม
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// ระบุดัชนีของปุ่มตัวเลือกจากกลุ่ม
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// บันทึกไฟล์ PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการเลือกปุ่มตัวเลือกโดยใช้ Aspose.PDF สำหรับ .NET เมื่อทำตามขั้นตอนที่ระบุไว้ข้างต้นแล้ว คุณสามารถจัดการและปรับเปลี่ยนปุ่มตัวเลือกในเอกสาร PDF ของคุณได้โดยใช้ Aspose.PDF สำหรับ .NET


### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถเลือกปุ่มตัวเลือกหลายปุ่มในกลุ่มโดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ ไม่ ปุ่มตัวเลือกในกลุ่มได้รับการออกแบบมาให้แยกจากกัน คุณสามารถเลือกปุ่มตัวเลือกได้ครั้งละปุ่มเดียวภายในกลุ่ม และการเลือกปุ่มตัวเลือกจะทำให้ปุ่มตัวเลือกใดๆ ที่เลือกไว้ก่อนหน้านี้ในกลุ่มเดียวกันถูกยกเลิกการเลือกโดยอัตโนมัติ

#### ถาม: ฉันจะดึงปุ่มตัวเลือกที่เลือกในกลุ่มโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 A: หากต้องการดึงปุ่มตัวเลือกที่เลือกในกลุ่ม คุณสามารถใช้`Selected` ทรัพย์สินของ`RadioButtonField` คลาส มันจะคืนค่าดัชนีของปุ่มตัวเลือกที่เลือกภายในกลุ่ม

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของปุ่มตัวเลือกที่เลือกในเอกสาร PDF ได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งรูปลักษณ์ของปุ่มตัวเลือกที่เลือกได้โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถปรับเปลี่ยนสี ขนาด สไตล์ขอบ และคุณลักษณะภาพอื่นๆ เพื่อให้ตรงกับรูปลักษณ์ที่คุณต้องการได้

#### ถาม: เป็นไปได้ไหมที่จะสร้างกลุ่มปุ่มตัวเลือกใหม่โดยใช้โปรแกรม Aspose.PDF สำหรับ .NET?

A: ใช่ คุณสามารถสร้างกลุ่มปุ่มตัวเลือกใหม่โดยใช้โปรแกรม Aspose.PDF สำหรับ .NET ได้ คุณสามารถเพิ่มปุ่มตัวเลือกใหม่ลงในแบบฟอร์มของเอกสารและระบุชื่อกลุ่มเดียวกันสำหรับปุ่มตัวเลือกแต่ละปุ่มเพื่อสร้างกลุ่มใหม่

#### ถาม: Aspose.PDF สำหรับ .NET รองรับการทำงานกับแบบฟอร์ม PDF เชิงโต้ตอบหรือไม่

A: ใช่ Aspose.PDF สำหรับ .NET รองรับการทำงานกับแบบฟอร์ม PDF แบบโต้ตอบได้อย่างสมบูรณ์ รวมถึงปุ่มตัวเลือก ช่องข้อความ ช่องกาเครื่องหมาย และองค์ประกอบแบบฟอร์มอื่นๆ คุณสามารถอ่าน แก้ไข และสร้างแบบฟอร์ม PDF แบบโต้ตอบได้อย่างง่ายดายโดยใช้ไลบรารี