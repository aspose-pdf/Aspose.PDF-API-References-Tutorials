---
title: ลบไฮเปอร์ลิงก์หลังจากแปลงจาก Html
linktitle: ลบไฮเปอร์ลิงก์หลังจากแปลงจาก Html
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: คำแนะนำทีละขั้นตอนในการลบไฮเปอร์ลิงก์หลังจากแปลง HTML เป็น PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 250
url: /th/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการลบไฮเปอร์ลิงก์ออกจากไฟล์ PDF ที่สร้างจากไฟล์ HTML โดยใช้ Aspose.PDF สำหรับ .NET ไฮเปอร์ลิงก์คือลิงก์ที่สามารถคลิกได้ซึ่งอาจเปลี่ยนเส้นทางไปยังหน้าหรือเว็บไซต์อื่น เมื่อทำตามขั้นตอนด้านล่าง คุณจะสามารถลบไฮเปอร์ลิงก์ออกจากไฟล์ PDF ที่ได้

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีคุณสมบัติตรงตามข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ไลบรารี Aspose.PDF สำหรับ .NET ที่ติดตั้งบนระบบของคุณ
- สภาพแวดล้อมการพัฒนาเช่น Visual Studio

## ขั้นตอนที่ 1: กำลังโหลดไฟล์ HTML และลบไฮเปอร์ลิงก์
ในขั้นตอนนี้ เราจะโหลดไฟล์ HTML และลบไฮเปอร์ลิงก์ออกจากเอกสาร PDF ที่ได้ ใช้รหัสต่อไปนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดไฟล์ HTML โดยใช้ตัวเลือกการโหลด HTML
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// เรียกดูคำอธิบายประกอบของหน้าแรกของเอกสาร
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // ตรวจสอบว่าคำอธิบายประกอบเป็นลิงก์หรือไม่
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // ตรวจสอบว่าการกระทำเป็นประเภท GoToURIAction หรือไม่
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // ใช้ตัวดูดซับส่วนของข้อความเพื่อค้นหาส่วนของข้อความที่ตรงกัน
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // วนซ้ำส่วนข้อความที่ตรงกันและลบแอตทริบิวต์ออกจากไฮเปอร์ลิงก์
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // ลบคำอธิบายประกอบออกจากหน้า
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENTS DIRECTORY"` ด้วยไดเร็กทอรีจริงที่มีไฟล์ HTML ของคุณอยู่

## ขั้นตอนที่ 2: บันทึกไฟล์ PDF ที่ได้
สุดท้าย เราจะบันทึกไฟล์ PDF ที่ได้โดยไม่มีไฮเปอร์ลิงก์ ใช้รหัสต่อไปนี้:

```csharp
// บันทึกไฟล์ PDF ที่ได้
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 โค้ดด้านบนจะบันทึกไฟล์ PDF ที่เป็นผลลัพธ์พร้อมชื่อไฟล์`"RemoveHyperlinksFromText_out.pdf"`.

### ตัวอย่างซอร์สโค้ดสำหรับการลบไฮเปอร์ลิงก์หลังจากแปลงจาก Html โดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงกระบวนการทีละขั้นตอนในการลบไฮเปอร์ลิงก์ออกจากไฟล์ PDF ที่สร้างจากไฟล์ HTML โดยใช้ Aspose.PDF สำหรับ .NET เมื่อทำตามคำแนะนำที่อธิบายไว้ข้างต้น คุณจะสามารถลบไฮเปอร์ลิงก์ออกจากไฟล์ PDF ที่ได้ได้สำเร็จ

### คำถามที่พบบ่อย

#### ถาม: Aspose.PDF สำหรับ .NET คืออะไร

ตอบ: Aspose.PDF สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับเอกสาร PDF ในแอปพลิเคชัน C# ได้ มีฟังก์ชันการทำงานที่หลากหลาย รวมถึงความสามารถในการแปลงไฟล์ HTML เป็น PDF และจัดการเนื้อหา PDF

#### ถาม: เหตุใดฉันจึงต้องการลบไฮเปอร์ลิงก์ออกจากไฟล์ PDF

ตอบ: มีเหตุผลหลายประการในการลบไฮเปอร์ลิงก์ออกจากไฟล์ PDF ตัวอย่างเช่น คุณอาจต้องการกำจัดลิงก์ภายนอกสำหรับการพิมพ์หรือการเก็บถาวร หรือตรวจสอบให้แน่ใจว่าเนื้อหา PDF ไม่สามารถนำทางผ่านไฮเปอร์ลิงก์ได้

#### ถาม: ฉันจะโหลดไฟล์ HTML และลบไฮเปอร์ลิงก์โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการโหลดไฟล์ HTML และลบไฮเปอร์ลิงก์ คุณสามารถใช้ Aspose.PDF สำหรับ .NET ได้`HtmlLoadOptions` ระดับ. วนซ้ำคำอธิบายประกอบของหน้า PDF เพื่อค้นหาคำอธิบายประกอบของลิงก์และแก้ไขแอตทริบิวต์

#### ถาม: ฉันสามารถปรับแต่งชื่อไฟล์เอาต์พุตสำหรับ PDF ที่ได้ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งชื่อไฟล์เอาต์พุตสำหรับไฟล์ PDF ที่ได้ โดยการแก้ไขโค้ดที่บันทึกเอกสาร PDF เพียงเปลี่ยนชื่อไฟล์ที่ต้องการในไฟล์`doc.Save()` วิธี.

#### ถาม: เป็นไปได้หรือไม่ที่จะเลือกลบไฮเปอร์ลิงก์ตามเกณฑ์ที่กำหนด

ตอบ: ได้ คุณสามารถเลือกลบไฮเปอร์ลิงก์ได้ตามเกณฑ์ที่กำหนด ตัวอย่างเช่น คุณสามารถเลือกลบเฉพาะลิงก์ภายนอกหรือลิงก์ที่ชี้ไปยัง URL ที่ระบุได้