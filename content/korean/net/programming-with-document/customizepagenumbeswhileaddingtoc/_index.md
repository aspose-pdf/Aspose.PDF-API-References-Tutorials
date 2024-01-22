---
title: TOC를 추가하는 동안 페이지 번호 사용자 정의
linktitle: TOC를 추가하는 동안 페이지 번호 사용자 정의
second_title: .NET API 참조용 Aspose.PDF
description: 이 단계별 가이드와 코드 예제를 통해 .NET용 Aspose.PDF를 사용하여 목차(TOC)를 추가하는 동안 페이지 번호를 사용자 정의하는 방법을 알아보세요.
type: docs
weight: 100
url: /ko/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 목차(TOC)를 추가하면서 페이지 번호를 사용자 정의하는 방법을 살펴보겠습니다. 이를 달성하는 데 도움이 되도록 코드 예제와 함께 단계별 지침을 제공할 것입니다.

## 1단계: 기존 PDF 파일 로드

먼저 기존 PDF 파일을 로드해야 합니다. 이 튜토리얼에서는 "YOUR DOCUMENT DIRECTORY" 디렉토리에 있는 "42824.pdf" 파일을 사용합니다. 이 디렉토리 경로를 문서 디렉토리의 실제 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## 2단계: 목차 페이지 추가

 다음으로 목차 페이지 역할을 할 새 페이지를 문서 시작 부분에 추가해야 합니다. 우리는 다음을 사용하여 이를 달성할 수 있습니다.`Insert()` 의 방법`Pages` 의 컬렉션`Document` 물체.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## 3단계: TOC 객체 생성

 TOC 객체를 생성하려면 먼저`TocInfo` 개체를 선택하고 해당 속성을 설정합니다. 이 튜토리얼에서는 TOC 제목을 "목차"로 설정하고 페이지 번호 접두어를 "P"로 설정합니다.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## 4단계: 목차 항목 만들기

목차 항목을 만들려면 목차 페이지를 제외한 문서의 모든 페이지를 반복하고 각 페이지에 대한 제목 개체를 만들어야 합니다. 그런 다음 목차 페이지에 제목 개체를 추가하고 대상 페이지를 지정할 수 있습니다.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // 제목 개체 만들기
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // 제목 개체의 대상 페이지 지정
    heading2.DestinationPage = doc.Pages[i + 1];
    // 목적지 페이지
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // 목적지 좌표
    segment2.Text = "Page " + i.ToString();
    // TOC가 포함된 페이지에 제목 추가
    tocPage.Paragraphs.Add(heading2);
}
```

## 5단계: 업데이트된 문서 저장

마지막으로 업데이트된 문서를 새 파일에 저장해야 합니다. 우리는 다음을 사용하여 이를 달성할 수 있습니다.`Save()` 의 방법`Document` 물체.

```csharp
doc.Save(outFile);
```

### .NET용 Aspose.PDF를 사용하여 TOC를 추가하는 동안 페이지 번호를 사용자 정의하기 위한 예제 소스 코드

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// 기존 PDF 파일 로드
Document doc = new Document(inFile);
// PDF 파일의 첫 번째 페이지에 액세스
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// TOC 정보를 나타내는 객체 생성
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// TOC 제목 설정
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// 제목 개체 만들기
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// 제목 개체의 대상 페이지 지정
	heading2.DestinationPage = doc.Pages[i + 1];
	// 목적지 페이지
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// 목적지 좌표
	segment2.Text = "Page " + i.ToString();
	// TOC가 포함된 페이지에 제목 추가
	tocPage.Paragraphs.Add(heading2);
}

// 업데이트된 문서 저장
doc.Save(outFile);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 목차를 추가하는 동안 페이지 번호를 사용자 정의하는 방법에 대한 단계별 지침을 제공했습니다. 또한 이 기능을 애플리케이션에 구현할 때 참조로 사용할 수 있는 코드 예제도 제공했습니다.

### FAQ

#### Q: PDF 문서의 목차(TOC)란 무엇입니까?

A: PDF 문서의 목차(TOC)는 해당 페이지 번호와 함께 문서 섹션이나 장의 정리된 목록을 제공하는 탐색 보조 도구입니다. 이를 통해 독자는 문서 내의 특정 섹션으로 빠르게 이동할 수 있습니다.

#### Q:목차의 페이지 번호를 사용자 정의하려는 이유는 무엇입니까?

A: 특정 페이지 번호 매기기 형식을 사용하거나 페이지 번호와 함께 추가 정보를 포함하려는 경우 목차의 페이지 번호를 사용자 정의하는 것이 유용할 수 있습니다. 이를 통해 보다 개인화되고 유익한 목차를 만들 수 있습니다.

#### Q: PDF 문서 내의 특정 섹션이나 페이지에 연결하기 위해 목차에 하이퍼링크를 포함할 수 있습니까?

A: 예, .NET용 Aspose.PDF를 사용하면 PDF 문서 내의 특정 섹션이나 페이지에 연결되는 하이퍼링크를 목차에 생성할 수 있습니다. 이는 PDF 문서의 상호 작용 및 탐색을 향상시킵니다.

#### Q: .NET용 Aspose.PDF는 PDF/A 표준과 호환됩니까?

A: 예, .NET용 Aspose.PDF는 PDF/A-1, PDF/A-2 및 PDF/A-3을 포함한 PDF/A 표준을 지원합니다. 보관 및 장기 보존 요구 사항을 준수하는 PDF 문서를 만들 수 있습니다.

#### Q: 목차 항목에 글꼴 스타일이나 색상 등 서식을 더 추가할 수 있나요?

A: 예, .NET용 Aspose.PDF를 사용하여 글꼴 스타일, 색상, 글꼴 크기 등 목차 항목에 추가 서식을 추가할 수 있습니다. 이를 통해 요구 사항에 따라 TOC의 모양을 사용자 정의할 수 있습니다.
