---
title: เพิ่มลบ Javascript ลงในเอกสาร PDF
linktitle: เพิ่มลบ Javascript ไปยัง Doc
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มและลบ JavaScript ลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมบทช่วยสอนโค้ดสำหรับการเขียนสคริปต์ระดับเอกสาร
type: docs
weight: 30
url: /th/net/programming-with-document/addremovejavascripttodoc/
---
ในการเพิ่มและลบ JavaScript ลงในเอกสาร PDF เราจะใช้ Aspose.PDF สำหรับไลบรารี .NET ไลบรารีอันทรงพลังนี้ช่วยให้เราจัดการไฟล์ PDF ในแอปพลิเคชัน .NET ทำตามคำแนะนำทีละขั้นตอนด้านล่างเพื่อเพิ่มและลบ JavaScript โดยใช้ Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 1: สร้างเอกสาร PDF ใหม่

 เริ่มต้นด้วยการสร้างอินสแตนซ์ใหม่ของ`Document` คลาสที่จัดทำโดย Aspose.PDF สำหรับ .NET ซึ่งจะทำหน้าที่เป็นเอกสาร PDF ที่เราจะเพิ่ม JavaScript

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## ขั้นตอนที่ 2: เพิ่ม JavaScript ในระดับเอกสาร

 หากต้องการเพิ่ม JavaScript ในระดับเอกสาร ให้ใช้`JavaScript` ทรัพย์สินของ`Document` ระดับ. กำหนดฟังก์ชัน JavaScript ให้กับคีย์ในพจนานุกรม JavaScript

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 ในบทช่วยสอนนี้ เราได้เพิ่มฟังก์ชัน JavaScript สองฟังก์ชัน`func1` และ`func2`ไปยังเอกสาร PDF

## ขั้นตอนที่ 3: ลบ JavaScript ระดับเอกสาร

 หากต้องการลบ JavaScript ในระดับเอกสาร ให้โหลดเอกสาร PDF และเข้าถึง`JavaScript`พจนานุกรม. วนซ้ำคีย์และลบฟังก์ชัน JavaScript ที่ต้องการ

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 ในบทช่วยสอนนี้ เราจะลบไฟล์`func1` ฟังก์ชั่น JavaScript จากเอกสาร PDF

## ขั้นตอนที่ 4: บันทึกและตรวจสอบการเปลี่ยนแปลง

บันทึกเอกสาร PDF ที่แก้ไขและตรวจสอบการเปลี่ยนแปลง

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

รหัสนี้จะบันทึกเอกสาร PDF ที่แก้ไขแล้วและแสดงข้อความแสดงความสำเร็จ

### ตัวอย่างซอร์สโค้ดสำหรับ Add Remove Javascript จากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// ลบ JavaScript ระดับเอกสาร
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## บทสรุป

ในบทความนี้ เราได้ให้คำแนะนำทีละขั้นตอนในการเพิ่มและลบ JavaScript ออกจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำและใช้บทช่วยสอนโค้ดที่ให้มา คุณสามารถรวม JavaScript เข้ากับเอกสาร PDF ของคุณได้อย่างง่ายดาย และลบออกได้เมื่อจำเป็น JavaScript เปิดใช้งานฟังก์ชันการทำงานแบบไดนามิกและการโต้ตอบในไฟล์ PDF ของคุณ ปรับปรุงประสบการณ์ผู้ใช้


### คำถามที่พบบ่อยสำหรับการเพิ่มการลบจาวาสคริปต์ลงในเอกสาร PDF

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถจัดการไฟล์ PDF ในแอปพลิเคชัน .NET ได้อย่างมีประสิทธิภาพ มีคุณสมบัติมากมายสำหรับการทำงานกับเอกสาร PDF โดยทางโปรแกรม

#### ถาม: ฉันจะเพิ่ม JavaScript ลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 ตอบ: คุณสามารถเพิ่ม JavaScript ในระดับเอกสารได้โดยใช้`JavaScript` ทรัพย์สินของ`Document` ระดับ. เพียงกำหนดฟังก์ชัน JavaScript ให้กับคีย์ในพจนานุกรม JavaScript

#### ถาม: ฉันสามารถลบ JavaScript ออกจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

 ตอบ: ได้ คุณสามารถลบ JavaScript ออกจากเอกสาร PDF ได้โดยเข้าไปที่`JavaScript` พจนานุกรมและลบฟังก์ชัน JavaScript ที่ต้องการ

#### ถาม: Aspose.PDF สำหรับ .NET เหมาะสำหรับโครงการระดับมืออาชีพหรือไม่

ตอบ: แน่นอนว่า Aspose.PDF สำหรับ .NET ถูกนำมาใช้กันอย่างแพร่หลายในโครงการระดับมืออาชีพสำหรับงานจัดการและสร้าง PDF มีฟังก์ชันการทำงานที่มีประสิทธิภาพสูงและเชื่อถือได้

#### ถาม: การเพิ่ม JavaScript ลงในเอกสาร PDF ให้ประโยชน์อะไรบ้าง

ตอบ: การเพิ่ม JavaScript ลงในเอกสาร PDF ช่วยให้คุณสามารถสร้างไฟล์ PDF แบบโต้ตอบและไดนามิกได้ คุณสามารถใช้การตรวจสอบแบบฟอร์ม คำนวณ และเพิ่มคุณลักษณะการโต้ตอบต่างๆ เพื่อปรับปรุงประสบการณ์ผู้ใช้