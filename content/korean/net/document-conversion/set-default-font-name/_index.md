---
title: 기본 글꼴 이름 설정
linktitle: 기본 글꼴 이름 설정
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 기본 글꼴 이름을 설정하는 단계별 가이드입니다.
type: docs
weight: 270
url: /ko/net/document-conversion/set-default-font-name/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에서 기본 글꼴 이름을 설정하는 방법을 보여줍니다. 가끔 PDF 파일에서 이미지를 추출할 때 글꼴 누락 문제가 발생할 수 있습니다. 기본 글꼴 이름을 지정하면 추출된 텍스트가 올바르게 표시되는지 확인할 수 있습니다. PDF 파일의 기본 글꼴 이름을 설정하려면 아래 단계를 따르세요.

## 전제조건
시작하기 전에 다음 전제 조건을 충족하는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- 시스템에 설치된 .NET용 Aspose.PDF 라이브러리.
- Visual Studio와 같은 개발 환경.

## 1단계: PDF 문서 로드
 첫 번째 단계는 PDF 문서를`Document` 물체. 다음 코드를 사용하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // 추가할 코드
}
```

 꼭 교체하세요`"YOUR DOCUMENTS DIRECTORY"` PDF 파일이 있는 실제 디렉토리를 사용하세요.

## 2단계: 기본 글꼴 이름 설정
 다음으로, 다음을 사용하여 기본 글꼴 이름을 설정하겠습니다.`DefaultFontName` 의 옵션`RenderingOptions` 물체. 다음 코드를 사용하세요.

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // 추가할 코드
     }
}
```

 꼭 교체하세요`"Arial"` 원하는 글꼴 이름으로

## 3단계: 이미지 추출
다음으로 PDF 문서의 지정된 페이지에서 이미지를 추출하겠습니다. 다음 코드를 사용하세요.

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 올바른 페이지 번호를 지정하십시오.`pdfDocument.Pages[1]`.

### .NET용 Aspose.PDF를 사용하여 기본 글꼴 이름 설정에 대한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일에서 기본 글꼴 이름을 설정하는 방법을 배웠습니다. 기본 글꼴 이름을 지정하면 추출된 텍스트가 올바르게 표시되는지 확인할 수 있습니다. PDF 파일에서 이미지를 추출할 때 누락된 글꼴 문제를 해결하려면 이 방법을 사용하십시오.

### FAQ

#### Q: .NET용 Aspose.PDF이 무엇인가요?

A: .NET용 Aspose.PDF는 개발자가 C# 애플리케이션에서 PDF 문서 작업을 할 수 있게 해주는 강력한 라이브러리입니다. PDF 파일의 기본 글꼴 이름 설정을 포함하여 다양한 기능을 제공합니다.

#### Q: PDF 파일에서 기본 글꼴 이름을 설정해야 하는 이유는 무엇입니까?

A: 기본 글꼴 이름을 설정하는 것은 PDF 문서에서 텍스트를 추출할 때 유용합니다. PDF에 추출 시스템에서 사용할 수 없는 글꼴이 포함된 텍스트가 포함되어 있는 경우 기본 글꼴 이름을 지정하면 텍스트가 올바르게 표시됩니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서를 로드하고 기본 글꼴 이름을 설정하려면 어떻게 해야 합니까?

 A: PDF 문서를 로드하고 기본 글꼴 이름을 설정하려면 다음을 사용할 수 있습니다.`Document`PDF 파일을 로드하는 클래스와`RenderingOptions.DefaultFontName` 원하는 기본 글꼴 이름을 지정하는 속성입니다.

#### Q: 어떤 글꼴이든 기본 글꼴 이름으로 선택할 수 있나요?

A:예, 추출 시스템에서 사용 가능한 모든 글꼴을 기본 글꼴 이름으로 선택할 수 있습니다. 정확한 텍스트 렌더링을 보장하려면 원본 PDF에서 누락된 글꼴과 거의 일치하는 글꼴을 사용하십시오.

#### Q: 기본 글꼴 이름을 설정하면 PDF 파일이 영구적으로 변경됩니까?

A: 아니요. .NET용 Aspose.PDF를 사용하여 기본 글꼴 이름을 설정하는 것은 텍스트 추출 중에 일시적으로 변경된 것입니다. 원본 PDF 파일은 수정되지 않습니다.