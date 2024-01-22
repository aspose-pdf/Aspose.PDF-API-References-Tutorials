---
title: แถวสไตล์ตาราง
linktitle: แถวสไตล์ตาราง
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีปรับแต่งแถวของตารางด้วย Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนในการจัดสไตล์และการจัดรูปแบบแถว
type: docs
weight: 180
url: /th/net/programming-with-tagged-pdf/style-table-row/
---
ในบทช่วยสอนโดยละเอียดนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# ที่ให้มาทีละขั้นตอนเพื่อจัดรูปแบบแถวตารางโดยใช้ Aspose.PDF สำหรับ .NET ทำตามคำแนะนำด้านล่างเพื่อทำความเข้าใจวิธีปรับแต่งสไตล์และคุณสมบัติของแถวตาราง

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้กำหนดค่าสภาพแวดล้อมการพัฒนาของคุณเพื่อใช้ Aspose.PDF สำหรับ .NET ซึ่งรวมถึงการติดตั้งไลบรารี Aspose.PDF และการกำหนดค่าโปรเจ็กต์ของคุณเพื่ออ้างอิง

## ขั้นตอนที่ 2: การสร้างเอกสาร

ในขั้นตอนนี้ เราจะสร้างออบเจ็กต์เอกสารใหม่ Aspose.PDF

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

## ขั้นตอนที่ 3: การได้รับองค์ประกอบโครงสร้างรูท

ในขั้นตอนนี้ เราจะได้องค์ประกอบโครงสร้างรูทสำหรับเอกสารของเรา

```csharp
//รับองค์ประกอบโครงสร้างรูท
StructureElement rootElement = taggedContent.RootElement;
```

เราได้รับองค์ประกอบโครงสร้างรูทซึ่งจะทำหน้าที่เป็นคอนเทนเนอร์สำหรับองค์ประกอบอาร์เรย์

## ขั้นตอนที่ 4: การสร้างองค์ประกอบโครงสร้างอาร์เรย์

ตอนนี้เรามาสร้างองค์ประกอบโครงสร้างตารางใหม่สำหรับเอกสารของเรากันดีกว่า

```csharp
// สร้างองค์ประกอบโครงสร้างอาร์เรย์
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

เราได้สร้างองค์ประกอบโครงสร้างอาร์เรย์ใหม่และเพิ่มลงในองค์ประกอบโครงสร้างราก

## ขั้นตอนที่ 5: ปรับแต่งสไตล์และคุณสมบัติของแถวตาราง

ในขั้นตอนนี้ เราจะปรับแต่งสไตล์และคุณสมบัติของแถวตาราง

```csharp
// ปรับแต่งสไตล์และคุณสมบัติของแถวตาราง
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

// ปรับแต่งแถวของเนื้อหาของตาราง
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

เราได้ปรับแต่งลักษณะต่างๆ ของแถวในตาราง เช่น สีพื้นหลัง เส้นขอบ ความสูงของแถว การแบ่งหน้า สไตล์เซลล์เริ่มต้น และอื่นๆ

## ขั้นตอนที่ 6: บันทึกเอกสาร PDF ที่แท็ก

ตอนนี้เราได้สร้างเอกสารของเราด้วยแถวตารางที่มีสไตล์แล้ว เราจะบันทึกเป็นเอกสาร PDF ที่ติดแท็ก
```csharp
// บันทึกเอกสาร PDF ที่แท็ก
document.Save(dataDir + "StyleTableRow.pdf");
```

เราบันทึกเอกสาร PDF ที่แท็กไว้ในไดเร็กทอรีที่ระบุ

## ขั้นตอนที่ 7: การตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA

ต่อไป เราจะตรวจสอบความสอดคล้องของ PDF/UA ของเอกสารของเรา

```csharp
// การตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

เราอัปโหลดเอกสาร PDF ที่ติดแท็กและตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA โดยการสร้างรายงาน XML


### ตัวอย่างซอร์สโค้ดสำหรับ Style Table Row โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// รับองค์ประกอบโครงสร้างรูท
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

// บันทึกเอกสาร PDF ที่ติดแท็ก
document.Save(dataDir + "StyleTableRow.pdf");

// ตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีจัดรูปแบบแถวของตารางด้วย Aspose.PDF สำหรับ .NET เราปรับแต่งสไตล์และคุณสมบัติของแถวตาราง เพิ่มส่วนหัว แถวเนื้อหา และส่วนท้าย บันทึกเอกสาร PDF ที่แท็ก และตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้เกี่ยวกับการจัดรูปแบบแถวตารางโดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: จุดประสงค์ของบทช่วยสอนนี้คือเพื่อแนะนำคุณตลอดกระบวนการจัดรูปแบบแถวตารางในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET โดยให้คำแนะนำทีละขั้นตอนและตัวอย่างซอร์สโค้ด C# เพื่อช่วยคุณปรับแต่งสไตล์และคุณสมบัติของแถวตาราง

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการติดตามบทช่วยสอนนี้มีอะไรบ้าง

ตอบ: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณเพื่อใช้ Aspose.PDF สำหรับ .NET สิ่งนี้เกี่ยวข้องกับการติดตั้งไลบรารี Aspose.PDF และการกำหนดค่าโปรเจ็กต์ของคุณเพื่ออ้างอิง

#### ถาม: ฉันจะสร้างเอกสาร PDF ใหม่และตั้งชื่อและภาษาโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการสร้างเอกสาร PDF ใหม่ คุณต้องสร้างไฟล์`Document` วัตถุจากไลบรารี Aspose.PDF ซอร์สโค้ด C# ที่ให้ไว้ในบทช่วยสอนสาธิตวิธีสร้างเอกสารและตั้งชื่อและคุณสมบัติภาษา

#### ถาม: องค์ประกอบโครงสร้างรากในเอกสาร PDF มีความสำคัญอย่างไร

ตอบ: องค์ประกอบโครงสร้างรากทำหน้าที่เป็นคอนเทนเนอร์สำหรับองค์ประกอบโครงสร้างอื่นๆ ซึ่งช่วยจัดระเบียบและจัดหมวดหมู่เนื้อหาของเอกสาร PDF มีบทบาทสำคัญในการสร้างโครงสร้างเชิงตรรกะของเอกสาร

#### ถาม: ฉันจะสร้างและปรับแต่งองค์ประกอบโครงสร้างตารางเพื่อจัดรูปแบบแถวตารางโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: บทช่วยสอนจะอธิบายวิธีสร้างองค์ประกอบโครงสร้างตารางและปรับแต่งคุณสมบัติเพื่อจัดรูปแบบแถวของตาราง โดยครอบคลุมลักษณะต่างๆ เช่น สีพื้นหลัง เส้นขอบ ความสูงของแถว การแบ่งหน้า สไตล์เซลล์เริ่มต้น และอื่นๆ

#### ถาม: ฉันสามารถปรับแต่งสไตล์และคุณสมบัติของแต่ละเซลล์ภายในแถวของตารางได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งสไตล์และคุณสมบัติของแต่ละเซลล์ภายในแถวของตารางได้ บทช่วยสอนสาธิตวิธีตั้งค่าคุณสมบัติ เช่น สีพื้นหลัง เส้นขอบ สีข้อความ การเติม และอื่นๆ สำหรับเซลล์ตารางภายในแถวของตารางที่จัดรูปแบบ

#### ถาม: ฉันจะเพิ่มส่วนหัว แถวเนื้อหา และส่วนท้ายลงในแถวของตารางที่จัดรูปแบบได้อย่างไร

ตอบ: บทช่วยสอนนี้ให้ตัวอย่างการสร้างและเพิ่มส่วนหัว แถวเนื้อหา และส่วนท้ายให้กับองค์ประกอบโครงสร้างตาราง องค์ประกอบเหล่านี้สามารถปรับแต่งเพิ่มเติมได้โดยใช้คุณสมบัติที่อธิบายไว้ในบทช่วยสอน

#### ถาม: การปฏิบัติตามข้อกำหนด PDF/UA คืออะไร และฉันสามารถตรวจสอบความถูกต้องของเอกสาร PDF ที่แท็กของฉันได้อย่างไร

 ตอบ: การปฏิบัติตามข้อกำหนด PDF/UA ช่วยให้มั่นใจได้ว่าเอกสาร PDF เป็นไปตามมาตรฐานการเข้าถึง ทำให้ผู้ใช้ที่มีความพิการสามารถเข้าถึงได้มากขึ้น บทช่วยสอนสาธิตวิธีการตรวจสอบความสอดคล้องของ PDF/UA โดยใช้`Validate()` วิธีการและสร้างรายงานการปฏิบัติตามข้อกำหนด XML

#### ถาม: ฉันจะรวมแนวคิดเหล่านี้เข้ากับแอปพลิเคชัน .NET ของฉันเองได้อย่างไร

ตอบ: คุณสามารถใช้ตัวอย่างซอร์สโค้ด C# ที่ให้มาเพื่อเป็นแนวทางในการใช้การจัดรูปแบบแถวตารางในแอปพลิเคชัน .NET ของคุณเอง แก้ไขและปรับใช้โค้ดให้ตรงกับความต้องการของคุณและรวมเข้ากับโปรเจ็กต์ของคุณ

#### ถาม: มีวิธีปฏิบัติที่ดีที่สุดที่แนะนำสำหรับการจัดรูปแบบแถวตารางในเอกสาร PDF หรือไม่

ตอบ: เมื่อจัดรูปแบบแถวของตาราง ให้พิจารณาความสามารถในการอ่านและการเข้าถึงเนื้อหา ตรวจสอบให้แน่ใจว่าสีมีคอนทราสต์เพียงพอ ใช้แบบอักษรที่ชัดเจนและอ่านง่าย และรักษาเค้าโครงที่สอดคล้องกัน ตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA เพื่อให้มั่นใจว่าเป็นไปตามมาตรฐานการเข้าถึง

#### ถาม: ฉันสามารถสำรวจคุณสมบัติอื่นใดของ Aspose.PDF สำหรับ .NET เพื่อปรับแต่งเอกสาร PDF ได้บ้าง

ตอบ: Aspose.PDF สำหรับ .NET นำเสนอคุณสมบัติที่หลากหลายสำหรับการปรับแต่งเอกสาร PDF รวมถึงการจัดการข้อความ การแทรกรูปภาพ การจัดการฟิลด์แบบฟอร์ม ลายเซ็นดิจิทัล คำอธิบายประกอบ และอื่นๆ ศึกษาเอกสารและแหล่งข้อมูลอย่างเป็นทางการเพื่อสำรวจฟังก์ชันเพิ่มเติม