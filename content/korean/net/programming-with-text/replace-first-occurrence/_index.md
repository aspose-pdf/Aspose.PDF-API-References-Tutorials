---
title: 첫 번째 발생을 대체합니다
linktitle: 첫 번째 발생을 대체합니다
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서에서 첫 번째로 나타나는 텍스트를 바꾸는 방법을 알아보세요.
type: docs
weight: 330
url: /ko/net/programming-with-text/replace-first-occurrence/
---
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 특정 텍스트의 첫 번째 발생을 바꾸는 방법을 설명합니다. PDF 문서를 열고, 검색어의 첫 번째 발생을 찾고, 텍스트를 바꾸고, 속성을 업데이트하고, 제공된 C# 소스 코드를 사용하여 수정된 PDF를 저장하는 단계별 프로세스를 살펴보겠습니다.

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 라이브러리용 Aspose.PDF가 설치되었습니다.
- C# 프로그래밍에 대한 기본적인 이해.

## 1단계: 문서 디렉토리 설정

 먼저 입력 PDF 파일이 있는 디렉토리 경로를 설정해야 합니다. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` PDF 파일 경로가 있는 변수입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: PDF 문서 열기

 다음으로, 다음을 사용하여 PDF 문서를 엽니다.`Document` Aspose.PDF 라이브러리의 클래스입니다.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## 3단계: 검색 구문의 첫 번째 발생 찾기

 우리는 만듭니다`TextFragmentAbsorber` 객체를 입력하고 PDF 문서의 모든 페이지에서 검색어가 포함된 모든 인스턴스를 찾습니다.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 4단계: 텍스트 바꾸기

검색어가 PDF 문서에서 발견되면 텍스트 조각의 첫 번째 항목을 검색하여 새 텍스트와 서식으로 속성을 업데이트합니다.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
    TextFragment textFragment = textFragmentCollection[1];
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
}
```

## 5단계: 수정된 PDF 저장

마지막으로 수정된 PDF 문서를 지정된 출력 파일에 저장합니다.

```csharp
dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### .NET용 Aspose.PDF를 사용하여 첫 번째 발생을 바꾸기 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
// 입력 검색어의 모든 인스턴스를 찾기 위해 TextAbsorber 객체를 생성합니다.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// 모든 페이지에 대한 흡수체를 수용합니다.
pdfDocument.Pages.Accept(textFragmentAbsorber);
// 추출된 텍스트 조각을 가져옵니다
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
	// 첫 번째 텍스트 발생을 가져와 바꾸기
	TextFragment textFragment = textFragmentCollection[1];
	// 텍스트 및 기타 속성 업데이트
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
	pdfDocument.Save(dataDir);                 
	Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
}
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 특정 텍스트의 첫 번째 발생을 바꾸는 방법을 알아보았습니다. 단계별 가이드를 따르고 제공된 C# 코드를 실행하면 PDF 문서를 열고, 검색어의 첫 번째 발생을 찾고, 텍스트를 바꾸고, 속성을 업데이트하고, 수정된 PDF를 저장할 수 있습니다.

### 자주 묻는 질문

#### 질문: "첫 번째 발생 바꾸기" 튜토리얼의 목적은 무엇입니까?

A: "첫 번째 발생 바꾸기" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 특정 텍스트의 첫 번째 발생을 바꾸는 방법을 보여줍니다. PDF 문서를 열고, 검색 구문의 첫 번째 발생을 찾고, 텍스트를 바꾸고, 속성을 업데이트하고, 수정된 PDF를 저장하는 방법에 대한 단계별 지침을 제공합니다.

#### 질문: PDF 문서에서 첫 번째로 나오는 텍스트를 바꾸고 싶은 이유는 무엇인가요?

A: PDF 문서에서 첫 번째 텍스트 발생을 바꾸는 것은 특정 문구의 특정 인스턴스에 대한 타깃 변경을 하고 다른 발생은 그대로 두어야 할 때 유용합니다. 이 접근 방식은 종종 통제된 방식으로 텍스트를 업데이트하거나 수정하는 데 사용됩니다.

#### 질문: 문서 디렉토리를 어떻게 설정하나요?

A: 문서 디렉토리를 설정하려면:

1.  바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 입력 PDF 파일이 있는 디렉토리의 경로를 포함하는 변수입니다.

#### 질문: PDF 문서에서 특정 텍스트가 처음 나오는 부분을 어떻게 바꾸나요?

A: 튜토리얼은 단계별로 과정을 안내합니다.

1.  PDF 문서를 열려면 다음을 사용하세요.`Document` 수업.
2.  생성하다`TextFragmentAbsorber` 객체를 만들고 모든 페이지에서 이를 허용하여 검색어의 인스턴스를 찾습니다.
3. 검색어가 발견되면 텍스트 조각의 첫 번째 항목을 검색하고 해당 속성을 새 텍스트와 서식으로 업데이트합니다.
4. 수정된 PDF 문서를 저장합니다.

####  Q: 사용 목적은 무엇입니까?`TextFragmentAbsorber` to find the first occurrence of the search phrase?

 A: 그`TextFragmentAbsorber` PDF 문서 내에서 검색 구문의 인스턴스를 찾는 데 사용됩니다. 이 튜토리얼에서는 대체해야 할 텍스트의 첫 번째 발생을 식별하는 데 도움이 됩니다.

#### 질문: 텍스트 조각의 속성을 어떻게 업데이트합니까?

A: 텍스트 조각의 첫 번째 발생을 찾으면 텍스트 자체, 글꼴, 글꼴 크기, 텍스트 색상과 같은 속성을 업데이트할 수 있습니다. 이를 통해 대체 텍스트의 모양을 사용자 정의할 수 있습니다.

#### 질문: 첫 번째로 나타나는 텍스트만 바꾸는 데 제한이 있나요?

 A: 네, 이 튜토리얼은 특히 텍스트의 첫 번째 발생을 대체하는 데 중점을 둡니다. 동일한 텍스트의 여러 발생을 대체해야 하는 경우 반복하여 접근 방식을 확장할 수 있습니다.`TextFragmentCollection` 각 인스턴스를 식별하고 업데이트합니다.

#### 질문: 제공된 코드를 실행하면 예상되는 결과는 무엇입니까?

A: 튜토리얼을 따라 제공된 C# 코드를 실행하면 PDF 문서에서 지정된 텍스트의 첫 번째 발생을 대체하게 됩니다. 대체 텍스트는 글꼴, 글꼴 크기, 텍스트 색상과 같은 업데이트된 속성을 갖게 됩니다.

#### 질문: 이 방법을 사용하면 같은 텍스트가 다른 곳에 나타날 때 이를 대체할 수 있나요?

 A: 네, 코드를 수정하여 반복할 수 있습니다.`TextFragmentCollection` 동일한 텍스트의 여러 발생을 대체합니다. 필요에 따라 각 인스턴스를 식별하고 업데이트하기 위해 논리를 확장하기만 하면 됩니다.