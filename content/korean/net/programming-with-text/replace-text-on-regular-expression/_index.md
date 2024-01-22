---
title: PDF 파일의 정규 표현식에서 텍스트 바꾸기
linktitle: PDF 파일에서 Texton 정규식 바꾸기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 정규식을 기반으로 텍스트를 바꾸는 방법을 알아보세요.
type: docs
weight: 360
url: /ko/net/programming-with-text/replace-text-on-regular-expression/
---
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일에서 정규식을 기반으로 텍스트를 바꾸는 방법을 설명합니다. 필요한 C# 소스 코드와 함께 단계별 가이드를 제공합니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 라이브러리용 Aspose.PDF가 설치되었습니다.
- C# 프로그래밍에 대한 기본 이해.

## 1단계: 문서 디렉터리 설정

 입력 PDF 파일이 있는 디렉터리로 경로를 설정합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 변수를 PDF 파일 경로로 바꿉니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: PDF 문서 로드

 다음을 사용하여 PDF 문서를 로드합니다.`Document` Aspose.PDF 라이브러리의 클래스입니다.

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## 3단계: 정규식을 사용하여 텍스트 검색 및 바꾸기

 만들기`TextFragmentAbsorber` 개체를 지정하고 정규식 패턴을 지정하여 패턴과 일치하는 모든 구문을 찾습니다. 정규식 사용을 활성화하려면 텍스트 검색 옵션을 설정하세요.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999~2000년처럼
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## 4단계: 텍스트 바꾸기

추출된 텍스트 조각을 반복하고 필요에 따라 텍스트를 바꿉니다. 텍스트와 글꼴, 글꼴 크기, 전경색, 배경색 등 기타 속성을 업데이트합니다.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## 5단계: 수정된 PDF 저장

수정된 PDF 문서를 지정된 출력 파일에 저장합니다.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### .NET용 Aspose.PDF를 사용하여 Texton 정규식 바꾸기의 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// 정규식과 일치하는 모든 구문을 찾기 위해 TextAbsorber 개체를 만듭니다.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999~2000년처럼
// 정규식 사용을 지정하려면 텍스트 검색 옵션을 설정하세요.
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// 단일 페이지에 대한 흡수체를 수락합니다.
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// 추출된 텍스트 조각 가져오기
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// 조각을 통해 반복
foreach (TextFragment textFragment in textFragmentCollection)
{
	// 텍스트 및 기타 속성 업데이트
	textFragment.Text = "New Phrase";
	// 개체의 인스턴스로 설정합니다.
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서의 정규식을 기반으로 텍스트를 바꾸는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 C# 코드를 실행하면 PDF 문서를 로드하고, 정규식을 사용하여 텍스트를 검색하고, 바꾸고, 수정된 PDF를 저장할 수 있습니다.

### FAQ

#### Q: "PDF 파일의 정규식 텍스트 바꾸기" 튜토리얼의 목적은 무엇입니까?

A: "PDF 파일의 정규식에서 텍스트 바꾸기" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 정규식을 기반으로 PDF 문서에서 텍스트를 검색하고 바꾸는 과정을 안내하는 것을 목표로 합니다. 샘플 C# 코드와 함께 단계별 가이드를 제공합니다.

#### Q: 정규식을 사용하여 PDF 문서의 텍스트를 바꾸는 이유는 무엇입니까?

A: 정규식을 사용하면 특정 형식을 따르는 텍스트 패턴을 검색하고 바꿀 수 있으므로 콘텐츠를 조작하는 강력한 방법이 됩니다. 이 접근 방식은 PDF 문서 전체에서 특정 패턴이나 구조와 일치하는 텍스트를 바꿔야 할 때 특히 유용합니다.

#### Q: 문서 디렉터리를 어떻게 설정합니까?

A: 문서 디렉토리를 설정하려면:

1.  바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 변수를 입력 PDF 파일이 있는 디렉터리의 경로로 바꿉니다.

#### Q: PDF 문서의 정규식을 기반으로 텍스트를 바꾸려면 어떻게 해야 합니까?

A: 튜토리얼에서는 다음 단계를 안내합니다.

1.  다음을 사용하여 PDF 문서를 로드합니다.`Document` 수업.
2.  만들기`TextFragmentAbsorber` 개체를 지정하고 정규식 패턴을 지정하여 패턴과 일치하는 구문을 찾습니다. 정규식 사용을 활성화하려면 텍스트 검색 옵션을 설정하세요.
3. 추출된 텍스트 조각을 반복하고 텍스트를 바꿉니다. 필요에 따라 글꼴, 글꼴 크기, 전경색, 배경색과 같은 기타 속성을 업데이트합니다.
4. 수정된 PDF 문서를 저장합니다.

#### Q: 복잡한 정규식을 사용하여 텍스트를 바꿀 수 있습니까?

A: 예, 복잡한 정규식을 사용하여 PDF 문서의 텍스트를 일치시키고 바꿀 수 있습니다. 정규식은 텍스트의 특정 패턴이나 구조를 식별하는 유연한 방법을 제공합니다.

####  Q: 이 프로그램의 목적은 무엇입니까?`TextSearchOptions` class in the tutorial?

 답:`TextSearchOptions`클래스를 사용하면 텍스트 조각을 검색할 때 정규식 사용을 활성화하는 등 텍스트 검색 옵션을 지정할 수 있습니다. 튜토리얼에서는 정규식 모드를 활성화하는 데 사용됩니다.`TextFragmentAbsorber`.

#### Q: 정규식을 사용하여 텍스트를 바꿀 때 글꼴 교체는 선택 사항입니까?

A: 예, 정규식을 사용하여 텍스트를 바꿀 때 글꼴 교체는 선택 사항입니다. 새 글꼴을 지정하지 않으면 텍스트는 원본 텍스트 조각의 글꼴을 유지합니다.

#### Q: 정규식을 사용하여 여러 페이지의 텍스트를 바꾸려면 어떻게 해야 합니까?

A: 튜토리얼 예제와 유사하게 PDF 문서의 모든 페이지를 포함하도록 텍스트 조각을 통해 루프를 수정할 수 있습니다. 이렇게 하면 정규식 패턴을 기반으로 여러 페이지의 텍스트를 바꿀 수 있습니다.

#### Q: 제공된 코드를 실행하면 예상되는 결과는 무엇입니까?

A: 튜토리얼을 따르고 제공된 C# 코드를 실행하면 PDF 문서에서 지정된 정규식 패턴과 일치하는 텍스트를 바꿀 수 있습니다. 대체된 텍스트에는 글꼴, 글꼴 크기, 전경색, 배경색 등 사용자가 지정한 속성이 적용됩니다.

#### Q: 이 접근 방식을 사용하여 텍스트를 복잡한 서식으로 바꿀 수 있습니까?

A: 예, 글꼴, 글꼴 크기, 전경색, 배경색과 같은 속성을 업데이트하여 대체된 텍스트의 서식을 사용자 지정할 수 있습니다. 이를 통해 필요에 따라 형식을 유지하거나 수정할 수 있습니다.