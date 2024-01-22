---
title: เพิ่มเส้นขอบข้อความในไฟล์ PDF
linktitle: เพิ่มเส้นขอบข้อความในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มเส้นขอบข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 70
url: /th/net/programming-with-text/add-text-border/
---
บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนการเพิ่มเส้นขอบข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ที่ติดตั้งบนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose หรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการเพิ่มเส้นขอบข้อความ ให้เพิ่มคำสั่งต่อไปนี้โดยใช้คำสั่งที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเร็กทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่เก็บเอกสารของคุณ

## ขั้นตอนที่ 4: สร้างวัตถุเอกสารใหม่
 สร้างอินสแตนซ์ใหม่`Document` object โดยการเพิ่มบรรทัดโค้ดต่อไปนี้:

```csharp
Document pdfDocument = new Document();
```

## ขั้นตอนที่ 5: เพิ่มหน้าลงในเอกสาร
 เพิ่มหน้าใหม่ให้กับเอกสารโดยใช้`Add` วิธีการของ`Pages`ของสะสม. ในโค้ดที่ให้มา หน้าใหม่จะถูกกำหนดให้กับตัวแปร`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## ขั้นตอนที่ 6: สร้าง TextFragment
 สร้างก`TextFragment` วัตถุและระบุข้อความที่ต้องการ กำหนดตำแหน่งของส่วนของข้อความโดยใช้`Position` คุณสมบัติ. ในโค้ดที่ให้มา ข้อความจะถูกตั้งค่าเป็น "ข้อความหลัก" และอยู่ที่ (100, 600) บนหน้า

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## ขั้นตอนที่ 7: ตั้งค่าคุณสมบัติข้อความ
ปรับแต่งคุณสมบัติข้อความ เช่น ขนาดแบบอักษร ประเภทแบบอักษร สีพื้นหลัง สีพื้นหน้า ฯลฯ ในโค้ดที่ให้มา คุณสมบัติ เช่น ขนาดแบบอักษร แบบอักษร สีพื้นหลัง สีพื้นหน้า และสีเส้นขีด จะถูกตั้งค่าสำหรับส่วนของข้อความ

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## ขั้นตอนที่ 8: เปิดใช้งานเส้นขอบข้อความ
 หากต้องการเปิดใช้งานเส้นขอบข้อความ ให้ตั้งค่า`DrawTextRectangleBorder`คุณสมบัติของส่วนของข้อความ`TextState` ถึง`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## ขั้นตอนที่ 9: เพิ่ม TextFragment ลงในเพจ
 ใช้`TextBuilder` คลาสที่จะเพิ่ม`TextFragment` คัดค้านหน้า

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## ขั้นตอนที่ 10: บันทึกเอกสาร PDF
 บันทึกเอกสาร PDF โดยใช้ไฟล์`Save` วิธีการของ`Document` วัตถุ. ระบุเส้นทางของไฟล์เอาต์พุตที่คุณตั้งค่าไว้ในขั้นตอนที่ 3

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับเพิ่มเส้นขอบข้อความโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างวัตถุเอกสารใหม่
Document pdfDocument = new Document();
// รับเฉพาะหน้า
Page pdfPage = (Page)pdfDocument.Pages.Add();
// สร้างส่วนของข้อความ
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// ตั้งค่าคุณสมบัติข้อความ
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// ตั้งค่าคุณสมบัติ StrokingColor สำหรับการวาดเส้นขอบ (การลาก) รอบสี่เหลี่ยมข้อความ
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// ตั้งค่าคุณสมบัติ DrawTextRectangleBorder เป็นจริง
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// บันทึกเอกสาร
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## บทสรุป
คุณได้เพิ่มเส้นขอบข้อความลงในเอกสาร PDF ของคุณสำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ขณะนี้ไฟล์ PDF ที่เป็นผลลัพธ์สามารถพบได้ที่เส้นทางไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: อะไรคือจุดสนใจหลักของบทช่วยสอนนี้

ตอบ: บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการเพิ่มเส้นขอบข้อความให้กับไฟล์ PDF โดยใช้ Aspose.PDF สำหรับไลบรารี .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็นเพื่อให้บรรลุเป้าหมายนี้

#### ถาม: ฉันจำเป็นต้องนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

ตอบ: ในไฟล์โค้ดที่คุณต้องการเพิ่มเส้นขอบข้อความ ให้นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร

 ตอบ: ในโค้ด ให้ค้นหาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างออบเจ็กต์ Document ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 4 คุณจะสร้างอินสแตนซ์ใหม่`Document` วัตถุโดยใช้บรรทัดโค้ดต่อไปนี้:

```csharp
Document pdfDocument = new Document();
```

#### ถาม: ฉันจะเพิ่มหน้าลงในเอกสารได้อย่างไร

 ตอบ: ในขั้นตอนที่ 5 คุณจะต้องเพิ่มหน้าใหม่ให้กับเอกสารโดยใช้`Add` วิธีการของ`Pages` ของสะสม:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### ถาม: ฉันจะสร้าง TextFragment และกำหนดตำแหน่งได้อย่างไร

 ตอบ: ในขั้นตอนที่ 6 คุณจะสร้างไฟล์`TextFragment`วัตถุและกำหนดตำแหน่งบนเพจโดยใช้`Position` คุณสมบัติ:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### ถาม: ฉันจะปรับแต่งคุณสมบัติข้อความ รวมถึงเส้นขอบข้อความได้อย่างไร

ตอบ: ในขั้นตอนที่ 7 คุณจะต้องปรับแต่งคุณสมบัติข้อความต่างๆ เช่น ขนาดแบบอักษร ประเภทแบบอักษร สีพื้นหลัง สีพื้นหน้า และเส้นขอบข้อความ:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### ถาม: ฉันจะเพิ่ม TextFragment ลงในเอกสาร PDF ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 9 คุณจะใช้`TextBuilder` คลาสที่จะเพิ่ม`TextFragment` คัดค้านหน้า:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่ได้ได้อย่างไร

 ตอบ: หลังจากเพิ่มข้อความที่มีเส้นขอบแล้ว ให้ใช้`Save` วิธีการของ`Document` วัตถุเพื่อบันทึกเอกสาร PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### ถาม: สิ่งสำคัญที่ได้รับจากบทช่วยสอนนี้คืออะไร

ตอบ: เมื่อทำตามบทช่วยสอนนี้ คุณได้เรียนรู้วิธีปรับปรุงเอกสาร PDF ของคุณโดยการเพิ่มเส้นขอบข้อความโดยใช้ Aspose.PDF สำหรับ .NET ได้สำเร็จ สิ่งนี้มีประโยชน์อย่างยิ่งในการเน้นเนื้อหาข้อความเฉพาะภายในไฟล์ PDF ของคุณ