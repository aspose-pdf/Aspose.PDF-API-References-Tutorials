---
title: เพิ่ม HTML โดยใช้ DOM และ PDF Overwrite
linktitle: เพิ่ม HTML โดยใช้ DOM และเขียนทับ
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มเนื้อหา HTML โดยใช้ DOM และ PDF เขียนทับใน Aspose.PDF สำหรับ .NET
type: docs
weight: 50
url: /th/net/programming-with-text/add-html-using-dom-and-overwrite/
---
บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการเพิ่มเนื้อหา HTML โดยใช้ DOM (Document Object Model) ใน Aspose.PDF สำหรับ .NET นอกจากนี้ คุณจะได้เรียนรู้วิธีการเขียนทับสไตล์สำหรับเนื้อหา HTML ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ที่ติดตั้งบนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose หรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการเพิ่มเนื้อหา HTML ให้เพิ่มคำสั่งต่อไปนี้โดยใช้คำสั่งที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเร็กทอรีเอกสารและเส้นทางไฟล์เอาต์พุต
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่เก็บเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 4: สร้างวัตถุเอกสารใหม่
 สร้างอินสแตนซ์ใหม่`Document` object โดยการเพิ่มบรรทัดโค้ดต่อไปนี้:

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 5: เพิ่มหน้าลงในเอกสาร
 เพิ่มหน้าใหม่ให้กับเอกสารโดยใช้`Add` วิธีการของ`Pages`ของสะสม. ในโค้ดที่ให้มา หน้าใหม่จะถูกกำหนดให้กับตัวแปร`page`.

```csharp
Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 6: สร้าง HtmlFragment ด้วยเนื้อหา HTML
 ยกตัวอย่าง`HtmlFragment` object และจัดเตรียมเนื้อหา HTML ที่ต้องการ ในโค้ดที่ให้มา เนื้อหา HTML ถูกกำหนดให้กับตัวแปร`title`. คุณสามารถแก้ไขเนื้อหา HTML ได้ตามต้องการ

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## ขั้นตอนที่ 7: เขียนทับสไตล์สำหรับเนื้อหา HTML
 หากต้องการเขียนทับสไตล์ของเนื้อหา HTML คุณสามารถแก้ไขได้`TextState` คุณสมบัติของ`HtmlFragment` วัตถุ. ในโค้ดที่ให้มา ตระกูลฟอนต์จะเปลี่ยนเป็น "Arial" และขนาดฟอนต์ถูกกำหนดเป็น 20

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## ขั้นตอนที่ 8: ตั้งค่าข้อมูลมาร์จิ้น
ปรับระยะขอบด้านล่างและด้านบนของส่วน HTML หากจำเป็น ในโค้ดที่ให้มา ระยะขอบด้านล่างตั้งค่าเป็น 10 และระยะขอบด้านบนตั้งค่าเป็น 400

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## ขั้นตอนที่ 9: เพิ่ม HtmlFragment ลงในเพจ
 เพิ่ม`HtmlFragment` คัดค้านการรวบรวมย่อหน้าของเพจ

```csharp
page.Paragraphs.Add(title);
```

## ขั้นตอนที่ 10: บันทึกเอกสาร PDF
 บันทึกเอกสาร PDF โดยใช้ไฟล์`Save` วิธีการของ`Document` วัตถุ. ระบุเส้นทางของไฟล์เอาต์พุตที่คุณตั้งค่าไว้ในขั้นตอนที่ 3

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับการเพิ่ม HTMLUsing DOM และเขียนทับโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างอินสแตนซ์วัตถุเอกสาร
Document doc = new Document();
// เพิ่มหน้าไปยังคอลเลกชันหน้าของไฟล์ PDF
Page page = doc.Pages.Add();
// สร้างอินสแตนซ์ HtmlFragment ด้วยคอนเทนต์ HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//ตระกูลแบบอักษรจาก 'Verdana' จะถูกรีเซ็ตเป็น 'Arial'
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// ตั้งค่าข้อมูลระยะขอบด้านล่าง
title.Margin.Bottom = 10;
// ตั้งค่าข้อมูลระยะขอบด้านบน
title.Margin.Top = 400;
// เพิ่ม HTML Fragment ให้กับคอลเลกชันย่อหน้าของหน้า
page.Paragraphs.Add(title);
// บันทึกไฟล์ PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// บันทึกไฟล์ PDF
doc.Save(dataDir);
```

## บทสรุป
คุณได้เพิ่มเนื้อหา HTML สำเร็จโดยใช้ DOM ใน Aspose.PDF สำหรับ .NET และเขียนทับสไตล์สำหรับเนื้อหา HTML ขณะนี้ไฟล์ PDF ที่เป็นผลลัพธ์สามารถพบได้ที่เส้นทางไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: บทช่วยสอนนี้เน้นอะไร

ตอบ: บทช่วยสอนนี้ออกแบบมาเพื่อแนะนำคุณตลอดขั้นตอนการเพิ่มเนื้อหา HTML ลงในเอกสาร PDF โดยใช้ Document Object Model (DOM) ใน Aspose.PDF สำหรับ .NET นอกจากนี้ คุณจะได้เรียนรู้วิธีเขียนทับสไตล์สำหรับเนื้อหา HTML ซึ่งช่วยให้คุณสามารถปรับแต่งลักษณะที่ปรากฏได้ บทช่วยสอนให้ตัวอย่างซอร์สโค้ด C# เพื่อสาธิตขั้นตอนที่จำเป็น

#### ถาม: ฉันจำเป็นต้องนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

ตอบ: ในไฟล์โค้ดที่คุณต้องการเพิ่มเนื้อหา HTML ให้นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารและเส้นทางไฟล์เอาต์พุตได้อย่างไร

 ตอบ: ในโค้ด ให้ค้นหาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างออบเจ็กต์ Document ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 4 คุณจะสร้างอินสแตนซ์ใหม่`Document` วัตถุโดยใช้บรรทัดโค้ดต่อไปนี้:

```csharp
Document doc = new Document();
```

#### ถาม: ฉันจะเพิ่มหน้าลงในเอกสารได้อย่างไร

 ตอบ: ในขั้นตอนที่ 5 คุณจะต้องเพิ่มหน้าใหม่ให้กับเอกสารโดยใช้`Add` วิธีการของ`Pages` ของสะสม:

```csharp
Page page = doc.Pages.Add();
```

#### ถาม: ฉันจะตั้งค่าเนื้อหา HTML โดยใช้ DOM ได้อย่างไร

 ตอบ: : ในขั้นตอนที่ 6 คุณจะสร้างไฟล์`HtmlFragment` วัตถุและกำหนดเนื้อหา HTML ที่คุณต้องการ เนื้อหา HTML ถูกกำหนดให้กับตัวแปร`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### ถาม: ฉันจะเขียนทับสไตล์ของเนื้อหา HTML ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 7 คุณจะต้องเขียนทับสไตล์ของเนื้อหา HTML โดยการแก้ไข`TextState` คุณสมบัติของ`HtmlFragment` วัตถุ. ตัวอย่างเช่น คุณสามารถเปลี่ยนตระกูลแบบอักษรเป็น "Arial" และตั้งค่าขนาดแบบอักษรเป็น 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### ถาม: ฉันสามารถปรับระยะขอบของเนื้อหา HTML ได้หรือไม่

ตอบ: ได้ ในขั้นตอนที่ 8 คุณสามารถปรับระยะขอบด้านล่างและด้านบนของส่วน HTML ได้ตามต้องการ:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### ถาม: ฉันจะเพิ่ม HtmlFragment ลงในเอกสาร PDF ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 9 คุณจะต้องเพิ่ม`HtmlFragment` วัตถุ (`title`) ไปยังคอลเลกชันย่อหน้าของหน้า:

```csharp
page.Paragraphs.Add(title);
```

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่ได้ได้อย่างไร

 ตอบ: หลังจากเพิ่มเนื้อหา HTML และปรับแต่งสไตล์แล้ว ให้ใช้ไฟล์`Save` วิธีการของ`Document` วัตถุเพื่อบันทึกเอกสาร PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### ถาม: สิ่งสำคัญที่ได้รับจากบทช่วยสอนนี้คืออะไร

ตอบ: เมื่อทำตามบทช่วยสอนนี้ คุณได้เรียนรู้วิธีรวมเนื้อหา HTML โดยใช้ Document Object Model (DOM) ใน Aspose.PDF สำหรับ .NET ได้สำเร็จ นอกจากนี้ คุณยังสามารถเขียนทับสไตล์เพื่อปรับแต่งลักษณะที่ปรากฏของเนื้อหา HTML ภายในเอกสาร PDF ที่ได้