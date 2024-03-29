---
title: ดึงฟิลด์แบบฟอร์มตามลำดับแท็บ
linktitle: ดึงฟิลด์แบบฟอร์มตามลำดับแท็บ
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีดึงข้อมูลฟิลด์แบบฟอร์มตามลำดับแท็บโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 240
url: /th/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
เมื่อทำงานกับเอกสาร PDF ใน C# โดยใช้ Aspose.PDF สำหรับ .NET คุณอาจพบสถานการณ์ที่คุณจำเป็นต้องดึงฟิลด์แบบฟอร์มตามลำดับแท็บเฉพาะ สิ่งนี้มีประโยชน์เมื่อคุณต้องการดำเนินการกับฟิลด์แบบฟอร์มตามลำดับแท็บ ในบทช่วยสอนนี้ เราจะแนะนำคุณทีละขั้นตอนเกี่ยวกับวิธีการดึงฟิลด์แบบฟอร์มตามลำดับแท็บโดยใช้ Aspose.PDF สำหรับ .NET

## ความต้องการ

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- ติดตั้ง Visual Studio บนระบบของคุณแล้ว
- ติดตั้ง Aspose.PDF สำหรับไลบรารี .NET แล้ว

ตอนนี้ เรามาเจาะลึกขั้นตอนในการดึงข้อมูลฟิลด์แบบฟอร์มตามลำดับแท็บ

## ขั้นตอนที่ 1: การตั้งค่าไดเร็กทอรีเอกสาร

 ขั้นแรก คุณต้องตั้งค่าไดเร็กทอรีเอกสารซึ่งมีเอกสาร PDF ของคุณอยู่ คุณสามารถทำได้โดยระบุเส้นทางไปยังไดเร็กทอรีในไฟล์`dataDir` ตัวแปร.

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร PDF

 ในขั้นตอนนี้ เราจะโหลดเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ที่`Document` คลาสให้ความสามารถในการโหลดและจัดการเอกสาร PDF

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 ที่นี่,`"Test2.pdf"`คือชื่อของเอกสาร PDF ที่คุณต้องการโหลด ตรวจสอบให้แน่ใจว่าเอกสารมีอยู่ในไดเร็กทอรีเอกสารที่ระบุ

## ขั้นตอนที่ 3: การดึงฟิลด์แบบฟอร์มตามลำดับแท็บ

 หากต้องการดึงข้อมูลแบบฟอร์มตามลำดับแท็บ เราจำเป็นต้องเข้าถึง`FieldsInTabOrder` ทรัพย์สินของ`Page` ระดับ. คุณสมบัตินี้ส่งคืนรายการฟิลด์แบบฟอร์มที่เรียงลำดับตามลำดับแท็บ

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

ในข้อมูลโค้ดด้านบน เราจะดึงข้อมูลฟิลด์แบบฟอร์มจากหน้าที่ 2 (`doc.Pages[1]` ) และวนซ้ำแต่ละฟิลด์เพื่อเชื่อมชื่อบางส่วนเข้าด้วยกัน`s` ตัวแปร. คุณสามารถแก้ไขข้อมูลโค้ดนี้ได้ตามความต้องการเฉพาะของคุณ

## ขั้นตอนที่ 4: การปรับเปลี่ยนลำดับแท็บ

 หากคุณต้องการแก้ไขลำดับแท็บของฟิลด์แบบฟอร์ม คุณสามารถทำได้โดยเข้าไปที่`TabOrder` คุณสมบัติของแต่ละฟิลด์และการกำหนดค่าลำดับแท็บใหม่ นี่คือตัวอย่าง:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

ในข้อมูลโค้ดข้างต้น เรากำหนดค่าลำดับแท็บใหม่ให้กับช่องแบบฟอร์มสามช่อง (`doc.Form[3]`, `doc.Form[1]` , และ`doc.Form[2]`). ปรับดัชนีฟิลด์และค่าลำดับแท็บตามความต้องการเฉพาะของคุณ

## ขั้นตอนที่ 5: บันทึกเอกสารที่แก้ไข

 หลังจากแก้ไขลำดับแท็บของฟิลด์แบบฟอร์มแล้ว คุณจะต้องบันทึกเอกสารที่แก้ไข คุณสามารถทำได้โดยใช้`Save` วิธีการของ`Document` ระดับ.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 ที่นี่,`"39522_out.pdf"` คือชื่อของไฟล์เอาต์พุตที่จะบันทึกเอกสารที่แก้ไข ระบุชื่อและตำแหน่งที่ต้องการสำหรับไฟล์เอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับการดึงฟิลด์แบบฟอร์มในลำดับแท็บโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีดึงฟิลด์แบบฟอร์มตามลำดับแท็บโดยใช้ Aspose.PDF สำหรับ .NET เราได้กล่าวถึงขั้นตอนต่างๆ ที่เกี่ยวข้องกับการโหลดเอกสาร PDF การเรียกฟิลด์แบบฟอร์มตามลำดับแท็บ การแก้ไขลำดับแท็บ และการบันทึกเอกสารที่แก้ไข ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถทำงานกับฟิลด์แบบฟอร์มและปรับแต่งลำดับแท็บตามความต้องการของคุณได้อย่างมีประสิทธิภาพ


### คำถามที่พบบ่อย

#### ถาม: ฉันจะใช้ฟิลด์ฟอร์มที่ดึงมาในโค้ด C# ของฉันเพื่อการประมวลผลเพิ่มเติมได้อย่างไร

 ตอบ: คุณสามารถใช้ฟิลด์ฟอร์มที่ดึงมาในโค้ด C# ของคุณได้โดยการเข้าถึงคุณสมบัติต่างๆ เช่น`Value`, `Name`, `Rect`ฯลฯ คุณสมบัติเหล่านี้ช่วยให้คุณสามารถอ่านและแก้ไขข้อมูลฟิลด์แบบฟอร์มได้ตามต้องการ

#### ถาม: ฉันสามารถดึงฟิลด์แบบฟอร์มจากทุกหน้าของเอกสาร PDF ตามลำดับแท็บได้หรือไม่

 ตอบ: ได้ คุณสามารถดึงข้อมูลฟิลด์แบบฟอร์มจากทุกหน้าของเอกสาร PDF ได้โดยการวนซ้ำแต่ละหน้าและเข้าถึง`FieldsInTabOrder` คุณสมบัติตามที่แสดงในบทช่วยสอน ซึ่งจะทำให้ช่องแบบฟอร์มจัดเรียงตามลำดับแท็บในทุกหน้า

#### ถาม: เป็นไปได้หรือไม่ที่จะดึงเฉพาะฟิลด์แบบฟอร์มบางประเภท เช่น ฟิลด์ข้อความหรือช่องทำเครื่องหมาย ตามลำดับแท็บ

ตอบ: ได้ คุณสามารถกรองฟิลด์แบบฟอร์มตามประเภทได้ เช่น ช่องข้อความหรือช่องทำเครื่องหมาย หลังจากดึงข้อมูลตามลำดับแท็บแล้ว คุณสามารถใช้คำสั่งแบบมีเงื่อนไขเพื่อตรวจสอบประเภทของช่องแบบฟอร์มแต่ละช่องและดำเนินการตามนั้น

#### ถาม: ฉันสามารถดึงข้อมูลฟิลด์แบบฟอร์มตามชื่อแทนลำดับแท็บได้หรือไม่

 ตอบ: ได้ คุณสามารถดึงข้อมูลฟิลด์ฟอร์มตามชื่อได้โดยใช้`doc.Form` รวบรวมและระบุชื่อฟิลด์เป็นดัชนี ตัวอย่างเช่น,`doc.Form["fieldName"]`จะดึงข้อมูลฟิลด์แบบฟอร์มที่มีชื่อที่ระบุ

#### ถาม: Aspose.PDF สำหรับ .NET รองรับการทำงานกับเอกสาร PDF ที่เข้ารหัสหรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET ให้การสนับสนุนการทำงานกับเอกสาร PDF ที่เข้ารหัส คุณสามารถโหลดและจัดการไฟล์ PDF ที่เข้ารหัสโดยใช้พารามิเตอร์รหัสผ่านที่เหมาะสม