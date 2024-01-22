---
title: ปรับให้พอดีกับหน้าต่างอัตโนมัติ
linktitle: ปรับให้พอดีกับหน้าต่างอัตโนมัติ
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนเพื่อใช้ Aspose.PDF สำหรับ .NET และปรับให้พอดีกับหน้าต่างโดยอัตโนมัติในการสร้าง PDF
type: docs
weight: 50
url: /th/net/programming-with-tables/auto-fit-to-window/
---
บทความต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการใช้ซอร์สโค้ด C# ที่ให้มาเพื่อให้บรรลุฟังก์ชันการทำงานของ Auto Fit To Window โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET ฟังก์ชันปรับให้พอดีกับหน้าต่างอัตโนมัติช่วยให้คุณสร้างไฟล์ PDF ด้วยเลย์เอาต์ที่ปรับให้เหมาะกับหน้าต่างการดู คุณลักษณะนี้มีประโยชน์อย่างยิ่งเมื่อคุณต้องการให้เอกสาร PDF ของคุณปรับขนาดของหน้าต่างโปรแกรมอ่าน PDF ที่ผู้ใช้ใช้โดยอัตโนมัติ

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่คุณจะเริ่มต้น คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET บนเครื่องของคุณ นอกจากนี้ อย่าลืมนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างเอกสาร PDF

 ในการเริ่มต้น คุณจะต้องสร้าง`Document` วัตถุโดยการเรียกตัวสร้างเริ่มต้น

```csharp
Document doc = new Document();
```

 ถัดไป สร้างส่วนใน`Pdf` วัตถุ.

```csharp
Page sec1 = doc.Pages.Add();
```

## ขั้นตอนที่ 3: การเพิ่มตารางลงในเอกสาร

 ในขั้นตอนนี้ เราจะเพิ่มตารางลงในเอกสาร PDF ของเรา ขั้นแรกให้สร้างก`Table` วัตถุ.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

จากนั้น เพิ่มตารางลงในคอลเลกชันย่อหน้าของส่วน

```csharp
sec1.Paragraphs.Add(tab1);
```

##  ขั้นตอนที่ 4: การปรับแต่งลักษณะที่ปรากฏของตาราง

คุณสามารถปรับแต่งลักษณะที่ปรากฏของตารางได้โดยการตั้งค่าคุณสมบัติ เช่น เส้นขอบเซลล์และระยะขอบ

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

ตอนนี้เรามาเพิ่มแถวและเซลล์ลงในตารางของเรา เริ่มต้นด้วยการสร้างแถวและเพิ่มเซลล์ลงในแถวนั้น

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

## ขั้นตอนที่ 5: บันทึกเอกสาร

สุดท้าย ระบุเส้นทางของไฟล์เอาต์พุตและบันทึกเอกสาร

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับ Auto Fit To Window โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างอินสแตนซ์วัตถุ Pdf โดยการเรียกตัวสร้างที่ว่างเปล่า
Document doc = new Document();
// สร้างส่วนในวัตถุ Pdf
Page sec1 = doc.Pages.Add();

// สร้างอินสแตนซ์ของวัตถุตาราง
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// เพิ่มตารางในคอลเลกชันย่อหน้าของส่วนที่ต้องการ
sec1.Paragraphs.Add(tab1);

// กำหนดความกว้างของคอลัมน์ของตาราง
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// ตั้งค่าเส้นขอบเซลล์เริ่มต้นโดยใช้วัตถุ BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// ตั้งค่าเส้นขอบตารางโดยใช้วัตถุ BorderInfo ที่กำหนดเองอื่น
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// สร้างวัตถุ MarginInfo และตั้งค่าระยะขอบด้านซ้าย ล่าง ขวา และบน
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// ตั้งค่าการเติมเซลล์เริ่มต้นเป็นวัตถุ MarginInfo
tab1.DefaultCellPadding = margin;

// สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// บันทึกเอกสารที่อัปเดตซึ่งมีวัตถุตาราง
doc.Save(dataDir);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อสร้างไฟล์ PDF พร้อมฟีเจอร์ปรับให้พอดีกับหน้าต่างอัตโนมัติ คุณสมบัตินี้มีประโยชน์อย่างยิ่งเมื่อคุณต้องการให้เอกสาร PDF ของคุณปรับขนาดของหน้าต่างการดูโดยอัตโนมัติ Aspose.PDF สำหรับ .NET นำเสนอคุณสมบัติอันทรงพลังอื่นๆ อีกมากมายสำหรับการสร้างและจัดการไฟล์ PDF ฉันขอแนะนำให้คุณสำรวจห้องสมุดนี้เพิ่มเติมเพื่อค้นพบความสามารถทั้งหมดของมัน

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของฟีเจอร์ Auto Fit To Window ในการสร้าง PDF คืออะไร

ตอบ: คุณสมบัติ Auto Fit To Window ในการสร้าง PDF ช่วยให้มั่นใจได้ว่าเค้าโครงของเอกสาร PDF จะปรับขนาดของหน้าต่างตัวอ่าน PDF ที่ผู้ใช้ใช้โดยอัตโนมัติ ช่วยให้รับชมได้ดีขึ้นและรับประกันว่าเนื้อหาจะลงตัวพอดีภายในพื้นที่รับชมที่มีอยู่

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของตาราง เช่น ขนาดตัวอักษรและสีได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของตารางในเอกสาร PDF ได้โดยใช้ Aspose.PDF สำหรับ .NET ข้อมูลโค้ดที่ให้มาสาธิตวิธีการตั้งค่าคุณสมบัติ เช่น เส้นขอบเซลล์ ระยะขอบ และความกว้างของคอลัมน์ คุณสามารถปรับแต่งขนาดตัวอักษร สี และลักษณะการจัดรูปแบบอื่นๆ ของตารางและเนื้อหาเพิ่มเติมได้

#### ถาม: ฉันจะผสานรวม Aspose.PDF สำหรับ .NET เข้ากับโปรเจ็กต์ C# ของฉันได้อย่างไร

ตอบ: หากต้องการใช้ Aspose.PDF สำหรับ .NET ในโปรเจ็กต์ C# ของคุณ คุณต้องติดตั้งไลบรารี Aspose.PDF สำหรับ .NET บนเครื่องของคุณก่อน จากนั้น คุณสามารถเพิ่มการอ้างอิงไปยังไลบรารีในโครงการ C# ของคุณได้ สุดท้าย นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงคลาสและวิธีการที่ได้รับจาก Aspose.PDF สำหรับ .NET

#### ถาม: Aspose.PDF สำหรับ .NET เข้ากันได้กับแอปพลิเคชัน .NET Core หรือไม่

ตอบ: ได้ Aspose.PDF สำหรับ .NET เข้ากันได้กับแอปพลิเคชัน .NET Core รองรับแพลตฟอร์ม .NET ที่หลากหลาย รวมถึง .NET Framework, .NET Core และ .NET 5.0+

#### ถาม: ฉันสามารถเพิ่มตารางลงในเอกสาร PDF ได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มหลายตารางลงในเอกสาร PDF ได้โดยทำตามขั้นตอนที่คล้ายกันดังที่แสดงในตัวอย่างโค้ด เพียงสร้างอินสแตนซ์ใหม่ของ`Aspose.Pdf.Table` และเพิ่มลงในส่วนหรือหน้าต่างๆ ของเอกสาร PDF