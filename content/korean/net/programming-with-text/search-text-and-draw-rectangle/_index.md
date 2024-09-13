---
title: 텍스트 검색 및 사각형 그리기
linktitle: 텍스트 검색 및 사각형 그리기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF에서 텍스트를 검색하고, 찾은 텍스트 주위에 사각형을 그린 다음, 수정된 문서를 저장하는 방법을 알아보세요.
type: docs
weight: 460
url: /ko/net/programming-with-text/search-text-and-draw-rectangle/
---
이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 문서에서 특정 텍스트를 검색하고, 찾은 텍스트 주위에 사각형을 그리고, 수정된 문서를 저장하는 방법을 설명합니다. 제공된 C# 소스 코드는 단계별로 프로세스를 보여줍니다.

## 필수 조건

튜토리얼을 진행하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- .NET 라이브러리용 Aspose.PDF가 설치되었습니다. Aspose 웹사이트에서 얻을 수 있거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

## 1단계: 프로젝트 설정

선호하는 통합 개발 환경(IDE)에서 새 C# 프로젝트를 만들고 .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필요한 네임스페이스 가져오기

필요한 네임스페이스를 가져오려면 C# 파일의 시작 부분에 다음 using 지시문을 추가합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## 3단계: 문서 디렉토리 경로 설정

 다음을 사용하여 문서 디렉토리 경로를 설정하세요.`dataDir` 변하기 쉬운:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 포함합니다.

## 4단계: PDF 문서 로드

 PDF 문서를 로드하려면 다음을 사용합니다.`Document` 수업:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 바꾸다`"SearchAndGetTextFromAll.pdf"` PDF 파일의 실제 이름을 입력하세요.

## 5단계: TextFragmentAbsorber 만들기

 생성하다`TextFragmentAbsorber` 입력 검색어의 모든 인스턴스를 찾는 객체:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 바꾸다`@"[\S]+"` 원하는 정규 표현식 패턴을 사용합니다.

## 6단계: 정규 표현식 검색 활성화

 정규 표현식 검색을 활성화하려면 다음을 설정하세요.`TextSearchOptions` 흡수체의 속성:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## 7단계: 모든 페이지에서 검색

문서의 모든 페이지에 대한 흡수체를 수락합니다.

```csharp
document.Pages.Accept(textAbsorber);
```

## 8단계: 찾은 텍스트 주위에 사각형을 그립니다.

 생성하다`PdfContentEditor` 객체를 만들고 검색된 텍스트 조각을 반복하면서 각 텍스트 세그먼트 주위에 사각형을 그립니다.

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

 교체를 꼭 해주세요`"SearchTextAndDrawRectangle_out.pdf"` 원하는 출력 파일 이름을 입력합니다.

### .NET용 Aspose.PDF를 사용하여 텍스트 검색 및 사각형 그리기를 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//정규 표현식과 일치하는 모든 구문을 찾기 위해 TextAbsorber 객체를 생성합니다.
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

축하합니다! PDF 문서에서 특정 텍스트를 검색하고, 찾은 텍스트 주위에 사각형을 그리고, Aspose.PDF for .NET을 사용하여 수정된 문서를 저장하는 방법을 성공적으로 배웠습니다. 이 튜토리얼은 프로젝트 설정부터 필요한 작업 수행까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일에서 텍스트를 조작하고 사각형을 그릴 수 있습니다.

### 자주 묻는 질문

#### 질문: "텍스트 검색 및 사각형 그리기" 튜토리얼의 목적은 무엇인가요?

A: "텍스트 검색 및 사각형 그리기" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서 내에서 특정 텍스트를 검색하고, 찾은 텍스트 세그먼트 주위에 사각형을 그리며, 수정된 문서를 저장하는 과정을 사용자에게 안내하는 것을 목표로 합니다. 이 튜토리얼은 프로세스의 각 단계를 설명하는 자세한 지침과 C# 코드 샘플을 제공합니다.

#### 질문: 이 튜토리얼은 PDF 문서의 특정 텍스트 주위에 사각형을 그리는 데 어떻게 도움이 되나요?

A: 이 튜토리얼은 PDF 문서 내의 특정 텍스트 세그먼트를 찾아 그 주위에 사각형을 그리는 방법에 대한 포괄적인 가이드를 제공합니다. 프로젝트 설정, PDF 문서 로드, 정규 표현식 검색 활성화, 찾은 텍스트 세그먼트 주위에 사각형 그리기, 수정된 PDF 저장 과정을 보여줍니다.

#### 질문: 이 튜토리얼을 따르려면 어떤 전제 조건이 필요합니까?

A: 튜토리얼을 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있어야 합니다. 또한 Aspose.PDF for .NET 라이브러리를 설치해야 합니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

#### 질문: 이 튜토리얼을 따르려면 프로젝트를 어떻게 설정해야 하나요?

A: 선호하는 통합 개발 환경(IDE)에서 새 C# 프로젝트를 만드는 것으로 시작합니다. 그런 다음 Aspose.PDF for .NET 라이브러리에 대한 참조를 프로젝트에 추가합니다. 이렇게 하면 라이브러리의 기능을 사용하여 PDF 문서를 조작할 수 있습니다.

#### 질문: 이 튜토리얼을 사용하여 특정 텍스트 주위에 사각형을 그릴 수 있나요?

A: 네, 이 튜토리얼은 PDF 문서 내의 특정 텍스트 세그먼트 주위에 사각형을 그리는 데 중점을 둡니다. 정규 표현식을 사용하여 원하는 텍스트를 찾고, 식별된 텍스트 세그먼트 주위에 사각형을 만들고, 수정된 PDF를 저장하는 방법을 보여줍니다.

#### 질문: 검색하고 싶은 텍스트를 지정해서 그 주위에 사각형을 그리려면 어떻게 해야 하나요?

 A: 검색하고 싶은 텍스트를 지정하고 그 주위에 사각형을 그리려면 다음을 만듭니다.`TextFragmentAbsorber` 객체를 만들고 패턴을 설정합니다.`Text` 매개변수. 기본 패턴을 대체합니다.`@"[\S]+"` 튜토리얼의 코드에 원하는 정규 표현식 패턴을 추가합니다.

#### 질문: 텍스트에 대한 정규 표현식 검색을 활성화하려면 어떻게 해야 하나요?

 A: 정규 표현식 검색은 다음을 생성하여 활성화됩니다.`TextSearchOptions` 객체를 만들고 값을 설정합니다.`true` . 이 객체를 다음에 할당합니다.`TextSearchOptions` 의 속성`TextFragmentAbsorber` 인스턴스. 이렇게 하면 텍스트 검색 중에 정규 표현식 패턴이 사용됩니다.

#### 질문: 찾은 텍스트 주위에 사각형을 그리려면 어떻게 해야 하나요?

 A: 텍스트 세그먼트를 식별한 후`TextFragmentAbsorber` , 이 튜토리얼은 이러한 세그먼트를 반복하는 루프를 제공합니다. 각 텍스트 세그먼트에 대해 이 튜토리얼은 다음을 사용하여 그 주위에 사각형을 만드는 방법을 보여줍니다.`DrawBox` 방법을 선택하고 사각형의 모양을 지정합니다.

#### 질문: 그려진 사각형이 있는 수정된 PDF를 저장하는 단계는 무엇입니까?

A: 원하는 텍스트 세그먼트 주위에 사각형을 그린 후 다음을 사용합니다.`Document` 수업의`Save` 수정된 문서를 저장하는 방법입니다. 튜토리얼의 샘플 코드는 편집된 PDF를 저장하고 성공 메시지를 표시하는 방법을 보여줍니다.

#### 질문: 그려진 사각형의 모양을 사용자 지정할 수 있나요?

 A: 네, 그려진 사각형의 모양을 사용자 정의할 수 있습니다. 튜토리얼의 샘플 코드에서`DrawBox` 이 메서드는 사각형을 만드는 데 사용됩니다. 색상, 스타일, 두께와 같은 속성을 수정하여 그려진 사각형의 모양을 사용자 지정할 수 있습니다.