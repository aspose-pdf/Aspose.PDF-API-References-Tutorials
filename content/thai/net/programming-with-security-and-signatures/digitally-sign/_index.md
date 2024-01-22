---
title: ลงชื่อเข้าใช้แบบดิจิทัลในไฟล์ PDF
linktitle: ลงชื่อเข้าใช้แบบดิจิทัลในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีลงชื่อเข้าใช้ไฟล์ PDF แบบดิจิทัลด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 40
url: /th/net/programming-with-security-and-signatures/digitally-sign/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเซ็นชื่อแบบดิจิทัลในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET ลายเซ็นดิจิทัลรับประกันความถูกต้องและความสมบูรณ์ของเอกสาร โดยการเพิ่มลายนิ้วมืออิเล็กทรอนิกส์ที่เป็นเอกลักษณ์

## ขั้นตอนที่ 1: ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- การติดตั้ง Visual Studio บนเครื่องของคุณ
- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว

## ขั้นตอนที่ 2: การตั้งค่าสภาพแวดล้อม

ในการเริ่มต้น ให้ทำตามขั้นตอนเหล่านี้เพื่อตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ:

1. เปิด Visual Studio และสร้างโครงการ C# ใหม่
2. นำเข้าเนมสเปซที่จำเป็นลงในไฟล์โค้ดของคุณ:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## ขั้นตอนที่ 3: ลายเซ็นดิจิทัล

ขั้นตอนแรกคือการเซ็นชื่อแบบดิจิทัลในไฟล์ PDF รหัสที่ให้มาจะแสดงวิธีสร้างลายเซ็นดิจิทัลด้วย Aspose.PDF สำหรับ .NET

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

โค้ดนี้จะโหลดไฟล์ PDF สร้างลายเซ็นดิจิทัลที่มีลักษณะตามที่ระบุ จากนั้นบันทึกไฟล์ PDF ด้วยลายเซ็นที่เพิ่มเข้าไป

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

### ตัวอย่างซอร์สโค้ดสำหรับการเซ็นชื่อแบบดิจิทัลโดยใช้ Aspose.PDF สำหรับ .NET 
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
			// สร้างลายเซ็นประเภทใดก็ได้จากสามประเภท
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// บันทึกไฟล์ PDF เอาต์พุต
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // มีลายเซ็นบ้างไหม?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // ยืนยันอันแรก
				{
					if (signature.IsCertified) // ได้รับการรับรอง?
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

ขอแสดงความยินดี! คุณดำเนินการลายเซ็นดิจิทัลในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว บทช่วยสอนนี้ครอบคลุมกระบวนการทีละขั้นตอน ตั้งแต่การเพิ่มลายเซ็นดิจิทัลไปจนถึงการตรวจสอบความถูกต้อง ตอนนี้คุณสามารถใช้คุณสมบัตินี้เพื่อรักษาความปลอดภัยไฟล์ PDF ของคุณด้วยลายเซ็นดิจิทัล

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอนนี้คืออะไร?

ตอบ: บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการเซ็นชื่อไฟล์ PDF แบบดิจิทัลโดยใช้ Aspose.PDF สำหรับ .NET ลายเซ็นดิจิทัลจะเพิ่มลายนิ้วมืออิเล็กทรอนิกส์เพื่อรับรองความถูกต้องและความสมบูรณ์ของเอกสาร

#### ถาม: มีข้อกำหนดเบื้องต้นอะไรบ้างก่อนที่จะเริ่ม?

ตอบ: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# ติดตั้ง Visual Studio และติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว

#### ถาม: ฉันจะตั้งค่าสภาพแวดล้อมการพัฒนาได้อย่างไร

ตอบ: ทำตามขั้นตอนที่ให้ไว้เพื่อตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ รวมถึงการสร้างโปรเจ็กต์ C# ใหม่ใน Visual Studio และการนำเข้าเนมสเปซที่จำเป็น

#### ถาม: ฉันจะเพิ่มลายเซ็นดิจิทัลลงในไฟล์ PDF ได้อย่างไร

 ตอบ: โค้ดตัวอย่างที่ให้มาจะสาธิตวิธีการโหลดไฟล์ PDF, สร้างลายเซ็นดิจิทัล, ระบุลักษณะที่ปรากฏ และบันทึกไฟล์ PDF ที่ลงนามแล้ว ลายเซ็นดิจิทัลถูกเพิ่มโดยใช้`Certify` วิธีการของ`PdfFileSignature` วัตถุ.

#### ถาม: ฉันจะตรวจสอบความถูกต้องของลายเซ็นดิจิทัลได้อย่างไร

ตอบ: หลังจากเพิ่มลายเซ็นดิจิทัลแล้ว คุณสามารถใช้โค้ดตัวอย่างเพื่อตรวจสอบความถูกต้องของลายเซ็นได้ จะตรวจสอบว่าลายเซ็นได้รับการรับรองและมีสิทธิ์การเข้าถึงเฉพาะหรือไม่

####  ถาม: อะไร`PKCS7` object represent?

 ตอบ:`PKCS7` วัตถุถูกใช้เพื่อให้ฟังก์ชันการเข้ารหัสสำหรับลายเซ็นดิจิทัล ใช้เพื่อสร้างลายเซ็นดิจิทัลในโค้ดตัวอย่างที่ให้มา

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของลายเซ็นดิจิทัลได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของลายเซ็นดิจิทัลได้โดยการระบุเส้นทางไปยังรูปภาพใน`SignatureAppearance` ทรัพย์สินของ`PdfFileSignature` วัตถุ.

#### ถาม: จะเกิดอะไรขึ้นหากลายเซ็นไม่ถูกต้อง

ตอบ: หากลายเซ็นไม่ถูกต้อง กระบวนการตรวจสอบจะล้มเหลว และการดำเนินการที่เกี่ยวข้องภายในบล็อครหัสยืนยันจะไม่ถูกดำเนินการ

#### ถาม: ฉันจะมั่นใจในความปลอดภัยของลายเซ็นดิจิทัลได้อย่างไร

ตอบ: ลายเซ็นดิจิทัลมีความปลอดภัยโดยการออกแบบและใช้เทคนิคการเข้ารหัสเพื่อให้มั่นใจในความถูกต้องและความสมบูรณ์ ตรวจสอบให้แน่ใจว่าคุณเก็บคีย์ส่วนตัวของคุณไว้อย่างปลอดภัยและปฏิบัติตามแนวทางปฏิบัติที่ดีที่สุดในการจัดการลายเซ็นดิจิทัล

#### ถาม: ฉันสามารถเพิ่มลายเซ็นดิจิทัลหลายรายการลงใน PDF ได้หรือไม่

 ตอบ: ได้ คุณสามารถเพิ่มลายเซ็นดิจิทัลหลายรายการลงในไฟล์ PDF ได้โดยใช้`PdfFileSignature` วัตถุ`Sign` หรือ`Certify` วิธีการ ลายเซ็นแต่ละรายการจะมีลักษณะและการกำหนดค่าของตัวเอง