---
title: รับฟิลด์จากภูมิภาคในรูปแบบไฟล์ PDF
linktitle: รับฟิลด์จากภูมิภาคในรูปแบบไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: รับฟิลด์จากภูมิภาคที่ต้องการในไฟล์ PDF ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 130
url: /th/net/programming-with-forms/get-fields-from-region/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีรับฟิลด์ของภูมิภาคเฉพาะในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ทีละขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการนี้

## ขั้นตอนที่ 1: การเตรียมการ

ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าไลบรารีที่จำเป็นและกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดไฟล์ PDF

เปิดไฟล์ PDF:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## ขั้นตอนที่ 3: สร้างวัตถุสี่เหลี่ยมผืนผ้าเพื่อผูกขอบเขต

สร้างวัตถุสี่เหลี่ยมเพื่อผูกขอบเขตที่คุณต้องการรับฟิลด์:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## ขั้นตอนที่ 4: รับแบบฟอร์ม PDF

รับแบบฟอร์ม PDF ของเอกสาร:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## ขั้นตอนที่ 5: รับฟิลด์ในพื้นที่สี่เหลี่ยม

รับเขตข้อมูลที่อยู่ในขอบเขตสี่เหลี่ยมที่ระบุ:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## ขั้นตอนที่ 6: แสดงชื่อฟิลด์และค่า

วนซ้ำฟิลด์ผลลัพธ์และแสดงชื่อและค่า:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### ตัวอย่างซอร์สโค้ดสำหรับรับฟิลด์จากภูมิภาคโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดไฟล์ PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// สร้างวัตถุสี่เหลี่ยมเพื่อรับฟิลด์ในพื้นที่นั้น
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// รับแบบฟอร์ม PDF
Aspose.Pdf.Forms.Form form = doc.Form;
// รับเขตข้อมูลในพื้นที่สี่เหลี่ยม
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// แสดงชื่อฟิลด์และค่า
foreach (Field field in fields)
{
	// แสดงคุณสมบัติการจัดวางรูปภาพสำหรับตำแหน่งทั้งหมด
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีรับฟิลด์ของภูมิภาคเฉพาะในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถแยกฟิลด์ที่อยู่ในพื้นที่สี่เหลี่ยมที่กำหนดของเอกสาร PDF ของคุณได้อย่างง่ายดายโดยใช้ Aspose.PDF

### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถใช้วิธีนี้เพื่อรับฟิลด์จากขอบเขตที่ไม่ใช่สี่เหลี่ยมในเอกสาร PDF ได้หรือไม่

 ตอบ: ไม่ใช่ วิธีการที่ให้ไว้`GetFieldsInRect` ได้รับการออกแบบมาโดยเฉพาะเพื่อดึงข้อมูลฟิลด์ที่อยู่ภายในขอบเขตสี่เหลี่ยมในเอกสาร PDF หากคุณต้องการแยกฟิลด์ออกจากขอบเขตที่ไม่ใช่สี่เหลี่ยม คุณจะต้องใช้ตรรกะแบบกำหนดเองเพื่อระบุและแยกฟิลด์ตามเกณฑ์อื่นๆ เช่น พิกัดของฟิลด์หรือชื่อ

#### ถาม: ฉันจะปรับขนาดหรือตำแหน่งของสี่เหลี่ยมผืนผ้าเพื่อรับฟิลด์จากภูมิภาคอื่นได้อย่างไร

 ตอบ: หากต้องการรับฟิลด์จากภูมิภาคอื่น คุณสามารถแก้ไขได้`Aspose.Pdf.Rectangle` พารามิเตอร์ของวัตถุที่ใช้ในการกำหนดสี่เหลี่ยมขอบเขต ที่`Rectangle` Constructor รับพารามิเตอร์สี่ตัว:`x`, `y`, `width` , และ`height`ซึ่งแสดงถึงพิกัดมุมซ้ายบนและขนาดของสี่เหลี่ยม การปรับพารามิเตอร์เหล่านี้จะเปลี่ยนขอบเขตของการแตกฟิลด์

#### ถาม: จะเกิดอะไรขึ้นหากไม่มีฟิลด์ภายในขอบเขตสี่เหลี่ยมที่ระบุ

 ตอบ: หากไม่มีฟิลด์ภายในขอบเขตสี่เหลี่ยมที่ระบุ ระบบจะ`GetFieldsInRect` วิธีการจะส่งคืนอาร์เรย์ว่าง คุณสามารถตรวจสอบความยาวของอาร์เรย์เพื่อดูว่ามีฟิลด์ใด ๆ ภายในขอบเขตหรือไม่

#### ถาม: ฉันสามารถรับฟิลด์จากขอบเขตที่ทับซ้อนกันในเอกสาร PDF ได้หรือไม่

 ตอบ: ได้ คุณสามารถรับฟิลด์จากขอบเขตที่ทับซ้อนกันในเอกสาร PDF ได้ด้วยการสร้างหลายรายการ`Aspose.Pdf.Rectangle` วัตถุและการเรียก`GetFieldsInRect` วิธีการสำหรับแต่ละคน ภูมิภาคที่ทับซ้อนกันจะได้รับการจัดการอย่างเป็นอิสระ และคุณจะได้รับอาร์เรย์ของฟิลด์แยกกันสำหรับแต่ละภูมิภาค

#### ถาม: เป็นไปได้ไหมที่จะรับฟิลด์จากหน้าใดหน้าหนึ่งหรือหลายหน้าในเอกสาร PDF

ตอบ: ได้ คุณสามารถรับฟิลด์จากหน้าใดหน้าหนึ่งหรือหลายหน้าในเอกสาร PDF ได้ เพื่อให้บรรลุเป้าหมายนี้ คุณสามารถโหลดเอกสาร PDF เข้าถึงหน้าที่ต้องการโดยใช้`doc.Pages` คอลเลกชันแล้วใช้`GetFieldsInRect` วิธีการไปยังภูมิภาคเฉพาะของแต่ละหน้า