---
title: 기존 PDF의 태그 이미지
linktitle: 기존 PDF의 태그 이미지
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 기존 PDF의 이미지를 마크업하는 방법을 알아보세요. 이미지에 태그를 추가하는 단계별 가이드.
type: docs
weight: 210
url: /ko/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
이 자세한 튜토리얼에서는 제공된 C# 소스 코드를 단계별로 안내하여 Aspose.PDF for .NET을 사용하여 기존 PDF의 이미지를 마크업합니다. 아래 지침을 따라 PDF의 이미지에 태그를 추가하는 방법을 이해하세요.

## 1단계: 환경 설정

시작하기 전에 Aspose.PDF for .NET을 사용하도록 개발 환경을 구성했는지 확인하세요. 여기에는 Aspose.PDF 라이브러리를 설치하고 이를 참조하도록 프로젝트를 구성하는 것이 포함됩니다.

## 2단계: 기존 PDF 문서 열기

이 단계에서는 Aspose.PDF를 사용하여 기존 PDF 문서를 엽니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 입력 및 출력 파일 경로
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// 문서를 엽니다
Document document = new Document(inFile);
```

Aspose.PDF를 사용하여 기존 PDF 문서를 열었습니다.

## 3단계: 태그가 지정된 콘텐츠 및 루트 구조 요소 가져오기

이제 PDF 문서의 태그가 지정된 콘텐츠와 해당 루트 구조 요소를 가져옵니다.

```csharp
// 태그가 지정된 콘텐츠 및 루트 구조 요소 가져오기
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

우리는 PDF 문서의 태그가 지정된 콘텐츠와 해당 루트 구조 요소를 얻었습니다.

## 4단계: 태그가 지정된 PDF 문서의 제목 설정

이제 태그가 지정된 PDF 문서의 제목을 설정해 보겠습니다.

```csharp
// 태그가 지정된 PDF 문서의 제목을 정의합니다.
taggedContent.SetTitle("Document with images");
```

태그가 지정된 PDF 문서의 제목을 설정했습니다.

## 5단계: 이미지에 대체 텍스트와 경계 상자 지정

이제 각 이미지 요소에 대해 대체 텍스트와 경계 상자를 지정하겠습니다.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // 이미지에 대체 텍스트를 지정하세요
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // 바운딩 박스(bbox)를 생성하고 할당합니다.
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

PDF 문서의 각 이미지 요소에 대체 텍스트와 경계 상자를 할당했습니다.

## 6단계: Span 요소를 문단으로 이동

이제 Span 요소를 문단으로 옮겨보겠습니다.

```csharp
// Span 요소를 문단으로 이동(첫 번째 TD에서 잘못된 span 및 문단 찾기)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// 문단에서 Span 요소를 이동합니다.
spanElement.ChangeParentElement(paragraph);
```

Span 요소를 지정된 문단으로 이동했습니다.

## 7단계: 수정된 PDF 문서 저장

이제 필요한 변경이 끝났으므로 수정된 PDF 문서를 저장하겠습니다.

```csharp
// PDF 문서 저장
document. Save(outFile);
```

수정된 PDF 문서를 지정된 디렉토리에 저장했습니다.

### .NET용 Aspose.PDF를 사용하여 기존 PDF의 태그 이미지에 대한 샘플 소스 코드 

```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// 문서 열기
Document document = new Document(inFile);

// 태그가 지정된 콘텐츠와 루트 구조 요소를 가져옵니다.
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// 태그가 지정된 PDF 문서의 제목 설정
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// 그림에 대한 대체 텍스트 설정
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// BBox 속성 생성 및 설정
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Span 요소를 문단으로 이동(첫 번째 TD에서 잘못된 span 및 문단 찾기)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Span 요소를 문단으로 이동
spanElement.ChangeParentElement(paragraph);

// 문서 저장
document.Save(outFile);

//문서의 PDF/UA 준수 확인
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 기존 PDF의 이미지를 마크업하는 방법을 알아보았습니다. 이제 Aspose.PDF를 사용하여 PDF 문서의 이미지에 태그를 추가하고 편집할 수 있습니다.

### 자주 묻는 질문

#### 질문: Aspose.PDF for .NET을 사용하여 기존 PDF의 이미지에 태그를 지정하는 것에 대한 이 튜토리얼의 주요 목적은 무엇입니까?

A: 이 튜토리얼의 주요 목표는 Aspose.PDF for .NET을 사용하여 기존 PDF 문서 내에서 이미지를 마크업하는 과정을 안내하는 것입니다. 이 튜토리얼은 이미지에 대체 텍스트와 경계 상자를 지정하고, 문서 내에서 요소를 이동하고, 이미지에 태그를 추가하는 방법을 이해하는 데 도움이 되는 단계별 지침과 C# 소스 코드 예제를 제공합니다.

#### 질문: Aspose.PDF for .NET을 사용하여 PDF의 이미지에 태그를 지정하는 방법에 대한 이 튜토리얼을 따르기 위한 전제 조건은 무엇입니까?

A: 시작하기 전에 Aspose.PDF for .NET을 사용하도록 개발 환경을 설정했는지 확인하세요. 여기에는 Aspose.PDF 라이브러리를 설치하고 프로젝트를 구성하여 참조하도록 하는 것이 포함됩니다.

#### 질문: Aspose.PDF for .NET을 사용하여 기존 PDF 문서를 열고 태그가 지정된 콘텐츠에 액세스하려면 어떻게 해야 합니까?

답변: 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 기존 PDF 문서를 열고 태그가 지정된 콘텐츠에 액세스하여 추가 조작하는 방법을 보여주는 C# 소스 코드 예제를 제공합니다.

#### 질문: PDF 문서에서 이미지에 대체 텍스트와 경계 상자를 지정하는 목적은 무엇입니까?

A: 이미지에 대체 텍스트와 경계 상자를 지정하면 이미지에 대한 설명 텍스트를 제공하고 문서 내에서 이미지의 레이아웃과 위치를 정의하여 접근성을 향상시킵니다. 이 정보는 화면 판독기 및 기타 보조 기술에 필수적입니다.

#### 질문: Aspose.PDF for .NET을 사용하여 태그가 지정된 PDF 문서의 제목을 설정하려면 어떻게 해야 합니까?

답변: 이 튜토리얼에는 Aspose.PDF for .NET을 사용하여 태그가 지정된 PDF 문서의 제목을 설정하는 방법을 보여주는 C# 소스 코드 예제가 포함되어 있습니다.

#### 질문: PDF 문서 내에서 요소를 이동하는 과정은 어떤 과정으로 이루어집니까?

A: PDF 문서 내에서 요소를 이동하려면 특정 요소의 부모 요소를 변경해야 합니다. 이 튜토리얼에서는 Span 요소를 테이블 내의 지정된 Paragraph 요소로 이동하는 방법을 알아봅니다.

#### 질문: 태그를 추가하고 이미지를 편집한 후 수정된 PDF 문서를 저장하려면 어떻게 해야 합니까?

 A: 태그를 추가하고, 대체 텍스트를 지정하고, 경계 상자를 설정하고, PDF 문서를 편집한 후 제공된 C# 소스 코드 예제를 사용하여 수정된 PDF 문서를 저장할 수 있습니다.`Save()` 방법.

#### 질문: 튜토리얼에 제공된 샘플 소스 코드의 목적은 무엇인가요?

A: 샘플 소스 코드는 Aspose.PDF for .NET을 사용하여 이미지 태그 지정 및 조작을 구현하기 위한 실제 참조로 사용됩니다. 이 코드를 시작점으로 사용하여 특정 요구 사항에 맞게 수정할 수 있습니다.

#### 질문: PDF 문서에서 이미지뿐만 아니라 다른 유형의 요소에도 이러한 기술을 적용할 수 있나요?

A: 네, 이 튜토리얼에서 보여주는 기술은 PDF 문서 내의 다양한 유형의 요소에 적용되도록 조정할 수 있습니다. 유사한 원리를 적용하여 텍스트, 표 등과 같은 다른 요소에 태그를 지정하고 조작할 수 있습니다.

#### 질문: 수정된 PDF 문서의 PDF/UA 준수 여부를 어떻게 검증할 수 있나요?

 A: 이 튜토리얼에서는 수정된 PDF 문서의 PDF/UA 준수 여부를 확인하는 방법을 보여주는 C# 소스 코드 예제를 제공합니다.`Validate()` 방법을 사용하여 XML 보고서를 생성합니다.

#### 질문: Aspose.PDF for .NET은 PDF 문서 작업을 위해 어떤 다른 기능을 제공합니까?

A: Aspose.PDF for .NET은 텍스트 조작, 이미지 삽입, 테이블 생성, 양식 필드 관리, 디지털 서명, 주석 등을 포함하여 PDF 문서 작업을 위한 광범위한 기능을 제공합니다. 자세한 내용은 공식 문서와 리소스를 참조하세요.