---
title: Gợi ý phông chữ PDF sang PNG
linktitle: Gợi ý phông chữ PDF sang PNG
second_title: Aspose.PDF cho tài liệu tham khảo API .NET
description: Hướng dẫn từng bước để chuyển đổi PDF sang PNG kèm theo gợi ý phông chữ bằng Aspose.PDF cho .NET.
type: docs
weight: 160
url: /vi/net/document-conversion/pdf-to-png-font-hinting/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình chuyển đổi hình ảnh PDF sang PNG bằng Aspose.PDF cho .NET, đồng thời bật tính năng gợi ý phông chữ. Gợi ý phông chữ là một kỹ thuật giúp cải thiện khả năng đọc của phông chữ nhỏ. Bằng cách làm theo các bước bên dưới, bạn sẽ có thể chuyển đổi mọi trang của PDF thành hình ảnh PNG kèm theo gợi ý phông chữ.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Thư viện Aspose.PDF cho .NET được cài đặt trên hệ thống của bạn.
- Một môi trường phát triển như Visual Studio.

## Bước 1: Mở tài liệu PDF nguồn
Trong bước này, chúng tôi sẽ mở tệp PDF nguồn bằng Aspose.PDF cho .NET. Thực hiện theo mã dưới đây:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Mở tài liệu
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Hãy chắc chắn để thay thế`"YOUR DOCUMENTS DIRECTORY"` với thư mục thực tế nơi chứa tệp PDF của bạn.

## Bước 2: Bật gợi ý phông chữ
Sau khi mở tệp PDF, chúng tôi sẽ bật gợi ý phông chữ bằng cách sử dụng các tùy chọn kết xuất. Sử dụng mã sau đây:

```csharp
// Tạo tùy chọn kết xuất để bật gợi ý phông chữ
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## Bước 3: Chuyển đổi sang hình ảnh PNG
Bây giờ chúng ta sẽ chuyển đổi từng trang PDF thành hình ảnh PNG kèm theo gợi ý phông chữ. Sử dụng mã sau đây:

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Tạo một đối tượng PNGDevice với các thuộc tính được chỉ định
         // Chiều rộng, chiều cao, độ phân giải, chất lượng
         // Chất lượng [0-100], 100 là tối đa
         // Tạo đối tượng Độ phân giải
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         // Đặt tùy chọn hiển thị được xác định trước
         pngDevice.RenderingOptions = opts;

         // Chuyển đổi một trang cụ thể và lưu hình ảnh vào luồng
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         // Đóng luồng
         imageStream.Close();
     }
}
```

Đoạn mã trên chuyển đổi từng trang PDF thành hình ảnh PNG kèm theo gợi ý phông chữ và lưu từng hình ảnh dưới dạng tệp PNG riêng biệt.

### Mã nguồn mẫu cho PDF sang PNGFont Gợi ý sử dụng Aspose.PDF for .NET

```csharp
try
{
	
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Mở tài liệu
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Tạo Aspose.Pdf.RenderingOptions để bật gợi ý phông chữ
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
		{
			// Tạo thiết bị PNG với các thuộc tính được chỉ định
			// Chiều rộng, chiều cao, độ phân giải, chất lượng
			// Chất lượng [0-100], 100 là tối đa
			// Tạo đối tượng Độ phân giải
			Resolution resolution = new Resolution(300);
			PngDevice pngDevice = new PngDevice(resolution);
			// Đặt tùy chọn hiển thị được xác định trước
			pngDevice.RenderingOptions = opts;

			//Chuyển đổi một trang cụ thể và lưu hình ảnh vào luồng
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			// Đóng luồng
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày quy trình từng bước chuyển đổi hình ảnh PDF sang PNG với gợi ý phông chữ bằng Aspose.PDF cho .NET. Bằng cách làm theo các hướng dẫn được nêu ở trên, giờ đây bạn có thể chuyển đổi mọi trang của tệp PDF thành hình ảnh PNG kèm theo gợi ý phông chữ. Tính năng này hữu ích khi bạn muốn duy trì khả năng đọc của phông chữ nhỏ khi chuyển đổi sang hình ảnh PNG.

### Câu hỏi thường gặp

#### Hỏi: Gợi ý phông chữ là gì và tại sao nó lại quan trọng khi chuyển đổi PDF sang PNG?

Đáp: Gợi ý phông chữ là một kỹ thuật được sử dụng để cải thiện khả năng đọc của phông chữ nhỏ bằng cách điều chỉnh hình dạng và vị trí của chúng. Khi chuyển đổi hình ảnh PDF sang PNG, việc bật gợi ý phông chữ sẽ đảm bảo rằng văn bản trong hình ảnh PNG thu được vẫn dễ đọc và rõ ràng, đặc biệt đối với kích thước phông chữ nhỏ. Điều này rất quan trọng để duy trì chất lượng và khả năng đọc văn bản khi chuyển đổi tài liệu PDF sang hình ảnh.

#### Câu hỏi: Gợi ý phông chữ ảnh hưởng như thế nào đến quá trình chuyển đổi PNG?

Đáp: Gợi ý phông chữ ảnh hưởng đến cách hiển thị văn bản trong hình ảnh PNG thu được trong quá trình chuyển đổi PDF sang PNG. Bằng cách bật gợi ý phông chữ, thư viện Aspose.PDF điều chỉnh kết xuất phông chữ để đảm bảo rằng các phông chữ nhỏ vẫn rõ ràng và dễ đọc, làm cho hình ảnh PNG trở nên hấp dẫn và dễ đọc hơn.

#### H: Tôi có thể điều chỉnh cài đặt gợi ý phông chữ để tùy chỉnh chuyển đổi PNG không?

 Trả lời: Có, thư viện Aspose.PDF for .NET cung cấp các tùy chọn để tùy chỉnh quy trình chuyển đổi PNG, bao gồm cài đặt gợi ý phông chữ. Trong ví dụ mã được cung cấp,`UseFontHinting` tài sản của`RenderingOptions` đối tượng được đặt thành`true` để bật gợi ý phông chữ. Bạn có thể tinh chỉnh thêm quá trình chuyển đổi bằng cách điều chỉnh các thuộc tính khác trong`RenderingOptions` lớp học theo yêu cầu của bạn.

#### Hỏi: Hình ảnh PNG được lưu trong quá trình chuyển đổi PNG như thế nào?

Đáp: Trong ví dụ về mã được cung cấp, mỗi trang của tài liệu PDF được chuyển đổi thành một hình ảnh PNG riêng biệt. Hình ảnh PNG được lưu dưới dạng tệp riêng lẻ với tên tệp theo mẫu "hình ảnh{pageCount}_ out.png", ở đâu`{pageCount}` là số trang đang được chuyển đổi. Mỗi hình ảnh PNG đại diện cho một trang của tài liệu PDF gốc.