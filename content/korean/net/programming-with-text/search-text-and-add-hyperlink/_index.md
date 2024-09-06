---
title: 텍스트 검색 및 하이퍼링크 추가
linktitle: 텍스트 검색 및 하이퍼링크 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF에서 텍스트를 검색하고, 찾은 텍스트에 하이퍼링크를 추가하고, 수정된 문서를 저장하는 방법을 알아보세요.
type: docs
weight: 450
url: /ko/net/programming-with-text/search-text-and-add-hyperlink/
---
이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 문서에서 특정 텍스트를 검색하고, 찾은 텍스트에 하이퍼링크를 추가하고, 수정된 문서를 저장하는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## 3단계: 문서 디렉토리 경로 설정

 다음을 사용하여 문서 디렉토리 경로를 설정하세요.`dataDir` 변하기 쉬운:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 포함합니다.

## 4단계: TextFragmentAbsorber 만들기

 생성하다`TextFragmentAbsorber` 입력 검색어의 모든 인스턴스를 찾는 객체:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 바꾸다`"\\d{4}-\\d{4}"` 원하는 정규 표현식 패턴을 사용합니다.

## 5단계: 정규 표현식 검색 활성화

 정규 표현식 검색을 활성화하려면 다음을 설정하세요.`TextSearchOptions` 흡수체의 속성:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## 6단계: PDF 문서 열기 및 바인딩

 생성하다`PdfContentEditor` 객체를 만들고 소스 PDF 파일에 바인딩합니다.

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 바꾸다`"SearchRegularExpressionPage.pdf"` PDF 파일의 실제 이름을 입력하세요.

## 7단계: 페이지에 대한 흡수체 수락

원하는 문서 페이지에 대한 흡수체를 수락하세요.

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 바꾸다`1` 원하는 페이지 번호로.

## 8단계: 찾은 텍스트에 하이퍼링크 추가

검색된 텍스트 조각을 반복하고 하이퍼링크를 추가합니다.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // 텍스트 조각의 위치를 기준으로 사각형을 만듭니다.
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //사각형에 웹 링크 추가
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, 시스템.드로잉.색상.블루);
}
```

 바꾸다`"http://www.aspose.com"` 원하는 하이퍼링크 URL을 입력합니다.

## 9단계: 수정된 문서를 저장하고 닫습니다.

수정된 문서를 저장하고 편집기를 닫습니다.

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 교체를 꼭 해주세요`"SearchTextAndAddHyperlink_out.pdf"` 원하는 출력 파일 이름을 입력합니다.

### .NET용 Aspose.PDF를 사용하여 텍스트 검색 및 하이퍼링크 추가를 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 입력 검색어의 모든 인스턴스를 찾기 위해 흡수기 객체를 생성합니다.
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// 정규 표현식 검색 활성화
absorber.TextSearchOptions = new TextSearchOptions(true);
// 문서 열기
PdfContentEditor editor = new PdfContentEditor();
// 소스 PDF 파일 바인딩
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// 페이지에 대한 흡수체를 수락합니다
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// 조각을 반복합니다
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, 파란색, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## 결론

축하합니다! PDF 문서에서 특정 텍스트를 검색하고, 찾은 텍스트에 하이퍼링크를 추가하고, Aspose.PDF for .NET을 사용하여 수정된 문서를 저장하는 방법을 성공적으로 배웠습니다. 이 튜토리얼은 프로젝트 설정부터 필요한 작업 수행까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일에 텍스트를 조작하고 하이퍼링크를 추가할 수 있습니다.

### 자주 묻는 질문

#### 질문: "텍스트 검색 및 하이퍼링크 추가" 튜토리얼의 목적은 무엇인가요?

A: "텍스트 검색 및 하이퍼링크 추가" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서 내에서 특정 텍스트를 검색하고, 찾은 텍스트에 하이퍼링크를 추가한 다음, 수정된 문서를 저장하는 방법을 보여줍니다. 이 튜토리얼은 단계별 프로세스를 설명하는 포괄적인 가이드와 C# 코드 샘플을 제공합니다.

#### 질문: 이 튜토리얼은 PDF 문서의 특정 텍스트에 하이퍼링크를 추가하는 데 어떻게 도움이 되나요?

A: 이 튜토리얼은 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 특정 텍스트를 찾고, 식별된 텍스트에 하이퍼링크를 적용하고, 수정된 PDF를 저장하는 과정을 안내합니다. 프로젝트 설정, 문서 로드, 정규 표현식 검색 활성화, 찾은 텍스트에 하이퍼링크 추가와 같은 필수 단계를 다룹니다.

#### 질문: 이 튜토리얼을 따르려면 어떤 전제 조건이 필요합니까?

A: 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있어야 합니다. 또한 Aspose.PDF for .NET 라이브러리를 설치해야 합니다. 이 라이브러리는 Aspose 웹사이트에서 얻거나 프로젝트에 NuGet을 사용하여 설치할 수 있습니다.

#### 질문: 이 튜토리얼을 따르려면 프로젝트를 어떻게 설정해야 하나요?

A: 선호하는 통합 개발 환경(IDE)에서 새 C# 프로젝트를 만드는 것으로 시작합니다. 그런 다음 Aspose.PDF for .NET 라이브러리에 대한 참조를 추가하면 프로젝트에서 라이브러리의 기능을 활용할 수 있습니다.

#### 질문: 이 튜토리얼을 사용하여 특정 텍스트에 하이퍼링크를 추가할 수 있나요?

A: 네, 이 튜토리얼은 PDF 문서의 특정 텍스트에 하이퍼링크를 추가하는 데 중점을 두고 있습니다. 정규 표현식을 사용하여 원하는 텍스트를 찾고 추출하는 방법, 텍스트 조각과 관련된 하이퍼링크를 만드는 방법, 수정된 PDF를 저장하는 방법을 보여줍니다.

#### 질문: 검색하고 하이퍼링크를 추가하려는 텍스트를 정의하려면 어떻게 해야 하나요?

 A: 검색하려는 텍스트를 지정하고 하이퍼링크를 추가하려면 다음을 만듭니다.`TextFragmentAbsorber` 객체를 만들고 패턴을 설정합니다.`Text` 매개변수. 기본 패턴을 대체합니다.`"\\d{4}-\\d{4}"` 튜토리얼의 코드에 원하는 정규 표현식 패턴을 추가합니다.

#### 질문: 텍스트에 대한 정규 표현식 검색을 활성화하려면 어떻게 해야 하나요?

 A: 정규 표현식 검색은 다음을 생성하여 활성화됩니다.`TextSearchOptions` 객체를 만들고 값을 설정합니다.`true` . 이 객체를 다음에 할당합니다.`TextSearchOptions` 의 속성`TextFragmentAbsorber` 인스턴스. 이렇게 하면 정규 표현식 패턴이 텍스트 검색 중에 적용됩니다.

#### 질문: 찾은 텍스트에 하이퍼링크를 추가하려면 어떻게 해야 하나요?

 A: 텍스트 조각을 식별한 후`TextFragmentAbsorber` , 이 튜토리얼은 이러한 조각을 반복하는 루프를 제공합니다. 각 텍스트 조각에 대해 이 튜토리얼은 텍스트 색상을 파란색으로 설정하고 하이퍼링크를 만드는 방법을 보여줍니다.`CreateWebLink` 방법.

#### 질문: 하이퍼링크가 포함된 수정된 PDF를 저장하는 단계는 무엇입니까?

 A: 원하는 텍스트 조각에 하이퍼링크를 추가한 후 다음을 사용합니다.`PdfContentEditor` 수정된 문서를 저장하는 클래스입니다. 튜토리얼의 샘플 코드는 편집된 PDF를 저장하고, 편집기를 닫고, 성공 메시지를 표시하는 방법을 보여줍니다.