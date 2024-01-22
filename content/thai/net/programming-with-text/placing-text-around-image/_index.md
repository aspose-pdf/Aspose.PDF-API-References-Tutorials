---
title: การวางข้อความรอบภาพในไฟล์ PDF
linktitle: การวางข้อความรอบภาพในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีวางข้อความรอบรูปภาพในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 260
url: /th/net/programming-with-text/placing-text-around-image/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีวางข้อความรอบรูปภาพในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะดำเนินการทีละขั้นตอนในการสร้างตาราง การเพิ่มรูปภาพ และการวางตำแหน่งข้อความรอบๆ รูปภาพโดยใช้ซอร์สโค้ด C# ที่ให้มา

## ความต้องการ

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร

 ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir`ตัวแปรพร้อมเส้นทางไปยังไดเร็กทอรีที่คุณต้องการ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารและหน้า

 ต่อไปเราจะสร้าง a`Document` object และเพิ่มหน้าเข้าไปโดยใช้`Pages.Add()` วิธี.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 3: สร้างตาราง

 เราสร้างตารางโดยใช้`Table` และเพิ่มลงในคอลเลกชันย่อหน้าของเพจ

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## ขั้นตอนที่ 4: ตั้งค่าความกว้างและระยะขอบของคอลัมน์ตาราง

 เรากำหนดความกว้างของคอลัมน์ของตารางและสร้าง`MarginInfo` วัตถุเพื่อกำหนดระยะขอบ

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

 เราสร้าง`Image` object ระบุพาธของไฟล์รูปภาพ และตั้งค่าความสูงและความกว้างคงที่ของรูปภาพ จากนั้น เราเพิ่มรูปภาพลงในคอลเลกชันย่อหน้าของเซลล์ตาราง

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## ขั้นตอนที่ 6: เพิ่มข้อความรอบภาพ

 เราสร้างตัวแปรสตริงที่มีข้อความในรูปแบบ HTML และสร้าง`HtmlFragment`วัตถุ. จากนั้นเราเพิ่มข้อความ HTML ลงในเซลล์ตารางที่มีรูปภาพ

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## ขั้นตอนที่ 7: เพิ่มข้อความเพิ่มเติม

 เราสร้างอีก`HtmlFragment` วัตถุที่มีข้อความรูปแบบ HTML เพิ่มเติมและเพิ่มลงในเซลล์ตารางที่แยกต่างหาก

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## ขั้นตอนที่ 8: บันทึกเอกสาร PDF

สุดท้าย เราจะบันทึกเอกสาร PDF ลงในไฟล์เอาต์พุตที่ระบุ

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับการวางข้อความรอบรูปภาพโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้างอินสแตนซ์ของวัตถุเอกสาร
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// สร้างหน้าในรูปแบบ Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// สร้างอินสแตนซ์ของวัตถุตาราง
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// เพิ่มตารางในคอลเลกชันย่อหน้าของส่วนที่ต้องการ
page.Paragraphs.Add(table1);
// กำหนดความกว้างของคอลัมน์ของตาราง
table1.ColumnWidths = "120 270";
// สร้างวัตถุ MarginInfo และตั้งค่าระยะขอบด้านซ้าย ล่าง ขวา และบน
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// ตั้งค่าการเติมเซลล์เริ่มต้นเป็นวัตถุ MarginInfo
table1.DefaultCellPadding = margin;
// สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
Aspose.Pdf.Row row1 = table1.Rows.Add();
// สร้างวัตถุรูปภาพ
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// ระบุเส้นทางไฟล์ภาพ
logo.File = dataDir + "aspose-logo.jpg";
// ระบุรูปภาพที่มีความสูงคงที่
logo.FixHeight = 120;
// ระบุความกว้างคงที่ของรูปภาพ
logo.FixWidth = 110;
row1.Cells.Add();
// เพิ่มรูปภาพลงในคอลเลกชันย่อหน้าของเซลล์ตาราง
row1.Cells[0].Paragraphs.Add(logo);
// สร้างตัวแปรสตริงด้วยข้อความที่มีแท็ก html
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//สร้างวัตถุข้อความที่จะเพิ่มทางด้านขวาของรูปภาพ
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// เพิ่มย่อหน้าข้อความที่มีข้อความ HTML ลงในเซลล์ตาราง
row1.Cells[1].Paragraphs.Add(TitleText);
// ตั้งค่าการจัดแนวแนวตั้งของเนื้อหาแถวเป็นด้านบน
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// ตั้งค่าช่วงแถวสำหรับแถวที่สองเป็น 2
SecondRow.Cells[0].ColSpan = 2;
// ตั้งค่าการจัดตำแหน่งแนวตั้งของแถวที่สองเป็นด้านบน
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// เพิ่มย่อหน้าข้อความที่มีข้อความ HTML ลงในเซลล์ตาราง
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// บันทึกไฟล์ PDF
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีวางข้อความรอบรูปภาพในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและดำเนินการโค้ด C# ที่ให้มา คุณสามารถสร้างตาราง เพิ่มรูปภาพ และจัดตำแหน่งข้อความรอบๆ รูปภาพในเอกสาร PDF ได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "การวางข้อความรอบภาพในไฟล์ PDF" คืออะไร

ตอบ: บทช่วยสอน "การวางข้อความรอบรูปภาพในไฟล์ PDF" สาธิตวิธีการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อวางข้อความรอบรูปภาพในเอกสาร PDF บทช่วยสอนนี้จะให้คำแนะนำทีละขั้นตอนและซอร์สโค้ด C# เพื่อช่วยคุณสร้างตาราง เพิ่มรูปภาพ และจัดตำแหน่งข้อความรอบๆ รูปภาพ

#### ถาม: เหตุใดฉันจึงต้องการวางข้อความรอบรูปภาพในเอกสาร PDF

ตอบ: การวางข้อความรอบรูปภาพช่วยเสริมการนำเสนอภาพของเอกสาร PDF ของคุณ ทำให้น่าสนใจและให้ข้อมูลมากขึ้น เทคนิคนี้มักใช้ในเอกสาร โบรชัวร์ รายงาน และเอกสารอื่นๆ ที่คุณต้องการรวมรูปภาพและข้อความในลักษณะที่สวยงามน่าพึงพอใจ

#### ถาม: ฉันจะตั้งค่าไดเร็กทอรีเอกสารได้อย่างไร

ตอบ: หากต้องการตั้งค่าไดเร็กทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรพร้อมพาธไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น

#### ถาม: ฉันจะสร้างตารางและเพิ่มรูปภาพได้อย่างไร

 ตอบ: บทช่วยสอนจะแนะนำคุณตลอดกระบวนการสร้างตารางโดยใช้`Table` คลาสและเพิ่มรูปภาพลงในตารางโดยใช้`Image` ระดับ. คุณจะต้องระบุเส้นทางไฟล์รูปภาพ ความสูง และความกว้าง ก่อนที่จะเพิ่มลงในเซลล์ตาราง

#### ถาม: ฉันจะวางตำแหน่งข้อความรอบรูปภาพได้อย่างไร

 ตอบ: หากต้องการวางตำแหน่งข้อความรอบรูปภาพ คุณจะต้องสร้างข้อความในรูปแบบ HTML โดยใช้`HtmlFragment` ระดับ. ข้อความนี้จะมีทั้งชื่อเรื่องและข้อความเนื้อหา จากนั้นคุณจะเพิ่มข้อความ HTML นี้ลงในเซลล์ตารางที่อยู่ติดกับเซลล์รูปภาพ

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของข้อความและรูปภาพได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของข้อความและรูปภาพได้โดยใช้แท็ก HTML และคุณสมบัติ ตัวอย่างเช่น คุณสามารถตั้งค่าขนาดแบบอักษร สี สไตล์ และการจัดแนวสำหรับข้อความได้ นอกจากนี้คุณยังสามารถปรับขนาดและขนาดของรูปภาพได้อีกด้วย

#### ถาม: ฉันจะบันทึกเอกสาร PDF ได้อย่างไร

 ตอบ: หลังจากเพิ่มรูปภาพและข้อความลงในตารางแล้ว คุณสามารถบันทึกเอกสาร PDF โดยใช้ไฟล์`Save` วิธีการของ`Document` ระดับ. ระบุเส้นทางไฟล์เอาต์พุตที่ต้องการเป็นอาร์กิวเมนต์ของ`Save` วิธี.

#### ถาม: ผลลัพธ์ที่คาดหวังจากบทช่วยสอนนี้คืออะไร

ตอบ: เมื่อทำตามบทช่วยสอนและดำเนินการตามโค้ด C# ที่ให้มา คุณจะสร้างเอกสาร PDF ที่สาธิตวิธีการวางข้อความรอบรูปภาพ เอกสารเอาต์พุตจะมีตารางที่มีรูปภาพและข้อความล้อมรอบ

#### ถาม: ฉันสามารถใช้รูปแบบรูปภาพอื่นนอกเหนือจาก JPG ได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้รูปแบบรูปภาพต่างๆ ที่ไลบรารี Aspose.PDF รองรับได้ เช่น PNG, BMP, GIF และอื่นๆ เมื่อสร้าง`Image` วัตถุ ระบุเส้นทางไฟล์ของรูปแบบภาพที่ต้องการ

#### ถาม: จำเป็นต้องมี Aspose License ที่ถูกต้องสำหรับบทช่วยสอนนี้หรือไม่

ตอบ: ใช่ จำเป็นต้องมี Aspose License ที่ถูกต้องเพื่อให้บทช่วยสอนนี้ทำงานได้อย่างถูกต้อง คุณสามารถซื้อใบอนุญาตแบบเต็มหรือรับใบอนุญาตชั่วคราว 30 วันได้จากเว็บไซต์ Aspose