---
title: Trích xuất văn bản được đánh dấu trong tệp PDF
linktitle: Trích xuất văn bản được đánh dấu trong tệp PDF
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách trích xuất văn bản được đánh dấu trong tệp PDF bằng Aspose.PDF cho .NET với hướng dẫn từng bước này.
type: docs
weight: 60
url: /vi/net/annotations/extracthighlightedtext/
---
Để trích xuất văn bản được đánh dấu trong tệp PDF, bạn có thể sử dụng API Aspose.PDF cho .NET. API này cung cấp một cách đơn giản để truy xuất tất cả văn bản đã được đánh dấu trong tài liệu.

## Bước 1: Tải tài liệu PDF

 Bước đầu tiên trong việc trích xuất văn bản được đánh dấu trong tệp PDF là tải tài liệu bằng API Aspose.PDF cho .NET. Bạn có thể làm điều này bằng cách tạo một phiên bản mới của`Document` class và chuyển đường dẫn đến tài liệu PDF dưới dạng tham số. 

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## Bước 2: Lặp lại tất cả các chú thích

 Bước tiếp theo là lặp qua tất cả các chú thích trong tài liệu PDF. Bạn có thể làm điều này bằng cách sử dụng một`foreach` vòng lặp, như vậy:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// Mã ở đây
}
```

## Bước 3: Lọc chú thích đánh dấu văn bản

 Bên trong`foreach` vòng lặp, bạn sẽ cần lọc ra tất cả các chú thích không phải là chú thích đánh dấu văn bản. Bạn có thể làm điều này bằng cách kiểm tra xem chú thích có phải là một phiên bản của`TextMarkupAnnotation` lớp học.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// Mã ở đây
}
```

## Bước 4: Truy xuất các đoạn văn bản được đánh dấu

 Khi bạn đã lọc tất cả các chú thích đánh dấu văn bản, bạn có thể truy xuất các đoạn văn bản được đánh dấu cho mỗi chú thích. Bạn có thể làm điều này bằng cách gọi`GetMarkedTextFragments()` phương pháp trên`TextMarkupAnnotation` sự vật.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## Bước 5: Hiển thị văn bản được đánh dấu

 Cuối cùng, bạn có thể hiển thị văn bản được đánh dấu cho người dùng. Bạn có thể làm điều này bằng cách lặp qua từng`TextFragment` đối tượng trong`TextFragmentCollection` và gọi`Text` tài sản.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Mã nguồn ví dụ để trích xuất văn bản được đánh dấu bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách trích xuất văn bản được đánh dấu từ tài liệu PDF bằng Aspose.PDF cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn C# được cung cấp, nhà phát triển có thể dễ dàng trích xuất và quản lý văn bản được đánh dấu trong tài liệu PDF của họ.

### Câu hỏi thường gặp về trích xuất văn bản được đánh dấu trong tệp PDF

#### Hỏi: Chú thích đánh dấu văn bản trong tài liệu PDF là gì?

Đáp: Chú thích đánh dấu văn bản là chú thích làm nổi bật hoặc đánh dấu văn bản cụ thể trong tài liệu PDF. Ví dụ về chú thích đánh dấu văn bản bao gồm đánh dấu, gạch chân và gạch ngang.

#### Câu hỏi: Tôi có thể trích xuất văn bản từ các loại chú thích khác bằng Aspose.PDF cho .NET không?

Trả lời: Có, Aspose.PDF cho .NET cung cấp nhiều phương pháp khác nhau để trích xuất văn bản từ các loại chú thích khác nhau, bao gồm chú thích đánh dấu văn bản, chú thích văn bản miễn phí, v.v.

#### Câu hỏi: Aspose.PDF for .NET có hỗ trợ trích xuất văn bản từ các tệp PDF được bảo vệ bằng mật khẩu không?

 Trả lời: Có, Aspose.PDF for .NET hỗ trợ trích xuất văn bản từ các tệp PDF được bảo vệ bằng mật khẩu. Bạn cần cung cấp mật khẩu chính xác khi tải tài liệu PDF bằng cách sử dụng`Document` lớp học.

#### Câu hỏi: Tôi có thể lọc văn bản được đánh dấu dựa trên các tiêu chí khác, chẳng hạn như màu sắc hoặc tác giả không?

Đáp: Có, bạn có thể lọc văn bản được đánh dấu dựa trên các tiêu chí khác, chẳng hạn như màu sắc, tác giả hoặc ngày tạo. Aspose.PDF for .NET cung cấp các phương thức truy cập và lọc các chú thích dựa trên thuộc tính của chúng.

#### Hỏi: Có thể lưu văn bản được đánh dấu đã trích xuất vào một tệp riêng biệt không?

Trả lời: Có, bạn có thể lưu văn bản được đánh dấu đã trích xuất vào một tệp riêng biệt hoặc lưu trữ nó trong cấu trúc dữ liệu để xử lý hoặc phân tích thêm.
