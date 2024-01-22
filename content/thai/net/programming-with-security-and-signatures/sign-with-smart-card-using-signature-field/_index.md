---
title: เซ็นชื่อด้วยสมาร์ทการ์ดโดยใช้ฟิลด์ลายเซ็น
linktitle: เซ็นชื่อด้วยสมาร์ทการ์ดโดยใช้ฟิลด์ลายเซ็น
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: ลงนามไฟล์ PDF ของคุณอย่างปลอดภัยด้วยสมาร์ทการ์ดโดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 120
url: /th/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
การเซ็นชื่อแบบดิจิทัลด้วยสมาร์ทการ์ดเป็นวิธีที่ปลอดภัยในการเซ็นชื่อไฟล์ PDF ด้วย Aspose.PDF สำหรับ .NET คุณสามารถเซ็นชื่อไฟล์ PDF ได้อย่างง่ายดายโดยใช้ฟิลด์ลายเซ็นและสมาร์ทการ์ดโดยทำตามซอร์สโค้ดต่อไปนี้:

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ก่อนที่คุณจะเริ่มต้น คุณต้องนำเข้าไลบรารีที่จำเป็นสำหรับโปรเจ็กต์ C# ของคุณ ต่อไปนี้เป็นคำสั่งนำเข้าที่จำเป็น:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## ขั้นตอนที่ 2: กำหนดเส้นทางไปยังโฟลเดอร์เอกสาร

 ในขั้นตอนนี้ คุณจะต้องระบุเส้นทางไปยังโฟลเดอร์ที่มีไฟล์ PDF ที่คุณต้องการเซ็นชื่อ แทนที่`"YOUR DOCUMENTS DIRECTORY"`ในรหัสต่อไปนี้พร้อมเส้นทางจริงไปยังโฟลเดอร์เอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 3: คัดลอกและเปิดเอกสาร PDF

ตอนนี้เราจะคัดลอกและเปิดเอกสาร PDF ที่จะลงนามโดยใช้รหัสต่อไปนี้:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // สร้างฟิลด์ลายเซ็น
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

 สุดท้ายนี้ เราจะตรวจสอบลายเซ็นของไฟล์ PDF ที่ลงนามโดยใช้นามสกุลไฟล์`PdfFileSignature` ระดับ. เราได้รับชื่อลายเซ็นและตรวจสอบทีละรายการ หากลายเซ็นไม่ผ่านการตรวจสอบ จะมีข้อยกเว้นเกิดขึ้น นี่คือรหัสที่เกี่ยวข้อง:

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

### ตัวอย่างซอร์สโค้ดสำหรับการลงชื่อเข้าใช้ด้วยสมาร์ทการ์ดโดยใช้ฟิลด์ลายเซ็นโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// ลงนามด้วยการเลือกใบรับรองในที่เก็บใบรับรอง Windows
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// เลือกใบรับรองด้วยตนเองในร้านค้า
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

ขอแสดงความยินดี! ขณะนี้คุณมีคำแนะนำทีละขั้นตอนในการลงนามไฟล์ PDF ด้วยสมาร์ทการ์ดโดยใช้ฟิลด์ลายเซ็นด้วย Aspose.PDF สำหรับ .NET คุณสามารถใช้รหัสนี้เพื่อเพิ่มลายเซ็นดิจิทัลที่ปลอดภัยให้กับเอกสาร PDF ของคุณ

อย่าลืมตรวจสอบเอกสารอย่างเป็นทางการของ Aspose.PDF สำหรับข้อมูลเพิ่มเติมเกี่ยวกับคุณสมบัติการจัดการลายเซ็นดิจิทัลและใบรับรองขั้นสูง

### คำถามที่พบบ่อย

#### ถาม: การใช้ฟิลด์ลายเซ็นสำหรับการเซ็นชื่อดิจิทัลด้วยสมาร์ทการ์ดมีประโยชน์อย่างไร

ตอบ: การใช้ฟิลด์ลายเซ็นสำหรับการเซ็นชื่อแบบดิจิทัลด้วยสมาร์ทการ์ดจะทำให้พื้นที่ที่กำหนดภายใน PDF ที่ใช้ลายเซ็น ซึ่งจะช่วยเพิ่มความชัดเจนของเอกสารและรับรองความถูกต้องของลายเซ็น

#### ถาม: ไลบรารี Aspose.PDF สำหรับ .NET ช่วยอำนวยความสะดวกในการเซ็นชื่อดิจิทัลบนสมาร์ทการ์ดด้วยฟิลด์ลายเซ็นได้อย่างไร

ตอบ: Aspose.PDF สำหรับ .NET ลดความซับซ้อนของกระบวนการสร้างฟิลด์ลายเซ็น การเลือกใบรับรองสมาร์ทการ์ด และการนำลายเซ็นดิจิทัลไปใช้กับพื้นที่เฉพาะภายในเอกสาร PDF

#### ถาม: เหตุใดการเลือกใบรับรองเฉพาะจึงมีความสำคัญสำหรับการเซ็นชื่อด้วยสมาร์ทการ์ด

ตอบ: การเลือกใบรับรองเฉพาะจะทำให้คุณสามารถระบุผู้ลงนามได้โดยไม่ซ้ำกัน และรับประกันความสมบูรณ์ของลายเซ็น ซึ่งจะช่วยสร้างความไว้วางใจและการปฏิบัติตามมาตรฐานการลงนามดิจิทัล

#### ถาม: ซอร์สโค้ดที่ให้มาจัดการกับกระบวนการเซ็นชื่อแบบสมาร์ทการ์ดด้วยฟิลด์ลายเซ็นอย่างไร

ตอบ: ซอร์สโค้ดสาธิตวิธีการสร้างฟิลด์ลายเซ็น เลือกใบรับรองสมาร์ทการ์ด และใช้ลายเซ็นดิจิทัลกับข้อมูลการเซ็นชื่อเฉพาะ นอกจากนี้ยังแสดงวิธีการตรวจสอบความถูกต้องของลายเซ็นด้วย

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของช่องลายเซ็นได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของฟิลด์ลายเซ็นได้ เช่น ขนาด ตำแหน่ง และการแสดงภาพ เพื่อให้สอดคล้องกับเค้าโครงของเอกสารของคุณ

#### ถาม: จะเกิดอะไรขึ้นหากลายเซ็นไม่ผ่านการตรวจสอบระหว่างขั้นตอนการตรวจสอบ?

ตอบ: หากลายเซ็นไม่ผ่านการตรวจสอบ จะมีข้อยกเว้นเกิดขึ้น ซึ่งบ่งชี้ว่าลายเซ็นนั้นไม่ถูกต้อง เพื่อให้แน่ใจว่ายอมรับเฉพาะลายเซ็นที่ถูกต้องและเชื่อถือได้เท่านั้น

#### ถาม: ฉันสามารถใช้ช่องลายเซ็นหลายช่องและลายเซ็นแบบสมาร์ทการ์ดกับเอกสาร PDF เดียวได้หรือไม่

ตอบ: แน่นอน คุณสามารถใช้ช่องลายเซ็นหลายช่องและลายเซ็นแบบสมาร์ทการ์ดกับพื้นที่ต่างๆ ของเอกสาร PDF เดียวกันได้ โดยให้การรักษาความปลอดภัยหลายชั้น

#### ถาม: การใช้ช่องลายเซ็นช่วยเพิ่มประสิทธิภาพกระบวนการเซ็นเอกสารโดยรวมได้อย่างไร

ตอบ: การใช้ฟิลด์ลายเซ็นทำให้กระบวนการลงนามในเอกสารมีความคล่องตัวมากขึ้น เนื่องจากจะช่วยแนะนำให้ผู้ลงนามวางลายเซ็นในพื้นที่ที่กำหนด ทำให้กระบวนการลงนามมีระเบียบและใช้งานง่ายยิ่งขึ้น

#### ถาม: มีข้อจำกัดในการใช้ฟิลด์ลายเซ็นกับการเซ็นชื่อแบบสมาร์ทการ์ดหรือไม่

ตอบ: ไม่มีข้อจำกัดโดยธรรมชาติในการใช้ฟิลด์ลายเซ็นกับการเซ็นชื่อแบบสมาร์ทการ์ด อย่างไรก็ตาม สิ่งสำคัญคือต้องแน่ใจว่าตำแหน่งฟิลด์ลายเซ็นที่เลือกไม่บดบังเนื้อหาเอกสารที่สำคัญ

#### ถาม: ฉันจะขอความช่วยเหลือหรือการสนับสนุนเพิ่มเติมสำหรับการดำเนินการเซ็นชื่อด้วยสมาร์ทการ์ดด้วยฟิลด์ลายเซ็นได้ที่ไหน

ตอบ: สำหรับคำแนะนำและการสนับสนุนเพิ่มเติม คุณสามารถดูเอกสารประกอบอย่างเป็นทางการของ Aspose.PDF และฟอรัมชุมชน ซึ่งนำเสนอข้อมูลเชิงลึกอันมีค่าและโซลูชันสำหรับการนำลายเซ็นดิจิทัลที่ปลอดภัยไปใช้