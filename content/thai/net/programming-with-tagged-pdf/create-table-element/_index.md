---
title: สร้างองค์ประกอบตาราง
linktitle: สร้างองค์ประกอบตาราง
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการสร้างองค์ประกอบอาร์เรย์ด้วย Aspose.PDF สำหรับ .NET สร้าง PDF แบบไดนามิกพร้อมตารางได้อย่างง่ายดาย
type: docs
weight: 80
url: /th/net/programming-with-tagged-pdf/create-table-element/
---
ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดกระบวนการสร้างองค์ประกอบอาร์เรย์โดยใช้ Aspose.PDF สำหรับ .NET Aspose.PDF เป็นไลบรารีอันทรงพลังที่ให้คุณจัดการเอกสาร PDF โดยทางโปรแกรม การสร้างองค์ประกอบอาร์เรย์เป็นข้อกำหนดทั่วไปในการสร้าง PDF แบบไดนามิก และ Aspose.PDF นำเสนอวิธีที่ง่ายและมีประสิทธิภาพในการบรรลุเป้าหมายนี้

มาเจาะลึกโค้ดและเรียนรู้วิธีสร้างองค์ประกอบอาร์เรย์โดยใช้ Aspose.PDF สำหรับ .NET กันดีกว่า

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
2. ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ในการเริ่มต้น ให้เปิดสภาพแวดล้อมการพัฒนา C# ของคุณและสร้างโปรเจ็กต์ใหม่ ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET ในโปรเจ็กต์ของคุณ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างเอกสาร

 ขั้นตอนแรกคือการสร้างเอกสาร PDF ใหม่โดยใช้ไฟล์`Document` ระดับ.

```csharp
// สร้างเอกสาร
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

ที่นี่เรายังตั้งชื่อและภาษาสำหรับเนื้อหาที่แท็กด้วย

## ขั้นตอนที่ 3: การสร้างองค์ประกอบอาร์เรย์

ต่อไปเราต้องสร้างองค์ประกอบอาร์เรย์และเพิ่มลงในเอกสาร เราเริ่มต้นด้วยการรับองค์ประกอบโครงสร้างรูท จากนั้นเราสร้างองค์ประกอบตารางใหม่โดยใช้`CreateTableElement` วิธี.

```csharp
// รับองค์ประกอบโครงสร้างรูท
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
TableTRElement trElement = tableTBodyElement.CreateTR();
trElement.AlternativeText = String.Format("Row {0}", rowIndex);
for (colIndex = 0; colIndex < colCount; colIndex++)
{
int colSpan = 1;
int rowSpan = 1;
if (colIndex == 1 && rowIndex == 1)
{
colSpan = 2;
rowSpan = 2;
}
else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
{
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
tdElement.BackgroundColor = Color.Yellow;
tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
tdElement.IsNoBorder = false;
tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
tdElement.Alignment = HorizontalAlignment.Center;
TextState cellTextState = new TextState();
cellTextState.ForegroundColor = Color.DarkBlue;
cellTextState.FontSize = 7.5F;
cellTextState.FontStyle = FontStyles.Bold;
cellTextState.Font = FontRepository.FindFont("Arial");
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// บันทึกเอกสาร PDF ที่แท็ก
document.Save(dataDir + "CreateTableElement.pdf");

// การตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### ตัวอย่างซอร์สโค้ดสำหรับสร้างองค์ประกอบตารางโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// รับองค์ประกอบโครงสร้างรูท
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// บันทึกเอกสาร PDF ที่ติดแท็ก
document.Save(dataDir + "CreateTableElement.pdf");

// ตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## บทสรุป

คุณได้เรียนรู้วิธีสร้างองค์ประกอบอาร์เรย์โดยใช้ Aspose.PDF สำหรับ .NET ตอนนี้คุณสามารถสร้างเอกสาร PDF ด้วยตารางไดนามิกโดยใช้วิธีนี้ สำรวจคุณสมบัติเพิ่มเติมของ Aspose.PDF ได้อย่างอิสระเพื่อค้นพบศักยภาพสูงสุดของมัน

### คำถามที่พบบ่อย

#### ถาม: องค์ประกอบอาร์เรย์ในเอกสาร PDF คืออะไร และเหตุใดฉันจึงต้องสร้างองค์ประกอบอาร์เรย์โดยใช้ Aspose.PDF สำหรับ .NET

ตอบ: องค์ประกอบอาร์เรย์ในเอกสาร PDF แสดงถึงคอลเลกชั่นข้อมูลที่มีโครงสร้าง ซึ่งมักใช้สำหรับการสร้างตารางหรือตาราง คุณอาจต้องสร้างองค์ประกอบอาร์เรย์โดยใช้ Aspose.PDF สำหรับ .NET เมื่อสร้าง PDF แบบไดนามิกที่ต้องมีการนำเสนอข้อมูลที่มีโครงสร้าง เช่น ข้อมูลแบบตารางหรือตาราง

#### ถาม: Aspose.PDF สำหรับ .NET ช่วยให้กระบวนการสร้างองค์ประกอบอาร์เรย์ง่ายขึ้นได้อย่างไร

ตอบ: Aspose.PDF สำหรับ .NET มีชุดคลาสและวิธีการที่ครอบคลุมซึ่งช่วยให้คุณสามารถสร้าง ปรับแต่ง และจัดการองค์ประกอบอาร์เรย์ (ตาราง) ในเอกสาร PDF โดยทางโปรแกรม ซึ่งช่วยลดความจำเป็นในการจัดการ PDF ด้วยตนเอง และปรับปรุงการสร้างการแสดงข้อมูลที่มีโครงสร้าง

#### ถาม: ขั้นตอนสำคัญในการสร้างองค์ประกอบอาร์เรย์โดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: ขั้นตอนสำคัญได้แก่ การตั้งค่าสภาพแวดล้อม การสร้างเอกสาร การได้รับองค์ประกอบโครงสร้างราก การสร้างองค์ประกอบตาราง การกำหนดแถวและเซลล์ภายในตาราง และการระบุการจัดรูปแบบและคุณสมบัติขององค์ประกอบ ตัวอย่างโค้ดที่ให้มาแสดงให้เห็นถึงขั้นตอนเหล่านี้

####  ถาม: มีบทบาทอะไร`taggedContent` object play in creating an array element?

 ตอบ:`taggedContent` วัตถุที่ได้รับจากเอกสาร`TaggedContent`คุณสมบัติ ช่วยให้คุณสามารถกำหนดโครงสร้างของเนื้อหาที่แท็กภายในเอกสาร PDF ซึ่งรวมถึงการสร้างและจัดระเบียบองค์ประกอบอาร์เรย์และองค์ประกอบย่อยในลักษณะลำดับชั้น

#### ถาม: โค้ดช่วยให้มั่นใจในการเข้าถึงและความหมายขององค์ประกอบอาร์เรย์ที่สร้างขึ้นได้อย่างไร

 ตอบ: แอตทริบิวต์ชุดโค้ดเช่น`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , และ`ColSpan` เพื่อปรับปรุงการเข้าถึงและความหมายขององค์ประกอบอาร์เรย์ คุณลักษณะเหล่านี้มีส่วนช่วยในการนำเสนอข้อมูลที่มีโครงสร้างดี ให้ข้อมูล และดึงดูดสายตา

#### ถาม: การปฏิบัติตามข้อกำหนด PDF/UA ในบริบทของการสร้างองค์ประกอบอาร์เรย์มีความสำคัญอย่างไร

 ตอบ: การปฏิบัติตามข้อกำหนด PDF/UA (การเข้าถึงแบบสากล) ช่วยให้มั่นใจได้ว่าเอกสาร PDF ที่สร้างขึ้นจะสามารถเข้าถึงได้โดยผู้ใช้ที่มีความพิการ และเป็นไปตามมาตรฐานการเข้าถึงบางประการ ตัวอย่างโค้ดจะตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA โดยใช้`Validate` วิธีการช่วยให้คุณสร้างเอกสารที่ครอบคลุมและเข้าถึงได้

#### ถาม: ฉันสามารถปรับแต่งการจัดรูปแบบและรูปลักษณ์ขององค์ประกอบอาร์เรย์เพิ่มเติมได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งการจัดรูปแบบและรูปลักษณ์ขององค์ประกอบอาร์เรย์ได้โดยการปรับคุณลักษณะต่างๆ เช่น สีพื้นหลัง ลักษณะเส้นขอบ ขนาดตัวอักษร และการจัดตำแหน่ง Aspose.PDF สำหรับ .NET มีคุณสมบัติที่หลากหลายเพื่อปรับแต่งการนำเสนอด้วยภาพให้ตรงตามความต้องการของคุณ

#### ถาม: ฉันจะขยายความรู้นี้เพื่อสร้างโครงสร้างตารางที่ซับซ้อนมากขึ้นหรือรวมองค์ประกอบอาร์เรย์ลงในเอกสาร PDF ขนาดใหญ่ได้อย่างไร

ตอบ: คุณสามารถขยายความรู้นี้ได้โดยการสำรวจคุณสมบัติเพิ่มเติมของ Aspose.PDF สำหรับ .NET เช่น การรวมองค์ประกอบอาร์เรย์หลายรายการ การสร้างตารางที่ซ้อนกัน การเพิ่มส่วนหัวและส่วนท้าย และการรวมองค์ประกอบอาร์เรย์เข้ากับเค้าโครง PDF ที่ใหญ่ขึ้น เอกสารและตัวอย่างของห้องสมุดให้คำแนะนำสำหรับสถานการณ์ขั้นสูงเหล่านี้

#### ถาม: เป็นไปได้ไหมที่จะนำเข้าข้อมูลจากแหล่งภายนอก เช่น ฐานข้อมูลหรือสเปรดชีต เพื่อเติมองค์ประกอบอาร์เรย์

ตอบ: ได้ คุณสามารถนำเข้าข้อมูลจากแหล่งภายนอกเพื่อเติมองค์ประกอบอาร์เรย์ได้ คุณสามารถใช้เทคนิคการดึงข้อมูลและการแปลงข้อมูลใน C# เพื่อดึงข้อมูลจากฐานข้อมูล สเปรดชีต หรือแหล่งอื่นๆ จากนั้นเติมองค์ประกอบอาร์เรย์ตามนั้น

#### ถาม: ฉันจะใช้ความรู้ที่ได้รับจากบทช่วยสอนนี้เพื่อปรับปรุงคุณภาพและการใช้งานเอกสาร PDF ที่ฉันสร้างโดยทางโปรแกรมได้อย่างไร

ตอบ: ความรู้ที่ได้รับจากบทช่วยสอนนี้ช่วยให้คุณสร้างองค์ประกอบอาร์เรย์ (ตาราง) ที่มีโครงสร้างและดึงดูดสายตาในเอกสาร PDF ด้วยการผสมผสานเทคนิคเหล่านี้ คุณสามารถปรับปรุงความสามารถในการอ่าน การเข้าถึง และประสบการณ์ผู้ใช้ของ PDF ที่สร้างขึ้นแบบไดนามิก ทำให้มีข้อมูลและใช้งานง่ายยิ่งขึ้น