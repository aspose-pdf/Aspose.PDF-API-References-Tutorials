---
title: กำลังแยกรูปภาพ
linktitle: กำลังแยกรูปภาพ
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: แยกรูปภาพจากเอกสาร PDF ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 70
url: /th/net/programming-with-security-and-signatures/extracting-image/
---
การแยกรูปภาพออกจากเอกสาร PDF อาจมีประโยชน์ในหลายกรณี ด้วย Aspose.PDF สำหรับ .NET คุณสามารถแยกรูปภาพได้อย่างง่ายดายโดยใช้ซอร์สโค้ดต่อไปนี้:

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ก่อนที่คุณจะเริ่มต้น คุณต้องนำเข้าไลบรารีที่จำเป็นสำหรับโปรเจ็กต์ C# ของคุณ ต่อไปนี้เป็นคำสั่งนำเข้าที่จำเป็น:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## ขั้นตอนที่ 2: กำหนดเส้นทางไปยังโฟลเดอร์เอกสาร

 ในขั้นตอนนี้ คุณจะต้องระบุเส้นทางไปยังโฟลเดอร์ที่มีไฟล์ PDF ที่คุณต้องการแยกรูปภาพ แทนที่`"YOUR DOCUMENTS DIRECTORY"`ในรหัสต่อไปนี้พร้อมเส้นทางจริงไปยังโฟลเดอร์เอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## ขั้นตอนที่ 3: แยกรูปภาพจากเอกสาร PDF

ตอนนี้เราจะแยกรูปภาพออกจากเอกสาร PDF โดยใช้รหัสต่อไปนี้:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

ในตัวอย่างนี้ เราวนซ้ำแต่ละฟิลด์ของแบบฟอร์มในเอกสาร PDF หากพบฟิลด์ลายเซ็น เราจะแยกรูปภาพที่เกี่ยวข้องและบันทึกเป็นไฟล์ JPEG

### ตัวอย่างซอร์สโค้ดสำหรับการแยกรูปภาพโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## บทสรุป

ขอแสดงความยินดี! ตอนนี้ คุณมีคำแนะนำทีละขั้นตอนในการแยกรูปภาพจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถรวมโค้ดนี้เข้ากับโปรเจ็กต์ของคุณเองเพื่อแยกรูปภาพและใช้งานได้ตามต้องการ

อย่าลืมตรวจสอบเอกสารอย่างเป็นทางการของ Aspose.PDF สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการแยกรูปภาพขั้นสูงและคุณสมบัติการจัดการเอกสาร PDF


### คำถามที่พบบ่อย

#### ถาม: Aspose.PDF สำหรับ .NET เหมาะสำหรับผู้เริ่มต้นหรือไม่

ตอบ: แม้ว่าความคุ้นเคยกับการเขียนโปรแกรม C# จะเป็นประโยชน์ แต่บทช่วยสอนของเราได้รับการออกแบบมาให้เหมาะกับผู้เริ่มต้น โดยจะแนะนำคุณในแต่ละขั้นตอน

#### ถาม: ฉันสามารถดึงภาพหลายภาพพร้อมกันได้หรือไม่

ตอบ: แน่นอน! ด้วยการใช้ลูปและการปรับโค้ดที่ให้มา คุณสามารถดึงภาพหลายภาพจากเอกสาร PDF เดียวได้

#### ถาม: Aspose.PDF สำหรับ .NET เป็นเพียงโซลูชันเดียวสำหรับการแตกไฟล์รูปภาพหรือไม่

ตอบ: แม้ว่าจะมีเครื่องมืออื่นๆ ให้ใช้งาน แต่ Aspose.PDF สำหรับ .NET ก็มีชื่อเสียงในด้านประสิทธิภาพและฟีเจอร์ที่ครอบคลุม

#### ถาม: ฉันสามารถใช้ภาพที่แยกออกมาเพื่อวัตถุประสงค์ทางการค้าได้หรือไม่

ตอบ: ได้ เมื่อแยกออกมาแล้ว รูปภาพต่างๆ จะเป็นของคุณเพื่อใช้ตามต้องการ รวมถึงสำหรับโครงการเชิงพาณิชย์ด้วย

#### ถาม: ฉันจะหาแหล่งข้อมูลเพิ่มเติมเกี่ยวกับการจัดการ PDF ด้วย Aspose.PDF ได้ที่ไหน

ตอบ: ไปที่เอกสารอย่างเป็นทางการของเราเพื่อดูทรัพยากรและข้อมูลเชิงลึกมากมายเกี่ยวกับการจัดการ PDF ขั้นสูงด้วย Aspose.PDF สำหรับ .NET