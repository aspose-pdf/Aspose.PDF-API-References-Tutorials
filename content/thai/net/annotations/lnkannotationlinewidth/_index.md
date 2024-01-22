---
title: lnk ความกว้างของบรรทัดคำอธิบายประกอบ
linktitle: lnk ความกว้างของบรรทัดคำอธิบายประกอบ
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: บทความนี้ให้คำแนะนำทีละขั้นตอนสำหรับการตั้งค่าความกว้างบรรทัดของคำอธิบายประกอบ lnk โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 110
url: /th/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF เป็นเครื่องมือที่ทรงพลังและใช้กันอย่างแพร่หลายสำหรับการทำงานกับไฟล์ PDF ในแอปพลิเคชัน .NET โดยมีคุณสมบัติที่หลากหลายสำหรับการสร้าง แก้ไข และจัดการไฟล์ PDF รวมถึงความสามารถในการเพิ่มคำอธิบายประกอบในหน้าต่างๆ ในบทช่วยสอนนี้ เราจะอธิบายวิธีตั้งค่าความกว้างบรรทัดของคำอธิบายประกอบลิงก์โดยใช้ Aspose.PDF สำหรับ .NET

เมื่อคุณมีข้อกำหนดเบื้องต้นเหล่านี้แล้ว ให้สร้างโครงการแอปพลิเคชันคอนโซลใหม่ใน Visual Studio จากนั้น เพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET โดยการคลิกขวาที่โปรเจ็กต์ใน Solution Explorer เลือก "จัดการแพ็คเกจ NuGet" และค้นหา "Aspose.PDF" ใน NuGet Package Manager

หากต้องการเพิ่มคำอธิบายประกอบ lnk ให้กับเอกสาร PDF ให้ทำตามขั้นตอนเหล่านี้:

##  ขั้นตอนที่ 1: สร้างใหม่`Document` object.
```csharp
Document doc = new Document();
```
## ขั้นตอนที่ 2: เพิ่มหน้าใหม่ลงในเอกสาร
```csharp
doc.Pages.Add();
```
##  ขั้นตอนที่ 3: สร้างรายการของ`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  ขั้นตอนที่ 4: สร้างใหม่`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  ขั้นตอนที่ 5: สร้างใหม่`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## ขั้นตอนที่ 6: เพิ่มท่าทางในรายการท่าทางหมึก
```csharp
inkList.Add(gesture);
```
##  ขั้นตอนที่ 7: สร้างใหม่`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## ขั้นตอนที่ 8: ตั้งชื่อเรื่องและชื่อเรื่องของคำอธิบายประกอบ
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## ขั้นตอนที่ 9: ตั้งค่าสีของคำอธิบายประกอบ
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  ขั้นตอนที่ 10: สร้างใหม่`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## ขั้นตอนที่ 11: เพิ่มคำอธิบายประกอบลงในหน้า
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## ขั้นตอนที่ 12: บันทึกเอกสารเป็นไฟล์
```csharp
// บันทึกไฟล์เอาต์พุต
doc.Save(dataDir);


```
### ตัวอย่างนี้แสดงความกว้างของบรรทัดคำอธิบายประกอบ lnk ด้วย Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// บันทึกไฟล์เอาต์พุต
doc.Save(dataDir);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งค่าความกว้างบรรทัดของคำอธิบายประกอบลิงก์ในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET Aspose.PDF สำหรับ .NET มีเครื่องมือและคุณสมบัติที่หลากหลายสำหรับการทำงานกับเอกสาร PDF รวมถึงความสามารถในการสร้างและปรับแต่งคำอธิบายประกอบลิงก์ ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ด C# ที่ให้มา นักพัฒนาสามารถเพิ่มลิงก์เชิงโต้ตอบไปยังเอกสาร PDF ของตนได้อย่างง่ายดาย ปรับปรุงประสบการณ์ผู้ใช้และการโต้ตอบของแอปพลิเคชันของตน Aspose.PDF สำหรับ .NET เป็นไลบรารีอเนกประสงค์ที่ช่วยให้นักพัฒนา .NET สามารถทำงานกับไฟล์ PDF ได้อย่างมีประสิทธิภาพและประสิทธิผล

### คำถามที่พบบ่อย

#### ถาม: คำอธิบายประกอบลิงก์ในเอกสาร PDF คืออะไร

ตอบ: คำอธิบายประกอบลิงก์ในเอกสาร PDF เป็นองค์ประกอบแบบโต้ตอบที่ช่วยให้คุณสามารถสร้างไฮเปอร์ลิงก์หรือการดำเนินการที่นำผู้ใช้ไปยังตำแหน่งอื่นภายในเอกสารเดียวกัน เว็บไซต์ภายนอก หรือเอกสาร PDF อื่น

#### ถาม: ฉันจะตั้งค่าความกว้างบรรทัดของคำอธิบายประกอบลิงก์โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการตั้งค่าความกว้างของบรรทัดของคำอธิบายประกอบลิงก์โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถสร้าง`InkAnnotation` วัตถุและระบุคุณสมบัติความกว้างของเส้น

#### ถาม: คุณสมบัติใดบ้างที่สามารถปรับแต่งสำหรับคำอธิบายประกอบลิงก์ใน Aspose.PDF สำหรับ .NET ได้

ตอบ: คุณสามารถปรับแต่งคุณสมบัติต่างๆ ของคำอธิบายประกอบลิงก์ใน Aspose.PDF สำหรับ .NET ได้ เช่น ตำแหน่ง ขนาด สี คุณสมบัติเส้นขอบ (ความกว้าง สไตล์ รูปแบบเส้นประ และเอฟเฟกต์) หัวเรื่อง ชื่อ และการมองเห็น

#### ถาม: ฉันสามารถสร้างคำอธิบายประกอบลิงก์ที่มีท่าทางหมึกหลายแบบได้หรือไม่

 ตอบ: ได้ คุณสามารถสร้างคำอธิบายประกอบลิงก์ที่มีรูปแบบลายเส้นหมึกหลายแบบได้โดยการเพิ่มหลายรูปแบบ`Point` อาร์เรย์ไปยัง`InkAnnotation` วัตถุ.

#### ถาม: ฉันจะเพิ่มคำอธิบายประกอบลิงก์ไปยังหน้าเฉพาะของเอกสาร PDF ได้อย่างไร

 ตอบ: หากต้องการเพิ่มคำอธิบายประกอบลิงก์ไปยังหน้าเฉพาะของเอกสาร PDF คุณต้องระบุหมายเลขหน้าเมื่อสร้าง`InkAnnotation` วัตถุ. ตัวอย่างเช่น,`new InkAnnotation(doc.Pages[1], ...)` เพิ่มคำอธิบายประกอบลิงก์ในหน้าแรก