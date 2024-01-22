---
title: 페이지로 분할
linktitle: 페이지로 분할
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서를 개별 페이지로 분할하는 단계별 가이드입니다.
type: docs
weight: 140
url: /ko/net/programming-with-pdf-pages/split-to-pages/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서를 개별 페이지로 분할하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 PDF 문서를 각각 단일 페이지를 포함하는 여러 PDF 파일로 분할하는 방법을 알게 됩니다.

## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식
- 개발 환경에 설치된 .NET용 Aspose.PDF

## 1단계: 문서 디렉터리 정의
먼저 문서 디렉터리의 경로를 설정해야 합니다. 분할하려는 PDF 문서가 있는 곳입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: PDF 문서 열기
 그런 다음 PDF 문서를 열어 분할할 수 있습니다.`Document` Aspose.PDF의 클래스입니다. 올바른 문서 경로를 지정하십시오.

```csharp
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
```

## 3단계: 페이지를 살펴보고 나누기
이제 루프를 사용하여 PDF 문서의 모든 페이지를 반복할 수 있습니다. 각 페이지에 대해 새 문서를 만들고 해당 페이지를 이 새 문서에 추가합니다. 그런 다음 각 페이지에 고유한 파일 이름을 사용하여 새 문서를 저장합니다.

```csharp
int pageCount = 1;
foreach(Page pdfPage in pdfDocument.Pages)
{
Document newDocument = newDocument();
newDocument.Pages.Add(pdfPage);
newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
pageCount++;
}
```

### .NET용 Aspose.PDF를 사용하여 페이지 분할에 대한 샘플 소스 코드 

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
int pageCount = 1;
// 모든 페이지를 반복합니다.
foreach (Page pdfPage in pdfDocument.Pages)
{
	Document newDocument = new Document();
	newDocument.Pages.Add(pdfPage);
	newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
	pageCount++;
}

```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서를 개별 페이지로 분할하는 방법을 배웠습니다. 이 단계별 가이드를 따르면 PDF 문서를 각각 단일 페이지를 포함하는 여러 PDF 파일로 쉽게 분할할 수 있습니다. Aspose.PDF는 프로젝트에서 PDF 문서 작업을 위한 강력하고 유연한 API를 제공합니다. 이제 이 기능을 사용하여 특정 요구 사항에 따라 PDF 문서 분할 작업을 수행할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서를 개별 페이지로 분할하려면 어떻게 해야 합니까?

A: .NET용 Aspose.PDF를 사용하여 PDF 문서를 개별 페이지로 분할하려면 다음 단계를 따르세요.

1. 원본 PDF 파일이 있는 경로와 분할된 PDF 파일을 저장할 위치를 지정하여 문서 디렉터리를 설정하세요. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.
2.  분할할 PDF 문서를 다음을 사용하여 엽니다.`Document` Aspose.PDF의 클래스입니다. 원본 PDF 문서의 올바른 경로를 지정하십시오.
3. 루프를 사용하여 PDF 문서의 모든 페이지를 반복합니다.
4.  각 페이지마다 다음을 사용하여 새 문서를 만듭니다.`Document` 클래스를 사용하여 해당 페이지를 이 새 문서에 추가합니다.`Add()` 의 방법`Pages` 재산.
5.  다음을 사용하여 각 페이지에 대해 고유한 파일 이름으로 새 문서를 저장합니다.`Save()` 의 방법`Document` 수업.

#### Q: PDF 문서를 분할하면 원본 PDF 파일에 영향을 미치나요?

A: 아니요. PDF 문서를 분할해도 원본 PDF 파일에는 영향을 미치지 않습니다. 각 페이지는 새 문서에 복사되고 새 문서는 별도로 저장되며 원본 PDF 파일은 그대로 유지됩니다.

#### Q: 분할 페이지에 이미지, 텍스트 파일 등 다른 파일 형식을 지정할 수 있나요?

A: 제공된 C# 소스 코드는 PDF 문서를 각 페이지에 대한 별도의 PDF 파일로 분할하는 방법을 보여줍니다. 그러나 특정 요구 사항에 따라 분할 페이지를 이미지나 텍스트 파일과 같은 다른 형식으로 저장하도록 코드를 수정할 수 있습니다.

#### Q: .NET용 Aspose.PDF를 사용하여 분할할 수 있는 페이지 수에 제한이 있나요?

A: Aspose.PDF for .NET에는 분할할 수 있는 페이지 수에 대한 특정 제한이 없습니다. 그러나 시스템에서 사용 가능한 메모리와 리소스의 양은 많은 수의 페이지로 작업할 때 성능에 영향을 미칠 수 있습니다.

#### Q: PDF 문서에서 특정 페이지 범위를 분할할 수 있습니까?

A: 예, 제공된 소스 코드를 수정하여 PDF 문서에서 특정 페이지 범위를 분할할 수 있습니다. 모든 페이지를 반복하는 대신 특정 페이지 범위를 선택하고 해당 페이지에 대해서만 새 문서를 만드는 논리를 구현할 수 있습니다.