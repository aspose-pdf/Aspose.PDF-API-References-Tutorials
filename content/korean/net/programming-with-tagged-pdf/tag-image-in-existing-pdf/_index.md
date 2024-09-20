---
title: 기존 PDF의 태그 이미지
linktitle: 기존 PDF의 태그 이미지
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 기존 PDF의 이미지에 태그를 지정하는 방법을 알아보세요. PDF/UA 준수를 통해 접근성을 강화하는 단계별 가이드입니다.
type: docs
weight: 210
url: /ko/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## 소개

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 기존 PDF의 이미지에 태그를 지정하는 방법을 안내합니다. 이 가이드를 마치면 이미지에 대한 대체 텍스트를 설정하고, 레이아웃 속성을 조정하고, PDF가 접근성 표준을 준수하는지 확인할 수 있습니다.

## 필수 조건

본격적으로 시작하기 전에, 먼저 필요한 사항을 살펴보겠습니다.

-  .NET용 Aspose.PDF: .NET용 Aspose.PDF의 최신 버전을 다운로드하여 설치했는지 확인하세요.[여기에서 다운로드하세요](https://releases.aspose.com/pdf/net/).
- .NET Framework: Visual Studio와 같은 .NET 개발 환경이 설정되어 있는지 확인하세요.
- PDF 구조에 대한 기본적인 이해: 문단, 범위, 표, 이미지 등 PDF 구조 요소에 대한 지식이 필요합니다.
-  유효한 라이센스: 라이센스를 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy) 또는 임시적인 것을 사용하세요[여기](https://purchase.aspose.com/temporary-license/).

## 패키지 가져오기

코딩을 시작하려면 Aspose.PDF for .NET에서 필수 네임스페이스를 가져와야 합니다. 이를 통해 PDF 문서를 조작하는 데 필요한 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

이제 배경이 마련되었으니, 이미지에 태그를 지정하는 과정을 여러 단계로 나누어 보겠습니다.

## 1단계: 기존 PDF 문서 로드

첫 번째 단계는 작업하려는 PDF 파일을 로드하는 것입니다. 이는 태그를 지정하려는 이미지가 있는 모든 PDF 파일일 수 있습니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// 문서를 엽니다
Document document = new Document(inFile);
```

-  바꾸다`"YOUR DOCUMENT DIRECTORY"` 파일의 실제 경로를 포함합니다.
-  그만큼`Document` 클래스를 사용하면 기존 PDF를 로드할 수 있습니다. 이 PDF를 수정하여 이미지에 태그를 지정합니다.

## 2단계: 태그가 지정된 콘텐츠 및 루트 구조 요소에 액세스

PDF를 열었다면 다음 단계는 태그가 지정된 콘텐츠에 액세스하고 루트 구조 요소를 식별하는 것입니다. 이는 PDF의 요소를 탐색하고 수정할 수 있으므로 매우 중요합니다.

```csharp
// 태그가 지정된 콘텐츠 및 루트 구조 요소 가져오기
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent` PDF의 구조화된 요소에 대한 액세스를 제공합니다.
-  그만큼`RootElement` 가장 위에 있는 구조 요소로, 여기에서 문단, 표, 이미지 등 다른 요소로 아래로 탐색할 수 있습니다.

## 3단계: 태그가 지정된 PDF 문서의 제목 설정

태그가 지정된 PDF 문서에 제목을 추가하면 문서에 적절한 레이블이 지정되어 접근성과 PDF/UA 규정 준수에 도움이 됩니다.

```csharp
// 태그가 지정된 PDF 문서의 제목 설정
taggedContent.SetTitle("Document with images");
```

- 태그가 지정된 PDF에 제목을 설정하면 접근성이 향상되고 화면 판독기와 보조 기술의 문서 명확성이 향상됩니다.

## 4단계: 이미지 찾기 및 태그 지정

 이제 이미지 요소(이미지 요소라고 함)를 찾아 보겠습니다.`FigureElement` Aspose.PDF에서 대체 텍스트를 설정하고 레이아웃 속성을 구성합니다.

```csharp
// 모든 Figure 요소(이미지)를 반복하고 대체 텍스트 및 레이아웃 속성을 설정합니다.
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    // 그림에 대한 대체 텍스트 설정
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    // BBox 속성(경계 상자)을 생성하고 설정합니다.
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    // 그림에 대한 레이아웃 속성 설정
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

-  이 코드는 모든 것을 반복합니다.`FigureElement` 이미지를 나타내는 루트 구조의 객체입니다.
- 접근성을 위한 대체 텍스트를 설정합니다(화면 판독기는 이를 사용하여 이미지를 설명합니다).
- 경계 상자(`BBox`)는 이미지 레이아웃에 대한 좌표를 지정하여 문서에 올바르게 표시되도록 합니다.

## 5단계: 테이블 내 Span 요소 수정

 어떤 경우에는 테이블 내의 span 요소를 수정해야 할 수도 있습니다. 여기서는 span 요소를 찾는 방법을 보여드리겠습니다.`SpanElement` 그것을 문단으로 옮기세요.

```csharp
// 테이블, 범위 및 문단 요소 찾기
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// span 요소를 문단으로 이동합니다.
spanElement.ChangeParentElement(paragraph);
```

-  여기서 우리는 다음을 찾습니다.`TableElement`, `SpanElement` , 그리고`ParagraphElement` PDF 내에서.
-  사용하여`ChangeParentElement` 이 방법을 사용하면 태그와 구조가 제대로 지정되도록 span을 문단으로 옮길 수 있습니다.

## 6단계: 문서 저장 및 PDF/UA 준수 확인

모든 변경이 완료되면 마지막 단계는 업데이트된 PDF를 저장하고 PDF/UA 표준을 준수하는지 확인하는 것입니다.

```csharp
// 업데이트된 PDF 문서를 저장합니다.
document.Save(outFile);

// PDF/UA 준수 확인
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

-  그만큼`Validate` 이 방법은 PDF 문서를 PDF/UA 표준과 비교하여 결과를 기록합니다.
- 규정 준수를 보장하면 접근성이 향상되고 문서 게시에 대한 규정 요구 사항을 충족하는 데 도움이 됩니다.

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 기존 PDF의 이미지에 태그를 지정하는 방법을 보여드렸습니다. 대체 텍스트를 설정하고, 레이아웃 속성을 조정하고, PDF/UA 준수를 위해 문서를 검증하면 PDF가 액세스 가능하고 최신 표준을 충족하는지 확인할 수 있습니다. Aspose.PDF를 사용하면 구조화된 요소로 작업하기 쉽고, 문서의 레이아웃과 액세스 가능성을 제어할 수 있습니다.

## 자주 묻는 질문

### Aspose.PDF for .NET은 무엇에 사용되나요?
.NET용 Aspose.PDF는 .NET 환경에서 프로그래밍 방식으로 PDF 문서를 만들고, 편집하고, 조작하는 데 사용되는 강력한 라이브러리입니다.

### PDF/UA 규정 준수를 어떻게 보장할 수 있나요?
 Aspose.PDF를 사용할 수 있습니다`Validate` 문서를 수정한 후 PDF/UA 준수 여부를 확인하는 방법입니다.

### PDF의 대체 텍스트란 무엇입니까?
대체 텍스트는 특히 화면 판독기를 사용하는 사용자의 접근성을 높이기 위해 PDF 이미지에 추가되는 설명입니다.

### Aspose.PDF를 사용하여 PDF의 표와 범위를 조작할 수 있나요?
네, Aspose.PDF를 사용하면 PDF 문서 내에서 표, 스팬 및 기타 구조화된 요소를 조작할 수 있습니다.

### .NET용 Aspose.PDF를 어디에서 다운로드할 수 있나요?
 .NET용 Aspose.PDF의 최신 버전을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).