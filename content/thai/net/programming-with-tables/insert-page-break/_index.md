---
title: แทรกตัวแบ่งหน้าในไฟล์ PDF
linktitle: แทรกตัวแบ่งหน้าในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีแทรกตัวแบ่งหน้าในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 110
url: /th/net/programming-with-tables/insert-page-break/
---
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีแทรกตัวแบ่งหน้าในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ดใน C# ทีละขั้นตอน ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีเพิ่มตัวแบ่งหน้าหลังจากจำนวนบรรทัดที่กำหนดในตารางของเอกสาร PDF เริ่มกันเลย!

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ตรวจสอบให้แน่ใจว่าคุณได้กำหนดค่าสภาพแวดล้อมการพัฒนา C# ของคุณด้วย Aspose.PDF สำหรับ .NET เพิ่มการอ้างอิงไปยังไลบรารีและนำเข้าเนมสเปซที่จำเป็น

## ขั้นตอนที่ 2: การสร้างเอกสารและตาราง
เราสร้างอินสแตนซ์เอกสารใหม่และเพิ่มหน้าให้กับเอกสารนี้ ต่อไป เราจะสร้างอินสแตนซ์ Table เพื่อแสดงตารางของเราในเอกสาร PDF เรายังกำหนดลักษณะเส้นขอบของตารางด้วย

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## ขั้นตอนที่ 3: เพิ่มแถวลงในตาราง
เราใช้การวนซ้ำเพื่อเพิ่ม 200 แถวให้กับอาร์เรย์ สำหรับแต่ละแถว เราจะสร้างอินสแตนซ์ของแถวและเพิ่มสองเซลล์ที่มีเนื้อหาข้อความ

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
เราเพิ่มตารางลงในคอลเลกชันย่อหน้าของหน้าเอกสาร

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## ขั้นตอนที่ 5: บันทึกเอกสาร
เราบันทึกเอกสาร PDF โดยแทรกตัวแบ่งหน้า

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกตัวแบ่งหน้าโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างอินสแตนซ์เอกสาร
Document doc = new Document();
// เพิ่มหน้าไปยังคอลเลกชันหน้าของไฟล์ PDF
doc.Pages.Add();
// สร้างอินสแตนซ์ของตาราง
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// กำหนดรูปแบบเส้นขอบให้กับตาราง
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// ตั้งค่ารูปแบบเส้นขอบเริ่มต้นสำหรับตารางที่มีสีเส้นขอบเป็นสีแดง
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// ระบุความกว้างของคอลัมน์ตาราง
tab.ColumnWidths = "100 100";
// สร้างลูปเพื่อเพิ่ม 200 แถวสำหรับตาราง
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// เมื่อเพิ่ม 10 แถวแล้ว ให้แสดงแถวใหม่ในหน้าใหม่
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
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแทรกตัวแบ่งหน้าในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้คำแนะนำทีละขั้นตอนนี้เพื่อเพิ่มตัวแบ่งหน้าหลังจำนวนบรรทัดในตารางในเอกสาร PDF โดยใช้ C#

### คำถามที่พบบ่อยสำหรับการแทรกตัวแบ่งหน้าในไฟล์ PDF

#### ถาม: ฉันจะเปลี่ยนขนาดหน้าสำหรับหน้าใหม่ที่สร้างขึ้นหลังจากตัวแบ่งหน้าได้อย่างไร

 ตอบ: หากต้องการเปลี่ยนขนาดหน้าสำหรับหน้าใหม่ที่สร้างขึ้นหลังจากตัวแบ่งหน้า คุณสามารถตั้งค่าได้`PageSize` ทรัพย์สินของ`Page` วัตถุ. ตัวอย่างเช่น คุณสามารถใช้รหัสต่อไปนี้เพื่อตั้งค่าขนาดหน้าเป็น A4:

```csharp
// ตั้งค่าขนาดหน้าเป็น A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### ถาม: ฉันสามารถควบคุมระยะขอบของหน้าใหม่หลังจากตัวแบ่งหน้าได้หรือไม่

 ตอบ: ได้ คุณสามารถควบคุมระยะขอบของหน้าสำหรับหน้าใหม่ได้หลังจากตัวแบ่งหน้า ใช้`Margin` ทรัพย์สินของ`Page` วัตถุเพื่อกำหนดระยะขอบหน้า ตัวอย่างเช่น เมื่อต้องการตั้งค่าระยะขอบทั้งหมดเป็น 10 จุด คุณสามารถใช้รหัสต่อไปนี้:

```csharp
// ตั้งค่าระยะขอบทั้งหมดเป็น 10 คะแนน
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### ถาม: เป็นไปได้ไหมที่จะเพิ่มส่วนหัวและส่วนท้ายในหน้าใหม่หลังจากตัวแบ่งหน้า

 ตอบ: ได้ คุณสามารถเพิ่มส่วนหัวและส่วนท้ายลงในหน้าใหม่ได้หลังจากตัวแบ่งหน้า ใช้`Page.Header` และ`Page.Footer` คุณสมบัติเพื่อเพิ่มเนื้อหาลงในส่วนหัวและส่วนท้ายของหน้า ตัวอย่างเช่น:

```csharp
// เพิ่มส่วนหัวในหน้าใหม่
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// เพิ่มส่วนท้ายในหน้าใหม่
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### ถาม: ฉันสามารถแทรกตัวแบ่งหน้าในตำแหน่งเฉพาะนอกเหนือจากหลังจำนวนแถวที่กำหนดได้หรือไม่

 ตอบ: ได้ คุณสามารถแทรกตัวแบ่งหน้าในตำแหน่งเฉพาะนอกเหนือจากหลังแถวจำนวนหนึ่งได้ คุณสามารถตั้งค่า`IsInNewPage` คุณสมบัติของแถวถึง`true` เพื่อบังคับให้ตารางเริ่มหน้าใหม่หลังจากแถวนั้น

#### ถาม: ฉันจะปรับลักษณะการทำงานของตัวแบ่งหน้าตามความสูงของเนื้อหาได้อย่างไร

ตอบ: คุณสามารถใช้`IsBroken` คุณสมบัติของตารางเพื่อเปิดหรือปิดการแบ่งแถวอัตโนมัติระหว่างหน้าต่างๆ เมื่อตั้งค่าเป็น`true`ช่วยให้สามารถแบ่งแถวข้ามหน้าต่างๆ ตามความสูงของเนื้อหา