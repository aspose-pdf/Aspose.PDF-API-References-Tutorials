---
title: แทรกตัวแบ่งหน้าในไฟล์ PDF
linktitle: แทรกตัวแบ่งหน้าในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีแทรกตัวแบ่งหน้าในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 110
url: /th/net/programming-with-tables/insert-page-break/
---
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีแทรกตัวแบ่งหน้าในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายโค้ดต้นฉบับใน C# ทีละขั้นตอน เมื่อจบบทช่วยสอนนี้ คุณจะทราบวิธีเพิ่มตัวแบ่งหน้าหลังบรรทัดจำนวนหนึ่งบนตารางของเอกสาร PDF มาเริ่มกันเลย!

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ตรวจสอบให้แน่ใจว่าคุณได้กำหนดค่าสภาพแวดล้อมการพัฒนา C# ด้วย Aspose.PDF สำหรับ .NET แล้ว เพิ่มการอ้างอิงไปยังไลบรารีและนำเข้าเนมสเปซที่จำเป็น

## ขั้นตอนที่ 2: การสร้างเอกสารและตาราง
เราสร้างอินสแตนซ์เอกสารใหม่และเพิ่มหน้าลงในเอกสารนี้ จากนั้นเราสร้างอินสแตนซ์ตารางเพื่อแสดงตารางในเอกสาร PDF นอกจากนี้ เรายังกำหนดรูปแบบเส้นขอบสำหรับตารางอีกด้วย

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## ขั้นตอนที่ 3: เพิ่มแถวลงในตาราง
เราใช้ลูปเพื่อเพิ่ม 200 แถวลงในอาร์เรย์ สำหรับแต่ละแถว เราสร้างอินสแตนซ์ของ Row และเพิ่มเซลล์สองเซลล์ที่มีเนื้อหาเป็นข้อความ

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // เมื่อเพิ่ม 10 บรรทัด เราจะแทรกตัวแบ่งหน้าใหม่
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## ขั้นตอนที่ 4: การเพิ่มตารางลงในเอกสาร
เราเพิ่มตารางลงในคอลเล็กชั่นย่อหน้าของหน้าเอกสาร

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## ขั้นตอนที่ 5: บันทึกเอกสาร
เราบันทึกเอกสาร PDF โดยแทรกตัวแบ่งหน้าไว้

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการแทรกตัวแบ่งหน้าโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างอินสแตนซ์เอกสาร
Document doc = new Document();
// เพิ่มหน้าเข้าไปยังคอลเลคชันไฟล์ PDF
doc.Pages.Add();
// สร้างอินสแตนซ์ตาราง
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// ตั้งค่ารูปแบบขอบสำหรับตาราง
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// ตั้งค่ารูปแบบเส้นขอบเริ่มต้นสำหรับตารางโดยมีสีเส้นขอบเป็นสีแดง
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// ระบุความกว้างของคอลัมน์ตาราง
tab.ColumnWidths = "100 100";
// สร้างลูปเพื่อเพิ่ม 200 แถวให้กับตาราง
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// เมื่อเพิ่ม 10 แถว ให้แสดงแถวใหม่ในหน้าใหม่
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// เพิ่มตารางลงในคอลเลกชันย่อหน้าของไฟล์ PDF
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// บันทึกเอกสาร PDF
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแทรกตัวแบ่งหน้าในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้คำแนะนำทีละขั้นตอนนี้เพื่อเพิ่มตัวแบ่งหน้าหลังบรรทัดจำนวนหนึ่งบนตารางในเอกสาร PDF โดยใช้ C#

### คำถามที่พบบ่อยสำหรับการแทรกตัวแบ่งหน้าในไฟล์ PDF

#### ถาม: ฉันจะเปลี่ยนขนาดหน้าสำหรับหน้าใหม่ที่ถูกสร้างหลังจากแบ่งหน้าได้อย่างไร

 A: หากต้องการเปลี่ยนขนาดหน้าสำหรับหน้าใหม่ที่สร้างขึ้นหลังจากแบ่งหน้า คุณสามารถตั้งค่าได้`PageSize` ทรัพย์สินของ`Page` วัตถุ ตัวอย่างเช่น คุณสามารถใช้โค้ดต่อไปนี้เพื่อตั้งค่าขนาดหน้าเป็น A4:

```csharp
// ตั้งค่าขนาดหน้าเป็น A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### ถาม: ฉันสามารถควบคุมระยะขอบหน้าสำหรับหน้าใหม่หลังจากแบ่งหน้าได้หรือไม่

 A: ใช่ คุณสามารถควบคุมระยะขอบหน้าสำหรับหน้าใหม่หลังจากแบ่งหน้าได้ ใช้`Margin` ทรัพย์สินของ`Page` วัตถุสำหรับตั้งค่าระยะขอบหน้า เช่น หากต้องการตั้งค่าระยะขอบทั้งหมดเป็น 10 จุด คุณสามารถใช้โค้ดต่อไปนี้:

```csharp
// ตั้งค่าระยะขอบทั้งหมดเป็น 10 จุด
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### ถาม: เป็นไปได้ไหมที่จะเพิ่มส่วนหัวและส่วนท้ายลงในหน้าใหม่หลังจากแบ่งหน้า?

 A: ใช่ คุณสามารถเพิ่มส่วนหัวและส่วนท้ายในหน้าใหม่หลังจากแบ่งหน้าได้ ใช้`Page.Header` และ`Page.Footer` คุณสมบัติในการเพิ่มเนื้อหาลงในส่วนหัวและส่วนท้ายของหน้า ตัวอย่างเช่น:

```csharp
// เพิ่มส่วนหัวให้กับหน้าใหม่
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// เพิ่มส่วนท้ายของหน้าใหม่
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### ถาม: ฉันสามารถแทรกตัวแบ่งหน้าในตำแหน่งที่เจาะจงอื่นๆ นอกเหนือจากหลังจากจำนวนแถวที่กำหนดได้หรือไม่

 A: ใช่ คุณสามารถแทรกตัวแบ่งหน้าในตำแหน่งเฉพาะอื่นๆ นอกเหนือจากหลังจำนวนแถวที่กำหนด คุณสามารถตั้งค่าได้`IsInNewPage` ทรัพย์สินของแถว`true` เพื่อบังคับให้ตารางเริ่มหน้าใหม่หลังจากแถวนั้น

#### ถาม: ฉันจะปรับเปลี่ยนพฤติกรรมการแบ่งหน้าตามความสูงของเนื้อหาได้อย่างไร

 A: คุณสามารถใช้`IsBroken` คุณสมบัติของตารางเพื่อเปิดใช้งานหรือปิดใช้งานการแบ่งแถวอัตโนมัติในแต่ละหน้า เมื่อตั้งค่าเป็น`true`มันช่วยให้แถวสามารถแบ่งข้ามหน้าตามความสูงของเนื้อหา