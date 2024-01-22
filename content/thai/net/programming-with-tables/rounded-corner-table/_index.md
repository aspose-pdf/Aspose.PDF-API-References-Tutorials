---
title: ตารางมุมโค้งมนในเอกสาร PDF
linktitle: ตารางมุมโค้งมนในเอกสาร PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีสร้างตารางมุมมนในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 190
url: /th/net/programming-with-tables/rounded-corner-table/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณทีละขั้นตอนในการสร้างตารางมุมมนในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและแสดงวิธีใช้งาน

## ขั้นตอนที่ 1: การสร้างตาราง
ขั้นแรกเราจะสร้างตารางโดยใช้โค้ดต่อไปนี้:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## ขั้นตอนที่ 2: การตั้งค่าสไตล์มุมโค้งมน
ต่อไป เราจะกำหนดค่ารูปแบบมุมโค้งมนสำหรับตาราง:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## ขั้นตอนที่ 3: การตั้งค่าเส้นขอบตาราง
เพื่อให้ตารางมีเส้นขอบมุมโค้งมน เราจำเป็นต้องสร้างวัตถุ BorderInfo และกำหนดค่าด้วยพารามิเตอร์ที่เหมาะสม:

```csharp
// สร้างวัตถุ GraphInfo เพื่อกำหนดสีเส้นขอบ
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// สร้างวัตถุ BorderInfo ที่ว่างเปล่า
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// ตั้งค่ารัศมีของเส้นขอบโค้งมนเป็น 15
bInfo.RoundedBorderRadius = 15;

// ใช้ข้อมูลเส้นขอบกับตาราง
tab1.Border = bInfo;
```

### ตัวอย่างซอร์สโค้ดสำหรับ Rounded Corner Table โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// สร้างวัตถุ BorderInfo เปล่า
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// กำหนดเส้นขอบเป็นเส้นขอบโค้งมนโดยรัศมีของวงกลมคือ 15
bInfo.RoundedBorderRadius = 15;
// ตั้งค่าสไตล์มุมโต๊ะเป็นทรงกลม
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// ตั้งค่าข้อมูลเส้นขอบตาราง
tab1.Border = bInfo;
```

## บทสรุป
ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีสร้างตารางมุมโค้งมนในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET แล้ว คำแนะนำทีละขั้นตอนนี้แสดงวิธีการตั้งค่ารูปแบบมุมโค้งมนและเส้นขอบตาราง ตอนนี้คุณสามารถใช้ความรู้นี้กับโครงการของคุณเองได้แล้ว

### คำถามที่พบบ่อยเกี่ยวกับโต๊ะเข้ามุมในเอกสาร PDF

#### ถาม: ฉันสามารถปรับแต่งรัศมีของมุมโค้งมนของโต๊ะได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งรัศมีของมุมโค้งมนของตารางได้โดยการแก้ไขค่าของ`bInfo.RoundedBorderRadius` คุณสมบัติในซอร์สโค้ด C # ที่ให้มา เพียงตั้งค่ารัศมีที่ต้องการ (เป็นจุด) เพื่อให้ได้ลักษณะมุมโค้งมนที่ต้องการ

#### ถาม: ฉันสามารถใช้มุมโค้งมนกับแต่ละเซลล์ภายในตารางได้หรือไม่

ตอบ: ไม่ รูปแบบมุมโค้งมนจะถูกนำไปใช้กับทั้งโต๊ะโดยรวม ปัจจุบัน Aspose.PDF สำหรับ .NET ไม่มีการสนับสนุนในตัวสำหรับการนำมุมโค้งมนไปใช้กับเซลล์แต่ละเซลล์ภายในตาราง

#### ถาม: ฉันสามารถเปลี่ยนสีของเส้นขอบมุมโค้งมนได้หรือไม่

 ตอบ: ได้ คุณสามารถเปลี่ยนสีของเส้นขอบมุมโค้งมนได้โดยการแก้ไขค่าของ`graph.Color` คุณสมบัติในซอร์สโค้ด C # เพียงระบุสีที่ต้องการ เช่น`Aspose.Pdf.Color.Red` หรือการแสดงสีที่ถูกต้องอื่น ๆ

#### ถาม: เป็นไปได้ไหมที่จะใช้รูปแบบมุมที่แตกต่างกัน (เช่น สี่เหลี่ยมจัตุรัสและโค้งมน) กับตารางต่างๆ ภายในเอกสาร PDF เดียวกัน

ตอบ: ได้ คุณสามารถใช้รูปแบบมุมที่แตกต่างกันกับตารางต่างๆ ภายในเอกสาร PDF เดียวกันได้ คุณสามารถสร้างตารางได้หลายตารางและกำหนดค่าสไตล์มุมของตารางแยกกันตามความต้องการของคุณ

#### ถาม: ฉันสามารถปรับความหนาของเส้นขอบมุมโค้งมนได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับความหนาของเส้นขอบมุมโค้งมนได้โดยการปรับเปลี่ยน`BorderInfo` คุณสมบัติของวัตถุในซอร์สโค้ด C# ตัวอย่างเช่น คุณสามารถตั้งค่า`bInfo.Width` คุณสมบัติในการปรับความหนาของเส้นขอบ