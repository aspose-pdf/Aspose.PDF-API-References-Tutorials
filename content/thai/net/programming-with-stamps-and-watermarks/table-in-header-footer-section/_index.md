---
title: ตารางในส่วนหัวส่วนท้าย
linktitle: ตารางในส่วนหัวส่วนท้าย
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการเพิ่มตารางในส่วนหัว/ส่วนท้ายของเอกสาร PDF ด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 170
url: /th/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณทีละขั้นตอนเกี่ยวกับวิธีการเพิ่มตารางในส่วนหัวหรือส่วนท้ายของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET โค้ดต้นฉบับ C# ที่ให้มาจะแสดงวิธีการสร้างเอกสาร PDF เปล่า เพิ่มหน้า กำหนดค่าส่วนหัว สร้างตาราง เพิ่มแถวและเซลล์ในตาราง และสุดท้ายบันทึกเอกสาร PDF

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งแล้ว
- ไลบรารี Aspose.PDF สำหรับ .NET ดาวน์โหลดและอ้างอิงในโครงการของคุณ

## ขั้นตอนที่ 2: การสร้างเอกสารและหน้า PDF

 ขั้นตอนแรกคือการสร้างอินสแตนซ์ของ`Document` และเพิ่มหน้าลงในเอกสาร ทำได้ดังนี้:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างอินสแตนซ์ของวัตถุเอกสาร
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// สร้างหน้าในเอกสาร PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีที่คุณต้องการบันทึกเอกสาร PDF

## ขั้นตอนที่ 3: การกำหนดค่าส่วนหัว

 ตอนนี้เราจะกำหนดค่าส่วนหัวของเอกสาร PDF โดยการสร้างอินสแตนซ์ของ`HeaderFooter` ชั้นเรียน ดังต่อไปนี้:

```csharp
// สร้างส่วนหัวสำหรับไฟล์ PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// กำหนดส่วนหัวสำหรับหน้า
page. Header = header;

// ตั้งค่าระยะขอบบนของส่วนหัว
header. Margin. Top = 20;
```

## ขั้นตอนที่ 4: การสร้างตาราง

 ตอนนี้เราจะสร้างตารางโดยใช้`Table` และเพิ่มลงในคอลเล็กชันย่อหน้าของหัวข้อ ดังต่อไปนี้:

```csharp
// สร้างอินสแตนซ์ของวัตถุตาราง
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// เพิ่มตารางลงในคอลเลกชันย่อหน้าของส่วนหัว
header.Paragraphs.Add(tab1);

// กำหนดความกว้างของคอลัมน์ของตาราง
tab1.ColumnWidths = "60,300";
```

โค้ดด้านบนจะสร้างตารางที่มี 2 คอลัมน์ โดยมีความกว้างตามที่กำหนด

## ขั้นตอนที่ 5: เพิ่มแถวและเซลล์ลงในตาราง

 ตอนนี้เราจะเพิ่มแถวและเซลล์ลงในตารางโดยใช้`Row` ชั้นเรียนและ`Cell` ชั้นเรียน ดังต่อไปนี้:

```csharp
// สร้างแถวในตารางและเพิ่มเซลล์
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// รวมเซลล์แรกของแถวแรก
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// สร้างแถวอื่นในตารางและเพิ่มเซลล์ด้วยรูปภาพ
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## ขั้นตอนที่ 6: บันทึกเอกสาร PDF

เมื่อเพิ่มตารางลงในส่วนหัวแล้ว เราจะบันทึกเอกสาร PDF ได้ ดังต่อไปนี้:

```csharp
// บันทึกไฟล์ PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีที่คุณต้องการบันทึกเอกสาร PDF

### ตัวอย่างโค้ดต้นฉบับสำหรับตารางในส่วนหัวส่วนท้ายโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างอินสแตนซ์เอกสารโดยเรียก constructor ที่ว่างเปล่า
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// สร้างหน้าในเอกสาร pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//สร้างส่วนหัวของไฟล์ PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// ตั้งค่าส่วนหัวคี่สำหรับไฟล์ PDF
page.Header = header;

// ตั้งค่าระยะขอบบนสำหรับส่วนหัว
header.Margin.Top = 20;

// สร้างอินสแตนซ์ของวัตถุตาราง
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// เพิ่มตารางในคอลเลกชันย่อหน้าของส่วนที่ต้องการ
header.Paragraphs.Add(tab1);

// ตั้งค่าเส้นขอบเซลล์เริ่มต้นโดยใช้ BorderInfo object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// ตั้งค่าด้วยความกว้างของคอลัมน์ของตาราง
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// ตั้งค่าช่วงแถวสำหรับแถวแรกเป็น 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// ตั้งค่าสีพื้นหลังสำหรับแถวที่ 2
row2.BackgroundColor = Color.White;

// เพิ่มเซลล์ที่เก็บรูปภาพ
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// ตั้งค่าความกว้างของภาพเป็น 60
img.FixWidth = 60;

// เพิ่มรูปภาพลงในเซลล์ตาราง
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// ตั้งค่าการจัดแนวแนวตั้งของข้อความให้จัดกึ่งกลาง
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// บันทึกไฟล์ PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีการเพิ่มตารางในส่วนหัวและส่วนท้ายของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET แล้ว ตอนนี้คุณสามารถปรับแต่งส่วนหัวและส่วนท้ายของคุณได้โดยการเพิ่มตารางเพื่อแสดงข้อมูลเพิ่มเติมในเอกสาร PDF ของคุณ

### คำถามที่พบบ่อยสำหรับตารางในส่วนหัวส่วนท้าย

#### ถาม: จุดประสงค์ของการเพิ่มตารางในส่วนหัวหรือส่วนท้ายของเอกสาร PDF คืออะไร

ก: การเพิ่มตารางในส่วนหัวหรือส่วนท้ายของเอกสาร PDF ช่วยให้คุณสามารถแสดงข้อมูลที่มีโครงสร้างและเป็นระเบียบ เช่น ชื่อเรื่อง คำบรรยายใต้ภาพ โลโก้ หรือเนื้อหาอื่นใดที่คุณต้องการให้ปรากฏสอดคล้องกันบนแต่ละหน้าของเอกสาร

#### ถาม: โค้ดต้นฉบับ C# ที่ให้มาทำการเพิ่มตารางในส่วนหัวหรือส่วนท้ายของเอกสาร PDF ได้อย่างไร

A: โค้ดนี้สาธิตขั้นตอนการสร้างเอกสาร PDF เปล่า การเพิ่มหน้า การกำหนดค่าส่วนหัว การสร้างตารางที่มีแถวและเซลล์ และขั้นตอนสุดท้ายคือการบันทึกเอกสาร PDF ผลลัพธ์คือตารางที่แสดงในส่วนหัวของเอกสาร PDF

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของเซลล์ตาราง เช่น เส้นขอบ สีพื้นหลัง และรูปแบบข้อความ ได้หรือไม่

A: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของเซลล์ตารางได้โดยการตั้งค่าคุณสมบัติเช่นเส้นขอบเซลล์ สีพื้นหลัง สไตล์ข้อความ แบบอักษร ขนาดแบบอักษร และอื่นๆ

#### ถาม: ตารางจะเพิ่มลงในส่วนหัวของเอกสาร PDF ได้อย่างไร

A: รหัสนี้จะเพิ่มตารางลงในคอลเล็กชั่นย่อหน้าของส่วนหัว ซึ่งจะทำให้แน่ใจว่าตารางจะแสดงในส่วนหัวของแต่ละหน้า

#### ถาม: ฉันสามารถเพิ่มแถวและเซลล์เพิ่มเติมลงในตารางตามต้องการได้หรือไม่

 A: แน่นอน คุณสามารถเพิ่มแถวและเซลล์เพิ่มเติมลงในตารางได้โดยใช้`Rows.Add()` และ`Cells.Add()` วิธีการนี้ช่วยให้คุณสามารถจัดโครงสร้างเนื้อหาตารางตามต้องการ

#### ถาม: สามารถปรับความกว้างของคอลัมน์ตารางได้หรือไม่?
 A: ใช่ คุณสามารถปรับความกว้างของคอลัมน์ตารางได้โดยใช้`ColumnWidths` คุณสมบัตินี้ช่วยให้คุณสามารถควบคุมเค้าโครงของตารางได้

#### ถาม: ฉันจะขยายเซลล์ข้ามหลายคอลัมน์หรือหลายแถวภายในตารางได้อย่างไร
 A: หากต้องการขยายเซลล์ข้ามหลายคอลัมน์ คุณสามารถใช้`ColSpan`คุณสมบัติของเซลล์ที่เกี่ยวข้อง ในทำนองเดียวกัน คุณสามารถใช้`RowSpan` คุณสมบัติในการขยายเซลล์ข้ามหลายแถว

#### ถาม: จะเกิดอะไรขึ้นถ้าฉันต้องการเพิ่มตารางทั้งในส่วนหัวและส่วนท้ายของเอกสาร PDF

 A: คุณสามารถทำตามแนวทางเดียวกันนี้สำหรับส่วนหัวและส่วนท้ายได้ เพียงสร้าง`HeaderFooter` อินสแตนซ์สำหรับส่วนท้าย กำหนดค่าและเพิ่มตารางลงในคอลเล็กชั่นย่อหน้า

#### ถาม: ฉันสามารถใช้รูปภาพภายในเซลล์ตารางได้หรือไม่ และทำอย่างไร

 A: ใช่ คุณสามารถเพิ่มรูปภาพในเซลล์ตารางได้ ตัวอย่างโค้ดสาธิตการเพิ่มรูปภาพลงในเซลล์โดยการสร้าง`Image` วัตถุ โดยตั้งค่าเส้นทางและขนาดของไฟล์ แล้วเพิ่มลงในย่อหน้าของเซลล์

#### ถาม: ฉันจะมั่นใจได้อย่างไรว่าตารางจะปรากฏสม่ำเสมอกันในทุกหน้าในเอกสาร PDF

 ก: เมื่อคุณเพิ่มตารางลงในส่วนหัวหรือส่วนท้ายโดยใช้`HeaderFooter` ตัวอย่างเช่น Aspose.PDF ช่วยให้แน่ใจว่าตารางจะปรากฏสอดคล้องกันในแต่ละหน้า ทำให้มีเค้าโครงที่สม่ำเสมอ