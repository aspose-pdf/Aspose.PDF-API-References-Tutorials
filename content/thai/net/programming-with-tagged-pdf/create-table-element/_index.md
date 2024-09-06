---
title: สร้างองค์ประกอบตาราง
linktitle: สร้างองค์ประกอบตาราง
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: คู่มือทีละขั้นตอนในการสร้างองค์ประกอบอาร์เรย์ด้วย Aspose.PDF สำหรับ .NET สร้าง PDF แบบไดนามิกด้วยตารางได้อย่างง่ายดาย
type: docs
weight: 80
url: /th/net/programming-with-tagged-pdf/create-table-element/
---
ในคู่มือทีละขั้นตอนนี้ เราจะแนะนำคุณเกี่ยวกับกระบวนการสร้างองค์ประกอบอาร์เรย์โดยใช้ Aspose.PDF สำหรับ .NET Aspose.PDF เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้คุณสามารถจัดการเอกสาร PDF ได้ด้วยโปรแกรม การสร้างองค์ประกอบอาร์เรย์เป็นข้อกำหนดทั่วไปเมื่อสร้าง PDF แบบไดนามิก และ Aspose.PDF นำเสนอวิธีการที่ง่ายและมีประสิทธิภาพในการดำเนินการดังกล่าว

มาเจาะลึกโค้ดและเรียนรู้วิธีการสร้างองค์ประกอบอาร์เรย์โดยใช้ Aspose.PDF สำหรับ .NET กัน

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
2. ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ในการเริ่มต้น ให้เปิดสภาพแวดล้อมการพัฒนา C# ของคุณและสร้างโปรเจ็กต์ใหม่ ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET ในโปรเจ็กต์ของคุณแล้ว

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างเอกสาร

 ขั้นตอนแรกคือการสร้างเอกสาร PDF ใหม่โดยใช้`Document` ระดับ.

```csharp
// สร้างเอกสาร
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

ที่นี่เรายังตั้งชื่อเรื่องและภาษาสำหรับเนื้อหาที่ถูกแท็กด้วย

## ขั้นตอนที่ 3: การสร้างองค์ประกอบอาร์เรย์

ขั้นต่อไป เราต้องสร้างองค์ประกอบอาร์เรย์และเพิ่มลงในเอกสาร เราเริ่มต้นด้วยการรับองค์ประกอบโครงสร้างราก จากนั้นจึงสร้างองค์ประกอบตารางใหม่โดยใช้`CreateTableElement` วิธี.

```csharp
// รับองค์ประกอบโครงสร้างราก
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

// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "CreateTableElement.pdf");

// การตรวจสอบการปฏิบัติตาม PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการสร้างองค์ประกอบตารางโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// รับองค์ประกอบโครงสร้างราก
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

// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "CreateTableElement.pdf");

// การตรวจสอบความสอดคล้องของ PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## บทสรุป

คุณได้เรียนรู้วิธีการสร้างองค์ประกอบอาร์เรย์โดยใช้ Aspose.PDF สำหรับ .NET แล้ว ตอนนี้คุณสามารถสร้างเอกสาร PDF ที่มีตารางแบบไดนามิกได้โดยใช้วิธีนี้ อย่าลังเลที่จะสำรวจคุณสมบัติเพิ่มเติมของ Aspose.PDF เพื่อค้นพบศักยภาพทั้งหมดของมัน

### คำถามที่พบบ่อย

#### ถาม: องค์ประกอบอาร์เรย์ในเอกสาร PDF คืออะไร และเหตุใดฉันจึงต้องสร้างองค์ประกอบอาร์เรย์โดยใช้ Aspose.PDF สำหรับ .NET

A: องค์ประกอบอาร์เรย์ในเอกสาร PDF แสดงถึงชุดข้อมูลที่มีโครงสร้าง ซึ่งมักใช้ในการสร้างตารางหรือกริด คุณอาจจำเป็นต้องสร้างองค์ประกอบอาร์เรย์โดยใช้ Aspose.PDF สำหรับ .NET เมื่อสร้าง PDF แบบไดนามิกที่ต้องการการนำเสนอข้อมูลที่มีโครงสร้าง เช่น ข้อมูลแบบตารางหรือกริด

#### ถาม: Aspose.PDF สำหรับ .NET ทำให้กระบวนการสร้างองค์ประกอบอาร์เรย์ง่ายขึ้นได้อย่างไร

A: Aspose.PDF สำหรับ .NET มีชุดคลาสและเมธอดที่ครอบคลุมซึ่งช่วยให้คุณสร้าง ปรับแต่ง และจัดการองค์ประกอบอาร์เรย์ (ตาราง) ในเอกสาร PDF ได้ด้วยโปรแกรม วิธีนี้จะช่วยขจัดความจำเป็นในการจัดการ PDF ด้วยตนเอง และทำให้การสร้างการแสดงข้อมูลที่มีโครงสร้างมีความคล่องตัวมากขึ้น

#### ถาม: ขั้นตอนสำคัญในการสร้างองค์ประกอบอาร์เรย์โดยใช้ Aspose.PDF สำหรับ .NET มีอะไรบ้าง

ขั้นตอนสำคัญ ได้แก่ การตั้งค่าสภาพแวดล้อม การสร้างเอกสาร การได้รับองค์ประกอบโครงสร้างราก การสร้างองค์ประกอบตาราง การกำหนดแถวและเซลล์ภายในตาราง และการระบุการจัดรูปแบบและคุณสมบัติสำหรับองค์ประกอบ ตัวอย่างโค้ดที่ให้มาจะสาธิตขั้นตอนเหล่านี้

####  ถาม: บทบาทหน้าที่คืออะไร`taggedContent` object play in creating an array element?

 ก. การ`taggedContent` วัตถุที่ได้มาจากเอกสาร`TaggedContent`คุณสมบัตินี้ช่วยให้คุณกำหนดโครงสร้างของเนื้อหาที่แท็กไว้ภายในเอกสาร PDF ได้ ซึ่งรวมถึงการสร้างและจัดระเบียบองค์ประกอบอาร์เรย์และองค์ประกอบย่อยตามลำดับชั้น

#### ถาม: โค้ดนี้รับประกันการเข้าถึงและความหมายขององค์ประกอบอาร์เรย์ที่สร้างขึ้นได้อย่างไร

 A: รหัสจะกำหนดคุณลักษณะต่างๆ เช่น`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , และ`ColSpan` เพื่อปรับปรุงการเข้าถึงและความหมายขององค์ประกอบอาร์เรย์ คุณลักษณะเหล่านี้ช่วยให้การแสดงข้อมูลมีโครงสร้างที่ดี ให้ข้อมูล และดึงดูดสายตา

#### ถาม: ความสำคัญของการปฏิบัติตาม PDF/UA ในบริบทของการสร้างองค์ประกอบอาร์เรย์คืออะไร

 A: การปฏิบัติตาม PDF/UA (Universal Accessibility) ช่วยให้มั่นใจว่าผู้ใช้ที่มีความทุพพลภาพสามารถเข้าถึงเอกสาร PDF ที่สร้างขึ้นได้และเป็นไปตามมาตรฐานการเข้าถึงบางประการ ตัวอย่างโค้ดจะตรวจสอบการปฏิบัติตาม PDF/UA โดยใช้`Validate` วิธีการที่ช่วยให้คุณสร้างเอกสารที่ครอบคลุมและสามารถเข้าถึงได้

#### ถาม: ฉันสามารถปรับแต่งการจัดรูปแบบและลักษณะที่ปรากฏขององค์ประกอบอาร์เรย์เพิ่มเติมได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งรูปแบบและรูปลักษณ์ขององค์ประกอบอาร์เรย์ได้โดยการปรับแอตทริบิวต์ เช่น สีพื้นหลัง สไตล์เส้นขอบ ขนาดแบบอักษร และการจัดตำแหน่ง Aspose.PDF สำหรับ .NET มีคุณสมบัติมากมายที่จะช่วยปรับแต่งการนำเสนอภาพให้ตรงตามความต้องการของคุณ

#### ถาม: ฉันจะขยายความรู้เหล่านี้เพื่อสร้างโครงสร้างตารางที่ซับซ้อนยิ่งขึ้นหรือรวมองค์ประกอบของอาร์เรย์ลงในเอกสาร PDF ขนาดใหญ่ได้อย่างไร

A: คุณสามารถขยายความรู้ได้โดยการสำรวจคุณลักษณะเพิ่มเติมของ Aspose.PDF สำหรับ .NET เช่น การรวมองค์ประกอบอาร์เรย์หลายองค์ประกอบ การสร้างตารางแบบซ้อน การเพิ่มส่วนหัวและส่วนท้าย และการรวมองค์ประกอบอาร์เรย์เข้าในเค้าโครง PDF ขนาดใหญ่ เอกสารประกอบและตัวอย่างของไลบรารีมีคำแนะนำสำหรับสถานการณ์ขั้นสูงเหล่านี้

#### ถาม: สามารถนำเข้าข้อมูลจากแหล่งภายนอก เช่น ฐานข้อมูลหรือสเปรดชีต เพื่อเติมองค์ประกอบอาร์เรย์ได้หรือไม่

A: ใช่ คุณสามารถนำเข้าข้อมูลจากแหล่งภายนอกเพื่อเติมลงในองค์ประกอบของอาร์เรย์ได้ คุณสามารถใช้เทคนิคการดึงข้อมูลและการแปลงข้อมูลใน C# เพื่อดึงข้อมูลจากฐานข้อมูล สเปรดชีต หรือแหล่งอื่นๆ จากนั้นจึงเติมลงในองค์ประกอบของอาร์เรย์ตามนั้น

#### ถาม: ฉันจะใช้ความรู้ที่ได้รับจากบทช่วยสอนนี้เพื่อปรับปรุงคุณภาพและการใช้งานของเอกสาร PDF ที่ฉันสร้างด้วยโปรแกรมได้อย่างไร

A: ความรู้ที่ได้รับจากบทช่วยสอนนี้ช่วยให้คุณสร้างองค์ประกอบอาร์เรย์ (ตาราง) ที่มีโครงสร้างและดึงดูดสายตาในเอกสาร PDF ได้ การนำเทคนิคเหล่านี้มาใช้จะช่วยเพิ่มความสามารถในการอ่าน การเข้าถึง และประสบการณ์การใช้งานของ PDF ที่สร้างแบบไดนามิก ทำให้มีข้อมูลและใช้งานง่ายขึ้น