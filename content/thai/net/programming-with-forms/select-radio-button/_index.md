---
title: เลือกปุ่มตัวเลือกในเอกสาร PDF
linktitle: เลือกปุ่มตัวเลือกในเอกสาร PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเลือกปุ่มตัวเลือกในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 250
url: /th/net/programming-with-forms/select-radio-button/
---
ต่อไปนี้เป็นบทช่วยสอนโดยละเอียดเกี่ยวกับวิธีเลือกปุ่มตัวเลือกโดยใช้ Aspose.PDF สำหรับ .NET ทำตามขั้นตอนเหล่านี้:

##  ขั้นตอนที่ 1: เริ่มต้นด้วยการกำหนดไดเร็กทอรีของเอกสารของคุณโดยระบุเส้นทางใน`dataDir` variable.

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  ขั้นตอนที่ 2: เปิดเอกสาร PDF โดยใช้ไฟล์`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## ขั้นตอนที่ 3: รับฟิลด์ปุ่มตัวเลือกจากแบบฟอร์มเอกสาร

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## ขั้นตอนที่ 4: ระบุดัชนีของปุ่มตัวเลือกเพื่อเลือกจากกลุ่ม

```csharp
radioField. Selected = 2;
```

## ขั้นตอนที่ 5: ตั้งค่าเส้นทางเอาต์พุตสำหรับไฟล์ PDF ที่แก้ไข

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## ขั้นตอนที่ 6: บันทึกไฟล์ PDF ที่แก้ไข

```csharp
pdfDocument.Save(dataDir);
```

## ขั้นตอนที่ 7: แสดงข้อความยืนยันและตำแหน่งของไฟล์ที่บันทึกไว้

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับ Select Radio Button โดยใช้ Aspose.PDF สำหรับ .NET 
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

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเลือกปุ่มตัวเลือกโดยใช้ Aspose.PDF สำหรับ .NET ด้วยการทำตามขั้นตอนที่อธิบายไว้ข้างต้น คุณสามารถจัดการและแก้ไขปุ่มตัวเลือกในเอกสาร PDF ของคุณโดยใช้ Aspose.PDF สำหรับ .NET


### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถเลือกปุ่มตัวเลือกหลายปุ่มในกลุ่มโดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ: ไม่ ปุ่มตัวเลือกในกลุ่มได้รับการออกแบบมาให้แยกจากกัน คุณสามารถเลือกปุ่มตัวเลือกได้ครั้งละหนึ่งปุ่มเท่านั้นภายในกลุ่ม และการเลือกหนึ่งปุ่มจะยกเลิกการเลือกปุ่มตัวเลือกที่เลือกไว้ก่อนหน้านี้ในกลุ่มเดียวกันโดยอัตโนมัติ

#### ถาม: ฉันจะดึงข้อมูลปุ่มตัวเลือกที่เลือกในกลุ่มโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการดึงปุ่มตัวเลือกที่เลือกในกลุ่ม คุณสามารถใช้`Selected` ทรัพย์สินของ`RadioButtonField` ระดับ. มันจะส่งคืนดัชนีของปุ่มตัวเลือกที่เลือกภายในกลุ่ม

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของปุ่มตัวเลือกที่เลือกในเอกสาร PDF ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของปุ่มตัวเลือกที่เลือกได้โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถปรับเปลี่ยนสี ขนาด ลักษณะเส้นขอบ และคุณลักษณะภาพอื่นๆ เพื่อให้ตรงกับลักษณะที่คุณต้องการได้

#### ถาม: เป็นไปได้หรือไม่ที่จะสร้างกลุ่มปุ่มตัวเลือกใหม่โดยใช้โปรแกรม Aspose.PDF สำหรับ .NET

ตอบ: ได้ คุณสามารถสร้างกลุ่มปุ่มตัวเลือกใหม่โดยใช้โปรแกรม Aspose.PDF สำหรับ .NET ได้ คุณสามารถเพิ่มปุ่มตัวเลือกใหม่ลงในแบบฟอร์มของเอกสารและระบุชื่อกลุ่มเดียวกันสำหรับปุ่มตัวเลือกแต่ละปุ่มเพื่อสร้างกลุ่มใหม่

#### ถาม: Aspose.PDF สำหรับ .NET รองรับการทำงานกับแบบฟอร์ม PDF แบบโต้ตอบหรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET รองรับการทำงานกับแบบฟอร์ม PDF แบบโต้ตอบได้อย่างสมบูรณ์ รวมถึงปุ่มตัวเลือก ช่องข้อความ กล่องกาเครื่องหมาย และองค์ประกอบแบบฟอร์มอื่นๆ คุณสามารถอ่าน แก้ไข และสร้างแบบฟอร์ม PDF แบบโต้ตอบได้อย่างง่ายดายโดยใช้ไลบรารี