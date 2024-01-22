---
title: Các phần tử cấu trúc khối văn bản
linktitle: Các phần tử cấu trúc khối văn bản
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Tìm hiểu cách sử dụng Aspose.PDF cho .NET để thêm các thành phần cấu trúc khối văn bản, chẳng hạn như tiêu đề và đoạn văn được gắn thẻ, vào tài liệu PDF hiện có.
type: docs
weight: 220
url: /vi/net/programming-with-tagged-pdf/text-block-structure-elements/
---
Trong hướng dẫn chi tiết này, chúng tôi sẽ hướng dẫn bạn từng bước về mã nguồn C# được cung cấp để tạo các thành phần cấu trúc khối văn bản trong tài liệu PDF được gắn thẻ bằng Aspose.PDF cho .NET. Hãy làm theo hướng dẫn bên dưới để hiểu cách thêm tiêu đề đa cấp và đoạn văn được gắn thẻ vào tài liệu PDF của bạn.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn đã định cấu hình môi trường phát triển của mình để sử dụng Aspose.PDF cho .NET. Điều này bao gồm việc cài đặt thư viện Aspose.PDF và định cấu hình dự án của bạn để tham chiếu nó.

## Bước 2: Tạo tài liệu PDF

Trong bước này, chúng tôi sẽ tạo một đối tượng tài liệu PDF mới với Aspose.PDF.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu PDF
Document document = new Document();
```

Chúng tôi đã tạo một tài liệu PDF mới với Aspose.PDF.

## Bước 3: Nhận nội dung được gắn thẻ và đặt tiêu đề và ngôn ngữ

Bây giờ, hãy lấy nội dung được gắn thẻ của tài liệu PDF và đặt tiêu đề cũng như ngôn ngữ cho tài liệu.

```csharp
// Nhận nội dung được gắn thẻ
ITaggedContent taggedContent = document.TaggedContent;

// Xác định tiêu đề và ngôn ngữ của tài liệu
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Chúng tôi đã đặt tiêu đề và ngôn ngữ của tài liệu PDF được gắn thẻ.

## Bước 4: Lấy phần tử cấu trúc gốc

Bây giờ hãy lấy phần tử cấu trúc gốc của tài liệu PDF.

```csharp
//Lấy phần tử cấu trúc gốc
StructureElement rootElement = taggedContent.RootElement;
```

Chúng ta đã thu được phần tử cấu trúc gốc của tài liệu PDF.

## Bước 5: Thêm tiêu đề và đoạn văn

Bây giờ chúng ta sẽ thêm các tiêu đề ở các cấp độ khác nhau và đoạn văn được gắn thẻ vào tài liệu PDF của mình.

```csharp
// Tạo tiêu đề ở các cấp độ khác nhau
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);

// Định nghĩa văn bản tiêu đề
h1.SetText("H1. Level 1 header");
h2.SetText("H2. Level 2 header");
h3.SetText("H3. Level 3 header");
h4.SetText("H4. Level 4 header");
h5.SetText("H5. Heading level 5");
h6.SetText("H6. Level 6 header");

// Thêm tiêu đề vào phần tử cấu trúc gốc
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Tạo đoạn văn
ParagraphElement p = taggedContent.CreateParagraphElement();

//Định nghĩa văn bản của đoạn văn
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet Nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");

// Thêm đoạn văn vào phần tử cấu trúc gốc
rootElement.AppendChild(p);
```

Chúng tôi đã thêm các tiêu đề ở các cấp độ khác nhau và đoạn văn được gắn thẻ vào thành phần cấu trúc gốc của tài liệu PDF.

## Bước 6: Lưu tài liệu PDF

Bây giờ chúng ta đã chỉnh sửa xong tài liệu PDF, hãy lưu nó vào một tệp.

```csharp
// Lưu tài liệu PDF được gắn thẻ
document.Save(dataDir + "ElementsDeStructureDeBlocsDeTexte.pdf");
```

Chúng tôi đã lưu tài liệu PDF được gắn thẻ với các thành phần cấu trúc khối văn bản trong thư mục được chỉ định.

### Mã nguồn mẫu cho Thành phần cấu trúc khối văn bản bằng Aspose.PDF cho .NET 
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
h1.SetText("H1. Header of Level 1");
h2.SetText("H2. Header of Level 2");
h3.SetText("H3. Header of Level 3");
h4.SetText("H4. Header of Level 4");
h5.SetText("H5. Header of Level 5");
h6.SetText("H6. Header of Level 6");
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
rootElement.AppendChild(p);

// Lưu tài liệu PDF được gắn thẻ
document.Save(dataDir + "TextBlockStructureElements.pdf");
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách sử dụng Aspose.PDF cho .NET để thêm các thành phần cấu trúc khối văn bản, chẳng hạn như tiêu đề và đoạn văn được gắn thẻ, vào tài liệu PDF. Bây giờ bạn có thể sử dụng các tính năng này để cải thiện cấu trúc và khả năng truy cập tài liệu PDF của mình.

### Câu hỏi thường gặp

#### Câu hỏi: Trọng tâm chính của hướng dẫn này về việc tạo các thành phần cấu trúc khối văn bản trong tài liệu PDF được gắn thẻ bằng Aspose.PDF cho .NET là gì?

Đáp: Hướng dẫn này tập trung vào việc hướng dẫn bạn trong quá trình thêm các thành phần cấu trúc khối văn bản, bao gồm các tiêu đề đa cấp và các đoạn văn được gắn thẻ, vào tài liệu PDF được gắn thẻ bằng Aspose.PDF cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước và ví dụ về mã nguồn C# để giúp bạn nâng cao cấu trúc và khả năng truy cập tài liệu PDF của mình.

#### Câu hỏi: Điều kiện tiên quyết để làm theo hướng dẫn này về các thành phần cấu trúc khối văn bản với Aspose.PDF cho .NET là gì?

Trả lời: Trước khi bắt đầu, hãy đảm bảo rằng bạn đã thiết lập môi trường phát triển của mình để sử dụng Aspose.PDF cho .NET. Điều này liên quan đến việc cài đặt thư viện Aspose.PDF và định cấu hình dự án của bạn để tham chiếu nó.

#### Câu hỏi: Làm cách nào tôi có thể tạo tài liệu PDF mới và thêm các thành phần cấu trúc khối văn bản bằng Aspose.PDF cho .NET?

Đáp: Hướng dẫn này cung cấp các ví dụ về mã nguồn C# minh họa cách tạo một tài liệu PDF mới cũng như thêm các tiêu đề đa cấp và các đoạn được gắn thẻ bằng Aspose.PDF cho .NET.

#### Câu hỏi: Tầm quan trọng của việc thêm các thành phần cấu trúc khối văn bản vào tài liệu PDF là gì?

Đáp: Việc thêm các thành phần cấu trúc khối văn bản, chẳng hạn như tiêu đề và đoạn văn được gắn thẻ, sẽ nâng cao cấu trúc ngữ nghĩa của tài liệu PDF. Điều này cải thiện khả năng truy cập cho trình đọc màn hình và các công nghệ hỗ trợ khác, giúp người dùng điều hướng và hiểu nội dung dễ dàng hơn.

#### Câu hỏi: Làm cách nào tôi có thể đặt tiêu đề và ngôn ngữ của tài liệu PDF được gắn thẻ bằng Aspose.PDF cho .NET?

Đáp: Hướng dẫn này bao gồm các ví dụ về mã nguồn C# minh họa cách đặt tiêu đề và ngôn ngữ của tài liệu PDF được gắn thẻ bằng Aspose.PDF cho .NET.

#### Câu hỏi: Làm cách nào tôi có thể tạo tiêu đề đa cấp trong tài liệu PDF được gắn thẻ bằng Aspose.PDF cho .NET?

 Đáp: Hướng dẫn này cung cấp các ví dụ về mã nguồn C# minh họa cách tạo các tiêu đề ở các cấp độ khác nhau bằng cách sử dụng`CreateHeaderElement()` phương thức và nối chúng vào phần tử cấu trúc gốc của tài liệu PDF được gắn thẻ.

#### Câu hỏi: Làm cách nào để thêm các đoạn được gắn thẻ vào tài liệu PDF bằng Aspose.PDF cho .NET?

Đáp: Hướng dẫn này bao gồm các ví dụ về mã nguồn C# chỉ ra cách tạo một đoạn văn bằng cách sử dụng`CreateParagraphElement()` phương thức và thêm văn bản được gắn thẻ vào nó bằng cách sử dụng`SetText()` phương pháp. Sau đó, đoạn văn này sẽ được thêm vào thành phần cấu trúc gốc của tài liệu PDF được gắn thẻ.

#### Câu hỏi: Tôi có thể tùy chỉnh giao diện và định dạng của các thành phần cấu trúc khối văn bản mà tôi thêm vào tài liệu PDF không?

Trả lời: Có, bạn có thể tùy chỉnh giao diện và định dạng của các thành phần cấu trúc khối văn bản bằng cách sử dụng các thuộc tính và phương thức khác nhau do Aspose.PDF cung cấp cho .NET. Bạn có thể điều chỉnh kiểu phông chữ, kích thước, màu sắc, căn chỉnh và các thuộc tính định dạng khác để đáp ứng các yêu cầu cụ thể của mình.

#### Câu hỏi: Mã nguồn mẫu được cung cấp trong hướng dẫn hỗ trợ như thế nào trong việc thêm các thành phần cấu trúc khối văn bản vào tài liệu PDF?

Trả lời: Mã nguồn mẫu được cung cấp đóng vai trò là tài liệu tham khảo thực tế để triển khai việc tạo các thành phần cấu trúc khối văn bản trong tài liệu PDF bằng Aspose.PDF cho .NET. Bạn có thể sử dụng mã này làm điểm bắt đầu và sửa đổi nó theo nhu cầu của bạn.

#### Câu hỏi: Làm cách nào tôi có thể nâng cao và tùy chỉnh hơn nữa tài liệu PDF của mình ngoài các thành phần cấu trúc khối văn bản bằng Aspose.PDF cho .NET?

Trả lời: Aspose.PDF for .NET cung cấp nhiều tính năng để thao tác tài liệu PDF, bao gồm thêm hình ảnh, bảng, siêu liên kết, chú thích, trường biểu mẫu, hình mờ, chữ ký số, v.v. Bạn có thể khám phá tài liệu và tài nguyên chính thức để hiểu toàn diện về khả năng của thư viện.