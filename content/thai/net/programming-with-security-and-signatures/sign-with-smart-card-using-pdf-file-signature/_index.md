---
title: เซ็นชื่อด้วยสมาร์ทการ์ดโดยใช้ลายเซ็นไฟล์ PDF
linktitle: เซ็นชื่อด้วยสมาร์ทการ์ดโดยใช้ลายเซ็นไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: ลงนามไฟล์ PDF ของคุณอย่างปลอดภัยด้วยสมาร์ทการ์ดโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 110
url: /th/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
การเซ็นชื่อแบบดิจิทัลด้วยสมาร์ทการ์ดเป็นวิธีที่ปลอดภัยในการเซ็นชื่อไฟล์ PDF ด้วย Aspose.PDF สำหรับ .NET คุณสามารถเซ็นชื่อไฟล์ PDF โดยใช้สมาร์ทการ์ดได้อย่างง่ายดายโดยทำตามซอร์สโค้ดต่อไปนี้:

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ก่อนที่คุณจะเริ่มต้น คุณต้องนำเข้าไลบรารีที่จำเป็นสำหรับโปรเจ็กต์ C# ของคุณ ต่อไปนี้เป็นคำสั่งนำเข้าที่จำเป็น:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## ขั้นตอนที่ 2: กำหนดเส้นทางไปยังโฟลเดอร์เอกสาร

 ในขั้นตอนนี้ คุณจะต้องระบุเส้นทางไปยังโฟลเดอร์ที่มีไฟล์ PDF ที่คุณต้องการเซ็นชื่อ แทนที่`"YOUR DOCUMENTS DIRECTORY"`ในรหัสต่อไปนี้พร้อมเส้นทางจริงไปยังโฟลเดอร์เอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 3: โหลดเอกสาร PDF

ตอนนี้เราจะโหลดเอกสาร PDF ที่จะลงนามโดยใช้รหัสต่อไปนี้:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## ขั้นตอนที่ 4: ดำเนินการลายเซ็นด้วยสมาร์ทการ์ด

 ในขั้นตอนนี้ เราจะดำเนินการลายเซ็นด้วยสมาร์ทการ์ดโดยใช้`PdfFileSignature` ชั้นเรียนจาก`Facades`ห้องสมุด. เราเลือกใบรับรองสมาร์ทการ์ดจากที่เก็บใบรับรอง Windows และระบุข้อมูลการลงนามที่จำเป็น นี่คือรหัสที่เกี่ยวข้อง:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // เลือกใบรับรองในร้านค้า
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## ขั้นตอนที่ 5: ตรวจสอบลายเซ็น

 สุดท้ายนี้ เราจะตรวจสอบลายเซ็นของไฟล์ PDF ที่ลงนามโดยใช้นามสกุลไฟล์`PdfFileSignature` ระดับ. เราได้รับชื่อลายเซ็นและตรวจสอบทีละรายการ หากลายเซ็นไม่ผ่านการตรวจสอบ จะมีข้อยกเว้นเกิดขึ้น นี่คือรหัสที่เกี่ยวข้อง:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### ตัวอย่างซอร์สโค้ดสำหรับการลงชื่อด้วยสมาร์ทการ์ดโดยใช้ลายเซ็นไฟล์ Pdf โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// ลงนามด้วยการเลือกใบรับรองในที่เก็บใบรับรอง Windows
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// เลือกใบรับรองด้วยตนเองในร้านค้า
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
	IList<string> sigNames = pdfSign.GetSignNames();
	for (int index = 0; index <= sigNames.Count - 1; index++)
	{
		if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
		{
			throw new ApplicationException("Not verified");
		}
	}
}
```

## บทสรุป

ขอแสดงความยินดี! ตอนนี้คุณมีคำแนะนำทีละขั้นตอนในการลงนามไฟล์ PDF ด้วยสมาร์ทการ์ดโดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้รหัสนี้เพื่อเพิ่มลายเซ็นดิจิทัลที่ปลอดภัยให้กับเอกสาร PDF ของคุณ

อย่าลืมตรวจสอบเอกสารอย่างเป็นทางการของ Aspose.PDF สำหรับข้อมูลเพิ่มเติมเกี่ยวกับคุณสมบัติการจัดการลายเซ็นดิจิทัลและใบรับรองขั้นสูง

### คำถามที่พบบ่อย

#### ถาม: เหตุใดฉันจึงควรพิจารณาเซ็นชื่อไฟล์ PDF ด้วยสมาร์ทการ์ด

ตอบ: การเซ็นชื่อไฟล์ PDF ด้วยสมาร์ทการ์ดช่วยเพิ่มความปลอดภัยโดยรับประกันความถูกต้องและความสมบูรณ์ของเอกสาร ลายเซ็นที่ใช้สมาร์ทการ์ดช่วยเพิ่มความน่าเชื่อถือและการปฏิบัติตามกฎระเบียบในระดับที่สูงขึ้น

#### ถาม: การเซ็นชื่อดิจิทัลที่ใช้สมาร์ทการ์ดทำงานอย่างไร

ตอบ: การเซ็นชื่อดิจิทัลโดยใช้สมาร์ทการ์ดเกี่ยวข้องกับการใช้คีย์การเข้ารหัสที่จัดเก็บไว้ในสมาร์ทการ์ดเพื่อสร้างลายเซ็นดิจิทัลที่ไม่ซ้ำใคร ลายเซ็นนี้แนบมากับไฟล์ PDF ช่วยให้ผู้รับสามารถตรวจสอบที่มาและความสมบูรณ์ของเอกสารได้

#### ถาม: Aspose.PDF สำหรับ .NET มีบทบาทอย่างไรในการลงนามโดยใช้สมาร์ทการ์ด

ตอบ: Aspose.PDF สำหรับ .NET มีชุดเครื่องมือและไลบรารีที่ครอบคลุมเพื่ออำนวยความสะดวกในการเซ็นชื่อไฟล์ PDF แบบดิจิทัลโดยใช้สมาร์ทการ์ด ช่วยให้กระบวนการง่ายขึ้นและรับประกันการลงนามเอกสารที่ปลอดภัย

#### ถาม: ฉันสามารถเลือกใบรับรองสมาร์ทการ์ดเฉพาะสำหรับการลงนามได้หรือไม่

ตอบ: ได้ คุณสามารถเลือกใบรับรองสมาร์ทการ์ดเฉพาะจากร้านค้าใบรับรอง Windows สำหรับการลงนามได้ Aspose.PDF สำหรับ .NET ช่วยให้คุณสามารถผสานรวมการเลือกใบรับรองเข้ากับแอปพลิเคชันของคุณได้อย่างราบรื่น

#### ถาม: ซอร์สโค้ดที่ให้มาจัดการกับการเซ็นชื่อด้วยสมาร์ทการ์ดอย่างไร

ตอบ: ซอร์สโค้ดสาธิตวิธีการผูกเอกสาร PDF เลือกใบรับรองสมาร์ทการ์ด ระบุข้อมูลการลงนาม และสร้างลายเซ็นดิจิทัล นอกจากนี้ยังแสดงวิธีการตรวจสอบความถูกต้องของลายเซ็นด้วย

#### ถาม: ฉันสามารถใช้ลายเซ็นหลายลายเซ็นโดยใช้สมาร์ทการ์ดในไฟล์ PDF ไฟล์เดียวได้หรือไม่

ตอบ: แน่นอน คุณสามารถใช้ลายเซ็นแบบสมาร์ทการ์ดหลายลายเซ็นกับไฟล์ PDF ไฟล์เดียวได้ ลายเซ็นแต่ละลายเซ็นมีเอกลักษณ์เฉพาะตัวและมีส่วนช่วยในการรักษาความปลอดภัยโดยรวมของเอกสาร

#### ถาม: จะเกิดอะไรขึ้นหากลายเซ็นไม่ผ่านการตรวจสอบในระหว่างขั้นตอนการตรวจสอบ?

ตอบ: หากลายเซ็นไม่ผ่านการตรวจสอบ จะมีข้อยกเว้นเกิดขึ้น ซึ่งบ่งชี้ว่าลายเซ็นนั้นไม่ถูกต้อง เพื่อให้แน่ใจว่ายอมรับเฉพาะลายเซ็นที่ถูกต้องและเชื่อถือได้เท่านั้น

#### ถาม: การเซ็นชื่อด้วยสมาร์ทการ์ดเข้ากันได้กับเอกสาร PDF ทุกประเภทหรือไม่

ตอบ: ได้ การเซ็นชื่อด้วยสมาร์ทการ์ดเข้ากันได้กับเอกสาร PDF ทุกประเภท คุณสามารถใช้ลายเซ็นดิจิทัลกับไฟล์ PDF ประเภทต่างๆ รวมถึงแบบฟอร์ม รายงาน และอื่นๆ อีกมากมาย

#### ถาม: ฉันจะเรียนรู้เพิ่มเติมเกี่ยวกับลายเซ็นดิจิทัลขั้นสูงและการจัดการใบรับรองได้อย่างไร

ตอบ: สำรวจเอกสารประกอบอย่างเป็นทางการของ Aspose.PDF เพื่อดูข้อมูลเชิงลึกโดยละเอียดเกี่ยวกับคุณสมบัติลายเซ็นดิจิทัลขั้นสูง การจัดการใบรับรอง และแนวทางปฏิบัติที่ดีที่สุดในการรับรองความปลอดภัยของเอกสาร

#### ถาม: ฉันจะขอความช่วยเหลือหรือการสนับสนุนเพิ่มเติมสำหรับการนำการเซ็นชื่อแบบสมาร์ทการ์ดไปใช้ได้จากที่ไหน

ตอบ: สำหรับคำแนะนำและการสนับสนุนเพิ่มเติม โปรดติดต่อฟอรัมชุมชน Aspose.PDF หรือดูเอกสารประกอบสำหรับข้อมูลที่ครอบคลุมเกี่ยวกับการเซ็นชื่อด้วยสมาร์ทการ์ด