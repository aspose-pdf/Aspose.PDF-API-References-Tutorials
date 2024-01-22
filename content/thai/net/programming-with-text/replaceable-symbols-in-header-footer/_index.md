---
title: สัญลักษณ์ที่ถอดเปลี่ยนได้ในส่วนท้ายของส่วนหัว
linktitle: สัญลักษณ์ที่ถอดเปลี่ยนได้ในส่วนท้ายของส่วนหัว
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีใช้สัญลักษณ์ที่เปลี่ยนได้ในส่วนหัวและส่วนท้ายของเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 320
url: /th/net/programming-with-text/replaceable-symbols-in-header-footer/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีใช้สัญลักษณ์ที่เปลี่ยนได้ในส่วนหัวและส่วนท้ายของเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET เราจะดำเนินการตามกระบวนการทีละขั้นตอนในการสร้าง PDF การตั้งค่าระยะขอบ การเพิ่มส่วนหัวและส่วนท้ายด้วยสัญลักษณ์ที่เปลี่ยนได้ และบันทึก PDF โดยใช้ซอร์สโค้ด C# ที่ให้มา

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร

 ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir`ตัวแปรพร้อมเส้นทางไปยังไดเร็กทอรีที่คุณต้องการ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสาร PDF และหน้า

 ต่อไป เราจะสร้างเอกสาร PDF ใหม่และเพิ่มหน้าโดยใช้`Document` ชั้นเรียนและ`Page` คลาสจากไลบรารี Aspose.PDF

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## ขั้นตอนที่ 3: ตั้งค่าระยะขอบ

 เรากำหนดระยะขอบสำหรับหน้าโดยใช้`MarginInfo`ระดับ. ปรับค่ามาร์จิ้นตามความต้องการของคุณ

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## ขั้นตอนที่ 4: เพิ่มส่วนหัวด้วยสัญลักษณ์ที่เปลี่ยนได้

 เราสร้างก`HeaderFooter` วัตถุสำหรับหน้าและเพิ่ม`TextFragment` โดยมีสัญลักษณ์แทนกันได้

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

// เพิ่ม TextFragments เพิ่มเติมหรือปรับแต่งตามความจำเป็น
```

## ขั้นตอนที่ 5: เพิ่มส่วนท้ายด้วยสัญลักษณ์ที่เปลี่ยนได้

 ในทำนองเดียวกัน เราสร้าง`HeaderFooter` วัตถุสำหรับส่วนท้ายของหน้าและเพิ่ม`TextFragment` วัตถุที่มีสัญลักษณ์ที่เปลี่ยนได้

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// เพิ่ม TextFragments เพิ่มเติมหรือปรับแต่งตามความจำเป็น

hfFoot.Paragraphs.Add(tab2);
```

## ขั้นตอนที่ 6: บันทึกเอกสาร PDF

สุดท้าย เราจะบันทึกเอกสาร PDF ลงในไฟล์เอาต์พุตที่ระบุ

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับสัญลักษณ์ที่เปลี่ยนได้ในส่วนท้ายของส่วนหัวโดยใช้ Aspose.PDF สำหรับ .NET 
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
// กำหนดอินสแตนซ์ MarginInfo ให้กับคุณสมบัติ Margin ของ sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// สร้างอินสแตนซ์ของย่อหน้าข้อความที่จะจัดเก็บเนื้อหาที่จะแสดงเป็นส่วนหัว
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
// สร้างวัตถุ HeaderFooter สำหรับส่วน
HeaderFooter hfFoot = new HeaderFooter();
// ตั้งค่าวัตถุ HeaderFooter ให้เป็นคี่และท้ายกระดาษคู่
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// เพิ่มย่อหน้าข้อความที่มีหมายเลขหน้าปัจจุบันของจำนวนหน้าทั้งหมด
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// สร้างอินสแตนซ์ของวัตถุตาราง
Table tab2 = new Table();
// เพิ่มตารางในคอลเลกชันย่อหน้าของส่วนที่ต้องการ
hfFoot.Paragraphs.Add(tab2);
// กำหนดความกว้างของคอลัมน์ของตาราง
tab2.ColumnWidths = "165 172 165";
// สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// ตั้งค่าการจัดแนวข้อความในแนวตั้งให้จัดกึ่งกลาง
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java เป็นการคอมไพล์ของทุกคอมโพเนนต์ Java ที่นำเสนอโดย Aspose โดยจะคอมไพล์บน #$NL" + "ทุกวันเพื่อให้แน่ใจว่ามีเวอร์ชันล่าสุดของแต่ละคอมโพเนนต์ ของส่วนประกอบ Java ของเรา #$NL " + "การใช้ Aspose.Total สำหรับนักพัฒนา Java สามารถสร้างแอปพลิเคชันได้หลากหลาย #$NL #$NL #$NP" + "Aspose.Total สำหรับ Java เป็นการคอมไพล์ของทุกองค์ประกอบ Java นำเสนอโดย Aspose มันถูกคอมไพล์บน #$NL" + "ทุกวันเพื่อให้แน่ใจว่ามีเวอร์ชันล่าสุดของแต่ละคอมโพเนนต์ Java ของเรา #$NL " + "การใช้ Aspose.Total สำหรับนักพัฒนา Java สามารถสร้าง ช่วงของแอปพลิเคชัน #$NL #$NL #$NP" + "Aspose.Total สำหรับ Java คือการคอมไพล์คอมโพเนนต์ Java ทุกตัวที่นำเสนอโดย Aspose โดยคอมไพล์บน#$NL" + "ทุกวันเพื่อให้แน่ใจว่าคอมโพเนนต์มีองค์ประกอบมากที่สุด เวอร์ชันล่าสุดของแต่ละองค์ประกอบ Java ของเรา #$NL " + "การใช้ Aspose.Total สำหรับนักพัฒนา Java สามารถสร้างแอปพลิเคชันได้หลากหลาย #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// เพิ่มตารางในคอลเลกชันย่อหน้าของส่วนที่ต้องการ
page.Paragraphs.Add(table);
// ตั้งค่าเส้นขอบเซลล์เริ่มต้นโดยใช้วัตถุ BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// ตั้งค่าเส้นขอบตารางโดยใช้วัตถุ BorderInfo ที่กำหนดเองอื่น
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// สร้างแถวในตารางแล้วสร้างเซลล์ในแถว
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

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีใช้สัญลักษณ์ที่เปลี่ยนได้ในส่วนหัวและส่วนท้ายของเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและดำเนินการโค้ด C# ที่ให้มา คุณสามารถสร้าง PDF กำหนดระยะขอบ เพิ่มส่วนหัวและส่วนท้ายด้วยสัญลักษณ์ที่เปลี่ยนได้ และบันทึก PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "สัญลักษณ์ที่เปลี่ยนได้ในส่วนท้ายของส่วนหัว" คืออะไร

ตอบ: บทช่วยสอน "สัญลักษณ์ที่เปลี่ยนได้ในส่วนท้ายของส่วนหัว" มีวัตถุประสงค์เพื่อแนะนำคุณตลอดกระบวนการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อเพิ่มสัญลักษณ์ที่เปลี่ยนได้ให้กับส่วนหัวและส่วนท้ายของเอกสาร PDF สัญลักษณ์ที่เปลี่ยนได้ทำให้คุณสามารถแทนที่ตัวยึดตำแหน่งเฉพาะด้วยค่าจริงแบบไดนามิกเมื่อสร้าง PDF

#### ถาม: สัญลักษณ์ที่สามารถเปลี่ยนได้ในบริบทของส่วนหัวและส่วนท้ายของ PDF คืออะไร

ตอบ: สัญลักษณ์ที่เปลี่ยนได้คือตัวยึดตำแหน่งที่คุณสามารถแทรกลงในส่วนหัวและส่วนท้ายของเอกสาร PDF ได้ สัญลักษณ์เหล่านี้ทำหน้าที่เป็นตัวแทนแบบไดนามิกสำหรับค่าที่สามารถกรอกในขณะรันไทม์ เช่น หมายเลขหน้า วันที่ และข้อมูลที่กำหนดเอง

#### ถาม: เหตุใดฉันจึงต้องการใช้สัญลักษณ์ที่เปลี่ยนได้ในส่วนหัวและส่วนท้ายของ PDF

ตอบ: สัญลักษณ์ที่สามารถเปลี่ยนได้ในส่วนหัวและส่วนท้ายจะมีประโยชน์เมื่อคุณต้องการรวมข้อมูลแบบไดนามิกในเอกสาร PDF ของคุณ เช่น หมายเลขหน้า วันที่ หรือข้อมูลตัวแปรอื่นๆ ที่อาจเปลี่ยนแปลงเมื่อสร้างเอกสาร

#### ถาม: ฉันจะกำหนดระยะขอบสำหรับหน้า PDF ได้อย่างไร

 ตอบ: คุณสามารถตั้งค่าระยะขอบสำหรับหน้า PDF ได้โดยใช้`MarginInfo` ชั้นเรียนและมอบหมายให้`Margin` ทรัพย์สินของ`PageInfo` ของหน้า ปรับค่ามาร์จิ้นตามต้องการ

#### ถาม: ฉันจะเพิ่มสัญลักษณ์ที่เปลี่ยนได้ลงในส่วนหัวและส่วนท้ายได้อย่างไร

 ตอบ: คุณสามารถเพิ่มสัญลักษณ์ทดแทนได้โดยการสร้าง`HeaderFooter` วัตถุสำหรับส่วนหัวและส่วนท้ายของหน้า จากนั้นคุณสามารถเพิ่มได้`TextFragment`วัตถุที่มีข้อความที่ต้องการรวมทั้งสัญลักษณ์ที่เปลี่ยนได้ไปที่`Paragraphs` คอลเลกชันของ`HeaderFooter` วัตถุ.

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของสัญลักษณ์ที่เปลี่ยนได้หรือไม่?

 ตอบ: ได้ คุณสามารถปรับแต่งรูปลักษณ์ของสัญลักษณ์ที่เปลี่ยนได้โดยการปรับเปลี่ยนคุณสมบัติของ`TextFragment` วัตถุที่มีสัญลักษณ์ คุณสามารถตั้งค่าคุณสมบัติ เช่น แบบอักษร ขนาดแบบอักษร สี การจัดตำแหน่ง และระยะห่างระหว่างบรรทัด

#### ถาม: ฉันสามารถใช้สัญลักษณ์ทดแทนประเภทใดได้บ้าง

ตอบ: คุณสามารถใช้สัญลักษณ์ทดแทนได้หลากหลาย เช่น:

- `$p`: หมายเลขหน้าปัจจุบัน
- `$P`: จำนวนหน้าทั้งหมด
- `$d`: วันที่ปัจจุบัน.
- `$t`: เวลาปัจจุบัน
- ตัวยึดตำแหน่งแบบกำหนดเองที่คุณกำหนด

#### ถาม: ฉันสามารถใส่ข้อความและการจัดรูปแบบอื่นรอบๆ สัญลักษณ์ที่เปลี่ยนได้หรือไม่

 ตอบ: ได้ คุณสามารถใส่ข้อความและการจัดรูปแบบอื่นรอบๆ สัญลักษณ์ที่เปลี่ยนได้ภายใน`TextFragment` วัตถุ สิ่งนี้ช่วยให้คุณสร้างส่วนหัวและส่วนท้ายที่ซับซ้อนมากขึ้นซึ่งรวมเนื้อหาแบบไดนามิกและแบบคงที่

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่สร้างขึ้นได้อย่างไร

 ตอบ: หากต้องการบันทึกเอกสาร PDF ที่สร้างขึ้น คุณสามารถใช้ไฟล์`Save` วิธีการของ`Document`ระดับ. ระบุเส้นทางไฟล์เอาต์พุตที่ต้องการและชื่อเป็นอาร์กิวเมนต์

#### ถาม: จำเป็นต้องมี Aspose License ที่ถูกต้องสำหรับบทช่วยสอนนี้หรือไม่

ตอบ: ใช่ จำเป็นต้องมี Aspose License ที่ถูกต้องเพื่อรันโค้ดได้สำเร็จในบทช่วยสอนนี้ คุณสามารถขอรับใบอนุญาตแบบเต็มหรือใบอนุญาตชั่วคราว 30 วันได้จากเว็บไซต์ Aspose