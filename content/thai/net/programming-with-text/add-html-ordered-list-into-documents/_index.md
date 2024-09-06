---
title: เพิ่มรายการเรียงลำดับ HTML ลงในเอกสาร
linktitle: เพิ่มรายการเรียงลำดับ HTML ลงในเอกสาร
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการเพิ่มรายการเรียงลำดับ HTML ลงในเอกสารโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 30
url: /th/net/programming-with-text/add-html-ordered-list-into-documents/
---
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อเพิ่มรายการเรียงลำดับ HTML ลงในเอกสาร โค้ดที่ให้มาจะสาธิตขั้นตอนที่จำเป็นในการทำงานนี้ให้สำเร็จ

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ติดตั้งอยู่บนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose อย่างเป็นทางการหรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการเพิ่มรายการเรียงลำดับ HTML ให้เพิ่มคำสั่งต่อไปนี้โดยใช้คำสั่งที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเรกทอรีเอกสารและเส้นทางไฟล์เอาท์พุต
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณเก็บเอกสารไว้

 จากนั้นค้นหาบรรทัดที่ระบุว่า`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` และแทนที่`"AddHTMLOrderedListIntoDocuments_out.pdf"` พร้อมชื่อที่ต้องการให้ไฟล์ PDF เอาท์พุตของคุณ

## ขั้นตอนที่ 4: สร้างวัตถุเอกสารใหม่
 สร้างอินสแตนซ์ใหม่`Document` วัตถุโดยการเพิ่มบรรทัดโค้ดดังต่อไปนี้:

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 5: สร้างวัตถุ HtmlFragment ที่มีเนื้อหา HTML
 สร้างอินสแตนซ์`HtmlFragment` วัตถุที่มีเนื้อหา HTML ที่คุณต้องการเพิ่มลงในเอกสาร ในโค้ดที่ให้มา เนื้อหา HTML จะถูกกำหนดให้กับตัวแปร`t`คุณสามารถปรับเปลี่ยนเนื้อหา HTML ตามต้องการ

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## ขั้นตอนที่ 6: เพิ่มหน้าลงในเอกสาร
 เพิ่มหน้าใหม่ลงในเอกสารโดยใช้`Add` วิธีการของ`Pages`คอลเลกชัน ในโค้ดที่ให้มา หน้าใหม่จะถูกกำหนดให้กับตัวแปร`page`.

```csharp
Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 7: เพิ่ม HtmlFragment ลงในเพจ
 เพิ่ม`HtmlFragment` คัดค้านหน้าโดยใช้`Add` วิธีการของ`Paragraphs` ของสะสม.

```csharp
page.Paragraphs.Add(t);
```

## ขั้นตอนที่ 8: บันทึกเอกสาร PDF
 บันทึกไฟล์ PDF ที่ได้โดยใช้`Save` วิธีการของ`Document` วัตถุ ระบุเส้นทางไฟล์เอาท์พุตที่คุณตั้งค่าไว้ในขั้นตอนที่ 3

```csharp
doc.Save(outFile);
```

### ตัวอย่างโค้ดที่มาสำหรับการเพิ่มรายการเรียงลำดับ HTML ลงในเอกสารโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เส้นทางไปยังเอกสารผลลัพธ์
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// สร้างอินสแตนซ์ของวัตถุเอกสาร
Document doc = new Document();
// สร้างอินสแตนซ์ของวัตถุ HtmlFragment ด้วยชิ้นส่วน HTML ที่สอดคล้องกัน
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// เพิ่มหน้าในคอลเลคชันหน้า
Page page = doc.Pages.Add();
// เพิ่ม HtmlFragment ลงในหน้า
page.Paragraphs.Add(t);
// บันทึกไฟล์ PDF ที่ได้
doc.Save(outFile);
```

## บทสรุป
คุณได้เพิ่มรายการเรียงลำดับ HTML ลงในเอกสารสำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้สามารถพบไฟล์ PDF ที่ได้ในเส้นทางไฟล์เอาต์พุตที่ระบุ

อย่าลืมปรับแต่งเนื้อหา HTML และปรับเปลี่ยนโค้ดตามความต้องการเฉพาะของคุณ

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้คืออะไร?

A: บทช่วยสอนนี้มีวัตถุประสงค์เพื่อแนะนำคุณตลอดกระบวนการเพิ่มรายการเรียงลำดับ HTML ลงในเอกสารโดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โดยจะให้คำแนะนำทีละขั้นตอนและตัวอย่างโค้ดเพื่อช่วยให้คุณบรรลุภารกิจนี้ได้

#### ถาม: ฉันต้องนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

A: คุณต้องนำเข้าเนมสเปซต่อไปนี้ที่ด้านบนของไฟล์โค้ดของคุณ:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารและเส้นทางไฟล์เอาต์พุตได้อย่างไร

 ก: ในโค้ด ให้ระบุตำแหน่งบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ นอกจากนี้ ให้ค้นหาบรรทัด`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` และแทนที่`"AddHTMLOrderedListIntoDocuments_out.pdf"` ด้วยชื่อไฟล์ PDF ที่คุณต้องการ

#### ถาม: ฉันสามารถปรับแต่งเนื้อหา HTML ที่จะเพิ่มลงในเอกสารได้หรือไม่

 A: แน่นอน! ในขั้นตอนที่ 5 คุณจะสร้าง`HtmlFragment` วัตถุที่มีชื่อว่า`t` ซึ่งเก็บเนื้อหา HTML คุณสามารถปรับเปลี่ยนเนื้อหา HTML ภายในแบ็กทิกส์ให้เหมาะกับความต้องการของคุณได้

#### ถาม: ฉันจะเพิ่มรายการเรียงลำดับ HTML ลงในหน้าในเอกสารได้อย่างไร

 A: ในขั้นตอนที่ 7 คุณจะเพิ่ม`HtmlFragment` วัตถุ (`t` ) ไปที่หน้าโดยใช้`Add` วิธีการของ`Paragraphs`คอลเลกชันนี้จะบูรณาการรายการเรียงลำดับ HTML เข้ากับเอกสารได้อย่างราบรื่น

#### ถาม: ฉันจะบันทึกเอกสาร PDF ผลลัพธ์ได้อย่างไร

 A: หลังจากเพิ่มเนื้อหา HTML และจัดเรียงบนหน้าแล้ว คุณสามารถบันทึกเอกสาร PDF โดยใช้`Save` วิธีการของ`Document` วัตถุ ตรวจสอบให้แน่ใจว่าคุณระบุเส้นทางไฟล์เอาท์พุตที่ถูกต้องที่คุณตั้งค่าไว้ก่อนหน้านี้

#### ถาม: คุณสามารถให้บทสรุปโค้ดตัวอย่างเพื่อใช้เป็นข้อมูลอ้างอิงได้หรือไม่?

A: แน่นอน! นี่คือตัวอย่างโค้ดต้นฉบับโดยย่อที่ให้ไว้ในบทช่วยสอนนี้:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### ถาม: สิ่งสำคัญที่ได้จากบทช่วยสอนนี้คืออะไร?

A: เมื่อทำตามบทช่วยสอนนี้แล้ว คุณจะเรียนรู้วิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อรวมรายการเรียงลำดับ HTML ลงในเอกสารได้สำเร็จ ความรู้ใหม่นี้สามารถนำมาใช้เพื่อปรับปรุงกระบวนการสร้างและจัดการเอกสารของคุณได้