---
title: PDF 파일에서 줄 간격 지정
linktitle: PDF 파일에서 줄 간격 지정
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에서 줄 간격을 지정하는 방법을 알아보세요.
type: docs
weight: 510
url: /ko/net/programming-with-text/specify-line-spacing/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일에서 줄 간격을 지정하는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

## 전제조건

튜토리얼을 진행하기 전에 다음 사항을 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- .NET 라이브러리용 Aspose.PDF가 설치되었습니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

## 1단계: 프로젝트 설정

선호하는 IDE(통합 개발 환경)에서 새 C# 프로젝트를 생성하고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하는 것으로 시작하세요.

## 2단계: 필요한 네임스페이스 가져오기

필수 네임스페이스를 가져오려면 C# 파일 시작 부분에 다음 using 지시문을 추가하세요.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## 3단계: 문서 디렉터리 경로 설정

 다음을 사용하여 문서 디렉토리의 경로를 설정하십시오.`dataDir` 변하기 쉬운:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

## 4단계: 입력 PDF 파일 로드

 다음을 사용하여 입력 PDF 파일을 로드합니다.`Document` 수업:

```csharp
Document doc = new Document();
```

## 5단계: TextFormattingOptions 생성

 만들기`TextFormattingOptions` 개체를 선택하고 줄 간격 모드를 다음으로 설정합니다.`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## 6단계: TextFragment 만들기

 만들기`TextFragment` 객체를 선택하고 텍스트 내용을 지정합니다.

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## 7단계: 글꼴 파일 로드(선택 사항)

 텍스트에 특정 글꼴을 사용하려면 트루타입 글꼴 파일을`FileStream` 물체:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 바꾸다`"HPSimplified.TTF"` 실제 글꼴 파일 이름으로.

## 8단계: 텍스트 위치 및 줄 간격 지정

 텍스트 조각의 위치를 설정하고`TextFormattingOptions` ~로`TextState.FormattingOptions` 재산:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## 9단계: 문서에 텍스트 추가

 텍스트 조각을 문서에 추가하거나`TextBuilder` 또는 페이지로 직접 이동`Paragraphs` 수집:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## 10단계: 결과 PDF 문서 저장

수정된 PDF 문서를 저장합니다.

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 꼭 교체하세요`"SpecifyLineSpacing_out.pdf"` 원하는 출력 파일 이름으로.

### .NET용 Aspose.PDF를 사용하여 줄 간격 지정에 대한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// 입력 PDF 파일 로드
Document doc = new Document();
//LineSpacingMode.FullSize를 사용하여 TextFormattingOptions 만들기
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// 문서의 첫 번째 페이지에 대한 텍스트 작성기 개체 만들기
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// 샘플 문자열로 텍스트 조각 만들기
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// 트루타입 글꼴을 스트림 개체에 로드
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		//텍스트 문자열의 글꼴 이름을 설정합니다.
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// 텍스트 조각의 위치 지정
		textFragment.Position = new Position(100, 600);
		//현재 조각의 TextFormattingOptions를 미리 정의된 항목으로 설정합니다(LineSpacingMode.FullSize를 가리킴).
		textFragment.TextState.FormattingOptions = formattingOptions;
		// PDF 파일 위에 배치할 수 있도록 TextBuilder에 텍스트를 추가합니다.
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// 결과 PDF 문서 저장
	doc.Save(dataDir);
}
```

## 결론

축하해요! .NET용 Aspose.PDF를 사용하여 PDF 문서에서 줄 간격을 지정하는 방법을 성공적으로 배웠습니다. 이 튜토리얼에서는 프로젝트 설정부터 수정된 문서 저장까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일의 텍스트 줄 간격을 사용자 지정할 수 있습니다.

### FAQ

#### Q: "PDF 파일에서 줄 간격 지정" 튜토리얼의 목적은 무엇입니까?

A: "PDF 파일에서 줄 간격 지정" 튜토리얼의 목적은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서 내 텍스트의 줄 간격을 사용자 지정하는 방법을 사용자에게 안내하는 것입니다. 이 자습서에서는 프로세스를 보여주기 위한 단계별 지침과 C# 코드 샘플을 제공합니다.

#### 질문: 이 튜토리얼은 PDF 문서 내에서 줄 간격을 지정하는 데 어떻게 도움이 됩니까?

A: 이 튜토리얼은 사용자가 .NET용 Aspose.PDF의 기능을 활용하여 PDF 문서의 텍스트 줄 간격을 지정하는 방법을 이해하는 데 도움이 됩니다. 제공된 단계와 코드 예제를 따르면 사용자는 원하는 대로 줄 간격을 조정할 수 있습니다.

#### Q: 이 튜토리얼을 따르려면 어떤 전제 조건이 필요합니까?

A: 자습서를 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있어야 합니다. 또한 .NET용 Aspose.PDF 라이브러리가 설치되어 있어야 합니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

#### Q: 이 튜토리얼을 따르려면 프로젝트를 어떻게 설정해야 합니까?

A: 시작하려면 선호하는 IDE(통합 개발 환경)에서 새 C# 프로젝트를 만들고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하세요. 이를 통해 PDF 문서 작업 및 줄 간격 사용자 정의를 위한 라이브러리 기능을 활용할 수 있습니다.

#### Q: 이 튜토리얼을 사용하여 모든 유형의 텍스트에 대한 줄 간격을 지정할 수 있습니까?

A: 예, 이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서 내 텍스트 내용의 줄 간격을 지정하는 방법에 대한 지침을 제공합니다. 제공된 코드 샘플을 사용하여 필요에 따라 텍스트의 줄 간격을 조정할 수 있습니다.

#### Q: 튜토리얼에서 줄 간격 모드를 어떻게 지정합니까?

 A: 튜토리얼에서는`TextFormattingOptions` 개체를 설정하고`LineSpacing` 재산`TextFormattingOptions.LineSpacingMode.FullSize`. 이 모드는 텍스트 내용의 전체 줄 간격을 지정합니다.

#### Q: 텍스트에 특정 글꼴을 로드하려면 어떻게 해야 합니까?

 A: 텍스트 내용에 특정 글꼴을 사용하려는 경우 튜토리얼에서는 트루타입 글꼴 파일을 텍스트 콘텐츠에 로드하는 방법에 대한 지침을 제공합니다.`FileStream` 개체에 대한 글꼴로 설정합니다.`TextFragment`. 이를 통해 줄 간격과 함께 텍스트 글꼴을 사용자 정의할 수 있습니다.

#### Q: PDF 문서 내 텍스트 위치를 어떻게 사용자 정의합니까?

 A: 텍스트 위치를 사용자 정의하려면`TextFragment` 개체를 설정하고`Position`속성을 원하는 좌표(X 및 Y)로 설정합니다. 이를 통해 PDF 문서 내에서 텍스트가 배치되는 위치를 제어할 수 있습니다.

#### Q: 기존 PDF 문서에 이러한 줄 간격 수정 사항을 적용할 수 있습니까?

 A: 예, 기존 PDF 문서에서 텍스트의 줄 간격을 수정할 수 있습니다. 튜토리얼에서는`TextFragment` 지정된 줄 간격과 위치로 페이지의`Paragraphs` 수집.