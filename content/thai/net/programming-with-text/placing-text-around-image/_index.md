---
title: การวางข้อความรอบรูปภาพในไฟล์ PDF
linktitle: การวางข้อความรอบรูปภาพในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีวางข้อความรอบ ๆ รูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 260
url: /th/net/programming-with-text/placing-text-around-image/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการวางข้อความรอบ ๆ รูปภาพในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะอธิบายกระบวนการทีละขั้นตอนในการสร้างตาราง การเพิ่มรูปภาพ และการวางตำแหน่งข้อความรอบ ๆ รูปภาพโดยใช้โค้ดต้นฉบับ C# ที่ให้มา

## ความต้องการ

ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

 ขั้นแรก คุณต้องตั้งค่าเส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไดเร็กทอรีที่คุณต้องการ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารและหน้า

 ถัดไปเราจะสร้าง`Document` วัตถุและเพิ่มหน้าโดยใช้`Pages.Add()` วิธี.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 3: สร้างตาราง

 เราสร้างตารางโดยใช้`Table` คลาสและเพิ่มลงในคอลเล็กชั่นย่อหน้าของหน้า

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## ขั้นตอนที่ 4: ตั้งค่าความกว้างและระยะขอบของคอลัมน์ตาราง

 เรากำหนดความกว้างของคอลัมน์ของตารางและสร้าง`MarginInfo` วัตถุที่จะกำหนดระยะขอบ

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## ขั้นตอนที่ 5: เพิ่มรูปภาพลงในตาราง

 เราสร้าง`Image` วัตถุ ระบุเส้นทางไฟล์ภาพ และตั้งค่าความสูงและความกว้างคงที่ของภาพ จากนั้น เพิ่มภาพลงในคอลเล็กชันย่อหน้าของเซลล์ตาราง

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## ขั้นตอนที่ 6: เพิ่มข้อความรอบ ๆ รูปภาพ

 เราสร้างตัวแปรสตริงที่มีข้อความที่จัดรูปแบบ HTML และสร้าง`HtmlFragment`วัตถุ จากนั้นเราเพิ่มข้อความ HTML ลงในเซลล์ตารางที่มีรูปภาพ

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## ขั้นตอนที่ 7: เพิ่มข้อความเพิ่มเติม

 เราสร้างอีกอย่างหนึ่ง`HtmlFragment` วัตถุที่มีข้อความในรูปแบบ HTML เพิ่มเติมและเพิ่มลงในเซลล์ตารางแยกต่างหาก

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## ขั้นตอนที่ 8: บันทึกเอกสาร PDF

สุดท้ายเราบันทึกเอกสาร PDF ลงในไฟล์เอาท์พุตที่ระบุ

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### ตัวอย่างโค้ดที่มาสำหรับการวางข้อความรอบภาพโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างอินสแตนซ์ของวัตถุเอกสาร
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// สร้างหน้าใน Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// สร้างอินสแตนซ์ของวัตถุตาราง
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// เพิ่มตารางในคอลเลกชันย่อหน้าของส่วนที่ต้องการ
page.Paragraphs.Add(table1);
// ตั้งค่าด้วยความกว้างของคอลัมน์ของตาราง
table1.ColumnWidths = "120 270";
// สร้างวัตถุ MarginInfo และตั้งค่าระยะขอบซ้าย ล่าง ขวา และบน
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// ตั้งค่าการเติมเซลล์เริ่มต้นเป็นวัตถุ MarginInfo
table1.DefaultCellPadding = margin;
// สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
Aspose.Pdf.Row row1 = table1.Rows.Add();
// สร้างวัตถุภาพ
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// ระบุเส้นทางไฟล์ภาพ
logo.File = dataDir + "aspose-logo.jpg";
// ระบุภาพความสูงคงที่
logo.FixHeight = 120;
// ระบุความกว้างของภาพคงที่
logo.FixWidth = 110;
row1.Cells.Add();
// เพิ่มรูปภาพลงในคอลเล็กชั่นย่อหน้าของเซลล์ตาราง
row1.Cells[0].Paragraphs.Add(logo);
// สร้างตัวแปรสตริงด้วยข้อความที่มีแท็ก HTML
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//สร้างวัตถุข้อความที่จะเพิ่มทางด้านขวาของรูปภาพ
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// เพิ่มย่อหน้าข้อความที่มีข้อความ HTML ลงในเซลล์ตาราง
row1.Cells[1].Paragraphs.Add(TitleText);
// ตั้งค่าการจัดแนวแนวตั้งของเนื้อหาแถวเป็นด้านบน
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
//สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// ตั้งค่าช่วงแถวสำหรับแถวที่ 2 เป็น 2
SecondRow.Cells[0].ColSpan = 2;
// ตั้งค่าการจัดแนวแนวตั้งของแถวที่ 2 เป็นด้านบน
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// เพิ่มย่อหน้าข้อความที่มีข้อความ HTML ลงในเซลล์ตาราง
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// บันทึกไฟล์ PDF
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการวางข้อความรอบ ๆ รูปภาพในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โดยปฏิบัติตามคำแนะนำทีละขั้นตอนและดำเนินการตามโค้ด C# ที่ให้มา คุณก็สามารถสร้างตาราง เพิ่มรูปภาพ และจัดตำแหน่งข้อความรอบ ๆ รูปภาพในเอกสาร PDF ได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "การวางข้อความรอบรูปภาพในไฟล์ PDF" คืออะไร

A: บทช่วยสอน "การวางข้อความรอบรูปภาพในไฟล์ PDF" สาธิตวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อวางข้อความรอบรูปภาพในเอกสาร PDF บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนและโค้ดต้นฉบับ C# เพื่อช่วยคุณสร้างตาราง เพิ่มรูปภาพ และจัดตำแหน่งข้อความรอบรูปภาพ

#### ถาม: เหตุใดฉันจึงต้องวางข้อความรอบ ๆ รูปภาพในเอกสาร PDF

A: การวางข้อความรอบรูปภาพจะช่วยให้การนำเสนอเอกสาร PDF ของคุณดูดีขึ้น ทำให้ดึงดูดใจและให้ข้อมูลมากขึ้น เทคนิคนี้มักใช้กับเอกสาร โบรชัวร์ รายงาน และสื่ออื่นๆ ที่คุณต้องการรวมรูปภาพและข้อความเข้าด้วยกันในลักษณะที่สวยงาม

#### ถาม: ฉันจะตั้งค่าไดเรกทอรีเอกสารได้อย่างไร?

ก: การตั้งค่าไดเรกทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น

#### ถาม: ฉันจะสร้างตารางและเพิ่มรูปภาพลงไปได้อย่างไร?

 A: บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการสร้างตารางโดยใช้`Table` คลาสและการเพิ่มรูปภาพลงในตารางโดยใช้`Image` คลาส คุณจะต้องระบุเส้นทางไฟล์รูปภาพ ความสูง และความกว้างก่อนที่จะเพิ่มลงในเซลล์ตาราง

#### ถาม: ฉันจะวางตำแหน่งข้อความรอบ ๆ รูปภาพได้อย่างไร

 ก: ในการวางตำแหน่งข้อความรอบ ๆ รูปภาพ คุณจะต้องสร้างข้อความที่จัดรูปแบบ HTML โดยใช้`HtmlFragment` คลาส ข้อความนี้จะมีทั้งข้อความชื่อเรื่องและเนื้อหา จากนั้นคุณจะเพิ่มข้อความ HTML นี้ลงในเซลล์ตารางที่อยู่ติดกับเซลล์รูปภาพ

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของข้อความและรูปภาพได้ไหม

A: ใช่ คุณสามารถปรับแต่งลักษณะของข้อความและรูปภาพได้โดยใช้แท็กและคุณสมบัติ HTML ตัวอย่างเช่น คุณสามารถกำหนดขนาดแบบอักษร สี สไตล์ และการจัดตำแหน่งของข้อความได้ นอกจากนี้ คุณยังสามารถปรับขนาดและมิติของรูปภาพได้อีกด้วย

#### ถาม: ฉันจะบันทึกเอกสาร PDF ได้อย่างไร

 A: หลังจากเพิ่มรูปภาพและข้อความลงในตารางแล้ว คุณสามารถบันทึกเอกสาร PDF โดยใช้`Save` วิธีการของ`Document` คลาส ระบุเส้นทางไฟล์เอาท์พุตที่ต้องการเป็นอาร์กิวเมนต์ของ`Save` วิธี.

#### ถาม: ผลลัพธ์ที่คาดหวังจากบทช่วยสอนนี้คืออะไร?

A: เมื่อทำตามบทช่วยสอนและดำเนินการตามโค้ด C# ที่ให้มา คุณจะสร้างเอกสาร PDF ที่สาธิตวิธีการวางข้อความรอบ ๆ รูปภาพ เอกสารเอาต์พุตจะมีตารางพร้อมรูปภาพและข้อความวางอยู่รอบ ๆ

#### ถาม: ฉันสามารถใช้รูปแบบรูปภาพอื่นนอกจาก JPG ได้หรือไม่?

 A: ใช่ คุณสามารถใช้รูปแบบภาพต่างๆ ที่รองรับโดยไลบรารี Aspose.PDF เช่น PNG, BMP, GIF และอื่นๆ เมื่อสร้างไฟล์`Image` วัตถุ ระบุเส้นทางไฟล์ของรูปแบบภาพที่ต้องการ

#### ถาม: จำเป็นต้องมีใบอนุญาต Aspose ที่ถูกต้องสำหรับบทช่วยสอนนี้หรือไม่

A: ใช่ ต้องมีใบอนุญาต Aspose ที่ถูกต้องเพื่อให้บทช่วยสอนนี้ทำงานได้อย่างถูกต้อง คุณสามารถซื้อใบอนุญาตเต็มรูปแบบหรือรับใบอนุญาตชั่วคราว 30 วันได้จากเว็บไซต์ Aspose