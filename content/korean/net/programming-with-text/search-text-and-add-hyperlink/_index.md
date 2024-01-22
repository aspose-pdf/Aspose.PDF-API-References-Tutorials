---
title: 텍스트 검색 및 하이퍼링크 추가
linktitle: 텍스트 검색 및 하이퍼링크 추가
second_title: .NET API 참조용 Aspose.PDF
description: PDF에서 텍스트를 검색하고, 찾은 텍스트에 하이퍼링크를 추가하고, Aspose.PDF for .NET을 사용하여 수정된 문서를 저장하는 방법을 알아보세요.
type: docs
weight: 450
url: /ko/net/programming-with-text/search-text-and-add-hyperlink/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 특정 텍스트를 검색하고, 발견된 텍스트에 하이퍼링크를 추가하고, 수정된 문서를 저장하는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## 3단계: 문서 디렉터리 경로 설정

 다음을 사용하여 문서 디렉토리의 경로를 설정하십시오.`dataDir` 변하기 쉬운:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

## 4단계: TextFragmentAbsorber 만들기

 만들기`TextFragmentAbsorber` 입력 검색 문구의 모든 인스턴스를 찾는 개체:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 바꾸다`"\\d{4}-\\d{4}"` 원하는 정규식 패턴으로.

## 5단계: 정규식 검색 활성화

 다음을 설정하여 정규식 검색을 활성화합니다.`TextSearchOptions` 흡수체의 특성:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## 6단계: PDF 문서 열기 및 바인딩

 만들기`PdfContentEditor` 개체를 생성하고 이를 소스 PDF 파일에 바인딩합니다.

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 바꾸다`"SearchRegularExpressionPage.pdf"` PDF 파일의 실제 이름으로.

## 7단계: 페이지에 대한 흡수체 수락

문서의 원하는 페이지에 대한 흡수체를 수락합니다.

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 바꾸다`1` 원하는 페이지 번호로

## 8단계: 찾은 텍스트에 하이퍼링크 추가

검색된 텍스트 조각을 반복하고 여기에 하이퍼링크를 추가합니다.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // 텍스트 조각의 위치를 기반으로 직사각형을 만듭니다.
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //직사각형에 웹 링크 추가
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, 시스템.드로잉.색상.블루);
}
```

 바꾸다`"http://www.aspose.com"` 원하는 하이퍼링크 URL로

## 9단계: 수정된 문서를 저장하고 닫습니다.

수정된 문서를 저장하고 편집기를 닫습니다.

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 꼭 교체하세요`"SearchTextAndAddHyperlink_out.pdf"` 원하는 출력 파일 이름으로.

### .NET용 Aspose.PDF를 사용하여 텍스트 검색 및 하이퍼링크 추가에 대한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 입력된 검색 구문의 모든 인스턴스를 찾기 위해 흡수체 개체를 만듭니다.
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// 정규식 검색 활성화
absorber.TextSearchOptions = new TextSearchOptions(true);
// 문서 열기
PdfContentEditor editor = new PdfContentEditor();
// 소스 PDF 파일 바인딩
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// 페이지의 흡수체를 수락합니다.
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// 조각을 통해 반복
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

축하해요! PDF 문서에서 특정 텍스트를 검색하고, 찾은 텍스트에 하이퍼링크를 추가하고, Aspose.PDF for .NET을 사용하여 수정된 문서를 저장하는 방법을 성공적으로 배웠습니다. 이 튜토리얼에서는 프로젝트 설정부터 필요한 작업 수행까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 텍스트를 조작하고 PDF 파일에 하이퍼링크를 추가할 수 있습니다.

### FAQ

#### Q: "텍스트 검색 및 하이퍼링크 추가" 튜토리얼의 목적은 무엇입니까?

A: "텍스트 검색 및 하이퍼링크 추가" 튜토리얼의 목적은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서 내의 특정 텍스트를 검색하고, 발견된 텍스트에 하이퍼링크를 추가한 다음 수정된 문서를 저장하는 방법을 보여 주는 것입니다. 이 자습서에서는 단계별 프로세스를 설명하기 위해 포괄적인 가이드와 C# 코드 샘플을 제공합니다.

#### 질문: 이 튜토리얼은 PDF 문서의 특정 텍스트에 하이퍼링크를 추가하는 데 어떻게 도움이 됩니까?

A: 이 튜토리얼에서는 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 특정 텍스트를 찾고, 식별된 텍스트에 하이퍼링크를 적용하고, 수정된 PDF를 저장하는 과정을 안내합니다. 프로젝트 설정, 문서 로드, 정규식 검색 활성화, 찾은 텍스트에 하이퍼링크 추가와 같은 필수 단계를 다룹니다.

#### Q: 이 튜토리얼을 따르려면 어떤 전제 조건이 필요합니까?

A: 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있어야 합니다. 또한 Aspose 웹사이트에서 얻거나 프로젝트에서 NuGet을 사용하여 설치할 수 있는 .NET용 Aspose.PDF 라이브러리가 설치되어 있어야 합니다.

#### Q: 이 튜토리얼을 따르려면 프로젝트를 어떻게 설정해야 합니까?

A: 선호하는 IDE(통합 개발 환경)에서 새 C# 프로젝트를 만드는 것부터 시작하세요. 그런 다음 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하면 프로젝트에서 라이브러리의 기능을 활용할 수 있습니다.

#### Q: 이 튜토리얼을 사용하여 특정 텍스트에 하이퍼링크를 추가할 수 있습니까?

A: 예, 이 튜토리얼은 특히 PDF 문서의 특정 텍스트에 하이퍼링크를 추가하는 데 중점을 둡니다. 정규식을 사용하여 원하는 텍스트를 찾아 추출하고, 텍스트 조각과 연결된 하이퍼링크를 만들고, 수정된 PDF를 저장하는 방법을 보여줍니다.

#### Q: 검색하고 하이퍼링크를 추가하려는 텍스트를 어떻게 정의합니까?

 A: 검색하고 하이퍼링크를 추가하려는 텍스트를 지정하려면`TextFragmentAbsorber` 객체를 선택하고 다음을 사용하여 패턴을 설정합니다.`Text` 매개변수. 기본 패턴 바꾸기`"\\d{4}-\\d{4}"` 튜토리얼의 코드에서 원하는 정규식 패턴을 사용하세요.

#### Q: 텍스트에 대한 정규식 검색을 활성화하려면 어떻게 해야 합니까?

 A: 정규식 검색은`TextSearchOptions` 개체를 설정하고 해당 값을 다음으로 설정합니다.`true` . 이 개체를`TextSearchOptions` 의 재산`TextFragmentAbsorber` 사례. 이렇게 하면 텍스트 검색 중에 정규식 패턴이 적용됩니다.

#### Q: 찾은 텍스트에 하이퍼링크를 어떻게 추가하나요?

 A: 다음을 사용하여 텍스트 조각을 식별한 후`TextFragmentAbsorber` , 튜토리얼에서는 이러한 조각을 반복하는 루프를 제공합니다. 각 텍스트 조각에 대해 튜토리얼에서는 텍스트 색상을 파란색으로 설정하고 다음을 사용하여 하이퍼링크를 만드는 방법을 보여줍니다.`CreateWebLink` 방법.

#### Q: 수정된 PDF를 하이퍼링크와 함께 저장하는 단계는 무엇입니까?

 A: 원하는 텍스트 조각에 하이퍼링크를 추가한 후`PdfContentEditor` 수정된 문서를 저장하는 클래스입니다. 튜토리얼의 샘플 코드는 편집된 PDF를 저장하고, 편집기를 닫고, 성공 메시지를 표시하는 방법을 보여줍니다.