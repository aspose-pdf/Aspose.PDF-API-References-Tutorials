---
title: 텍스트 검색 및 사각형 그리기
linktitle: 텍스트 검색 및 사각형 그리기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF에서 텍스트를 검색하고 사각형으로 강조하는 방법을 알아보세요! 향상된 PDF 조작 기술을 위한 쉬운 단계별 튜토리얼.
type: docs
weight: 460
url: /ko/net/programming-with-text/search-text-and-draw-rectangle/
---
## 소개

PDF 조작 기술을 향상시키고 싶으신가요? PDF 파일에서 특정 텍스트를 검색하여 사각형으로 강조하는 방법을 배우고 싶으신가요? 완벽한 가이드를 찾으셨습니다! 오늘은 Aspose.PDF for .NET을 사용하여 PDF 문서에서 텍스트를 검색하고 그 주위에 사각형을 그리는 방법을 안내해 드리겠습니다. 이 문서에서는 명확성과 유용성을 염두에 두고 설계된 단계별 자습서를 제공하여 이러한 기술을 따라하고 프로젝트에 적용할 수 있도록 보장합니다. 

## 필수 조건

튜토리얼을 시작하기에 앞서, 원활한 워크플로를 보장하는 데 필요한 것을 준비하겠습니다.

1. .NET에 대한 기본적인 이해: 이 튜토리얼을 효과적으로 따라가려면 C# 프로그래밍과 .NET 프레임워크에 대해 잘 알고 있어야 합니다.
   
2. Visual Studio 설치됨: 코드를 작성하고 테스트하려면 통합 개발 환경(IDE)이 필요합니다. Visual Studio Community는 좋은 옵션이며 무료입니다.
   
3. .NET용 Aspose.PDF: 프로젝트에 Aspose.PDF 라이브러리를 설치해야 합니다. 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/) 또는 고려하다[임시 면허](https://purchase.aspose.com/temporary-license/) 확장된 기능을 위해.
   
4.  샘플 PDF 문서: 이 튜토리얼에서는 샘플 PDF 파일이 필요합니다.`SearchAndGetTextFromAll.pdf` 프로젝트 디렉토리에 저장됩니다. 

## 패키지 가져오기

시작하려면 먼저 필요한 패키지를 .NET 프로젝트로 가져와야 합니다. 다음 단계를 따르세요.

### Visual Studio를 엽니다

Visual Studio를 실행하고 PDF 기능을 구현할 새 콘솔 애플리케이션을 만들거나 기존 애플리케이션을 사용합니다.

### 프로젝트에 Aspose.PDF 추가

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭합니다.
2. "NuGet 패키지 관리"를 선택하세요.
3.  검색`Aspose.PDF` 최신 버전을 설치하세요.

이렇게 하면 앞으로 수행할 모든 놀라운 PDF 조작의 기초를 마련하는 셈입니다.

## 네임스페이스 가져오기

프로그램 파일의 맨 위에서 Aspose 라이브러리에서 관련 네임스페이스를 가져와야 합니다.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

이렇게 하면 작업에 필요한 Aspose.PDF 라이브러리 내의 클래스와 메서드에 더 쉽게 액세스할 수 있습니다.


이제 모든 것이 설정되었으니 PDF에서 텍스트를 검색하고 그 주위에 사각형을 그리는 과정을 관리 가능한 단계로 나누어 보겠습니다.

## 1단계: 문서 경로 설정

 먼저 PDF 파일의 경로를 설정합니다. 다음을 반드시 바꾸세요.`YOUR DOCUMENT DIRECTORY` 실제 경로와 함께`SearchAndGetTextFromAll.pdf` 저장됩니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: PDF 문서 열기

 다음으로 인스턴스를 생성합니다.`Document` PDF를 로드하는 클래스:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

이 코드 줄은 지정된 PDF 파일을 열어 추가로 조작할 수 있도록 해줍니다.

## 3단계: 텍스트 흡수기 만들기

 이제 해당 문서 내에서 텍스트를 검색할 방법이 필요합니다. 이를 위해 다음을 사용합니다.`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 정규 표현식`@"[\S]+"` PDF에서 공백이 아닌 모든 문자열과 일치하도록 설계되었습니다. 

## 4단계: 텍스트 검색 옵션 구성

다음으로, 텍스트 검색 옵션을 설정해야 합니다.

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

 여기서,`true` 매개변수는 검색이 대소문자를 구분한다는 것을 의미합니다. 이를 다음과 같이 설정할 수 있습니다.`false` 대소문자를 구분하지 않고 검색하고 싶은 경우

## 5단계: 문서에서 텍스트 흡수기 수락

 당신과 함께`TextFragmentAbsorber` 검색 옵션이 준비되었으니 이제 문서에서 텍스트를 흡수할 시간입니다.

```csharp
document.Pages.Accept(textAbsorber);
```

이 방법은 PDF의 각 페이지를 조사하여 지정된 패턴과 일치하는 텍스트 조각을 찾습니다.

## 6단계: PdfContentEditor 만들기

 문서에 모양을 그리려면 다음이 필요합니다.`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

이 편집기를 사용하면 PDF 콘텐츠를 쉽게 조작하고 편집할 수 있습니다.

## 7단계: 찾은 텍스트 조각을 반복합니다.

이제 찾은 텍스트 조각을 반복하여 그 주위에 사각형을 그려보세요.

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

 이 루프는 각 텍스트 조각과 해당 세그먼트를 반복하며 다음을 호출합니다.`DrawBox` 직사각형 그리기 방법

## 8단계: DrawBox 메서드 정의

 정의해야 합니다`DrawBox` 사각형 그리기 논리를 처리하는 메서드입니다. 간단한 구현은 다음과 같습니다.

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // 텍스트 세그먼트를 기준으로 사각형 크기를 계산합니다.
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // 계산된 값을 사용하여 사각형을 그립니다.
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

이 방법은 세그먼트의 경계 사각형을 기준으로 사각형의 위치와 크기를 결정하고 편집기를 사용하여 그립니다.

## 9단계: 수정된 문서 저장

찾은 텍스트 주위에 사각형을 그린 후 수정된 문서를 저장할 수 있습니다.

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

원본 문서를 덮어쓰는 것을 방지하려면 새 파일을 고유한 이름으로 저장해야 합니다.

## 10단계: 확인 메시지

마지막으로 작업이 성공적이었음을 알려주는 확인 메시지를 콘솔에 인쇄합니다.

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

이제 다 됐어요! PDF에서 텍스트를 검색하고 사각형으로 강조하는 스크립트를 성공적으로 만들었습니다.

## 결론

축하합니다! 방금 Aspose.PDF for .NET을 사용하여 PDF 조작 능력을 크게 향상시킬 수 있는 강력한 기술을 잠금 해제했습니다. 몇 가지 간단한 단계만 거치면 문서에서 모든 텍스트를 검색하여 시각적으로 강조 표시하여 PDF 문서를 보다 상호 작용적이고 관리하기 쉽게 만들 수 있습니다. 다양한 정규식 패턴과 색상 옵션을 실험하여 이 도구를 진정으로 자신만의 도구로 만들어보세요!

## 자주 묻는 질문

### .NET용 Aspose.PDF란 무엇인가요?
.NET용 Aspose.PDF는 PDF 문서를 프로그래밍 방식으로 만들고, 조작하고, 변환하는 포괄적인 방법을 제공하는 라이브러리입니다.

### Aspose.PDF를 무료로 사용할 수 있나요?
네, Aspose는 라이브러리의 기능을 테스트하는 데 사용할 수 있는 무료 평가판을 제공합니다. 확인해 보세요[여기](https://releases.aspose.com/).

### Aspose.PDF for .NET과 함께 어떤 프로그래밍 언어를 사용해야 합니까?
.NET용 Aspose.PDF는 C# 및 기타 .NET 언어와 함께 사용하도록 설계되었습니다.

### Aspose.PDF에 대한 도움은 어떻게 받을 수 있나요?
 Aspose 지원 포럼을 방문하여 문제나 궁금한 사항에 대한 도움을 받을 수 있습니다. 지원 찾기[여기](https://forum.aspose.com/c/pdf/10).

### .NET용 Aspose.PDF를 어디에서 다운로드할 수 있나요?
 Aspose 웹사이트에서 라이브러리를 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).