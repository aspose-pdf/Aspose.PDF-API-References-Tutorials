---
title: เพิ่มเส้นขอบข้อความในไฟล์ PDF
linktitle: เพิ่มเส้นขอบข้อความในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการเพิ่มเส้นขอบข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 70
url: /th/net/programming-with-text/add-text-border/
---
บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการเพิ่มเส้นขอบข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ติดตั้งอยู่บนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose อย่างเป็นทางการหรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการเพิ่มเส้นขอบข้อความ ให้เพิ่มคำสั่ง using ต่อไปนี้ที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเรกทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณเก็บเอกสารไว้

## ขั้นตอนที่ 4: สร้างวัตถุเอกสารใหม่
 สร้างอินสแตนซ์ใหม่`Document` วัตถุโดยการเพิ่มบรรทัดโค้ดดังต่อไปนี้:

```csharp
Document pdfDocument = new Document();
```

## ขั้นตอนที่ 5: เพิ่มหน้าลงในเอกสาร
 เพิ่มหน้าใหม่ลงในเอกสารโดยใช้`Add` วิธีการของ`Pages` คอลเลกชัน ในโค้ดที่ให้มา หน้าใหม่จะถูกกำหนดให้กับตัวแปร`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## ขั้นตอนที่ 6: สร้าง TextFragment
 สร้าง`TextFragment`วัตถุและจัดเตรียมข้อความที่ต้องการ กำหนดตำแหน่งของส่วนข้อความโดยใช้`Position` คุณสมบัติ ในโค้ดที่ให้มา ข้อความจะถูกตั้งเป็น "ข้อความหลัก" และอยู่ในตำแหน่ง (100, 600) บนหน้า

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## ขั้นตอนที่ 7: ตั้งค่าคุณสมบัติข้อความ
ปรับแต่งคุณสมบัติของข้อความ เช่น ขนาดตัวอักษร ประเภทของตัวอักษร สีพื้นหลัง สีพื้นหน้า ฯลฯ ในโค้ดที่ให้ไว้ คุณสมบัติต่างๆ เช่น ขนาดตัวอักษร แบบอักษร สีพื้นหลัง สีพื้นหน้า และสีเส้น จะถูกตั้งค่าให้กับส่วนข้อความ

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## ขั้นตอนที่ 8: เปิดใช้งานเส้นขอบข้อความ
 หากต้องการเปิดใช้งานเส้นขอบข้อความ ให้ตั้งค่า`DrawTextRectangleBorder` คุณสมบัติของชิ้นส่วนข้อความ`TextState` ถึง`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## ขั้นตอนที่ 9: เพิ่ม TextFragment ลงในหน้า
 ใช้`TextBuilder` ชั้นเรียนที่จะเพิ่ม`TextFragment` คัดค้านหน้าดังกล่าว

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## ขั้นตอนที่ 10: บันทึกเอกสาร PDF
 บันทึกเอกสาร PDF โดยใช้`Save` วิธีการของ`Document` วัตถุ ระบุเส้นทางไฟล์เอาท์พุตที่คุณตั้งค่าไว้ในขั้นตอนที่ 3

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### ตัวอย่างโค้ดที่มาสำหรับการเพิ่มเส้นขอบข้อความโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างวัตถุเอกสารใหม่
Document pdfDocument = new Document();
// รับหน้าเฉพาะ
Page pdfPage = (Page)pdfDocument.Pages.Add();
// สร้างข้อความส่วนย่อย
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// ตั้งค่าคุณสมบัติข้อความ
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// ตั้งค่าคุณสมบัติ StrokingColor สำหรับการวาดเส้นขอบ (การขีดเส้น) รอบ ๆ ข้อความสี่เหลี่ยม
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// ตั้งค่าคุณสมบัติ DrawTextRectangleBorder เป็น true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// บันทึกเอกสาร
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## บทสรุป
คุณได้เพิ่มเส้นขอบข้อความลงในเอกสาร PDF สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้สามารถค้นหาไฟล์ PDF ที่ได้ในเส้นทางไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: บทช่วยสอนนี้เน้นอะไรเป็นหลัก?

A: บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการเพิ่มเส้นขอบข้อความลงในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็นในการบรรลุขั้นตอนนี้

#### ถาม: ฉันต้องนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

ก: ในไฟล์โค้ดที่คุณต้องการเพิ่มเส้นขอบข้อความ นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร?

 ก: ในโค้ด ให้ระบุตำแหน่งบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างวัตถุเอกสารได้อย่างไร

 ก: ในขั้นตอนที่ 4 คุณจะสร้างอินสแตนซ์ใหม่`Document` วัตถุที่ใช้บรรทัดโค้ดต่อไปนี้:

```csharp
Document pdfDocument = new Document();
```

#### ถาม: ฉันจะเพิ่มหน้าลงในเอกสารได้อย่างไร

 ก: ในขั้นตอนที่ 5 คุณจะเพิ่มหน้าใหม่ลงในเอกสารโดยใช้`Add` วิธีการของ`Pages` ของสะสม:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### ถาม: ฉันจะสร้าง TextFragment และกำหนดตำแหน่งได้อย่างไร

 A: ในขั้นตอนที่ 6 คุณจะสร้าง`TextFragment` วัตถุและกำหนดตำแหน่งบนหน้าโดยใช้`Position` คุณสมบัติ:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### ถาม: ฉันจะปรับแต่งคุณสมบัติข้อความ รวมถึงขอบข้อความได้อย่างไร

ก: ในขั้นตอนที่ 7 คุณจะปรับแต่งคุณสมบัติข้อความต่างๆ เช่น ขนาดแบบอักษร ประเภทแบบอักษร สีพื้นหลัง สีพื้นหน้า และขอบข้อความ:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### ถาม: ฉันจะเพิ่ม TextFragment ลงในเอกสาร PDF ได้อย่างไร

 A: ในขั้นตอนที่ 9 คุณจะใช้`TextBuilder` ชั้นเรียนที่จะเพิ่ม`TextFragment` คัดค้านหน้า:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### ถาม: ฉันจะบันทึกเอกสาร PDF ผลลัพธ์ได้อย่างไร

ก: หลังจากเพิ่มข้อความพร้อมขอบแล้ว ให้ใช้`Save` วิธีการของ`Document` วัตถุที่จะบันทึกเอกสาร PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### ถาม: สิ่งสำคัญที่สุดที่ได้จากบทช่วยสอนนี้คืออะไร?

A: เมื่อทำตามบทช่วยสอนนี้แล้ว คุณจะเรียนรู้วิธีการปรับปรุงเอกสาร PDF ของคุณโดยการเพิ่มเส้นขอบข้อความโดยใช้ Aspose.PDF สำหรับ .NET ได้แล้ว วิธีนี้มีประโยชน์อย่างยิ่งในการเน้นเนื้อหาข้อความเฉพาะภายในไฟล์ PDF ของคุณ