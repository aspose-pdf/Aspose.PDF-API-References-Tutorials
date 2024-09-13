---
title: ปรับให้พอดีกับหน้าต่างโดยอัตโนมัติ
linktitle: ปรับให้พอดีกับหน้าต่างโดยอัตโนมัติ
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: คู่มือทีละขั้นตอนในการใช้ Aspose.PDF สำหรับ .NET และทำให้หน้าต่างพอดีโดยอัตโนมัติในการสร้าง PDF
type: docs
weight: 50
url: /th/net/programming-with-tables/auto-fit-to-window/
---
บทความต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเกี่ยวกับวิธีใช้โค้ดต้นฉบับ C# ที่ให้มาเพื่อให้ได้ฟังก์ชันปรับให้พอดีกับหน้าต่างโดยอัตโนมัติโดยใช้ไลบรารี Aspose.PDF สำหรับ .NET ฟังก์ชันปรับให้พอดีกับหน้าต่างโดยอัตโนมัติช่วยให้คุณสร้างไฟล์ PDF ที่มีเค้าโครงที่ปรับให้เข้ากับหน้าต่างการดูได้ คุณลักษณะนี้มีประโยชน์อย่างยิ่งเมื่อคุณต้องการให้เอกสาร PDF ของคุณปรับขนาดโดยอัตโนมัติตามขนาดของหน้าต่างโปรแกรมอ่าน PDF ที่ผู้ใช้ใช้

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนเริ่มต้น คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET บนเครื่องของคุณก่อน นอกจากนี้ อย่าลืมนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณด้วย

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างเอกสาร PDF

 ในการเริ่มต้น คุณต้องสร้าง`Document` วัตถุโดยการเรียก constructor เริ่มต้นของมัน

```csharp
Document doc = new Document();
```

 ขั้นตอนต่อไปสร้างส่วนใน`Pdf` วัตถุ.

```csharp
Page sec1 = doc.Pages.Add();
```

## ขั้นตอนที่ 3: การเพิ่มตารางลงในเอกสาร

 ในขั้นตอนนี้ เราจะเพิ่มตารางลงในเอกสาร PDF ของเรา ก่อนอื่นให้สร้างตาราง`Table` วัตถุ.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

ขั้นตอนต่อไป เพิ่มตารางลงในคอลเล็กชั่นย่อหน้าของส่วน

```csharp
sec1.Paragraphs.Add(tab1);
```

##  ขั้นตอนที่ 4: ปรับแต่งรูปลักษณ์ของตาราง

คุณสามารถปรับแต่งลักษณะที่ปรากฏของตารางได้โดยการตั้งค่าคุณสมบัติเช่นเส้นขอบและระยะขอบเซลล์

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  ขั้นตอนที่ 4: การเพิ่มแถวและเซลล์ลงในตาราง

ตอนนี้เรามาเพิ่มแถวและเซลล์ลงในตารางกัน เริ่มต้นด้วยการสร้างแถวและเพิ่มเซลล์ลงในแถวนั้น

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## ขั้นตอนที่ 5: การบันทึกเอกสาร

สุดท้ายให้ระบุเส้นทางไฟล์เอาต์พุตและบันทึกเอกสาร

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการปรับให้พอดีกับหน้าต่างโดยอัตโนมัติโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างอินสแตนซ์ของวัตถุ Pdf โดยเรียก constructor ที่ว่างเปล่า
Document doc = new Document();
// สร้างส่วนในวัตถุ Pdf
Page sec1 = doc.Pages.Add();

// สร้างอินสแตนซ์ของวัตถุตาราง
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// เพิ่มตารางในคอลเลกชันย่อหน้าของส่วนที่ต้องการ
sec1.Paragraphs.Add(tab1);

// ตั้งค่าด้วยความกว้างของคอลัมน์ของตาราง
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// ตั้งค่าเส้นขอบเซลล์เริ่มต้นโดยใช้ BorderInfo object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// กำหนดเส้นขอบตารางโดยใช้ BorderInfo วัตถุที่กำหนดเองอื่น
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// สร้างวัตถุ MarginInfo และตั้งค่าระยะขอบซ้าย ล่าง ขวา และบน
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// ตั้งค่าการเติมเซลล์เริ่มต้นเป็นวัตถุ MarginInfo
tab1.DefaultCellPadding = margin;

//สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// บันทึกเอกสารอัปเดตที่มีวัตถุตาราง
doc.Save(dataDir);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อสร้างไฟล์ PDF ด้วยฟีเจอร์ปรับให้พอดีกับหน้าต่างโดยอัตโนมัติ ฟีเจอร์นี้มีประโยชน์อย่างยิ่งเมื่อคุณต้องการให้เอกสาร PDF ปรับขนาดให้พอดีกับหน้าต่างการดูโดยอัตโนมัติ Aspose.PDF สำหรับ .NET นำเสนอฟีเจอร์อันทรงพลังอื่นๆ มากมายสำหรับการสร้างและจัดการไฟล์ PDF ฉันขอแนะนำให้คุณสำรวจไลบรารีนี้เพิ่มเติมเพื่อค้นพบความสามารถทั้งหมดของไลบรารีนี้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของฟีเจอร์ปรับพอดีอัตโนมัติกับหน้าต่างในการสร้าง PDF คืออะไร

A: คุณลักษณะปรับให้พอดีกับหน้าต่างโดยอัตโนมัติในการสร้าง PDF ช่วยให้เค้าโครงของเอกสาร PDF ปรับขนาดให้พอดีกับหน้าต่างอ่าน PDF ที่ผู้ใช้ใช้โดยอัตโนมัติ ซึ่งช่วยให้ดูได้ดีขึ้นและช่วยให้มั่นใจว่าเนื้อหาจะพอดีกับพื้นที่การดูที่มีอยู่

#### ถาม: ฉันสามารถปรับแต่งลักษณะของตาราง เช่น ขนาดตัวอักษรและสีได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งลักษณะของตารางในเอกสาร PDF ได้โดยใช้ Aspose.PDF สำหรับ .NET ตัวอย่างโค้ดที่ให้มาจะสาธิตวิธีตั้งค่าคุณสมบัติต่างๆ เช่น ขอบเซลล์ ขอบ และความกว้างของคอลัมน์ คุณสามารถปรับแต่งขนาดแบบอักษร สี และลักษณะอื่นๆ ของตารางและเนื้อหาได้เพิ่มเติม

#### ถาม: ฉันจะรวม Aspose.PDF สำหรับ .NET เข้ากับโปรเจ็กต์ C# ของฉันได้อย่างไร

A: หากต้องการใช้ Aspose.PDF สำหรับ .NET ในโปรเจ็กต์ C# คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET บนเครื่องของคุณก่อน จากนั้นจึงเพิ่มการอ้างอิงไปยังไลบรารีในโปรเจ็กต์ C# ของคุณได้ สุดท้าย ให้อิมพอร์ตเนมสเปซที่จำเป็นเพื่อเข้าถึงคลาสและวิธีการที่ Aspose.PDF สำหรับ .NET จัดเตรียมไว้

#### ถาม: Aspose.PDF สำหรับ .NET เข้ากันได้กับแอปพลิเคชัน .NET Core ได้หรือไม่

A: ใช่ Aspose.PDF สำหรับ .NET เข้ากันได้กับแอปพลิเคชัน .NET Core รองรับแพลตฟอร์ม .NET ต่างๆ รวมถึง .NET Framework, .NET Core และ .NET 5.0+

#### ถาม: ฉันสามารถเพิ่มตารางเพิ่มเติมลงในเอกสาร PDF ได้หรือไม่

A: ใช่ คุณสามารถเพิ่มตารางหลายตารางลงในเอกสาร PDF ได้โดยทำตามขั้นตอนที่คล้ายกันตามที่แสดงในโค้ดสั้นๆ เพียงสร้างอินสแตนซ์ใหม่ของตาราง`Aspose.Pdf.Table` และเพิ่มลงในส่วนหรือหน้าต่างๆ ของเอกสาร PDF