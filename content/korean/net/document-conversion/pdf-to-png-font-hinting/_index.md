---
title: PDF를 PNG 글꼴 힌트로 변환
linktitle: PDF를 PNG 글꼴 힌트로 변환
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 글꼴 힌트를 사용하여 PDF를 PNG로 변환하는 단계별 가이드입니다.
type: docs
weight: 160
url: /ko/net/document-conversion/pdf-to-png-font-hinting/
---
이 튜토리얼에서는 글꼴 힌트를 활성화하면서 .NET용 Aspose.PDF를 사용하여 PDF를 PNG 이미지로 변환하는 과정을 안내합니다. 글꼴 힌트는 작은 글꼴의 가독성을 향상시키는 기술입니다. 아래 단계를 따르면 PDF의 모든 페이지를 글꼴 힌트가 포함된 PNG 이미지로 변환할 수 있습니다.

## 전제조건
시작하기 전에 다음 전제 조건을 충족하는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- 시스템에 설치된 .NET용 Aspose.PDF 라이브러리.
- Visual Studio와 같은 개발 환경.

## 1단계: 소스 PDF 문서 열기
이 단계에서는 .NET용 Aspose.PDF를 사용하여 소스 PDF 파일을 엽니다. 아래 코드를 따르십시오.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 꼭 교체하세요`"YOUR DOCUMENTS DIRECTORY"` PDF 파일이 있는 실제 디렉토리를 사용하세요.

## 2단계: 글꼴 힌트 활성화
PDF 파일을 연 후 렌더링 옵션을 사용하여 글꼴 힌트를 활성화합니다. 다음 코드를 사용하세요.

```csharp
// 글꼴 힌트를 활성화하는 렌더링 옵션 만들기
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## 3단계: PNG 이미지로 변환
이제 PDF의 각 페이지를 글꼴 힌트를 사용하여 PNG 이미지로 변환하겠습니다. 다음 코드를 사용하세요.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // 지정된 속성을 가진 PNGDevice 객체 생성
         // 너비, 높이, 해상도, 품질
         // 품질 [0-100], 100이 최대값입니다.
         // 해결 개체 만들기
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         // 사전 정의된 렌더링 옵션 설정
         pngDevice.RenderingOptions = opts;

         // 특정 페이지를 변환하고 이미지를 스트림에 저장
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         // 스트림 닫기
         imageStream.Close();
     }
}
```

위의 코드는 PDF의 각 페이지를 글꼴 힌트가 포함된 PNG 이미지로 변환하고 각 이미지를 별도의 PNG 파일로 저장합니다.

### .NET용 Aspose.PDF를 사용하여 PDF에서 PNGFont로의 힌트를 제공하는 예제 소스 코드

```csharp
try
{
	
	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// 문서 열기
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Aspose.Pdf.RenderingOptions를 생성하여 글꼴 힌트 활성화
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
		{
			// 지정된 속성을 사용하여 PNG 장치 생성
			// 너비, 높이, 해상도, 품질
			// 품질 [0-100], 100이 최대값입니다.
			// 해결 객체 생성
			Resolution resolution = new Resolution(300);
			PngDevice pngDevice = new PngDevice(resolution);
			// 사전 정의된 렌더링 옵션 설정
			pngDevice.RenderingOptions = opts;

			//특정 페이지를 변환하고 이미지를 스트리밍에 저장
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			// 스트림 닫기
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 글꼴 힌트를 사용하여 PDF를 PNG 이미지로 변환하는 단계별 프로세스를 다루었습니다. 위에 설명된 지침을 따르면 이제 PDF의 모든 페이지를 글꼴 힌트가 포함된 PNG 이미지로 변환할 수 있습니다. 이 기능은 PNG 이미지로 변환할 때 작은 글꼴의 가독성을 유지하려는 경우에 유용합니다.

### FAQ

#### Q: 글꼴 힌트란 무엇이며, PDF를 PNG로 변환할 때 글꼴 힌트가 중요한 이유는 무엇입니까?

A: 글꼴 힌트는 모양과 위치를 조정하여 작은 글꼴의 가독성을 향상시키는 데 사용되는 기술입니다. PDF를 PNG 이미지로 변환할 때 글꼴 힌트를 활성화하면 특히 작은 글꼴 크기의 경우 결과 PNG 이미지의 텍스트를 읽기 쉽고 명확하게 유지할 수 있습니다. 이는 PDF 문서를 이미지로 변환할 때 텍스트의 품질과 가독성을 유지하는 데 중요합니다.

#### Q: 글꼴 힌트는 PNG 변환 프로세스에 어떤 영향을 줍니까?

A: 글꼴 힌트는 PDF에서 PNG로의 변환 프로세스 중에 결과 PNG 이미지에서 텍스트가 렌더링되는 방식에 영향을 줍니다. Aspose.PDF 라이브러리는 글꼴 힌트를 활성화하여 작은 글꼴의 선명도와 가독성을 유지하도록 글꼴 렌더링을 조정하여 PNG 이미지를 시각적으로 더욱 매력적이고 읽기 쉽게 만듭니다.

#### Q: PNG 변환을 사용자 정의하기 위해 글꼴 힌트 설정을 조정할 수 있습니까?

 A: 예, .NET용 Aspose.PDF 라이브러리는 글꼴 힌트 설정을 포함하여 PNG 변환 프로세스를 사용자 정의하는 옵션을 제공합니다. 제공된 코드 예제에서는`UseFontHinting` 의 재산`RenderingOptions` 개체가 다음으로 설정되었습니다.`true` 글꼴 힌트를 활성화합니다. 다음에서 다른 속성을 조정하여 변환 프로세스를 더욱 세부적으로 조정할 수 있습니다.`RenderingOptions` 귀하의 요구 사항에 따라 수업.

#### Q: PNG 변환 과정에서 PNG 이미지는 어떻게 저장되나요?

A: 제공된 코드 예제에서 PDF 문서의 각 페이지는 별도의 PNG 이미지로 변환됩니다. PNG 이미지는 "image" 패턴을 따르는 파일 이름을 가진 개별 파일로 저장됩니다.{pageCount}_ out.png", 여기서`{pageCount}` 변환되는 페이지의 번호입니다. 각 PNG 이미지는 원본 PDF 문서의 한 페이지를 나타냅니다.