---
title: เพิ่มรายการสั่งซื้อ HTML ลงในเอกสาร
linktitle: เพิ่มรายการสั่งซื้อ HTML ลงในเอกสาร
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มรายการที่เรียงลำดับ HTML ลงในเอกสารโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 30
url: /th/net/programming-with-text/add-html-ordered-list-into-documents/
---
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อเพิ่มรายการที่เรียงลำดับ HTML ลงในเอกสาร รหัสที่ให้มาแสดงให้เห็นถึงขั้นตอนที่จำเป็นเพื่อให้งานนี้สำเร็จ

## ความต้องการ
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Visual Studio หรือคอมไพเลอร์ C# อื่น ๆ ที่ติดตั้งบนเครื่องของคุณ
- Aspose.PDF สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose หรือใช้ตัวจัดการแพ็คเกจเช่น NuGet เพื่อติดตั้ง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
1. สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในไฟล์โค้ดที่คุณต้องการเพิ่มรายการเรียงลำดับ HTML ให้เพิ่มคำสั่งต่อไปนี้โดยใช้คำสั่งที่ด้านบนของไฟล์:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## ขั้นตอนที่ 3: ตั้งค่าไดเร็กทอรีเอกสารและเส้นทางไฟล์เอาต์พุต
 ในโค้ด ให้ค้นหาบรรทัดที่ระบุว่า`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีที่เก็บเอกสารของคุณ

 จากนั้นค้นหาบรรทัดที่ระบุว่า`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` และแทนที่`"AddHTMLOrderedListIntoDocuments_out.pdf"` ด้วยชื่อที่ต้องการสำหรับไฟล์ PDF เอาท์พุตของคุณ

## ขั้นตอนที่ 4: สร้างวัตถุเอกสารใหม่
 สร้างอินสแตนซ์ใหม่`Document` object โดยการเพิ่มบรรทัดโค้ดต่อไปนี้:

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 5: สร้างวัตถุ HtmlFragment ด้วยเนื้อหา HTML
 ยกตัวอย่าง`HtmlFragment` วัตถุที่มีเนื้อหา HTML ที่คุณต้องการเพิ่มลงในเอกสาร ในโค้ดที่ให้มา เนื้อหา HTML ถูกกำหนดให้กับตัวแปร`t`. คุณสามารถแก้ไขเนื้อหา HTML ได้ตามต้องการ

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## ขั้นตอนที่ 6: เพิ่มหน้าลงในเอกสาร
 เพิ่มหน้าใหม่ให้กับเอกสารโดยใช้`Add` วิธีการของ`Pages`ของสะสม. ในโค้ดที่ให้มา หน้าใหม่จะถูกกำหนดให้กับตัวแปร`page`.

```csharp
Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 7: เพิ่ม HtmlFragment ลงในเพจ
 เพิ่ม`HtmlFragment` คัดค้านหน้าโดยใช้`Add` วิธีการของ`Paragraphs` ของสะสม.

```csharp
page.Paragraphs.Add(t);
```

## ขั้นตอนที่ 8: บันทึกเอกสาร PDF
 บันทึกไฟล์ PDF ที่ได้โดยใช้นามสกุลไฟล์`Save` วิธีการของ`Document` วัตถุ. ระบุเส้นทางของไฟล์เอาต์พุตที่คุณตั้งค่าไว้ในขั้นตอนที่ 3

```csharp
doc.Save(outFile);
```

### ตัวอย่างซอร์สโค้ดสำหรับเพิ่มรายการ HTMLOrdered ลงในเอกสารโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เส้นทางไปยังเอกสารเอาต์พุต
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// สร้างอินสแตนซ์วัตถุเอกสาร
Document doc = new Document();
// สร้างอินสแตนซ์วัตถุ HtmlFragment ด้วยส่วน HTML ที่สอดคล้องกัน
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// เพิ่มหน้าในคอลเลกชันเพจ
Page page = doc.Pages.Add();
// เพิ่ม HtmlFragment ภายในหน้า
page.Paragraphs.Add(t);
// บันทึกไฟล์ PDF ที่เป็นผลลัพธ์
doc.Save(outFile);
```

## บทสรุป
คุณได้เพิ่มรายการเรียงลำดับ HTML ลงในเอกสารโดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว ขณะนี้ไฟล์ PDF ที่เป็นผลลัพธ์สามารถพบได้ที่เส้นทางไฟล์เอาต์พุตที่ระบุ

อย่าลืมปรับแต่งเนื้อหา HTML และปรับโค้ดตามความต้องการเฉพาะของคุณ

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้คืออะไร?

ตอบ: บทช่วยสอนนี้มีจุดมุ่งหมายเพื่อแนะนำคุณตลอดขั้นตอนการเพิ่มรายการที่เรียงลำดับ HTML ลงในเอกสารโดยใช้ Aspose.PDF สำหรับไลบรารี .NET โดยให้คำแนะนำทีละขั้นตอนและตัวอย่างโค้ดเพื่อช่วยให้คุณบรรลุภารกิจนี้

#### ถาม: ฉันจำเป็นต้องนำเข้าเนมสเปซใดสำหรับบทช่วยสอนนี้

ตอบ: คุณต้องนำเข้าเนมสเปซต่อไปนี้ที่ด้านบนของไฟล์โค้ดของคุณ:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### ถาม: ฉันจะระบุไดเรกทอรีเอกสารและเส้นทางไฟล์เอาต์พุตได้อย่างไร

 ตอบ: ในโค้ด ให้ค้นหาบรรทัด`string dataDir = "YOUR DOCUMENT DIRECTORY";` และแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ หาเส้นด้วย`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` และแทนที่`"AddHTMLOrderedListIntoDocuments_out.pdf"` ด้วยชื่อไฟล์ PDF เอาต์พุตที่คุณต้องการ

#### ถาม: ฉันสามารถปรับแต่งเนื้อหา HTML ที่จะเพิ่มลงในเอกสารได้หรือไม่

 ตอบ: แน่นอน! ในขั้นตอนที่ 5 คุณจะสร้างไฟล์`HtmlFragment` วัตถุชื่อ`t` ที่เก็บเนื้อหา HTML คุณสามารถแก้ไขเนื้อหา HTML ภายใน backticks เพื่อให้เหมาะกับความต้องการของคุณ

#### ถาม: ฉันจะเพิ่มรายการที่เรียงลำดับ HTML ลงในหน้าในเอกสารได้อย่างไร

 ตอบ: ในขั้นตอนที่ 7 คุณจะต้องเพิ่มไฟล์`HtmlFragment` วัตถุ (`t` ) ไปยังหน้าโดยใช้`Add` วิธีการของ`Paragraphs`ของสะสม. สิ่งนี้จะรวมรายการเรียงลำดับ HTML เข้ากับเอกสารได้อย่างราบรื่น

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่ได้ได้อย่างไร

 ตอบ: หลังจากเพิ่มเนื้อหา HTML และจัดเรียงเนื้อหาบนหน้าแล้ว คุณสามารถบันทึกเอกสาร PDF โดยใช้ไฟล์`Save` วิธีการของ`Document` วัตถุ. ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางไฟล์เอาต์พุตที่ถูกต้องที่คุณตั้งไว้ก่อนหน้านี้

#### ถาม: คุณสามารถให้ข้อมูลสรุปของซอร์สโค้ดตัวอย่างเพื่อใช้อ้างอิงได้หรือไม่

ตอบ: แน่นอน! ต่อไปนี้เป็นเวอร์ชันสรุปของซอร์สโค้ดตัวอย่างที่ให้ไว้ในบทช่วยสอนนี้:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### ถาม: สิ่งสำคัญที่ได้รับจากบทช่วยสอนนี้คืออะไร

ตอบ: เมื่อทำตามบทช่วยสอนนี้ คุณได้เรียนรู้วิธีใช้ประโยชน์จากไลบรารี Aspose.PDF สำหรับ .NET เพื่อรวมรายการที่เรียงลำดับ HTML ไว้ในเอกสารได้สำเร็จ ความรู้ที่เพิ่งค้นพบนี้สามารถนำไปใช้เพื่อปรับปรุงกระบวนการสร้างและจัดการเอกสารของคุณ