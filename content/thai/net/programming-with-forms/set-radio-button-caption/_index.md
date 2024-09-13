---
title: ตั้งค่าคำอธิบายปุ่มตัวเลือก
linktitle: ตั้งค่าคำอธิบายปุ่มตัวเลือก
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีตั้งค่าคำอธิบายปุ่มตัวเลือกใน PDF โดยใช้ Aspose.PDF สำหรับ .NET คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดขั้นตอนการโหลด แก้ไข และบันทึกแบบฟอร์ม PDF ของคุณ
type: docs
weight: 280
url: /th/net/programming-with-forms/set-radio-button-caption/
---
## การแนะนำ

หากคุณกำลังจะเริ่มต้นใช้งานการจัดการ PDF ด้วย Aspose.PDF สำหรับ .NET คุณก็จะได้รับประสบการณ์ที่ดี! วันนี้ เราจะมาเน้นที่ฟีเจอร์ที่มีประโยชน์: การกำหนดคำบรรยายปุ่มตัวเลือกในแบบฟอร์ม PDF ของคุณ ปุ่มตัวเลือกมีความจำเป็นสำหรับแบบฟอร์มของผู้ใช้ซึ่งคุณต้องเลือกจากชุดตัวเลือก ลองจินตนาการว่าปุ่มตัวเลือกเป็นคำถามแบบเลือกตอบซึ่งอนุญาตให้ตอบได้เพียงคำตอบเดียว บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการอัปเดตคำบรรยายปุ่มตัวเลือกในแบบฟอร์ม PDF เพื่อให้เอกสารของคุณเป็นแบบโต้ตอบและใช้งานง่าย 

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกโค้ด มีบางสิ่งที่คุณจะต้องแน่ใจว่าคุณมี:

1. Aspose.PDF สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.PDF แล้ว ไลบรารีนี้จะช่วยให้คุณจัดการไฟล์ PDF ด้วยโปรแกรมได้
2. สภาพแวดล้อมการพัฒนา: คุณควรมีการตั้งค่าสภาพแวดล้อมการพัฒนา .NET เช่น Visual Studio
3. แบบฟอร์ม PDF ตัวอย่าง: สำหรับบทช่วยสอนนี้ คุณจะต้องมีแบบฟอร์ม PDF ตัวอย่างพร้อมปุ่มตัวเลือก คุณสามารถใช้แบบฟอร์ม PDF ที่มีอยู่แล้วหรือสร้างแบบฟอร์มใหม่พร้อมปุ่มตัวเลือกก็ได้
4. ความรู้พื้นฐานเกี่ยวกับ C#: คู่มือนี้ถือว่าคุณมีความเข้าใจพื้นฐานเกี่ยวกับแนวคิดการเขียนโปรแกรม C# และ .NET

 หากคุณยังไม่ได้ติดตั้ง Aspose.PDF สำหรับ .NET หรือคุณต้องการใบอนุญาตชั่วคราว คุณสามารถทำได้[ดาวน์โหลดได้ที่นี่](https://releases.aspose.com/pdf/net/) หรือ[รับใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).

## แพ็คเกจนำเข้า

ในการเริ่มต้น คุณต้องนำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ C# ของคุณ ต่อไปนี้เป็นวิธีรวมไลบรารี Aspose.PDF:

```csharp
using System;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
using Aspose.Pdf.Text;
```

ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มแพ็คเกจเหล่านี้ลงในโปรเจ็กต์ของคุณผ่าน NuGet หรือวิธีที่คุณต้องการ

## ขั้นตอนที่ 1: โหลดแบบฟอร์ม PDF

 ขั้นแรก คุณต้องโหลดฟอร์ม PDF ที่มีปุ่มตัวเลือก`Aspose.Pdf.Facades.Form`คลาสนี้ใช้เพื่อจุดประสงค์นี้ คุณสามารถทำได้ดังนี้:

```csharp
// กำหนดเส้นทางไปยังไดเรกทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

// โหลดแบบฟอร์ม PDF ต้นฉบับ
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
```

ในชิ้นส่วนโค้ดนี้:
- `dataDir` ระบุเส้นทางที่ PDF ของคุณตั้งอยู่
- `Form` คลาสนี้ใช้ในการโต้ตอบกับฟิลด์ฟอร์มภายใน PDF
- `Document` คลาสนี้ให้การเข้าถึงหน้าเอกสาร PDF

## ขั้นตอนที่ 2: ทำซ้ำผ่านฟิลด์ปุ่มตัวเลือก

ต่อไป คุณจะต้องทำซ้ำผ่านฟิลด์ในแบบฟอร์มของคุณเพื่อระบุและจัดการฟิลด์ปุ่มตัวเลือก:

```csharp
foreach (var item in form1.FieldNames)
{
    Console.WriteLine(item.ToString());
    Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
```

ในลูปนี้:
- `FieldNames` ให้รายชื่อชื่อฟิลด์ทั้งหมดใน PDF
- `GetButtonOptionValues(item)` ดึงตัวเลือกที่มีให้สำหรับปุ่มตัวเลือกแต่ละปุ่ม

## ขั้นตอนที่ 3: ปรับเปลี่ยนตัวเลือกปุ่มตัวเลือก

 เมื่อคุณระบุฟิลด์ของปุ่มตัวเลือกแล้ว คุณสามารถแก้ไขตัวเลือกของฟิลด์เหล่านั้นได้ สำหรับสิ่งนี้ คุณต้องแปลงฟิลด์เป็น`RadioButtonField` และอัพเดตตัวเลือกของมัน:

```csharp
    if (item.Contains("radio1"))
    {
        Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
        Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
        fieldoption.OptionName = "Yes";
        fieldoption.PartialName = "Yesname";
```

ที่นี่:
- เราตรวจสอบว่าชื่อฟิลด์มี "radio1" หรือไม่เพื่อระบุฟิลด์ปุ่มตัวเลือกที่เราต้องการแก้ไข
- `RadioButtonField`จะถูกแปลงจากฟิลด์ฟอร์มเพื่อทำการปรับเปลี่ยนเฉพาะเจาะจง

## ขั้นตอนที่ 4: ตั้งค่าคำบรรยายสำหรับปุ่มตัวเลือก

 หากต้องการตั้งค่าหรืออัปเดตคำบรรยายสำหรับปุ่มตัวเลือก คุณจะต้องสร้าง`TextFragment` และใช้`TextBuilder` เพื่อวางไว้ในตำแหน่งที่ต้องการ:

```csharp
        var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
        updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
        updatedFragment.TextState.FontSize = 10;
        updatedFragment.TextState.LineSpacing = 6.32f;

        // สร้างวัตถุ TextParagraph
        TextParagraph par = new TextParagraph();
        // ตั้งค่าตำแหน่งย่อหน้า
        par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
        // ระบุโหมดการห่อคำ
        par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
        // เพิ่ม TextFragment ใหม่ลงในย่อหน้า
        par.AppendLine(updatedFragment);
        // เพิ่ม TextParagraph โดยใช้ TextBuilder
        TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
        textBuilder.AppendParagraph(par);
```

ในส่วนนี้:
- `TextFragment` ใช้เพื่อกำหนดข้อความและลักษณะที่ปรากฏ
- `TextParagraph` ช่วยวางตำแหน่งและจัดรูปแบบข้อความ
- `TextBuilder` เพิ่มข้อความลงในหน้าที่ระบุของ PDF

## ขั้นตอนที่ 5: บันทึก PDF ที่อัปเดต

สุดท้ายให้บันทึก PDF ที่อัปเดตลงในไฟล์ใหม่:

```csharp
        field0.DeleteOption("item1");
    }
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

สิ่งนี้จะทำให้มั่นใจได้ว่า:
- การเปลี่ยนแปลงจะมีผลกับ PDF
- ตัวเลือกปุ่มตัวเลือกเดิมจะถูกลบออกตามที่ระบุไว้

## บทสรุป

การแก้ไขคำอธิบายปุ่มตัวเลือกในแบบฟอร์ม PDF โดยใช้ Aspose.PDF สำหรับ .NET สามารถปรับปรุงการโต้ตอบและการใช้งานเอกสารของคุณได้อย่างมาก ด้วยขั้นตอนที่อธิบายไว้ในบทช่วยสอนนี้ คุณสามารถโหลด PDF อัปเดตตัวเลือกปุ่มตัวเลือก และบันทึกการเปลี่ยนแปลงของคุณได้อย่างง่ายดาย วิธีนี้มีประโยชน์สำหรับการจัดการแบบฟอร์มและช่วยให้มั่นใจว่า PDF ของคุณตรงตามความต้องการที่แท้จริงของผู้ใช้ เจาะลึก Aspose.PDF และสำรวจความสามารถสำหรับการจัดการ PDF อื่นๆ!

## คำถามที่พบบ่อย

### ฉันสามารถอัปเดตฟิลด์ปุ่มตัวเลือกหลายปุ่มพร้อมกันได้ไหม
ใช่ คุณสามารถทำซ้ำผ่านฟิลด์ปุ่มตัวเลือกทั้งหมดและใช้การเปลี่ยนแปลงตามต้องการได้

### ฉันต้องมีใบอนุญาตเพื่อใช้ Aspose.PDF หรือไม่?
 คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรี แต่จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานระยะยาว[รับใบอนุญาตที่นี่](https://purchase.aspose.com/buy).

### ฉันจะทดสอบการเปลี่ยนแปลงก่อนบันทึก PDF ได้อย่างไร
คุณสามารถดูตัวอย่าง PDF ในสภาพแวดล้อมการพัฒนาของคุณหรือใช้โปรแกรมดู PDF เพื่อตรวจสอบการปรับเปลี่ยน

### Aspose.PDF เข้ากันได้กับ .NET ทุกเวอร์ชันหรือไม่
Aspose.PDF รองรับ .NET หลายเวอร์ชัน ตรวจสอบความเข้ากันได้กับเวอร์ชัน .NET ที่คุณใช้

### ฉันสามารถจัดการฟิลด์ฟอร์มอื่นในลักษณะเดียวกันได้หรือไม่
ใช่ เทคนิคที่คล้ายกันสามารถนำไปใช้กับฟิลด์ฟอร์มประเภทอื่นในเอกสาร PDF ได้