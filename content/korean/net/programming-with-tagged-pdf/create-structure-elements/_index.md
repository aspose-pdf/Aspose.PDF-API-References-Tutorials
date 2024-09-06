---
title: 구조 요소 생성
linktitle: 구조 요소 생성
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 태그가 지정된 PDF 문서에 구조적 요소를 만드는 방법을 알아봅니다.
type: docs
weight: 60
url: /ko/net/programming-with-tagged-pdf/create-structure-elements/
---
다음 C# 소스 코드는 Aspose.PDF for .NET을 사용하여 구조 요소를 만듭니다. 아래 단계를 따라 코드 작동 방식을 이해합니다.

## 1단계: 필요한 라이브러리 가져오기

```csharp
using Aspose.Pdf;
```

## 2단계: 문서 디렉토리 정의

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

문서 디렉토리의 올바른 경로를 지정하세요.

## 3단계: PDF 문서 만들기

```csharp
Document document = new Document();
```

PDF 문서를 나타내는 새로운 Document 객체를 생성합니다.

## 4단계: TaggedPdf로 작업할 콘텐츠 가져오기

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

PDF 문서의 태그가 지정된 콘텐츠를 검색합니다. 이를 통해 구조적 요소를 조작할 수 있습니다.

## 5단계: 문서 제목 및 언어 설정

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

태그가 지정된 PDF 문서의 제목과 언어를 설정합니다. 이렇게 하면 문서의 접근성이 향상됩니다.

## 6단계: 그룹화 요소 만들기

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

PDF 문서의 콘텐츠를 그룹화하기 위해 다양한 구조적 요소를 만듭니다.

## 7단계: 문단 구조 요소 만들기

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

우리는 문단과 제목에 대한 블록 레벨 구조적 요소를 만듭니다. 위의 예는 레벨 1 헤더를 만드는 것을 보여줍니다.

## 8단계: 인라인 레벨 구조 요소 만들기

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

우리는 문단이나 제목 내부에 나타나는 텍스트 부분에 대해 인라인 레벨 구조 요소를 생성합니다.

## 9단계: 아트워크 구조 요소 만들기

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

우리는 문서에 나와 있는 그림과 수학 공식을 위한 구조적 요소를 만듭니다.

## 10단계: 태그가 지정된 PDF 문서 저장

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

생성된 구조 요소와 함께 태그가 지정된 PDF 문서를 저장합니다.

### .NET용 Aspose.PDF를 사용하여 구조 요소 생성을 위한 샘플 소스 코드 

```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF 문서 생성
Document document = new Document();
// TaggedPdf로 작업할 콘텐츠 가져오기
ITaggedContent taggedContent = document.TaggedContent;
// Documnet의 제목 및 언어 설정
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// 그룹화 요소 만들기
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// 텍스트 블록 수준 구조 요소 만들기
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// 텍스트 인라인 수준 구조 요소 만들기
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// 일러스트레이션 구조 요소 생성
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// 방법들이 개발 중입니다
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// 태그가 지정된 PDF 문서 저장
document.Save(dataDir + "StructureElements.pdf");

```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 태그가 지정된 PDF 문서에서 구조적 요소를 만드는 방법을 알아보았습니다. 구조적 요소는 문서 접근성을 개선하고 콘텐츠를 의미 있는 방식으로 구성하는 데 도움이 됩니다. 이제 이러한 지식을 사용하여 구조화되고 탐색하기 쉬운 PDF 문서를 만들 수 있습니다.

### 자주 묻는 질문

#### 질문: Aspose.PDF for .NET을 사용하여 PDF 문서에 구조 요소를 만드는 목적은 무엇입니까?

A: Aspose.PDF for .NET을 사용하여 PDF 문서에서 구조 요소를 만들면 문서 콘텐츠의 접근성과 구성이 향상됩니다. 구조 요소는 탐색, 의미론 및 보조 기술과의 호환성을 개선하는 계층적 구조를 제공합니다.

#### 질문: 제공된 C# 코드는 어떻게 PDF 문서에 구조 요소를 생성하나요?

A: 코드 예제는 그룹화 요소(예: 부분, 섹션 및 div), 블록 수준 요소(예: 문단 및 제목), 인라인 수준 요소(span, quote, note) 및 아트워크 요소(예: 그림 및 수식)를 포함한 다양한 유형의 구조 요소를 만드는 방법을 보여줍니다. 이러한 구조 요소는 콘텐츠를 구성하는 데 도움이 됩니다.

####  질문: 문서 제목과 언어를 설정하는 것이 중요한 이유는 무엇입니까?`SetTitle` and `SetLanguage` methods?

 A: 문서 제목 및 언어 설정`SetTitle` 그리고`SetLanguage`방법은 문서 접근성과 의미론을 개선합니다. 제목은 문서의 목적에 대한 간략한 설명을 제공하는 반면, 언어 속성은 언어별 렌더링과 접근성을 향상시킵니다.

####  질문: 그룹화 요소(예:`PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: 요소를 그룹화하면 PDF 문서 내에 계층 구조가 생성되어 관련 콘텐츠를 논리적으로 구성하고 그룹화할 수 있습니다. 이를 통해 탐색이 향상되고 사용자에게 명확한 구조가 제공됩니다.

#### 질문: 블록 수준 구조 요소와 인라인 수준 구조 요소는 무엇이며, 어떻게 다릅니까?

A: 블록 수준 구조 요소는 문단 및 제목과 같은 더 큰 콘텐츠 블록을 나타내는 반면, 인라인 수준 요소는 span, 인용문 및 메모와 같은 문단 또는 제목 내의 텍스트 부분을 나타냅니다. 이들은 콘텐츠의 계층 구조와 관계를 정의하는 데 도움이 됩니다.

####  질문: 아트워크는 어떻게 요소를 구성합니까?`FigureElement` and `FormulaElement`, contribute to the document?

A: 아트워크 구조 요소를 사용하면 문서에 그림, 그림 및 수학 공식을 추가할 수 있습니다. 시각적 및 수학적 콘텐츠를 포함하는 구조화된 방법을 제공합니다.

#### 질문: 비슷한 기술을 사용해 목록, 표, 주석 등 다른 유형의 구조 요소를 만들 수 있나요?

A: 네, 유사한 기술을 사용하여 목록, 표, 주석, 참조 등과 같은 다른 유형의 구조 요소를 만들 수 있습니다. Aspose.PDF는 광범위한 구조 요소 생성 방법을 제공합니다.

####  질문: 태그가 지정된 PDF 문서를 저장하는 방법은 무엇입니까?`Save` method ensure the preservation of structure elements?

 A: 그`Save` 이 방법은 생성된 구조 요소와 함께 PDF 문서를 저장하여 접근성과 탐색을 위해 문서의 계층적 및 의미적 구조가 보존되도록 합니다.

#### 질문: 구조 요소는 접근성과 보조 기술과의 호환성 측면에서 PDF 문서에 어떤 이점을 가져다줍니까?

A: 구조 요소는 문서에 의미 있는 구조와 의미를 제공하여 접근성을 향상시킵니다. 이를 통해 화면 판독기와 같은 보조 기술이 장애가 있는 사용자에게 문서의 내용을 보다 효과적으로 해석하고 전달할 수 있습니다.

#### 질문: PDF 문서에서 다양한 유형의 구조 요소를 더욱 구체적으로 사용자 지정하고 결합하려면 어떻게 해야 합니까?

A: Aspose.PDF에서 제공하는 적절한 생성 방법을 사용하여 구조 요소를 결합하고 사용자 정의할 수 있습니다. 다양한 요소와 그 속성을 실험하여 잘 구조화되고 정리된 PDF 문서를 만드세요.