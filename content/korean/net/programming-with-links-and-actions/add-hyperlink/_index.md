---
title: PDF 파일에 하이퍼링크 추가
linktitle: PDF 파일에 하이퍼링크 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF에 하이퍼링크를 쉽게 추가하는 방법을 알아보세요. 문서에서 상호 작용성과 사용자 참여를 강화하세요.
type: docs
weight: 10
url: /ko/net/programming-with-links-and-actions/add-hyperlink/
---
## 소개

PDF 파일에 하이퍼링크를 추가하면 문서의 상호 작용성과 탐색성이 크게 향상될 수 있습니다. 결제 포털에 연결되는 송장을 만들든 독자를 관련 온라인 리소스로 안내하는 보고서를 만들든, 하이퍼링크는 PDF를 더욱 사용자 친화적으로 만드는 기능 계층을 추가할 수 있습니다. 이 가이드에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 하이퍼링크를 원활하게 추가하는 방법을 보여드리겠습니다. 그러니 소매를 걷어붙이세요. 모든 것을 하나하나, 단계별로 배우게 될 겁니다!

## 필수 조건

하이퍼링크 추가의 세부적인 내용을 살펴보기 전에 반드시 확인해야 할 몇 가지 전제 조건이 있습니다.

1. .NET Framework 설치: 컴퓨터에 호환되는 .NET Framework가 설치되어 있는지 확인하세요. Aspose.PDF는 다양한 버전과 호환되므로 사용 중인 버전과의 호환성을 확인하세요.
2.  .NET 라이브러리용 Aspose.PDF: Aspose.PDF 라이브러리가 필요합니다. 다음에서 다운로드할 수 있습니다.[다운로드 페이지](https://releases.aspose.com/pdf/net/) 아직 하지 않았다면.
3. 기본 C# 지식: C# 프로그래밍에 익숙하다면 이 튜토리얼을 더 매끄럽고 이해하기 쉽게 이해할 수 있습니다.
4. 개발 환경: Visual Studio와 같은 IDE를 설정하여 코드를 작성하고 실행하세요.

이러한 전제 조건을 충족하면 계속 진행할 준비가 된 것입니다!

## 패키지 가져오기

Aspose.PDF로 작업하려면 관련 네임스페이스를 C# 프로젝트로 가져와야 합니다. 프로젝트를 열고 C# 파일의 맨 위에 다음 using 지시문을 추가합니다.

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

이제 PDF에 하이퍼링크를 추가하는 단계별 과정을 살펴보겠습니다.

## 1단계: 문서 디렉토리 설정

가장 먼저 해야 할 일은 PDF 파일이 상주할 작업 디렉토리를 설정하는 것입니다. 방법은 다음과 같습니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`YOUR DOCUMENT DIRECTORY` PDF를 저장하려는 실제 경로와 함께. 이 경로는 PDF를 읽고 쓸 때 파일을 탐색하는 데 도움이 됩니다.

## 2단계: 기존 PDF 문서 열기

 다음으로, 하이퍼링크를 추가하려는 PDF 파일을 열어 보겠습니다. 기존 PDF는 다음을 사용하여 열 수 있습니다.`Document` Aspose.PDF 라이브러리의 클래스입니다.

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

 이 스니펫은 PDF 파일을 읽고 수정을 위해 준비합니다.`"AddHyperlink.pdf"` 지정한 디렉토리에 존재하거나 파일 이름을 적절히 조정하세요.

## 3단계: PDF 페이지에 액세스

이제 하이퍼링크가 나타날 문서 내의 페이지를 선택해야 합니다. 예를 들어, 첫 번째 페이지에 링크를 추가하는 경우:

```csharp
Page page = document.Pages[1];
```

Aspose의 페이지 인덱스는 0이 아니라 1부터 시작한다는 걸 기억하세요. 그러므로 첫 번째 페이지는 페이지 1입니다.

## 4단계: 링크 주석 개체 만들기

다음으로, 하이퍼링크를 클릭할 수 있는 사각형 영역을 정의해야 합니다. 필요에 따라 이 영역을 사용자 정의할 수 있습니다.

```csharp
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
```

 여기서 우리는 시작점에서 시작하는 사각형을 만들고 있습니다.`(100, 100)` 그리고 뻗어있다`(300, 300)`. 이 숫자를 조정하여 링크의 크기와 위치를 수정하세요.

## 5단계: 링크 테두리 구성

이제 링크 영역이 설정되었으므로 시각적 스타일을 지정해야 합니다. 테두리를 만들 수 있지만 이 경우에는 보이지 않게 설정하겠습니다.

```csharp
Border border = new Border(link);
border.Width = 0;
link.Border = border;
```

이렇게 하면 PDF 디자인과 깔끔하게 어울리는 보이지 않는 링크 테두리가 생성됩니다.

## 6단계: 하이퍼링크 동작 지정

사용자가 이 링크를 클릭하면 어떤 일이 일어나는지 지정해야 합니다. 예를 들어, 사용자를 Aspose 웹사이트로 안내하겠습니다.

```csharp
link.Action = new GoToURIAction("http://www.aspose.com");
```

 꼭 사용해보세요`"http://"` 웹 주소의 시작 부분에 넣어서는 안 됩니다. 그렇지 않으면 제대로 작동하지 않을 수 있습니다.

## 7단계: 페이지에 링크 주석 추가

이 시점에서 특정 페이지의 주석 컬렉션에 하이퍼링크를 추가하여 우리가 만든 모든 것을 실행해 보겠습니다.

```csharp
page.Annotations.Add(link);
```

이 줄을 통해 하이퍼링크가 준비되고 사용자 상호 작용을 기다리게 됩니다!

## 8단계: 자유 텍스트 주석 만들기

하이퍼링크에 텍스트 컨텍스트를 추가하는 것이 좋습니다. 이렇게 하면 사용자가 무엇을 클릭하는지 이해하는 데 도움이 됩니다. FreeText 주석을 추가해 보겠습니다.

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(FontRepository.FindFont("TimesNewRoman"), 10, Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation.Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

여기서 텍스트의 글꼴, 크기, 색상을 정의합니다. 디자인 요구 사항에 따라 이러한 속성을 조정할 수 있습니다.

## 9단계: 문서 저장

하이퍼링크부터 텍스트 주석까지 모든 것을 추가한 후에는 모든 변경 사항이 반영되도록 문서를 저장해야 합니다.

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document.Save(dataDir);
```

 이렇게 하면 업데이트된 PDF가 새 파일로 저장됩니다.`"AddHyperlink_out.pdf"` 귀하가 지정한 디렉토리에 있습니다.

## 결론

Aspose.PDF for .NET을 사용하여 PDF 문서에 하이퍼링크를 추가하면 PDF의 전문성이 높아질 뿐만 아니라 사용자 참여도 향상됩니다. 쉽게 할 수 있으며 정적 문서에서는 따라올 수 없는 완전히 새로운 수준의 상호 작용성을 제공합니다. 이 가이드에 설명된 단계를 사용하면 만들거나 수정하는 모든 PDF에 자신 있게 하이퍼링크를 추가할 수 있습니다. 

## 자주 묻는 질문

### 하이퍼링크의 스타일을 다르게 지정할 수 있나요?  
네, 다양한 글꼴, 색상, 테두리 스타일을 사용하여 하이퍼링크와 텍스트의 모양을 변경할 수 있습니다.

### 내부 페이지에 링크를 걸려면 어떻게 해야 하나요?  
 사용할 수 있습니다`GoToAction` 대신에`GoToURIAction` PDF 내의 다른 페이지에 링크합니다.

### Aspose.PDF는 다른 파일 형식을 지원합니까?  
네, Aspose.PDF는 PDF 조작 및 변환을 위한 다양한 파일 형식과 기능을 지원합니다.

### 개발을 위한 임시 라이선스는 어떻게 받을 수 있나요?  
 임시 면허증은 다음 사이트를 방문하여 취득할 수 있습니다.[이 링크](https://purchase.aspose.com/temporary-license/).

### Aspose.PDF에 대한 더 많은 튜토리얼은 어디에서 찾을 수 있나요?  
더 많은 튜토리얼은 다음에서 찾을 수 있습니다.[선적 서류 비치](https://reference.aspose.com/pdf/net/).