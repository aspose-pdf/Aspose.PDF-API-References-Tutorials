---
title: Html에서 변환 후 하이퍼링크 제거
linktitle: Html에서 변환 후 하이퍼링크 제거
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 HTML을 PDF로 변환한 후 하이퍼링크를 제거하는 단계별 안내입니다.
type: docs
weight: 250
url: /ko/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 HTML 파일에서 생성된 PDF 파일에서 하이퍼링크를 제거하는 과정을 안내합니다. 하이퍼링크는 다른 페이지나 웹사이트로 리디렉션될 수 있는 클릭 가능한 링크입니다. 아래 단계에 따라 결과 PDF 파일에서 하이퍼링크를 제거할 수 있습니다.

## 전제조건
시작하기 전에 다음 전제 조건을 충족하는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- 시스템에 설치된 .NET용 Aspose.PDF 라이브러리.
- Visual Studio와 같은 개발 환경.

## 1단계: HTML 파일 로드 및 하이퍼링크 제거
이 단계에서는 HTML 파일을 로드하고 결과 PDF 문서에서 하이퍼링크를 제거합니다. 다음 코드를 사용하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// HTML 로딩 옵션을 사용하여 HTML 파일 로드
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// 문서 첫 페이지의 주석을 찾아보세요.
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // 주석이 링크인지 확인하세요.
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // 작업이 GoToURIAction 유형인지 확인하세요.
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // 텍스트 조각 흡수기를 사용하여 일치하는 텍스트 조각 찾기
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // 일치하는 텍스트 조각을 반복하고 하이퍼링크에서 속성을 제거합니다.
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // 페이지에서 주석을 제거합니다.
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 꼭 교체하세요`"YOUR DOCUMENTS DIRECTORY"` HTML 파일이 있는 실제 디렉토리를 사용합니다.

## 2단계: 결과 PDF 파일 저장
마지막으로 하이퍼링크 없이 결과 PDF 파일을 저장하겠습니다. 다음 코드를 사용하세요.

```csharp
// 결과 PDF 파일을 저장
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 위의 코드는 결과 PDF 파일을 파일 이름으로 저장합니다.`"RemoveHyperlinksFromText_out.pdf"`.

### .NET용 Aspose.PDF를 사용하여 Html에서 변환한 후 하이퍼링크 제거에 대한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## 결론
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 HTML 파일에서 생성된 PDF 파일에서 하이퍼링크를 제거하는 단계별 프로세스를 다루었습니다. 위에 설명된 지침을 따르면 결과 PDF 파일에서 하이퍼링크를 성공적으로 제거할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.PDF이 무엇인가요?

A: .NET용 Aspose.PDF는 개발자가 C# 애플리케이션에서 PDF 문서 작업을 할 수 있게 해주는 강력한 라이브러리입니다. HTML 파일을 PDF로 변환하고 PDF 콘텐츠를 조작하는 기능을 포함하여 광범위한 기능을 제공합니다.

#### Q: PDF 파일에서 하이퍼링크를 제거하려는 이유는 무엇입니까?

A: PDF 파일에서 하이퍼링크를 제거하는 데에는 여러 가지 이유가 있습니다. 예를 들어 인쇄 또는 보관 목적으로 외부 링크를 제거하거나 PDF 콘텐츠가 하이퍼링크를 통해 탐색되지 않도록 할 수 있습니다.

#### Q: .NET용 Aspose.PDF를 사용하여 HTML 파일을 로드하고 하이퍼링크를 제거하려면 어떻게 해야 합니까?

 A: HTML 파일을 로드하고 하이퍼링크를 제거하려면 .NET용 Aspose.PDF를 사용할 수 있습니다.`HtmlLoadOptions` 수업. PDF 페이지의 주석을 반복하여 링크 주석을 찾고 해당 속성을 수정합니다.

#### Q: 결과 PDF의 출력 파일 이름을 사용자 정의할 수 있습니까?

A: 예, PDF 문서를 저장하는 코드를 수정하여 결과 PDF 파일의 출력 파일 이름을 사용자 정의할 수 있습니다. 간단히 원하는 파일 이름을 변경하세요.`doc.Save()` 방법.

#### Q: 특정 기준에 따라 하이퍼링크를 선택적으로 제거할 수 있나요?

A: 예, 특정 기준에 따라 하이퍼링크를 선택적으로 제거할 수 있습니다. 예를 들어, 외부 링크나 특정 URL을 가리키는 링크만 제거하도록 선택할 수 있습니다.