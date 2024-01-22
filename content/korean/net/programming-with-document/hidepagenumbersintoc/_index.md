---
title: 목차에서 페이지 번호 숨기기
linktitle: 목차에서 페이지 번호 숨기기
second_title: .NET API 참조용 Aspose.PDF
description: 이 단계별 가이드를 통해 .NET용 Aspose.PDF를 사용하여 목차에서 페이지 번호를 숨기는 방법을 알아보세요.
type: docs
weight: 220
url: /ko/net/programming-with-document/hidepagenumbersintoc/
---
이 기사에서는 C#을 사용하여 .NET용 Aspose.PDF의 목차에서 페이지 번호 숨기기 기능 구현에 대해 설명합니다. .NET용 Aspose.PDF에 대한 간략한 소개로 시작한 다음 이 기능을 구현하기 위한 단계별 가이드를 살펴보겠습니다. 

## .NET용 Aspose.PDF 소개

.NET용 Aspose.PDF는 개발자가 프로그래밍 방식으로 PDF 파일을 생성, 편집 및 조작할 수 있는 강력한 PDF 조작 구성 요소입니다. PDF 문서 작업을 쉽게 할 수 있는 다양한 기능을 제공합니다. .NET용 Aspose.PDF는 32비트 및 64비트 운영 체제를 모두 지원하며 .NET Framework, .NET Core 및 Xamarin 플랫폼과 함께 사용할 수 있습니다. 

## 목차 기능에서 페이지 번호 숨기기란 무엇입니까?

목차(TOC)는 사용자에게 내용에 대한 빠른 개요를 제공하는 PDF 문서의 필수 부분입니다. 때때로 사용자는 목차를 보다 사용자 친화적으로 만들기 위해 목차에서 페이지 번호를 숨길 수 있습니다. .NET용 Aspose.PDF는 목차에서 페이지 번호를 숨기는 기능을 내장하고 있습니다. 이 기능을 사용하면 보다 사용자 친화적인 PDF 문서를 만들 수 있습니다. 

## 전제조건

이 튜토리얼을 따르려면 다음이 필요합니다.

- 비주얼 스튜디오 2010 이상
- 시스템에 설치된 .NET용 Aspose.PDF
- C# 프로그래밍 언어에 대한 기본 지식

## TOC에서 페이지 번호 숨기기 기능을 구현하기 위한 단계별 가이드

.NET용 Aspose.PDF를 사용하여 목차에서 페이지 번호 숨기기 기능을 구현하려면 아래 단계를 따르세요.

## 1단계: Visual Studio에서 새 C# 콘솔 애플리케이션 만들기

Visual Studio를 열고 새 C# 콘솔 애플리케이션을 만듭니다.

## 2단계: .NET용 Aspose.PDF에 대한 참조 추가

프로젝트의 참조 폴더를 마우스 오른쪽 버튼으로 클릭하고 참조 추가를 선택합니다. 시스템에 Aspose.PDF for .NET이 설치된 위치를 찾아 참조를 추가하세요.

## 1단계: 새 PDF 문서 만들기

다음 코드를 사용하여 새 PDF 문서를 만듭니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## 2단계: 목차 페이지 만들기

목차에 대한 새 페이지를 만들고 다음 코드를 사용하여 PDF 문서에 추가합니다.

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

## 4단계: 4개 수준 목록의 형식 정의

다음 코드를 사용하여 각 수준의 왼쪽 여백과 텍스트 형식 설정을 설정하여 4개 수준 목록의 형식을 정의합니다.

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

### .NET용 Aspose.PDF를 사용하여 TOC에서 페이지 번호 숨기기에 대한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//PDF 문서의 섹션 컬렉션에 목록 섹션을 추가합니다.
tocPage.TocInfo = tocInfo;
//왼쪽 여백을 설정하여 4개 수준 목록의 형식을 정의하고
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
//섹션에 4개의 제목을 추가하세요.
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

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 XMP 메타데이터로 작업하는 방법을 살펴보았습니다. XMP 메타데이터는 제목, 작성자, 생성 날짜 등을 포함하여 PDF 문서에 대한 귀중한 정보를 제공합니다. .NET용 Aspose.PDF를 사용하면 개발자가 이 메타데이터에 액세스하고 조작할 수 있으며 PDF 문서 작업을 위한 유연하고 강력한 API를 제공합니다.

### FAQ

#### Q: PDF 문서의 XMP 메타데이터란 무엇입니까?

A: PDF 문서의 XMP(Extensible Metadata Platform) 메타데이터는 문서에 대한 메타데이터 정보를 저장하기 위한 표준 형식입니다. 여기에는 문서 제목, 작성자, 작성 날짜, 키워드 등과 같은 세부 정보가 포함됩니다. XMP 메타데이터는 PDF 문서에 대한 정보를 저장하고 공유하는 체계적이고 표준화된 방법을 제공합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서의 XMP 메타데이터를 수정할 수 있습니까?

 A: 예, Aspose.PDF for .NET을 사용하여 프로그래밍 방식으로 PDF 문서의 XMP 메타데이터를 수정할 수 있습니다. 당신은 액세스할 수 있습니다`Info` 의 재산`Document` XMP 메타데이터 속성에 대한 액세스를 제공하는 개체입니다. 그런 다음 이러한 속성 값을 업데이트하여 PDF 문서의 XMP 메타데이터를 수정할 수 있습니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 사용자 정의 XMP 메타데이터 속성을 추출할 수 있습니까?

 A: 예, .NET용 Aspose.PDF를 사용하여 PDF 문서에서 사용자 정의 XMP 메타데이터 속성을 추출할 수 있습니다. 당신은 사용할 수 있습니다`Metadata` 의 재산`Document`PDF 문서의 모든 XMP 메타데이터 속성에 대한 액세스를 제공하는 개체입니다. 그런 다음 사용자 정의 속성을 추출하고 필요에 따라 해당 값을 사용할 수 있습니다.