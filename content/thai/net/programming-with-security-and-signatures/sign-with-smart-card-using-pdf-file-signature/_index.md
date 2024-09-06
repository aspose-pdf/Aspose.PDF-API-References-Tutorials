---
title: ลงนามด้วยสมาร์ทการ์ดโดยใช้ลายเซ็นไฟล์ PDF
linktitle: ลงนามด้วยสมาร์ทการ์ดโดยใช้ลายเซ็นไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: ลงนามไฟล์ PDF ของคุณอย่างปลอดภัยด้วยสมาร์ทการ์ดโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 110
url: /th/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
การลงนามดิจิทัลด้วยสมาร์ทการ์ดเป็นวิธีที่ปลอดภัยในการลงนามไฟล์ PDF ด้วย Aspose.PDF สำหรับ .NET คุณสามารถลงนามไฟล์ PDF โดยใช้สมาร์ทการ์ดได้อย่างง่ายดายโดยทำตามโค้ดต้นฉบับต่อไปนี้:

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ก่อนที่คุณจะเริ่มต้น คุณต้องนำเข้าไลบรารีที่จำเป็นสำหรับโครงการ C# ของคุณ ต่อไปนี้คือคำสั่งนำเข้าที่จำเป็น:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## ขั้นตอนที่ 2: ตั้งค่าเส้นทางไปยังโฟลเดอร์เอกสาร

 ในขั้นตอนนี้ คุณต้องระบุเส้นทางไปยังโฟลเดอร์ที่มีไฟล์ PDF ที่คุณต้องการลงนาม แทนที่`"YOUR DOCUMENTS DIRECTORY"` ในโค้ดต่อไปนี้โดยมีเส้นทางจริงไปยังโฟลเดอร์เอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 3: โหลดเอกสาร PDF

ตอนนี้เราจะโหลดเอกสาร PDF ที่จะลงนามโดยใช้โค้ดต่อไปนี้:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## ขั้นตอนที่ 4: ดำเนินการลงนามด้วยสมาร์ทการ์ด

 ในขั้นตอนนี้เราจะดำเนินการลงนามด้วยสมาร์ทการ์ดโดยใช้`PdfFileSignature` ชั้นเรียนจาก`Facades`ไลบรารี เราเลือกใบรับรองสมาร์ทการ์ดจากที่เก็บใบรับรองของ Windows และระบุข้อมูลการลงนามที่จำเป็น นี่คือรหัสที่เกี่ยวข้อง:

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

 สุดท้ายเราตรวจสอบลายเซ็นของไฟล์ PDF ที่ลงนามแล้วโดยใช้`PdfFileSignature` คลาส เราจะได้ชื่อลายเซ็นและตรวจสอบทีละชื่อ หากลายเซ็นไม่ผ่านการตรวจสอบ ข้อยกเว้นจะเกิดขึ้น นี่คือโค้ดที่เกี่ยวข้อง:

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

### ตัวอย่างโค้ดต้นฉบับสำหรับการลงนามด้วยสมาร์ทการ์ดโดยใช้ไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// ลงชื่อเข้าใช้ด้วยการเลือกใบรับรองในที่เก็บใบรับรองของ Windows
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// เลือกใบรับรองในร้านค้าด้วยตนเอง
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

ขอแสดงความยินดี! ตอนนี้คุณมีคำแนะนำทีละขั้นตอนในการลงนามไฟล์ PDF ด้วยสมาร์ทการ์ดโดยใช้ Aspose.PDF สำหรับ .NET แล้ว คุณสามารถใช้โค้ดนี้เพื่อเพิ่มลายเซ็นดิจิทัลที่ปลอดภัยลงในเอกสาร PDF ของคุณได้

อย่าลืมตรวจสอบเอกสาร Aspose.PDF อย่างเป็นทางการเพื่อดูข้อมูลเพิ่มเติมเกี่ยวกับคุณลักษณะการจัดการลายเซ็นดิจิทัลขั้นสูงและใบรับรอง

### คำถามที่พบบ่อย

#### ถาม: เหตุใดฉันจึงควรพิจารณาการลงนามไฟล์ PDF ด้วยสมาร์ทการ์ด?

A: การลงนามในไฟล์ PDF ด้วยสมาร์ทการ์ดช่วยเพิ่มความปลอดภัยโดยรับรองความถูกต้องและความสมบูรณ์ของเอกสาร ลายเซ็นบนสมาร์ทการ์ดช่วยเพิ่มความน่าเชื่อถือและการปฏิบัติตามข้อกำหนดในระดับที่สูงขึ้น

#### ถาม: การลงนามดิจิทัลที่ใช้สมาร์ทการ์ดทำงานอย่างไร

A: การลงนามดิจิทัลโดยใช้สมาร์ทการ์ดเกี่ยวข้องกับการใช้คีย์การเข้ารหัสที่เก็บไว้ในสมาร์ทการ์ดเพื่อสร้างลายเซ็นดิจิทัลที่ไม่ซ้ำใคร ลายเซ็นนี้จะแนบไปกับไฟล์ PDF ช่วยให้ผู้รับสามารถตรวจสอบแหล่งที่มาและความสมบูรณ์ของเอกสารได้

#### ถาม: บทบาทของ Aspose.PDF สำหรับ .NET ในการลงนามโดยใช้สมาร์ทการ์ดคืออะไร

A: Aspose.PDF สำหรับ .NET มอบชุดเครื่องมือและไลบรารีที่ครอบคลุมเพื่ออำนวยความสะดวกในการลงนามดิจิทัลบนไฟล์ PDF โดยใช้สมาร์ทการ์ด ช่วยให้กระบวนการง่ายขึ้นและรับรองการลงนามเอกสารอย่างปลอดภัย

#### ถาม: ฉันสามารถเลือกใบรับรองสมาร์ทการ์ดเฉพาะสำหรับการลงนามได้หรือไม่

A: ใช่ คุณสามารถเลือกใบรับรองสมาร์ทการ์ดเฉพาะจากที่เก็บใบรับรองของ Windows สำหรับการลงนาม Aspose.PDF สำหรับ .NET ช่วยให้คุณรวมการเลือกใบรับรองเข้ากับแอปพลิเคชันของคุณได้อย่างราบรื่น

#### ถาม: ซอร์สโค้ดที่ให้มาจัดการการลงนามโดยใช้สมาร์ทการ์ดอย่างไร

A: ซอร์สโค้ดสาธิตวิธีการผูกเอกสาร PDF เลือกใบรับรองสมาร์ทการ์ด ระบุข้อมูลการลงนาม และสร้างลายเซ็นดิจิทัล นอกจากนี้ยังแสดงวิธีการตรวจสอบความถูกต้องของลายเซ็นอีกด้วย

#### ถาม: ฉันสามารถใช้ลายเซ็นหลายรายการโดยใช้สมาร์ทการ์ดในไฟล์ PDF เดียวได้หรือไม่

A: แน่นอน คุณสามารถนำลายเซ็นบนสมาร์ทการ์ดหลายรายการมาใช้กับไฟล์ PDF ไฟล์เดียวได้ ลายเซ็นแต่ละรายการไม่ซ้ำกันและช่วยเพิ่มความปลอดภัยให้กับเอกสารโดยรวม

#### ถาม: จะเกิดอะไรขึ้นถ้าลายเซ็นไม่ผ่านการตรวจสอบในขั้นตอนการตรวจสอบ?

ก: หากลายเซ็นไม่ผ่านการตรวจสอบ จะมีการแสดงข้อยกเว้นเพื่อระบุว่าลายเซ็นนั้นไม่ถูกต้อง วิธีนี้จะช่วยให้มั่นใจได้ว่าลายเซ็นนั้นถูกต้องและเชื่อถือได้เท่านั้นที่จะได้รับการยอมรับ

#### ถาม: การลงนามโดยใช้สมาร์ทการ์ดสามารถใช้งานร่วมกับเอกสาร PDF ทุกประเภทได้หรือไม่

A: ใช่ การลงนามโดยใช้สมาร์ทการ์ดนั้นใช้ได้กับเอกสาร PDF ทุกประเภท คุณสามารถใช้ลายเซ็นดิจิทัลกับไฟล์ PDF หลายประเภท รวมถึงแบบฟอร์ม รายงาน และอื่นๆ

#### ถาม: ฉันจะเรียนรู้เพิ่มเติมเกี่ยวกับการจัดการลายเซ็นดิจิทัลและใบรับรองขั้นสูงได้อย่างไร

ก: สำรวจเอกสาร Aspose.PDF อย่างเป็นทางการเพื่อรับข้อมูลเชิงลึกเกี่ยวกับคุณลักษณะลายเซ็นดิจิทัลขั้นสูง การจัดการใบรับรอง และแนวทางปฏิบัติที่ดีที่สุดในการรับรองความปลอดภัยของเอกสาร

#### ถาม: ฉันสามารถขอความช่วยเหลือหรือการสนับสนุนเพิ่มเติมสำหรับการนำระบบลงนามโดยใช้สมาร์ทการ์ดได้จากที่ใด

ตอบ: สำหรับคำแนะนำและการสนับสนุนเพิ่มเติม โปรดติดต่อฟอรัมชุมชน Aspose.PDF หรือดูเอกสารประกอบเพื่อดูข้อมูลโดยละเอียดเกี่ยวกับการลงนามโดยใช้สมาร์ทการ์ด