---
title: PDF 파일에서 하이퍼링크 대상 가져오기
linktitle: PDF 파일에서 하이퍼링크 대상 가져오기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에서 하이퍼링크 대상을 추출하는 방법을 알아보세요.
type: docs
weight: 60
url: /ko/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF for .NET은 C# 프로그래밍 언어를 사용하여 PDF 파일의 정보를 조작하고 추출하기 위한 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에서 하이퍼링크 대상을 추출하는 데 중점을 둘 것입니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- Visual Studio와 같은 IDE(통합 개발 환경).
- 컴퓨터에 설치된 .NET용 Aspose.PDF 라이브러리.

## 1단계: 개발 환경 설정

코드 작성을 시작하기 전에 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만들어 개발 환경을 설정해야 합니다.

## 2단계: Aspose.PDF 참조 가져오기

.NET용 Aspose.PDF를 사용하려면 프로젝트에 적절한 참조를 추가해야 합니다. 필요한 참조를 가져오려면 아래 단계를 따르세요.

1. 프로젝트에서 "참조"를 마우스 오른쪽 버튼으로 클릭하고 "참조 추가"를 선택합니다.
2. "참조 추가" 창에서 Aspose.PDF for .NET의 DLL 파일을 찾아 선택합니다.
3. 참조를 프로젝트로 가져오려면 "확인"을 클릭하세요.

## 3단계: PDF 파일 로드

하이퍼링크 대상을 추출하려면 먼저 PDF 파일을 응용 프로그램에 로드해야 합니다. 다음 코드를 사용하여 PDF 파일을 로드합니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// PDF 파일 로드
Document document = new Document(dataDir + "input.pdf");
```

문서 디렉터리와 처리하려는 PDF 파일의 올바른 경로를 지정해야 합니다.

## 4단계: 문서 페이지 탐색

이제 PDF 파일이 로드되었으므로 문서의 모든 페이지를 살펴보아야 합니다. 이를 통해 다음을 얻을 수 있습니다.

각 페이지에 있는 하이퍼링크 주석입니다. 다음 코드를 사용하여 문서 페이지를 반복합니다.

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // 특정 페이지의 링크 주석 가져오기
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // 모든 링크를 저장하는 목록 만들기
     IList<Annotation> list = selector. Selected;
     // 목록의 각 항목을 반복합니다.
     foreach(LinkAnnotation a in list)
     {
         // 도착 URL 인쇄
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

이 코드는 문서의 각 페이지를 반복하면서 각 페이지에 있는 하이퍼링크 주석을 선택합니다. 그런 다음 이러한 주석을 목록에 저장하고 각 링크의 대상 URL을 인쇄합니다.

## 5단계: 하이퍼링크 대상 얻기

마지막 단계는 하이퍼링크 주석에서 하이퍼링크 대상을 추출하는 것입니다. 다음 코드는 이를 수행하는 방법을 보여줍니다.

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // 원하는 대로 목적지를 사용하세요
     }
}
```

이 코드에서는 링크 주석에서 각 하이퍼링크 대상을 가져오고 대상을 변수에 저장합니다. 그러면 애플리케이션에서 원하는 대로 이 대상을 사용할 수 있습니다.

### .NET용 Aspose.PDF를 사용하여 하이퍼링크 대상 가져오기의 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// PDF 파일 로드
	Document document = new Document(dataDir + "input.pdf");
	// PDF의 모든 페이지를 탐색합니다.
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// 특정 페이지에서 링크 주석 가져오기
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// 모든 링크를 포함하는 목록 만들기
		IList<Annotation> list = selector.Selected;
		// 목록 내부의 개별 항목을 반복합니다.
		foreach (LinkAnnotation a in list)
		{
			// 도착 URL을 인쇄하세요.
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

### PDF 파일에서 하이퍼링크 대상 가져오기에 대한 FAQ

#### Q: PDF 파일의 하이퍼링크 대상은 무엇입니까?

A: PDF 파일의 하이퍼링크 대상은 하이퍼링크가 가리키는 특정 위치 또는 대상입니다. URL, 동일한 문서 내의 페이지 또는 외부 문서일 수 있습니다.

#### Q: 하이퍼링크 대상을 추출하면 PDF 문서 분석에 어떤 이점이 있습니까?

A: 하이퍼링크 대상을 추출하면 PDF 문서 내에서 하이퍼링크가 가리키는 모든 대상을 식별하고 카탈로그화할 수 있습니다. 이 정보는 콘텐츠 유효성 검사, 링크 확인 및 데이터 분석에 유용할 수 있습니다.

#### Q: .NET용 Aspose.PDF는 하이퍼링크 대상 추출을 어떻게 지원합니까?

A: .NET용 Aspose.PDF는 하이퍼링크 대상을 쉽게 추출할 수 있는 강력한 API를 제공합니다. 이 자습서에서는 C#을 사용하여 하이퍼링크 대상을 추출하는 방법을 단계별로 보여줍니다.

#### Q: 특정 기준에 따라 하이퍼링크 대상을 선택적으로 추출할 수 있나요?

A: 예, PDF 문서의 페이지를 반복하고 기준에 따라 원하는 하이퍼링크 주석을 필터링하여 하이퍼링크 대상을 선택적으로 추출할 수 있습니다.

#### Q: 비밀번호로 보호된 PDF 문서에서 하이퍼링크 대상을 추출할 수 있습니까?

A: .NET용 Aspose.PDF는 문서를 열 때 필요한 인증 자격 증명을 제공하는 한 암호로 보호된 PDF 문서에서 하이퍼링크 대상을 추출할 수 있습니다.

#### Q: 내 애플리케이션에서 추출된 하이퍼링크 대상을 어떻게 활용할 수 있나요?

A: 하이퍼링크 대상을 추출한 후에는 이를 사용하여 링크 URL 확인, 보고서 생성 또는 사용자 정의 탐색 구현과 같은 다양한 작업을 수행할 수 있습니다.

#### Q: 하이퍼링크 대상을 추출할 때 제한 사항이 있나요?

A: 하이퍼링크 대상 추출은 강력하지만 PDF 문서의 구조를 고려하는 것이 중요합니다. 복잡한 그래픽이나 멀티미디어 콘텐츠에 포함된 하이퍼링크에는 추가 처리가 필요할 수 있습니다.

#### Q: 링크 유형이나 좌표 등 하이퍼링크의 다른 속성을 추출할 수 있습니까?

A: 튜토리얼은 하이퍼링크 대상 추출에 중점을 둡니다. 그러나 공식 Aspose.PDF 문서를 참조하여 링크 유형 및 좌표 추출을 포함한 고급 기능을 탐색할 수 있습니다.