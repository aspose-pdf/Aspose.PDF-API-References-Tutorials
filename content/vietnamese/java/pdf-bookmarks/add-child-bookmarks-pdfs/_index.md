---
title: Thêm dấu trang con vào tệp PDF
linktitle: Thêm dấu trang con vào tệp PDF
second_title: Aspose.PDF API xử lý PDF Java
description: Tìm hiểu cách cải thiện tài liệu PDF bằng dấu trang con bằng Aspose.PDF cho Java. Hướng dẫn từng bước với các ví dụ về mã để cải thiện việc điều hướng và tổ chức.
type: docs
weight: 11
url: /vi/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## Giới thiệu về Thêm dấu trang con vào tệp PDF

Trong bài viết này, chúng ta sẽ khám phá cách thêm dấu trang con vào tài liệu PDF bằng Aspose.PDF cho Java. Dấu trang con là một cách thuận tiện để sắp xếp và điều hướng qua nội dung của tài liệu PDF, giúp người dùng dễ dàng tìm thấy các phần hoặc chủ đề cụ thể trong tài liệu hơn.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào triển khai, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Môi trường phát triển Java được cài đặt trên hệ thống của bạn.
-  Aspose.PDF cho thư viện Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/pdf/java/).

## Thiết lập môi trường

1. Tải xuống thư viện Aspose.PDF cho Java từ liên kết được cung cấp.
2. Thêm thư viện vào dự án Java của bạn.

Bây giờ, hãy bắt đầu bằng cách tạo một tài liệu PDF mới và thêm dấu trang con vào đó theo từng bước.

## Tạo một tài liệu PDF mới

Để bắt đầu, chúng ta cần khởi tạo một tài liệu PDF và thêm các trang vào đó. Đây là đoạn mã để bắt đầu:

```java
// Khởi tạo một tài liệu PDF
Document pdfDocument = new Document();

// Thêm trang vào PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

Trong ví dụ này, chúng tôi đã tạo một tài liệu PDF mới và thêm hai trang vào đó.

## Thêm dấu trang dành cho phụ huynh

Dấu trang gốc đóng vai trò là phần hoặc danh mục chính trong tài liệu PDF của bạn. Hãy tạo một số dấu trang gốc:

```java
// Tạo dấu trang gốc
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

Chúng tôi đã thêm hai dấu trang gốc, "Dấu trang gốc 1" và "Dấu trang gốc 2".

## Thêm dấu trang con

Bây giờ là lúc thêm dấu trang con vào dấu trang gốc mà chúng ta đã tạo trước đó. Dấu trang con đại diện cho các chủ đề hoặc phần phụ cụ thể trong mỗi dấu trang gốc. Đây là cách bạn có thể làm điều đó:

```java
// Thêm dấu trang con vào Dấu trang gốc 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Thêm dấu trang con vào Dấu trang gốc 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

Chúng tôi đã thêm dấu trang con vào cả "Dấu trang gốc 1" và "Dấu trang gốc 2".

## Tùy chỉnh giao diện dấu trang

Bạn có thể tùy chỉnh giao diện của dấu trang bằng cách thay đổi văn bản và kiểu dáng của dấu trang. Ngoài ra, bạn có thể thêm biểu tượng vào dấu trang để thể hiện trực quan hơn. Đây là một ví dụ về cách thực hiện:

```java
// Tùy chỉnh giao diện dấu trang
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

Trong ví dụ này, chúng tôi đã in nghiêng dấu trang gốc, thay đổi màu văn bản của dấu trang con thành màu xanh lá cây và thêm biểu tượng in nghiêng vào dấu trang con.

## Xử lý sự kiện

Dấu trang cũng có thể có các hành động liên quan đến chúng. Ví dụ: bạn có thể thêm các hành động kích hoạt khi người dùng nhấp vào dấu trang. Dưới đây là cách bạn có thể xử lý các sự kiện nhấp vào dấu trang:

```java
// Thêm hành động vào dấu trang
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

Trong mã này, chúng tôi đã thêm hành động "GoTo" vào dấu trang con sẽ đưa người dùng đến trang thứ hai của tệp PDF khi được nhấp vào.

## Lưu tệp PDF

Khi bạn đã thêm tất cả các dấu trang cần thiết cũng như tùy chỉnh giao diện và hành động của chúng, bạn có thể lưu tài liệu PDF đã sửa đổi:

```java
// Lưu tài liệu PDF
pdfDocument.save("output.pdf");
```

Tài liệu PDF có dấu trang con của bạn hiện đã sẵn sàng.

## Mã nguồn hoàn chỉnh

Đây là mã nguồn hoàn chỉnh để thêm dấu trang con vào tài liệu PDF bằng Aspose.PDF cho Java:

```java
// Khởi tạo một tài liệu PDF
Document pdfDocument = new Document();

// Thêm trang vào PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// Tạo dấu trang gốc
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// Thêm dấu trang con vào Dấu trang gốc 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Thêm dấu trang con vào Dấu trang gốc 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// Tùy chỉnh giao diện dấu trang
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// Thêm hành động vào dấu trang
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// Lưu tài liệu PDF
pdfDocument.save("output.pdf");
```

## Phần kết luận

Thêm dấu trang con vào tệp PDF bằng Aspose.PDF cho Java là một tính năng mạnh mẽ giúp nâng cao khả năng điều hướng và sắp xếp tài liệu của bạn. Bằng cách làm theo các bước được nêu trong bài viết này, bạn có thể tạo các tệp PDF có cấu trúc tốt với dấu trang gốc và dấu trang con, tùy chỉnh giao diện của chúng và thậm chí thêm các hành động để nâng cao trải nghiệm người dùng.

## Câu hỏi thường gặp

### Làm cách nào tôi có thể tải xuống Aspose.PDF cho Java?

 Bạn có thể tải xuống Aspose.PDF cho Java từ trang web[đây](https://releases.aspose.com/pdf/java/).

### Dấu trang con có được hỗ trợ trong tất cả trình xem PDF không?

Có, dấu trang con được hỗ trợ trong hầu hết các trình xem PDF hiện đại và cung cấp trải nghiệm người dùng nâng cao để điều hướng qua các tài liệu PDF.

### Tôi có thể tùy chỉnh thêm giao diện của dấu trang không?

Có, bạn có thể tùy chỉnh giao diện của dấu trang bằng cách điều chỉnh kiểu văn bản, màu sắc và biểu tượng cho phù hợp với thiết kế tài liệu của bạn.

### Tôi có thể thêm những hành động nào khác vào dấu trang?

Bên cạnh các hành động "GoTo", bạn có thể thêm các hành động như hành động "URI" để mở liên kết web hoặc hành động "JavaScript" để thực thi các tập lệnh tùy chỉnh khi nhấp vào dấu trang.

### Aspose.PDF cho Java có phù hợp với các dự án thương mại không?

Có, Aspose.PDF cho Java phù hợp cho cả dự án cá nhân và thương mại, đồng thời nó cung cấp nhiều tính năng để thao tác và tạo PDF.