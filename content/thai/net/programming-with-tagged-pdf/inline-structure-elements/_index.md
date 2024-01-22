---
title: องค์ประกอบโครงสร้างอินไลน์
linktitle: องค์ประกอบโครงสร้างอินไลน์
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการใช้องค์ประกอบโครงสร้างออนไลน์กับ Aspose.PDF สำหรับ .NET จัดระเบียบ PDF ของคุณด้วยส่วนหัวและย่อหน้า
type: docs
weight: 110
url: /th/net/programming-with-tagged-pdf/inline-structure-elements/
---
ในคำแนะนำทีละขั้นตอนนี้ เราจะแสดงวิธีใช้องค์ประกอบโครงสร้างอินไลน์กับ Aspose.PDF สำหรับ .NET Aspose.PDF เป็นไลบรารีอันทรงพลังที่ให้คุณจัดการเอกสาร PDF โดยทางโปรแกรม องค์ประกอบโครงสร้างอินไลน์ช่วยให้คุณสร้างโครงสร้างแบบลำดับชั้นในเอกสาร PDF ของคุณโดยใช้ส่วนหัวของระดับและย่อหน้าต่างๆ

มาเจาะลึกโค้ดและเรียนรู้วิธีใช้องค์ประกอบโครงสร้างอินไลน์ด้วย Aspose.PDF สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
2. ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ในการเริ่มต้น ให้เปิดสภาพแวดล้อมการพัฒนา C# ของคุณและสร้างโปรเจ็กต์ใหม่ ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET ในโปรเจ็กต์ของคุณ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างเอกสาร

 ขั้นตอนแรกคือการสร้างเอกสาร PDF ใหม่โดยใช้ไฟล์`Document` ระดับ.

```csharp
// สร้างเอกสาร PDF
Document document = new Document();
```

## ขั้นตอนที่ 3: ทำงานกับเนื้อหาที่แท็ก

จากนั้นเราจะได้รับเนื้อหาที่แท็กของเอกสารเพื่อใช้งาน

```csharp
// รับเนื้อหาที่แท็กของเอกสาร
ITaggedContent taggedContent = document.TaggedContent;
```

## ขั้นตอนที่ 4: ตั้งชื่อเอกสารและภาษา

ตอนนี้เราสามารถตั้งชื่อเอกสารและภาษาได้แล้ว

```csharp
// กำหนดชื่อเอกสารและภาษา
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## ขั้นตอนที่ 5: เพิ่มองค์ประกอบโครงสร้างออนไลน์

ตอนนี้เรากำลังจะเพิ่มองค์ประกอบโครงสร้างแบบอินไลน์ เช่น ส่วนหัวของระดับต่างๆ และย่อหน้าลงในเอกสารของเรา

```csharp
// รับองค์ประกอบโครงสร้างรูท
StructureElement rootElement = taggedContent.RootElement;

// เพิ่มส่วนหัวของระดับต่างๆ
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// เพิ่มเนื้อหาลงในแต่ละส่วนหัว
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// เพิ่มย่อหน้า
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// เพิ่มเนื้อหาลงในย่อหน้า
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

ที่นี่เราสร้างองค์ประกอบโครงสร้างแบบอินไลน์ เช่น ส่วนหัวของระดับต่างๆ และย่อหน้า และเพิ่มเนื้อหาลงไป

## ขั้นตอนที่ 6: บันทึกเอกสาร PDF ที่แท็ก

สุดท้าย เราจะบันทึกเอกสาร PDF ที่แท็กไว้

```csharp
// บันทึกเอกสาร PDF ที่แท็ก
document.Save(dataDir + "InlineStructureElements.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับองค์ประกอบโครงสร้างอินไลน์โดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร PDF
Document document = new Document();

// รับเนื้อหาสำหรับการทำงานกับ TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// ตั้งชื่อและภาษาสำหรับ Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// รับองค์ประกอบโครงสร้างรูท
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// บันทึกเอกสาร PDF ที่ติดแท็ก
document.Save(dataDir + "InlineStructureElements.pdf");

```

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีใช้องค์ประกอบโครงสร้างอินไลน์กับ Aspose.PDF สำหรับ .NET แล้ว ตอนนี้คุณสามารถสร้างโครงสร้างแบบลำดับชั้นในเอกสาร PDF ของคุณโดยใช้ส่วนหัวของระดับและย่อหน้าต่างๆ สำรวจคุณสมบัติเพิ่มเติมของ Aspose.PDF เพื่อค้นพบศักยภาพสูงสุด

### คำถามที่พบบ่อย

#### ถาม: องค์ประกอบโครงสร้างอินไลน์ในเอกสาร PDF คืออะไร และองค์ประกอบเหล่านี้มีส่วนช่วยในการสร้างโครงสร้างแบบลำดับชั้นอย่างไร

ตอบ: องค์ประกอบโครงสร้างแบบอินไลน์ในเอกสาร PDF เช่น ส่วนหัวของระดับและย่อหน้าต่างๆ จะถูกใช้เพื่อสร้างโครงสร้างแบบลำดับชั้นที่จัดระเบียบและนำเสนอเนื้อหาในลักษณะที่มีโครงสร้าง องค์ประกอบเหล่านี้ช่วยให้คุณสร้างลำดับชั้นและการไหลของข้อมูลภายในเอกสารได้อย่างชัดเจน

#### ถาม: องค์ประกอบโครงสร้างอินไลน์จะช่วยเพิ่มความสามารถในการอ่านและการจัดระเบียบเอกสาร PDF ได้อย่างไร

ตอบ: องค์ประกอบโครงสร้างอินไลน์ โดยเฉพาะส่วนหัวและย่อหน้า ช่วยปรับปรุงความสามารถในการอ่านและการจัดระเบียบของเอกสาร PDF โดยจัดเตรียมโครงสร้างเชิงตรรกะ ส่วนหัวจะระบุระดับความสำคัญที่แตกต่างกันและช่วยให้ผู้อ่านไปยังส่วนต่างๆ ของเนื้อหา ในขณะที่ย่อหน้าจะจัดกลุ่มข้อมูลที่เกี่ยวข้องไว้ด้วยกัน

#### ถาม: Aspose.PDF สำหรับ .NET อำนวยความสะดวกในการใช้องค์ประกอบโครงสร้างอินไลน์อย่างไร

ตอบ: Aspose.PDF สำหรับ .NET มีคลาสและวิธีการสร้างและจัดการองค์ประกอบโครงสร้างอินไลน์ เช่น ส่วนหัวและย่อหน้า องค์ประกอบเหล่านี้สามารถปรับแต่ง จัดระเบียบตามลำดับชั้น และเสริมด้วยเนื้อหาเพื่อปรับปรุงการนำเสนอด้วยภาพและการเข้าถึงเอกสารได้

####  ถาม: จุดประสงค์ของ.`taggedContent` object in relation to inline structure elements?

 ตอบ:`taggedContent` วัตถุที่ได้รับจาก`TaggedContent` ทรัพย์สินของ`Document`ช่วยให้คุณสามารถทำงานกับองค์ประกอบที่มีโครงสร้าง รวมถึงองค์ประกอบโครงสร้างแบบอินไลน์ ช่วยให้คุณสามารถสร้าง ปรับแต่ง และจัดระเบียบหัวเรื่องและย่อหน้าภายในเอกสารได้

#### ถาม: องค์ประกอบโครงสร้างอินไลน์ช่วยในการสร้างลำดับชั้นของเอกสารที่ชัดเจนได้อย่างไร

ตอบ: องค์ประกอบโครงสร้างอินไลน์ เช่น ส่วนหัวของระดับที่แตกต่างกัน มีส่วนช่วยสร้างลำดับชั้นที่ชัดเจนและชัดเจนในเอกสาร ผู้อ่านสามารถระบุหัวข้อหลัก หัวข้อย่อย และเนื้อหาที่เกี่ยวข้องได้อย่างรวดเร็ว ทำให้สามารถนำทางและทำความเข้าใจเอกสารได้ง่ายขึ้น

#### ถาม: ฉันสามารถปรับแต่งรูปลักษณ์และการจัดรูปแบบขององค์ประกอบโครงสร้างอินไลน์โดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏและการจัดรูปแบบขององค์ประกอบโครงสร้างอินไลน์ได้ คุณสามารถตั้งค่าคุณสมบัติ เช่น ลักษณะแบบอักษร ขนาด สี การจัดตำแหน่ง การเยื้อง และระยะห่าง เพื่อให้ได้การนำเสนอภาพสำหรับหัวเรื่องและย่อหน้าตามต้องการ

#### ถาม: ฉันจะสร้างและเพิ่มส่วนหัวของระดับต่างๆ ลงในเอกสาร PDF โดยใช้องค์ประกอบโครงสร้างอินไลน์ใน Aspose.PDF สำหรับ .NET ได้อย่างไร

 ตอบ: คุณสามารถสร้างส่วนหัวของระดับต่างๆ ได้โดยใช้`CreateHeaderElement` วิธีการแล้วผนวกเข้ากับองค์ประกอบโครงสร้างราก จากนั้น คุณสามารถเพิ่มเนื้อหาให้กับแต่ละองค์ประกอบส่วนหัวได้โดยใช้`CreateSpanElement` วิธีสร้างช่วงข้อความ

#### ถาม: ฉันสามารถใช้องค์ประกอบโครงสร้างอินไลน์เพื่อสร้างรายการ สัญลักษณ์แสดงหัวข้อย่อย หรือการจัดระเบียบเนื้อหาประเภทอื่นๆ ในเอกสาร PDF ได้หรือไม่

ตอบ: แม้ว่าองค์ประกอบโครงสร้างอินไลน์จะใช้กับส่วนหัวและย่อหน้าเป็นหลัก แต่คุณสามารถใช้องค์ประกอบเหล่านี้ร่วมกับคุณสมบัติอื่นๆ ที่นำเสนอโดย Aspose.PDF สำหรับ .NET เพื่อสร้างรายการ สัญลักษณ์แสดงหัวข้อย่อย ตาราง และการจัดระเบียบเนื้อหาประเภทอื่นๆ เพื่อการจัดระเบียบเนื้อหาที่ครอบคลุม โครงสร้างเอกสาร

#### ถาม: องค์ประกอบโครงสร้างอินไลน์มีส่วนช่วยในการเข้าถึงเอกสารอย่างไร

ตอบ: องค์ประกอบโครงสร้างอินไลน์มีบทบาทสำคัญในการปรับปรุงการเข้าถึงเอกสาร ส่วนหัวและย่อหน้าที่มีโครงสร้างอย่างเหมาะสมให้ลำดับชั้นของเอกสารที่ชัดเจนซึ่งช่วยให้โปรแกรมอ่านหน้าจอและเทคโนโลยีช่วยเหลืออื่นๆ ในการตีความและถ่ายทอดเนื้อหาไปยังผู้ใช้ที่มีความพิการได้อย่างถูกต้อง

#### ถาม: ฉันสามารถสำรวจการใช้งานขั้นสูงเพิ่มเติมขององค์ประกอบโครงสร้างอินไลน์ เช่น การสร้างองค์ประกอบเชิงโต้ตอบ หรือการฝังมัลติมีเดียได้หรือไม่

ตอบ: แน่นอน! แม้ว่าบทช่วยสอนนี้จะเน้นที่การสร้างหัวเรื่องและย่อหน้า แต่ Aspose.PDF สำหรับ .NET ก็มีฟีเจอร์ขั้นสูงเพื่อสร้างองค์ประกอบเชิงโต้ตอบ มัลติมีเดียแบบฝัง เพิ่มไฮเปอร์ลิงก์ และอื่นๆ อีกมากมาย ตรวจสอบเอกสารและตัวอย่างของห้องสมุดเพื่อเจาะลึกความสามารถขั้นสูงเหล่านี้