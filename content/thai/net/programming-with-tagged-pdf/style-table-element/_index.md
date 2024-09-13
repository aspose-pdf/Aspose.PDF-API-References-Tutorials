---
title: องค์ประกอบตารางสไตล์
linktitle: องค์ประกอบตารางสไตล์
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีจัดรูปแบบองค์ประกอบตารางด้วย Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนในการปรับแต่งรูปแบบและคุณสมบัติ
type: docs
weight: 170
url: /th/net/programming-with-tagged-pdf/style-table-element/
---
ในบทช่วยสอนโดยละเอียดนี้ เราจะแนะนำคุณทีละขั้นตอนเกี่ยวกับโค้ดต้นฉบับ C# ที่ให้มาเพื่อจัดรูปแบบองค์ประกอบอาร์เรย์โดยใช้ Aspose.PDF สำหรับ .NET ปฏิบัติตามคำแนะนำด้านล่างเพื่อทำความเข้าใจวิธีปรับแต่งรูปแบบและคุณสมบัติขององค์ประกอบอาร์เรย์

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนเริ่มต้น โปรดแน่ใจว่าคุณได้กำหนดค่าสภาพแวดล้อมการพัฒนาของคุณให้ใช้ Aspose.PDF สำหรับ .NET แล้ว ซึ่งรวมถึงการติดตั้งไลบรารี Aspose.PDF และกำหนดค่าโปรเจ็กต์ของคุณเพื่ออ้างอิงไลบรารีดังกล่าว

## ขั้นตอนที่ 2: การสร้างเอกสาร

ในขั้นตอนนี้เราจะสร้างวัตถุเอกสารใหม่ Aspose.PDF

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// การสร้างเอกสาร
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

เราได้สร้างเอกสารใหม่และตั้งชื่อเอกสารและภาษา

## ขั้นตอนที่ 3: การได้รับองค์ประกอบโครงสร้างราก

ในขั้นตอนนี้เราจะได้รับองค์ประกอบโครงสร้างรากสำหรับเอกสารของเรา

```csharp
// รับองค์ประกอบโครงสร้างราก
StructureElement rootElement = taggedContent.RootElement;
```

เราได้รับองค์ประกอบโครงสร้างรากที่จะทำหน้าที่เป็นคอนเทนเนอร์สำหรับองค์ประกอบอาร์เรย์

## ขั้นตอนที่ 4: การสร้างองค์ประกอบโครงสร้างอาร์เรย์

ตอนนี้เรามาสร้างองค์ประกอบโครงสร้างตารางใหม่สำหรับเอกสารของเรากัน

```csharp
// สร้างองค์ประกอบโครงสร้างอาร์เรย์
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

เราได้สร้างองค์ประกอบโครงสร้างอาร์เรย์ใหม่และเพิ่มลงในองค์ประกอบโครงสร้างรากแล้ว

## ขั้นตอนที่ 5: การปรับแต่งสไตล์และคุณสมบัติขององค์ประกอบอาร์เรย์

ในขั้นตอนนี้เราจะปรับแต่งรูปแบบและคุณสมบัติขององค์ประกอบอาร์เรย์

```csharp
// ปรับแต่งรูปแบบและคุณสมบัติขององค์ประกอบอาร์เรย์
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// ปรับแต่งรูปแบบของเส้นที่ซ้ำกัน
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

เราใช้คุณสมบัติต่าง ๆ เพื่อปรับแต่งองค์ประกอบของตาราง เช่น สีพื้นหลัง ขอบ การจัดตำแหน่ง สไตล์เซลล์เริ่มต้น ระยะขอบ ความกว้างของคอลัมน์ ฯลฯ

## ขั้นตอนที่ 6: เพิ่มส่วนหัวของตาราง เนื้อหา และส่วนท้ายของตาราง

ตอนนี้เรามาเพิ่มส่วนหัว เนื้อหา และส่วนท้ายของตารางลงในองค์ประกอบตารางกัน
```csharp
// เพิ่มส่วนหัวตาราง
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// จำนวนแถวและคอลัมน์ในตาราง
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// สร้างแถวส่วนหัวของตาราง
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//เพิ่มแถวของตัวตาราง
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// เพิ่มเส้นฐานของตาราง
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

เราเพิ่มส่วนหัว แถวเนื้อหา และแถวส่วนท้ายลงในตารางโดยใช้องค์ประกอบที่สอดคล้องกัน

## ขั้นตอนที่ 7: บันทึกเอกสาร PDF ที่ถูกแท็ก

ตอนนี้เราได้สร้างเอกสารที่มีองค์ประกอบตารางรูปแบบแล้ว เราจะบันทึกเป็นเอกสาร PDF ที่มีแท็ก

```csharp
// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "StyleTableElement.pdf");
```

เราบันทึกเอกสาร PDF ที่ถูกแท็กไว้ในไดเร็กทอรีที่ระบุ

## ขั้นตอนที่ 8: การตรวจสอบการปฏิบัติตาม PDF/UA

ต่อไปเราจะตรวจสอบความสอดคล้องของเอกสาร PDF/UA

```csharp
// การตรวจสอบการปฏิบัติตาม PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

เราอัปโหลดเอกสาร PDF ที่มีแท็ก และตรวจสอบความสอดคล้องกับ PDF/UA ด้วยการสร้างรายงาน XML

### ตัวอย่างโค้ดต้นฉบับสำหรับ Style Table Element โดยใช้ Aspose.PDF สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// รับองค์ประกอบโครงสร้างราก
StructureElement rootElement = taggedContent.RootElement;

// สร้างองค์ประกอบโครงสร้างตาราง
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "StyleTableElement.pdf");

// การตรวจสอบความสอดคล้องของ PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีจัดรูปแบบองค์ประกอบอาร์เรย์ด้วย Aspose.PDF สำหรับ .NET เราปรับแต่งรูปแบบและคุณสมบัติขององค์ประกอบตาราง เพิ่มส่วนหัว แถวเนื้อหา และส่วนท้าย บันทึกเอกสาร PDF ที่มีแท็ก และตรวจสอบการปฏิบัติตาม PDF/UA

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้ในการจัดรูปแบบองค์ประกอบอาร์เรย์โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

A: เป้าหมายของบทช่วยสอนนี้คือเพื่อแนะนำคุณตลอดขั้นตอนการจัดรูปแบบองค์ประกอบอาร์เรย์ในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET โดยบทช่วยสอนนี้จะให้คำแนะนำทีละขั้นตอนและตัวอย่างโค้ดต้นฉบับ C# เพื่อช่วยคุณปรับแต่งรูปแบบและคุณสมบัติขององค์ประกอบอาร์เรย์

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการปฏิบัติตามบทช่วยสอนนี้คืออะไร

A: ก่อนเริ่มต้น ให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณเพื่อใช้ Aspose.PDF สำหรับ .NET แล้ว ซึ่งเกี่ยวข้องกับการติดตั้งไลบรารี Aspose.PDF และกำหนดค่าโปรเจ็กต์ของคุณเพื่ออ้างอิงไลบรารีดังกล่าว

#### ถาม: ฉันจะสร้างเอกสาร PDF ใหม่และตั้งชื่อและภาษาโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 ก: หากต้องการสร้างเอกสาร PDF ใหม่ คุณจะต้องสร้าง`Document` วัตถุจากไลบรารี Aspose.PDF โค้ดต้นฉบับ C# ที่ให้ไว้ในบทช่วยสอนจะสาธิตวิธีการสร้างเอกสารและตั้งค่าคุณสมบัติชื่อและภาษา

#### ถาม: ความสำคัญขององค์ประกอบโครงสร้างรากในเอกสาร PDF คืออะไร

A: องค์ประกอบโครงสร้างรากทำหน้าที่เป็นตัวบรรจุองค์ประกอบโครงสร้างอื่นๆ ช่วยจัดระเบียบและจัดหมวดหมู่เนื้อหาของเอกสาร PDF มีบทบาทสำคัญในการกำหนดโครงสร้างเชิงตรรกะของเอกสาร

#### ถาม: ฉันจะสร้างและปรับแต่งองค์ประกอบโครงสร้างอาร์เรย์โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 A: คุณสามารถสร้างองค์ประกอบโครงสร้างอาร์เรย์โดยใช้`CreateTableElement()` วิธีการ ซอร์สโค้ดของบทช่วยสอนมีตัวอย่างการปรับแต่งคุณสมบัติต่างๆ ขององค์ประกอบตาราง เช่น สีพื้นหลัง ขอบ การจัดตำแหน่ง ความกว้างของคอลัมน์ และอื่นๆ

#### ถาม: ฉันสามารถกำหนดรูปแบบและคุณสมบัติของเซลล์ตารางภายในองค์ประกอบอาร์เรย์ได้หรือไม่

A: ใช่ บทช่วยสอนครอบคลุมถึงวิธีการปรับแต่งรูปแบบและคุณสมบัติขององค์ประกอบตารางทั้งหมด รวมถึงส่วนหัว แถวเนื้อหา และส่วนท้าย อย่างไรก็ตาม บทช่วยสอนไม่ได้กล่าวถึงการปรับแต่งเซลล์ตารางแต่ละเซลล์โดยเฉพาะ

#### ถาม: ฉันจะเพิ่มส่วนหัว แถวเนื้อหา และส่วนท้ายลงในองค์ประกอบตารางได้อย่างไร

A: บทช่วยสอนนี้จะอธิบายวิธีการสร้างและเพิ่มส่วนหัว แถวเนื้อหา และส่วนท้ายลงในองค์ประกอบตารางโดยใช้วิธีการที่เหมาะสมที่ Aspose.PDF จัดทำไว้สำหรับ .NET

#### ถาม: การปฏิบัติตามมาตรฐาน PDF/UA คืออะไร และฉันสามารถตรวจสอบได้สำหรับเอกสาร PDF ที่มีแท็กของฉันได้อย่างไร

 A: การปฏิบัติตาม PDF/UA ช่วยให้มั่นใจได้ว่าเอกสาร PDF เป็นไปตามมาตรฐานการเข้าถึง ทำให้ผู้ใช้ที่มีความทุพพลภาพเข้าถึงได้ง่ายขึ้น บทช่วยสอนจะสาธิตวิธีการตรวจสอบความสอดคล้องของ PDF/UA โดยใช้`Validate()` วิธีการและสร้างรายงานการปฏิบัติตามมาตรฐาน XML

#### ถาม: ฉันจะนำแนวคิดเหล่านี้ไปใช้ในแอปพลิเคชัน .NET ของตัวเองได้อย่างไร

A: คุณสามารถใช้ตัวอย่างโค้ด C# ที่ให้มาเป็นแนวทางในการนำการจัดรูปแบบองค์ประกอบอาร์เรย์ไปใช้ในแอปพลิเคชัน .NET ของคุณเองได้ ปรับเปลี่ยนโค้ดให้ตรงกับความต้องการของคุณและรวมเข้ากับโปรเจ็กต์ของคุณ

#### ถาม: มีแนวทางปฏิบัติที่ดีที่สุดที่แนะนำสำหรับการจัดรูปแบบองค์ประกอบอาร์เรย์ในเอกสาร PDF หรือไม่

A: เมื่อจัดรูปแบบองค์ประกอบของอาร์เรย์ (ตาราง) โปรดพิจารณาถึงความสามารถในการอ่านและการเข้าถึงเนื้อหา ใช้แบบอักษรที่ชัดเจนและอ่านออกได้ สีที่เหมาะสม และรักษาเค้าโครงที่สอดคล้องกัน ตรวจสอบการปฏิบัติตาม PDF/UA เพื่อให้แน่ใจว่าเป็นไปตามมาตรฐานการเข้าถึง

#### ถาม: ฉันสามารถทดลองใช้ฟีเจอร์อื่นๆ ของ Aspose.PDF สำหรับ .NET อะไรในการปรับแต่งเอกสาร PDF ได้บ้าง

A: Aspose.PDF สำหรับ .NET นำเสนอฟีเจอร์ต่างๆ สำหรับการปรับแต่งเอกสาร PDF รวมถึงการจัดการข้อความ การแทรกภาพ การจัดการฟิลด์ฟอร์ม ลายเซ็นดิจิทัล คำอธิบายประกอบ และอื่นๆ อีกมากมาย โปรดดูเอกสารและทรัพยากรอย่างเป็นทางการเพื่อสำรวจฟังก์ชันเพิ่มเติม