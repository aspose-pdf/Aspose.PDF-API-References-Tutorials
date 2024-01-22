---
title: PDF 파일에 목차 추가
linktitle: PDF 파일에 목차 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에 목차를 추가하는 방법을 알아보세요. 예제 소스 코드가 포함된 단계별 가이드입니다. 문서 탐색 기능을 강화하세요!
type: docs
weight: 40
url: /ko/net/programming-with-document/addtoc/
---
이 튜토리얼에서는 .NET용 Aspose.PDF의 PDF 파일에 목차(목차) 추가 기능을 사용하여 PDF 문서에 목차를 추가하는 방법을 살펴보겠습니다. 단계별 가이드를 제공하고 이를 달성하는 데 필요한 C# 소스 코드를 설명합니다. 이 튜토리얼이 끝나면 Aspose.PDF for .NET을 사용하여 목차가 포함된 PDF 문서를 생성할 수 있습니다.


## 1단계: 기존 PDF 파일 로드

 시작하려면 기존 PDF 파일을 로드해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 다음 코드에 PDF 파일의 실제 경로를 입력하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## 2단계: 목차를 위한 새 페이지 만들기

목차를 보관할 새 페이지를 만듭니다. 다음 코드는 인덱스 1에 새 페이지를 삽입합니다.

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## 3단계: 목차 정보 정의

다음으로 목차 정보를 정의해야 합니다. 목차의 제목과 기타 속성을 설정하겠습니다. 다음 코드를 추가하세요.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## 4단계: TOC 요소 생성

이제 목차의 요소를 만들어 보겠습니다. 이 튜토리얼에서는 서로 다른 페이지에 해당하는 4개의 TOC 요소를 생성합니다. 요구 사항에 따라 다음 코드를 수정합니다.

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## 5단계: 업데이트된 문서 저장

 마지막으로 수정된 문서를 목차와 함께 저장해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 원하는 출력 파일 경로를 사용하여 아래 코드에:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### .NET용 Aspose.PDF를 사용하여 PDF 문서에 TOC를 추가하는 예제 소스 코드

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 기존 PDF 파일 로드
Document doc = new Document(dataDir + "AddTOC.pdf");

// PDF 파일의 첫 번째 페이지에 액세스
Page tocPage = doc.Pages.Insert(1);

// TOC 정보를 나타내는 객체 생성
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// TOC 제목 설정
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//TOC 요소로 사용될 문자열 개체를 만듭니다.
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// 제목 개체 만들기
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// 제목 개체의 대상 페이지 지정
	heading2.DestinationPage = doc.Pages[i + 2];

	// 목적지 페이지
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// 목적지 좌표
	segment2.Text = titles[i];

	// TOC가 포함된 페이지에 제목 추가
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// 업데이트된 문서 저장
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에 목차(TOC)를 추가하는 방법을 살펴보았습니다. 단계별 가이드를 따르고 제공된 C# 소스 코드를 활용하면 목차가 포함된 PDF 문서를 쉽게 생성할 수 있습니다. TOC는 문서의 유용성을 향상시켜 사용자가 특정 섹션이나 페이지를 보다 효율적으로 탐색할 수 있도록 합니다. .NET용 Aspose.PDF는 .NET 응용 프로그램에서 PDF 파일 작업을 위한 강력하고 사용자 친화적인 솔루션을 제공하므로 동적 및 대화형 PDF 문서를 쉽게 만들 수 있습니다.

### PDF 파일에 목차 추가에 대한 FAQ

#### Q: .NET용 Aspose.PDF이 무엇인가요?

A: Aspose.PDF for .NET은 개발자가 .NET 애플리케이션에서 PDF 파일을 효과적으로 작업할 수 있게 해주는 강력한 라이브러리입니다. PDF 문서를 프로그래밍 방식으로 생성, 조작 및 관리하기 위한 광범위한 기능을 제공합니다.

#### Q: PDF 문서에 목차(TOC)를 추가하는 목적은 무엇입니까?

A: 목차(TOC)는 사용자가 PDF 문서 내의 특정 섹션이나 페이지로 빠르게 이동할 수 있도록 탐색 지원을 제공합니다. 문서의 유용성과 사용자 경험을 향상시킵니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서에 목차를 어떻게 추가합니까?

A: .NET용 Aspose.PDF를 사용하여 PDF 문서에 목차를 추가하려면 목차를 담을 새 페이지를 만들고 목차 정보를 정의한 다음 특정 페이지에 해당하는 목차 요소를 만들어야 합니다. 문서의 섹션.

#### Q: 목차의 모양을 사용자 정의할 수 있나요?

A: 예, 글꼴 크기, 글꼴 스타일, 정렬 등 목차 요소의 다양한 속성을 설정하여 목차의 모양을 사용자 정의할 수 있습니다. .NET용 Aspose.PDF는 원하는 모양과 느낌에 맞게 TOC를 설계하는 유연성을 제공합니다.

#### Q: Aspose.PDF for .NET은 PDF 문서에 고급 기능을 추가하는 데 적합합니까?

A: 물론입니다. .NET용 Aspose.PDF는 대화형 요소, 양식 필드, 디지털 서명 등을 포함하여 PDF 문서에 고급 기능을 추가할 수 있는 기능이 풍부한 라이브러리입니다.