---
title: เพิ่ม HTML โดยใช้ DOM และ PDF Overwrite
linktitle: เพิ่ม HTML โดยใช้ DOM และเขียนทับ
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการเพิ่มเนื้อหา HTML โดยใช้ DOM และการเขียนทับ PDF ใน Aspose.PDF สำหรับ .NET
type: docs
weight: 50
url: /th/net/programming-with-text/add-html-using-dom-and-overwrite/
---
บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการเพิ่มเนื้อหา HTML โดยใช้ DOM (Document Object Model) ใน Aspose.PDF สำหรับ .NET นอกจากนี้ คุณจะได้เรียนรู้วิธีการเขียนทับรูปแบบสำหรับเนื้อหา HTML โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ติดตั้งอยู่บนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose อย่างเป็นทางการหรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการเพิ่มเนื้อหา HTML ให้เพิ่มคำสั่งต่อไปนี้ที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเรกทอรีเอกสารและเส้นทางไฟล์เอาท์พุต
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณเก็บเอกสารไว้

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 4: สร้างวัตถุเอกสารใหม่
 สร้างอินสแตนซ์ใหม่`Document` วัตถุโดยการเพิ่มบรรทัดโค้ดดังต่อไปนี้:

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 5: เพิ่มหน้าลงในเอกสาร
 เพิ่มหน้าใหม่ลงในเอกสารโดยใช้`Add` วิธีการของ`Pages`คอลเลกชัน ในโค้ดที่ให้มา หน้าใหม่จะถูกกำหนดให้กับตัวแปร`page`.

```csharp
Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 6: สร้าง HtmlFragment ด้วยเนื้อหา HTML
 สร้างอินสแตนซ์`HtmlFragment` วัตถุและจัดเตรียมเนื้อหา HTML ที่ต้องการ ในโค้ดที่ให้มา เนื้อหา HTML จะถูกกำหนดให้กับตัวแปร`title`คุณสามารถปรับเปลี่ยนเนื้อหา HTML ตามต้องการ

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## ขั้นตอนที่ 7: เขียนทับรูปแบบสำหรับเนื้อหา HTML
 หากต้องการเขียนทับรูปแบบของเนื้อหา HTML คุณสามารถแก้ไข`TextState` คุณสมบัติของ`HtmlFragment` วัตถุ ในโค้ดที่ให้มา ฟอนต์แฟมิลีถูกเปลี่ยนเป็น "Arial" และขนาดฟอนต์ถูกตั้งเป็น 20

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## ขั้นตอนที่ 8: ตั้งค่าข้อมูลระยะขอบ
ปรับระยะขอบล่างและบนของส่วน HTML หากจำเป็น ในโค้ดที่ให้มา ระยะขอบล่างถูกตั้งค่าเป็น 10 และระยะขอบบนถูกตั้งค่าเป็น 400

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## ขั้นตอนที่ 9: เพิ่ม HtmlFragment ลงในเพจ
 เพิ่ม`HtmlFragment` คัดค้านการรวบรวมย่อหน้าของหน้า

```csharp
page.Paragraphs.Add(title);
```

## ขั้นตอนที่ 10: บันทึกเอกสาร PDF
 บันทึกเอกสาร PDF โดยใช้`Save` วิธีการของ`Document` วัตถุ ระบุเส้นทางไฟล์เอาท์พุตที่คุณตั้งค่าไว้ในขั้นตอนที่ 3

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับ Add HTML การใช้ DOM และการเขียนทับโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างอินสแตนซ์ของวัตถุเอกสาร
Document doc = new Document();
// เพิ่มหน้าลงในคอลเลคชันหน้าของไฟล์ PDF
Page page = doc.Pages.Add();
// สร้างอินสแตนซ์ HtmlFragment ด้วยเนื้อหา HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//ฟอนต์แฟมิลี่จาก 'Verdana' จะถูกรีเซ็ตเป็น 'Arial'
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// ตั้งค่าข้อมูลระยะขอบล่าง
title.Margin.Bottom = 10;
// ตั้งค่าข้อมูลระยะขอบบน
title.Margin.Top = 400;
// เพิ่ม HTML Fragment ลงในคอลเล็กชั่นย่อหน้าของหน้า
page.Paragraphs.Add(title);
// บันทึกไฟล์ PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// บันทึกไฟล์ PDF
doc.Save(dataDir);
```

## บทสรุป
คุณได้เพิ่มเนื้อหา HTML โดยใช้ DOM ใน Aspose.PDF สำหรับ .NET สำเร็จแล้ว และเขียนทับรูปแบบสำหรับเนื้อหา HTML ไฟล์ PDF ที่ได้จะพบได้ในเส้นทางไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: บทช่วยสอนนี้เน้นอะไร?

A: บทช่วยสอนนี้ได้รับการออกแบบมาเพื่อแนะนำคุณเกี่ยวกับขั้นตอนการเพิ่มเนื้อหา HTML ลงในเอกสาร PDF โดยใช้ Document Object Model (DOM) ใน Aspose.PDF สำหรับ .NET นอกจากนี้ คุณจะได้เรียนรู้วิธีการเขียนทับรูปแบบสำหรับเนื้อหา HTML ซึ่งจะช่วยให้คุณปรับแต่งลักษณะที่ปรากฏของเนื้อหาได้ บทช่วยสอนนี้ให้ข้อมูลโค้ดต้นฉบับของ C# เพื่อสาธิตขั้นตอนที่จำเป็น

#### ถาม: ฉันต้องนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

ก: ในไฟล์โค้ดที่คุณต้องการเพิ่มเนื้อหา HTML นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารและเส้นทางไฟล์เอาต์พุตได้อย่างไร

 ก: ในโค้ด ให้ระบุตำแหน่งบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างวัตถุเอกสารได้อย่างไร

 ก: ในขั้นตอนที่ 4 คุณจะสร้างอินสแตนซ์ใหม่`Document` วัตถุที่ใช้บรรทัดโค้ดต่อไปนี้:

```csharp
Document doc = new Document();
```

#### ถาม: ฉันจะเพิ่มหน้าลงในเอกสารได้อย่างไร

 ก: ในขั้นตอนที่ 5 คุณจะเพิ่มหน้าใหม่ลงในเอกสารโดยใช้`Add` วิธีการของ`Pages` ของสะสม:

```csharp
Page page = doc.Pages.Add();
```

#### ถาม: ฉันจะตั้งค่าเนื้อหา HTML โดยใช้ DOM ได้อย่างไร

 A- ในขั้นตอนที่ 6 คุณจะสร้าง`HtmlFragment` วัตถุและกำหนดเนื้อหา HTML ที่คุณต้องการให้กับวัตถุนั้น เนื้อหา HTML จะถูกกำหนดให้กับตัวแปร`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### ถาม: ฉันจะเขียนทับรูปแบบของเนื้อหา HTML ได้อย่างไร

 ก: ในขั้นตอนที่ 7 คุณจะเขียนทับรูปแบบของเนื้อหา HTML โดยการแก้ไข`TextState` คุณสมบัติของ`HtmlFragment` วัตถุ ตัวอย่างเช่น คุณสามารถเปลี่ยนแบบอักษรเป็น "Arial" และตั้งขนาดแบบอักษรเป็น 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### ถาม: ฉันสามารถปรับระยะขอบของเนื้อหา HTML ได้หรือไม่?

A: ใช่ ในขั้นตอนที่ 8 คุณสามารถปรับระยะขอบด้านล่างและด้านบนของส่วน HTML ได้ตามต้องการ:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### ถาม: ฉันจะเพิ่ม HtmlFragment ลงในเอกสาร PDF ได้อย่างไร

 ก: ในขั้นตอนที่ 9 คุณจะเพิ่ม`HtmlFragment` วัตถุ (`title`) ไปยังคอลเลกชันย่อหน้าของหน้า:

```csharp
page.Paragraphs.Add(title);
```

#### ถาม: ฉันจะบันทึกเอกสาร PDF ผลลัพธ์ได้อย่างไร

 A: หลังจากเพิ่มเนื้อหา HTML และปรับแต่งรูปแบบแล้ว ให้ใช้`Save` วิธีการของ`Document` วัตถุที่จะบันทึกเอกสาร PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### ถาม: สิ่งสำคัญที่ได้จากบทช่วยสอนนี้คืออะไร?

A: เมื่อทำตามบทช่วยสอนนี้แล้ว คุณจะเรียนรู้วิธีการผสานรวมเนื้อหา HTML โดยใช้ Document Object Model (DOM) ใน Aspose.PDF สำหรับ .NET สำเร็จแล้ว นอกจากนี้ คุณยังได้รับความสามารถในการเขียนทับรูปแบบเพื่อปรับแต่งลักษณะของเนื้อหา HTML ภายในเอกสาร PDF ที่ได้