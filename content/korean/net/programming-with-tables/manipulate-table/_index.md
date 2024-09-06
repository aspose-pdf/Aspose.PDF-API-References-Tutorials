---
title: PDF 파일에서 테이블 조작
linktitle: PDF 파일에서 테이블 조작
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하면 PDF 파일의 표를 쉽게 조작할 수 있습니다.
type: docs
weight: 130
url: /ko/net/programming-with-tables/manipulate-table/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에서 표를 조작하는 단계별 프로세스를 안내합니다. 표는 PDF 문서에서 일반적인 요소이며, 다양한 시나리오에서 프로그래밍 방식으로 내용을 수정할 수 있는 것은 매우 유익할 수 있습니다. 제공된 C# 소스 코드를 사용하여 프로세스를 시연합니다.

## 요구 사항

시작하기 전에 다음 사항이 있는지 확인하세요.

- Visual Studio 또는 다른 C# 개발 환경이 설치되어 있어야 합니다.
- .NET 라이브러리용 Aspose.PDF가 프로젝트에 참조로 추가되었습니다.

이제 Aspose.PDF for .NET을 사용하여 PDF 문서의 표를 조작하는 데 필요한 단계를 살펴보겠습니다.

## 1단계: PDF 문서 로딩

첫 번째 단계는 기존 PDF 문서를 C# 애플리케이션에 로드하는 것입니다. 문서가 있는 디렉토리 경로를 제공해야 합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "input.pdf");
```

"YOUR DOCUMENT DIRECTORY"를 PDF 문서가 있는 디렉토리의 실제 경로로 바꾸세요.

## 2단계: 문서에서 테이블 찾기

표를 조작하려면 PDF 문서에서 찾아야 합니다. .NET용 Aspose.PDF는 문서에서 표를 추출할 수 있는 TableAbsorber 클래스를 제공합니다. TableAbsorber 클래스의 인스턴스를 만들고 문서의 원하는 페이지를 방문합니다.

```csharp
TableAbsorber absorber = new TableAbsorber();
absorb.Visit(pdfDocument.Pages[1]);
```

이 예에서 우리는 문서의 첫 번째 페이지를 방문하고 있습니다. 요구 사항에 따라 페이지 번호를 변경할 수 있습니다.

## 3단계: 테이블 셀 및 텍스트 조각 액세스

테이블이 있으면 조작을 위해 셀과 텍스트 조각에 액세스할 수 있습니다. 제공된 소스 코드에서 첫 번째 테이블, 첫 번째 행의 첫 번째 셀, 해당 셀 내의 두 번째 텍스트 조각에 액세스합니다.

```csharp
TextFragment fragment = absorb.TableList[0].RowList[0].CellList[0].TextFragments[1];
```

사용자의 특정 요구 사항에 따라 다양한 표, 셀 또는 텍스트 조각을 타겟으로 코드를 수정할 수 있습니다.

## 4단계: 테이블 텍스트 조작

텍스트 조각에 액세스했으므로 이제 해당 내용을 수정할 수 있습니다. 주어진 예에서 텍스트를 "hi world"로 변경합니다.

```csharp
fragment.Text = "hi world";
```

"hi world"를 원하는 텍스트로 바꿔도 됩니다.

## 5단계: 수정된 문서 저장

원하는 수정 작업을 마친 후에는 수정된 PDF 문서를 저장해야 합니다.

```csharp
dataDir = dataDir + "ManipulateTable_out.pdf";
pdfDocument.Save(dataDir);
```

수정된 문서의 경로와 파일 이름을 제공하세요.


### .NET용 Aspose.PDF를 사용하여 테이블 조작을 위한 예제 소스 코드

```csharp
try
{
	
	// 문서 디렉토리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// 기존 PDF 파일 로드
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// 테이블을 찾기 위해 TableAbsorber 객체를 생성합니다.
	TableAbsorber absorber = new TableAbsorber();

	// 흡수체로 첫 페이지 방문
	absorber.Visit(pdfDocument.Pages[1]);

	// 페이지의 첫 번째 표, 첫 번째 셀 및 해당 텍스트 조각에 액세스합니다.
	TextFragment fragment = absorber.TableList[0].RowList[0].CellList[0].TextFragments[1];

	// 셀의 첫 번째 텍스트 조각의 텍스트를 변경합니다.
	fragment.Text = "hi world";
	dataDir = dataDir + "ManipulateTable_out.pdf";
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nTable manipulated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 표를 조작하는 방법을 알아보았습니다. 단계별 가이드를 따르면 PDF 문서를 쉽게 로드하고, 표를 찾고, 셀과 텍스트 조각에 액세스하고, 표 내용을 수정하고, 수정된 문서를 저장할 수 있습니다. 이 접근 방식은 PDF 문서에서 표 조작을 처리할 때 유연성과 효율성을 제공합니다.

### PDF 파일에서 테이블 조작에 대한 FAQ

#### 질문: 여러 페이지로 된 PDF 문서에서 표를 조작할 수 있나요?

A: 네, Aspose.PDF for .NET을 사용하여 여러 페이지 PDF 문서의 표를 조작할 수 있습니다. 제공된 예에서 우리는 문서의 첫 번째 페이지를 방문했습니다(`pdfDocument.Pages[1]`), 하지만 모든 페이지를 반복하고 필요에 따라 각 페이지의 표를 조작할 수 있습니다.

#### 질문: 기존 표에 새로운 행이나 열을 추가하려면 어떻게 해야 하나요?

 A: 기존 테이블에 새 행이나 열을 추가하려면 Aspose.PDF for .NET에서 제공하는 API를 사용할 수 있습니다.`RowList` 그리고`CellList` 의 속성`TableAbsorber.TableList` 새로운 행과 셀을 프로그래밍 방식으로 추가합니다. 자세한 정보와 코드 예제는 .NET 설명서용 Aspose.PDF를 참조하세요.

#### 질문: PDF 문서에서 표를 제거할 수 있나요?

 A: 네, Aspose.PDF for .NET을 사용하여 PDF 문서에서 표를 제거할 수 있습니다. 이를 위해 특정`Table` ~로부터 물체`Page.Paragraphs` 컬렉션. 속성을 사용하여 제거할 테이블을 식별할 수 있습니다.`Table.NumberOfColumns`, `Table.NumberOfRows`및 기타 고유 식별자.

#### 질문: 표 텍스트의 서식(글꼴, 색상, 정렬)을 변경할 수 있나요?

 A: 네, Aspose.PDF for .NET을 사용하여 테이블 텍스트의 서식을 변경할 수 있습니다.`TextState` 의 속성`TextFragment` 개체는 텍스트의 글꼴, 글꼴 크기, 색상 및 정렬을 수정합니다.

#### 질문: .NET용 Aspose.PDF는 PDF 양식(AcroForms)의 표 작업을 지원합니까?

A: 네, Aspose.PDF for .NET은 PDF 양식(AcroForms)에서 표 작업을 지원합니다. 이 튜토리얼에서 보여준 접근 방식과 유사하게 PDF 양식에서 표 요소에 액세스하고 조작할 수 있습니다. Aspose.PDF for .NET은 AcroForms 및 양식 필드 작업에 대한 광범위한 지원을 제공합니다.