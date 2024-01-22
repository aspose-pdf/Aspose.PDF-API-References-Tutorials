---
title: 기존 PDF의 이미지에 태그 지정
linktitle: 기존 PDF의 이미지에 태그 지정
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 기존 PDF의 이미지를 마크업하는 방법을 알아보세요. 이미지에 태그를 추가하는 방법에 대한 단계별 가이드입니다.
type: docs
weight: 210
url: /ko/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
이 상세한 튜토리얼에서는 제공된 C# 소스 코드를 단계별로 안내하여 .NET용 Aspose.PDF를 사용하여 기존 PDF의 이미지를 마크업합니다. PDF의 이미지에 태그를 추가하는 방법을 이해하려면 아래 지침을 따르십시오.

## 1단계: 환경 설정

시작하기 전에 Aspose.PDF for .NET을 사용하도록 개발 환경을 구성했는지 확인하세요. 여기에는 Aspose.PDF 라이브러리 설치 및 이를 참조하도록 프로젝트 구성이 포함됩니다.

## 2단계: 기존 PDF 문서 열기

이 단계에서는 Aspose.PDF를 사용하여 기존 PDF 문서를 엽니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 입력 및 출력 파일 경로
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// 문서 열기
Document document = new Document(inFile);
```

Aspose.PDF를 사용하여 기존 PDF 문서를 열었습니다.

## 3단계: 태그된 콘텐츠 및 루트 구조 요소 얻기

이제 PDF 문서의 태그된 콘텐츠와 해당 루트 구조 요소를 가져옵니다.

```csharp
// 태그된 콘텐츠 및 루트 구조 요소 가져오기
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

PDF 문서의 태그된 콘텐츠와 해당 루트 구조 요소를 얻었습니다.

## 4단계: 태그가 지정된 PDF 문서의 제목 설정

이제 태그가 지정된 PDF 문서의 제목을 설정해 보겠습니다.

```csharp
// 태그가 있는 PDF 문서의 제목 정의
taggedContent.SetTitle("Document with images");
```

태그가 지정된 PDF 문서의 제목을 설정했습니다.

## 5단계: 이미지에 대체 텍스트 및 경계 상자 할당

이제 각 이미지 요소에 대해 대체 텍스트와 경계 상자를 할당하겠습니다.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // 이미지에 대체 텍스트 할당
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // 경계 상자(bbox) 생성 및 할당
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

PDF 문서의 각 이미지 요소에 대체 텍스트와 경계 상자를 할당했습니다.

## 6단계: Span 요소를 단락으로 이동

이제 Span 요소를 단락으로 이동해 보겠습니다.

```csharp
// Span 요소를 단락으로 이동합니다(첫 번째 TD에서 잘못된 범위 및 단락 찾기).
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// 단락에서 Span 요소 이동
spanElement.ChangeParentElement(paragraph);
```

Span 요소를 지정된 단락으로 이동했습니다.

## 7단계: 수정된 PDF 문서 저장

이제 필요한 사항을 변경했으므로 수정된 PDF 문서를 저장하겠습니다.

```csharp
// PDF 문서 저장
document. Save(outFile);
```

수정된 PDF 문서를 지정된 디렉토리에 저장했습니다.

### .NET용 Aspose.PDF를 사용하여 기존 PDF의 태그 이미지에 대한 샘플 소스 코드 

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// 문서 열기
Document document = new Document(inFile);

// 태그가 지정된 콘텐츠 및 루트 구조 요소를 가져옵니다.
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// 태그가 지정된 PDF 문서의 제목 설정
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// 그림의 대체 텍스트 설정
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// BBox 속성 생성 및 설정
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// 범위 요소를 단락으로 이동(첫 번째 TD에서 잘못된 범위 및 단락 찾기)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// 범위 요소를 단락으로 이동
spanElement.ChangeParentElement(paragraph);

// 문서 저장
document.Save(outFile);

//출력 문서에 대한 PDF/UA 준수 확인
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 기존 PDF의 이미지를 마크업하는 방법을 배웠습니다. 이제 Aspose.PDF를 사용하여 태그를 추가하고 PDF 문서의 이미지를 편집할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 기존 PDF의 이미지에 태그를 지정하는 방법에 대한 이 튜토리얼의 주요 목적은 무엇입니까?

A: 이 튜토리얼의 기본 목표는 .NET용 Aspose.PDF를 사용하여 기존 PDF 문서 내의 이미지를 마크업하는 프로세스를 안내하는 것입니다. 이 자습서에서는 대체 텍스트와 경계 상자를 이미지에 할당하고, 문서 내에서 요소를 이동하고, 이미지에 태그를 추가하는 방법을 이해하는 데 도움이 되는 단계별 지침과 C# 소스 코드 예제를 제공합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF의 이미지에 태그를 지정하는 방법에 대한 이 튜토리얼을 따르기 위한 전제 조건은 무엇입니까?

A: 시작하기 전에 Aspose.PDF for .NET을 사용하도록 개발 환경을 설정했는지 확인하세요. 여기에는 Aspose.PDF 라이브러리를 설치하고 이를 참조하도록 프로젝트를 구성하는 작업이 포함됩니다.

#### Q: .NET용 Aspose.PDF를 사용하여 기존 PDF 문서를 열고 태그된 콘텐츠에 액세스하려면 어떻게 해야 합니까?

A: 이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 기존 PDF 문서를 열고 추가 조작을 위해 태그가 지정된 콘텐츠에 액세스하는 방법을 보여주는 C# 소스 코드 예제를 제공합니다.

#### Q: PDF 문서의 이미지에 대체 텍스트와 경계 상자를 할당하는 목적은 무엇입니까?

A: 이미지에 대체 텍스트와 경계 상자를 할당하면 이미지에 대한 설명 텍스트를 제공하고 문서 내 레이아웃과 위치를 정의하여 접근성이 향상됩니다. 이 정보는 화면 판독기와 기타 보조 기술에 중요합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 태그가 지정된 PDF 문서의 제목을 어떻게 설정할 수 있습니까?

A: 튜토리얼에는 .NET용 Aspose.PDF를 사용하여 태그가 지정된 PDF 문서의 제목을 설정하는 방법을 보여주는 C# 소스 코드 예제가 포함되어 있습니다.

#### Q: PDF 문서 내에서 요소를 이동하는 과정에는 어떤 과정이 포함됩니까?

답변: PDF 문서 내에서 요소를 이동하려면 특정 요소의 상위 요소를 변경해야 합니다. 이 튜토리얼에서는 Span 요소를 테이블 내의 지정된 Paragraph 요소로 이동하는 방법을 알아봅니다.

#### Q: 태그를 추가하고 이미지를 편집한 후 수정된 PDF 문서를 어떻게 저장합니까?

 A: 태그를 추가하고, 대체 텍스트를 할당하고, 경계 상자를 설정하고, PDF 문서를 편집한 후에는 제공된 C# 소스 코드 예제를 사용하여 수정된 PDF 문서를 저장할 수 있습니다.`Save()` 방법.

#### Q: 튜토리얼에서 제공되는 샘플 소스코드의 목적은 무엇인가요?

A: 샘플 소스 코드는 Aspose.PDF for .NET을 사용하여 이미지 태깅 및 조작을 구현하기 위한 실용적인 참조 역할을 합니다. 이 코드를 시작점으로 사용하여 특정 요구 사항에 맞게 수정할 수 있습니다.

#### 질문: 이러한 기술을 이미지뿐만 아니라 PDF 문서의 다른 유형의 요소에도 적용할 수 있습니까?

A: 예, 이 튜토리얼에서 설명하는 기술은 PDF 문서 내의 다양한 유형의 요소에 맞게 조정될 수 있습니다. 유사한 원칙을 적용하여 텍스트, 표 등과 같은 다른 요소에 태그를 지정하고 조작할 수 있습니다.

#### Q: 수정된 PDF 문서의 PDF/UA 준수 여부를 어떻게 확인할 수 있습니까?

 A: 이 자습서에서는 다음을 사용하여 수정된 PDF 문서의 PDF/UA 준수 여부를 확인하는 방법을 보여주는 C# 소스 코드 예제를 제공합니다.`Validate()` 방법을 사용하고 XML 보고서를 생성합니다.

#### Q: PDF 문서 작업을 위해 Aspose.PDF for .NET이 제공하는 다른 기능은 무엇입니까?

답변: Aspose.PDF for .NET은 텍스트 조작, 이미지 삽입, 테이블 생성, 양식 필드 관리, 디지털 서명, 주석 등을 포함하여 PDF 문서 작업을 위한 광범위한 기능을 제공합니다. 자세한 내용은 공식 문서와 리소스를 참조하세요.