---
title: กำหนดตัวแบ่งบรรทัดในไฟล์ PDF
linktitle: กำหนดตัวแบ่งบรรทัดในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีกำหนดตัวขึ้นบรรทัดใหม่ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 130
url: /th/net/programming-with-text/determine-line-break/
---
บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการกำหนดตัวขึ้นบรรทัดใหม่ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ที่ติดตั้งบนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose หรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการกำหนดตัวขึ้นบรรทัดใหม่ ให้เพิ่มคำสั่งต่อไปนี้โดยใช้คำสั่งที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using System.IO;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเร็กทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่เก็บเอกสารของคุณ

## ขั้นตอนที่ 4: สร้างอินสแตนซ์เอกสารใหม่
 สร้างอินสแตนซ์ใหม่`Document` object โดยการเพิ่มบรรทัดโค้ดต่อไปนี้:

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 5: เพิ่มหน้าลงในเอกสาร
 เพิ่มหน้าใหม่ให้กับเอกสารโดยใช้`Add` วิธีการของ`Pages`ของสะสม. ในโค้ดที่ให้มา หน้าใหม่จะถูกกำหนดให้กับตัวแปร`page`.

```csharp
Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 6: เพิ่มส่วนของข้อความด้วยการขึ้นบรรทัดใหม่
สร้างการวนซ้ำเพื่อเพิ่มส่วนของข้อความหลายส่วนลงในหน้า โดยแต่ละส่วนจะมีย่อหน้าที่มีการขึ้นบรรทัดใหม่

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## ขั้นตอนที่ 7: บันทึกเอกสาร PDF และแยกข้อมูลตัวแบ่งบรรทัด
 บันทึกเอกสาร PDF โดยใช้ไฟล์`Save` วิธีการของ`Document` วัตถุ. จากนั้นแยกข้อมูลตัวแบ่งบรรทัดโดยใช้`GetNotifications` วิธีการหน้าที่ต้องการ

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### ตัวอย่างซอร์สโค้ดสำหรับกำหนดตัวแบ่งบรรทัดโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
	text.TextState.FontSize = 20;
	page.Paragraphs.Add(text);
}
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

## บทสรุป
คุณกำหนดตัวแบ่งบรรทัดในเอกสาร PDF ได้สำเร็จโดยใช้ Aspose.PDF สำหรับ .NET ข้อมูลตัวแบ่งบรรทัดถูกแยกและบันทึกลงในไฟล์ข้อความ

### คำถามที่พบบ่อย

#### ถาม: อะไรคือจุดสนใจหลักของบทช่วยสอนนี้

ตอบ: บทช่วยสอนนี้เน้นที่การแนะนำคุณตลอดกระบวนการกำหนดตัวขึ้นบรรทัดใหม่ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับไลบรารี .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็นเพื่อให้บรรลุเป้าหมายนี้

#### ถาม: ฉันควรนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

ตอบ: ในไฟล์โค้ดที่คุณต้องการกำหนดตัวแบ่งบรรทัด ให้นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร

 ตอบ: ในโค้ด ให้ค้นหาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างอินสแตนซ์เอกสารใหม่ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 4 คุณจะสร้างอินสแตนซ์ใหม่`Document` วัตถุโดยใช้รหัสที่ให้มา

#### ถาม: ฉันจะเพิ่มหน้าลงในเอกสารได้อย่างไร

 ตอบ: ในขั้นตอนที่ 5 คุณจะต้องเพิ่มหน้าใหม่ให้กับเอกสารโดยใช้`Add` วิธีการของ`Pages` ของสะสม.

#### ถาม: ฉันจะเพิ่มส่วนของข้อความด้วยการขึ้นบรรทัดใหม่ได้อย่างไร

ตอบ: ในขั้นตอนที่ 6 คุณจะต้องสร้างวงวนเพื่อเพิ่มส่วนของข้อความหลายส่วนลงในหน้า โดยแต่ละส่วนจะมีย่อหน้าที่มีการขึ้นบรรทัดใหม่

#### ถาม: ฉันจะบันทึกเอกสาร PDF และแยกข้อมูลตัวแบ่งบรรทัดได้อย่างไร

 ตอบ: ในขั้นตอนที่ 7 คุณจะต้องบันทึกเอกสาร PDF โดยใช้นามสกุลไฟล์`Save` วิธีการของ`Document` วัตถุ. จากนั้น คุณจะแยกข้อมูลตัวแบ่งบรรทัดโดยใช้`GetNotifications` ของหน้าที่ต้องการและบันทึกลงในไฟล์ข้อความ

#### ถาม: จุดประสงค์ของข้อมูลตัวแบ่งบรรทัดที่แยกออกมาคืออะไร

ตอบ: ข้อมูลตัวแบ่งบรรทัดที่แยกออกมาจะให้รายละเอียดเกี่ยวกับการขึ้นบรรทัดใหม่และการแจ้งเตือนที่แสดงในเอกสาร PDF สิ่งนี้มีประโยชน์สำหรับการวิเคราะห์และทำความเข้าใจว่าข้อความและย่อหน้ามีโครงสร้างอย่างไรในเอกสาร

#### ถาม: สิ่งสำคัญที่ได้รับจากบทช่วยสอนนี้คืออะไร

ตอบ: เมื่อทำตามบทช่วยสอนนี้ คุณได้เรียนรู้วิธีกำหนดการขึ้นบรรทัดใหม่ในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้ความรู้นี้เพื่อแยกและวิเคราะห์ข้อมูลตัวแบ่งบรรทัดจากไฟล์ PDF โดยทางโปรแกรม