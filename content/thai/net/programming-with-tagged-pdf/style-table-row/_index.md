---
title: สไตล์แถวตาราง
linktitle: สไตล์แถวตาราง
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีปรับแต่งแถวตารางด้วยคำแนะนำแบบทีละขั้นตอนของ Aspose.PDF สำหรับ .NET ในการกำหนดรูปแบบและการจัดรูปแบบแถว
type: docs
weight: 180
url: /th/net/programming-with-tagged-pdf/style-table-row/
---
ในบทช่วยสอนโดยละเอียดนี้ เราจะแนะนำคุณทีละขั้นตอนเกี่ยวกับโค้ดต้นฉบับ C# ที่ให้มาเพื่อจัดรูปแบบแถวตารางโดยใช้ Aspose.PDF สำหรับ .NET ปฏิบัติตามคำแนะนำด้านล่างเพื่อทำความเข้าใจเกี่ยวกับการปรับแต่งรูปแบบและคุณสมบัติของแถวตาราง

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
taggedContent.SetTitle("Example of Table Row Formatting");
taggedContent.SetLanguage("fr-FR");
```

เราได้สร้างเอกสารใหม่และตั้งชื่อเอกสารและภาษา

## ขั้นตอนที่ 3: การได้รับองค์ประกอบโครงสร้างราก

ในขั้นตอนนี้เราจะได้รับองค์ประกอบโครงสร้างรากสำหรับเอกสารของเรา

```csharp
//รับองค์ประกอบโครงสร้างราก
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

## ขั้นตอนที่ 5: ปรับแต่งรูปแบบและคุณสมบัติของแถวตาราง

ในขั้นตอนนี้เราจะปรับแต่งรูปแบบและคุณสมบัติของแถวตาราง

```csharp
// ปรับแต่งรูปแบบและคุณสมบัติของแถวตาราง
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
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

// ปรับแต่งแถวของเนื้อหาตาราง
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// สร้างบรรทัดส่วนท้ายของตาราง
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

เราได้ปรับแต่งด้านต่างๆ ของแถวตาราง เช่น สีพื้นหลัง ขอบ ความสูงของแถว การแบ่งหน้า สไตล์เซลล์เริ่มต้น และอื่นๆ อีกมากมาย

## ขั้นตอนที่ 6: บันทึกเอกสาร PDF ที่ถูกแท็ก

ตอนนี้เราได้สร้างเอกสารที่มีแถวตารางแบบมีสไตล์แล้ว เราจะบันทึกเป็นเอกสาร PDF ที่มีแท็ก
```csharp
// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "StyleTableRow.pdf");
```

เราบันทึกเอกสาร PDF ที่ถูกแท็กไว้ในไดเร็กทอรีที่ระบุ

## ขั้นตอนที่ 7: การตรวจสอบการปฏิบัติตาม PDF/UA

ต่อไปเราจะตรวจสอบความสอดคล้องของเอกสาร PDF/UA

```csharp
// การตรวจสอบการปฏิบัติตาม PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

เราอัปโหลดเอกสาร PDF ที่มีแท็ก และตรวจสอบความสอดคล้องกับ PDF/UA ด้วยการสร้างรายงาน XML


### ตัวอย่างโค้ดต้นฉบับสำหรับ Style Table Row โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// รับองค์ประกอบโครงสร้างราก
StructureElement rootElement = taggedContent.RootElement;

// สร้างองค์ประกอบโครงสร้างตาราง
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
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
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
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
document.Save(dataDir + "StyleTableRow.pdf");

// การตรวจสอบความสอดคล้องของ PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีจัดรูปแบบแถวในตารางด้วย Aspose.PDF สำหรับ .NET เราปรับแต่งรูปแบบและคุณสมบัติของแถวในตาราง เพิ่มส่วนหัว แถวเนื้อหา และส่วนท้าย บันทึกเอกสาร PDF ที่มีแท็ก และตรวจสอบการปฏิบัติตาม PDF/UA

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้เกี่ยวกับการจัดรูปแบบแถวตารางโดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

A: วัตถุประสงค์ของบทช่วยสอนนี้คือเพื่อแนะนำคุณเกี่ยวกับขั้นตอนการจัดรูปแบบแถวตารางในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET โดยบทช่วยสอนนี้จะให้คำแนะนำทีละขั้นตอนและตัวอย่างโค้ดต้นฉบับของ C# เพื่อช่วยคุณปรับแต่งรูปแบบและคุณสมบัติของแถวตาราง

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการปฏิบัติตามบทช่วยสอนนี้คืออะไร

A: ก่อนเริ่มต้น ให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณเพื่อใช้ Aspose.PDF สำหรับ .NET แล้ว ซึ่งเกี่ยวข้องกับการติดตั้งไลบรารี Aspose.PDF และกำหนดค่าโปรเจ็กต์ของคุณเพื่ออ้างอิงไลบรารีดังกล่าว

#### ถาม: ฉันจะสร้างเอกสาร PDF ใหม่และตั้งชื่อและภาษาโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 ก: หากต้องการสร้างเอกสาร PDF ใหม่ คุณจะต้องสร้าง`Document` วัตถุจากไลบรารี Aspose.PDF โค้ดต้นฉบับ C# ที่ให้ไว้ในบทช่วยสอนจะสาธิตวิธีการสร้างเอกสารและตั้งค่าคุณสมบัติชื่อและภาษา

#### ถาม: ความสำคัญขององค์ประกอบโครงสร้างรากในเอกสาร PDF คืออะไร

A: องค์ประกอบโครงสร้างรากทำหน้าที่เป็นตัวบรรจุองค์ประกอบโครงสร้างอื่นๆ ช่วยจัดระเบียบและจัดหมวดหมู่เนื้อหาของเอกสาร PDF มีบทบาทสำคัญในการกำหนดโครงสร้างเชิงตรรกะของเอกสาร

#### ถาม: ฉันจะสร้างและปรับแต่งองค์ประกอบโครงสร้างตารางเพื่อจัดรูปแบบแถวตารางโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

A: บทช่วยสอนนี้จะอธิบายวิธีการสร้างองค์ประกอบโครงสร้างตารางและปรับแต่งคุณสมบัติเพื่อจัดรูปแบบแถวตาราง โดยครอบคลุมถึงด้านต่างๆ เช่น สีพื้นหลัง ขอบ ความสูงของแถว การแบ่งหน้า สไตล์เซลล์เริ่มต้น และอื่นๆ

#### ถาม: ฉันสามารถปรับแต่งรูปแบบและคุณสมบัติของแต่ละเซลล์ภายในแถวตารางได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งรูปแบบและคุณสมบัติของแต่ละเซลล์ภายในแถวตารางได้ บทช่วยสอนจะสาธิตวิธีการตั้งค่าคุณสมบัติต่างๆ เช่น สีพื้นหลัง ขอบ สีข้อความ การเติม และอื่นๆ สำหรับเซลล์ตารางภายในแถวตารางที่จัดรูปแบบแล้ว

#### ถาม: ฉันจะเพิ่มส่วนหัว แถวเนื้อหา และส่วนท้ายลงในแถวตารางที่จัดรูปแบบได้อย่างไร

A: บทช่วยสอนนี้มีตัวอย่างการสร้างและเพิ่มส่วนหัว แถวเนื้อหา และส่วนท้ายลงในองค์ประกอบโครงสร้างตาราง คุณสามารถปรับแต่งองค์ประกอบเหล่านี้เพิ่มเติมได้โดยใช้คุณสมบัติที่อธิบายไว้ในบทช่วยสอน

#### ถาม: การปฏิบัติตามมาตรฐาน PDF/UA คืออะไร และฉันสามารถตรวจสอบได้สำหรับเอกสาร PDF ที่มีแท็กของฉันได้อย่างไร

 A: การปฏิบัติตาม PDF/UA ช่วยให้มั่นใจได้ว่าเอกสาร PDF เป็นไปตามมาตรฐานการเข้าถึง ทำให้ผู้ใช้ที่มีความทุพพลภาพเข้าถึงได้ง่ายขึ้น บทช่วยสอนจะสาธิตวิธีการตรวจสอบความสอดคล้องของ PDF/UA โดยใช้`Validate()` วิธีการและสร้างรายงานการปฏิบัติตามมาตรฐาน XML

#### ถาม: ฉันจะนำแนวคิดเหล่านี้ไปใช้ในแอปพลิเคชัน .NET ของตัวเองได้อย่างไร

A: คุณสามารถใช้ตัวอย่างโค้ดต้นฉบับ C# ที่ให้มาเป็นแนวทางในการนำการจัดรูปแบบแถวตารางไปใช้ในแอปพลิเคชัน .NET ของคุณเองได้ ปรับเปลี่ยนโค้ดให้ตรงกับความต้องการของคุณและรวมเข้ากับโปรเจ็กต์ของคุณ

#### ถาม: มีแนวทางปฏิบัติที่ดีที่สุดที่แนะนำสำหรับการจัดรูปแบบแถวตารางในเอกสาร PDF หรือไม่

ก: เมื่อจัดรูปแบบแถวของตาราง ให้พิจารณาถึงความสามารถในการอ่านและการเข้าถึงเนื้อหา ตรวจสอบว่าสีมีความคมชัดเพียงพอ ใช้แบบอักษรที่ชัดเจนและอ่านออกได้ และรักษาเค้าโครงให้สม่ำเสมอ ตรวจสอบการปฏิบัติตาม PDF/UA เพื่อให้แน่ใจว่าเป็นไปตามมาตรฐานการเข้าถึง

#### ถาม: ฉันสามารถทดลองใช้ฟีเจอร์อื่นๆ ของ Aspose.PDF สำหรับ .NET อะไรในการปรับแต่งเอกสาร PDF ได้บ้าง

A: Aspose.PDF สำหรับ .NET นำเสนอฟีเจอร์มากมายสำหรับการปรับแต่งเอกสาร PDF รวมถึงการจัดการข้อความ การแทรกภาพ การจัดการฟิลด์ฟอร์ม ลายเซ็นดิจิทัล คำอธิบายประกอบ และอื่นๆ อีกมากมาย โปรดดูเอกสารและทรัพยากรอย่างเป็นทางการเพื่อสำรวจฟังก์ชันเพิ่มเติม