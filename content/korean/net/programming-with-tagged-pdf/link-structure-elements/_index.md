---
title: 링크 구조 요소
linktitle: 링크 구조 요소
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF와 함께 링크 구조 요소를 사용하는 방법에 대한 단계별 가이드입니다. PDF 문서에 하이퍼링크를 만듭니다.
type: docs
weight: 120
url: /ko/net/programming-with-tagged-pdf/link-structure-elements/
---
이 단계별 가이드에서는 .NET용 Aspose.PDF와 함께 링크 구조 요소를 사용하는 방법을 보여줍니다. Aspose.PDF는 프로그래밍 방식으로 PDF 문서를 생성하고 조작할 수 있는 강력한 라이브러리입니다. 링크 구조 요소를 사용하면 PDF 문서에 하이퍼링크를 추가하여 사용자가 링크를 클릭하고 온라인 리소스로 이동할 수 있습니다.

코드를 자세히 살펴보고 Aspose.PDF for .NET에서 링크 구조 요소를 사용하는 방법을 알아보세요.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. .NET용 Aspose.PDF 라이브러리가 설치되었습니다.
2. C# 프로그래밍 언어에 대한 기본 지식입니다.

## 1단계: 환경 설정

시작하려면 C# 개발 환경을 열고 새 프로젝트를 만듭니다. 프로젝트에 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가했는지 확인하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## 2단계: 문서 만들기

 첫 번째 단계는 다음을 사용하여 새 PDF 문서를 만드는 것입니다.`Document` 수업.

```csharp
// PDF 문서 만들기
Document document = new Document();
```

## 3단계: 태그된 콘텐츠 작업

그런 다음 작업할 문서의 태그된 콘텐츠를 가져옵니다.

```csharp
// 문서의 태그된 콘텐츠 가져오기
ITaggedContent taggedContent = document.TaggedContent;
```

## 4단계: 문서 제목 및 언어 설정

이제 문서 제목과 언어를 설정할 수 있습니다.

```csharp
// 문서 제목 및 언어 정의
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## 5단계: 링크 구조 요소 추가

이제 문서에 링크 구조 요소를 추가해 보겠습니다. 간단한 텍스트 링크, 이미지 링크, 여러 줄 링크 등 다양한 유형의 링크를 만듭니다.
```csharp
// 루트 구조 요소(문서 구조 요소) 가져오기
StructureElement rootElement = taggedContent.RootElement;

// 하이퍼링크가 있는 단락 추가
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// 서식 있는 텍스트가 포함된 하이퍼링크가 있는 단락 추가
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// 부분적으로 서식이 지정된 텍스트가 포함된 하이퍼링크가 있는 단락 추가
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// 여러 줄 하이퍼링크가 있는 단락 추가
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// 이미지가 포함된 하이퍼링크가 있는 단락 추가
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## 6단계: 태그가 있는 PDF 문서 저장

마지막으로 태그가 지정된 PDF 문서를 저장합니다.

```csharp
// 태그가 있는 PDF 문서 저장
document. Save(outFile);
```

## 7단계: PDF/UA 규정 준수 확인

 또한 다음을 사용하여 문서의 PDF/UA 준수 여부를 확인할 수도 있습니다.`Validate` 의 방법`Document` 수업.

```csharp
// PDF/UA 규정 준수 확인
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### .NET용 Aspose.PDF를 사용하는 링크 구조 요소의 샘플 소스 코드 
```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// 문서 생성 및 태그된 PDF 콘텐츠 가져오기
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// 문서 제목 및 자연어 설정
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// 루트 구조 요소 가져오기(문서 구조 요소)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// 태그가 있는 PDF 문서 저장
document.Save(outFile);

// PDF/UA 준수 확인
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## 결론

축하합니다! .NET용 Aspose.PDF와 함께 링크 구조 요소를 사용하는 방법을 배웠습니다. 이제 PDF 문서에 하이퍼링크를 생성하여 사용자가 온라인 리소스로 이동할 수 있습니다. Aspose.PDF의 더 많은 기능을 실험하고 탐색하여 대화형의 풍부한 PDF 문서를 만드세요.

### FAQ

#### Q: PDF 문서의 링크 구조 요소는 무엇이며 문서 상호 작용성을 어떻게 향상합니까?

A: PDF 문서의 링크 구조 요소는 사용자가 온라인 리소스나 문서 내의 특정 위치로 이동할 수 있는 하이퍼링크를 만드는 데 사용됩니다. 이러한 요소는 사용자가 관련 콘텐츠나 외부 웹사이트에 액세스할 수 있는 클릭 가능한 링크를 제공하여 상호작용성을 향상시킵니다.

#### Q: PDF 문서에서 링크 구조 요소가 어떻게 도움이 됩니까?

답변: 링크 구조 요소는 PDF 문서를 대화형으로 만들어 사용자 경험을 향상시킵니다. 추가 정보, 관련 콘텐츠, 외부 웹 사이트 또는 문서 내의 특정 섹션에 대한 빠른 액세스를 제공하여 탐색을 개선하고 정보 검색을 용이하게 합니다.

#### Q: Aspose.PDF for .NET의 링크 구조 요소를 사용하여 다양한 유형의 하이퍼링크를 만들 수 있습니까?

A: 예, 링크 구조 요소를 사용하여 다양한 유형의 하이퍼링크를 생성할 수 있습니다. .NET용 Aspose.PDF를 사용하면 일반 텍스트, 서식 있는 텍스트, 이미지 및 여러 줄 설명이 포함된 하이퍼링크를 생성할 수 있어 문서 내의 외부 콘텐츠나 위치에 연결하는 방법에 대한 다양성을 제공합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 링크 구조 요소를 어떻게 설정하고 초기화합니까?

 A: 링크 구조 요소를 사용하려면 먼저 다음을 사용하여 새 PDF 문서를 만들어야 합니다.`Document` 수업. 그런 다음 다음을 사용하여 태그가 지정된 콘텐츠를 얻습니다.`TaggedContent`문서의 속성입니다. 여기에서 링크 구조 요소를 생성 및 사용자 정의하고 이를 루트 구조 요소에 추가할 수 있습니다.

#### Q: 링크 구조 요소를 사용하여 간단한 텍스트 하이퍼링크를 만들려면 어떻게 해야 합니까?
 A: 간단한 텍스트 하이퍼링크를 만들 수 있습니다.`LinkElement` 그리고 그것을 설정`Hyperlink` 재산을`WebHyperlink` 연결하려는 URL을 사용하세요. 다음을 사용하여 링크의 표시 텍스트를 설정할 수도 있습니다.`SetText` 방법.

#### Q: 링크 구조 요소를 사용하여 이미지로 하이퍼링크를 생성할 수 있나요?

 A: 예, 링크 구조 요소를 사용하여 이미지로 하이퍼링크를 만들 수 있습니다. 당신은`LinkElement` 그런 다음`FigureElement` 그것에 이미지가 있습니다. 이를 통해 이미지 기반 하이퍼링크를 만들 수 있습니다.

#### 질문: 하이퍼링크가 포함된 PDF 문서가 접근성에 대한 PDF/UA 표준을 준수하는지 어떻게 확인할 수 있습니까?

 A: .NET용 Aspose.PDF는 다음을 사용하여 PDF 문서가 PDF/UA 표준을 준수하는지 검증하는 기능을 제공합니다.`Validate` 의 방법`Document`수업. 이렇게 하면 장애가 있는 사용자가 문서의 하이퍼링크에 액세스할 수 있습니다.

#### Q: 링크 구조 요소에 대한 대체 설명은 무엇이며 왜 중요한가요?

A: 링크 구조 요소에 대한 대체 설명(대체 텍스트)은 하이퍼링크에 대한 텍스트 설명을 제공합니다. 이러한 설명은 시각 장애가 있는 사용자가 링크의 목적과 대상을 이해할 수 있도록 접근성을 위해 필수적입니다.

#### Q: 링크 구조 요소를 사용하여 생성된 하이퍼링크의 모양과 동작을 사용자 정의할 수 있습니까?

A: 링크 구조 요소는 주로 하이퍼링크 생성에 중점을 두고 있지만 Aspose.PDF for .NET에서 제공하는 다른 기능을 사용하면 하이퍼링크의 모양과 동작을 추가로 사용자 정의할 수 있습니다. 여기에는 색상, 스타일 및 링크 작업 지정이 포함됩니다.

#### 질문: 링크 구조 요소는 PDF 문서를 보다 대화형이고 사용자 친화적으로 만드는 데 어떻게 기여합니까?

A: 링크 구조 요소는 클릭 가능한 하이퍼링크를 추가하여 정적 PDF 문서를 대화형 환경으로 변환합니다. 이러한 상호 작용은 사용자 참여를 향상시키고, 관련 콘텐츠 간의 원활한 탐색을 가능하게 하며, 문서의 전반적인 유용성을 향상시킵니다.