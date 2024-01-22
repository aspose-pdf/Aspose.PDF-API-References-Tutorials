---
title: เพิ่มจาวาสคริปต์ลงในไฟล์ PDF
linktitle: เพิ่มไฟล์ PDF จาวาสคริปต์
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีเพิ่ม JavaScript ลงในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมบทช่วยสอนโค้ดสำหรับการเขียนสคริปต์ระดับเอกสารและหน้า
type: docs
weight: 10
url: /th/net/programming-with-document/addjavascripttopage/
---
หากต้องการเพิ่ม JavaScript ลงในไฟล์ PDF เราจะใช้ Aspose.PDF สำหรับ .NET ไลบรารีนี้มอบวิธีที่ง่ายและมีประสิทธิภาพในการทำงานกับไฟล์ PDF ในแอปพลิเคชัน .NET ขั้นตอนต่อไปนี้จะแนะนำคุณตลอดกระบวนการเพิ่ม JavaScript ลงในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 1: โหลดไฟล์ PDF

 ขั้นตอนแรกคือโหลดไฟล์ PDF ที่คุณต้องการเพิ่ม JavaScript ลงไป คุณสามารถทำได้โดยใช้`Document` คลาสที่จัดทำโดย Aspose.PDF สำหรับ .NET ที่`Document` class จัดเตรียมวิธีการสำหรับการโหลด บันทึก และจัดการไฟล์ PDF

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// โหลดไฟล์ PDF ที่มีอยู่
Document doc = new Document(dataDir + "input.pdf");
```

## ขั้นตอนที่ 2: เพิ่ม JavaScript ในระดับเอกสาร

ในการเพิ่ม JavaScript ในระดับเอกสาร เราจะใช้`JavascriptAction` คลาสที่จัดทำโดย Aspose.PDF สำหรับ .NET คลาสนี้ให้คุณระบุคำสั่ง JavaScript ที่คุณต้องการเพิ่มลงในไฟล์ PDF

```csharp
// การเพิ่ม JavaScript ในระดับเอกสาร
// สร้างอินสแตนซ์ JavascriptAction ด้วยคำสั่ง JavaScript ที่ต้องการ
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// กำหนดวัตถุ JavascriptAction ให้กับการกระทำที่ต้องการของเอกสาร
doc.OpenAction = javaScript;
```

ในบทช่วยสอนนี้ เรากำลังเพิ่มคำสั่ง JavaScript ที่จะพิมพ์ไฟล์ PDF พร้อมตัวเลือกที่ระบุเมื่อเปิดเอกสาร

## ขั้นตอนที่ 3: เพิ่ม JavaScript ในระดับหน้า

 ในการเพิ่ม JavaScript ในระดับเพจ เราจะใช้`JavascriptAction` ชั้นเรียนและ`Actions` คุณสมบัติที่จัดทำโดย Aspose.PDF สำหรับ .NET คุณสมบัตินี้ช่วยให้คุณสามารถระบุคำสั่ง JavaScript ที่จะถูกดำเนินการเมื่อเปิดหรือปิดเพจ

```csharp
// การเพิ่ม JavaScript ในระดับเพจ
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

ในบทช่วยสอนนี้ เรากำลังเพิ่มคำสั่ง JavaScript ที่จะแสดงข้อความแจ้งเตือนเมื่อมีการเปิดหรือปิดเพจ

## ขั้นตอนที่ 4: บันทึกไฟล์ PDF

หลังจากที่คุณเพิ่ม JavaScript ลงในไฟล์ PDF แล้ว คุณจะต้องบันทึกไฟล์ที่แก้ไข คุณสามารถทำได้โดยใช้`Save` วิธีการที่กำหนดโดย`Document` ระดับ.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// บันทึกเอกสาร PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

รหัสนี้จะบันทึกไฟล์ PDF ที่แก้ไขไปยังไดเร็กทอรีที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับการเพิ่มสคริปต์ Java ไปยังเพจโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
            
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// โหลดไฟล์ PDF ที่มีอยู่
Document doc = new Document(dataDir + "input.pdf");

// การเพิ่ม JavaScript ในระดับเอกสาร
// สร้างอินสแตนซ์ JavascriptAction ด้วยคำสั่ง JavaScript ที่ต้องการ
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// กำหนดวัตถุ JavascriptAction ให้กับการกระทำที่ต้องการของเอกสาร
doc.OpenAction = javaScript;

// การเพิ่ม JavaScript ในระดับเพจ
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// บันทึกเอกสาร PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## บทสรุป

ในบทความนี้ เราได้อธิบายวิธีการเพิ่ม JavaScript ให้กับไฟล์ PDF ทั้งในระดับเอกสารและระดับเพจโดยใช้ Aspose.PDF สำหรับ .NET เราได้ให้คำแนะนำทีละขั้นตอนและรวมซอร์สโค้ดแบบเต็มสำหรับแต่ละตัวอย่าง ด้วยความรู้นี้ คุณสามารถเพิ่ม JavaScript ลงในไฟล์ PDF ของคุณและปรับแต่งลักษณะการทำงานได้ตามความต้องการของคุณ


### คำถามที่พบบ่อยสำหรับการเพิ่มสคริปต์ Java ลงในไฟล์ PDF

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ PDF ในแอปพลิเคชัน .NET ได้ มันมีคุณสมบัติที่หลากหลายสำหรับการสร้าง การแก้ไข และการจัดการเอกสาร PDF

#### ถาม: ฉันสามารถเพิ่ม JavaScript ลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ: ได้ Aspose.PDF สำหรับ .NET ช่วยให้คุณสามารถเพิ่ม JavaScript ลงในทั้งระดับเอกสารและระดับหน้าของไฟล์ PDF ได้ ทำให้คุณสามารถสร้างเอกสาร PDF แบบไดนามิกและโต้ตอบได้

#### ถาม: ฉันจะโหลดไฟล์ PDF ที่มีอยู่โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 ตอบ: คุณสามารถโหลดไฟล์ PDF ที่มีอยู่ได้โดยใช้ไฟล์`Document` คลาสและวิธีการของมัน ดังที่แสดงในคำแนะนำทีละขั้นตอน

#### ถาม: ฉันสามารถเพิ่มการทำงานของ JavaScript ประเภทใดลงในเอกสาร PDF ได้

ตอบ: ด้วย Aspose.PDF สำหรับ .NET คุณสามารถเพิ่มการทำงานของ JavaScript ได้หลากหลาย เช่น การพิมพ์ ข้อความแจ้งเตือน การจัดการฟิลด์แบบฟอร์ม และอื่นๆ อีกมากมาย

#### ถาม: Aspose.PDF สำหรับ .NET เหมาะสำหรับโครงการเชิงพาณิชย์หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET เป็นไลบรารีที่เชื่อถือได้และมีประสิทธิภาพ ซึ่งมักใช้ในโครงการเชิงพาณิชย์สำหรับงานจัดการและสร้าง PDF

