---
title: การแสดงสัญลักษณ์ที่เปลี่ยนได้ในไฟล์ PDF
linktitle: การแสดงสัญลักษณ์ที่เปลี่ยนได้ในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีแสดงสัญลักษณ์ที่เปลี่ยนได้ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 310
url: /th/net/programming-with-text/rendering-replaceable-symbols/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีแสดงสัญลักษณ์ที่เปลี่ยนได้ในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะดำเนินการตามกระบวนการทีละขั้นตอนในการสร้าง PDF เพิ่มส่วนข้อความด้วยเครื่องหมายขึ้นบรรทัดใหม่ การตั้งค่าคุณสมบัติข้อความ การวางตำแหน่งข้อความ และบันทึก PDF โดยใช้ซอร์สโค้ด C# ที่ให้มา

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร

 ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir`ตัวแปรพร้อมเส้นทางไปยังไดเร็กทอรีที่คุณต้องการ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสาร PDF และหน้า

 ต่อไป เราจะสร้างเอกสาร PDF ใหม่และเพิ่มหน้าโดยใช้`Document` ชั้นเรียนและ`Page` คลาสจากไลบรารี Aspose.PDF

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## ขั้นตอนที่ 3: เพิ่มส่วนข้อความด้วยเครื่องหมายขึ้นบรรทัดใหม่

 เราสร้างก`TextFragment`object และตั้งค่าข้อความให้รวมเครื่องหมายขึ้นบรรทัดใหม่ (`Environment.NewLine`) เพื่อแสดงข้อความหลายบรรทัด

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## ขั้นตอนที่ 4: ตั้งค่าคุณสมบัติส่วนของข้อความ

เราสามารถตั้งค่าคุณสมบัติต่างๆ สำหรับส่วนของข้อความได้หากต้องการ เช่น ขนาดตัวอักษร แบบอักษร สีพื้นหลัง และสีพื้นหน้า

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## ขั้นตอนที่ 5: สร้างย่อหน้าข้อความและตำแหน่ง

 เราสร้างก`TextParagraph` วัตถุ เพิ่มส่วนข้อความต่อท้ายย่อหน้า และกำหนดตำแหน่งของย่อหน้าบนหน้า

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## ขั้นตอนที่ 6: เพิ่มย่อหน้าข้อความลงในเพจ

 เราสร้างก`TextBuilder` วัตถุกับหน้าและเพิ่มย่อหน้าข้อความต่อท้ายตัวสร้างข้อความ

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## ขั้นตอนที่ 7: บันทึกเอกสาร PDF

สุดท้าย เราจะบันทึกเอกสาร PDF ลงในไฟล์เอาต์พุตที่ระบุ

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับการแสดงสัญลักษณ์ที่เปลี่ยนได้โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// เริ่มต้น TextFragment ใหม่ด้วยข้อความที่มีเครื่องหมายขึ้นบรรทัดใหม่ที่จำเป็น
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// ตั้งค่าคุณสมบัติส่วนของข้อความหากจำเป็น
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// สร้างวัตถุ TextParagraph
TextParagraph par = new TextParagraph();
// เพิ่ม TextFragment ใหม่ลงในย่อหน้า
par.AppendLine(textFragment);
// กำหนดตำแหน่งย่อหน้า
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// สร้างวัตถุ TextBuilder
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// เพิ่ม TextParagraph โดยใช้ TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีแสดงสัญลักษณ์ที่เปลี่ยนได้ในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและดำเนินการโค้ด C# ที่ให้มา คุณสามารถสร้าง PDF เพิ่มข้อความด้วยเครื่องหมายขึ้นบรรทัดใหม่ ตั้งค่าคุณสมบัติข้อความ วางตำแหน่งข้อความบนหน้า และบันทึก PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "การแสดงสัญลักษณ์ที่เปลี่ยนได้ในไฟล์ PDF" คืออะไร

ตอบ: บทช่วยสอน "การแสดงสัญลักษณ์ที่ถอดเปลี่ยนได้ในไฟล์ PDF" สาธิตวิธีการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อสร้างเอกสาร PDF ที่มีสัญลักษณ์ที่ถอดเปลี่ยนได้ สัญลักษณ์เหล่านี้จะแสดงเป็นส่วนของข้อความโดยมีเครื่องหมายขึ้นบรรทัดใหม่เพื่อสร้างเนื้อหาแบบหลายบรรทัด

#### ถาม: เหตุใดฉันจึงต้องการแสดงสัญลักษณ์ที่เปลี่ยนได้ในเอกสาร PDF

ตอบ: การแสดงสัญลักษณ์ที่เปลี่ยนได้มีประโยชน์เมื่อคุณต้องการสร้างเนื้อหา PDF แบบไดนามิกที่มีข้อมูลตัวแปรหรือเฉพาะผู้ใช้ สัญลักษณ์เหล่านี้ทำหน้าที่เป็นตัวยึดตำแหน่งที่สามารถแทนที่ด้วยข้อมูลจริงในระหว่างรันไทม์ เช่น ค่าฟิลด์แบบฟอร์มหรือรายละเอียดส่วนบุคคล

#### ถาม: ฉันจะตั้งค่าไดเร็กทอรีเอกสารได้อย่างไร

ตอบ: หากต้องการตั้งค่าไดเร็กทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรพร้อมพาธไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น

#### ถาม: ฉันจะเรนเดอร์สัญลักษณ์ที่เปลี่ยนได้ในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF ได้อย่างไร

ตอบ: บทช่วยสอนจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน:

1.  สร้างเอกสาร PDF ใหม่โดยใช้ไฟล์`Document` ระดับ.
2.  เพิ่มหน้าให้กับเอกสารโดยใช้`Page` ระดับ.
3.  สร้างก`TextFragment` วัตถุที่มีเครื่องหมายขึ้นบรรทัดใหม่ (`Environment.NewLine`) เพื่อแสดงเนื้อหาหลายบรรทัด
4. ปรับแต่งคุณสมบัติของส่วนของข้อความ เช่น ขนาดแบบอักษร แบบอักษร สีพื้นหลัง และสีพื้นหน้า
5.  สร้างก`TextParagraph` วัตถุ เพิ่มส่วนข้อความต่อท้าย และกำหนดตำแหน่งของย่อหน้าบนหน้า
6.  สร้างก`TextBuilder` วัตถุกับหน้าและเพิ่มย่อหน้าข้อความต่อท้าย
7. บันทึกเอกสาร PDF

#### ถาม: จุดประสงค์ของการใช้เครื่องหมายขึ้นบรรทัดใหม่ (`Environment.NewLine`) in the text fragment?

 ตอบ: เครื่องหมายขึ้นบรรทัดใหม่ใช้เพื่อสร้างเนื้อหาหลายบรรทัดภายในส่วนของข้อความเดียว โดยใช้`Environment.NewLine`คุณสามารถระบุได้ว่าควรขึ้นบรรทัดใหม่ตรงไหนในข้อความ

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของสัญลักษณ์ที่เปลี่ยนได้หรือไม่?

ตอบ: ได้ คุณสามารถปรับแต่งคุณสมบัติต่างๆ ของส่วนข้อความได้ เช่น ขนาดตัวอักษร แบบอักษร สีพื้นหลัง และสีพื้นหน้า คุณสมบัติเหล่านี้จะกำหนดลักษณะที่ปรากฏของสัญลักษณ์ที่เปลี่ยนได้ในเอกสาร PDF

#### ถาม: ฉันจะระบุตำแหน่งของข้อความบนเพจได้อย่างไร?

 ตอบ: คุณสามารถกำหนดตำแหน่งของข้อความได้โดยการสร้าง`TextParagraph` วัตถุและการใช้`Position` คุณสมบัติเพื่อระบุพิกัด X และ Y บนเพจที่ควรวางตำแหน่งย่อหน้า

#### ถาม: ผลลัพธ์ที่คาดหวังจากการรันโค้ดที่ให้มาคืออะไร?

ตอบ: เมื่อทำตามบทช่วยสอนและเรียกใช้โค้ด C# ที่ให้มา คุณจะสร้างเอกสาร PDF ที่มีสัญลักษณ์ที่เปลี่ยนได้ สัญลักษณ์ที่เปลี่ยนได้จะแสดงเป็นส่วนของข้อความพร้อมเครื่องหมายขึ้นบรรทัดใหม่และคุณสมบัติที่กำหนดเอง

#### ถาม: ฉันสามารถใช้แนวทางนี้เพื่อสร้างเอกสาร PDF ส่วนบุคคลแบบไดนามิกได้หรือไม่

ตอบ: ใช่ วิธีการนี้เหมาะสำหรับการสร้างเอกสาร PDF แบบไดนามิกพร้อมข้อมูลส่วนตัว ด้วยการแทนที่สัญลักษณ์ที่เปลี่ยนได้ด้วยข้อมูลจริง คุณสามารถสร้างเนื้อหา PDF แบบกำหนดเองสำหรับผู้ใช้แต่ละรายหรือสถานการณ์ได้