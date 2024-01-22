---
title: Xóa siêu liên kết sau khi chuyển đổi từ Html
linktitle: Xóa siêu liên kết sau khi chuyển đổi từ Html
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước để loại bỏ siêu liên kết sau khi chuyển đổi HTML sang PDF bằng Aspose.PDF cho .NET.
type: docs
weight: 250
url: /vi/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình xóa siêu liên kết khỏi tệp PDF được tạo từ tệp HTML bằng Aspose.PDF cho .NET. Siêu liên kết là các liên kết có thể nhấp vào và có thể chuyển hướng đến các trang hoặc trang web khác. Bằng cách làm theo các bước bên dưới, bạn sẽ có thể xóa siêu liên kết khỏi tệp PDF thu được.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Thư viện Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn.
- Một môi trường phát triển như Visual Studio.

## Bước 1: Tải tệp HTML và xóa siêu liên kết
Ở bước này, chúng tôi sẽ tải tệp HTML và xóa các siêu liên kết khỏi tài liệu PDF thu được. Sử dụng mã sau đây:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tệp HTML bằng các tùy chọn tải HTML
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Duyệt qua các chú thích của trang đầu tiên của tài liệu
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Kiểm tra xem chú thích có phải là một liên kết không
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Kiểm tra xem hành động có thuộc loại GoToURIAction không
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Sử dụng trình hấp thụ đoạn văn bản để tìm các đoạn văn bản phù hợp
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Lặp qua các đoạn văn bản phù hợp và xóa thuộc tính khỏi siêu liên kết
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Xóa chú thích khỏi trang
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 Hãy chắc chắn để thay thế`"YOUR DOCUMENTS DIRECTORY"` với thư mục thực nơi chứa tệp HTML của bạn.

## Bước 2: Lưu tệp PDF kết quả
Cuối cùng, chúng tôi sẽ lưu tệp PDF kết quả mà không có siêu liên kết. Sử dụng mã sau đây:

```csharp
// Lưu tệp PDF kết quả
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Đoạn mã trên lưu tệp PDF kết quả với tên tệp`"RemoveHyperlinksFromText_out.pdf"`.

### Mã nguồn ví dụ cho Xóa siêu liên kết sau khi chuyển đổi từ Html bằng Aspose.PDF cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày quy trình từng bước để xóa siêu liên kết khỏi tệp PDF được tạo từ tệp HTML bằng Aspose.PDF cho .NET. Bằng cách làm theo các hướng dẫn được mô tả ở trên, bạn sẽ có thể xóa thành công các siêu liên kết khỏi tệp PDF thu được.

### Câu hỏi thường gặp

#### Câu hỏi: Aspose.PDF dành cho .NET là gì?

Đáp: Aspose.PDF for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tài liệu PDF trong các ứng dụng C#. Nó cung cấp nhiều chức năng, bao gồm khả năng chuyển đổi tệp HTML sang PDF và thao tác nội dung PDF.

#### Hỏi: Tại sao tôi muốn xóa siêu liên kết khỏi tệp PDF?

Trả lời: Có nhiều lý do khác nhau để xóa siêu liên kết khỏi tệp PDF. Ví dụ: bạn có thể muốn loại bỏ các liên kết bên ngoài cho mục đích in hoặc lưu trữ hoặc đảm bảo rằng nội dung PDF không thể điều hướng được qua các siêu liên kết.

#### Câu hỏi: Làm cách nào tôi có thể tải tệp HTML và xóa siêu liên kết bằng Aspose.PDF cho .NET?

 Trả lời: Để tải tệp HTML và xóa siêu liên kết, bạn có thể sử dụng Aspose.PDF cho .NET`HtmlLoadOptions` lớp học. Lặp lại các chú thích của trang PDF để tìm chú thích liên kết và sửa đổi thuộc tính của chúng.

#### Hỏi: Tôi có thể tùy chỉnh tên tệp đầu ra cho tệp PDF thu được không?

Trả lời: Có, bạn có thể tùy chỉnh tên tệp đầu ra cho tệp PDF thu được bằng cách sửa đổi mã lưu tài liệu PDF. Chỉ cần thay đổi tên tệp mong muốn trong`doc.Save()` phương pháp.

#### Hỏi: Có thể loại bỏ có chọn lọc các siêu liên kết dựa trên các tiêu chí nhất định không?

Đáp: Có, bạn có thể loại bỏ có chọn lọc các siêu liên kết dựa trên các tiêu chí cụ thể. Ví dụ: bạn có thể chọn chỉ xóa các liên kết bên ngoài hoặc các liên kết trỏ đến các URL cụ thể.