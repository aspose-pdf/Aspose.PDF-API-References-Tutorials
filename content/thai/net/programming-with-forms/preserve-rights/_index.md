---
title: รักษาสิทธิ
linktitle: รักษาสิทธิ
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: รักษาสิทธิ์ของแบบฟอร์มในเอกสาร PDF ของคุณด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 210
url: /th/net/programming-with-forms/preserve-rights/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีรักษาสิทธิ์ของแบบฟอร์มในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ทีละขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการนี้

## ขั้นตอนที่ 1: การเตรียมการ

ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าไลบรารีที่จำเป็นและกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดเอกสาร

 เปิดเอกสาร PDF ต้นฉบับโดยใช้ไฟล์`FileStream` ด้วยสิทธิ์ในการอ่านและเขียน:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## ขั้นตอนที่ 3: แก้ไขฟิลด์แบบฟอร์ม

ตรวจดูช่องแบบฟอร์มทั้งหมดในเอกสารและทำการเปลี่ยนแปลงที่จำเป็น ในตัวอย่างนี้ เรากำลังเปลี่ยนค่าของฟิลด์ฟอร์มที่มี "A1" อยู่ในชื่อ:

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## ขั้นตอนที่ 4: บันทึกเอกสารที่อัปเดต

บันทึกเอกสาร PDF ที่แก้ไข:

```csharp
pdfDocument.Save();
```

##  ขั้นตอนที่ 5: ปิด`FileStream`

 อย่าลืมปิด.`FileStream` วัตถุเมื่อคุณทำเสร็จแล้ว:

```csharp
fs. Close();
```

### ตัวอย่างซอร์สโค้ดสำหรับการรักษาสิทธิ์โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// อ่านแบบฟอร์ม PDF ต้นฉบับด้วย FileAccess ของการอ่านและเขียน
// เราต้องการสิทธิ์ ReadWrite เพราะหลังจากแก้ไขแล้ว
// เราจำเป็นต้องบันทึกเนื้อหาที่อัปเดตไว้ในเอกสาร/ไฟล์เดียวกัน
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// สร้างอินสแตนซ์เอกสาร
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// รับค่าจากทุกสาขา
foreach (Field formField in pdfDocument.Form)
{
	// หากชื่อเต็มของฟิลด์มี A1 ให้ดำเนินการดังกล่าว
	if (formField.FullName.Contains("A1"))
	{
		// กรอกแบบฟอร์มเป็นกล่องข้อความ
		TextBoxField textBoxField = formField as TextBoxField;
		// แก้ไขค่าฟิลด์
		textBoxField.Value = "Testing";
	}
}
// บันทึกเอกสารที่อัปเดตในบันทึก FileStream
pdfDocument.Save();
// ปิดวัตถุสตรีมไฟล์
fs.Close();
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการรักษาสิทธิ์ของแบบฟอร์มในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถเข้าถึงฟิลด์แบบฟอร์มและทำการเปลี่ยนแปลงเฉพาะได้โดยยังคงรักษาสิทธิ์ในการเข้าถึงและเขียนไว้


### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถรักษาสิทธิ์ในช่องแบบฟอร์มเฉพาะโดยไม่กระทบต่อช่องอื่นในเอกสาร PDF ได้หรือไม่

 ตอบ: ได้ โดยใช้`FullName` คุณสมบัติของฟิลด์ฟอร์ม คุณสามารถกำหนดเป้าหมายฟิลด์ฟอร์มเฉพาะเพื่อเก็บรักษาไว้ได้ โดยปล่อยให้ฟิลด์อื่นๆ ไม่ได้รับผลใดๆ

#### ถาม: ฉันสามารถรักษาสิทธิ์ของแบบฟอร์มในเอกสาร PDF ที่มีการป้องกันด้วยรหัสผ่านได้หรือไม่

ตอบ: ได้ Aspose.PDF สำหรับ .NET ช่วยให้คุณรักษาสิทธิ์ของแบบฟอร์มได้แม้ในเอกสาร PDF ที่มีการป้องกันด้วยรหัสผ่าน ตราบใดที่คุณระบุรหัสผ่านที่ถูกต้องเพื่อเข้าถึงและแก้ไขไฟล์

#### ถาม: จะเกิดอะไรขึ้นหากฉันพยายามแก้ไขฟิลด์แบบฟอร์มโดยไม่มีสิทธิ์การเข้าถึงที่เหมาะสม

ตอบ: หากคุณพยายามแก้ไขฟิลด์แบบฟอร์มโดยไม่มีสิทธิ์การเข้าถึงที่เหมาะสม การเปลี่ยนแปลงจะไม่ถูกบันทึกในเอกสาร PDF และคุณอาจได้รับข้อยกเว้นหรือข้อความแสดงข้อผิดพลาด

#### ถาม: Aspose.PDF สำหรับ .NET เข้ากันได้กับ .NET Framework ทุกเวอร์ชันหรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET เข้ากันได้กับ .NET Framework ทุกเวอร์ชัน รวมถึง .NET Core และ .NET Standard

#### ถาม: ฉันสามารถรักษาสิทธิ์ของแบบฟอร์มในเอกสาร PDF โดยทางโปรแกรมในภาษาโปรแกรมอื่นนอกเหนือจาก C# ได้หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET รองรับภาษาการเขียนโปรแกรมที่หลากหลาย เช่น VB.NET และ ASP.NET นอกเหนือจาก C#