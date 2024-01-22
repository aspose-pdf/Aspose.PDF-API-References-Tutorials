---
title: ตารางในส่วนท้ายกระดาษส่วนหัว
linktitle: ตารางในส่วนท้ายกระดาษส่วนหัว
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่มตารางในส่วนหัว/ส่วนท้ายของเอกสาร PDF ด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 170
url: /th/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณทีละขั้นตอนเกี่ยวกับวิธีเพิ่มตารางในส่วนหัวหรือส่วนท้ายของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ซอร์สโค้ด C# ที่ให้มาจะแสดงวิธีสร้างเอกสาร PDF เปล่า เพิ่มหน้า กำหนดค่าส่วนหัว สร้างตาราง เพิ่มแถวและเซลล์ลงในตาราง และสุดท้ายคือบันทึกเอกสาร PDF

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไว้
- ไลบรารี Aspose.PDF สำหรับ .NET ดาวน์โหลดและอ้างอิงในโครงการของคุณ

## ขั้นตอนที่ 2: การสร้างเอกสาร PDF และหน้า

 ขั้นตอนแรกคือการสร้างอินสแตนซ์ของ`Document` และเพิ่มหน้าลงในเอกสาร มีวิธีดังนี้:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างอินสแตนซ์วัตถุเอกสาร
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// สร้างหน้าในเอกสาร PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีที่คุณต้องการบันทึกเอกสาร PDF

## ขั้นตอนที่ 3: การกำหนดค่าส่วนหัว

 ตอนนี้เราจะกำหนดค่าส่วนหัวของเอกสาร PDF โดยการสร้างอินสแตนซ์ของ`HeaderFooter` ระดับ. มีวิธีดังนี้:

```csharp
// สร้างส่วนหัวสำหรับไฟล์ PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// กำหนดส่วนหัวของเพจ
page. Header = header;

// ตั้งค่าระยะขอบด้านบนของส่วนหัว
header. Margin. Top = 20;
```

## ขั้นตอนที่ 4: การสร้างตาราง

 ตอนนี้เรากำลังจะสร้างตารางโดยใช้`Table` และเพิ่มลงในคอลเลกชันย่อหน้าของส่วนหัว มีวิธีดังนี้:

```csharp
// สร้างอินสแตนซ์ให้กับวัตถุ Table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// เพิ่มตารางลงในคอลเลกชันย่อหน้าของส่วนหัว
header.Paragraphs.Add(tab1);

// กำหนดความกว้างของคอลัมน์ของตาราง
tab1.ColumnWidths = "60,300";
```

โค้ดด้านบนสร้างตารางที่มีความกว้างตามที่ระบุสองคอลัมน์

## ขั้นตอนที่ 5: เพิ่มแถวและเซลล์ลงในตาราง

 ตอนนี้เราจะเพิ่มแถวและเซลล์ลงในตารางโดยใช้`Row` ชั้นเรียนและ`Cell` ระดับ. มีวิธีดังนี้:

```csharp
// สร้างแถวในตารางและเพิ่มเซลล์
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// รวมเซลล์แรกของแถวแรก
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// สร้างอีกแถวในตารางและเพิ่มเซลล์ที่มีรูปภาพ
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

เมื่อเพิ่มตารางลงในส่วนหัวแล้ว เราก็สามารถบันทึกเอกสาร PDF ได้ มีวิธีดังนี้:

```csharp
// บันทึกไฟล์ PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีที่คุณต้องการบันทึกเอกสาร PDF

### ตัวอย่างซอร์สโค้ดสำหรับตารางในส่วนท้ายส่วนหัวโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างอินสแตนซ์ของเอกสารโดยการเรียกตัวสร้างที่ว่างเปล่า
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// สร้างหน้าในเอกสาร pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// สร้างส่วนหัวของไฟล์ PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//ตั้งค่า Odd Header สำหรับไฟล์ PDF
page.Header = header;

// ตั้งค่าระยะขอบบนสำหรับส่วนหัว
header.Margin.Top = 20;

// สร้างอินสแตนซ์ของวัตถุตาราง
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// เพิ่มตารางในคอลเลกชันย่อหน้าของส่วนที่ต้องการ
header.Paragraphs.Add(tab1);

// ตั้งค่าเส้นขอบเซลล์เริ่มต้นโดยใช้วัตถุ BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// กำหนดความกว้างของคอลัมน์ของตาราง
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

// ตั้งค่าสีพื้นหลังสำหรับ Row2
row2.BackgroundColor = Color.White;

// เพิ่มเซลล์ที่เก็บรูปภาพ
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// ตั้งค่าความกว้างของภาพเป็น 60
img.FixWidth = 60;

// เพิ่มรูปภาพลงในเซลล์ตาราง
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// ตั้งค่าการจัดแนวข้อความในแนวตั้งให้จัดกึ่งกลาง
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// บันทึกไฟล์ PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีเพิ่มตารางในส่วนหัวหรือส่วนท้ายของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถปรับแต่งส่วนหัวและส่วนท้ายของคุณได้โดยการเพิ่มตารางเพื่อแสดงข้อมูลเพิ่มเติมในเอกสาร PDF ของคุณ

### คำถามที่พบบ่อยสำหรับตารางในส่วนท้ายกระดาษส่วนหัว

#### ถาม: การเพิ่มตารางในส่วนหัวหรือส่วนท้ายของเอกสาร PDF มีวัตถุประสงค์อะไร

ตอบ: การเพิ่มตารางในส่วนหัวหรือส่วนท้ายของเอกสาร PDF ช่วยให้คุณสามารถแสดงข้อมูลที่มีโครงสร้างและจัดระเบียบได้ เช่น ชื่อเรื่อง คำบรรยาย โลโก้ หรือเนื้อหาอื่นใดที่คุณต้องการให้ปรากฏอย่างสม่ำเสมอในแต่ละหน้าของเอกสาร

#### ถาม: ซอร์สโค้ด C# ที่ให้มาสามารถเพิ่มตารางในส่วนหัวหรือส่วนท้ายของเอกสาร PDF ได้อย่างไร

ตอบ: โค้ดนี้สาธิตกระบวนการสร้างเอกสาร PDF เปล่า เพิ่มหน้า กำหนดค่าส่วนหัว สร้างตารางที่มีแถวและเซลล์ และสุดท้ายคือการบันทึกเอกสาร PDF ผลลัพธ์คือตารางที่แสดงในส่วนหัวของเอกสาร PDF

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของเซลล์ตาราง เช่น เส้นขอบ สีพื้นหลัง และลักษณะข้อความ ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของเซลล์ตารางได้โดยการตั้งค่าคุณสมบัติ เช่น เส้นขอบเซลล์ สีพื้นหลัง ลักษณะข้อความ แบบอักษร ขนาดแบบอักษร และอื่นๆ

#### ถาม: ตารางถูกเพิ่มไปยังส่วนหัวของเอกสาร PDF อย่างไร

ตอบ: โค้ดจะเพิ่มตารางลงในคอลเลกชันย่อหน้าของส่วนหัว ซึ่งช่วยให้มั่นใจว่าตารางจะแสดงในส่วนหัวของแต่ละหน้า

#### ถาม: ฉันสามารถเพิ่มแถวและเซลล์ลงในตารางได้ตามต้องการได้หรือไม่

 ตอบ: แน่นอนคุณสามารถเพิ่มแถวและเซลล์ลงในตารางได้โดยใช้`Rows.Add()` และ`Cells.Add()` วิธีการ ซึ่งจะทำให้คุณสามารถจัดโครงสร้างเนื้อหาของตารางได้ตามต้องการ

#### ถาม: สามารถปรับความกว้างของคอลัมน์ในตารางได้หรือไม่?
 ตอบ: ได้ คุณสามารถปรับความกว้างของคอลัมน์ในตารางได้โดยใช้`ColumnWidths` คุณสมบัติ. ซึ่งช่วยให้คุณสามารถควบคุมเค้าโครงของตารางได้

#### ถาม: ฉันจะขยายเซลล์ไปยังหลายคอลัมน์หรือหลายแถวภายในตารางได้อย่างไร
 ตอบ: หากต้องการขยายเซลล์ไปยังหลายคอลัมน์ คุณสามารถใช้`ColSpan` คุณสมบัติของเซลล์ที่เกี่ยวข้อง ในทำนองเดียวกัน คุณสามารถใช้`RowSpan` คุณสมบัติเพื่อขยายเซลล์ไปยังหลายแถว

#### ถาม: จะเกิดอะไรขึ้นหากฉันต้องการเพิ่มตารางทั้งส่วนหัวและส่วนท้ายของเอกสาร PDF

ตอบ: คุณสามารถปฏิบัติตามแนวทางที่คล้ายกันสำหรับทั้งส่วนหัวและส่วนท้าย เพียงสร้าง`HeaderFooter` อินสแตนซ์สำหรับส่วนท้าย กำหนดค่า และเพิ่มตารางลงในคอลเลกชันย่อหน้า

#### ถาม: ฉันสามารถใช้รูปภาพภายในเซลล์ตารางได้หรือไม่ และทำอย่างไร

 ตอบ: ได้ คุณสามารถเพิ่มรูปภาพภายในเซลล์ตารางได้ ตัวอย่างโค้ดสาธิตการเพิ่มรูปภาพลงในเซลล์โดยการสร้าง`Image` วัตถุ ตั้งค่าพาธและขนาดไฟล์ จากนั้นเพิ่มลงในย่อหน้าของเซลล์

#### ถาม: ฉันจะแน่ใจได้อย่างไรว่าตารางปรากฏอย่างสม่ำเสมอในทุกหน้าในเอกสาร PDF

 ตอบ: เมื่อคุณเพิ่มตารางลงในส่วนหัวหรือส่วนท้ายโดยใช้`HeaderFooter` เช่น Aspose.PDF ช่วยให้มั่นใจได้ว่าตารางจะปรากฏอย่างสม่ำเสมอในแต่ละหน้า โดยมีรูปแบบที่เหมือนกัน