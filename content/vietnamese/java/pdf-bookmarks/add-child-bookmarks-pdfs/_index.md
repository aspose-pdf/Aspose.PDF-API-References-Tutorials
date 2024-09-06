---
title: Thêm dấu trang con vào PDF
linktitle: Thêm dấu trang con vào PDF
second_title: API xử lý PDF Java Aspose.PDF
description: Tìm hiểu cách cải thiện tài liệu PDF bằng các dấu trang con bằng Aspose.PDF cho Java. Hướng dẫn từng bước với các ví dụ mã để cải thiện khả năng điều hướng và tổ chức.
type: docs
weight: 11
url: /vi/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## Giới thiệu về Thêm Dấu trang Con vào PDF

Trong bài viết này, chúng ta sẽ khám phá cách thêm dấu trang con vào tài liệu PDF bằng Aspose.PDF cho Java. Dấu trang con là một cách thuận tiện để sắp xếp và điều hướng qua nội dung của tài liệu PDF, giúp người dùng dễ dàng tìm thấy các phần hoặc chủ đề cụ thể trong tài liệu.

## Điều kiện tiên quyết

Trước khi bắt đầu triển khai, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

- Môi trường phát triển Java được cài đặt trên hệ thống của bạn.
-  Aspose.PDF cho thư viện Java. Bạn có thể tải xuống từ[đây](https://releases.aspose.com/pdf/java/).

## Thiết lập môi trường

1. Tải xuống thư viện Aspose.PDF cho Java từ liên kết được cung cấp.
2. Thêm thư viện vào dự án Java của bạn.

Bây giờ, chúng ta hãy bắt đầu bằng cách tạo một tài liệu PDF mới và thêm dấu trang con vào đó theo từng bước.

## Tạo một tài liệu PDF mới

Để bắt đầu, chúng ta cần khởi tạo một tài liệu PDF và thêm các trang vào đó. Sau đây là đoạn mã để bắt đầu:

```java
// Khởi tạo một tài liệu PDF
Document pdfDocument = new Document();

// Thêm trang vào PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

Trong ví dụ này, chúng tôi đã tạo một tài liệu PDF mới và thêm hai trang vào đó.

## Thêm Dấu trang Cha mẹ

Dấu trang gốc đóng vai trò là các phần hoặc danh mục chính trong tài liệu PDF của bạn. Hãy tạo một số dấu trang gốc:

```java
// Tạo dấu trang cha mẹ
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

Chúng tôi đã thêm hai dấu trang phụ huynh, "Dấu trang phụ huynh 1" và "Dấu trang phụ huynh 2".

## Thêm dấu trang con

Bây giờ, đã đến lúc thêm các dấu trang con vào các dấu trang cha mà chúng ta đã tạo trước đó. Các dấu trang con đại diện cho các chủ đề hoặc tiểu mục cụ thể trong mỗi dấu trang cha. Sau đây là cách bạn có thể thực hiện:

```java
// Thêm dấu trang con vào Dấu trang cha 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Thêm dấu trang con vào Dấu trang cha 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

Chúng tôi đã thêm dấu trang con vào cả "Dấu trang cha 1" và "Dấu trang cha 2".

## Tùy chỉnh giao diện dấu trang

Bạn có thể tùy chỉnh giao diện của dấu trang bằng cách thay đổi văn bản và kiểu dáng của chúng. Ngoài ra, bạn có thể thêm biểu tượng vào dấu trang để thể hiện trực quan hơn. Sau đây là ví dụ về cách thực hiện:

```java
// Tùy chỉnh giao diện dấu trang
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

Trong ví dụ này, chúng tôi đã làm cho dấu trang cha in nghiêng, thay đổi màu văn bản của dấu trang con thành màu xanh lá cây và thêm biểu tượng in nghiêng vào dấu trang con.

## Xử lý sự kiện

Dấu trang cũng có thể có các hành động liên kết với chúng. Ví dụ: bạn có thể thêm các hành động kích hoạt khi người dùng nhấp vào dấu trang. Sau đây là cách bạn có thể xử lý các sự kiện nhấp vào dấu trang:

```java
// Thêm một hành động vào dấu trang
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

Trong mã này, chúng tôi đã thêm hành động "GoTo" vào một dấu trang con để đưa người dùng đến trang thứ hai của tệp PDF khi nhấp vào.

## Lưu PDF

Sau khi bạn đã thêm tất cả các dấu trang cần thiết và tùy chỉnh giao diện cũng như hành động của chúng, bạn có thể lưu tài liệu PDF đã sửa đổi:

```java
// Lưu tài liệu PDF
pdfDocument.save("output.pdf");
```

Tài liệu PDF có dấu trang con của bạn hiện đã sẵn sàng.

## Mã nguồn đầy đủ

Sau đây là mã nguồn đầy đủ để thêm dấu trang con vào tài liệu PDF bằng Aspose.PDF cho Java:

```java
// Khởi tạo một tài liệu PDF
Document pdfDocument = new Document();

// Thêm trang vào PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// Tạo dấu trang cha mẹ
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// Thêm dấu trang con vào Dấu trang cha 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Thêm dấu trang con vào Dấu trang cha 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// Tùy chỉnh giao diện dấu trang
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// Thêm một hành động vào dấu trang
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// Lưu tài liệu PDF
pdfDocument.save("output.pdf");
```

## Phần kết luận

Thêm dấu trang con vào PDF bằng Aspose.PDF for Java là một tính năng mạnh mẽ giúp cải thiện khả năng điều hướng và sắp xếp tài liệu của bạn. Bằng cách làm theo các bước được nêu trong bài viết này, bạn có thể tạo PDF có cấu trúc tốt với dấu trang cha và dấu trang con, tùy chỉnh giao diện của chúng và thậm chí thêm các hành động để nâng cao trải nghiệm của người dùng.

## Câu hỏi thường gặp

### Làm thế nào tôi có thể tải xuống Aspose.PDF cho Java?

 Bạn có thể tải xuống Aspose.PDF cho Java từ trang web[đây](https://releases.aspose.com/pdf/java/).

### Có hỗ trợ dấu trang con trong tất cả các trình xem PDF không?

Có, hầu hết các trình xem PDF hiện đại đều hỗ trợ dấu trang con và mang đến trải nghiệm nâng cao cho người dùng khi duyệt qua các tài liệu PDF.

### Tôi có thể tùy chỉnh thêm giao diện của dấu trang không?

Có, bạn có thể tùy chỉnh giao diện của dấu trang bằng cách điều chỉnh kiểu văn bản, màu sắc và biểu tượng cho phù hợp với thiết kế tài liệu.

### Tôi có thể thêm những hành động nào khác vào dấu trang?

Bên cạnh hành động "GoTo", bạn có thể thêm các hành động như hành động "URI" để mở liên kết web hoặc hành động "JavaScript" để thực thi các tập lệnh tùy chỉnh khi nhấp vào dấu trang.

### Aspose.PDF cho Java có phù hợp cho các dự án thương mại không?

Có, Aspose.PDF for Java phù hợp cho cả dự án cá nhân và thương mại, và cung cấp nhiều tính năng để tạo và chỉnh sửa PDF.