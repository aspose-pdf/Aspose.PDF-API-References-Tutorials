---
title: 인라인 구조 요소
linktitle: 인라인 구조 요소
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF와 함께 온라인 구조 요소를 사용하는 방법에 대한 단계별 가이드입니다. 제목과 단락으로 PDF를 정리하세요.
type: docs
weight: 110
url: /ko/net/programming-with-tagged-pdf/inline-structure-elements/
---
이 단계별 가이드에서는 .NET용 Aspose.PDF와 함께 인라인 구조 요소를 사용하는 방법을 보여줍니다. Aspose.PDF는 프로그래밍 방식으로 PDF 문서를 조작할 수 있는 강력한 라이브러리입니다. 인라인 구조 요소를 사용하면 다양한 수준과 단락의 제목을 사용하여 PDF 문서에 계층 구조를 만들 수 있습니다.

코드를 자세히 살펴보고 Aspose.PDF for .NET에서 인라인 구조 요소를 사용하는 방법을 알아보세요.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. .NET용 Aspose.PDF 라이브러리가 설치되었습니다.
2. C# 프로그래밍 언어에 대한 기본 지식입니다.

## 1단계: 환경 설정

시작하려면 C# 개발 환경을 열고 새 프로젝트를 만듭니다. 프로젝트에 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가했는지 확인하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
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
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## 5단계: 온라인으로 구조 요소 추가

이제 다양한 수준의 제목과 단락과 같은 인라인 구조 요소를 문서에 추가하겠습니다.

```csharp
// 루트 구조 요소 가져오기
StructureElement rootElement = taggedContent.RootElement;

// 다양한 수준의 헤더 추가
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// 각 헤더에 콘텐츠 추가
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// 단락 추가
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// 단락에 내용 추가
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

여기서는 다양한 수준의 제목 및 단락과 같은 인라인 구조 요소를 만들고 여기에 콘텐츠를 추가합니다.

## 6단계: 태그가 있는 PDF 문서 저장

마지막으로 태그가 지정된 PDF 문서를 저장합니다.

```csharp
// 태그가 있는 PDF 문서 저장
document.Save(dataDir + "InlineStructureElements.pdf");
```

### .NET용 Aspose.PDF를 사용하는 인라인 구조 요소의 샘플 소스 코드 

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF 문서 만들기
Document document = new Document();

// TaggedPdf로 작업할 콘텐츠 가져오기
ITaggedContent taggedContent = document.TaggedContent;

// Documnet의 제목 및 언어 설정
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// 루트 구조 요소 가져오기
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// 태그가 있는 PDF 문서 저장
document.Save(dataDir + "InlineStructureElements.pdf");

```

## 결론

축하합니다! .NET용 Aspose.PDF와 함께 인라인 구조 요소를 사용하는 방법을 배웠습니다. 이제 다양한 수준과 단락의 제목을 사용하여 PDF 문서에 계층 구조를 만들 수 있습니다. Aspose.PDF의 더 많은 기능을 탐색하여 잠재력을 최대한 알아보세요.

### FAQ

#### Q: PDF 문서의 인라인 구조 요소는 무엇이며 계층 구조를 만드는 데 어떻게 기여합니까?

A: PDF 문서의 인라인 구조 요소(예: 다양한 수준의 제목 및 단락)는 콘텐츠를 구조화된 방식으로 구성하고 표시하는 계층 구조를 만드는 데 사용됩니다. 이러한 요소를 사용하면 문서 내에서 명확한 계층 구조와 정보 흐름을 설정할 수 있습니다.

#### Q: 인라인 구조 요소는 어떻게 PDF 문서의 가독성과 구성을 향상시킬 수 있습니까?

답변: 인라인 구조 요소, 특히 제목과 단락은 논리적 구조를 제공하여 PDF 문서의 가독성과 구성을 향상시키는 데 도움이 됩니다. 제목은 다양한 수준의 중요도를 나타내며 독자가 콘텐츠를 탐색하는 데 도움이 되는 반면 단락은 관련 정보를 함께 그룹화합니다.

#### Q: .NET용 Aspose.PDF는 인라인 구조 요소의 사용을 어떻게 촉진합니까?

A: .NET용 Aspose.PDF는 제목 및 단락과 같은 인라인 구조 요소를 생성하고 조작하는 클래스와 메서드를 제공합니다. 이러한 요소는 사용자 정의하고, 계층적으로 구성하고, 콘텐츠를 풍부하게 하여 문서의 시각적 표현과 접근성을 향상시킬 수 있습니다.

####  Q: 이 프로그램의 목적은 무엇입니까?`taggedContent` object in relation to inline structure elements?

 답:`taggedContent` 에서 얻은 객체`TaggedContent` a의 속성`Document`를 사용하면 인라인 구조 요소를 포함한 구조화된 요소로 작업할 수 있습니다. 문서 내에서 제목과 단락을 만들고, 사용자 정의하고, 구성할 수 있습니다.

#### Q: 인라인 구조 요소는 명확한 문서 계층 구조를 만드는 데 어떻게 도움이 됩니까?

A: 다양한 수준의 제목과 같은 인라인 구조 요소는 문서에서 명확하고 잘 정의된 계층 구조를 설정하는 데 도움이 됩니다. 독자는 주요 주제, 하위 주제 및 관련 콘텐츠를 빠르게 식별할 수 있으므로 문서를 더 쉽게 탐색하고 이해할 수 있습니다.

#### Q: .NET용 Aspose.PDF를 사용하여 인라인 구조 요소의 모양과 형식을 사용자 정의할 수 있습니까?

A: 예, 인라인 구조 요소의 모양과 형식을 사용자 정의할 수 있습니다. 제목과 단락에 대해 원하는 시각적 표현을 얻기 위해 글꼴 스타일, 크기, 색상, 정렬, 들여쓰기 및 간격과 같은 속성을 설정할 수 있습니다.

#### Q: .NET용 Aspose.PDF의 인라인 구조 요소를 사용하여 PDF 문서에 다양한 수준의 제목을 만들고 추가하려면 어떻게 해야 합니까?

 A: 다음을 사용하여 다양한 수준의 제목을 만들 수 있습니다.`CreateHeaderElement` 메소드를 루트 구조 요소에 추가합니다. 그런 다음 다음을 사용하여 각 제목 요소에 콘텐츠를 추가할 수 있습니다.`CreateSpanElement` 텍스트 범위를 만드는 방법입니다.

#### Q: 인라인 구조 요소를 사용하여 PDF 문서에서 목록, 글머리 기호 또는 기타 유형의 콘텐츠 구성을 만들 수 있습니까?

A: 인라인 구조 요소 자체는 주로 제목과 단락에 사용되지만 Aspose.PDF for .NET에서 제공하는 다른 기능과 함께 사용하여 포괄적인 구성을 위한 목록, 글머리 기호, 표 및 기타 유형의 콘텐츠 구성을 만들 수 있습니다. 문서 구조.

#### Q: 인라인 구조 요소는 문서 접근성에 어떻게 기여합니까?

A: 인라인 구조 요소는 문서 접근성을 향상시키는 데 중요한 역할을 합니다. 적절하게 구조화된 제목과 단락은 스크린 리더와 기타 보조 기술이 장애가 있는 사용자에게 콘텐츠를 정확하게 해석하고 전달하는 데 도움이 되는 명확한 문서 계층 구조를 제공합니다.

#### Q: 대화형 요소 생성, 멀티미디어 삽입 등 인라인 구조 요소의 고급 사용을 탐색할 수 있습니까?

답: 물론이죠! 이 튜토리얼은 제목과 단락 생성에 중점을 두고 있지만 .NET용 Aspose.PDF는 대화형 요소 생성, 멀티미디어 포함, 하이퍼링크 추가 등을 위한 고급 기능을 제공합니다. 이러한 고급 기능을 자세히 알아보려면 라이브러리의 문서와 예제를 확인하세요.