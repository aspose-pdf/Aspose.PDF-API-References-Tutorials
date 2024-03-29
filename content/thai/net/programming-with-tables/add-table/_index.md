---
title: เพิ่มตารางในไฟล์ PDF
linktitle: เพิ่มตารางในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เพิ่มตารางในไฟล์ PDF ได้อย่างง่ายดายโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 40
url: /th/net/programming-with-tables/add-table/
---
Aspose.PDF สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงเอกสาร PDF โดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มตารางในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายแต่ละขั้นตอนของข้อมูลโค้ดที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและใช้งานฟังก์ชันต่างๆ ในโครงการของคุณเอง

## การแนะนำ

เอกสาร PDF ถูกนำมาใช้กันอย่างแพร่หลายในการแบ่งปันและรักษาข้อมูลในรูปแบบพกพา การเพิ่มตารางลงในเอกสาร PDF สามารถปรับปรุงลักษณะที่ปรากฏของภาพและทำให้การนำเสนอข้อมูลมีระเบียบและมีโครงสร้างมากขึ้น Aspose.PDF สำหรับ .NET มอบวิธีที่สะดวกในการเพิ่มตารางลงในเอกสาร PDF ที่มีอยู่หรือสร้างตารางใหม่ตั้งแต่ต้น

## Aspose.PDF สำหรับ .NET คืออะไร

Aspose.PDF สำหรับ .NET เป็นไลบรารีที่ทรงพลังและเต็มไปด้วยฟีเจอร์ที่ช่วยให้นักพัฒนา .NET สามารถสร้าง จัดการ และแปลงเอกสาร PDF โดยทางโปรแกรม มันมีฟังก์ชันการทำงานที่หลากหลาย รวมถึงการสร้างไฟล์ PDF ตั้งแต่เริ่มต้น การแก้ไขเอกสาร PDF ที่มีอยู่ การรวมหรือแยกไฟล์ PDF การเพิ่มข้อความ รูปภาพ และตาราง การดึงข้อมูลจาก PDF และอื่นๆ อีกมากมาย ด้วย Aspose.PDF สำหรับ .NET นักพัฒนาสามารถทำงานที่เกี่ยวข้องกับ PDF ที่ซับซ้อนได้โดยอัตโนมัติ และส่งมอบโซลูชัน PDF คุณภาพสูง

## การเพิ่มตารางลงในเอกสาร PDF

หากต้องการเพิ่มตารางลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ให้ทำตามคำแนะนำทีละขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร PDF ต้นฉบับ

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

ข้อมูลโค้ดด้านบนจะโหลดเอกสาร PDF ต้นฉบับที่คุณต้องการเพิ่มตารางเข้าไป ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางที่ถูกต้องไปยังไฟล์ PDF ของคุณ

## ขั้นตอนที่ 2: การเริ่มต้นอินสแตนซ์ใหม่ของตาราง

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

ในขั้นตอนนี้ เราสร้างอินสแตนซ์ใหม่ของคลาส Table ซึ่งแสดงถึงตารางในเอกสาร PDF

## ขั้นตอนที่ 3: การตั้งค่าสีเส้นขอบตาราง

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

ที่นี่ เราตั้งค่าสีเส้นขอบสำหรับตารางโดยใช้คลาส BorderInfo คุณสามารถปรับแต่งรูปแบบเส้นขอบ ความกว้าง และสีได้ตามความต้องการของคุณ

## ขั้นตอนที่ 4: การตั้งค่าเส้นขอบสำหรับเซลล์ตาราง

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

นอกจากนี้เรายังตั้งค่าเส้นขอบสำหรับเซลล์ตารางโดยใช้คุณสมบัติ DefaultCellBorder ของวัตถุตาราง เพื่อให้แน่ใจว่าแต่ละเซลล์ในตารางมีสไตล์เส้นขอบ ความกว้าง และสีที่ระบุ

## ขั้นตอนที่ 5: การเพิ่มแถวและเซลล์ลงในตาราง

```csharp
for (int row_count = 1; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. Cells. Add("Column("+row_count+",1)");
   

  row. Cells. Add("Column("+row_count+",2)");
     row. Cells. Add("Column("+row_count+",3)");
}
```

ในขั้นตอนนี้ เราสร้างลูปเพื่อเพิ่ม 10 แถวลงในตาราง ภายในแต่ละแถว เราจะเพิ่มเซลล์สามเซลล์พร้อมข้อมูลตัวอย่าง คุณสามารถแก้ไขโค้ดเพื่อเพิ่มแถวและเซลล์ได้ตามความต้องการเฉพาะของคุณ

## ขั้นตอนที่ 6: การเพิ่มวัตถุตารางลงในเอกสาร

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// บันทึกเอกสารที่อัปเดตซึ่งมีวัตถุตาราง
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

สุดท้ายนี้ เราเพิ่มวัตถุตารางลงในหน้าแรกของเอกสาร PDF โดยใช้คอลเลกชันย่อหน้าของหน้าที่เกี่ยวข้อง

### ตัวอย่างซอร์สโค้ดสำหรับเพิ่มตารางโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

//โหลดเอกสาร PDF ต้นฉบับ
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
// เริ่มต้นอินสแตนซ์ใหม่ของตาราง
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// ตั้งค่าสีเส้นขอบตารางเป็น LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// กำหนดเส้นขอบให้กับเซลล์ตาราง
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// สร้างวงวนเพื่อเพิ่ม 10 แถว
for (int row_count = 1; row_count < 10; row_count++)
{
	// เพิ่มแถวลงในตาราง
	Aspose.Pdf.Row row = table.Rows.Add();
	// เพิ่มเซลล์ตาราง
	row.Cells.Add("Column (" + row_count + ", 1)");
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
// เพิ่มวัตถุตารางลงในหน้าแรกของเอกสารอินพุต
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// บันทึกเอกสารที่อัปเดตซึ่งมีวัตถุตาราง
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายกระบวนการทีละขั้นตอนในการเพิ่มตารางลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราครอบคลุมถึงการโหลดเอกสาร PDF ต้นฉบับ การเริ่มต้นอินสแตนซ์ใหม่ของคลาส Table การตั้งค่าสีเส้นขอบตารางและเส้นขอบเซลล์ การเพิ่มแถวและเซลล์ลงในตาราง และเพิ่มวัตถุตารางลงในเอกสาร ด้วยการทำตามคำแนะนำนี้ คุณสามารถรวมตารางลงในเอกสาร PDF ของคุณโดยทางโปรแกรมได้อย่างง่ายดาย และปรับแต่งตามความต้องการเฉพาะของคุณ

### คำถามที่พบบ่อยสำหรับการเพิ่มตารางในไฟล์ PDF

#### ถาม: ฉันสามารถเพิ่มคอลัมน์ลงในตารางได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มคอลัมน์ลงในตารางได้โดยเพิ่มจำนวนเซลล์ที่เพิ่มลงในแต่ละแถว ในตัวอย่างที่ให้มา แต่ละแถวมีเซลล์สามเซลล์ที่แสดงถึงสามคอลัมน์ คุณสามารถเพิ่มเซลล์ลงในแต่ละแถวเพื่อเพิ่มคอลัมน์เพิ่มเติมได้

#### ถาม: ฉันจะเปลี่ยนรูปลักษณ์ของตาราง เช่น ขนาดตัวอักษรและสไตล์ได้อย่างไร

 ตอบ: คุณสามารถปรับแต่งลักษณะที่ปรากฏของตาราง รวมถึงขนาดตัวอักษรและสไตล์ได้ โดยการตั้งค่าคุณสมบัติบน`Aspose.Pdf.Table` และ`Aspose.Pdf.TextFragment` วัตถุ ตัวอย่างเช่น คุณสามารถตั้งค่า`DefaultCellTextState` คุณสมบัติเพื่อเปลี่ยนคุณสมบัติแบบอักษรของข้อความในเซลล์ตาราง

#### ถาม: เป็นไปได้ไหมที่จะรวมเซลล์ในตาราง?

 ตอบ: ได้ คุณสามารถผสานเซลล์ในตารางได้โดยใช้`MergeCells` วิธีการของ`Aspose.Pdf.Row` ระดับ. ซึ่งจะทำให้คุณสามารถสร้างเซลล์ที่ขยายหลายแถวและคอลัมน์ได้

#### ถาม: ฉันสามารถเพิ่มรูปภาพหรือเนื้อหาอื่นลงในเซลล์ตารางได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มเนื้อหาประเภทต่างๆ ลงในเซลล์ตารางได้ รวมถึงรูปภาพ ข้อความ ไฮเปอร์ลิงก์ และอื่นๆ คุณสามารถใช้คลาสที่เหมาะสมจาก Aspose.PDF สำหรับ .NET เพื่อเพิ่มเนื้อหาประเภทต่างๆ ลงในเซลล์

#### ถาม: Aspose.PDF สำหรับ .NET เข้ากันได้กับ .NET 5.0 หรือเวอร์ชันที่ใหม่กว่าหรือไม่

ตอบ: ได้ Aspose.PDF สำหรับ .NET เข้ากันได้กับ .NET 5.0 และเวอร์ชันที่ใหม่กว่า รองรับแพลตฟอร์ม .NET ที่หลากหลาย รวมถึง .NET Framework, .NET Core และ .NET 5.0+