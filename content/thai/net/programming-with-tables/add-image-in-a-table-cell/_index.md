---
title: เพิ่มรูปภาพในเซลล์ตาราง
linktitle: เพิ่มรูปภาพในเซลล์ตาราง
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เพิ่มรูปภาพในเซลล์ตารางด้วย Aspose.PDF สำหรับ .NET ซึ่งเป็นคำแนะนำทีละขั้นตอนเพื่อการจัดการรูปภาพในเอกสาร PDF อย่างแม่นยำ
type: docs
weight: 10
url: /th/net/programming-with-tables/add-image-in-a-table-cell/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มรูปภาพลงในเซลล์ตารางโดยใช้ Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาสาธิตวิธีการใช้ฟังก์ชันนี้ เมื่อทำตามขั้นตอนด้านล่างนี้ คุณจะสามารถรวมรูปภาพลงในเซลล์ตารางของคุณได้อย่างมีประสิทธิภาพ

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET และอ้างอิงในโปรเจ็กต์ของคุณแล้ว

## ขั้นตอนที่ 1: การตั้งค่าเอกสาร

 ในการเริ่มต้น เราต้องสร้างอินสแตนซ์ใหม่ของ`Document` คลาสจากเนมสเปซ Aspose.Pdf ชั้นเรียนนี้แสดงถึงเอกสาร PDF

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างอินสแตนซ์วัตถุเอกสาร
Document pdfDocument = new Document();
```

## ขั้นตอนที่ 2: การสร้างเพจ

ต่อไปเราต้องเพิ่มหน้าลงในเอกสาร PDF หน้าทำหน้าที่เป็นคอนเทนเนอร์สำหรับตารางและองค์ประกอบอื่นๆ

```csharp
// สร้างหน้าในเอกสาร pdf
Page sec1 = pdfDocument.Pages.Add();
```

## ขั้นตอนที่ 3: การเพิ่มตาราง

 ในขั้นตอนนี้ เราจะสร้างตารางโดยการสร้างอินสแตนซ์`Table` คลาสจากเนมสเปซ Aspose.Pdf

```csharp
// สร้างอินสแตนซ์ของวัตถุตาราง
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## ขั้นตอนที่ 4: การตั้งค่าเส้นขอบเซลล์เริ่มต้น

 เพื่อให้มั่นใจถึงความสอดคล้อง เราสามารถตั้งค่าเส้นขอบเซลล์เริ่มต้นได้โดยใช้`DefaultCellBorder`คุณสมบัติของโต๊ะ`BorderInfo` วัตถุ.

```csharp
// ตั้งค่าเส้นขอบเซลล์เริ่มต้นโดยใช้วัตถุ BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## ขั้นตอนที่ 5: การตั้งค่าความกว้างของคอลัมน์

 เพื่อกำหนดความกว้างของแต่ละคอลัมน์ในตาราง เราสามารถตั้งค่าได้`ColumnWidths` คุณสมบัติ. ระบุความกว้างเป็นสตริงที่มีค่าคั่นด้วยช่องว่าง

```csharp
// กำหนดความกว้างของคอลัมน์ของตาราง
tab1.ColumnWidths = "100 100 120";
```

## ขั้นตอนที่ 6: การเพิ่มรูปภาพลงในเซลล์ตาราง

มาถึงส่วนที่น่าตื่นเต้นแล้ว โดยการเพิ่มรูปภาพลงในเซลล์ตาราง โดยเราจะทำตามขั้นตอนย่อยเหล่านี้:

## ขั้นตอนที่ 6.1: การสร้างวัตถุรูปภาพ

 สร้างอินสแตนซ์ของ`Image` คลาสจากเนมสเปซ Aspose.Pdf ตั้ง`File` คุณสมบัติให้กับเส้นทางของไฟล์ภาพที่คุณต้องการเพิ่ม

```csharp
// สร้างวัตถุรูปภาพ
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## ขั้นตอนที่ 6.2: การสร้างแถวและเซลล์

ในการเพิ่มรูปภาพลงในตาราง เราต้องสร้างแถวและเซลล์ที่จำเป็นก่อน

```csharp
// สร้างแถวในตาราง
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// เพิ่มเซลล์ข้อความลงในแถว
row1.Cells.Add("Sample text in cell");

// เพิ่มเซลล์ที่เก็บรูปภาพ
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## ขั้นตอนที่ 6.3: การเพิ่มรูปภาพลงในเซลล์ตาราง

สุดท้ายนี้ เราสามารถเพิ่มรูปภาพลงในเซลล์ตารางได้โดยการเพิ่มเป็นย่อหน้าภายในเซลล์

```csharp
// เพิ่มรูปภาพลงในเซลล์ตาราง
cell2.Paragraphs.Add(img);
```

## ขั้นตอนที่ 6.4: การเพิ่มเซลล์เพิ่มเติม

หลังจากเพิ่มเซลล์รูปภาพแล้ว เราจะสามารถเพิ่มเซลล์ลงในแถวได้หากจำเป็น

```csharp
//เพิ่มเซลล์อื่นลงในแถว
row1.Cells.Add("Previous cell with image");

// ปรับการจัดตำแหน่งแนวตั้งของเซลล์ที่สาม
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## ขั้นตอนที่ 7: บันทึกเอกสาร

 สุดท้าย เราสามารถบันทึกเอกสารที่แก้ไขไปยังตำแหน่งที่ระบุได้โดยใช้`Save` วิธี.

```csharp
// บันทึกเอกสาร
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่มรูปภาพลงในเซลล์ตารางโดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว สำรวจตัวเลือกการปรับแต่งเพิ่มเติมได้ตามใจชอบ และรวมฟังก์ชันการทำงานนี้เข้ากับโปรเจ็กต์ของคุณ

### ตัวอย่างซอร์สโค้ดสำหรับเพิ่มรูปภาพในเซลล์ตารางโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างอินสแตนซ์วัตถุเอกสาร
Document pdfDocument = new Document();
// สร้างหน้าในเอกสาร pdf
Page sec1 = pdfDocument.Pages.Add();
// สร้างอินสแตนซ์ของวัตถุตาราง
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// เพิ่มตารางในคอลเลกชันย่อหน้าของหน้าที่ต้องการ
sec1.Paragraphs.Add(tab1);
// ตั้งค่าเส้นขอบเซลล์เริ่มต้นโดยใช้วัตถุ BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// กำหนดความกว้างของคอลัมน์ของตาราง
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// เพิ่มเซลล์ที่เก็บรูปภาพ
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// เพิ่มรูปภาพลงในเซลล์ตาราง
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// บันทึกเอกสาร
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้กล่าวถึงคำแนะนำทีละขั้นตอนเกี่ยวกับวิธีเพิ่มรูปภาพลงในเซลล์ตารางโดยใช้ Aspose.PDF สำหรับ .NET เราเริ่มต้นด้วยการตั้งค่าเอกสาร การสร้างหน้า และเพิ่มตาราง จากนั้นเราตั้งค่าเส้นขอบเซลล์และความกว้างของคอลัมน์เริ่มต้น เราได้สาธิตวิธีการเพิ่มรูปภาพลงในเซลล์ตารางและปรับการจัดตำแหน่งตามแนวตั้งของเซลล์ ในที่สุด เราก็บันทึกเอกสารที่แก้ไขแล้ว ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถปรับปรุงเอกสาร PDF ของคุณด้วยรูปภาพในเซลล์ตารางได้อย่างมีประสิทธิภาพ

### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถเพิ่มรูปภาพหลายรูปลงในเซลล์ต่างๆ ภายในตารางเดียวกันโดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มรูปภาพหลายรูปลงในเซลล์ต่างๆ ภายในตารางเดียวกันได้โดยใช้ Aspose.PDF สำหรับ .NET เพียงทำตามขั้นตอนเดียวกับที่แสดงในบทช่วยสอนสำหรับแต่ละภาพที่คุณต้องการเพิ่มลงในตาราง

#### ถาม: ฉันสามารถปรับแต่งขนาดและตำแหน่งรูปภาพภายในเซลล์ตารางได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งขนาดและตำแหน่งรูปภาพภายในเซลล์ตารางได้โดยการปรับคุณสมบัติของ`Image`วัตถุ. คุณสามารถตั้งค่าความกว้างและความสูงของรูปภาพ รวมถึงการจัดแนวภายในเซลล์ได้

#### ถาม: ฉันสามารถเพิ่มรูปภาพลงในตารางโดยมีจำนวนแถวและคอลัมน์แบบไดนามิกได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มรูปภาพลงในตารางโดยมีจำนวนแถวและคอลัมน์แบบไดนามิกได้ Aspose.PDF สำหรับ .NET ให้ความยืดหยุ่นในการสร้างตารางที่มีขนาดแตกต่างกัน คุณสามารถเพิ่มแถวและเซลล์ได้ตามต้องการ จากนั้นจึงเพิ่มรูปภาพลงในเซลล์ที่ต้องการตามลำดับ

#### ถาม: Aspose.PDF สำหรับ .NET รองรับรูปแบบรูปภาพใดบ้างในการเพิ่มรูปภาพลงในเซลล์ตาราง

ตอบ: Aspose.PDF สำหรับ .NET รองรับรูปแบบรูปภาพที่หลากหลาย รวมถึง JPEG, PNG, GIF, BMP และ TIFF คุณสามารถใช้รูปภาพในรูปแบบเหล่านี้เพื่อเพิ่มลงในเซลล์ตารางได้

#### ถาม: ฉันสามารถเพิ่มรูปภาพลงในตารางในเอกสาร PDF ที่มีอยู่ได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มรูปภาพลงในตารางในเอกสาร PDF ที่มีอยู่ได้โดยใช้ Aspose.PDF สำหรับ .NET เพียงโหลดเอกสารที่มีอยู่แล้วทำตามขั้นตอนเดียวกันเพื่อเพิ่มรูปภาพลงในตารางตามที่แสดงในบทช่วยสอน