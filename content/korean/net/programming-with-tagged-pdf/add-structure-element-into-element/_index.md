---
title: 요소에 구조 요소 추가
linktitle: 요소에 구조 요소 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서의 요소에 구조 요소를 추가하는 단계별 가이드입니다.
type: docs
weight: 20
url: /ko/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서의 요소에 구조 요소를 추가하는 방법에 대한 단계별 가이드를 제공합니다. Aspose.PDF는 PDF 문서를 프로그래밍 방식으로 생성, 조작 및 변환할 수 있는 강력한 라이브러리입니다. Aspose.PDF의 표시된 콘텐츠 구조 기능을 사용하면 PDF 문서에 계층 구조를 만들 수 있습니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. .NET 프레임워크와 함께 설치된 Visual Studio.
2. .NET용 Aspose.PDF 라이브러리.

## 1단계: 프로젝트 설정

시작하려면 Visual Studio에서 새 프로젝트를 만들고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하세요. Aspose 공식 웹사이트에서 라이브러리를 다운로드하여 컴퓨터에 설치할 수 있습니다.

## 2단계: 필요한 네임스페이스 가져오기

C# 코드 파일에서 Aspose.PDF에서 제공하는 클래스 및 메서드에 액세스하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 3단계: PDF 문서 만들기 및 구조화된 요소 정의

다음 코드를 사용하여 PDF 문서를 만들고 구조화된 요소를 정의합니다.

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

이 코드는 빈 PDF 문서를 만들고 단락 및 범위와 같은 구조화된 요소를 추가합니다. 각 구조 요소는 Aspose.PDF에서 제공하는 방법을 사용하여 생성됩니다.

## 4단계: PDF 문서 저장

PDF 문서를 저장하려면 다음 코드를 사용하십시오.

```csharp
document. Save(outFile);
```

이 코드는 구조화된 요소가 포함된 PDF 문서를 지정된 파일에 저장합니다.

### .NET용 Aspose.PDF를 사용하여 요소에 구조 요소 추가에 대한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// 문서 생성 및 태그된 PDF 콘텐츠 가져오기
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// 문서 제목 및 자연어 설정
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// 루트 구조 요소 가져오기(문서 구조 요소)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// 태그가 있는 PDF 문서 저장
document.Save(outFile);
// PDF/UA 준수 확인
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서의 요소에 구조 요소를 추가하는 방법을 배웠습니다. Aspose.PDF의 표시된 콘텐츠 구조 기능을 사용하면 PDF 문서에 계층 구조를 생성할 수 있으므로 콘텐츠를 더 쉽게 관리하고 탐색할 수 있습니다.

### FAQ

#### Q: Aspose.PDF for .NET을 사용하여 PDF 문서의 요소에 구조 요소를 추가하는 목적은 무엇입니까?

A: .NET용 Aspose.PDF를 사용하여 PDF 문서의 요소에 구조 요소를 추가하면 문서 내용 내에 계층 구조를 만들 수 있습니다. 이 계층 구조는 콘텐츠의 구성과 탐색을 향상시켜 특정 요소를 더 쉽게 관리하고 액세스할 수 있게 해줍니다.

#### Q: Aspose.PDF 라이브러리는 PDF 문서에 구조 요소를 추가하는 데 어떻게 도움이 됩니까?

A: .NET용 Aspose.PDF는 프로그래밍 방식으로 PDF 문서를 생성, 조작 및 변환하는 기능을 제공하는 강력한 라이브러리입니다. 이 튜토리얼에서는 라이브러리의 표시된 컨텐츠 구조 기능을 활용하여 PDF 문서 컨텐츠에 구조 요소를 생성하고 추가합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서에 구조 요소를 추가하기 위한 전제 조건은 무엇입니까?

A: 시작하기 전에 .NET 프레임워크와 함께 Visual Studio가 설치되어 있고 프로젝트에서 참조되는 .NET용 Aspose.PDF 라이브러리가 있는지 확인하세요.

#### Q: 제공된 C# 코드는 어떻게 구조 요소를 생성하고 PDF 문서 콘텐츠에 추가합니까?

답변: 코드는 PDF 문서를 생성하고, 루트 구조 요소를 정의하고, 단락 및 범위와 같은 다양한 구조적 요소를 추가하는 방법을 보여줍니다. 각 구조화된 요소는 Aspose.PDF에서 제공하는 방법을 사용하여 생성되므로 계층 구조를 구축할 수 있습니다.

#### Q: PDF 문서에 추가하는 구조 요소 유형을 사용자 정의할 수 있습니까?

A: 예, Aspose.PDF 라이브러리에서 제공하는 다양한 방법을 탐색하여 구조 요소 유형을 사용자 정의할 수 있습니다. 코드에서는 단락과 범위를 예로 보여주지만 필요에 따라 다른 유형의 구조화된 요소를 만들고 추가할 수 있습니다.

#### Q: 추가된 구조 요소 간의 계층 관계를 어떻게 정의합니까?

 A: 구조 요소 간의 계층 관계는 해당 요소를 상위 요소에 추가하는 순서에 따라 정의됩니다. 코드에서 부모-자식 관계는 다음을 사용하여 설정됩니다.`AppendChild` 방법.

#### Q: PDF 문서에 계층 구조를 만들면 어떤 이점이 있나요?

답변: PDF 문서에 계층 구조를 만들면 접근성, 탐색 및 구성이 향상됩니다. 이를 통해 보조 기술을 통해 문서의 내용을 더 잘 해석하고 전달할 수 있으므로 장애가 있는 개인이 더욱 사용자 친화적으로 만들 수 있습니다.

#### Q: 구조 요소를 추가한 후 PDF/UA 준수 여부를 어떻게 확인할 수 있습니까?

 A: 튜토리얼에 제공된 코드는 다음을 사용하여 PDF/UA 규정 준수를 검증하는 방법을 보여줍니다.`Validate` 방법. PDF/UA 표준에 따라 문서의 유효성을 검사하면 추가된 구조 요소가 접근성 지침을 준수하는지 확인할 수 있습니다.

#### Q: 이 접근 방식을 사용하여 기존 PDF 문서에 구조 요소를 추가할 수 있습니까?

A: 예, 기존 PDF 문서에 구조 요소를 추가하기 위해 제공된 접근 방식을 수정할 수 있습니다. 새 문서를 만드는 대신 Aspose.PDF를 사용하여 기존 문서를 로드한 다음 유사한 단계에 따라 구조 요소를 추가합니다.