---
title: PDF 파일에서 하이퍼링크 대상 가져오기
linktitle: PDF 파일에서 하이퍼링크 대상 가져오기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에서 하이퍼링크 대상을 추출하는 방법을 알아보세요.
type: docs
weight: 60
url: /ko/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF for .NET은 C# 프로그래밍 언어를 사용하여 PDF 파일에서 정보를 조작하고 추출하기 위한 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에서 하이퍼링크 대상을 추출하는 데 중점을 둡니다.

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- Visual Studio와 같은 통합 개발 환경(IDE).
- 컴퓨터에 .NET용 Aspose.PDF 라이브러리가 설치되어 있습니다.

## 1단계: 개발 환경 설정

코드 작성을 시작하기 전에 먼저 좋아하는 IDE에서 새 C# 프로젝트를 만들어 개발 환경을 설정해야 합니다.

## 2단계: Aspose.PDF 참조 가져오기

Aspose.PDF for .NET을 사용하려면 프로젝트에 적절한 참조를 추가해야 합니다. 다음 단계에 따라 필요한 참조를 가져오세요.

1. 프로젝트에서 "참조"를 마우스 오른쪽 버튼으로 클릭하고 "참조 추가"를 선택합니다.
2. "참조 추가" 창에서 .NET용 Aspose.PDF DLL 파일을 찾아 선택합니다.
3. "확인"을 클릭하여 참조를 프로젝트로 가져옵니다.

## 3단계: PDF 파일 로딩

하이퍼링크 대상을 추출하기 전에 PDF 파일을 애플리케이션에 로드해야 합니다. 다음 코드를 사용하여 PDF 파일을 로드합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// PDF 파일을 로드합니다
Document document = new Document(dataDir + "input.pdf");
```

처리하려는 PDF 파일과 문서 디렉토리의 올바른 경로를 지정하세요.

## 4단계: 문서 페이지 탐색

이제 PDF 파일이 로드되었으므로 문서의 모든 페이지를 살펴봐야 합니다. 이렇게 하면 다음을 얻을 수 있습니다.

각 페이지에 있는 하이퍼링크 주석. 다음 코드를 사용하여 문서의 페이지를 반복합니다.

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // 특정 페이지의 링크 주석 가져오기
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // 모든 링크를 저장할 목록을 만듭니다.
     IList<Annotation> list = selector. Selected;
     // 목록의 각 항목을 반복합니다.
     foreach(LinkAnnotation a in list)
     {
         // 목적지 URL 인쇄
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

이 코드는 문서의 각 페이지를 순환하며 각 페이지에 있는 하이퍼링크 주석을 선택합니다. 그런 다음 이러한 주석을 목록에 저장하고 각 링크의 대상 URL을 인쇄합니다.

## 5단계: 하이퍼링크 대상 얻기

마지막 단계는 하이퍼링크 주석에서 하이퍼링크 목적지를 추출하는 것입니다. 다음 코드는 이를 수행하는 방법을 보여줍니다.

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // 목적지를 원하는 대로 사용하세요
     }
}
```

이 코드에서 우리는 링크 주석에서 각 하이퍼링크 목적지를 가져와 변수에 목적지를 저장합니다. 그런 다음 이 목적지를 원하는 대로 애플리케이션에서 사용할 수 있습니다.

### .NET용 Aspose.PDF를 사용하여 하이퍼링크 대상 가져오기 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉토리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// PDF 파일을 로드합니다
	Document document = new Document(dataDir + "input.pdf");
	// PDF의 모든 페이지를 탐색합니다
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// 특정 페이지에서 링크 주석 가져오기
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// 모든 링크를 포함하는 목록을 만듭니다.
		IList<Annotation> list = selector.Selected;
		// 목록 내의 개별 항목을 반복합니다.
		foreach (LinkAnnotation a in list)
		{
			// 목적지 URL을 인쇄하세요
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

### PDF 파일에서 하이퍼링크 대상을 가져오기 위한 FAQ

#### 질문: PDF 파일의 하이퍼링크 대상이란 무엇인가요?

A: PDF 파일의 하이퍼링크 대상은 하이퍼링크가 가리키는 특정 위치 또는 대상입니다. URL, 같은 문서 내의 페이지 또는 외부 문서일 수 있습니다.

#### 질문: 하이퍼링크 대상을 추출하는 것이 PDF 문서 분석에 어떤 도움이 될까요?

A: 하이퍼링크 대상을 추출하면 PDF 문서 내에서 하이퍼링크가 가리키는 모든 대상을 식별하고 카탈로그화할 수 있습니다. 이 정보는 콘텐츠 검증, 링크 확인 및 데이터 분석에 유용할 수 있습니다.

#### 질문: Aspose.PDF for .NET은 하이퍼링크 대상 추출에 어떻게 도움이 되나요?

A: Aspose.PDF for .NET은 하이퍼링크 목적지를 쉽게 추출할 수 있는 강력한 API를 제공합니다. 이 튜토리얼은 C#을 사용하여 하이퍼링크 목적지를 추출하는 방법을 단계별로 보여줍니다.

#### 질문: 특정 기준에 따라 하이퍼링크 대상을 선택적으로 추출할 수 있나요?

대답: 네, PDF 문서의 페이지를 반복하면서 원하는 하이퍼링크 주석을 기준에 맞게 필터링하여 하이퍼링크 대상을 선택적으로 추출할 수 있습니다.

#### 질문: 암호로 보호된 PDF 문서에서 하이퍼링크 대상을 추출할 수 있나요?

대답: Aspose.PDF for .NET은 문서를 열 때 필요한 인증 자격 증명을 제공하는 한 암호로 보호된 PDF 문서에서 하이퍼링크 대상을 추출할 수 있습니다.

#### 질문: 추출된 하이퍼링크 대상을 내 응용프로그램에 어떻게 활용할 수 있나요?

답변: 하이퍼링크 대상을 추출한 후에는 링크 URL 검증, 보고서 작성, 사용자 지정 탐색 구현 등 다양한 작업을 수행하는 데 사용할 수 있습니다.

#### 질문: 하이퍼링크 대상을 추출할 때 제한이 있나요?

A: 하이퍼링크 목적지 추출이 강력하기는 하지만 PDF 문서의 구조를 고려하는 것이 필수적입니다. 복잡한 그래픽이나 멀티미디어 콘텐츠에 포함된 하이퍼링크는 추가 처리가 필요할 수 있습니다.

#### 질문: 링크 유형이나 좌표와 같은 하이퍼링크의 다른 속성을 추출할 수 있나요?

A: 이 튜토리얼은 하이퍼링크 목적지 추출에 초점을 맞춥니다. 그러나 Aspose.PDF 공식 문서를 참조하여 링크 유형 및 좌표 추출을 포함한 고급 기능을 살펴볼 수 있습니다.