---
title: TOC에서 페이지 번호 숨기기
linktitle: TOC에서 페이지 번호 숨기기
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 단계별 가이드를 통해 Aspose.PDF for .NET을 사용하여 목차에서 페이지 번호를 숨기는 방법을 알아보세요.
type: docs
weight: 220
url: /ko/net/programming-with-document/hidepagenumbersintoc/
---
이 글에서는 C#을 사용하여 Aspose.PDF for .NET의 TOC에서 페이지 번호 숨기기 기능 구현에 대해 논의합니다. Aspose.PDF for .NET에 대한 간략한 소개로 시작한 다음 이 기능을 구현하기 위한 단계별 가이드로 들어갑니다. 

## .NET용 Aspose.PDF 소개

Aspose.PDF for .NET은 개발자가 PDF 파일을 프로그래밍 방식으로 만들고, 편집하고, 조작할 수 있는 강력한 PDF 조작 구성 요소입니다. PDF 문서 작업을 쉽게 만드는 광범위한 기능과 기능을 제공합니다. Aspose.PDF for .NET은 32비트 및 64비트 운영 체제를 모두 지원하며 .NET Framework, .NET Core 및 Xamarin 플랫폼과 함께 사용할 수 있습니다. 

## TOC에서 페이지 번호 숨기기 기능이란 무엇인가요?

목차(TOC)는 사용자에게 콘텐츠에 대한 간략한 개요를 제공하는 PDF 문서의 필수적인 부분입니다. 때때로 사용자는 TOC에서 페이지 번호를 숨겨서 더 사용자 친화적으로 만들고 싶어할 수 있습니다. Aspose.PDF for .NET은 TOC에서 페이지 번호를 숨기는 기본 제공 기능을 제공합니다. 이 기능을 사용하면 더 사용자 친화적인 PDF 문서를 만들 수 있습니다. 

## 필수 조건

이 튜토리얼을 따르려면 다음이 필요합니다.

- Visual Studio 2010 이상
- 시스템에 설치된 .NET용 Aspose.PDF
- C# 프로그래밍 언어에 대한 기본 지식

## TOC에서 페이지 번호 숨기기 기능을 구현하기 위한 단계별 가이드

Aspose.PDF for .NET을 사용하여 TOC에서 페이지 번호 숨기기 기능을 구현하려면 아래 단계를 따르세요.

## 1단계: Visual Studio에서 새 C# 콘솔 애플리케이션 만들기

Visual Studio를 열고 새로운 C# 콘솔 애플리케이션을 만듭니다.

## 2단계: .NET용 Aspose.PDF에 대한 참조 추가

프로젝트의 References 폴더를 마우스 오른쪽 버튼으로 클릭하고 Add Reference를 선택합니다. Aspose.PDF for .NET이 시스템에 설치된 위치로 이동하여 참조를 추가합니다.

## 1단계: 새 PDF 문서 만들기

다음 코드를 사용하여 새 PDF 문서를 만듭니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## 2단계: TOC 페이지 만들기

다음 코드를 사용하여 TOC에 대한 새 페이지를 만들고 PDF 문서에 추가합니다.

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## 3단계: PDF 문서의 섹션 컬렉션에 목록 섹션 추가

다음 코드를 사용하여 PDF 문서의 섹션 컬렉션에 목록 섹션을 추가합니다.

```csharp
tocPage.TocInfo = tocInfo;
```

## 4단계: 4단계 목록의 형식 정의

다음 코드를 사용하여 각 레벨의 왼쪽 여백과 텍스트 형식 설정을 설정하여 4개 레벨 목록의 형식을 정의합니다.

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## 5단계: 섹션에 4개의 제목 추가

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### .NET용 Aspose.PDF를 사용하여 TOC에서 페이지 번호를 숨기기 위한 예제 소스 코드

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Pdf 문서의 섹션 컬렉션에 목록 섹션을 추가합니다.
tocPage.TocInfo = tocInfo;
//왼쪽 여백을 설정하여 4단계 목록의 형식을 정의합니다.
//각 레벨의 텍스트 형식 설정

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//섹션에 4개의 제목을 추가합니다.
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 XMP 메타데이터로 작업하는 방법을 살펴보았습니다. XMP 메타데이터는 제목, 작성자, 작성 날짜 등 PDF 문서에 대한 귀중한 정보를 제공합니다. Aspose.PDF for .NET을 사용하면 개발자가 이 메타데이터에 액세스하고 조작할 수 있어 PDF 문서 작업을 위한 유연하고 강력한 API를 제공합니다.

### 자주 묻는 질문

#### 질문: PDF 문서의 XMP 메타데이터란 무엇인가요?

A: PDF 문서의 XMP(Extensible Metadata Platform) 메타데이터는 문서에 대한 메타데이터 정보를 저장하기 위한 표준 형식입니다. 여기에는 문서 제목, 작성자, 생성 날짜, 키워드 등의 세부 정보가 포함됩니다. XMP 메타데이터는 PDF 문서에 대한 정보를 저장하고 공유하는 구조화되고 표준화된 방법을 제공합니다.

#### 질문: Aspose.PDF for .NET을 사용하여 PDF 문서의 XMP 메타데이터를 수정할 수 있나요?

 A: 네, Aspose.PDF for .NET을 사용하여 PDF 문서의 XMP 메타데이터를 프로그래밍 방식으로 수정할 수 있습니다.`Info` 의 속성`Document` XMP 메타데이터 속성에 액세스할 수 있는 개체입니다. 그런 다음 이러한 속성의 값을 업데이트하여 PDF 문서의 XMP 메타데이터를 수정할 수 있습니다.

#### 질문: Aspose.PDF for .NET을 사용하여 PDF 문서에서 사용자 정의 XMP 메타데이터 속성을 추출할 수 있습니까?

 A: 네, Aspose.PDF for .NET을 사용하여 PDF 문서에서 사용자 정의 XMP 메타데이터 속성을 추출할 수 있습니다. 다음을 사용할 수 있습니다.`Metadata` 의 속성`Document`PDF 문서의 모든 XMP 메타데이터 속성에 대한 액세스를 제공하는 개체입니다. 그런 다음 사용자 지정 속성을 추출하여 필요에 따라 해당 값을 사용할 수 있습니다.