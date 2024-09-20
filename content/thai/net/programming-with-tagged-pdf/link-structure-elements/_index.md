---
title: องค์ประกอบโครงสร้างลิงก์
linktitle: องค์ประกอบโครงสร้างลิงก์
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีสร้างองค์ประกอบโครงสร้างลิงก์ใน PDF โดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนสำหรับการเพิ่มลิงก์ที่เข้าถึงได้ รูปภาพ และการตรวจสอบการปฏิบัติตามข้อกำหนด
type: docs
weight: 120
url: /th/net/programming-with-tagged-pdf/link-structure-elements/
---
## การแนะนำ

การสร้างและจัดการองค์ประกอบโครงสร้างลิงก์ภายใน PDF อาจมีความสำคัญสำหรับเอกสารที่ต้องการการเข้าถึงและการนำทางที่ราบรื่น ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับวิธีการดำเนินการนี้โดยใช้ Aspose.PDF สำหรับ .NET หากคุณเพิ่งเริ่มใช้ Aspose.PDF หรือการจัดการ PDF โดยทั่วไป ไม่ต้องกังวล ฉันจะอธิบายทุกขั้นตอนอย่างละเอียดเพื่อให้คุณทำตามได้ง่าย!

## ข้อกำหนดเบื้องต้น  

ก่อนที่เราจะลงลึกในการเขียนโค้ด เรามาทำความเข้าใจกับบางสิ่งก่อน นี่คือข้อกำหนดพื้นฐานที่จะช่วยให้ประสบการณ์การพัฒนาเป็นไปอย่างราบรื่น

1.  Aspose.PDF สำหรับ .NET: คุณสามารถดาวน์โหลดเวอร์ชันล่าสุดได้[ที่นี่](https://releases.aspose.com/pdf/net/).
2. สภาพแวดล้อมการพัฒนา .NET: ไม่ว่าจะเป็น Visual Studio หรือ IDE ที่เข้ากันได้กับ .NET ใดๆ ก็ติดตั้งไว้และพร้อมใช้งาน
3.  ใบอนุญาต Aspose: คุณสามารถใช้ Aspose.PDF เวอร์ชันทดลองใช้งานฟรีได้[ที่นี่](https://releases.aspose.com/) หรือได้รับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).
4. ความรู้พื้นฐานเกี่ยวกับ C#: เราจะทำงานกับโค้ด C# ดังนั้นการทำความเข้าใจพื้นฐานจะทำให้ทุกอย่างง่ายขึ้นมาก

## แพ็คเกจนำเข้า

คุณจะต้องนำเข้าแพ็คเกจสองสามรายการก่อนที่จะเขียนโค้ดสำหรับองค์ประกอบโครงสร้างลิงก์ เริ่มต้นด้วยการอ้างอิงไลบรารี Aspose.PDF ที่จำเป็นในโปรเจ็กต์ของคุณ:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

การนำเข้าเหล่านี้ช่วยให้เราทำงานกับเอกสาร PDF เพิ่มแท็ก และจัดการองค์ประกอบโครงสร้างได้

ตอนนี้เราจะสร้างเอกสาร PDF ที่มีโครงสร้างลิงก์หลายประเภท และเราจะแบ่งขั้นตอนแต่ละขั้นตอนออกเป็นส่วนๆ เพื่อช่วยให้คุณเข้าใจกระบวนการได้อย่างถ่องแท้

## ขั้นตอนที่ 1: เริ่มต้นเอกสาร  

เริ่มต้นด้วยการสร้างเอกสาร PDF ใหม่และตั้งค่าเนื้อหาที่แท็กไว้เพื่อการเข้าถึงได้

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// สร้างเอกสาร PDF ใหม่
Document document = new Document(); 

// ดึงข้อมูลอินเทอร์เฟซ TaggedContent
ITaggedContent taggedContent = document.TaggedContent;
```
  
 ที่นี่เราจะเริ่มต้น`Document` วัตถุซึ่งแสดงถึงไฟล์ PDF ของเรา นอกจากนี้ เรายังดึงข้อมูล`TaggedContent` อินเทอร์เฟซที่ช่วยให้เราเพิ่มองค์ประกอบโครงสร้างเช่นย่อหน้า ลิงก์ และรูปภาพ

## ขั้นตอนที่ 2: ตั้งชื่อเรื่องและภาษา  

ไฟล์ PDF ทุกไฟล์ควรมีการกำหนดชื่อและภาษา โดยเฉพาะอย่างยิ่งหากคุณต้องการให้เป็นไปตามมาตรฐาน PDF/UA

```csharp
// ตั้งค่าชื่อเอกสารและภาษา
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
ขั้นตอนนี้จะช่วยให้แน่ใจว่า PDF ของคุณมีชื่อที่มีความหมายและตั้งค่าภาษาเป็นภาษาอังกฤษ (`en-US`) ซึ่งถือเป็นสิ่งสำคัญสำหรับการเข้าถึงได้และช่วยให้แน่ใจว่าโปรแกรมอ่านหน้าจอหรือเทคโนโลยีช่วยเหลืออื่นสามารถตีความเอกสารของคุณได้อย่างถูกต้อง

## ขั้นตอนที่ 3: สร้างและผนวกย่อหน้า  

ในขั้นตอนนี้เราจะเพิ่มย่อหน้าเพื่อเก็บองค์ประกอบลิงก์ของเรา

```csharp
// สร้างองค์ประกอบราก
StructureElement rootElement = taggedContent.RootElement;

// สร้างย่อหน้าและเพิ่มลงในองค์ประกอบราก
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
เราสร้างองค์ประกอบโครงสร้างรากซึ่งโดยพื้นฐานแล้วเป็นคอนเทนเนอร์ระดับบนสุดสำหรับองค์ประกอบอื่นทั้งหมด จากนั้นเราสร้างย่อหน้า (`p1`) และผนวกเข้ากับองค์ประกอบราก

## ขั้นตอนที่ 4: เพิ่มลิงค์แบบง่าย  

ตอนนี้เรามาเพิ่มไฮเปอร์ลิงก์พื้นฐานที่ชี้ไปยัง Google กัน

```csharp
// สร้างองค์ประกอบลิงก์และเพิ่มลงในย่อหน้า
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

// ตั้งค่าไฮเปอร์ลิงก์และข้อความสำหรับลิงก์
link1.Hyperlink = new WebHyperlink("http://"google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
ในขั้นตอนนี้ เราสร้างองค์ประกอบลิงก์ ตั้งค่าไฮเปอร์ลิงก์เป็น "http://google.com" และใส่ข้อความ ("Google") ให้กับลิงก์ นอกจากนี้ เรายังเพิ่มคำอธิบายทางเลือกเพื่อให้เข้าถึงได้

## ขั้นตอนที่ 5: การเพิ่มลิงก์พร้อมสแปน  

เราสามารถสร้างลิงก์ด้วยข้อความช่วงต่างๆ กันได้

```csharp
// สร้างย่อหน้าใหม่
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

// สร้างลิงก์ด้วยองค์ประกอบสแปน
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://"google.com");

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
ที่นี่ เราใช้องค์ประกอบ span เพื่อล้อมรอบข้อความบางส่วนไว้ภายในลิงก์ ทำให้เราปรับแต่งลักษณะการแสดงส่วนต่างๆ ของลิงก์ได้

## ขั้นตอนที่ 6: การเชื่อมโยงหลายบรรทัด  

จะเกิดอะไรขึ้นหากข้อความลิงก์ของคุณยาวเกินไป ไม่ต้องกังวล คุณสามารถแบ่งข้อความออกเป็นหลายบรรทัดได้

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://"google.com");
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
ในกรณีนี้ เราได้สร้างลิงก์หลายบรรทัดโดยเพียงตั้งค่าข้อความยาว และข้อความจะห่อข้ามหลายบรรทัดโดยอัตโนมัติ

## ขั้นตอนที่ 7: เพิ่มรูปภาพลงในลิงก์  

สุดท้ายคุณสามารถเพิ่มรูปภาพภายในลิงค์ได้อีกด้วย

```csharp
// สร้างย่อหน้าใหม่และองค์ประกอบลิงค์
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://"google.com");

// เพิ่มรูปภาพลงในลิงค์
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
ขั้นตอนนี้จะแสดงวิธีปรับปรุงลิงก์ของคุณด้วยรูปภาพ ในกรณีนี้ เราได้เพิ่มไอคอน Google ไว้ภายในลิงก์ นอกจากนี้ เรายังทำให้เข้าถึงได้ง่ายขึ้นด้วยการตั้งค่าข้อความทางเลือกสำหรับรูปภาพ

## ขั้นตอนที่ 8: ตรวจสอบ PDF ว่าเป็นไปตามข้อกำหนดหรือไม่  

หากคุณต้องการให้เป็นไปตามมาตรฐาน PDF/UA (มาตรฐานการเข้าถึง) การตรวจสอบความถูกต้องของเอกสารถือเป็นแนวทางปฏิบัติที่ดี

```csharp
// บันทึกเอกสาร PDF
document.Save(outFile);

// ตรวจสอบเอกสารให้เป็นไปตาม PDF/UA
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
เราบันทึกเอกสารและตรวจสอบเทียบกับมาตรฐาน PDF/UA ซึ่งทำให้แน่ใจได้ว่า PDF ตรงตามข้อกำหนดการเข้าถึง

## บทสรุป  

ในบทช่วยสอนนี้ เราได้กล่าวถึงวิธีการสร้างเอกสาร PDF ที่มีโครงสร้างโดยใช้ Aspose.PDF สำหรับ .NET ตั้งแต่การเพิ่มไฮเปอร์ลิงก์พื้นฐานไปจนถึงโครงสร้างที่ซับซ้อนยิ่งขึ้น เช่น สแปน ลิงก์หลายบรรทัด และแม้แต่รูปภาพ คู่มือนี้ให้พื้นฐานที่มั่นคงสำหรับการจัดการองค์ประกอบลิงก์ใน PDF ของคุณ ด้วยประโยชน์เพิ่มเติมของการปฏิบัติตาม PDF/UA ตอนนี้คุณจึงพร้อมแล้วที่จะสร้าง PDF ที่เข้าถึงได้และนำทางได้

## คำถามที่พบบ่อย

### ฉันสามารถเพิ่มโครงสร้างที่ซับซ้อนมากขึ้น เช่น ตาราง ภายในลิงก์ได้หรือไม่  
ไม่ ลิงก์ส่วนใหญ่เป็นข้อความและรูปภาพ แต่คุณสามารถฝังองค์ประกอบที่ซับซ้อนไว้ใกล้ๆ ได้

### การตรวจสอบ PDF/UA เป็นสิ่งที่จำเป็นหรือไม่  
ไม่เสมอไป แต่ขอแนะนำอย่างยิ่งหากคุณกังวลเกี่ยวกับการเข้าถึง

### จะเกิดอะไรขึ้นถ้าเส้นทางไฟล์ภาพไม่ถูกต้อง?  
เอกสารจะไม่แสดงรูปภาพ และอาจเกิดข้อผิดพลาดระหว่างการเรนเดอร์

### ฉันสามารถกำหนดรูปแบบข้อความภายในลิงค์ได้ไหม  
ใช่ คุณสามารถใช้รูปแบบข้อความด้วยการใช้องค์ประกอบ span ได้

### สามารถสร้างลิงก์เอกสารภายในได้หรือไม่  
แน่นอน! คุณสามารถลิงก์ไปยังส่วนที่เจาะจงภายในเอกสารเดียวกันได้