---
title: ลงนามด้วยสมาร์ทการ์ดโดยใช้ช่องลายเซ็น
linktitle: ลงนามด้วยสมาร์ทการ์ดโดยใช้ช่องลายเซ็น
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: ลงนามไฟล์ PDF ของคุณอย่างปลอดภัยด้วยสมาร์ทการ์ดโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 120
url: /th/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
การลงนามดิจิทัลด้วยสมาร์ทการ์ดเป็นวิธีที่ปลอดภัยในการลงนามไฟล์ PDF ด้วย Aspose.PDF สำหรับ .NET คุณสามารถลงนามไฟล์ PDF ได้อย่างง่ายดายโดยใช้ฟิลด์ลายเซ็นและสมาร์ทการ์ดโดยทำตามโค้ดต้นฉบับต่อไปนี้:

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ก่อนที่คุณจะเริ่มต้น คุณต้องนำเข้าไลบรารีที่จำเป็นสำหรับโครงการ C# ของคุณ ต่อไปนี้คือคำสั่งนำเข้าที่จำเป็น:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## ขั้นตอนที่ 2: ตั้งค่าเส้นทางไปยังโฟลเดอร์เอกสาร

 ในขั้นตอนนี้ คุณต้องระบุเส้นทางไปยังโฟลเดอร์ที่มีไฟล์ PDF ที่คุณต้องการลงนาม แทนที่`"YOUR DOCUMENTS DIRECTORY"` ในโค้ดต่อไปนี้โดยมีเส้นทางจริงไปยังโฟลเดอร์เอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 3: คัดลอกและเปิดเอกสาร PDF

ตอนนี้เราจะคัดลอกและเปิดเอกสาร PDF ที่จะลงนามโดยใช้โค้ดต่อไปนี้:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // สร้างช่องลายเซ็น
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // เลือกใบรับรองในร้านค้า
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // สร้างลายเซ็นภายนอกพร้อมข้อมูลที่จำเป็น
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## ขั้นตอนที่ 4: ตรวจสอบลายเซ็น

 สุดท้ายเราตรวจสอบลายเซ็นของไฟล์ PDF ที่ลงนามแล้วโดยใช้`PdfFileSignature` คลาส เราจะได้ชื่อลายเซ็นและตรวจสอบทีละชื่อ หากลายเซ็นไม่ผ่านการตรวจสอบ ข้อยกเว้นจะเกิดขึ้น นี่คือโค้ดที่เกี่ยวข้อง:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

### ตัวอย่างโค้ดต้นฉบับสำหรับการลงนามด้วยสมาร์ทการ์ดโดยใช้ฟิลด์ลายเซ็นโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// ลงชื่อเข้าใช้ด้วยการเลือกใบรับรองในที่เก็บใบรับรองของ Windows
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// เลือกใบรับรองในร้านค้าด้วยตนเอง
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

ขอแสดงความยินดี! ตอนนี้คุณมีคำแนะนำทีละขั้นตอนในการลงนามไฟล์ PDF ด้วยสมาร์ทการ์ดโดยใช้ฟิลด์ลายเซ็นด้วย Aspose.PDF สำหรับ .NET คุณสามารถใช้โค้ดนี้เพื่อเพิ่มลายเซ็นดิจิทัลที่ปลอดภัยลงในเอกสาร PDF ของคุณได้

อย่าลืมตรวจสอบเอกสาร Aspose.PDF อย่างเป็นทางการเพื่อดูข้อมูลเพิ่มเติมเกี่ยวกับคุณลักษณะการจัดการลายเซ็นดิจิทัลขั้นสูงและใบรับรอง

### คำถามที่พบบ่อย

#### ถาม: มีประโยชน์อะไรจากการใช้ช่องลายเซ็นเพื่อลงนามดิจิทัลด้วยสมาร์ทการ์ด?

A: การใช้ช่องลายเซ็นสำหรับการลงนามดิจิทัลด้วยสมาร์ทการ์ดจะช่วยให้มีพื้นที่สำหรับลงลายเซ็นในไฟล์ PDF ซึ่งจะทำให้เอกสารมีความชัดเจนมากขึ้นและรับรองความถูกต้องของลายเซ็น

#### ถาม: ไลบรารี Aspose.PDF สำหรับ .NET รองรับการลงนามแบบดิจิทัลบนสมาร์ทการ์ดที่มีฟิลด์ลายเซ็นได้อย่างไร

A: Aspose.PDF สำหรับ .NET ทำให้กระบวนการสร้างฟิลด์ลายเซ็น การเลือกใบรับรองสมาร์ทการ์ด และการลงลายเซ็นดิจิทัลในพื้นที่เฉพาะภายในเอกสาร PDF ง่ายขึ้น

#### ถาม: เหตุใดการเลือกใบรับรองเฉพาะจึงมีความสำคัญสำหรับการลงนามโดยใช้สมาร์ทการ์ด?

A: การเลือกใบรับรองเฉพาะช่วยให้คุณระบุผู้ลงนามได้อย่างชัดเจนและรับรองความถูกต้องของลายเซ็น ซึ่งจะช่วยสร้างความน่าเชื่อถือและการปฏิบัติตามมาตรฐานการลงนามดิจิทัล

#### ถาม: ซอร์สโค้ดที่ให้มาจัดการกระบวนการลงนามโดยใช้สมาร์ทการ์ดที่มีฟิลด์ลายเซ็นอย่างไร

A: ซอร์สโค้ดสาธิตวิธีการสร้างฟิลด์ลายเซ็น เลือกใบรับรองสมาร์ทการ์ด และใช้ลายเซ็นดิจิทัลพร้อมข้อมูลการลงนามเฉพาะ นอกจากนี้ยังแสดงวิธีการตรวจสอบความถูกต้องของลายเซ็นอีกด้วย

#### ถาม: ฉันสามารถปรับแต่งลักษณะของช่องลายเซ็นได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏของช่องลายเซ็น เช่น ขนาด ตำแหน่ง และการแสดงภาพ ให้สอดคล้องกับเค้าโครงเอกสารของคุณได้

#### ถาม: จะเกิดอะไรขึ้นถ้าลายเซ็นไม่ผ่านการตรวจสอบในขั้นตอนการตรวจสอบ?

ก: หากลายเซ็นไม่ผ่านการตรวจสอบ จะมีการแสดงข้อยกเว้นเพื่อระบุว่าลายเซ็นนั้นไม่ถูกต้อง วิธีนี้จะช่วยให้มั่นใจได้ว่าลายเซ็นนั้นถูกต้องและเชื่อถือได้เท่านั้นที่จะได้รับการยอมรับ

#### ถาม: ฉันสามารถใช้ฟิลด์ลายเซ็นหลายรายการและลายเซ็นแบบสมาร์ทการ์ดกับเอกสาร PDF เดียวได้หรือไม่

A: แน่นอน คุณสามารถนำช่องลายเซ็นหลายช่องและลายเซ็นแบบสมาร์ทการ์ดไปใช้กับพื้นที่ต่างๆ ของเอกสาร PDF เดียวกันได้ ซึ่งจะช่วยเพิ่มความปลอดภัยหลายชั้น

#### ถาม: การใช้ช่องลายเซ็นช่วยปรับปรุงกระบวนการลงนามเอกสารโดยรวมได้อย่างไร

ตอบ การใช้ช่องลายเซ็นช่วยให้กระบวนการลงนามเอกสารมีประสิทธิภาพมากขึ้น เนื่องจากช่องลายเซ็นจะช่วยแนะนำให้ผู้ลงนามวางลายเซ็นในพื้นที่ที่กำหนด ทำให้กระบวนการลงนามเป็นระเบียบมากขึ้นและเป็นมิตรต่อผู้ใช้มากขึ้น

#### ถาม: มีข้อจำกัดใด ๆ ในการใช้ฟิลด์ลายเซ็นกับการลงนามโดยใช้สมาร์ทการ์ดหรือไม่

A: ไม่มีข้อจำกัดโดยธรรมชาติในการใช้ช่องลายเซ็นกับการลงนามโดยใช้สมาร์ทการ์ด อย่างไรก็ตาม สิ่งสำคัญคือต้องแน่ใจว่าตำแหน่งช่องลายเซ็นที่เลือกไว้จะไม่บดบังเนื้อหาเอกสารที่สำคัญ

#### ถาม: ฉันจะค้นหาความช่วยเหลือหรือการสนับสนุนเพิ่มเติมสำหรับการนำการลงนามโดยใช้สมาร์ทการ์ดที่มีฟิลด์ลายเซ็นได้จากที่ใด

ก: สำหรับคำแนะนำและการสนับสนุนเพิ่มเติม คุณสามารถดูเอกสาร Aspose.PDF อย่างเป็นทางการและฟอรัมชุมชน ซึ่งให้ข้อมูลเชิงลึกและโซลูชั่นที่มีค่าสำหรับการนำลายเซ็นดิจิทัลที่ปลอดภัยไปใช้