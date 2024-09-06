---
title: เพิ่ม HTML โดยใช้ DOM
linktitle: เพิ่ม HTML โดยใช้ DOM
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการเพิ่มเนื้อหา HTML โดยใช้ DOM ใน Aspose.PDF สำหรับ .NET
type: docs
weight: 40
url: /th/net/programming-with-text/add-html-using-dom/
---
บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการเพิ่มเนื้อหา HTML โดยใช้ DOM (Document Object Model) ใน Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนที่จำเป็น

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
```

## ขั้นตอนที่ 3: ตั้งค่าไดเรกทอรีเอกสารและเส้นทางไฟล์เอาท์พุต
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณเก็บเอกสารไว้

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
 สร้างอินสแตนซ์`HtmlFragment` วัตถุและจัดเตรียมเนื้อหา HTML ที่ต้องการ ในโค้ดที่ให้มา เนื้อหา HTML จะถูกกำหนดให้กับตัวแปร`titel`คุณสามารถปรับเปลี่ยนเนื้อหา HTML ตามต้องการ

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## ขั้นตอนที่ 7: ตั้งค่าข้อมูลระยะขอบ
ปรับระยะขอบล่างและบนของส่วน HTML หากจำเป็น ในโค้ดที่ให้มา ระยะขอบล่างถูกตั้งค่าเป็น 10 และระยะขอบบนถูกตั้งค่าเป็น 200

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## ขั้นตอนที่ 8: เพิ่ม HtmlFragment ลงในเพจ
 เพิ่ม`HtmlFragment` คัดค้านการรวบรวมย่อหน้าของหน้า

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## ขั้นตอนที่ 9: บันทึกเอกสาร PDF
 บันทึกเอกสาร PDF โดยใช้`Save` วิธีการของ`Document` วัตถุ ระบุเส้นทางไฟล์เอาท์พุตที่คุณตั้งค่าไว้ในขั้นตอนที่ 3

```csharp
doc.Save(dataDir);
```

## ขั้นตอนที่ 10: แสดงข้อความแสดงความสำเร็จ
แสดงข้อความแสดงความสำเร็จพร้อมเส้นทางที่บันทึกไฟล์ PDF

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### ตัวอย่างโค้ดที่มาสำหรับ Add HTML การใช้ DOM โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างอินสแตนซ์ของวัตถุเอกสาร
Document doc = new Document();
// เพิ่มหน้าลงในคอลเลคชันหน้าของไฟล์ PDF
Page page = doc.Pages.Add();
// สร้างอินสแตนซ์ HtmlFragment ด้วยเนื้อหา HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// ตั้งค่าข้อมูลระยะขอบล่าง
titel.Margin.Bottom = 10;
// ตั้งค่าข้อมูลระยะขอบบน
titel.Margin.Top = 200;
// เพิ่ม HTML Fragment ลงในคอลเล็กชั่นย่อหน้าของหน้า
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// บันทึกไฟล์ PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## บทสรุป
คุณได้เพิ่มเนื้อหา HTML โดยใช้ DOM ใน Aspose.PDF สำหรับ .NET สำเร็จแล้ว ตอนนี้สามารถพบไฟล์ PDF ที่ได้ในเส้นทางไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: วัตถุประสงค์ของบทช่วยสอนนี้คืออะไร?

A: บทช่วยสอนนี้มีวัตถุประสงค์เพื่อให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการเพิ่มเนื้อหา HTML ลงในเอกสาร PDF โดยใช้ Document Object Model (DOM) ใน Aspose.PDF สำหรับ .NET โดยมีตัวอย่างโค้ดต้นฉบับของ C# เพื่อช่วยให้คุณเข้าใจและนำกระบวนการนี้ไปใช้

#### ถาม: ฉันต้องนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

ก: ในไฟล์โค้ดที่คุณวางแผนจะเพิ่มเนื้อหา HTML นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารและเส้นทางไฟล์เอาต์พุตได้อย่างไร

 ก: ในโค้ด ให้หาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างวัตถุเอกสารได้อย่างไร

 ก: ในขั้นตอนที่ 4 สร้างอินสแตนซ์ใหม่`Document` วัตถุโดยการเพิ่มบรรทัดโค้ดดังต่อไปนี้:

```csharp
Document doc = new Document();
```

#### ถาม: ฉันจะเพิ่มหน้าลงในเอกสารได้อย่างไร

 ก: ในขั้นตอนที่ 5 คุณจะเพิ่มหน้าใหม่ลงในเอกสารโดยใช้`Add` วิธีการของ`Pages` ของสะสม:

```csharp
Page page = doc.Pages.Add();
```

#### ถาม: ฉันจะตั้งค่าเนื้อหา HTML โดยใช้ DOM ได้อย่างไร

 A- ในขั้นตอนที่ 6 คุณจะสร้าง`HtmlFragment` วัตถุและกำหนดเนื้อหา HTML ที่คุณต้องการให้กับวัตถุนั้น เนื้อหา HTML จะถูกกำหนดให้กับตัวแปร`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### ถาม: ฉันสามารถปรับระยะขอบของเนื้อหา HTML ได้หรือไม่?

A: ใช่ ในขั้นตอนที่ 7 คุณสามารถปรับระยะขอบด้านล่างและด้านบนของส่วน HTML ได้ตามต้องการ:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### ถาม: ฉันจะเพิ่ม HTMLFragment ลงในเอกสาร PDF ได้อย่างไร

 A: ในขั้นตอนที่ 8 คุณจะเพิ่ม`HtmlFragment` วัตถุ (`titel`) ไปยังคอลเลกชันย่อหน้าของหน้า:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### ถาม: ฉันจะบันทึกเอกสาร PDF ผลลัพธ์ได้อย่างไร

 A: หลังจากเพิ่มเนื้อหา HTML และปรับระยะขอบแล้ว ให้ใช้`Save` วิธีการของ`Document` วัตถุที่จะบันทึกเอกสาร PDF:

```csharp
doc.Save(dataDir);
```

#### ถาม: มีวิธีตรวจสอบว่ากระบวนการประสบความสำเร็จหรือไม่หรือไม่

A: แน่นอนว่าในขั้นตอนที่ 10 จะมีข้อความแสดงความสำเร็จพร้อมกับเส้นทางที่บันทึกไฟล์ PDF:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### ถาม: สิ่งสำคัญที่ได้จากบทช่วยสอนนี้คืออะไร?

A: เมื่อทำตามบทช่วยสอนนี้แล้ว คุณจะเรียนรู้วิธีใช้ Document Object Model (DOM) ใน Aspose.PDF สำหรับ .NET เพื่อเพิ่มเนื้อหา HTML ลงในเอกสาร PDF ได้สำเร็จ ความรู้ดังกล่าวจะช่วยให้คุณสามารถปรับปรุงความสามารถในการสร้าง PDF ของคุณได้