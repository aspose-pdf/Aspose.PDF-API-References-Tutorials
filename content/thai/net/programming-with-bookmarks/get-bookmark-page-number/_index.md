---
title: รับหมายเลขหน้าบุ๊กมาร์กในไฟล์ PDF
linktitle: รับหมายเลขหน้าบุ๊กมาร์กในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: รับหมายเลขหน้าบุ๊กมาร์กในไฟล์ PDF ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 60
url: /th/net/programming-with-bookmarks/get-bookmark-page-number/
---
การดึงหมายเลขหน้าที่เกี่ยวข้องกับบุ๊กมาร์กในไฟล์ PDF จะมีประโยชน์สำหรับการนำทาง ด้วย Aspose.PDF สำหรับ .NET คุณสามารถรับหมายเลขหน้าของบุ๊กมาร์กได้อย่างง่ายดายโดยทำตามซอร์สโค้ดต่อไปนี้:

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ก่อนที่คุณจะเริ่มต้น คุณต้องนำเข้าไลบรารีที่จำเป็นสำหรับโปรเจ็กต์ C# ของคุณ นี่คือคำสั่งการนำเข้าที่จำเป็น:

```csharp
using Aspose.Pdf.Facades;
```

## ขั้นตอนที่ 2: กำหนดเส้นทางไปยังโฟลเดอร์เอกสาร

 ในขั้นตอนนี้ คุณจะต้องระบุเส้นทางไปยังโฟลเดอร์ที่มีไฟล์ PDF ที่คุณต้องการแยกหมายเลขหน้าบุ๊กมาร์ก แทนที่`"YOUR DOCUMENT DIRECTORY"`ในรหัสต่อไปนี้พร้อมเส้นทางจริงไปยังโฟลเดอร์เอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 3: สร้างเครื่องมือแก้ไขบุ๊กมาร์ก

 ตอนนี้เราจะสร้าง`PdfBookmarkEditor` วัตถุเพื่อจัดการบุ๊กมาร์กของเอกสาร ใช้รหัสต่อไปนี้:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## ขั้นตอนที่ 4: เปิดไฟล์ PDF

 ในขั้นตอนนี้ เราจะเปิดไฟล์ PDF โดยใช้นามสกุล`BindPdf` วิธีการแก้ไขบุ๊กมาร์ก นี่คือรหัสที่เกี่ยวข้อง:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## ขั้นตอนที่ 5: แยกบุ๊กมาร์ก

 ตอนนี้เราจะแยกบุ๊กมาร์กออกจากเอกสารโดยใช้`ExtractBookmarks` วิธีการแก้ไขบุ๊กมาร์ก นี่คือรหัสที่เกี่ยวข้อง:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## ขั้นตอนที่ 6: เรียกดูบุ๊กมาร์กและรับหมายเลขหน้า

 สุดท้าย เราจะวนซ้ำบุ๊กมาร์กที่แยกออกมา และรับหมายเลขหน้าที่เกี่ยวข้องกับบุ๊กมาร์กแต่ละอันโดยใช้`foreach` วนซ้ำ นี่คือรหัสที่เกี่ยวข้อง:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### ตัวอย่างซอร์สโค้ดสำหรับรับหมายเลขหน้าบุ๊กมาร์กโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// สร้าง PdfBookmarkEditor
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// เปิดไฟล์ PDF
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// แยกบุ๊กมาร์ก
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## บทสรุป

ขอแสดงความยินดี! ตอนนี้ คุณมีคำแนะนำทีละขั้นตอนในการรับหมายเลขหน้าบุ๊กมาร์กด้วย Aspose.PDF สำหรับ .NET คุณสามารถใช้รหัสนี้เพื่อดึงข้อมูลการนำทางที่เกี่ยวข้องกับบุ๊กมาร์กแต่ละรายการในเอกสาร PDF ของคุณ

อย่าลืมตรวจสอบเอกสารอย่างเป็นทางการของ Aspose.PDF สำหรับข้อมูลเพิ่มเติมเกี่ยวกับคุณสมบัติการจัดการบุ๊กมาร์กขั้นสูง

### คำถามที่พบบ่อยในการรับหมายเลขหน้าบุ๊กมาร์กในรูปแบบไฟล์ PDF

#### ถาม: บุ๊กมาร์กในไฟล์ PDF คืออะไร

ตอบ: บุ๊กมาร์กในไฟล์ PDF เป็นเครื่องมือช่วยนำทางที่ช่วยให้ผู้ใช้สามารถข้ามไปยังส่วนหรือหน้าเฉพาะภายในเอกสารได้อย่างรวดเร็ว พวกเขาปรับปรุงประสบการณ์ผู้ใช้ด้วยการจัดเตรียมทางลัดไปยังเนื้อหาที่เกี่ยวข้อง

#### ถาม: เหตุใดฉันจึงต้องดึงหมายเลขหน้าบุ๊กมาร์กจากไฟล์ PDF

ตอบ: การดึงหมายเลขหน้าบุ๊กมาร์กช่วยให้ผู้ใช้นำทางผ่านเอกสารได้อย่างมีประสิทธิภาพมากขึ้น โดยให้ข้อบ่งชี้ที่ชัดเจนว่าบุ๊กมาร์กแต่ละรายการนำไปสู่ที่ใด สิ่งนี้มีประโยชน์อย่างยิ่งสำหรับเอกสารขนาดยาวที่มีหลายส่วน

#### ถาม: ฉันจะนำเข้าไลบรารีที่จำเป็นสำหรับโปรเจ็กต์ C# ของฉันได้อย่างไร

ตอบ: หากต้องการนำเข้าไลบรารีที่จำเป็นสำหรับโครงการ C# ของคุณ ให้ใช้คำสั่งการนำเข้าต่อไปนี้:

```csharp
using Aspose.Pdf.Facades;
```

คำสั่งนี้อนุญาตให้คุณใช้คลาสและวิธีการที่ได้รับจาก Aspose.PDF สำหรับ .NET

#### ถาม: ฉันจะระบุเส้นทางไปยังโฟลเดอร์เอกสารได้อย่างไร

 ตอบ: ในซอร์สโค้ดที่ให้มา ให้แทนที่`"YOUR DOCUMENT DIRECTORY"`ด้วยเส้นทางจริงไปยังโฟลเดอร์ที่มีไฟล์ PDF ที่คุณต้องการแยกหมายเลขหน้าบุ๊กมาร์ก เพื่อให้แน่ใจว่าโค้ดสามารถค้นหาไฟล์ PDF เป้าหมายได้

#### ถาม: ฉันจะสร้างเครื่องมือแก้ไขบุ๊กมาร์กได้อย่างไร

ตอบ: หากต้องการสร้างเครื่องมือแก้ไขบุ๊กมาร์ก ให้ใช้โค้ดต่อไปนี้:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### ถาม: ฉันจะเปิดไฟล์ PDF เพื่อจัดการบุ๊กมาร์กได้อย่างไร

ตอบ: หากต้องการเปิดไฟล์ PDF เพื่อแยกข้อมูลบุ๊กมาร์ก ให้ใช้รหัสต่อไปนี้:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 แทนที่`"GetBookmarks.pdf"` ด้วยชื่อไฟล์จริง

#### ถาม: ฉันจะแยกบุ๊กมาร์กออกจากไฟล์ PDF ได้อย่างไร

 ตอบ: หากต้องการแยกบุ๊กมาร์กออกจากไฟล์ PDF ให้ใช้ไฟล์`ExtractBookmarks` วิธีการแก้ไขบุ๊กมาร์ก:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### ถาม: ฉันจะดึงและแสดงหมายเลขหน้าบุ๊กมาร์กได้อย่างไร

 ตอบ: วนซ้ำบุ๊กมาร์กที่แยกออกมาโดยใช้`foreach` วนซ้ำและเข้าถึง`PageNumber` คุณสมบัติของแต่ละบุ๊กมาร์กเพื่อดึงและแสดงหมายเลขหน้าที่เกี่ยวข้อง:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### ถาม: ฉันสามารถแก้ไขคุณสมบัติบุ๊กมาร์กโดยใช้วิธีนี้ได้หรือไม่

 ตอบ: แม้ว่าบทช่วยสอนนี้จะเน้นไปที่การดึงหมายเลขหน้าบุ๊กมาร์ก คุณสามารถแก้ไขคุณสมบัติบุ๊กมาร์กอื่นๆ ได้โดยใช้คุณสมบัติเดียวกัน`Bookmark`วัตถุและคุณสมบัติที่เกี่ยวข้อง

#### ถาม: ฉันจะบันทึกไฟล์ PDF ที่อัปเดตหลังจากแยกข้อมูลบุ๊กมาร์กได้อย่างไร

ตอบ: การแยกบุ๊กมาร์กไม่ได้แก้ไขไฟล์ PDF ต้นฉบับ หากคุณต้องการบันทึกการเปลี่ยนแปลง คุณสามารถทำได้โดยใช้วิธีอื่นที่ Aspose.PDF สำหรับ .NET ให้มา