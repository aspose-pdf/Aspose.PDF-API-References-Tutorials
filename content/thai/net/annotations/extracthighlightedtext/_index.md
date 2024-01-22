---
title: แยกข้อความที่เน้นสีในไฟล์ PDF
linktitle: แยกข้อความที่เน้นสีในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีแยกข้อความที่ไฮไลต์ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนนี้
type: docs
weight: 60
url: /th/net/annotations/extracthighlightedtext/
---
หากต้องการแยกข้อความที่ไฮไลต์เป็นไฟล์ PDF คุณสามารถใช้ Aspose.PDF สำหรับ .NET API API นี้มีวิธีง่ายๆ ในการดึงข้อความทั้งหมดที่ถูกไฮไลต์ในเอกสาร

## ขั้นตอนที่ 1: โหลดเอกสาร PDF

 ขั้นตอนแรกในการแยกข้อความที่ไฮไลต์ในไฟล์ PDF คือการโหลดเอกสารโดยใช้ Aspose.PDF สำหรับ .NET API คุณสามารถทำได้โดยสร้างอินสแตนซ์ใหม่ของ`Document` คลาสและส่งเส้นทางไปยังเอกสาร PDF เป็นพารามิเตอร์ 

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## ขั้นตอนที่ 2: วนซ้ำคำอธิบายประกอบทั้งหมด

 ขั้นตอนต่อไปคือการวนซ้ำคำอธิบายประกอบทั้งหมดในเอกสาร PDF คุณสามารถทำได้โดยใช้`foreach` วนซ้ำเช่นนั้น:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// รหัสไปที่นี่
}
```

## ขั้นตอนที่ 3: กรองคำอธิบายประกอบมาร์กอัปข้อความ

 ข้างใน`foreach` คุณจะต้องกรองคำอธิบายประกอบทั้งหมดที่ไม่ใช่คำอธิบายประกอบมาร์กอัปข้อความออก คุณสามารถทำได้โดยตรวจสอบว่าคำอธิบายประกอบเป็นตัวอย่างของหรือไม่`TextMarkupAnnotation` ระดับ.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// รหัสไปที่นี่
}
```

## ขั้นตอนที่ 4: ดึงส่วนข้อความที่เน้นสี

 เมื่อคุณกรองคำอธิบายประกอบมาร์กอัปข้อความทั้งหมดแล้ว คุณสามารถดึงส่วนข้อความที่ไฮไลต์สำหรับคำอธิบายประกอบแต่ละรายการได้ คุณสามารถทำได้โดยโทรไปที่`GetMarkedTextFragments()` วิธีการบน`TextMarkupAnnotation` วัตถุ.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## ขั้นตอนที่ 5: แสดงข้อความที่ไฮไลต์

 สุดท้าย คุณสามารถแสดงข้อความที่ไฮไลต์ให้ผู้ใช้เห็นได้ คุณสามารถทำได้โดยการวนซ้ำแต่ละอัน`TextFragment` วัตถุใน`TextFragmentCollection` และโทรไปที่`Text` คุณสมบัติ.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### ตัวอย่างซอร์สโค้ดสำหรับแยกข้อความที่เน้นสีโดยใช้ Aspose.PDF สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีแยกข้อความที่เน้นสีจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ด C# ที่ให้มา นักพัฒนาจึงสามารถแยกและจัดการข้อความที่ไฮไลต์ในเอกสาร PDF ของตนได้อย่างง่ายดาย

### คำถามที่พบบ่อยสำหรับการแยกข้อความที่เน้นสีเป็นไฟล์ PDF

#### ถาม: คำอธิบายประกอบมาร์กอัปข้อความในเอกสาร PDF คืออะไร

ตอบ: คำอธิบายประกอบมาร์กอัปข้อความคือคำอธิบายประกอบที่เน้นหรือทำเครื่องหมายข้อความเฉพาะในเอกสาร PDF ตัวอย่างของคำอธิบายประกอบมาร์กอัปข้อความ ได้แก่ ไฮไลต์ ขีดเส้นใต้ และขีดทับ

#### ถาม: ฉันสามารถแยกข้อความจากคำอธิบายประกอบประเภทอื่นโดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET มีวิธีต่างๆ มากมายในการแยกข้อความจากคำอธิบายประกอบประเภทต่างๆ รวมถึงคำอธิบายประกอบแบบมาร์กอัปข้อความ คำอธิบายประกอบข้อความอิสระ และอื่นๆ อีกมากมาย

#### ถาม: Aspose.PDF สำหรับ .NET รองรับการแยกข้อความจากไฟล์ PDF ที่มีการป้องกันด้วยรหัสผ่านหรือไม่

 ตอบ: ใช่ Aspose.PDF สำหรับ .NET รองรับการแยกข้อความจากไฟล์ PDF ที่มีการป้องกันด้วยรหัสผ่าน คุณต้องระบุรหัสผ่านที่ถูกต้องเมื่อโหลดเอกสาร PDF โดยใช้`Document` ระดับ.

#### ถาม: ฉันสามารถกรองข้อความที่ไฮไลต์ตามเกณฑ์อื่นๆ เช่น สีหรือผู้เขียนได้หรือไม่

ตอบ: ได้ คุณสามารถกรองข้อความที่ไฮไลต์ตามเกณฑ์อื่นๆ ได้ เช่น สี ผู้เขียน หรือวันที่สร้าง Aspose.PDF สำหรับ .NET มีวิธีการเข้าถึงและกรองคำอธิบายประกอบตามคุณสมบัติ

#### ถาม: เป็นไปได้หรือไม่ที่จะบันทึกข้อความที่ไฮไลต์ที่แยกออกมาเป็นไฟล์อื่น

ตอบ: ได้ คุณสามารถบันทึกข้อความที่ไฮไลต์ที่แยกออกมาเป็นไฟล์แยกต่างหาก หรือจัดเก็บไว้ในโครงสร้างข้อมูลเพื่อการประมวลผลหรือการวิเคราะห์เพิ่มเติมได้
