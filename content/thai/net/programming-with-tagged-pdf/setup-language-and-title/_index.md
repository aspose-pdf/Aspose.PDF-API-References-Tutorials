---
title: ตั้งค่าภาษาและชื่อเรื่อง
linktitle: ตั้งค่าภาษาและชื่อเรื่อง
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: คู่มือทีละขั้นตอนในการกำหนดค่าภาษาและหัวเรื่องของเอกสาร PDF ด้วย Aspose.PDF สำหรับ .NET สร้างเอกสารหลายภาษาที่เป็นส่วนตัว
type: docs
weight: 140
url: /th/net/programming-with-tagged-pdf/setup-language-and-title/
---
ในคู่มือนี้ เราจะบอกคุณถึงวิธีการกำหนดค่าภาษาและหัวเรื่องของเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET Aspose.PDF เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณสร้าง จัดการ และแปลงไฟล์ PDF ได้ด้วยการเขียนโปรแกรม

มาเจาะลึกโค้ดและเรียนรู้วิธีการกำหนดค่าภาษาและหัวเรื่องของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET กัน

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณได้ติดตั้ง Aspose.PDF สำหรับ .NET และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณแล้ว

## ขั้นตอนที่ 1: การสร้างเอกสาร

 ขั้นตอนแรกคือการสร้างเอกสาร PDF ใหม่โดยใช้`Document` ระดับ.

```csharp
// สร้างเอกสาร PDF
Document document = new Document();
```

## ขั้นตอนที่ 2: เข้าถึงเนื้อหาที่ถูกแท็ก

 ต่อไปเราเข้าถึงเนื้อหาที่แท็กของเอกสารโดยใช้`ITaggedContent` วัตถุ.

```csharp
// เข้าถึงเนื้อหาที่ถูกแท็ก
Tagged.ITaggedContent taggedContent = document.TaggedContent;
```

## ขั้นตอนที่ 3: ตั้งชื่อเรื่องและภาษา

 ตอนนี้เราสามารถตั้งชื่อเอกสารและภาษาได้โดยใช้`SetTitle` และ`SetLanguage` วิธีการของ`ITaggedContent` วัตถุ.

```csharp
// กำหนดชื่อเอกสาร
taggedContent.SetTitle("Example of tagged document");

// ตั้งค่าภาษาเอกสาร
taggedContent.SetLanguage("fr-FR");
```

## ขั้นตอนที่ 4: เพิ่มเนื้อหาหลายภาษา

ถัดไป เราจะเพิ่มเนื้อหาหลายภาษาลงในเอกสารโดยใช้องค์ประกอบย่อหน้าสำหรับแต่ละภาษา

```csharp
// เพิ่มย่อหน้าเป็นภาษาอังกฤษ
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// เพิ่มย่อหน้าเป็นภาษาเยอรมัน
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hello Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

//เพิ่มย่อหน้าเป็นภาษาฝรั่งเศส
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Hello world!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// เพิ่มย่อหน้าในภาษาสเปน
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);
```

## ขั้นตอนที่ 5: บันทึกเอกสาร PDF ที่ถูกแท็ก

ในที่สุดเราก็บันทึกเอกสาร PDF ที่ถูกแท็ก

```csharp
// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "SetupLanguageAndTitle.pdf");
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการตั้งค่าภาษาและชื่อโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp

Document document = new Document();

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// รับเนื้อหาที่ถูกแท็ก
Tagged.ITaggedContent taggedContent = document.TaggedContent;

// ตั้งค่าชื่อและภาษา
taggedContent.SetTitle("Example Tagged Document");
taggedContent.SetLanguage("en-US");

// ส่วนหัว (en-US, สืบทอดจากเอกสาร)
LogicalStructure.HeaderElement h1 = taggedContent.CreateHeaderElement(1);
h1.SetText("Phrase on different languages");
taggedContent.RootElement.AppendChild(h1);

// ย่อหน้า (ภาษาอังกฤษ)
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// ย่อหน้า (ภาษาเยอรมัน)
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hallo Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// ย่อหน้า (ภาษาฝรั่งเศส)
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Bonjour le monde!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// ย่อหน้า (ภาษาสเปน)
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);

// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "SetupLanguageAndTitle.pdf");

```

## บทสรุป

ขอแสดงความยินดี! ตอนนี้คุณทราบวิธีการกำหนดค่าภาษาและหัวเรื่องของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET แล้ว คุณสามารถศึกษาคุณลักษณะของ Aspose.PDF เพิ่มเติมเพื่อสร้างเอกสาร PDF ที่เป็นส่วนตัวและมีหลายภาษาได้

### คำถามที่พบบ่อย

#### ถาม: การกำหนดค่าภาษาและชื่อเอกสาร PDF มีความสำคัญอย่างไร

ก: การกำหนดค่าภาษาและชื่อเรื่องของเอกสาร PDF เป็นสิ่งสำคัญสำหรับการเข้าถึงและเมตาดาต้า การตั้งค่าภาษาที่ถูกต้องจะช่วยให้แท็กภาษาและการแยกข้อความออกมาถูกต้อง ในขณะที่การกำหนดชื่อเรื่องที่เหมาะสมจะช่วยให้ระบุและจัดระเบียบเอกสารได้ดีขึ้น

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยอำนวยความสะดวกในการกำหนดค่าภาษาและชื่อเอกสารได้อย่างไร

 A: Aspose.PDF สำหรับ .NET มี API ที่สามารถตั้งค่าชื่อเอกสารและภาษาได้อย่างง่ายดายโดยใช้`SetTitle` และ`SetLanguage` วิธีการของ`ITaggedContent` วัตถุ ซึ่งจะช่วยให้คุณมั่นใจได้ว่าการแสดงภาษาจะมีความถูกต้องและชื่อเอกสารมีความหมาย

#### ถาม: ฉันสามารถตั้งค่าภาษาต่างๆ สำหรับส่วนเฉพาะของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

 A: ใช่ คุณสามารถตั้งค่าภาษาต่างๆ สำหรับส่วนเฉพาะของเอกสาร PDF ได้โดยใช้ Aspose.PDF สำหรับ .NET โดยการใช้`Language` คุณสมบัติสำหรับองค์ประกอบย่อหน้า คุณสามารถระบุภาษาสำหรับแต่ละส่วนของเนื้อหาได้ ทำให้สามารถใช้งานเอกสารหลายภาษาได้

#### ถาม: เหตุใดเนื้อหาหลายภาษาจึงมีความสำคัญ และฉันสามารถเพิ่มเนื้อหาเหล่านั้นลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

A: เนื้อหาหลายภาษาช่วยเพิ่มการเข้าถึงและการเข้าถึงทั่วโลกของเอกสาร PDF Aspose.PDF สำหรับ .NET ช่วยให้คุณสามารถเพิ่มเนื้อหาหลายภาษาได้โดยการสร้างองค์ประกอบย่อหน้าสำหรับแต่ละภาษา และตั้งค่าคุณสมบัติข้อความและภาษาให้เหมาะสม

####  ถาม: ทำอย่างไร`SetTitle` method contribute to improving document accessibility and organization?

 ก. การ`SetTitle` วิธีการนี้กำหนดชื่อเอกสาร PDF ซึ่งใช้สำหรับระบุเอกสาร ค้นหาผลลัพธ์ และจัดระเบียบเอกสาร การให้ชื่อที่ชัดเจนและมีความหมายจะช่วยเพิ่มการเข้าถึงเอกสารและปรับปรุงประสบการณ์ของผู้ใช้

####  ถาม: บทบาทของมันคืออะไร`SetLanguage` method in PDF document configuration?

 ก. การ`SetLanguage` วิธีการนี้จะตั้งค่าภาษาเริ่มต้นสำหรับเอกสาร PDF เพื่อให้แน่ใจว่าแท็กภาษาและการแยกข้อความมีความถูกต้องแม่นยำ ช่วยรักษาความสอดคล้องของภาษาและการเข้าถึงได้ทั่วทั้งเอกสาร

#### ถาม: ฉันสามารถใช้ Aspose.PDF สำหรับ .NET เพื่อตั้งค่าชื่อเอกสารและภาษาแบบไดนามิกตามการตั้งค่าของผู้ใช้ได้หรือไม่

A: ใช่ คุณสามารถกำหนดชื่อเอกสารและภาษาแบบไดนามิกได้ตามความต้องการของผู้ใช้โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถปรับแต่งชื่อเอกสารและภาษาได้ตามต้องการโดยการผสานข้อมูลอินพุตของผู้ใช้หรือข้อมูลระบบ

#### ถาม: ฉันจะตรวจสอบได้อย่างไรว่าการกำหนดค่าภาษาและชื่อเรื่องได้ถูกนำไปใช้กับเอกสาร PDF อย่างถูกต้องหรือไม่

A: คุณสามารถตรวจสอบการกำหนดค่าภาษาและชื่อเรื่องได้โดยตรวจสอบคุณสมบัติและข้อมูลเมตาของเอกสาร PDF นอกจากนี้ คุณยังสามารถใช้โปรแกรมดู PDF หรือเครื่องมือแยกข้อความเพื่อให้แน่ใจว่าการแท็กภาษาและชื่อเรื่องเอกสารนั้นถูกต้อง

#### ถาม: มีแนวทางปฏิบัติที่ดีที่สุดใดๆ ที่ควรปฏิบัติตามเมื่อกำหนดค่าภาษาและหัวเรื่องของเอกสาร PDF หรือไม่

ก: เมื่อกำหนดค่าภาษาและชื่อเรื่อง ให้พิจารณาถึงกลุ่มเป้าหมาย เนื้อหาของเอกสาร และข้อกำหนดด้านการเข้าถึง เลือกชื่อเรื่องที่อธิบายได้ดีและการตั้งค่าภาษาที่ถูกต้องเพื่อปรับปรุงการใช้งานและการเข้าถึงเอกสาร

#### ถาม: ฉันสามารถปรับเปลี่ยนภาษาและหัวเรื่องของเอกสาร PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

 A: ใช่ คุณสามารถปรับเปลี่ยนภาษาและชื่อของเอกสาร PDF ที่มีอยู่ได้โดยใช้ Aspose.PDF สำหรับ .NET โดยการโหลดเอกสาร เข้าถึงเนื้อหาที่แท็ก และใช้`SetTitle` และ`SetLanguage`วิธีการคุณสามารถอัปเดตคุณลักษณะเหล่านี้ตามต้องการได้
