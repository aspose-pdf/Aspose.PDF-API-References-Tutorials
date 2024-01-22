---
title: Nhận tài nguyên chú thích
linktitle: Nhận tài nguyên chú thích
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách truy xuất tài nguyên của chú thích bằng Aspose.PDF cho .NET với hướng dẫn từng bước này.
type: docs
weight: 90
url: /vi/net/annotations/getresourceofannotation/
---
Ví dụ cho thấy cách lấy tài nguyên chú thích bằng Aspose.PDF cho .NET. Để lấy tài nguyên của chú thích bằng Aspose.PDF cho .NET, hãy làm theo các bước sau:

## Bước 1: Thiết lập đường dẫn thư mục chứa tài liệu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Mở tài liệu PDF chứa chú thích có tài nguyên bạn muốn lấy.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Bước 3: Tạo chú thích

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Bước 4: Thêm chú thích vào một trang trong tài liệu.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Bước 5: Lưu tài liệu.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Bước 6: Mở tài liệu đã sửa đổi.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Bước 7: Nhận hành động của chú thích.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Bước 7: Nhận kết quả của hành động.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Bước 8: Lấy clip truyền thông.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Bước 9: Lấy thông số kỹ thuật của tệp.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Bước 10: Đọc dữ liệu của phương tiện.

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## Bước 11: In tên trình diễn và thao tác trình diễn.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Bằng cách làm theo các bước này, bạn có thể dễ dàng lấy tài nguyên chú thích trong tài liệu PDF bằng Aspose.PDF cho .NET.

### Mã nguồn mẫu cho Nhận tài nguyên chú thích bằng Aspose.PDF cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mở tài liệu
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//Tạo chú thích
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// Lưu tài liệu
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// Mở tài liệu
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//Nhận hành động của chú thích
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//Nhận biểu hiện của hành động hiển thị
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// Đoạn phim truyền thông
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//Dữ liệu của phương tiện có thể truy cập được trong FileSpecification.Contents
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách lấy tài nguyên của một chú thích cụ thể từ tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn C# được cung cấp, nhà phát triển có thể dễ dàng truy cập và quản lý các chú thích, bao gồm cả chú thích hiển thị, trong tài liệu PDF của họ.

### Câu hỏi thường gặp

#### Câu hỏi: Phiên bản trong ngữ cảnh chú thích PDF là gì?

Đáp: Trong ngữ cảnh của các chú thích PDF, bản trình diễn là bản trình bày nội dung đa phương tiện. Nó cho phép nhúng đa phương tiện, chẳng hạn như âm thanh hoặc video, trong tài liệu PDF. Chú thích hiển thị chỉ định phương tiện sẽ được trình bày và cách phát phương tiện đó.

#### Câu hỏi: Tôi có thể lấy tên của tệp phương tiện được liên kết với chú thích hiển thị không?

Đáp: Có, bạn có thể lấy tên của tệp phương tiện được liên kết với chú thích hiển thị bằng Aspose.PDF cho .NET. Tên tập tin media có thể được truy cập thông qua`FileSpecification` sau đó`MediaClip` sự vật.

#### Câu hỏi: Aspose.PDF cho .NET có thể trích xuất các tệp phương tiện từ chú thích hiển thị không?

Trả lời: Có, Aspose.PDF cho .NET có thể trích xuất dữ liệu đa phương tiện từ chú thích hiển thị, bao gồm nội dung âm thanh hoặc video và lưu dưới dạng tệp riêng biệt.

#### Câu hỏi: Làm cách nào tôi có thể truy cập dữ liệu đa phương tiện của chú thích hiển thị?

 Đáp: Dữ liệu đa phương tiện của chú thích hiển thị có thể được truy cập thông qua`FileSpecification.Contents` tài sản của`MediaClipData` sự vật.

#### Câu hỏi: Tôi có thể sửa đổi phương tiện được liên kết với chú thích hiển thị bằng Aspose.PDF cho .NET không?

Trả lời: Aspose.PDF for .NET cung cấp các phương thức để truy cập và sửa đổi dữ liệu phương tiện được liên kết với chú thích hiển thị. Bạn có thể cập nhật hoặc thay thế tệp phương tiện được sử dụng bởi chú thích hiển thị.