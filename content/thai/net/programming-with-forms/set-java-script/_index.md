---
title: ตั้งค่าจาวาสคริปต์
linktitle: ตั้งค่าจาวาสคริปต์
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อตั้งค่า JavaScript ในช่องแบบฟอร์มในไฟล์ PDF
type: docs
weight: 270
url: /th/net/programming-with-forms/set-java-script/
---
ในคู่มือนี้ เราจะอธิบายทีละขั้นตอนวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อกำหนด JavaScript ในช่องแบบฟอร์มของเอกสาร PDF เราจะแสดงวิธีกำหนดค่าการทำงานของ JavaScript เพื่อดำเนินการเฉพาะในช่องข้อความ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งบนระบบของคุณ
- ไลบรารี Aspose.PDF สำหรับ .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose

## ขั้นตอนที่ 1: การกำหนดค่าไดเร็กทอรีเอกสาร

 ขั้นตอนแรกคือการกำหนดค่าไดเร็กทอรีเอกสารซึ่งมีไฟล์ PDF ที่คุณต้องการใช้งาน คุณสามารถใช้`dataDir` ตัวแปรเพื่อระบุเส้นทางไดเรกทอรี

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 2: กำลังโหลดไฟล์ PDF อินพุต

ในขั้นตอนนี้ เราจะโหลดไฟล์ PDF อินพุตโดยใช้ไฟล์`Document` คลาสของ Aspose.PDF

```csharp
// โหลดไฟล์ PDF อินพุต
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

ตรวจสอบให้แน่ใจว่าไฟล์ PDF อินพุตมีอยู่ในไดเร็กทอรีเอกสารที่ระบุ

## ขั้นตอนที่ 3: การเข้าถึงฟิลด์กล่องข้อความ

 หากต้องการใช้ JavaScript กับช่องข้อความเฉพาะ เราต้องเข้าถึงช่องนั้นก่อน ในตัวอย่างนี้ เราถือว่าช่องข้อความชื่อ "textbox1" ใช้`doc.Form["textbox1"]` วิธีการรับที่สอดคล้องกัน`TextBoxField` วัตถุ.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

ตรวจสอบให้แน่ใจว่าฟิลด์ข้อความที่ระบุมีอยู่ในไฟล์ PDF อินพุต

## ขั้นตอนที่ 4: กำหนดค่าการทำงานของ JavaScript

 ตอนนี้เราได้เข้าถึงฟิลด์ข้อความแล้ว เราสามารถกำหนดค่าการทำงานของ JavaScript ที่เชื่อมโยงกับฟิลด์นี้ได้ ในตัวอย่างนี้ เราจะใช้การกระทำสองอย่าง:`OnModifyCharacter` และ`OnFormat` . การกระทำเหล่านี้จะถูกกำหนดโดยใช้`JavascriptAction` วัตถุ

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

อย่าลืมปรับแต่งการทำงานของ JavaScript ตามความต้องการของคุณ

## ขั้นตอนที่ 5: การตั้งค่าฟิลด์เริ่มต้น

ก่อนที่จะบันทึกผลลัพธ์ PDF เราสามารถตั้งค่าเริ่มต้นสำหรับฟิลด์ข้อความได้ ในตัวอย่างนี้ เราจะตั้งค่า "123" สำหรับฟิลด์

```csharp
field.Value = "123";
```

ปรับแต่งค่านี้ตามความต้องการของคุณ

## ขั้นตอนที่ 6: บันทึก PDF ที่เป็นผลลัพธ์

 ตอนนี้เราได้ตั้งค่าฟิลด์ข้อความและการทำงานของ JavaScript เสร็จแล้ว เราสามารถบันทึกไฟล์ PDF ที่เป็นผลลัพธ์ได้โดยใช้`Save` วิธีการของ`Document` ระดับ.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// บันทึก PDF ที่ได้
doc.Save(dataDir);
```

อย่าลืมระบุเส้นทางแบบเต็มและชื่อไฟล์สำหรับ PDF ที่ได้


### ตัวอย่างซอร์สโค้ดสำหรับ Set Java Script โดยใช้ Aspose.PDF สำหรับ .NET 
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
// ตั้งค่าฟิลด์เริ่มต้น
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// บันทึก PDF ผลลัพธ์
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## บทสรุป

ในคู่มือนี้ เราได้เรียนรู้วิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อตั้งค่า JavaScript ในช่องแบบฟอร์มของเอกสาร PDF ด้วยการทำตามขั้นตอนที่อธิบายไว้ คุณสามารถปรับแต่งการทำงานของ JavaScript เพื่อดำเนินการต่างๆ บนช่องข้อความได้ สำรวจฟีเจอร์ของ Aspose.PDF สำหรับ .NET เพิ่มเติมได้ตามสบาย เพื่อขยายความเป็นไปได้ในการจัดการไฟล์ PDF


### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถใช้ Aspose.PDF สำหรับ .NET เพื่อเพิ่ม JavaScript ให้กับองค์ประกอบแบบฟอร์มอื่นๆ เช่น ช่องทำเครื่องหมายและปุ่มตัวเลือกได้หรือไม่

 ตอบ: ได้ Aspose.PDF สำหรับ .NET อนุญาตให้คุณเพิ่ม JavaScript ให้กับองค์ประกอบแบบฟอร์มต่างๆ รวมถึงช่องทำเครื่องหมาย ปุ่มตัวเลือก และรายการแบบเลื่อนลง คุณสามารถใช้`JavascriptAction` คลาสเพื่อกำหนดการกระทำของ JavaScript สำหรับองค์ประกอบแบบฟอร์มต่างๆ

#### ถาม: เป็นไปได้ไหมที่จะตรวจสอบอินพุตของผู้ใช้โดยใช้ JavaScript ในช่องแบบฟอร์ม

 ตอบ: ได้ คุณสามารถใช้ JavaScript เพื่อตรวจสอบการป้อนข้อมูลของผู้ใช้ในช่องแบบฟอร์มได้ โดยกำหนดการกระทำของ JavaScript เช่น`OnBlur` หรือ`OnKeystroke` สำหรับฟิลด์แบบฟอร์ม คุณสามารถตรวจสอบข้อมูลที่ป้อนและแสดงข้อความแสดงข้อผิดพลาดได้หากจำเป็น

#### ถาม: ฉันสามารถรันฟังก์ชัน JavaScript ที่ซับซ้อนโดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

 ตอบ: ได้ คุณสามารถรันฟังก์ชัน JavaScript ที่ซับซ้อนได้โดยใช้ Aspose.PDF สำหรับ .NET คุณมีความยืดหยุ่นในการกำหนดฟังก์ชัน JavaScript ที่กำหนดเองและเรียกฟังก์ชันเหล่านั้นภายใน`JavascriptAction`.

#### ถาม: Aspose.PDF สำหรับ .NET รองรับเหตุการณ์ JavaScript นอกเหนือจากที่กล่าวถึงในบทช่วยสอนนี้หรือไม่

 ตอบ: ใช่ Aspose.PDF สำหรับ .NET รองรับเหตุการณ์ JavaScript ที่หลากหลาย รวมถึง`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , และ`OnMouseUp`, ท่ามกลางคนอื่น ๆ. คุณสามารถใช้เหตุการณ์เหล่านี้เพื่อทริกเกอร์การทำงานของ JavaScript ตามการโต้ตอบของผู้ใช้

#### ถาม: ฉันสามารถใช้ Aspose.PDF สำหรับ .NET เพื่อแยกโค้ด JavaScript จากเอกสาร PDF ที่มีอยู่ได้หรือไม่

 ตอบ: Aspose.PDF สำหรับ .NET ให้ความสามารถในการแยกโค้ด JavaScript จากเอกสาร PDF ที่มีอยู่ คุณสามารถใช้`JavascriptAction` คลาสและวิธีการอื่น ๆ ที่เกี่ยวข้องเพื่อเข้าถึงและวิเคราะห์การทำงานของ JavaScript ในรูปแบบ PDF