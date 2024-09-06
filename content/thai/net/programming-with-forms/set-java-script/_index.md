---
title: ตั้งค่า Java Script
linktitle: ตั้งค่า Java Script
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการใช้ Aspose.PDF สำหรับ .NET เพื่อตั้งค่า JavaScript ในฟิลด์ฟอร์มในไฟล์ PDF
type: docs
weight: 270
url: /th/net/programming-with-forms/set-java-script/
---
ในคู่มือนี้ เราจะอธิบายทีละขั้นตอนเกี่ยวกับวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อกำหนด JavaScript ในฟิลด์ฟอร์มของเอกสาร PDF เราจะแสดงวิธีการกำหนดค่าการดำเนินการ JavaScript เพื่อดำเนินการเฉพาะกับฟิลด์ข้อความ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- สภาพแวดล้อมการพัฒนา .NET ติดตั้งอยู่บนระบบของคุณ
- ไลบรารี Aspose.PDF สำหรับ .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose

## ขั้นตอนที่ 1: การกำหนดค่าไดเรกทอรีเอกสาร

 ขั้นตอนแรกคือการกำหนดค่าไดเรกทอรีเอกสารที่ไฟล์ PDF ที่คุณต้องการทำงานอยู่ คุณสามารถใช้`dataDir` ตัวแปรสำหรับระบุเส้นทางไดเร็กทอรี

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENTS DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 2: โหลดไฟล์ PDF อินพุต

 ในขั้นตอนนี้เราจะโหลดไฟล์ PDF อินพุตโดยใช้`Document` ชั้นเรียนของ Aspose.PDF

```csharp
// โหลดไฟล์ PDF อินพุต
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

ตรวจสอบให้แน่ใจว่าไฟล์ PDF อินพุตมีอยู่ในไดเร็กทอรีเอกสารที่ระบุ

## ขั้นตอนที่ 3: การเข้าถึงฟิลด์ TextBox

 หากต้องการใช้ JavaScript กับฟิลด์ข้อความเฉพาะ เราต้องเข้าถึงฟิลด์นั้นก่อน ในตัวอย่างนี้ เราถือว่าฟิลด์ข้อความนั้นเรียกว่า "textbox1" ใช้`doc.Form["textbox1"]` วิธีการที่จะได้รับสิ่งที่สอดคล้องกัน`TextBoxField` วัตถุ.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

ตรวจสอบให้แน่ใจว่าช่องข้อความที่ระบุมีอยู่ในไฟล์ PDF อินพุต

## ขั้นตอนที่ 4: กำหนดค่าการดำเนินการ JavaScript

 ตอนนี้เราได้เข้าถึงฟิลด์ข้อความแล้ว เราสามารถกำหนดค่าการดำเนินการ JavaScript ที่เชื่อมโยงกับฟิลด์นี้ได้ ในตัวอย่างนี้ เราจะใช้การดำเนินการสองอย่าง:`OnModifyCharacter` และ`OnFormat` การดำเนินการเหล่านี้จะถูกกำหนดโดยใช้`JavascriptAction` วัตถุ

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

อย่าลืมปรับแต่งการดำเนินการ JavaScript ตามความต้องการของคุณ

## ขั้นตอนที่ 5: ตั้งค่าค่าฟิลด์เริ่มต้น

ก่อนที่จะบันทึก PDF ที่ได้ เราสามารถตั้งค่าเริ่มต้นให้กับฟิลด์ข้อความได้ ในตัวอย่างนี้ เราจะตั้งค่า "123" ให้กับฟิลด์

```csharp
field.Value = "123";
```

ปรับแต่งค่านี้ตามความต้องการของคุณ

## ขั้นตอนที่ 6: บันทึก PDF ที่ได้

 ตอนนี้เราได้ตั้งค่าฟิลด์ข้อความและการดำเนินการ JavaScript เสร็จเรียบร้อยแล้ว เราสามารถบันทึก PDF ที่ได้โดยใช้`Save` วิธีการของ`Document` ระดับ.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// บันทึกผลลัพธ์ PDF
doc.Save(dataDir);
```

อย่าลืมระบุเส้นทางเต็มและชื่อไฟล์สำหรับ PDF ที่ได้


### ตัวอย่างซอร์สโค้ดสำหรับการตั้งค่า Java Script โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// โหลดไฟล์ PDF อินพุต
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 หลักหลังจุด
// ไม่มีตัวคั่น
// สไตล์ Neg = ลบ
// ไม่มีสกุลเงิน
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// ตั้งค่าฟิลด์ค่าเริ่มต้น
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// บันทึกผลลัพธ์ PDF
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## บทสรุป

ในคู่มือนี้ เราได้เรียนรู้วิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อตั้งค่า JavaScript ในฟิลด์ฟอร์มของเอกสาร PDF โดยทำตามขั้นตอนที่ระบุไว้ คุณสามารถปรับแต่งการดำเนินการ JavaScript เพื่อดำเนินการต่างๆ กับฟิลด์ข้อความได้ อย่าลังเลที่จะสำรวจคุณลักษณะของ Aspose.PDF สำหรับ .NET เพิ่มเติมเพื่อขยายความเป็นไปได้ในการจัดการไฟล์ PDF


### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถใช้ Aspose.PDF สำหรับ .NET เพื่อเพิ่ม JavaScript ลงในองค์ประกอบแบบฟอร์มอื่นๆ เช่น ช่องกาเครื่องหมายและปุ่มตัวเลือกได้หรือไม่

 A: ใช่ Aspose.PDF สำหรับ .NET ช่วยให้คุณเพิ่ม JavaScript ลงในองค์ประกอบแบบฟอร์มต่างๆ ได้ รวมถึงช่องกาเครื่องหมาย ปุ่มตัวเลือก และรายการแบบดรอปดาวน์ คุณสามารถใช้`JavascriptAction` คลาสในการกำหนดการดำเนินการ JavaScript สำหรับองค์ประกอบแบบฟอร์มที่แตกต่างกัน

#### ถาม: เป็นไปได้ไหมที่จะตรวจสอบอินพุตของผู้ใช้โดยใช้ JavaScript ในฟิลด์แบบฟอร์ม?

 A: ใช่ คุณสามารถใช้ JavaScript เพื่อตรวจสอบข้อมูลอินพุตของผู้ใช้ในช่องฟอร์มได้ โดยการกำหนดการดำเนินการของ JavaScript เช่น`OnBlur` หรือ`OnKeystroke` สำหรับฟิลด์ฟอร์ม คุณสามารถตรวจสอบข้อมูลที่ป้อนและแสดงข้อความแสดงข้อผิดพลาดหากจำเป็น

#### ถาม: ฉันสามารถเรียกใช้ฟังก์ชัน JavaScript ที่ซับซ้อนโดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

 A: ใช่ คุณสามารถเรียกใช้ฟังก์ชัน JavaScript ที่ซับซ้อนได้โดยใช้ Aspose.PDF สำหรับ .NET คุณมีความยืดหยุ่นในการกำหนดฟังก์ชัน JavaScript ที่กำหนดเองและเรียกใช้ได้ภายใน`JavascriptAction`.

#### ถาม: Aspose.PDF สำหรับ .NET รองรับเหตุการณ์ JavaScript อื่นๆ นอกเหนือจากที่กล่าวถึงในบทช่วยสอนนี้หรือไม่

 A: ใช่ Aspose.PDF สำหรับ .NET รองรับเหตุการณ์ JavaScript มากมาย รวมถึง`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , และ`OnMouseUp`และอื่นๆ คุณสามารถใช้เหตุการณ์เหล่านี้เพื่อเรียกใช้งานการดำเนินการ JavaScript ตามการโต้ตอบของผู้ใช้

#### ถาม: ฉันสามารถใช้ Aspose.PDF สำหรับ .NET เพื่อแยกโค้ด JavaScript จากเอกสาร PDF ที่มีอยู่ได้หรือไม่

 A: Aspose.PDF สำหรับ .NET ให้ความสามารถในการแยกโค้ด JavaScript จากเอกสาร PDF ที่มีอยู่ คุณสามารถใช้`JavascriptAction` คลาสและวิธีการอื่นที่เกี่ยวข้องในการเข้าถึงและวิเคราะห์การกระทำ JavaScript ในรูปแบบ PDF