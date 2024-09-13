---
title: กำหนดการแบ่งบรรทัดในไฟล์ PDF
linktitle: กำหนดการแบ่งบรรทัดในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการกำหนดเส้นแบ่งบรรทัดในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 130
url: /th/net/programming-with-text/determine-line-break/
---
บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนในการกำหนดการแบ่งบรรทัดในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ติดตั้งอยู่บนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose อย่างเป็นทางการหรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการกำหนดการแบ่งบรรทัด ให้เพิ่มคำสั่ง using ต่อไปนี้ที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using System.IO;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเรกทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณเก็บเอกสารไว้

## ขั้นตอนที่ 4: สร้างอินสแตนซ์เอกสารใหม่
 สร้างอินสแตนซ์ใหม่`Document` วัตถุโดยการเพิ่มบรรทัดโค้ดดังต่อไปนี้:

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 5: เพิ่มหน้าลงในเอกสาร
 เพิ่มหน้าใหม่ลงในเอกสารโดยใช้`Add` วิธีการของ`Pages` คอลเลกชัน ในโค้ดที่ให้มา หน้าใหม่จะถูกกำหนดให้กับตัวแปร`page`.

```csharp
Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 6: เพิ่มข้อความบางส่วนพร้อมแบ่งบรรทัด
สร้างลูปเพื่อเพิ่มข้อความหลายส่วนลงในหน้า โดยแต่ละส่วนประกอบด้วยย่อหน้าพร้อมแบ่งบรรทัด

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## ขั้นตอนที่ 7: บันทึกเอกสาร PDF และแยกข้อมูลแบ่งบรรทัด
 บันทึกเอกสาร PDF โดยใช้`Save` วิธีการของ`Document` วัตถุ จากนั้นแยกข้อมูลการแบ่งบรรทัดโดยใช้`GetNotifications` วิธีการของหน้าที่ต้องการ

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการกำหนดการแบ่งบรรทัดโดยใช้ Aspose.PDF สำหรับ .NET 
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
คุณได้กำหนดการแบ่งบรรทัดในเอกสาร PDF สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ข้อมูลการแบ่งบรรทัดได้รับการแยกและบันทึกลงในไฟล์ข้อความ

### คำถามที่พบบ่อย

#### ถาม: บทช่วยสอนนี้เน้นอะไรเป็นหลัก?

A: บทช่วยสอนนี้เน้นที่การแนะนำคุณตลอดกระบวนการในการกำหนดการแบ่งบรรทัดในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็นในการบรรลุสิ่งนี้

#### ถาม: ฉันควรนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้?

ก: ในไฟล์โค้ดที่คุณต้องการกำหนดการแบ่งบรรทัด นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร?

 ก: ในโค้ด ให้หาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างอินสแตนซ์เอกสารใหม่ได้อย่างไร

 ก: ในขั้นตอนที่ 4 คุณจะสร้างอินสแตนซ์ใหม่`Document` วัตถุโดยใช้โค้ดที่ให้มา

#### ถาม: ฉันจะเพิ่มหน้าลงในเอกสารได้อย่างไร

 ก: ในขั้นตอนที่ 5 คุณจะเพิ่มหน้าใหม่ลงในเอกสารโดยใช้`Add` วิธีการของ`Pages` ของสะสม.

#### ถาม: ฉันจะเพิ่มข้อความบางส่วนพร้อมแบ่งบรรทัดได้อย่างไร

ก: ในขั้นตอนที่ 6 คุณจะสร้างลูปเพื่อเพิ่มข้อความหลายส่วนลงในหน้า โดยแต่ละส่วนประกอบด้วยย่อหน้าพร้อมแบ่งบรรทัด

#### ถาม: ฉันจะบันทึกเอกสาร PDF และแยกข้อมูลแบ่งบรรทัดได้อย่างไร

 ก: ในขั้นตอนที่ 7 คุณจะบันทึกเอกสาร PDF โดยใช้`Save` วิธีการของ`Document` วัตถุ จากนั้นคุณจะแยกข้อมูลการแบ่งบรรทัดโดยใช้`GetNotifications` วิธีการของหน้าที่ต้องการและบันทึกลงในไฟล์ข้อความ

#### ถาม: วัตถุประสงค์ของข้อมูลแบ่งบรรทัดที่ถูกแยกออกมาคืออะไร

A: ข้อมูลการแบ่งบรรทัดที่แยกออกมาจะให้รายละเอียดเกี่ยวกับการแบ่งบรรทัดและการแจ้งเตือนที่มีอยู่ในเอกสาร PDF ซึ่งอาจมีประโยชน์ในการวิเคราะห์และทำความเข้าใจว่าข้อความและย่อหน้าต่างๆ มีโครงสร้างอย่างไรในเอกสาร

#### ถาม: สิ่งสำคัญที่สุดที่ได้จากบทช่วยสอนนี้คืออะไร?

A: เมื่อทำตามบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการกำหนดเส้นแบ่งบรรทัดในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้ความรู้เหล่านี้เพื่อแยกและวิเคราะห์ข้อมูลเส้นแบ่งบรรทัดจากไฟล์ PDF ได้ด้วยโปรแกรม