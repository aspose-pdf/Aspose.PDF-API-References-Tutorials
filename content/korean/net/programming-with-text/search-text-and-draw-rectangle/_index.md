---
title: 텍스트 검색 및 직사각형 그리기
linktitle: 텍스트 검색 및 직사각형 그리기
second_title: .NET API 참조용 Aspose.PDF
description: PDF에서 텍스트를 검색하고, 발견된 텍스트 주위에 직사각형을 그리고, .NET용 Aspose.PDF를 사용하여 수정된 문서를 저장하는 방법을 알아보세요.
type: docs
weight: 460
url: /ko/net/programming-with-text/search-text-and-draw-rectangle/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 특정 텍스트를 검색하고, 발견된 텍스트 주위에 직사각형을 그리고, 수정된 문서를 저장하는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## 3단계: 문서 디렉터리 경로 설정

 다음을 사용하여 문서 디렉토리의 경로를 설정하십시오.`dataDir` 변하기 쉬운:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

## 4단계: PDF 문서 로드

 다음을 사용하여 PDF 문서를 로드합니다.`Document` 수업:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 바꾸다`"SearchAndGetTextFromAll.pdf"` PDF 파일의 실제 이름으로.

## 5단계: TextFragmentAbsorber 만들기

 만들기`TextFragmentAbsorber` 입력 검색 문구의 모든 인스턴스를 찾는 개체:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 바꾸다`@"[\S]+"` 원하는 정규식 패턴으로.

## 6단계: 정규식 검색 활성화

 다음을 설정하여 정규식 검색을 활성화합니다.`TextSearchOptions` 흡수체의 특성:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## 7단계: 모든 페이지에서 검색

문서의 모든 페이지에 대해 흡수체를 적용합니다.

```csharp
document.Pages.Accept(textAbsorber);
```

## 8단계: 찾은 텍스트 주위에 직사각형 그리기

 만들기`PdfContentEditor` 객체를 생성하고 검색된 텍스트 조각을 반복하여 각 텍스트 세그먼트 주위에 직사각형을 그립니다.

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## 9단계: 수정된 문서 저장

수정된 문서를 저장합니다.

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 꼭 교체하세요`"SearchTextAndDrawRectangle_out.pdf"` 원하는 출력 파일 이름으로.

### .NET용 Aspose.PDF를 사용하여 텍스트 검색 및 직사각형 그리기의 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// 정규식과 일치하는 모든 구문을 찾기 위해 TextAbsorber 개체를 만듭니다.
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## 결론

축하해요! PDF 문서에서 특정 텍스트를 검색하고, 발견된 텍스트 주위에 직사각형을 그리고, .NET용 Aspose.PDF를 사용하여 수정된 문서를 저장하는 방법을 성공적으로 배웠습니다. 이 튜토리얼에서는 프로젝트 설정부터 필요한 작업 수행까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일에서 텍스트를 조작하고 직사각형을 그릴 수 있습니다.

### FAQ

#### Q: "텍스트 검색 및 직사각형 그리기" 튜토리얼의 목적은 무엇입니까?

A: "텍스트 검색 및 직사각형 그리기" 튜토리얼의 목적은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서 내의 특정 텍스트를 검색하고, 발견된 텍스트 세그먼트 주위에 직사각형을 그리고, 수정된 텍스트를 저장하는 과정을 사용자에게 안내하는 것입니다. 문서. 이 자습서에서는 프로세스의 각 단계를 설명하기 위한 자세한 지침과 C# 코드 샘플을 제공합니다.

#### 질문: 이 튜토리얼은 PDF 문서의 특정 텍스트 주위에 직사각형을 그리는 데 어떻게 도움이 됩니까?

답변: 이 튜토리얼은 PDF 문서 내의 특정 텍스트 세그먼트 주위에 직사각형을 찾고 그리는 방법에 대한 포괄적인 가이드를 제공합니다. 프로젝트 설정, PDF 문서 로드, 정규식 검색 활성화, 발견된 텍스트 세그먼트 주위에 직사각형 그리기 및 수정된 PDF 저장 프로세스를 보여줍니다.

#### Q: 이 튜토리얼을 따르려면 어떤 전제 조건이 필요합니까?

A: 자습서를 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있어야 합니다. 또한 .NET용 Aspose.PDF 라이브러리가 설치되어 있어야 합니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

#### Q: 이 튜토리얼을 따르려면 프로젝트를 어떻게 설정해야 합니까?

A: 선호하는 IDE(통합 개발 환경)에서 새 C# 프로젝트를 만드는 것부터 시작하세요. 그런 다음 .NET용 Aspose.PDF 라이브러리에 대한 참조를 프로젝트에 추가합니다. 이렇게 하면 라이브러리의 기능을 사용하여 PDF 문서를 조작할 수 있습니다.

#### Q: 이 튜토리얼을 사용하여 특정 텍스트 주위에 직사각형을 그릴 수 있습니까?

A: 예, 이 튜토리얼은 PDF 문서 내의 특정 텍스트 세그먼트 주위에 직사각형을 그리는 데 중점을 둡니다. 정규식을 사용하여 원하는 텍스트를 찾고, 식별된 텍스트 세그먼트 주위에 직사각형을 만들고, 수정된 PDF를 저장하는 방법을 보여줍니다.

#### Q: 검색하려는 텍스트를 지정하고 주위에 직사각형을 그리려면 어떻게 해야 합니까?

 A: 검색하려는 텍스트를 지정하고 주위에 직사각형을 그리려면`TextFragmentAbsorber` 객체를 선택하고 다음을 사용하여 패턴을 설정합니다.`Text` 매개변수. 기본 패턴 바꾸기`@"[\S]+"` 튜토리얼의 코드에서 원하는 정규식 패턴을 사용하세요.

#### Q: 텍스트에 대한 정규식 검색을 활성화하려면 어떻게 해야 합니까?

 A: 정규식 검색은`TextSearchOptions` 개체를 설정하고 해당 값을 다음으로 설정합니다.`true` . 이 개체를`TextSearchOptions` 의 재산`TextFragmentAbsorber` 사례. 이렇게 하면 텍스트 검색 중에 정규식 패턴이 사용됩니다.

#### Q: 찾은 텍스트 주위에 직사각형을 그리려면 어떻게 해야 합니까?

 A: 다음을 사용하여 텍스트 세그먼트를 식별한 후`TextFragmentAbsorber` , 튜토리얼에서는 이러한 세그먼트를 반복하는 루프를 제공합니다. 각 텍스트 세그먼트에 대해 튜토리얼에서는 다음을 사용하여 텍스트 세그먼트 주위에 직사각형을 만드는 방법을 보여줍니다.`DrawBox` 메서드를 사용하여 직사각형의 모양을 지정합니다.

#### Q: 수정된 PDF를 그려진 직사각형과 함께 저장하는 단계는 무엇입니까?

A: 원하는 텍스트 세그먼트 주위에 직사각형을 그린 후`Document` 수업의`Save` 수정된 문서를 저장하는 방법입니다. 튜토리얼의 샘플 코드는 편집된 PDF를 저장하고 성공 메시지를 표시하는 방법을 보여줍니다.

#### Q: 그려진 직사각형의 모양을 사용자 정의할 수 있나요?

 A: 예, 그려진 직사각형의 모양을 사용자 정의할 수 있습니다. 튜토리얼의 샘플 코드에서는`DrawBox` 메서드를 사용하여 직사각형을 만듭니다. 색상, 스타일, 두께 등의 속성을 수정하여 그려진 직사각형의 모양을 사용자 정의할 수 있습니다.