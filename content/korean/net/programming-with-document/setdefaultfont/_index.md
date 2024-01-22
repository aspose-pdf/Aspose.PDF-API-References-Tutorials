---
title: PDF 파일에 기본 글꼴 설정
linktitle: PDF 파일에 기본 글꼴 설정
second_title: .NET API 참조용 Aspose.PDF
description: 이 단계별 가이드를 통해 .NET용 Aspose.PDF를 사용하여 PDF 파일의 기본 글꼴을 설정하는 방법을 알아보세요.
type: docs
weight: 280
url: /ko/net/programming-with-document/setdefaultfont/
---
.NET에서 PDF 문서로 작업하는 경우 PDF에 사용된 글꼴을 PDF를 보거나 인쇄하는 시스템에서 사용할 수 없는 문제가 발생할 수 있습니다. 이로 인해 텍스트가 잘못 표시되거나 전혀 표시되지 않을 수 있습니다. .NET용 Aspose.PDF는 문서의 기본 글꼴을 설정할 수 있도록 하여 이 문제에 대한 솔루션을 제공합니다. 이 예에서는 .NET용 Aspose.PDF를 사용하여 기본 글꼴을 설정하는 방법을 보여줍니다.

## 1단계: 문서 디렉터리 경로 설정

PDF 문서가 있는 디렉토리의 경로를 설정해야 합니다. 이 경로를 "dataDir"이라는 변수에 저장합니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: PDF 문서 로드

 누락된 글꼴이 있는 기존 PDF 문서를 로드하는 것부터 시작하겠습니다. 이 예에서는 PDF 문서가`dataDir` 변하기 쉬운.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // 코드는 여기에 들어갑니다
}
```

## 3단계: 기본 글꼴 설정

 다음으로, 다음을 사용하여 PDF 문서의 기본 글꼴을 설정하겠습니다.`PdfSaveOptions` 수업. 이 예에서는 기본 글꼴을 "Arial"로 설정하겠습니다.

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## 4단계: 업데이트된 문서 저장

마지막으로 업데이트된 문서를 새 파일에 저장하겠습니다. 이 예에서는 업데이트된 문서를 입력 파일과 동일한 디렉터리에 있는 "output_out.pdf"라는 파일에 저장합니다.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### .NET용 Aspose.PDF를 사용하여 기본 글꼴 설정에 대한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 글꼴이 누락된 기존 PDF 문서 로드
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// 기본 글꼴 이름 지정
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## 결론

.NET용 Aspose.PDF를 사용하여 PDF 문서에서 기본 글꼴을 설정하는 것은 원본 글꼴을 사용할 수 없는 경우에도 텍스트가 올바르게 표시되도록 하는 간단하고 효과적인 방법입니다. 단계별 가이드를 따르고 제공된 C# 소스 코드를 사용하여 개발자는 기본 글꼴을 쉽게 설정하고 다양한 환경에서 일관되고 안정적인 보기 환경을 제공하는 PDF를 만들 수 있습니다. 이 기능은 다양한 글꼴 세트가 설치된 다양한 시스템에서 PDF를 보거나 인쇄하는 시나리오에서 특히 유용합니다.

### PDF 파일의 기본 글꼴 설정에 대한 FAQ

#### Q: PDF 문서에서 기본 글꼴 설정이 중요한 이유는 무엇입니까?

답변: PDF 문서에서 기본 글꼴을 설정하는 것은 PDF를 보거나 인쇄하는 시스템에서 원본 글꼴을 사용할 수 없는 경우에도 텍스트가 올바르게 표시되도록 보장하기 때문에 중요합니다. 텍스트 누락이나 깨짐과 같은 문제를 방지하여 일관되고 안정적인 시청 경험을 보장합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 어떤 글꼴이든 기본 글꼴로 선택할 수 있나요?

 A: 예, .NET용 Aspose.PDF를 사용하여 시스템에서 사용 가능한 모든 글꼴을 기본 글꼴로 선택할 수 있습니다. 간단히 글꼴 이름을 지정하십시오.`DefaultFontName` 의 재산`PdfSaveOptions` 수업.

#### Q: 지정된 기본 글꼴을 시스템에서 사용할 수 없으면 어떻게 됩니까?

답변: 지정된 기본 글꼴을 시스템에서 사용할 수 없는 경우 PDF 뷰어는 대체 글꼴을 사용하여 텍스트를 표시합니다. 다양한 시스템 간의 호환성을 보장하려면 Arial 또는 Times New Roman과 같이 일반적으로 사용 가능한 글꼴을 선택하는 것이 좋습니다.