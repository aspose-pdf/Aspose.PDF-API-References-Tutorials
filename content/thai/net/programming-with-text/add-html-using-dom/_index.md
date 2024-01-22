---
title: เพิ่ม HTML โดยใช้ DOM
linktitle: เพิ่ม HTML โดยใช้ DOM
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มเนื้อหา HTML โดยใช้ DOM ใน Aspose.PDF สำหรับ .NET
type: docs
weight: 40
url: /th/net/programming-with-text/add-html-using-dom/
---
บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการเพิ่มเนื้อหา HTML โดยใช้ DOM (Document Object Model) ใน Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาสาธิตขั้นตอนที่จำเป็น

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
```

## ขั้นตอนที่ 3: ตั้งค่าไดเร็กทอรีเอกสารและเส้นทางไฟล์เอาต์พุต
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่เก็บเอกสารของคุณ

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
 ยกตัวอย่าง`HtmlFragment` object และจัดเตรียมเนื้อหา HTML ที่ต้องการ ในโค้ดที่ให้มา เนื้อหา HTML ถูกกำหนดให้กับตัวแปร`titel`. คุณสามารถแก้ไขเนื้อหา HTML ได้ตามต้องการ

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## ขั้นตอนที่ 7: ตั้งค่าข้อมูลระยะขอบ
ปรับระยะขอบด้านล่างและด้านบนของส่วน HTML หากจำเป็น ในโค้ดที่ให้มา ระยะขอบด้านล่างตั้งค่าเป็น 10 และระยะขอบด้านบนตั้งค่าเป็น 200

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## ขั้นตอนที่ 8: เพิ่ม HtmlFragment ลงในเพจ
 เพิ่ม`HtmlFragment` คัดค้านการรวบรวมย่อหน้าของเพจ

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## ขั้นตอนที่ 9: บันทึกเอกสาร PDF
 บันทึกเอกสาร PDF โดยใช้ไฟล์`Save` วิธีการของ`Document` วัตถุ. ระบุเส้นทางของไฟล์เอาต์พุตที่คุณตั้งค่าไว้ในขั้นตอนที่ 3

```csharp
doc.Save(dataDir);
```

## ขั้นตอนที่ 10: แสดงข้อความแสดงความสำเร็จ
แสดงข้อความแสดงความสำเร็จพร้อมกับเส้นทางที่บันทึกไฟล์ PDF

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับการเพิ่ม HTMLUsing DOM โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างอินสแตนซ์วัตถุเอกสาร
Document doc = new Document();
// เพิ่มหน้าไปยังคอลเลกชันหน้าของไฟล์ PDF
Page page = doc.Pages.Add();
// สร้างอินสแตนซ์ HtmlFragment ด้วยคอนเทนต์ HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// ตั้งค่าข้อมูลระยะขอบด้านล่าง
titel.Margin.Bottom = 10;
// ตั้งค่าข้อมูลระยะขอบด้านบน
titel.Margin.Top = 200;
// เพิ่ม HTML Fragment ให้กับคอลเลกชันย่อหน้าของหน้า
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// บันทึกไฟล์ PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## บทสรุป
คุณได้เพิ่มเนื้อหา HTML โดยใช้ DOM ใน Aspose.PDF สำหรับ .NET สำเร็จแล้ว ขณะนี้ไฟล์ PDF ที่เป็นผลลัพธ์สามารถพบได้ที่เส้นทางไฟล์เอาต์พุตที่ระบุ

### คำถามที่พบบ่อย

#### ถาม: วัตถุประสงค์ของบทช่วยสอนนี้คืออะไร

ตอบ: บทช่วยสอนนี้มีจุดมุ่งหมายเพื่อให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีเพิ่มเนื้อหา HTML ลงในเอกสาร PDF โดยใช้ Document Object Model (DOM) ใน Aspose.PDF สำหรับ .NET ประกอบด้วยข้อมูลโค้ด C# เพื่อช่วยให้คุณเข้าใจและนำกระบวนการไปใช้

#### ถาม: ฉันจำเป็นต้องนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

ตอบ: ในไฟล์โค้ดที่คุณวางแผนจะเพิ่มเนื้อหา HTML ให้นำเข้าเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์:

```csharp
using Aspose.Pdf;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารและเส้นทางไฟล์เอาต์พุตได้อย่างไร

 ตอบ: ในโค้ด ให้ค้นหาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

#### ถาม: ฉันจะสร้างออบเจ็กต์ Document ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 4 สร้างอินสแตนซ์ใหม่`Document` object โดยการเพิ่มบรรทัดโค้ดต่อไปนี้:

```csharp
Document doc = new Document();
```

#### ถาม: ฉันจะเพิ่มหน้าลงในเอกสารได้อย่างไร

 ตอบ: ในขั้นตอนที่ 5 คุณจะต้องเพิ่มหน้าใหม่ให้กับเอกสารโดยใช้`Add` วิธีการของ`Pages` ของสะสม:

```csharp
Page page = doc.Pages.Add();
```

#### ถาม: ฉันจะตั้งค่าเนื้อหา HTML โดยใช้ DOM ได้อย่างไร

 ตอบ: : ในขั้นตอนที่ 6 คุณจะสร้างไฟล์`HtmlFragment` วัตถุและกำหนดเนื้อหา HTML ที่คุณต้องการ เนื้อหา HTML ถูกกำหนดให้กับตัวแปร`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### ถาม: ฉันสามารถปรับระยะขอบของเนื้อหา HTML ได้หรือไม่

ตอบ: ได้ ในขั้นตอนที่ 7 คุณสามารถปรับระยะขอบด้านล่างและด้านบนของส่วน HTML ได้ตามต้องการ:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### ถาม: ฉันจะเพิ่ม HTMLFragment ลงในเอกสาร PDF ได้อย่างไร

 ตอบ: ในขั้นตอนที่ 8 คุณจะต้องเพิ่มไฟล์`HtmlFragment` วัตถุ (`titel`) ไปยังคอลเลกชันย่อหน้าของหน้า:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่ได้ได้อย่างไร

 ตอบ: หลังจากเพิ่มเนื้อหา HTML และปรับระยะขอบแล้ว ให้ใช้`Save` วิธีการของ`Document` วัตถุเพื่อบันทึกเอกสาร PDF:

```csharp
doc.Save(dataDir);
```

#### ถาม: มีวิธีตรวจสอบว่ากระบวนการนี้สำเร็จหรือไม่?

ตอบ: แน่นอนว่าในขั้นตอนที่ 10 ข้อความแสดงความสำเร็จจะปรากฏขึ้นพร้อมกับเส้นทางที่บันทึกไฟล์ PDF:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### ถาม: สิ่งสำคัญที่ได้รับจากบทช่วยสอนนี้คืออะไร

ตอบ: ด้วยการทำตามบทช่วยสอนนี้ คุณได้เรียนรู้วิธีใช้ Document Object Model (DOM) ใน Aspose.PDF สำหรับ .NET เพื่อเพิ่มเนื้อหา HTML ลงในเอกสาร PDF ได้สำเร็จ ความรู้นี้ช่วยให้คุณเพิ่มขีดความสามารถในการสร้าง PDF ของคุณได้