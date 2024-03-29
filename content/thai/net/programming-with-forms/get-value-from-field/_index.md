---
title: รับค่าจากฟิลด์ในเอกสาร PDF
linktitle: รับค่าจากฟิลด์ในเอกสาร PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: รับค่าของฟิลด์แบบฟอร์มในเอกสาร PDF ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 140
url: /th/net/programming-with-forms/get-value-from-field/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีรับค่าของฟิลด์แบบฟอร์มโดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ทีละขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการนี้

## ขั้นตอนที่ 1: การเตรียมการ

ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าไลบรารีที่จำเป็นและกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดเอกสาร

เปิดเอกสาร PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## ขั้นตอนที่ 3: รับฟิลด์

รับฟิลด์ฟอร์มที่ต้องการ (ในตัวอย่างนี้ เราใช้ฟิลด์ "textbox1"):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## ขั้นตอนที่ 4: รับค่าฟิลด์

 รับค่าฟิลด์โดยใช้`Value` คุณสมบัติ:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### ตัวอย่างซอร์สโค้ดสำหรับรับค่าจากฟิลด์โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// รับสนาม
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// รับค่าฟิลด์
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีรับค่าของฟิลด์แบบฟอร์มโดยใช้ Aspose.PDF สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถแยกค่าของฟิลด์ฟอร์มเฉพาะในเอกสาร PDF ของคุณโดยใช้ Aspose.PDF ได้อย่างง่ายดาย

### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถรับค่าของฟิลด์ฟอร์มโดยไม่ทราบชื่อล่วงหน้าได้หรือไม่

 ตอบ: ไม่ คุณจำเป็นต้องทราบชื่อหรือชื่อบางส่วนของฟิลด์แบบฟอร์มเพื่อรับค่าโดยใช้ Aspose.PDF สำหรับ .NET ที่`pdfDocument.Form["fieldname"]` ไวยากรณ์ต้องการชื่อที่แน่นอนหรือชื่อบางส่วนของฟิลด์แบบฟอร์มเพื่อเข้าถึงคุณสมบัติรวมถึงค่าด้วย

#### ถาม: จะเกิดอะไรขึ้นหากไม่มีฟิลด์แบบฟอร์มในเอกสาร PDF

 ตอบ: หากไม่มีฟิลด์แบบฟอร์มในเอกสาร PDF จะต้อง`pdfDocument.Form["fieldname"]` ไวยากรณ์จะกลับมา`null` . จำเป็นอย่างยิ่งที่จะต้องจัดการกับกรณีดังกล่าวโดยการตรวจสอบ`null` ก่อนที่จะเข้าถึงคุณสมบัติของฟิลด์แบบฟอร์มเพื่อหลีกเลี่ยงข้อยกเว้น

#### ถาม: ฉันจะจัดการกับฟิลด์แบบฟอร์มประเภทต่างๆ (เช่น ช่องทำเครื่องหมาย ปุ่มตัวเลือก) เพื่อรับค่าได้อย่างไร

 ตอบ: ในการจัดการฟิลด์แบบฟอร์มประเภทต่างๆ คุณสามารถใช้คลาสฟิลด์ที่เหมาะสมที่มีอยู่ใน Aspose.PDF สำหรับ .NET ได้ ตัวอย่างเช่น ใช้`CheckBoxField` เพื่อทำงานกับช่องทำเครื่องหมายและ`RadioButtonField`เพื่อทำงานกับปุ่มตัวเลือก เมื่อคุณมีออบเจ็กต์ฟิลด์ที่ถูกต้องแล้ว คุณสามารถเข้าถึงคุณสมบัติของออบเจ็กต์ได้ รวมถึงค่าด้วย

#### ถาม: ฉันสามารถรับค่าของช่องแบบฟอร์มหลายช่องพร้อมกันได้หรือไม่

ตอบ: ได้ คุณสามารถรับค่าของช่องแบบฟอร์มหลายรายการพร้อมกันได้โดยการวนซ้ำคอลเลกชันช่องแบบฟอร์มโดยใช้การวนซ้ำหรือการสืบค้น LINQ ด้วยวิธีนี้ คุณจะสามารถเข้าถึงค่าของฟิลด์แบบฟอร์มแต่ละฟิลด์ในเอกสาร PDF โดยทางโปรแกรม

#### ถาม: เป็นไปได้หรือไม่ที่จะแก้ไขค่าของฟิลด์แบบฟอร์มและบันทึกการเปลี่ยนแปลงกลับไปยังเอกสาร PDF

 ตอบ: ได้ คุณสามารถแก้ไขค่าของฟิลด์แบบฟอร์มได้โดยใช้ Aspose.PDF สำหรับ .NET และบันทึกการเปลี่ยนแปลงกลับไปยังเอกสาร PDF หลังจากอัพเดต.`Value` คุณสมบัติของฟิลด์แบบฟอร์มคุณสามารถใช้`pdfDocument.Save()` วิธีการบันทึกการเปลี่ยนแปลงในเอกสาร PDF ต้นฉบับ