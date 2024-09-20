---
title: PDF 파일에서 정규 표현식의 텍스트 바꾸기
linktitle: PDF 파일에서 Texton 정규 표현식을 교체하세요
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에서 정규 표현식을 기반으로 텍스트를 바꾸는 방법을 알아보세요. 텍스트 변경을 효율적으로 자동화하기 위한 단계별 가이드를 따르세요.
type: docs
weight: 360
url: /ko/net/programming-with-text/replace-text-on-regular-expression/
---
## 소개

Aspose.PDF for .NET은 개발자가 PDF 파일을 쉽게 조작할 수 있는 놀라운 도구입니다. 강력한 기능 중 하나는 정규 표현식을 기반으로 텍스트를 검색하여 바꿀 수 있는 기능입니다. 날짜, 전화번호 또는 코드와 같이 특정 텍스트 패턴을 변경해야 하는 PDF를 처리해야 했던 적이 있다면 이것이 바로 여러분이 찾고 있는 것입니다. 이 튜토리얼에서는 PDF 파일에서 정규 표현식을 사용하여 텍스트를 바꾸는 과정을 안내해 드리겠습니다. 이 기능을 프로젝트에 원활하게 통합할 수 있도록 쉽게 따를 수 있는 단계로 나누어 설명하겠습니다.

## 필수 조건

코드를 살펴보기 전에 모든 것이 설정되어 있는지 확인해 보겠습니다.

1.  .NET용 Aspose.PDF: .NET용 Aspose.PDF의 최신 버전이 필요합니다. 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
2. IDE: Visual Studio 또는 기타 .NET 호환 통합 개발 환경(IDE).
3. .NET Framework: .NET Framework 4.0 이상이 설치되어 있는지 확인하세요.
4. PDF 문서: 텍스트를 검색하고 바꾸려는 샘플 PDF 파일입니다.

모든 것을 준비했으면 시작할 준비가 된 것입니다!

## 패키지 가져오기

우리가 해야 할 첫 번째 일은 필요한 패키지를 가져오는 것입니다. 이렇게 하면 Aspose.PDF에서 필요한 모든 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

이를 통해 PDF 문서를 다루고 문서 내의 텍스트 조각을 처리할 수 있습니다.

이제 단계별로 프로세스를 살펴보겠습니다. 정규 표현식을 기반으로 텍스트를 대체하는 과정을 따라가세요.

## 1단계: PDF 문서 로드

 먼저, 텍스트 교체를 수행할 PDF 문서를 로드해야 합니다. 이는 다음을 사용하여 수행됩니다.`Document` Aspose.PDF의 클래스입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

 이 단계에서는 다음을 교체합니다.`"YOUR DOCUMENT DIRECTORY"`PDF 파일이 저장된 실제 경로와 함께. 이 코드는 PDF를 열고 로드합니다.`pdfDocument` 다음 단계에서 조작할 객체입니다.

## 2단계: 정규 표현식 정의

 이제 문서를 로드했으므로 다음 단계는 관심 있는 텍스트 패턴을 검색할 정규 표현식을 정의하는 것입니다. 예를 들어 "1999-2000"과 같은 연도 범위를 바꾸려는 경우 정규 표현식을 사용할 수 있습니다.`\d{4}-\d{4}`.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); 
```

 이 라인은 다음을 설정합니다.`TextFragmentAbsorber` 4자리 숫자, 하이픈, 그리고 또 다른 4자리 숫자를 검색합니다. 필요에 따라 정규 표현식을 수정하여 특정 사용 사례와 일치시킬 수 있습니다.

## 3단계: 정규 표현식 검색 옵션 활성화

 Aspose.PDF를 사용하면 텍스트 검색 방법을 미세 조정할 수 있습니다. 이 경우 다음을 사용하여 정규 표현식 일치를 활성화합니다.`TextSearchOptions` 수업.

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

 이 옵션을 설정하면`true`PDF 내에서 검색 시 정규 표현식을 사용할 수 있습니다.

## 4단계: 특정 페이지에 흡수체 적용

 다음으로, 우리는 다음을 적용합니다.`TextFragmentAbsorber` 문서의 특정 페이지로. 이 예는 첫 번째 페이지에 적용합니다.

```csharp
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

이 방법은 문서의 첫 페이지에서 정규 표현식과 일치하는 모든 텍스트 조각을 추출합니다. 전체 문서를 검색하려면 모든 페이지를 반복할 수 있습니다.

## 5단계: 텍스트 반복 및 바꾸기

이제 재밌는 부분이 왔습니다! 추출된 텍스트 조각을 반복하고, 텍스트를 대체하고, 글꼴 크기, 글꼴 유형, 색상과 같은 속성을 사용자 정의합니다.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

foreach (TextFragment textFragment in textFragmentCollection)
{
    textFragment.Text = "New Phrase"; // 새로운 텍스트로 바꾸세요
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

 여기서는 정규 표현식과 일치하는 각 텍스트 조각을 반복합니다. 각 일치 항목에 대해 텍스트가 다음으로 바뀝니다.`"New Phrase"`. 또한 글꼴을 "Verdana"로 사용자 지정하고, 글꼴 크기를 22로 설정하고, 텍스트와 배경색을 변경합니다.

## 6단계: 업데이트된 PDF 문서 저장

모든 변경을 마쳤으면 수정된 PDF 문서를 저장할 차례입니다.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
```

이렇게 하면 모든 텍스트 대체 내용이 포함된 업데이트된 PDF가 새 파일인 다음 파일에 저장됩니다.`ReplaceTextonRegularExpression_out.pdf`.

## 7단계: 변경 사항 확인

마지막으로 모든 것이 제대로 작동했는지 확인하려면 콘솔에 메시지를 출력하세요.

```csharp
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

이 메시지는 텍스트 바꾸기 과정이 성공적으로 이루어졌음을 확인하고 새 PDF가 저장된 위치를 보여줍니다.

## 결론

Aspose.PDF for .NET을 사용하여 정규 표현식을 기반으로 PDF 파일의 텍스트를 성공적으로 대체했습니다! 문서 처리를 자동화하든 오래된 정보를 정리하든 이 기능은 매우 강력합니다. 몇 줄의 코드만 있으면 몇 초 만에 큰 문서에서 복잡한 텍스트를 변경할 수 있습니다.

## 자주 묻는 질문

### 하나의 문서에서 여러 개의 정규 표현식을 사용할 수 있나요?
 네, 여러 개를 만들 수 있습니다.`TextFragmentAbsorber` 각각 다른 정규 표현식을 갖는 객체를 만들고 이를 문서에 적용합니다.

### .NET용 Aspose.PDF는 .NET Core와 호환됩니까?
예, Aspose.PDF for .NET은 .NET Framework와 .NET Core를 모두 지원합니다.

### 여러 페이지의 텍스트를 한 번에 바꿀 수 있나요?
물론입니다! 흡수제를 한 페이지에 적용하는 대신 모든 페이지를 반복하거나 전체 문서에 한 번에 적용할 수도 있습니다.

### 대소문자를 구분하지 않고 검색하고 싶다면 어떻게 해야 하나요?
적절한 정규 표현식 플래그를 사용하거나 검색 옵션을 조정하여 정규 표현식을 대소문자를 구분하지 않도록 수정할 수 있습니다.

### PDF 파일의 이미지를 바꿀 수 있나요?
네, .NET용 Aspose.PDF도 PDF 문서 내에서 이미지 교체 및 조작을 지원합니다.