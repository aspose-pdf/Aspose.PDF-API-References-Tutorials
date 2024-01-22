---
title: เซลล์ตารางสไตล์
linktitle: เซลล์ตารางสไตล์
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีจัดสไตล์เซลล์ตารางด้วย Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนในการสร้างและปรับแต่งตาราง
type: docs
weight: 160
url: /th/net/programming-with-tagged-pdf/style-table-cell/
---
ยินดีต้อนรับสู่บทช่วยสอนโดยละเอียดเกี่ยวกับการจัดรูปแบบเซลล์ตารางโดยใช้ Aspose.PDF สำหรับ .NET ในคู่มือนี้ เราจะอธิบายรายละเอียดแต่ละขั้นตอนของซอร์สโค้ด C# ที่ให้มาเพื่อช่วยให้คุณเข้าใจวิธีจัดรูปแบบเซลล์ตาราง ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.PDF สำหรับ .NET และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณก่อนที่จะเริ่มต้น

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
taggedContent.SetTitle("Example of table cell formatting");
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
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

เราได้สร้างองค์ประกอบโครงสร้างอาร์เรย์ใหม่และเพิ่มลงในองค์ประกอบโครงสร้างราก นอกจากนี้เรายังสร้างองค์ประกอบส่วนหัว เนื้อหา และส่วนท้ายของตารางด้วย

## ขั้นตอนที่ 5: การเพิ่มส่วนหัวของตาราง

ในขั้นตอนนี้ เราจะเพิ่มส่วนหัวของตารางลงในตารางของเรา

```csharp
// จำนวนแถวและคอลัมน์ในตาราง
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// สร้างแถวส่วนหัวของตาราง
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

เราสร้างแถวส่วนหัวสำหรับตารางของเราและเพิ่มเซลล์ส่วนหัวที่มีคุณสมบัติการจัดรูปแบบ เช่น สีพื้นหลัง เส้นขอบ ระยะขอบ และการจัดตำแหน่ง

## ขั้นตอนที่ 6: การเพิ่มแถวเนื้อหาของตาราง

ตอนนี้เรามาเพิ่มแถวเนื้อหาของตารางลงในตารางของเรา
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

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
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
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
```

เราได้เพิ่มแถวลงในเนื้อหาของตารางโดยใช้ลูปเพื่อวนซ้ำแต่ละเซลล์ของตาราง เราตั้งค่าคุณสมบัติการจัดรูปแบบสำหรับแต่ละเซลล์ เช่น สีพื้นหลัง เส้นขอบ ระยะขอบ การจัดตำแหน่งข้อความ ฯลฯ

## ขั้นตอนที่ 7: การเพิ่มส่วนท้าย

สุดท้ายนี้ เราจะเพิ่มส่วนท้ายของตารางลงในตารางของเรา

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

เราสร้างส่วนท้ายสำหรับตารางของเราและเพิ่มเซลล์ส่วนท้ายพร้อมข้อความ



## ขั้นตอนที่ 8: บันทึกเอกสาร PDF ที่แท็ก

ตอนนี้เราได้สร้างเอกสารของเราด้วยตารางที่มีสไตล์แล้ว เราจะบันทึกเป็นเอกสาร PDF ที่ติดแท็ก

```csharp
// บันทึกเอกสาร PDF ที่แท็ก
document.Save(dataDir + "StyleTableCell.pdf");
```

เราบันทึกเอกสาร PDF ที่แท็กไว้ในไดเร็กทอรีที่ระบุ

## ขั้นตอนที่ 9: การตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA

ต่อไป เราจะตรวจสอบความสอดคล้องของ PDF/UA ของเอกสารของเรา

```csharp
// การตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

เราอัปโหลดเอกสาร PDF ที่ติดแท็กและตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA โดยการสร้างรายงาน XML

### ตัวอย่างซอร์สโค้ดสำหรับ Style Table Cell โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// รับองค์ประกอบโครงสร้างรูท
StructureElement rootElement = taggedContent.RootElement;

// สร้างองค์ประกอบโครงสร้างตาราง
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
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
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// บันทึกเอกสาร PDF ที่ติดแท็ก
document.Save(dataDir + "StyleTableCell.pdf");

// ตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีจัดสไตล์เซลล์ตารางโดยใช้ Aspose.PDF สำหรับ .NET เราได้เห็นวิธีการสร้างเอกสาร เพิ่มตารางที่มีส่วนหัว แถวเนื้อหา และส่วนท้าย และปรับแต่งสไตล์เซลล์ สุดท้าย เราได้บันทึกเอกสาร PDF ที่แท็กและตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA ตอนนี้คุณสามารถใช้ Aspose.PDF สำหรับ .NET เพื่อสร้างและจัดรูปแบบตารางในแอปพลิเคชัน .NET ของคุณได้แล้ว

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้เกี่ยวกับการจัดรูปแบบเซลล์ตารางโดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: บทช่วยสอนนี้มีจุดมุ่งหมายเพื่อให้คำแนะนำที่ครอบคลุมเกี่ยวกับวิธีจัดรูปแบบเซลล์ตารางในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โดยครอบคลุมคำแนะนำทีละขั้นตอนและตัวอย่างซอร์สโค้ด C# เพื่อช่วยให้คุณเข้าใจและนำการจัดรูปแบบเซลล์ตารางไปใช้

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการติดตามบทช่วยสอนนี้มีอะไรบ้าง

ตอบ: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.PDF สำหรับ .NET และได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณแล้ว ซึ่งรวมถึงการกำหนดค่าโปรเจ็กต์ของคุณเพื่ออ้างอิงไลบรารี Aspose.PDF

#### ถาม: ฉันจะสร้างเอกสาร PDF ใหม่โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการสร้างเอกสาร PDF ใหม่ คุณจะต้องสร้างอินสแตนซ์ a`Document` วัตถุจากไลบรารี Aspose.PDF ซอร์สโค้ด C# ที่ให้มาสาธิตวิธีการสร้างเอกสารและตั้งชื่อและภาษา

#### ถาม: องค์ประกอบโครงสร้างรากในเอกสาร PDF มีความสำคัญอย่างไร

ตอบ: องค์ประกอบโครงสร้างรากทำหน้าที่เป็นคอนเทนเนอร์สำหรับองค์ประกอบโครงสร้างอื่นๆ ซึ่งช่วยจัดระเบียบและจัดหมวดหมู่เนื้อหาของเอกสาร PDF มีบทบาทสำคัญในการสร้างโครงสร้างเชิงตรรกะของเอกสาร

#### ถาม: ฉันจะสร้างองค์ประกอบโครงสร้างตารางและปรับแต่งลักษณะที่ปรากฏโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 ตอบ: คุณสามารถสร้างองค์ประกอบโครงสร้างตารางโดยใช้`CreateTableElement()` วิธี. ซอร์สโค้ดที่ให้มาสาธิตวิธีปรับแต่งลักษณะที่ปรากฏของตาราง รวมถึงส่วนหัว เนื้อหา และส่วนท้ายของตาราง โดยการตั้งค่าคุณสมบัติ เช่น สีพื้นหลัง เส้นขอบ ระยะขอบ และการจัดตำแหน่ง

#### ถาม: ฉันสามารถเพิ่มหลายแถวและคอลัมน์ลงในเนื้อหาของตารางและปรับแต่งการจัดรูปแบบได้หรือไม่

ตอบ: ใช่ บทช่วยสอนสาธิตวิธีเพิ่มแถวและคอลัมน์หลายรายการให้กับเนื้อหาของตารางโดยใช้ลูป นอกจากนี้ยังมีตัวอย่างการปรับแต่งการจัดรูปแบบเซลล์ เช่น สีพื้นหลัง เส้นขอบ การจัดแนวข้อความ ลักษณะแบบอักษร และอื่นๆ

#### ถาม: จุดประสงค์ของการตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA คืออะไร และฉันจะดำเนินการตรวจสอบนี้ได้อย่างไร

 ตอบ: การตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA ช่วยให้มั่นใจได้ว่าเอกสาร PDF เป็นไปตามมาตรฐานการเข้าถึง ทำให้ผู้ใช้ที่มีความพิการสามารถเข้าถึงได้มากขึ้น บทช่วยสอนนี้แสดงวิธีการตรวจสอบความสอดคล้องของ PDF/UA โดยใช้`Validate()` วิธีการและสร้างรายงาน XML

#### ถาม: ฉันจะนำแนวคิดเหล่านี้ไปใช้กับแอปพลิเคชัน .NET ของตัวเองได้อย่างไร

ตอบ: คุณสามารถใช้ตัวอย่างซอร์สโค้ด C# ที่ให้มาเพื่อเป็นแนวทางในการใช้การจัดรูปแบบเซลล์ตารางในแอปพลิเคชัน .NET ของคุณเอง ปรับแต่งโค้ดตามความจำเป็นเพื่อให้เหมาะกับความต้องการของคุณและรวมเข้ากับโปรเจ็กต์ของคุณ

#### ถาม: มีวิธีปฏิบัติที่ดีที่สุดที่แนะนำสำหรับการจัดสไตล์เซลล์ตารางในเอกสาร PDF หรือไม่

ตอบ: เมื่อจัดรูปแบบเซลล์ตาราง ให้พิจารณาความต้องการของผู้ชมของคุณ รวมถึงข้อกำหนดในการเข้าถึงด้วย ใช้สีที่ตัดกัน แบบอักษรที่เหมาะสม และการจัดแนวเซลล์ที่ชัดเจนเพื่อให้อ่านง่ายขึ้น นอกจากนี้ ตรวจสอบการปฏิบัติตามข้อกำหนด PDF/UA เพื่อให้มั่นใจว่าเป็นไปตามมาตรฐานการเข้าถึง

#### ถาม: ฉันสามารถสำรวจคุณสมบัติอื่นใดของ Aspose.PDF สำหรับ .NET เพื่อจัดการเอกสาร PDF ได้บ้าง

ตอบ: Aspose.PDF สำหรับ .NET นำเสนอคุณสมบัติที่หลากหลายสำหรับการจัดการเอกสาร PDF รวมถึงการแตกข้อความ การแทรกรูปภาพ การจัดการฟิลด์แบบฟอร์ม ลายเซ็นดิจิทัล และอื่นๆ อีกมากมาย สำรวจเอกสารและแหล่งข้อมูลอย่างเป็นทางการเพื่อเรียนรู้เกี่ยวกับฟังก์ชันเพิ่มเติม
