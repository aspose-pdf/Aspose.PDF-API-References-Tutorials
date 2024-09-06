---
title: ลงชื่อเข้าใช้ไฟล์ PDF แบบดิจิทัล
linktitle: ลงชื่อเข้าใช้ไฟล์ PDF แบบดิจิทัล
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีลงนามดิจิทัลในไฟล์ PDF ด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 40
url: /th/net/programming-with-security-and-signatures/digitally-sign/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับกระบวนการลงนามดิจิทัลในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ลายเซ็นดิจิทัลช่วยรับประกันความถูกต้องและความสมบูรณ์ของเอกสารโดยการเพิ่มลายนิ้วมืออิเล็กทรอนิกส์เฉพาะ

## ขั้นตอนที่ 1: ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- การติดตั้ง Visual Studio บนเครื่องของคุณ
- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว

## ขั้นตอนที่ 2: การตั้งค่าสภาพแวดล้อม

ในการเริ่มต้น ให้ทำตามขั้นตอนเหล่านี้เพื่อตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ:

1. เปิด Visual Studio และสร้างโปรเจ็กต์ C# ใหม่
2. นำเข้าเนมสเปซที่จำเป็นลงในไฟล์โค้ดของคุณ:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## ขั้นตอนที่ 3: ลายเซ็นดิจิทัล

ขั้นตอนแรกคือการลงนามดิจิทัลในไฟล์ PDF รหัสที่ให้มาจะแสดงวิธีการสร้างลายเซ็นดิจิทัลด้วย Aspose.PDF สำหรับ .NET

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

โค้ดนี้จะโหลดไฟล์ PDF สร้างลายเซ็นดิจิทัลที่มีลักษณะตามที่กำหนด จากนั้นบันทึกไฟล์ PDF พร้อมลายเซ็นที่เพิ่มเข้ามา

## ขั้นตอนที่ 4: การตรวจสอบลายเซ็น

หลังจากเพิ่มลายเซ็นดิจิทัลแล้ว คุณสามารถตรวจสอบว่าไฟล์ PDF มีลายเซ็นที่ถูกต้องหรือไม่

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // ทำอะไรสักอย่าง
                     }
                 }
             }
         }
     }
}
```

รหัสนี้จะตรวจสอบลายเซ็นแรกของไฟล์ PDF และดำเนินการเพิ่มเติมหากลายเซ็นได้รับการรับรองและมีสิทธิ์เฉพาะ

### ตัวอย่างโค้ดต้นฉบับสำหรับการลงนามแบบดิจิทัลโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
try
{
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // ใช้วัตถุ PKCS7/PKCS7Detached
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// ตั้งค่าลักษณะลายเซ็น
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// สร้างลายเซ็นประเภทใดประเภทหนึ่งจากสามประเภท
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// บันทึกไฟล์ PDF เอาท์พุต
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // มีลายเซ็นมั้ย?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // ตรวจสอบอันแรก
				{
					if (signature.IsCertified) // ได้รับการรับรองแล้ว?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // รับสิทธิ์การเข้าถึง
						{
							// ทำอะไรสักอย่าง
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## บทสรุป

ขอแสดงความยินดี! คุณได้ดำเนินการลงนามดิจิทัลบนไฟล์ PDF สำเร็จแล้วโดยใช้ Aspose.PDF สำหรับ .NET บทช่วยสอนนี้ครอบคลุมกระบวนการทีละขั้นตอนตั้งแต่การเพิ่มลายเซ็นดิจิทัลไปจนถึงการตรวจสอบความถูกต้อง ตอนนี้คุณสามารถใช้คุณลักษณะนี้เพื่อรักษาความปลอดภัยไฟล์ PDF ของคุณด้วยลายเซ็นดิจิทัล

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้คืออะไร?

A: บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับกระบวนการลงนามดิจิทัลในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ลายเซ็นดิจิทัลจะเพิ่มลายนิ้วมืออิเล็กทรอนิกส์เพื่อรับรองความถูกต้องและความสมบูรณ์ของเอกสาร

#### ถาม: มีข้อกำหนดเบื้องต้นอะไรบ้างก่อนเริ่มต้น?

ก: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# แล้ว ติดตั้ง Visual Studio และติดตั้งไลบรารี Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว

#### ถาม: ฉันจะตั้งค่าสภาพแวดล้อมการพัฒนาได้อย่างไร?

ตอบ: ปฏิบัติตามขั้นตอนที่ให้มาเพื่อตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ รวมถึงการสร้างโปรเจ็กต์ C# ใหม่ใน Visual Studio และนำเข้าเนมสเปซที่จำเป็น

#### ถาม: ฉันจะเพิ่มลายเซ็นดิจิทัลลงในไฟล์ PDF ได้อย่างไร

 A: ตัวอย่างโค้ดที่ให้มาจะสาธิตวิธีการโหลดไฟล์ PDF สร้างลายเซ็นดิจิทัล กำหนดลักษณะที่ปรากฏ และบันทึกไฟล์ PDF ที่ลงนามแล้ว ลายเซ็นดิจิทัลจะถูกเพิ่มโดยใช้`Certify` วิธีการของ`PdfFileSignature` วัตถุ.

#### ถาม: ฉันจะตรวจสอบความถูกต้องของลายเซ็นดิจิทัลได้อย่างไร

A: หลังจากเพิ่มลายเซ็นดิจิทัลแล้ว คุณสามารถใช้โค้ดตัวอย่างเพื่อตรวจสอบความถูกต้องของลายเซ็นได้ โดยโค้ดตัวอย่างจะตรวจสอบว่าลายเซ็นได้รับการรับรองและมีสิทธิ์การเข้าถึงเฉพาะหรือไม่

####  ถาม: อะไร`PKCS7` object represent?

 ก. การ`PKCS7` วัตถุนี้ใช้เพื่อให้มีฟังก์ชันการเข้ารหัสสำหรับลายเซ็นดิจิทัล ใช้เพื่อสร้างลายเซ็นดิจิทัลในโค้ดตัวอย่างที่ให้มา

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของลายเซ็นดิจิทัลได้หรือไม่

 A: ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏของลายเซ็นดิจิทัลได้โดยระบุเส้นทางไปยังรูปภาพใน`SignatureAppearance` ทรัพย์สินของ`PdfFileSignature` วัตถุ.

#### ถาม: จะเกิดอะไรขึ้นถ้าลายเซ็นไม่ถูกต้อง?

A: หากลายเซ็นไม่ถูกต้อง กระบวนการตรวจสอบจะล้มเหลว และการดำเนินการที่เกี่ยวข้องภายในบล็อกรหัสตรวจสอบจะไม่ถูกดำเนินการ

#### ถาม: ฉันจะมั่นใจได้ถึงความปลอดภัยของลายเซ็นดิจิทัลของฉันได้อย่างไร

A: ลายเซ็นดิจิทัลได้รับการออกแบบมาเพื่อให้ปลอดภัย และใช้เทคนิคการเข้ารหัสเพื่อรับรองความถูกต้องและความสมบูรณ์ ตรวจสอบให้แน่ใจว่าคุณเก็บคีย์ส่วนตัวของคุณไว้อย่างปลอดภัย และปฏิบัติตามแนวทางปฏิบัติที่ดีที่สุดสำหรับการจัดการลายเซ็นดิจิทัล

#### ถาม: ฉันสามารถเพิ่มลายเซ็นดิจิทัลหลายรายการลงใน PDF ได้หรือไม่

 A: ใช่ คุณสามารถเพิ่มลายเซ็นดิจิทัลหลายรายการลงในไฟล์ PDF ได้โดยใช้`PdfFileSignature` วัตถุ`Sign` หรือ`Certify` วิธีการ ลายเซ็นแต่ละอันจะมีรูปลักษณ์และการกำหนดค่าของตัวเอง