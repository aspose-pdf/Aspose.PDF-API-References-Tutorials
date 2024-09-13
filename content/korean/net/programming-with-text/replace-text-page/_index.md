---
title: PDF 파일에서 텍스트 페이지 바꾸기
linktitle: PDF 파일에서 텍스트 페이지 바꾸기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일의 특정 페이지에 있는 텍스트를 바꾸는 방법을 알아보세요.
type: docs
weight: 370
url: /ko/net/programming-with-text/replace-text-page/
---
이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 파일의 특정 페이지에 있는 텍스트를 바꾸는 방법을 설명합니다. 제공된 C# 소스 코드는 단계별로 프로세스를 보여줍니다.

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
```

## 3단계: PDF 문서 로드

 PDF 문서 디렉토리 경로를 설정하고 다음을 사용하여 문서를 로드합니다.`Document` 수업:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

 교체를 꼭 해주세요`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 포함합니다.

## 4단계: 텍스트 찾기 및 바꾸기

 생성하다`TextFragmentAbsorber` 입력 검색어의 모든 인스턴스를 찾는 객체:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 바꾸다`"text"` 검색하여 바꾸려는 실제 텍스트와 일치합니다.

## 5단계: 대상 페이지 지정

 특정 페이지에 대한 흡수체를 수락하려면 다음을 수행합니다.`Pages` 의 컬렉션`pdfDocument` 객체를 호출하고`Accept` 방법:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 바꾸다`2` 텍스트를 대체하려는 페이지 번호와 함께. 페이지 번호는 0부터 시작한다는 점에 유의하세요.`0` 첫 번째 페이지를 나타냅니다.

## 6단계: 추출된 텍스트 조각 검색

 다음을 사용하여 추출된 텍스트 조각을 가져옵니다.`TextFragments` 의 속성`TextFragmentAbsorber` 물체:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 7단계: 텍스트 조각 반복

검색된 텍스트 조각을 반복하고 원하는 대로 텍스트 및 기타 속성을 업데이트합니다.

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

 위의 코드 조각에서 다음을 바꾸세요.`"New Phrase"` 사용하고 싶은 대체 텍스트로. 글꼴, 글꼴 크기, 전경색, 배경색과 같은 다른 속성을 사용자 정의할 수도 있습니다.

## 8단계: 수정된 PDF 저장

 수정된 PDF 문서를 새 파일에 저장하려면 다음을 사용합니다.`Save` 방법:

```csharp
pdfDocument.Save(dataDir + "ReplaceTextPage_out.pdf");
```

 교체를 꼭 해주세요`"ReplaceTextPage_out.pdf"` 원하는 출력 파일 이름을 입력합니다.

### .NET용 Aspose.PDF를 사용하여 텍스트 페이지를 바꾸기 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
// 입력 검색어의 모든 인스턴스를 찾기 위해 TextAbsorber 객체를 생성합니다.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
//특정 페이지에 대한 흡수체 수락
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// 추출된 텍스트 조각을 가져옵니다
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// 조각을 반복합니다
foreach (TextFragment textFragment in textFragmentCollection)
{
	// 텍스트 및 기타 속성 업데이트
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
pdfDocument.Save(dataDir + "ReplaceTextPage_out.pdf");
```

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 문서의 특정 페이지에 있는 텍스트를 바꾸는 방법을 성공적으로 배웠습니다. 이 튜토리얼은 문서 로드부터 수정된 버전 저장까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일에서 텍스트 바꾸기를 자동화할 수 있습니다.

### 자주 묻는 질문

#### 질문: "PDF 파일의 텍스트 페이지 바꾸기" 튜토리얼의 목적은 무엇인가요?

A: "PDF 파일에서 텍스트 페이지 바꾸기" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일의 특정 페이지에 있는 텍스트를 바꾸는 과정을 안내합니다. 샘플 C# 코드와 함께 단계별 가이드를 제공합니다.

#### 질문: PDF 문서의 특정 페이지에 있는 텍스트를 바꾸고 싶은 이유는 무엇인가요?

A: 특정 페이지의 텍스트를 바꾸는 것은 PDF 문서의 특정 페이지의 내용을 업데이트하고 다른 페이지는 그대로 두어야 할 때 유용합니다. 이는 일반적으로 특정 페이지의 내용을 타깃팅하여 변경하는 데 사용됩니다.

#### Q4: 튜토리얼 프로젝트를 어떻게 설정하나요?

A: 프로젝트를 설정하려면:

1. 선호하는 통합 개발 환경(IDE)에서 새로운 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

####  Q: 왜`Aspose.Pdf` and `Aspose.Pdf.Text` namespaces imported?

A: 이러한 네임스페이스는 PDF 문서를 로드하고, 수정하고, 저장하고, 텍스트 조각을 작업하는 데 필요한 Aspose.PDF 라이브러리가 제공하는 클래스와 메서드에 액세스할 수 있도록 가져오기 위해 제공됩니다.

#### 질문: Aspose.PDF를 사용하여 PDF 문서를 로드하려면 어떻게 해야 하나요?

 A: PDF 문서를 로드하려면 다음을 사용하십시오.`Document` 클래스 및 PDF 파일 경로 지정:

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

 바꾸다`"ReplaceTextPage.pdf"` 실제 파일 이름으로.

#### 질문: 이 방법을 사용하여 여러 페이지의 텍스트를 바꿀 수 있나요?

 A: 네, 원하는 각 페이지에 대해 프로세스를 반복하여 여러 페이지의 텍스트를 바꿀 수 있습니다. 페이지 인덱스를 수정합니다(예:`pdfDocument.Pages[2]`)을 클릭하여 작업할 페이지를 지정하세요.

#### 질문: 텍스트를 다른 서식으로 바꾸고 싶은 경우에는 어떻게 해야 하나요?

 A: 속성을 업데이트할 수 있습니다.`TextFragment` 글꼴, 글꼴 크기, 전경색, 배경색 등의 개체를 사용하여 바뀐 텍스트에 원하는 서식을 적용합니다.

#### 질문: 지정된 페이지에서 검색어를 찾을 수 없으면 어떻게 되나요?

A: 지정된 페이지에서 검색어가 발견되지 않는 경우,`TextFragmentCollection` 비어 있고, 대체가 이루어지지 않습니다. 타겟팅하는 페이지에 검색어가 있는지 확인하세요.

#### 질문: 각 텍스트 조각에 대한 대체 텍스트를 사용자 지정하려면 어떻게 해야 하나요?

 A: 반복되는 루프 내에서`TextFragmentCollection` , 각각의 대체 텍스트를 사용자 정의할 수 있습니다.`TextFragment` 다른 문자열을 할당하여 개별적으로`Text` 재산.

#### 질문: 대소문자를 구분하지 않고 검색한 내용을 기준으로 텍스트를 바꿀 수 있나요?

 A: 네, 정규 표현식 패턴을 수정하여 대소문자를 구분하지 않는 검색을 수행할 수 있습니다. 예를 들어 다음을 사용할 수 있습니다.`"text"` 대신에`"text"` 에서`TextFragmentAbsorber` 건설자.