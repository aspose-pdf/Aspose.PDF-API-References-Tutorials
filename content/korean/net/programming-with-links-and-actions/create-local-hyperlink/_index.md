---
title: PDF 파일에 로컬 하이퍼링크 만들기
linktitle: PDF 파일에 로컬 하이퍼링크 만들기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 로컬 하이퍼링크를 쉽게 만들 수 있습니다.
type: docs
weight: 40
url: /ko/net/programming-with-links-and-actions/create-local-hyperlink/
---
PDF 파일에 로컬 하이퍼링크를 만들면 사용자를 동일한 PDF 문서의 다른 페이지로 안내하는 클릭 가능한 링크를 만들 수 있습니다. Aspose.PDF for .NET을 사용하면 다음 소스 코드를 따라 이러한 링크를 쉽게 만들 수 있습니다.

## 1단계: 필요한 라이브러리 가져오기

시작하기 전에 C# 프로젝트에 필요한 라이브러리를 가져와야 합니다. 필요한 가져오기 지시문은 다음과 같습니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## 2단계: 문서 폴더 경로 설정

 이 단계에서는 결과 PDF 파일을 저장할 폴더 경로를 지정해야 합니다. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 다음 코드에서는 문서 폴더의 실제 경로를 사용합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3단계: Document 인스턴스 생성

 우리는 인스턴스를 생성할 것입니다`Document` PDF 문서를 나타내는 클래스입니다. 해당 코드는 다음과 같습니다.

```csharp
Document doc = new Document();
```

## 4단계: 하이퍼링크가 있는 페이지 및 텍스트 추가

이 단계에서는 PDF 문서에 페이지를 추가하고 로컬 하이퍼링크가 포함된 텍스트를 추가합니다. 각 링크에 대한 대상 페이지를 정의합니다. 해당 코드는 다음과 같습니다.

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## 5단계: 업데이트된 문서 저장

이제 업데이트된 PDF 파일을 다음을 사용하여 저장해 보겠습니다.`Save` 의 방법`doc` 객체입니다. 해당 코드는 다음과 같습니다.

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 로컬 하이퍼링크 만들기 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 인스턴스 생성
Document doc = new Document();
// PDF 파일의 페이지 컬렉션에 페이지 추가
Page page = doc.Pages.Add();
// Text Fragment 인스턴스 생성
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// 로컬 하이퍼링크 인스턴스 생성
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// 링크 인스턴스에 대한 대상 페이지 설정
link.TargetPageNumber = 7;
// TextFragment 하이퍼링크 설정
text.Hyperlink = link;
// 페이지의 문단 컬렉션에 텍스트 추가
page.Paragraphs.Add(text);
// 새로운 TextFragment 인스턴스를 만듭니다.
text = new TextFragment("link page number test to page 1");
// TextFragment는 새 페이지에 추가되어야 합니다.
text.IsInNewPage = true;
// 다른 로컬 하이퍼링크 인스턴스를 만듭니다.
link = new LocalHyperlink();
// 두 번째 하이퍼링크에 대한 대상 페이지 설정
link.TargetPageNumber = 1;
// 두 번째 TextFragment에 대한 링크 설정
text.Hyperlink = link;
// 페이지 객체의 문단 컬렉션에 텍스트 추가
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// 업데이트된 문서 저장
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## 결론

축하합니다! 이제 Aspose.PDF for .NET을 사용하여 PDF에서 로컬 하이퍼링크를 만드는 단계별 가이드가 있습니다. 이 코드를 사용하여 사용자를 같은 문서의 다른 페이지로 안내하는 클릭 가능한 링크를 만들 수 있습니다.

고급 하이퍼링크 기능에 대한 자세한 내용은 공식 Aspose.PDF 문서를 확인하세요.

### PDF 파일에 로컬 하이퍼링크를 만드는 방법에 대한 FAQ

#### 질문: PDF 파일의 로컬 하이퍼링크란 무엇입니까?

A: PDF 파일의 로컬 하이퍼링크는 사용자를 동일한 문서 내의 다른 페이지로 안내하는 클릭 가능한 링크입니다. 이러한 링크는 탐색을 향상시키고 독자가 관련 섹션에 빠르게 액세스할 수 있도록 합니다.

#### 질문: 로컬 하이퍼링크는 PDF 문서에 어떤 이점이 있나요?

A: 로컬 하이퍼링크는 동일한 PDF 문서 내에서 관련 콘텐츠를 연결하는 효율적인 방법을 제공합니다. 이는 독자가 전체 문서를 스크롤하지 않고도 특정 섹션으로 빠르게 이동할 수 있도록 하여 사용자 경험을 개선합니다.

#### 질문: Aspose.PDF for .NET은 로컬 하이퍼링크 생성을 어떻게 지원하나요?
A: Aspose.PDF for .NET은 로컬 하이퍼링크를 만드는 데 대한 포괄적인 지원을 제공합니다. 이 가이드에 제공된 단계별 튜토리얼은 C#을 사용하여 PDF 문서에 로컬 하이퍼링크를 추가하는 방법을 보여줍니다.

#### 질문: 로컬 하이퍼링크의 모양을 사용자 지정할 수 있나요?

대답: 네, 로컬 하이퍼링크의 모양(텍스트 색상 및 스타일 포함)을 사용자 지정하여 문서 디자인과 일치하고 일관된 시각적 환경을 제공할 수 있습니다.

#### 질문: 단일 PDF 페이지 내에 여러 개의 로컬 하이퍼링크를 만들 수 있나요?

A: 물론입니다! 단일 PDF 페이지 내에 여러 로컬 하이퍼링크를 만들 수 있어 독자가 필요에 따라 다양한 섹션이나 페이지로 이동할 수 있습니다. 각 로컬 하이퍼링크는 해당 대상에 맞게 조정할 수 있습니다.

#### 질문: 로컬 하이퍼링크를 사용하여 페이지의 특정 섹션에 링크할 수 있나요?

A: 로컬 하이퍼링크는 일반적으로 전체 페이지로 이동하지만 PDF 문서 내에 앵커나 북마크를 만들어서 타겟 링크를 만들 수 있습니다. Aspose.PDF for .NET은 다양한 하이퍼링크 옵션을 지원합니다.

#### 질문: 로컬 하이퍼링크가 제대로 작동하는지 어떻게 확인할 수 있나요?

A: 제공된 튜토리얼과 샘플 코드를 따르면 자신 있게 기능적인 로컬 하이퍼링크를 만들 수 있습니다. 생성된 PDF 문서를 열고 하이퍼링크된 텍스트를 클릭하여 링크를 테스트할 수 있습니다.

#### 질문: 로컬 하이퍼링크를 사용할 때 제한이 있나요?

A: 로컬 하이퍼링크는 문서 탐색을 향상시키는 효과적인 방법이지만, 문서의 구조가 명확하고 직관적으로 유지되도록 하는 것이 중요합니다. 적절하게 레이블이 지정된 하이퍼링크와 앵커는 긍정적인 사용자 경험에 기여합니다.

#### 질문: 표나 이미지 내에 로컬 하이퍼링크를 만들 수 있나요?

A: 네, 표, 이미지, 텍스트를 포함하여 PDF 문서의 다양한 요소 내에 로컬 하이퍼링크를 만들 수 있습니다. Aspose.PDF for .NET은 다양한 유형의 콘텐츠에 하이퍼링크를 추가하는 데 유연성을 제공합니다.