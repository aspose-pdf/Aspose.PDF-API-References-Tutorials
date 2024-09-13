---
title: องค์ประกอบโครงสร้างลิงก์
linktitle: องค์ประกอบโครงสร้างลิงก์
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: คู่มือทีละขั้นตอนในการใช้องค์ประกอบโครงสร้างลิงก์กับ Aspose.PDF สำหรับ .NET สร้างไฮเปอร์ลิงก์ในเอกสาร PDF ของคุณ
type: docs
weight: 120
url: /th/net/programming-with-tagged-pdf/link-structure-elements/
---
ในคู่มือทีละขั้นตอนนี้ เราจะแสดงวิธีใช้องค์ประกอบโครงสร้างลิงก์กับ Aspose.PDF สำหรับ .NET Aspose.PDF เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณสร้างและจัดการเอกสาร PDF ได้ด้วยโปรแกรม องค์ประกอบโครงสร้างลิงก์ช่วยให้คุณสามารถเพิ่มไฮเปอร์ลิงก์ไปยังเอกสาร PDF ของคุณ ทำให้ผู้ใช้สามารถคลิกลิงก์และนำทางไปยังแหล่งข้อมูลออนไลน์ได้

มาเจาะลึกโค้ดและเรียนรู้วิธีใช้องค์ประกอบโครงสร้างลิงก์ใน Aspose.PDF สำหรับ .NET กัน

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
2. ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ในการเริ่มต้น ให้เปิดสภาพแวดล้อมการพัฒนา C# ของคุณและสร้างโปรเจ็กต์ใหม่ ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET ในโปรเจ็กต์ของคุณแล้ว

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
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
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## ขั้นตอนที่ 5: เพิ่มองค์ประกอบโครงสร้างลิงก์

ตอนนี้เรามาเพิ่มองค์ประกอบโครงสร้างลิงก์ในเอกสารกัน เราจะสร้างลิงก์ประเภทต่างๆ รวมถึงลิงก์ข้อความธรรมดา ลิงก์รูปภาพ และลิงก์หลายบรรทัด
```csharp
// รับองค์ประกอบโครงสร้างราก (องค์ประกอบโครงสร้างเอกสาร)
StructureElement rootElement = taggedContent.RootElement;

// เพิ่มย่อหน้าด้วยไฮเปอร์ลิงก์
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://"google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// เพิ่มย่อหน้าด้วยไฮเปอร์ลิงก์ที่มีข้อความที่หลากหลาย
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://"google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// เพิ่มย่อหน้าด้วยไฮเปอร์ลิงก์ที่มีข้อความที่จัดรูปแบบบางส่วน
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://"google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// เพิ่มย่อหน้าด้วยไฮเปอร์ลิงก์หลายบรรทัด
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://"google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// เพิ่มย่อหน้าด้วยไฮเปอร์ลิงก์ที่มีรูปภาพ
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://"google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## ขั้นตอนที่ 6: บันทึกเอกสาร PDF ที่ถูกแท็ก

ในที่สุดเราก็บันทึกเอกสาร PDF ที่ถูกแท็ก

```csharp
// บันทึกเอกสาร PDF ที่ถูกแท็ก
document. Save(outFile);
```

## ขั้นตอนที่ 7: ตรวจสอบความสอดคล้องของ PDF/UA

 เราสามารถตรวจสอบเอกสารเพื่อให้เป็นไปตามมาตรฐาน PDF/UA ได้โดยใช้`Validate` วิธีการของ`Document` ระดับ.

```csharp
// ตรวจสอบความสอดคล้องของ PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### ตัวอย่างโค้ดต้นฉบับสำหรับองค์ประกอบโครงสร้างลิงก์โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

//การสร้างเอกสารและการรับเนื้อหา PDF ที่ถูกแท็ก
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// การตั้งชื่อเรื่องและภาษาธรรมชาติของเอกสาร
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// การรับองค์ประกอบโครงสร้างราก (องค์ประกอบโครงสร้างเอกสาร)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://"google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://"google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://"google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://"google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://"google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(outFile);

// การตรวจสอบความสอดคล้องของ PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีใช้องค์ประกอบโครงสร้างลิงก์กับ Aspose.PDF สำหรับ .NET แล้ว ตอนนี้คุณสามารถสร้างไฮเปอร์ลิงก์ในเอกสาร PDF ของคุณ ช่วยให้ผู้ใช้นำทางไปยังแหล่งข้อมูลออนไลน์ได้ ทดลองใช้และสำรวจฟีเจอร์เพิ่มเติมของ Aspose.PDF เพื่อสร้างเอกสาร PDF แบบโต้ตอบและสมบูรณ์ยิ่งขึ้น

### คำถามที่พบบ่อย

#### ถาม: องค์ประกอบโครงสร้างลิงก์ในเอกสาร PDF คืออะไร และช่วยปรับปรุงการโต้ตอบของเอกสารได้อย่างไร

A: องค์ประกอบโครงสร้างลิงก์ในเอกสาร PDF ใช้เพื่อสร้างไฮเปอร์ลิงก์ที่ให้ผู้ใช้นำทางไปยังแหล่งข้อมูลออนไลน์หรือตำแหน่งเฉพาะภายในเอกสาร องค์ประกอบเหล่านี้ช่วยเพิ่มการโต้ตอบโดยจัดให้มีลิงก์ที่คลิกได้ซึ่งช่วยให้ผู้ใช้สามารถเข้าถึงเนื้อหาที่เกี่ยวข้องหรือเว็บไซต์ภายนอกได้

#### ถาม: องค์ประกอบโครงสร้างลิงก์สามารถเป็นประโยชน์ในเอกสาร PDF ได้อย่างไร

A: องค์ประกอบโครงสร้างลิงก์ช่วยปรับปรุงประสบการณ์ของผู้ใช้โดยทำให้เอกสาร PDF เป็นแบบโต้ตอบได้ ช่วยให้เข้าถึงข้อมูลเพิ่มเติม เนื้อหาที่เกี่ยวข้อง เว็บไซต์ภายนอก หรือส่วนเฉพาะภายในเอกสารได้อย่างรวดเร็ว ช่วยปรับปรุงการนำทางและอำนวยความสะดวกในการดึงข้อมูล

#### ถาม: ฉันสามารถสร้างไฮเปอร์ลิงก์ประเภทต่างๆ โดยใช้องค์ประกอบโครงสร้างลิงก์ใน Aspose.PDF สำหรับ .NET ได้หรือไม่

A: ใช่ คุณสามารถสร้างไฮเปอร์ลิงก์ประเภทต่างๆ ได้โดยใช้องค์ประกอบโครงสร้างลิงก์ Aspose.PDF สำหรับ .NET ช่วยให้คุณสร้างไฮเปอร์ลิงก์ที่มีข้อความธรรมดา ข้อความที่มีรูปแบบ รูปภาพ และคำอธิบายหลายบรรทัด ทำให้คุณสามารถลิงก์ไปยังเนื้อหาภายนอกหรือตำแหน่งต่างๆ ภายในเอกสารได้อย่างหลากหลาย

#### ถาม: ฉันจะตั้งค่าและเริ่มต้นองค์ประกอบโครงสร้างลิงก์ในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 ก: หากต้องการใช้องค์ประกอบโครงสร้างลิงก์ ก่อนอื่นคุณต้องสร้างเอกสาร PDF ใหม่โดยใช้`Document` คลาส จากนั้นรับเนื้อหาที่แท็กโดยใช้`TaggedContent`คุณสมบัติของเอกสาร จากนั้น คุณสามารถสร้างและปรับแต่งองค์ประกอบโครงสร้างลิงก์และเพิ่มลงในองค์ประกอบโครงสร้างรากได้

#### ถาม: ฉันจะสร้างไฮเปอร์ลิงก์ข้อความธรรมดาโดยใช้องค์ประกอบโครงสร้างลิงก์ได้อย่างไร
 A: คุณสามารถสร้างไฮเปอร์ลิงก์ข้อความธรรมดาได้โดยการสร้าง`LinkElement` และการตั้งค่าของมัน`Hyperlink` ทรัพย์สินให้กับ`WebHyperlink` ด้วย URL ที่คุณต้องการลิงก์ไป คุณยังสามารถตั้งค่าข้อความแสดงของลิงก์ได้โดยใช้`SetText` วิธี.

#### ถาม: เป็นไปได้ไหมที่จะสร้างไฮเปอร์ลิงก์ด้วยรูปภาพโดยใช้องค์ประกอบโครงสร้างลิงก์?

 A: ใช่ คุณสามารถสร้างไฮเปอร์ลิงก์ด้วยรูปภาพโดยใช้องค์ประกอบโครงสร้างลิงก์ คุณจะสร้าง`LinkElement` แล้วจึงผนวก`FigureElement` โดยมีรูปภาพประกอบ วิธีนี้ช่วยให้คุณสร้างไฮเปอร์ลิงก์ที่อิงตามรูปภาพได้

#### ถาม: ฉันจะมั่นใจได้อย่างไรว่าเอกสาร PDF ของฉันที่มีไฮเปอร์ลิงก์เป็นไปตามมาตรฐาน PDF/UA สำหรับการเข้าถึงได้

 A: Aspose.PDF สำหรับ .NET ให้ความสามารถในการตรวจสอบความสอดคล้องของเอกสาร PDF ของคุณกับมาตรฐาน PDF/UA โดยใช้`Validate` วิธีการของ`Document`คลาส ซึ่งจะทำให้มั่นใจได้ว่าผู้ใช้ที่มีความทุพพลภาพสามารถเข้าถึงไฮเปอร์ลิงก์ของเอกสารได้

#### ถาม: คำอธิบายอื่นๆ สำหรับองค์ประกอบโครงสร้างลิงก์คืออะไร และเหตุใดจึงมีความสำคัญ?

A: คำอธิบายทางเลือก (ข้อความอื่น) สำหรับองค์ประกอบโครงสร้างลิงก์จะให้คำอธิบายข้อความของไฮเปอร์ลิงก์ คำอธิบายเหล่านี้มีความสำคัญต่อการเข้าถึง ช่วยให้ผู้ใช้ที่มีความบกพร่องทางสายตาเข้าใจวัตถุประสงค์และปลายทางของลิงก์ได้

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏและลักษณะการทำงานของไฮเปอร์ลิงก์ที่สร้างโดยใช้องค์ประกอบโครงสร้างลิงก์ได้หรือไม่

A: แม้ว่าองค์ประกอบโครงสร้างลิงก์จะเน้นไปที่การสร้างไฮเปอร์ลิงก์เป็นหลัก แต่คุณสามารถปรับแต่งลักษณะที่ปรากฏและพฤติกรรมของไฮเปอร์ลิงก์เพิ่มเติมได้โดยใช้ฟีเจอร์อื่นๆ ที่ Aspose.PDF สำหรับ .NET นำเสนอ ซึ่งรวมถึงการระบุสี สไตล์ และการดำเนินการของลิงก์

#### ถาม: องค์ประกอบโครงสร้างลิงก์มีส่วนช่วยให้เอกสาร PDF มีการโต้ตอบและเป็นมิตรต่อผู้ใช้มากขึ้นได้อย่างไร

A: องค์ประกอบโครงสร้างลิงก์จะเปลี่ยนเอกสาร PDF แบบคงที่ให้กลายเป็นประสบการณ์แบบโต้ตอบได้โดยการเพิ่มไฮเปอร์ลิงก์ที่คลิกได้ การโต้ตอบนี้ช่วยเพิ่มการมีส่วนร่วมของผู้ใช้ ช่วยให้สามารถนำทางระหว่างเนื้อหาที่เกี่ยวข้องได้อย่างราบรื่น และปรับปรุงการใช้งานเอกสารโดยรวม