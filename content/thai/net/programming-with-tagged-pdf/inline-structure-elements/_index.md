---
title: องค์ประกอบโครงสร้างแบบอินไลน์
linktitle: องค์ประกอบโครงสร้างแบบอินไลน์
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: คู่มือทีละขั้นตอนในการใช้องค์ประกอบโครงสร้างออนไลน์ด้วย Aspose.PDF สำหรับ .NET จัดระเบียบ PDF ของคุณด้วยหัวเรื่องและย่อหน้า
type: docs
weight: 110
url: /th/net/programming-with-tagged-pdf/inline-structure-elements/
---
ในคู่มือทีละขั้นตอนนี้ เราจะแสดงวิธีใช้องค์ประกอบโครงสร้างอินไลน์กับ Aspose.PDF สำหรับ .NET Aspose.PDF เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณจัดการเอกสาร PDF ได้ด้วยโปรแกรม องค์ประกอบโครงสร้างอินไลน์ช่วยให้คุณสร้างโครงสร้างแบบลำดับชั้นในเอกสาร PDF ของคุณโดยใช้หัวเรื่องในระดับและย่อหน้าที่แตกต่างกัน

มาเจาะลึกโค้ดและเรียนรู้วิธีใช้องค์ประกอบโครงสร้างอินไลน์ใน Aspose.PDF สำหรับ .NET กัน

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
2. ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ในการเริ่มต้น ให้เปิดสภาพแวดล้อมการพัฒนา C# ของคุณและสร้างโปรเจ็กต์ใหม่ ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET ในโปรเจ็กต์ของคุณแล้ว

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างเอกสาร

 ขั้นตอนแรกคือการสร้างเอกสาร PDF ใหม่โดยใช้`Document` ระดับ.

```csharp
// สร้างเอกสาร PDF
Document document = new Document();
```

## ขั้นตอนที่ 3: ทำงานกับเนื้อหาที่มีแท็ก

จากนั้นเราจะได้รับเนื้อหาที่ถูกแท็กของเอกสารเพื่อใช้งาน

```csharp
// รับเนื้อหาที่ถูกแท็กของเอกสาร
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

ตอนนี้เรากำลังจะเพิ่มองค์ประกอบโครงสร้างแบบอินไลน์เช่นหัวเรื่องระดับต่างๆ และย่อหน้าลงในเอกสารของเรา

```csharp
// รับองค์ประกอบโครงสร้างราก
StructureElement rootElement = taggedContent.RootElement;

// เพิ่มส่วนหัวของระดับที่แตกต่างกัน
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

// เพิ่มเนื้อหาในแต่ละส่วนหัว
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

ที่นี่เราสร้างองค์ประกอบโครงสร้างแบบอินไลน์ เช่น หัวข้อระดับต่างๆ และย่อหน้า และเพิ่มเนื้อหาลงไป

## ขั้นตอนที่ 6: บันทึกเอกสาร PDF ที่ถูกแท็ก

ในที่สุดเราก็บันทึกเอกสาร PDF ที่ถูกแท็ก

```csharp
// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "InlineStructureElements.pdf");
```

### ตัวอย่างโค้ดต้นฉบับสำหรับองค์ประกอบโครงสร้างอินไลน์โดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร PDF
Document document = new Document();

// รับเนื้อหาสำหรับงานด้วย TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// ตั้งชื่อเรื่องและภาษาสำหรับ Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// รับองค์ประกอบโครงสร้างราก
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

// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "InlineStructureElements.pdf");

```

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีใช้องค์ประกอบโครงสร้างอินไลน์กับ Aspose.PDF สำหรับ .NET แล้ว ตอนนี้คุณสามารถสร้างโครงสร้างแบบลำดับชั้นในเอกสาร PDF ของคุณโดยใช้หัวเรื่องของระดับและย่อหน้าที่แตกต่างกัน สำรวจคุณสมบัติเพิ่มเติมของ Aspose.PDF เพื่อค้นพบศักยภาพทั้งหมดของมัน

### คำถามที่พบบ่อย

#### ถาม: องค์ประกอบโครงสร้างอินไลน์ในเอกสาร PDF คืออะไร และมีส่วนช่วยสร้างโครงสร้างลำดับชั้นอย่างไร

A: องค์ประกอบโครงสร้างแบบอินไลน์ในเอกสาร PDF เช่น หัวข้อที่มีระดับและย่อหน้าต่างกัน จะใช้เพื่อสร้างโครงสร้างแบบลำดับชั้นที่จัดระเบียบและนำเสนอเนื้อหาในลักษณะที่มีโครงสร้าง องค์ประกอบเหล่านี้ช่วยให้คุณกำหนดลำดับชั้นและการไหลของข้อมูลภายในเอกสารได้อย่างชัดเจน

#### ถาม: องค์ประกอบโครงสร้างอินไลน์ช่วยเพิ่มความสามารถในการอ่านและการจัดระเบียบของเอกสาร PDF ได้อย่างไร

A: องค์ประกอบโครงสร้างแบบอินไลน์ โดยเฉพาะหัวเรื่องและย่อหน้า ช่วยปรับปรุงการอ่านและการจัดระเบียบเอกสาร PDF โดยให้โครงสร้างที่เป็นตรรกะ หัวเรื่องจะระบุระดับความสำคัญที่แตกต่างกันและช่วยให้ผู้อ่านนำทางเนื้อหาได้ ในขณะที่ย่อหน้าจะจัดกลุ่มข้อมูลที่เกี่ยวข้องไว้ด้วยกัน

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยอำนวยความสะดวกในการใช้องค์ประกอบโครงสร้างอินไลน์ได้อย่างไร

A: Aspose.PDF สำหรับ .NET นำเสนอคลาสและวิธีการสำหรับสร้างและจัดการองค์ประกอบโครงสร้างอินไลน์ เช่น หัวเรื่องและย่อหน้า องค์ประกอบเหล่านี้สามารถปรับแต่ง จัดระเบียบตามลำดับชั้น และเสริมด้วยเนื้อหาเพื่อปรับปรุงการนำเสนอภาพและการเข้าถึงเอกสาร

####  ถาม: จุดประสงค์ของการ`taggedContent` object in relation to inline structure elements?

 ก. การ`taggedContent` วัตถุที่ได้มาจาก`TaggedContent` ทรัพย์สินของ`Document`ช่วยให้คุณสามารถทำงานกับองค์ประกอบที่มีโครงสร้าง รวมถึงองค์ประกอบโครงสร้างแบบอินไลน์ ช่วยให้คุณสามารถสร้าง ปรับแต่ง และจัดระเบียบหัวเรื่องและย่อหน้าภายในเอกสารได้

#### ถาม: องค์ประกอบโครงสร้างอินไลน์ช่วยสร้างลำดับชั้นเอกสารที่ชัดเจนได้อย่างไร

A: องค์ประกอบโครงสร้างแบบอินไลน์ เช่น หัวข้อที่มีระดับต่างๆ กัน จะช่วยสร้างลำดับชั้นที่ชัดเจนและกำหนดไว้อย่างชัดเจนในเอกสาร ผู้อ่านสามารถระบุหัวข้อหลัก หัวข้อย่อย และเนื้อหาที่เกี่ยวข้องได้อย่างรวดเร็ว ทำให้สามารถนำทางและทำความเข้าใจเอกสารได้ง่ายขึ้น

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏและการจัดรูปแบบขององค์ประกอบโครงสร้างอินไลน์โดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏและการจัดรูปแบบขององค์ประกอบโครงสร้างอินไลน์ได้ คุณสามารถตั้งค่าคุณสมบัติต่างๆ เช่น รูปแบบของแบบอักษร ขนาด สี การจัดตำแหน่ง การเยื้อง และระยะห่าง เพื่อให้ได้การนำเสนอภาพตามต้องการสำหรับหัวเรื่องและย่อหน้า

#### ถาม: ฉันจะสร้างและเพิ่มหัวเรื่องระดับต่างๆ ลงในเอกสาร PDF โดยใช้องค์ประกอบโครงสร้างอินไลน์ใน Aspose.PDF สำหรับ .NET ได้อย่างไร

 A: คุณสามารถสร้างหัวข้อระดับต่าง ๆ ได้โดยใช้`CreateHeaderElement`จากนั้นจึงผนวกเข้ากับองค์ประกอบโครงสร้างราก จากนั้นคุณสามารถเพิ่มเนื้อหาลงในองค์ประกอบหัวข้อแต่ละองค์ประกอบโดยใช้`CreateSpanElement` วิธีการสร้างช่วงของข้อความ

#### ถาม: ฉันสามารถใช้องค์ประกอบโครงสร้างอินไลน์เพื่อสร้างรายการ จุดหัวข้อ หรือประเภทการจัดระเบียบเนื้อหาอื่น ๆ ในเอกสาร PDF ได้หรือไม่

A: แม้ว่าองค์ประกอบโครงสร้างอินไลน์นั้นถูกใช้เป็นหลักสำหรับหัวเรื่องและย่อหน้า แต่คุณสามารถใช้องค์ประกอบดังกล่าวควบคู่ไปกับคุณลักษณะอื่นๆ ที่ Aspose.PDF สำหรับ .NET นำเสนอเพื่อสร้างรายการ จุดหัวข้อ ตาราง และประเภทอื่นๆ ของการจัดระเบียบเนื้อหาสำหรับโครงสร้างเอกสารที่ครอบคลุม

#### ถาม: องค์ประกอบโครงสร้างอินไลน์มีส่วนสนับสนุนต่อการเข้าถึงเอกสารอย่างไร

A: องค์ประกอบโครงสร้างแบบอินไลน์มีบทบาทสำคัญในการปรับปรุงการเข้าถึงเอกสาร หัวเรื่องและย่อหน้าที่จัดโครงสร้างอย่างเหมาะสมจะช่วยให้มีลำดับชั้นของเอกสารที่ชัดเจน ซึ่งช่วยให้โปรแกรมอ่านหน้าจอและเทคโนโลยีช่วยเหลืออื่นๆ สามารถตีความและถ่ายทอดเนื้อหาไปยังผู้ใช้ที่มีความทุพพลภาพได้อย่างถูกต้อง

#### ถาม: ฉันสามารถสำรวจการใช้งานขั้นสูงเพิ่มเติมขององค์ประกอบโครงสร้างอินไลน์ เช่น การสร้างองค์ประกอบแบบโต้ตอบหรือการฝังมัลติมีเดียได้หรือไม่

A: แน่นอน! แม้ว่าบทช่วยสอนนี้จะเน้นที่การสร้างหัวเรื่องและย่อหน้า แต่ Aspose.PDF สำหรับ .NET ก็มีคุณลักษณะขั้นสูงในการสร้างองค์ประกอบแบบโต้ตอบ ฝังมัลติมีเดีย เพิ่มไฮเปอร์ลิงก์ และอื่นๆ อีกมากมาย ตรวจสอบเอกสารและตัวอย่างของไลบรารีเพื่อเจาะลึกความสามารถขั้นสูงเหล่านี้