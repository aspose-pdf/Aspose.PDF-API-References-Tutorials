---
title: 링크 구조 요소
linktitle: 링크 구조 요소
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF에서 링크 구조 요소를 만드는 방법을 알아보세요. 접근 가능한 링크, 이미지 및 규정 준수 검증을 추가하기 위한 단계별 가이드입니다.
type: docs
weight: 120
url: /ko/net/programming-with-tagged-pdf/link-structure-elements/
---
## 소개

PDF 내에서 링크 구조 요소를 만들고 관리하는 것은 접근성과 원활한 탐색이 필요한 문서에 매우 중요할 수 있습니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 이를 수행하는 방법을 안내해 드리겠습니다. Aspose.PDF나 PDF 조작에 익숙하지 않다면 걱정하지 마세요. 모든 단계를 자세히 설명하여 쉽게 따라할 수 있도록 하겠습니다!

## 필수 조건  

코딩에 들어가기 전에 먼저 몇 가지를 정리하겠습니다. 이는 원활한 개발 경험을 보장하기 위한 기본 요구 사항입니다.

1.  .NET용 Aspose.PDF: 최신 버전을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
2. .NET 개발 환경: Visual Studio나 .NET 호환 IDE를 설치하여 준비하세요.
3.  Aspose 라이센스: Aspose.PDF의 무료 평가판을 사용할 수 있습니다.[여기](https://releases.aspose.com/) 또는 획득하다[임시 면허](https://purchase.aspose.com/temporary-license/).
4. C#에 대한 기본 지식: C# 코드를 다루게 되므로 기본 사항을 이해하면 작업이 훨씬 수월해질 것입니다.

## 패키지 가져오기

링크 구조 요소에 대한 코드를 작성하기 전에 몇 가지 패키지를 가져와야 합니다. 프로젝트에서 필요한 Aspose.PDF 라이브러리를 참조하여 시작하세요.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

이러한 가져오기를 사용하면 PDF 문서 작업, 태그 추가, 구조 요소 관리가 가능합니다.

이제 다양한 유형의 링크 구조를 사용하여 PDF 문서를 만들어 보겠습니다. 각 단계를 나누어 과정을 철저히 이해하는 데 도움을 드리겠습니다.

## 1단계: 문서 초기화  

먼저, 새로운 PDF 문서를 만들고 접근성을 위해 태그가 지정된 콘텐츠를 설정해 보겠습니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// 새 PDF 문서 만들기
Document document = new Document(); 

// TaggedContent 인터페이스 검색
ITaggedContent taggedContent = document.TaggedContent;
```
  
 여기서 우리는 초기화하고 있습니다`Document` PDF 파일을 나타내는 객체입니다. 또한 다음을 검색합니다.`TaggedContent` 인터페이스를 통해 문단, 링크, 이미지 등의 구조적 요소를 추가할 수 있습니다.

## 2단계: 제목 및 언어 설정  

모든 PDF에는 제목과 언어 설정이 있어야 합니다. 특히 PDF/UA 표준을 준수하는 것이 목표라면 더욱 그렇습니다.

```csharp
// 문서 제목과 언어 설정
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
이 단계에서는 PDF에 의미 있는 제목이 있는지 확인하고 언어를 영어로 설정합니다(`en-US`). 이는 접근성에 중요하며 화면 판독기나 기타 보조 기술이 문서를 올바르게 해석할 수 있도록 합니다.

## 3단계: 문단 만들기 및 추가  

이 단계에서는 링크 요소를 담을 문단을 추가하겠습니다.

```csharp
// 루트 요소를 생성합니다
StructureElement rootElement = taggedContent.RootElement;

// 문단을 생성하여 루트 요소에 추가하세요
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
우리는 루트 구조 요소를 만듭니다. 이것은 본질적으로 다른 모든 요소의 최상위 컨테이너입니다. 그런 다음 문단(`p1`)을 루트 요소에 추가합니다.

## 4단계: 간단한 링크 추가  

이제 Google을 가리키는 기본 하이퍼링크를 추가해 보겠습니다.

```csharp
// 링크 요소를 생성하여 문단에 추가합니다.
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

// 링크에 대한 하이퍼링크 및 텍스트 설정
link1.Hyperlink = new WebHyperlink("http://"google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
이 단계에서는 링크 요소를 만들고, 하이퍼링크를 "http://google.com"으로 설정하고, 링크에 대한 텍스트("Google")를 제공했습니다. 또한 접근성을 보장하기 위해 대체 설명을 추가했습니다.

## 5단계: Span을 사용하여 링크 추가  

다양한 텍스트 범위를 사용하여 링크를 만들 수도 있습니다.

```csharp
// 다른 문단을 만드세요
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

// span 요소로 링크 생성
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://"google.com");

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
여기서는 span 요소를 사용하여 텍스트의 일부를 링크 안에 포함시켜서 링크의 특정 부분이 어떻게 표시되는지 사용자 지정할 수 있었습니다.

## 6단계: 다중 라인 링크  

링크 텍스트가 너무 길다면요? 걱정하지 마세요. 여러 줄로 나눌 수 있습니다.

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://"google.com");
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
이 경우에는 긴 텍스트 값을 설정하여 다중 줄 링크를 만들었고, 텍스트는 자동으로 여러 줄에 걸쳐 줄바꿈되었습니다.

## 7단계: 링크에 이미지 추가  

마지막으로, 링크 안에 이미지를 추가할 수도 있습니다.

```csharp
// 새로운 문단과 링크 요소를 만듭니다.
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://"google.com");

// 링크에 이미지를 추가하세요
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
이 단계에서는 이미지로 링크를 강화하는 방법을 보여줍니다. 이 경우 링크 내부에 Google 아이콘을 추가했습니다. 또한 이미지에 대한 대체 텍스트를 설정하여 접근성을 보장했습니다.

## 8단계: PDF의 규정 준수 여부 확인  

PDF/UA 규정 준수(접근성 표준)를 목표로 하는 경우 문서의 유효성을 검사하는 것이 좋습니다.

```csharp
// PDF 문서 저장
document.Save(outFile);

// PDF/UA 규정 준수를 위해 문서 검증
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
우리는 문서를 저장하고 PDF/UA 표준에 따라 검증했으며, 이를 통해 PDF가 접근성 요구 사항을 충족하는지 확인했습니다.

## 결론  

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 구조화된 PDF 문서를 만드는 방법을 다루었습니다. 기본 하이퍼링크를 추가하는 것부터 span, 다중 라인 링크, 심지어 이미지와 같은 더 복잡한 구조에 이르기까지, 이 가이드는 PDF에서 링크 요소를 조작하기 위한 견고한 기반을 제공합니다. PDF/UA 준수의 추가 이점을 통해 이제 액세스 가능하고 탐색 가능한 PDF를 만들 준비가 되었습니다.

## 자주 묻는 질문

### 링크 안에 표와 같은 더 복잡한 구조를 추가할 수 있나요?  
아니요. 링크는 주로 텍스트와 이미지에 적용되지만, 근처에 복잡한 요소를 포함할 수 있습니다.

### PDF/UA 검증은 필수입니까?  
항상 그런 것은 아니지만, 접근성이 걱정된다면 적극 권장됩니다.

### 이미지 파일 경로가 올바르지 않으면 어떻게 되나요?  
문서에 이미지가 표시되지 않으며 렌더링 중에 오류가 발생할 수 있습니다.

### 링크 내의 텍스트에 스타일을 지정할 수 있나요?  
네, span 요소를 사용하여 텍스트 스타일을 적용할 수 있습니다.

### 내부 문서 링크를 만드는 것이 가능합니까?  
물론입니다! 같은 문서 내의 특정 섹션에 링크할 수 있습니다.