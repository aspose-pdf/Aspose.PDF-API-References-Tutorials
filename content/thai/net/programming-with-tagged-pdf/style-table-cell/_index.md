---
title: สไตล์ตารางเซลล์
linktitle: สไตล์ตารางเซลล์
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีกำหนดรูปแบบเซลล์ตารางด้วย Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนในการสร้างและปรับแต่งตาราง
type: docs
weight: 160
url: /th/net/programming-with-tagged-pdf/style-table-cell/
---
ยินดีต้อนรับสู่บทช่วยสอนโดยละเอียดเกี่ยวกับการจัดรูปแบบเซลล์ตารางโดยใช้ Aspose.PDF สำหรับ .NET ในคู่มือนี้ เราจะอธิบายรายละเอียดแต่ละขั้นตอนของโค้ดต้นฉบับ C# ที่ให้มา เพื่อช่วยให้คุณเข้าใจวิธีจัดรูปแบบเซลล์ตาราง ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.PDF สำหรับ .NET และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณก่อนเริ่มต้น

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

เราได้สร้างเอกสารใหม่และตั้งชื่อเอกสารและภาษา

## ขั้นตอนที่ 3: การได้รับองค์ประกอบโครงสร้างราก

ในขั้นตอนนี้เราจะได้รับองค์ประกอบโครงสร้างรากสำหรับเอกสารของเรา

```csharp
// รับองค์ประกอบโครงสร้างราก
StructureElement rootElement = taggedContent.RootElement;
```

เราได้รับองค์ประกอบโครงสร้างรากซึ่งจะทำหน้าที่เป็นคอนเทนเนอร์สำหรับองค์ประกอบอาร์เรย์

## ขั้นตอนที่ 4: การสร้างองค์ประกอบโครงสร้างอาร์เรย์

ตอนนี้เรามาสร้างองค์ประกอบโครงสร้างตารางใหม่สำหรับเอกสารของเรากัน

```csharp
// สร้างองค์ประกอบโครงสร้างอาร์เรย์
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

เราได้สร้างองค์ประกอบโครงสร้างอาร์เรย์ใหม่และเพิ่มลงในองค์ประกอบโครงสร้างราก นอกจากนี้ เรายังสร้างองค์ประกอบส่วนหัว เนื้อหา และส่วนท้ายของตารางอีกด้วย

## ขั้นตอนที่ 5: การเพิ่มส่วนหัวตาราง

ในขั้นตอนนี้เราจะเพิ่มส่วนหัวตารางลงในตารางของเรา

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

เราสร้างแถวส่วนหัวสำหรับตารางของเราและเพิ่มเซลล์ส่วนหัวพร้อมด้วยคุณสมบัติการจัดรูปแบบเช่น สีพื้นหลัง ขอบ ระยะขอบ และการจัดตำแหน่ง

## ขั้นตอนที่ 6: การเพิ่มแถวเนื้อหาตาราง

ตอนนี้เรามาเพิ่มแถวเนื้อหาตารางลงในตารางของเรา
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

เราเพิ่มแถวลงในเนื้อหาของตารางโดยใช้การวนซ้ำในแต่ละเซลล์ของตาราง เราตั้งค่าคุณสมบัติการจัดรูปแบบสำหรับแต่ละเซลล์ เช่น สีพื้นหลัง ขอบ ระยะขอบ การจัดตำแหน่งข้อความ เป็นต้น

## ขั้นตอนที่ 7: การเพิ่มส่วนท้าย

สุดท้ายเราจะเพิ่มส่วนท้ายตารางลงในตารางของเรา

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

เราสร้างส่วนท้ายให้กับตารางของเราและเพิ่มเซลล์ส่วนท้ายด้วยข้อความ



## ขั้นตอนที่ 8: บันทึกเอกสาร PDF ที่ถูกแท็ก

ตอนนี้เราได้สร้างเอกสารที่มีตารางรูปแบบแล้ว เราจะบันทึกเป็นเอกสาร PDF ที่มีแท็ก

```csharp
// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "StyleTableCell.pdf");
```

เราบันทึกเอกสาร PDF ที่ถูกแท็กไว้ในไดเร็กทอรีที่ระบุ

## ขั้นตอนที่ 9: การตรวจสอบการปฏิบัติตาม PDF/UA

ต่อไปเราจะตรวจสอบความสอดคล้องของเอกสาร PDF/UA

```csharp
// การตรวจสอบการปฏิบัติตาม PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

เราอัปโหลดเอกสาร PDF ที่มีแท็ก และตรวจสอบความสอดคล้องกับ PDF/UA ด้วยการสร้างรายงาน XML

### ตัวอย่างโค้ดต้นฉบับสำหรับ Style Table Cell โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// รับองค์ประกอบโครงสร้างราก
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

// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "StyleTableCell.pdf");

// การตรวจสอบความสอดคล้องของ PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการกำหนดรูปแบบเซลล์ตารางโดยใช้ Aspose.PDF สำหรับ .NET เราได้เรียนรู้วิธีการสร้างเอกสาร เพิ่มตารางด้วยส่วนหัว แถวเนื้อหา และส่วนท้าย และปรับแต่งรูปแบบเซลล์ ในที่สุด เราได้บันทึกเอกสาร PDF ที่มีแท็กและตรวจสอบความสอดคล้องของ PDF/UA แล้ว ตอนนี้คุณสามารถใช้ Aspose.PDF สำหรับ .NET เพื่อสร้างและกำหนดรูปแบบตารางในแอปพลิเคชัน .NET ของคุณได้แล้ว

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้เกี่ยวกับการจัดรูปแบบเซลล์ตารางโดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

A: บทช่วยสอนนี้มีวัตถุประสงค์เพื่อให้คำแนะนำที่ครอบคลุมเกี่ยวกับวิธีการจัดรูปแบบเซลล์ตารางในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โดยครอบคลุมคำแนะนำทีละขั้นตอนและตัวอย่างโค้ดต้นฉบับ C# เพื่อช่วยให้คุณเข้าใจและนำการจัดรูปแบบเซลล์ตารางไปใช้

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการปฏิบัติตามบทช่วยสอนนี้คืออะไร

A: ก่อนเริ่มต้น โปรดแน่ใจว่าคุณได้ติดตั้ง Aspose.PDF สำหรับ .NET และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณแล้ว ซึ่งรวมถึงการกำหนดค่าโปรเจ็กต์ของคุณเพื่ออ้างอิงไลบรารี Aspose.PDF

#### ถาม: ฉันจะสร้างเอกสาร PDF ใหม่โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 ก: หากต้องการสร้างเอกสาร PDF ใหม่ คุณจำเป็นต้องสร้างอินสแตนซ์`Document` วัตถุจากไลบรารี Aspose.PDF โค้ดต้นฉบับ C# ที่ให้มาแสดงวิธีการสร้างเอกสารและกำหนดชื่อและภาษาของเอกสาร

#### ถาม: ความสำคัญขององค์ประกอบโครงสร้างรากในเอกสาร PDF คืออะไร

A: องค์ประกอบโครงสร้างรากทำหน้าที่เป็นตัวบรรจุองค์ประกอบโครงสร้างอื่นๆ ช่วยจัดระเบียบและจัดหมวดหมู่เนื้อหาของเอกสาร PDF มีบทบาทสำคัญในการกำหนดโครงสร้างเชิงตรรกะของเอกสาร

#### ถาม: ฉันจะสร้างองค์ประกอบโครงสร้างตารางและปรับแต่งรูปลักษณ์ของมันโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 A: คุณสามารถสร้างองค์ประกอบโครงสร้างตารางโดยใช้`CreateTableElement()` วิธีการ ซอร์สโค้ดที่ให้มาสาธิตวิธีการปรับแต่งลักษณะของตาราง รวมถึงส่วนหัว เนื้อหา และส่วนท้าย โดยการตั้งค่าคุณสมบัติ เช่น สีพื้นหลัง ขอบ ระยะขอบ และการจัดตำแหน่ง

#### ถาม: ฉันสามารถเพิ่มแถวหรือคอลัมน์หลายรายการลงในเนื้อหาตารางและปรับแต่งการจัดรูปแบบได้หรือไม่

A: ใช่ บทช่วยสอนนี้สาธิตวิธีการเพิ่มแถวและคอลัมน์หลายรายการลงในเนื้อหาตารางโดยใช้การวนซ้ำ นอกจากนี้ยังมีตัวอย่างการปรับแต่งการจัดรูปแบบเซลล์ เช่น สีพื้นหลัง ขอบ การจัดตำแหน่งข้อความ สไตล์แบบอักษร และอื่นๆ อีกมากมาย

#### ถาม: จุดประสงค์ของการตรวจสอบความสอดคล้องกับ PDF/UA คืออะไร และฉันจะดำเนินการตรวจสอบนี้ได้อย่างไร

 A: การตรวจสอบความสอดคล้องของ PDF/UA ช่วยให้มั่นใจได้ว่าเอกสาร PDF เป็นไปตามมาตรฐานการเข้าถึง ทำให้ผู้ใช้ที่มีความทุพพลภาพเข้าถึงได้ง่ายขึ้น บทช่วยสอนแสดงวิธีการตรวจสอบความสอดคล้องของ PDF/UA โดยใช้`Validate()` วิธีการและสร้างรายงาน XML

#### ถาม: ฉันจะนำแนวคิดเหล่านี้ไปใช้กับแอปพลิเคชัน .NET ของตัวเองได้อย่างไร

A: คุณสามารถใช้ตัวอย่างโค้ดต้นฉบับ C# ที่ให้มาเป็นแนวทางในการนำการจัดรูปแบบเซลล์ตารางไปใช้ในแอปพลิเคชัน .NET ของคุณเองได้ ปรับแต่งโค้ดตามต้องการเพื่อให้เหมาะกับความต้องการของคุณ และรวมโค้ดเข้ากับโครงการของคุณ

#### ถาม: มีแนวทางปฏิบัติที่ดีที่สุดที่แนะนำสำหรับการกำหนดรูปแบบเซลล์ตารางในเอกสาร PDF หรือไม่

A: เมื่อกำหนดรูปแบบเซลล์ตาราง ให้พิจารณาความต้องการของกลุ่มเป้าหมาย รวมถึงข้อกำหนดด้านการเข้าถึง ใช้สีตัดกัน แบบอักษรที่เหมาะสม และจัดตำแหน่งเซลล์ให้ชัดเจนเพื่อเพิ่มความสามารถในการอ่าน นอกจากนี้ ให้ตรวจสอบการปฏิบัติตาม PDF/UA เพื่อให้แน่ใจว่าเป็นไปตามมาตรฐานด้านการเข้าถึง

#### ถาม: ฉันสามารถทดลองใช้ฟีเจอร์อื่นๆ ของ Aspose.PDF สำหรับ .NET ในการจัดการเอกสาร PDF อะไรอีกบ้าง

A: Aspose.PDF สำหรับ .NET นำเสนอฟีเจอร์มากมายสำหรับการจัดการเอกสาร PDF รวมถึงการแยกข้อความ การแทรกภาพ การจัดการฟิลด์ฟอร์ม ลายเซ็นดิจิทัล และอื่นๆ อีกมากมาย สำรวจเอกสารและทรัพยากรอย่างเป็นทางการเพื่อเรียนรู้เกี่ยวกับฟังก์ชันเพิ่มเติม
