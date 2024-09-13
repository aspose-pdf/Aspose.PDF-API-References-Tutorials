---
title: สัญลักษณ์ที่แทนที่ได้ในส่วนหัวส่วนท้าย
linktitle: สัญลักษณ์ที่แทนที่ได้ในส่วนหัวส่วนท้าย
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีใช้สัญลักษณ์ที่แทนที่ได้ในส่วนหัวและส่วนท้ายของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 320
url: /th/net/programming-with-text/replaceable-symbols-in-header-footer/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการใช้สัญลักษณ์ที่แทนที่ได้ในส่วนหัวและส่วนท้ายของเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะอธิบายกระบวนการทีละขั้นตอนในการสร้าง PDF ตั้งค่าระยะขอบ เพิ่มส่วนหัวและส่วนท้ายด้วยสัญลักษณ์ที่แทนที่ได้ และบันทึก PDF โดยใช้โค้ดต้นฉบับ C# ที่ให้มา

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

 ขั้นแรก คุณต้องตั้งค่าเส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไดเร็กทอรีที่คุณต้องการ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารและหน้า PDF

 ถัดไป เราจะสร้างเอกสาร PDF ใหม่และเพิ่มหน้าลงไปโดยใช้`Document` ชั้นเรียนและ`Page` คลาสจากไลบรารี Aspose.PDF

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 3: ตั้งค่าระยะขอบ

 เรากำหนดระยะขอบของหน้าโดยใช้`MarginInfo` คลาส ปรับค่าระยะขอบให้เหมาะสมตามความต้องการของคุณ

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## ขั้นตอนที่ 4: เพิ่มส่วนหัวพร้อมสัญลักษณ์ที่สามารถเปลี่ยนแทนได้

 เราสร้าง`HeaderFooter` วัตถุสำหรับหน้าและเพิ่ม`TextFragment` ซึ่งมีสัญลักษณ์ที่สามารถทดแทนได้

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// ตั้งค่าคุณสมบัติข้อความหากต้องการ
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// เพิ่ม TextFragments เพิ่มเติมหรือปรับแต่งตามความต้องการ
```

## ขั้นตอนที่ 5: เพิ่มส่วนท้ายด้วยสัญลักษณ์ที่สามารถเปลี่ยนแทนได้

 ในทำนองเดียวกันเราสร้าง`HeaderFooter` วัตถุสำหรับส่วนท้ายของหน้าและเพิ่ม`TextFragment` วัตถุซึ่งมีสัญลักษณ์ที่สามารถแทนที่ได้

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// เพิ่ม TextFragments เพิ่มเติมหรือปรับแต่งตามความต้องการ

hfFoot.Paragraphs.Add(tab2);
```

## ขั้นตอนที่ 6: บันทึกเอกสาร PDF

สุดท้ายเราบันทึกเอกสาร PDF ลงในไฟล์เอาท์พุตที่ระบุ

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับสัญลักษณ์ที่แทนที่ได้ในส่วนหัวและส่วนท้ายโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
//กำหนดอินสแตนซ์ marginInfo ให้กับคุณสมบัติ Margin ของ sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// สร้างตัวอย่างย่อหน้าข้อความที่จะเก็บเนื้อหาที่จะแสดงเป็นส่วนหัว
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// สร้างวัตถุ HeaderFooter สำหรับส่วนนี้
HeaderFooter hfFoot = new HeaderFooter();
// ตั้งค่าวัตถุ HeaderFooter ให้เป็นส่วนท้ายคี่และคู่
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// เพิ่มย่อหน้าข้อความที่มีหมายเลขหน้าปัจจุบันหรือจำนวนหน้าทั้งหมด
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// สร้างอินสแตนซ์ของวัตถุตาราง
Table tab2 = new Table();
// เพิ่มตารางในคอลเลกชันย่อหน้าของส่วนที่ต้องการ
hfFoot.Paragraphs.Add(tab2);
// ตั้งค่าด้วยความกว้างของคอลัมน์ของตาราง
tab2.ColumnWidths = "165 172 165";
//สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// ตั้งค่าการจัดแนวแนวตั้งของข้อความให้จัดกึ่งกลาง
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total สำหรับ Java คือการคอมไพล์ส่วนประกอบ Java ทุกตัวที่ Aspose เสนอ คอมไพล์ทุกวันเพื่อให้แน่ใจว่ามีเวอร์ชันล่าสุดของส่วนประกอบ Java แต่ละตัวของเรา #$NL " + "การใช้ Aspose.Total สำหรับนักพัฒนา Java สามารถสร้างแอปพลิเคชันได้หลากหลาย #$NL #$NL #$NP" + "Aspose.Total สำหรับ Java คือการคอมไพล์ส่วนประกอบ Java ทุกตัวที่ Aspose เสนอ คอมไพล์ทุกวันเพื่อให้แน่ใจว่ามีเวอร์ชันล่าสุดของส่วนประกอบ Java แต่ละตัวของเรา #$NL " + "การใช้ Aspose.Total สำหรับนักพัฒนา Java สามารถสร้างแอปพลิเคชันได้หลากหลาย #$NL #$NL #$NP" + "Aspose.Total สำหรับ Java คือการคอมไพล์ส่วนประกอบ Java ทุกตัวที่ Aspose เสนอ คอมไพล์ทุกวันเพื่อให้แน่ใจว่ามีเวอร์ชันล่าสุดของส่วนประกอบ Java แต่ละตัวของเรา #$NL ส่วนประกอบ #$NL " + "การใช้ Aspose.Total สำหรับนักพัฒนา Java สามารถสร้างแอปพลิเคชันได้หลากหลาย #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// เพิ่มตารางในคอลเลกชันย่อหน้าของส่วนที่ต้องการ
page.Paragraphs.Add(table);
// ตั้งค่าเส้นขอบเซลล์เริ่มต้นโดยใช้ BorderInfo object
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// กำหนดเส้นขอบตารางโดยใช้ BorderInfo วัตถุที่กำหนดเองอื่น
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
//สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีใช้สัญลักษณ์ที่แทนที่ได้ในส่วนหัวและส่วนท้ายของเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โดยปฏิบัติตามคำแนะนำทีละขั้นตอนและดำเนินการตามโค้ด C# ที่ให้มา คุณก็สามารถสร้าง PDF กำหนดระยะขอบ เพิ่มส่วนหัวและส่วนท้ายด้วยสัญลักษณ์ที่แทนที่ได้ และบันทึก PDF ได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "สัญลักษณ์ที่แทนที่ได้ในส่วนหัวส่วนท้าย" คืออะไร

A: บทช่วยสอน "สัญลักษณ์ที่แทนที่ได้ในส่วนหัวและส่วนท้าย" มีวัตถุประสงค์เพื่อแนะนำคุณตลอดขั้นตอนการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อเพิ่มสัญลักษณ์ที่แทนที่ได้ลงในส่วนหัวและส่วนท้ายของเอกสาร PDF สัญลักษณ์ที่แทนที่ได้ช่วยให้คุณสามารถแทนที่ตัวแทนเฉพาะด้วยค่าจริงแบบไดนามิกเมื่อสร้าง PDF

#### ถาม: สัญลักษณ์ที่สามารถแทนที่ได้ในบริบทของส่วนหัวและส่วนท้ายของ PDF คืออะไร

A: สัญลักษณ์ที่แทนที่ได้คือตัวแทนที่คุณสามารถแทรกเข้าไปในส่วนหัวและส่วนท้ายของเอกสาร PDF สัญลักษณ์เหล่านี้ทำหน้าที่เป็นตัวแทนแบบไดนามิกสำหรับค่าที่สามารถกรอกได้ในระหว่างการรันไทม์ เช่น หมายเลขหน้า วันที่ และข้อมูลที่กำหนดเอง

#### ถาม: เหตุใดฉันจึงต้องการใช้สัญลักษณ์ที่สามารถแทนที่ได้ในส่วนหัวและส่วนท้ายของ PDF

ตอบ: สัญลักษณ์ที่แทนที่ได้ในส่วนหัวและส่วนท้ายนั้นมีประโยชน์เมื่อคุณต้องการรวมข้อมูลแบบไดนามิก เช่น หมายเลขหน้า วันที่ หรือข้อมูลตัวแปรอื่นๆ ที่อาจเปลี่ยนแปลงเมื่อสร้างเอกสารลงในเอกสาร PDF ของคุณ

#### ถาม: ฉันจะตั้งค่าระยะขอบให้กับหน้า PDF ได้อย่างไร

 A: คุณสามารถตั้งค่าระยะขอบสำหรับหน้า PDF ได้โดยใช้`MarginInfo` ชั้นเรียนและมอบหมายให้กับ`Margin` ทรัพย์สินของ`PageInfo` ของหน้า ปรับค่าระยะขอบตามต้องการ

#### ถาม: ฉันจะเพิ่มสัญลักษณ์ที่สามารถแทนที่ได้ลงในส่วนหัวและส่วนท้ายได้อย่างไร

 A: คุณสามารถเพิ่มสัญลักษณ์ที่แทนที่ได้โดยการสร้าง`HeaderFooter` วัตถุสำหรับส่วนหัวและส่วนท้ายของหน้า จากนั้นคุณสามารถเพิ่ม`TextFragment`วัตถุที่มีข้อความตามต้องการ รวมถึงสัญลักษณ์ที่สามารถแทนที่ได้`Paragraphs` การรวบรวมของ`HeaderFooter` วัตถุ.

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของสัญลักษณ์ที่สามารถเปลี่ยนได้หรือไม่

 A: ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏของสัญลักษณ์ที่สามารถเปลี่ยนได้โดยการปรับเปลี่ยนคุณสมบัติของ`TextFragment` วัตถุที่มีสัญลักษณ์ คุณสามารถตั้งค่าคุณสมบัติต่างๆ เช่น แบบอักษร ขนาดแบบอักษร สี การจัดตำแหน่ง และระยะห่างระหว่างบรรทัด

#### ถาม: ฉันสามารถใช้สัญลักษณ์ทดแทนแบบใดได้บ้าง?

A: คุณสามารถใช้สัญลักษณ์ที่สามารถแทนที่ได้หลากหลาย เช่น:

- `$p`: เลขที่หน้าปัจจุบัน.
- `$P`: จำนวนหน้าทั้งหมด.
- `$d`: วันที่ปัจจุบัน.
- `$t`: เวลาปัจจุบัน.
- ตัวแทนที่กำหนดเองที่คุณกำหนด

#### ถาม: ฉันสามารถรวมข้อความและการจัดรูปแบบอื่นๆ รอบสัญลักษณ์ที่แทนที่ได้หรือไม่

 A: ใช่ คุณสามารถรวมข้อความและการจัดรูปแบบอื่นๆ รอบๆ สัญลักษณ์ที่แทนที่ได้ภายใน`TextFragment` วัตถุ ซึ่งจะช่วยให้คุณสร้างส่วนหัวและส่วนท้ายที่ซับซ้อนมากขึ้นได้ โดยรวมเนื้อหาแบบไดนามิกและแบบคงที่

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่สร้างขึ้นได้อย่างไร

 A: หากต้องการบันทึกเอกสาร PDF ที่สร้างขึ้น คุณสามารถใช้`Save` วิธีการของ`Document`คลาส ระบุเส้นทางและชื่อไฟล์เอาท์พุตที่ต้องการเป็นอาร์กิวเมนต์

#### ถาม: จำเป็นต้องมีใบอนุญาต Aspose ที่ถูกต้องสำหรับบทช่วยสอนนี้หรือไม่

A: ใช่ ต้องมีใบอนุญาต Aspose ที่ถูกต้องจึงจะสามารถรันโค้ดได้สำเร็จในบทช่วยสอนนี้ คุณสามารถขอใบอนุญาตฉบับเต็มหรือใบอนุญาตชั่วคราว 30 วันได้จากเว็บไซต์ Aspose