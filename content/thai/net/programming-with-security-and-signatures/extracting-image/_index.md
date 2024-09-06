---
title: การดึงภาพออกมา
linktitle: การดึงภาพออกมา
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: แยกภาพจากเอกสาร PDF ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 70
url: /th/net/programming-with-security-and-signatures/extracting-image/
---
การแยกภาพจากเอกสาร PDF อาจมีประโยชน์ในหลายกรณี ด้วย Aspose.PDF สำหรับ .NET คุณสามารถแยกภาพได้อย่างง่ายดายโดยใช้โค้ดต้นฉบับต่อไปนี้:

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ก่อนที่คุณจะเริ่มต้น คุณต้องนำเข้าไลบรารีที่จำเป็นสำหรับโครงการ C# ของคุณ ต่อไปนี้คือคำสั่งนำเข้าที่จำเป็น:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## ขั้นตอนที่ 2: ตั้งค่าเส้นทางไปยังโฟลเดอร์เอกสาร

 ในขั้นตอนนี้ คุณต้องระบุเส้นทางไปยังโฟลเดอร์ที่มีไฟล์ PDF ที่คุณต้องการแยกภาพออกมา แทนที่`"YOUR DOCUMENTS DIRECTORY"` ในโค้ดต่อไปนี้โดยมีเส้นทางจริงไปยังโฟลเดอร์เอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## ขั้นตอนที่ 3: ดึงภาพจากเอกสาร PDF

ตอนนี้เราจะดึงภาพจากเอกสาร PDF โดยใช้โค้ดต่อไปนี้:

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

ในตัวอย่างนี้ เราจะวนซ้ำผ่านแต่ละฟิลด์ของฟอร์มในเอกสาร PDF หากพบฟิลด์ลายเซ็น เราจะแยกภาพที่เกี่ยวข้องและบันทึกลงในไฟล์ JPEG

### ตัวอย่างโค้ดต้นฉบับสำหรับการดึงภาพโดยใช้ Aspose.PDF สำหรับ .NET 
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

ขอแสดงความยินดี! ตอนนี้คุณมีคำแนะนำทีละขั้นตอนในการแยกภาพจากเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET แล้ว คุณสามารถรวมโค้ดนี้เข้ากับโปรเจ็กต์ของคุณเองเพื่อแยกภาพและใช้งานตามต้องการ

อย่าลืมดูเอกสาร Aspose.PDF อย่างเป็นทางการเพื่อดูข้อมูลเพิ่มเติมเกี่ยวกับการแยกภาพขั้นสูงและฟีเจอร์การจัดการเอกสาร PDF


### คำถามที่พบบ่อย

#### ถาม: Aspose.PDF สำหรับ .NET เหมาะสำหรับผู้เริ่มต้นหรือไม่

A: แม้ว่าความคุ้นเคยกับการเขียนโปรแกรม C# จะเป็นประโยชน์ แต่บทช่วยสอนของเราได้รับการออกแบบมาให้เป็นมิตรต่อผู้เริ่มต้น โดยจะแนะนำคุณในแต่ละขั้นตอน

#### ถาม: ฉันสามารถดึงรูปภาพหลายภาพออกมาพร้อมกันได้ไหม?

A: แน่นอน! ด้วยการใช้ลูปและปรับเปลี่ยนโค้ดที่ให้มา คุณสามารถดึงภาพหลายภาพจากเอกสาร PDF เดียวได้

#### ถาม: Aspose.PDF สำหรับ .NET เป็นโซลูชั่นเดียวสำหรับการแยกรูปภาพหรือไม่

A: แม้จะมีเครื่องมืออื่นๆ ให้ใช้งาน แต่ Aspose.PDF สำหรับ .NET ได้รับการยกย่องในเรื่องประสิทธิภาพและคุณสมบัติที่ครอบคลุม

#### ถาม: ฉันสามารถใช้รูปภาพที่แยกออกมาเพื่อวัตถุประสงค์เชิงพาณิชย์ได้หรือไม่

A: ใช่ เมื่อแยกไฟล์ออกมาแล้ว คุณสามารถนำรูปภาพเหล่านั้นไปใช้งานได้ตามต้องการ รวมถึงสำหรับโปรเจ็กต์เชิงพาณิชย์ด้วย

#### ถาม: ฉันสามารถหาแหล่งข้อมูลเพิ่มเติมเกี่ยวกับการจัดการ PDF ด้วย Aspose.PDF ได้จากที่ใด

ตอบ: เยี่ยมชมเอกสารอย่างเป็นทางการของเราเพื่อดูทรัพยากรและข้อมูลเชิงลึกมากมายเกี่ยวกับการจัดการ PDF ขั้นสูงด้วย Aspose.PDF สำหรับ .NET