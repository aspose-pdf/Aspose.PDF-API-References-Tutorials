---
title: แท็บหยุดแบบกำหนดเองในไฟล์ PDF
linktitle: แท็บหยุดแบบกำหนดเองในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการสร้างแท็บหยุดแบบกำหนดเองในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 120
url: /th/net/programming-with-text/custom-tab-stops/
---

บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการสร้างแท็บหยุดแบบกำหนดเองในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็น

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ติดตั้งอยู่บนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose อย่างเป็นทางการหรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการสร้างแท็บหยุดแบบกำหนดเอง ให้เพิ่มคำสั่ง using ต่อไปนี้ที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเรกทอรีเอกสาร
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณเก็บเอกสารไว้

## ขั้นตอนที่ 4: สร้างอินสแตนซ์เอกสารใหม่
 สร้างอินสแตนซ์ใหม่`Document` วัตถุโดยการเพิ่มบรรทัดโค้ดดังต่อไปนี้:

```csharp
Document _pdfdocument = new Document();
```

## ขั้นตอนที่ 5: เพิ่มหน้าลงในเอกสาร
 เพิ่มหน้าใหม่ลงในเอกสารโดยใช้`Add` วิธีการของ`Pages` คอลเลกชัน ในโค้ดที่ให้มา หน้าใหม่จะถูกกำหนดให้กับตัวแปร`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## ขั้นตอนที่ 6: สร้างแท็บหยุดแบบกำหนดเอง
 สร้าง`TabStops` วัตถุและเพิ่มแท็บสต็อปแบบกำหนดเอง ตั้งค่าประเภทการจัดตำแหน่งและประเภทผู้นำสำหรับแท็บสต็อปแต่ละอัน

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## ขั้นตอนที่ 7: สร้างส่วนข้อความที่มีแท็บหยุด
 สร้าง`TextFragment` วัตถุและส่งแท็บหยุดแบบกำหนดเองให้กับวัตถุเหล่านั้น ใช้ตัวอักษรพิเศษ`#$TAB` เพื่อระบุตำแหน่งแท็บหยุดภายในข้อความ

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## ขั้นตอนที่ 8: บันทึกเอกสาร PDF
 บันทึกเอกสาร PDF โดยใช้`Save` วิธีการของ`Document` วัตถุ.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### ตัวอย่างโค้ดที่มาสำหรับ Custom Tab Stops โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## บทสรุป
คุณได้สร้างเอกสาร PDF พร้อมแท็บหยุดแบบกำหนดเองโดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว ตอนนี้สามารถพบไฟล์ PDF ที่ได้ในเส้นทางไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: บทช่วยสอนนี้เน้นอะไร?

A: บทช่วยสอนนี้เน้นที่การแนะนำคุณตลอดกระบวนการสร้างแท็บหยุดแบบกำหนดเองในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็นในการบรรลุสิ่งนี้

#### ถาม: ฉันควรนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้?

A: ในไฟล์โค้ดที่คุณต้องการสร้างแท็บหยุดแบบกำหนดเอง โปรดนำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารได้อย่างไร?

 ก: ในโค้ด ให้หาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างอินสแตนซ์เอกสารใหม่ได้อย่างไร

 ก: ในขั้นตอนที่ 4 คุณจะสร้างอินสแตนซ์ใหม่`Document` วัตถุโดยใช้โค้ดที่ให้มา

#### ถาม: ฉันจะเพิ่มหน้าลงในเอกสารได้อย่างไร

 ก: ในขั้นตอนที่ 5 คุณจะเพิ่มหน้าใหม่ลงในเอกสารโดยใช้`Add` วิธีการของ`Pages` ของสะสม.

#### ถาม: ฉันจะสร้างแท็บหยุดแบบกำหนดเองได้อย่างไร

 A: ในขั้นตอนที่ 6 คุณจะสร้าง`TabStops` วัตถุและเพิ่มแท็บสต็อปแบบกำหนดเองให้กับวัตถุนั้น นอกจากนี้ คุณยังตั้งค่าการจัดตำแหน่งและประเภทผู้นำสำหรับแท็บสต็อปแต่ละอันได้อีกด้วย

#### ถาม: ฉันจะสร้างชิ้นส่วนข้อความที่มีแท็บหยุดได้อย่างไร

 A: ในขั้นตอนที่ 7 คุณจะสร้าง`TextFragment` วัตถุและส่งแท็บหยุดแบบกำหนดเองให้กับวัตถุเหล่านั้น คุณจะใช้อักขระพิเศษ`#$TAB` เพื่อระบุตำแหน่งแท็บหยุดภายในข้อความ

#### ถาม: ฉันจะบันทึกเอกสาร PDF ได้อย่างไร

 ก: ในขั้นตอนที่ 8 คุณจะบันทึกเอกสาร PDF โดยใช้`Save` วิธีการของ`Document` วัตถุ.

#### ถาม: สิ่งสำคัญที่สุดที่ได้จากบทช่วยสอนนี้คืออะไร?

A: เมื่อทำตามบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีสร้างเอกสาร PDF ที่มีแท็บหยุดแบบกำหนดเองโดยใช้ Aspose.PDF สำหรับ .NET วิธีนี้มีประโยชน์สำหรับการจัดระเบียบและจัดตำแหน่งข้อความในลักษณะที่มีโครงสร้าง