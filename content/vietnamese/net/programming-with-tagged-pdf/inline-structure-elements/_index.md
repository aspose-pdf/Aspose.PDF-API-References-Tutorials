---
title: Các phần tử cấu trúc nội tuyến
linktitle: Các phần tử cấu trúc nội tuyến
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước cách sử dụng các thành phần cấu trúc trực tuyến với Aspose.PDF cho .NET. Sắp xếp các tệp PDF của bạn với các tiêu đề và đoạn văn.
type: docs
weight: 110
url: /vi/net/programming-with-tagged-pdf/inline-structure-elements/
---
Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách sử dụng các thành phần cấu trúc nội tuyến với Aspose.PDF cho .NET. Aspose.PDF là một thư viện mạnh mẽ cho phép bạn thao tác các tài liệu PDF theo chương trình. Các phần tử cấu trúc nội tuyến cho phép bạn tạo cấu trúc phân cấp trong tài liệu PDF của mình bằng cách sử dụng các tiêu đề ở các cấp độ và đoạn văn khác nhau.

Hãy đi sâu vào mã và tìm hiểu cách sử dụng các phần tử cấu trúc nội tuyến với Aspose.PDF cho .NET.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Thư viện Aspose.PDF dành cho .NET được cài đặt.
2. Có kiến thức cơ bản về ngôn ngữ lập trình C#.

## Bước 1: Thiết lập môi trường

Để bắt đầu, hãy mở môi trường phát triển C# của bạn và tạo một dự án mới. Đảm bảo rằng bạn đã thêm tham chiếu đến thư viện Aspose.PDF cho .NET trong dự án của mình.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tạo tài liệu

 Bước đầu tiên là tạo một tài liệu PDF mới bằng cách sử dụng`Document` lớp học.

```csharp
// Tạo tài liệu PDF
Document document = new Document();
```

## Bước 3: Làm việc với nội dung được gắn thẻ

Sau đó, chúng tôi lấy nội dung được gắn thẻ của tài liệu để làm việc.

```csharp
// Lấy nội dung được gắn thẻ của tài liệu
ITaggedContent taggedContent = document.TaggedContent;
```

## Bước 4: Đặt tiêu đề và ngôn ngữ tài liệu

Bây giờ chúng ta có thể đặt tiêu đề và ngôn ngữ tài liệu.

```csharp
// Xác định tiêu đề và ngôn ngữ của tài liệu
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Bước 5: Thêm các phần tử kết cấu trực tuyến

Bây giờ chúng ta sẽ thêm các thành phần cấu trúc nội tuyến chẳng hạn như tiêu đề ở các cấp độ và đoạn văn khác nhau vào tài liệu của chúng ta.

```csharp
// Lấy phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;

// Thêm tiêu đề ở các cấp độ khác nhau
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Thêm nội dung vào mỗi tiêu đề
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// Thêm một đoạn văn
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Thêm nội dung vào đoạn văn
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

Ở đây, chúng tôi tạo các thành phần cấu trúc nội tuyến, chẳng hạn như tiêu đề ở các cấp độ khác nhau và một đoạn văn, rồi thêm nội dung vào chúng.

## Bước 6: Lưu tài liệu PDF được gắn thẻ

Cuối cùng, chúng tôi lưu tài liệu PDF được gắn thẻ.

```csharp
// Lưu tài liệu PDF được gắn thẻ
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Mã nguồn mẫu cho Thành phần cấu trúc nội tuyến bằng Aspose.PDF cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo tài liệu PDF
Document document = new Document();

// Nhận nội dung để làm việc với TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Đặt tiêu đề và ngôn ngữ cho Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Nhận phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// Lưu tài liệu PDF được gắn thẻ
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Phần kết luận

Xin chúc mừng! Bạn đã học cách sử dụng các phần tử cấu trúc nội tuyến với Aspose.PDF cho .NET. Bây giờ bạn có thể tạo cấu trúc phân cấp trong tài liệu PDF của mình bằng cách sử dụng các tiêu đề ở các cấp độ và đoạn văn khác nhau. Khám phá thêm các tính năng của Aspose.PDF để khám phá toàn bộ tiềm năng của nó.

### Câu hỏi thường gặp

#### Câu hỏi: Các thành phần cấu trúc nội tuyến trong tài liệu PDF là gì và chúng góp phần tạo ra cấu trúc phân cấp như thế nào?

Đáp: Các thành phần cấu trúc nội tuyến trong tài liệu PDF, chẳng hạn như tiêu đề ở các cấp độ và đoạn văn khác nhau, được sử dụng để tạo cấu trúc phân cấp nhằm tổ chức và trình bày nội dung theo cách có cấu trúc. Những phần tử này cho phép bạn thiết lập hệ thống phân cấp và luồng thông tin rõ ràng trong tài liệu.

#### Câu hỏi: Các thành phần cấu trúc nội tuyến có thể nâng cao khả năng đọc và tổ chức của tài liệu PDF bằng cách nào?

Đáp: Các thành phần cấu trúc nội tuyến, đặc biệt là các tiêu đề và đoạn văn, giúp cải thiện khả năng đọc và tổ chức của tài liệu PDF bằng cách cung cấp cấu trúc logic. Các tiêu đề cho biết mức độ quan trọng khác nhau và giúp người đọc điều hướng nội dung, trong khi các đoạn văn nhóm các thông tin liên quan lại với nhau.

#### Câu hỏi: Aspose.PDF cho .NET tạo điều kiện thuận lợi cho việc sử dụng các phần tử cấu trúc nội tuyến như thế nào?

Đáp: Aspose.PDF for .NET cung cấp các lớp và phương thức để tạo và thao tác các thành phần cấu trúc nội tuyến, chẳng hạn như tiêu đề và đoạn văn. Các thành phần này có thể được tùy chỉnh, sắp xếp theo thứ bậc và làm phong phú thêm nội dung để cải thiện cách trình bày trực quan và khả năng truy cập của tài liệu.

####  Hỏi: Mục đích của việc này là gì?`taggedContent` object in relation to inline structure elements?

 Đáp: Cái`taggedContent` đối tượng thu được từ`TaggedContent` tài sản của một`Document`, cho phép bạn làm việc với các phần tử có cấu trúc, bao gồm các phần tử cấu trúc nội tuyến. Nó cho phép bạn tạo, tùy chỉnh và sắp xếp các tiêu đề và đoạn văn trong tài liệu.

#### Câu hỏi: Các phần tử cấu trúc nội tuyến hỗ trợ như thế nào trong việc tạo ra hệ thống phân cấp tài liệu rõ ràng?

Đáp: Các phần tử cấu trúc nội tuyến, chẳng hạn như các tiêu đề ở các cấp độ khác nhau, góp phần thiết lập hệ thống phân cấp rõ ràng và được xác định rõ ràng trong tài liệu. Người đọc có thể nhanh chóng xác định các chủ đề chính, chủ đề phụ và nội dung liên quan, giúp tài liệu dễ dàng điều hướng và dễ hiểu hơn.

#### Câu hỏi: Tôi có thể tùy chỉnh giao diện và định dạng của các thành phần cấu trúc nội tuyến bằng Aspose.PDF cho .NET không?

Đáp: Có, bạn có thể tùy chỉnh hình thức và định dạng của các thành phần cấu trúc nội tuyến. Bạn có thể đặt các thuộc tính như kiểu phông chữ, kích thước, màu sắc, căn chỉnh, thụt lề và khoảng cách để đạt được cách trình bày trực quan mong muốn cho các tiêu đề và đoạn văn.

#### Câu hỏi: Làm cách nào để tạo và thêm tiêu đề ở các cấp độ khác nhau vào tài liệu PDF bằng cách sử dụng các thành phần cấu trúc nội tuyến trong Aspose.PDF cho .NET?

 Đáp: Bạn có thể tạo các tiêu đề ở các cấp độ khác nhau bằng cách sử dụng`CreateHeaderElement` phương thức và sau đó nối chúng vào phần tử cấu trúc gốc. Sau đó, bạn có thể thêm nội dung vào từng thành phần tiêu đề bằng cách sử dụng`CreateSpanElement` phương pháp tạo các đoạn văn bản.

#### Câu hỏi: Tôi có thể sử dụng các thành phần cấu trúc nội tuyến để tạo danh sách, dấu đầu dòng hoặc các kiểu tổ chức nội dung khác trong tài liệu PDF không?

Trả lời: Mặc dù bản thân các phần tử cấu trúc nội tuyến chủ yếu được sử dụng cho tiêu đề và đoạn văn, nhưng bạn có thể sử dụng chúng kết hợp với các tính năng khác do Aspose.PDF cung cấp cho .NET để tạo danh sách, dấu đầu dòng, bảng và các loại tổ chức nội dung khác để có một cái nhìn toàn diện. cấu trúc tài liệu.

#### Câu hỏi: Các phần tử cấu trúc nội tuyến đóng góp như thế nào vào khả năng truy cập tài liệu?

Đáp: Các thành phần cấu trúc nội tuyến đóng vai trò quan trọng trong việc nâng cao khả năng truy cập tài liệu. Các tiêu đề và đoạn văn có cấu trúc phù hợp sẽ cung cấp hệ thống phân cấp tài liệu rõ ràng nhằm hỗ trợ trình đọc màn hình và các công nghệ hỗ trợ khác trong việc diễn giải và truyền tải nội dung một cách chính xác tới người dùng khuyết tật.

#### Câu hỏi: Tôi có thể khám phá các cách sử dụng nâng cao hơn của các phần tử cấu trúc nội tuyến, chẳng hạn như tạo các phần tử tương tác hoặc nhúng đa phương tiện không?

Đ: Chắc chắn rồi! Trong khi hướng dẫn này tập trung vào việc tạo tiêu đề và đoạn văn, Aspose.PDF cho .NET cung cấp các tính năng nâng cao để tạo các phần tử tương tác, nhúng đa phương tiện, thêm siêu liên kết, v.v. Kiểm tra tài liệu và ví dụ của thư viện để tìm hiểu sâu hơn về các khả năng nâng cao này.