---
title: 첫 번째 발생 바꾸기
linktitle: 첫 번째 발생 바꾸기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 처음 나타나는 텍스트를 바꾸는 방법을 알아보세요.
type: docs
weight: 330
url: /ko/net/programming-with-text/replace-first-occurrence/
---
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 특정 텍스트의 첫 번째 항목을 바꾸는 방법을 설명합니다. 제공된 C# 소스 코드를 사용하여 PDF 문서 열기, 처음 나타나는 검색 문구 찾기, 텍스트 바꾸기, 속성 업데이트, 수정된 PDF 저장 등의 과정을 단계별로 살펴보겠습니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 라이브러리용 Aspose.PDF가 설치되었습니다.
- C# 프로그래밍에 대한 기본적인 이해.

## 1단계: 문서 디렉터리 설정

 먼저 입력 PDF 파일이 있는 디렉터리의 경로를 설정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 변수를 PDF 파일 경로로 바꿉니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: PDF 문서 열기

 다음으로, 다음을 사용하여 PDF 문서를 엽니다.`Document` Aspose.PDF 라이브러리의 클래스입니다.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## 3단계: 검색 문구의 첫 번째 항목 찾기

 우리는`TextFragmentAbsorber` 검색 문구의 모든 인스턴스를 찾으려면 PDF 문서의 모든 페이지에 대해 이의를 제기하고 이를 수락합니다.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 4단계: 텍스트 바꾸기

PDF 문서에서 검색 문구가 발견되면 텍스트 조각의 첫 번째 항목을 검색하고 해당 속성을 새 텍스트 및 서식으로 업데이트합니다.

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

### .NET용 Aspose.PDF를 사용하여 첫 번째 항목 바꾸기의 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
// 입력된 검색 문구의 모든 인스턴스를 찾기 위해 TextAbsorber 개체를 만듭니다.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// 모든 페이지에 대한 흡수체를 수락합니다.
pdfDocument.Pages.Accept(textFragmentAbsorber);
// 추출된 텍스트 조각 가져오기
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
	// 텍스트의 첫 번째 발생을 가져오고 교체
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

이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 특정 텍스트의 첫 번째 항목을 바꾸는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 C# 코드를 실행하면 PDF 문서를 열고, 처음 나타나는 검색 문구를 찾고, 텍스트를 바꾸고, 속성을 업데이트하고, 수정된 PDF를 저장할 수 있습니다.

### FAQ

#### Q: "첫 번째 항목 바꾸기" 튜토리얼의 목적은 무엇입니까?

A: "첫 번째 항목 바꾸기" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 특정 텍스트의 첫 번째 항목을 바꾸는 방법을 보여줍니다. PDF 문서를 열고, 검색 문구의 첫 번째 인스턴스를 찾고, 텍스트를 바꾸고, 속성을 업데이트하고, 수정된 PDF를 저장하는 방법에 대한 단계별 지침을 제공합니다.

#### Q: PDF 문서에서 처음 나타나는 텍스트를 바꾸려는 이유는 무엇입니까?

답변: PDF 문서에서 처음 나타나는 텍스트를 바꾸는 것은 다른 항목은 그대로 유지하면서 특정 문구의 특정 인스턴스를 대상으로 변경해야 할 때 유용합니다. 이 접근 방식은 제어된 방식으로 텍스트를 업데이트하거나 수정하는 데 자주 사용됩니다.

#### Q: 문서 디렉터리를 어떻게 설정합니까?

A: 문서 디렉토리를 설정하려면:

1.  바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 변수를 입력 PDF 파일이 있는 디렉터리의 경로로 바꿉니다.

#### Q: PDF 문서에서 처음 나타나는 특정 텍스트를 어떻게 바꾸나요?

A: 튜토리얼에서는 프로세스를 단계별로 안내합니다.

1.  다음을 사용하여 PDF 문서를 엽니다.`Document` 수업.
2.  만들기`TextFragmentAbsorber` 모든 페이지에서 검색 문구의 인스턴스를 찾으려면 이의를 제기하고 이를 수락하세요.
3. 검색 문구가 발견되면 텍스트 조각의 첫 번째 항목을 검색하고 해당 속성을 새 텍스트 및 서식으로 업데이트합니다.
4. 수정된 PDF 문서를 저장합니다.

####  Q. 사용목적이 무엇인가요?`TextFragmentAbsorber` to find the first occurrence of the search phrase?

 답:`TextFragmentAbsorber` PDF 문서 내에서 검색 문구의 인스턴스를 찾는 데 사용됩니다. 이 튜토리얼에서는 교체해야 하는 텍스트의 첫 번째 항목을 식별하는 데 도움이 됩니다.

#### Q: 텍스트 조각의 속성을 어떻게 업데이트합니까?

A: 첫 번째 텍스트 조각을 찾으면 텍스트 자체, 글꼴, 글꼴 크기, 텍스트 색상과 같은 해당 속성을 업데이트할 수 있습니다. 이를 통해 대체 텍스트의 모양을 사용자 정의할 수 있습니다.

#### Q: 텍스트의 첫 번째 항목만 바꾸는 데 제한이 있나요?

 A: 예, 이 튜토리얼에서는 특히 처음 나타나는 텍스트를 바꾸는 데 중점을 둡니다. 동일한 텍스트가 여러 번 나타나는 경우 교체해야 하는 경우 다음을 반복하여 접근 방식을 확장할 수 있습니다.`TextFragmentCollection` 각 인스턴스를 식별하고 업데이트합니다.

#### Q: 제공된 코드를 실행하면 예상되는 결과는 무엇입니까?

A: 튜토리얼을 따르고 제공된 C# 코드를 실행하면 PDF 문서에서 지정된 텍스트의 첫 번째 항목을 바꾸게 됩니다. 대체 텍스트에는 글꼴, 글꼴 크기, 텍스트 색상과 같은 속성이 업데이트됩니다.

#### Q: 이 접근 방식을 사용하여 동일한 텍스트가 나타나는 다른 항목을 바꿀 수 있습니까?

 A: 예, 코드를 수정하여`TextFragmentCollection` 동일한 텍스트가 여러 번 나타나는 경우를 대체합니다. 필요에 따라 각 인스턴스를 식별하고 업데이트하는 논리를 확장하기만 하면 됩니다.