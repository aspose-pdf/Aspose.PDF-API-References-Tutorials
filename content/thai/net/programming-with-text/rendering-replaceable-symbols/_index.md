---
title: การแสดงสัญลักษณ์ที่แทนที่ได้ในไฟล์ PDF
linktitle: การแสดงสัญลักษณ์ที่แทนที่ได้ในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการแสดงสัญลักษณ์ที่สามารถแทนที่ได้ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 310
url: /th/net/programming-with-text/rendering-replaceable-symbols/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการแสดงสัญลักษณ์ที่แทนที่ได้ในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะอธิบายกระบวนการทีละขั้นตอนในการสร้าง PDF การเพิ่มส่วนข้อความพร้อมเครื่องหมายบรรทัดใหม่ การตั้งค่าคุณสมบัติข้อความ การจัดตำแหน่งข้อความ และการบันทึก PDF โดยใช้โค้ดต้นฉบับ C# ที่ให้มา

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

 ขั้นแรก คุณต้องตั้งค่าเส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไดเร็กทอรีที่คุณต้องการ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารและหน้า PDF

 ถัดไป เราจะสร้างเอกสาร PDF ใหม่และเพิ่มหน้าลงไปโดยใช้`Document` ชั้นเรียนและ`Page` คลาสจากไลบรารี Aspose.PDF

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## ขั้นตอนที่ 3: เพิ่มข้อความส่วนย่อยด้วยเครื่องหมายบรรทัดใหม่

 เราสร้าง`TextFragment` วัตถุและตั้งค่าข้อความให้รวมเครื่องหมายบรรทัดใหม่ (`Environment.NewLine`) เพื่อแสดงข้อความหลายบรรทัด

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## ขั้นตอนที่ 4: ตั้งค่าคุณสมบัติส่วนของข้อความ

เราสามารถตั้งค่าคุณสมบัติต่าง ๆ ให้กับส่วนของข้อความได้ตามต้องการ เช่น ขนาดตัวอักษร แบบอักษร สีพื้นหลัง และสีพื้นหน้า

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## ขั้นตอนที่ 5: สร้างย่อหน้าข้อความและตำแหน่ง

 เราสร้าง`TextParagraph` วัตถุ ผนวกส่วนข้อความเข้าในย่อหน้า และกำหนดตำแหน่งของย่อหน้าบนหน้า

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## ขั้นตอนที่ 6: เพิ่มย่อหน้าข้อความลงในหน้า

 เราสร้าง`TextBuilder` วัตถุกับหน้าและผนวกย่อหน้าข้อความลงในตัวสร้างข้อความ

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## ขั้นตอนที่ 7: บันทึกเอกสาร PDF

สุดท้ายเราบันทึกเอกสาร PDF ลงในไฟล์เอาท์พุตที่ระบุ

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### ตัวอย่างโค้ดที่มาสำหรับการเรนเดอร์สัญลักษณ์ที่แทนที่ได้โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// เริ่มต้น TextFragment ใหม่ด้วยข้อความที่มีเครื่องหมายบรรทัดใหม่ตามต้องการ
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// ตั้งค่าคุณสมบัติของชิ้นส่วนข้อความหากจำเป็น
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// สร้างวัตถุ TextParagraph
TextParagraph par = new TextParagraph();
// เพิ่ม TextFragment ใหม่ลงในย่อหน้า
par.AppendLine(textFragment);
// ตั้งค่าตำแหน่งย่อหน้า
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

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการแสดงสัญลักษณ์ที่แทนที่ได้ในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โดยปฏิบัติตามคำแนะนำทีละขั้นตอนและดำเนินการตามโค้ด C# ที่ให้มา คุณก็สามารถสร้าง PDF เพิ่มข้อความด้วยเครื่องหมายขึ้นบรรทัดใหม่ ตั้งค่าคุณสมบัติข้อความ วางตำแหน่งข้อความบนหน้า และบันทึก PDF ได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "การแสดงสัญลักษณ์ที่แทนที่ได้ในไฟล์ PDF" คืออะไร

A: บทช่วยสอน "การแสดงสัญลักษณ์ที่แทนที่ได้ในไฟล์ PDF" สาธิตวิธีการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อสร้างเอกสาร PDF ที่มีสัญลักษณ์ที่แทนที่ได้ สัญลักษณ์เหล่านี้แสดงเป็นชิ้นส่วนข้อความที่มีเครื่องหมายขึ้นบรรทัดใหม่เพื่อสร้างเนื้อหาหลายบรรทัด

#### ถาม: เหตุใดฉันจึงต้องการแสดงสัญลักษณ์ที่สามารถแทนที่ได้ในเอกสาร PDF

A: การแสดงสัญลักษณ์ที่แทนที่ได้นั้นมีประโยชน์เมื่อคุณจำเป็นต้องสร้างเนื้อหา PDF แบบไดนามิกที่มีข้อมูลตัวแปรหรือเฉพาะผู้ใช้ สัญลักษณ์เหล่านี้ทำหน้าที่เป็นตัวแทนที่สามารถแทนที่ด้วยข้อมูลจริงในระหว่างรันไทม์ เช่น ค่าฟิลด์ฟอร์มหรือรายละเอียดส่วนบุคคล

#### ถาม: ฉันจะตั้งค่าไดเรกทอรีเอกสารได้อย่างไร?

ก: การตั้งค่าไดเรกทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น

#### ถาม: ฉันจะแสดงสัญลักษณ์ที่สามารถแทนที่ได้ในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF ได้อย่างไร

A: บทช่วยสอนจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน:

1.  สร้างเอกสาร PDF ใหม่โดยใช้`Document` ระดับ.
2.  เพิ่มหน้าลงในเอกสารโดยใช้`Page` ระดับ.
3.  สร้าง`TextFragment` วัตถุที่มีเครื่องหมายขึ้นบรรทัดใหม่ (`Environment.NewLine`) เพื่อแสดงเนื้อหาหลายบรรทัด
4. ปรับแต่งคุณสมบัติของชิ้นส่วนข้อความ เช่น ขนาดตัวอักษร แบบอักษร สีพื้นหลัง และสีพื้นหน้า
5.  สร้าง`TextParagraph` วัตถุ ให้ผนวกส่วนของข้อความเข้าไป และกำหนดตำแหน่งของย่อหน้าบนหน้า
6.  สร้าง`TextBuilder` วัตถุกับหน้าและผนวกย่อหน้าข้อความเข้าไป
7. บันทึกเอกสาร PDF

#### ถาม: จุดประสงค์ของการใช้เครื่องหมายขึ้นบรรทัดใหม่คืออะไร (`Environment.NewLine`) in the text fragment?

 A: เครื่องหมายบรรทัดใหม่ใช้เพื่อสร้างเนื้อหาหลายบรรทัดภายในส่วนข้อความเดียว โดยใช้`Environment.NewLine`คุณสามารถระบุได้ว่าควรแบ่งบรรทัดตรงไหนในข้อความ

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของสัญลักษณ์ที่สามารถเปลี่ยนได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งคุณสมบัติต่างๆ ของส่วนข้อความได้ เช่น ขนาดแบบอักษร แบบอักษร สีพื้นหลัง และสีพื้นหน้า คุณสมบัติเหล่านี้จะกำหนดลักษณะที่ปรากฏของสัญลักษณ์ที่แทนที่ได้ในเอกสาร PDF

#### ถาม: ฉันจะระบุตำแหน่งของข้อความบนหน้าได้อย่างไร

 A: คุณสามารถกำหนดตำแหน่งของข้อความได้โดยการสร้าง`TextParagraph` วัตถุและการใช้`Position` คุณสมบัติในการระบุพิกัด X และ Y บนหน้าที่จะวางย่อหน้าไว้

#### ถาม: ผลลัพธ์ที่คาดหวังจากการดำเนินการโค้ดที่ให้มาคืออะไร

A: หากทำตามบทช่วยสอนและรันโค้ด C# ที่ให้มา คุณจะสร้างเอกสาร PDF ที่มีสัญลักษณ์ที่แทนที่ได้ สัญลักษณ์ที่แทนที่ได้จะแสดงเป็นชิ้นส่วนข้อความพร้อมเครื่องหมายขึ้นบรรทัดใหม่และคุณสมบัติที่กำหนดเอง

#### ถาม: ฉันสามารถใช้แนวทางนี้เพื่อสร้างเอกสาร PDF ส่วนบุคคลแบบไดนามิกได้หรือไม่

A: ใช่ แนวทางนี้เหมาะสำหรับการสร้างเอกสาร PDF แบบไดนามิกพร้อมข้อมูลส่วนบุคคล โดยการแทนที่สัญลักษณ์ที่แทนที่ได้ด้วยข้อมูลจริง คุณสามารถสร้างเนื้อหา PDF ที่กำหนดเองสำหรับแต่ละผู้ใช้หรือสถานการณ์ต่างๆ ได้