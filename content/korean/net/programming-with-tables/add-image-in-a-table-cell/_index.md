---
title: 테이블 셀에 이미지 추가
linktitle: 테이블 셀에 이미지 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 표 셀에 이미지를 추가합니다. 이 단계별 가이드는 PDF 문서에서 이미지를 정밀하게 조작하기 위한 것입니다.
type: docs
weight: 10
url: /ko/net/programming-with-tables/add-image-in-a-table-cell/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 표 셀에 이미지를 추가하는 과정을 안내합니다. 제공된 C# 소스 코드는 이 기능을 구현하는 방법을 보여줍니다. 아래에 설명된 단계를 따르면 이미지를 표 셀에 효과적으로 통합할 수 있습니다.

코드를 살펴보기 전에 .NET 라이브러리용 Aspose.PDF가 설치되어 있고 프로젝트에서 참조되고 있는지 확인하세요.

## 1단계: 문서 설정

 시작하려면 새 인스턴스를 만들어야 합니다.`Document` Aspose.Pdf 네임스페이스의 클래스입니다. 이 클래스는 PDF 문서를 나타냅니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document 객체를 인스턴스화합니다
Document pdfDocument = new Document();
```

## 2단계: 페이지 만들기

다음으로, PDF 문서에 페이지를 추가해야 합니다. 페이지는 표와 다른 요소를 담는 컨테이너 역할을 합니다.

```csharp
// pdf 문서에 페이지 만들기
Page sec1 = pdfDocument.Pages.Add();
```

## 3단계: 테이블 추가

 이 단계에서는 인스턴스화하여 테이블을 생성합니다.`Table` Aspose.Pdf 네임스페이스의 클래스입니다.

```csharp
// 테이블 객체 인스턴스화
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## 4단계: 기본 셀 테두리 설정

 일관성을 유지하기 위해 다음을 사용하여 기본 셀 테두리를 설정할 수 있습니다.`DefaultCellBorder` 테이블의 속성`BorderInfo` 물체.

```csharp
// BorderInfo 객체를 사용하여 기본 셀 테두리 설정
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## 5단계: 열 너비 설정

 표의 각 열의 너비를 정의하려면 다음을 설정할 수 있습니다.`ColumnWidths` 속성. 공백으로 구분된 값을 가진 문자열로 너비를 지정합니다.

```csharp
// 표의 열 너비로 설정
tab1.ColumnWidths = "100 100 120";
```

## 6단계: 테이블 셀에 이미지 추가

이제 흥미로운 부분이 옵니다. 테이블 셀에 이미지를 추가하는 것입니다. 이를 위해 다음 하위 단계를 따릅니다.

## 6.1단계: 이미지 객체 생성

 인스턴스를 생성합니다`Image` Aspose.Pdf 네임스페이스의 클래스입니다.`File` 추가하려는 이미지 파일의 경로에 대한 속성을 지정합니다.

```csharp
// 이미지 객체 생성
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## 6.2단계: 행 및 셀 생성

표에 이미지를 추가하려면 먼저 행과 필요한 셀을 만들어야 합니다.

```csharp
// 테이블에 행을 만듭니다
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// 행에 텍스트 셀 추가
row1.Cells.Add("Sample text in cell");

// 이미지가 들어있는 셀을 추가합니다
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## 6.3단계: 테이블 셀에 이미지 추가

마지막으로, 셀 안에 이미지를 문단으로 추가하여 표 셀에 이미지를 추가할 수 있습니다.

```csharp
//테이블 셀에 이미지 추가
cell2.Paragraphs.Add(img);
```

## 6.4단계: 추가 셀 추가

이미지 셀을 추가한 후, 필요에 따라 행에 셀을 더 추가할 수 있습니다.

```csharp
// 행에 다른 셀을 추가합니다
row1.Cells.Add("Previous cell with image");

// 세 번째 셀의 수직 정렬을 조정합니다.
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## 7단계: 문서 저장

 마지막으로, 다음을 사용하여 수정된 문서를 지정된 위치에 저장할 수 있습니다.`Save` 방법.

```csharp
//문서 저장
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

축하합니다! Aspose.PDF for .NET을 사용하여 표 셀에 이미지를 추가하는 방법을 성공적으로 배웠습니다. 추가 사용자 지정 옵션을 탐색하고 이 기능을 프로젝트에 통합하세요.

### .NET용 Aspose.PDF를 사용하여 테이블 셀에 이미지를 추가하는 예제 소스 코드

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document 객체를 인스턴스화합니다
Document pdfDocument = new Document();
// pdf 문서에 페이지 만들기
Page sec1 = pdfDocument.Pages.Add();
// 테이블 객체 인스턴스화
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// 원하는 페이지의 문단 컬렉션에 표를 추가합니다.
sec1.Paragraphs.Add(tab1);
// BorderInfo 객체를 사용하여 기본 셀 테두리 설정
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// 표의 열 너비로 설정
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
//표에 행을 만든 다음 행에 셀을 만듭니다.
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// 이미지가 들어있는 셀을 추가합니다
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
//테이블 셀에 이미지 추가
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
//문서 저장
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 표 셀에 이미지를 추가하는 방법에 대한 단계별 가이드를 다루었습니다. 문서를 설정하고, 페이지를 만들고, 표를 추가하는 것으로 시작했습니다. 그런 다음 기본 셀 테두리와 열 너비를 설정했습니다. 표 셀에 이미지를 추가하고 셀의 수직 정렬을 조정하는 방법을 보여주었습니다. 마지막으로 수정된 문서를 저장했습니다. 이러한 단계를 따르면 표 셀에 이미지가 있는 PDF 문서를 효율적으로 향상시킬 수 있습니다.

### 자주 묻는 질문

#### 질문: Aspose.PDF for .NET을 사용하여 동일한 표 내의 여러 셀에 여러 이미지를 추가할 수 있나요?

A: 네, Aspose.PDF for .NET을 사용하여 동일한 테이블 내의 다른 셀에 여러 이미지를 추가할 수 있습니다. 테이블에 추가하려는 각 이미지에 대해 튜토리얼에서 설명한 것과 동일한 프로세스를 따르기만 하면 됩니다.

#### 질문: 표 셀 내에서 이미지 크기와 위치를 사용자 지정할 수 있나요?

 A: 예, 테이블 셀의 속성을 조정하여 테이블 셀 내에서 이미지 크기와 위치를 사용자 정의할 수 있습니다.`Image` 객체. 셀 내에서 이미지 너비와 높이, 정렬을 설정할 수 있습니다.

#### 질문: 행과 열의 개수가 동적으로 변하는 표에 이미지를 추가할 수 있나요?

A: 네, 행과 열의 수가 동적으로 변하는 표에 이미지를 추가할 수 있습니다. Aspose.PDF for .NET은 다양한 차원의 표를 만드는 데 유연성을 제공합니다. 필요에 따라 행과 셀을 추가한 다음, 그에 따라 특정 셀에 이미지를 추가할 수 있습니다.

#### 질문: Aspose.PDF for .NET에서는 테이블 셀에 이미지를 추가할 때 어떤 이미지 형식을 지원합니까?

A: Aspose.PDF for .NET은 JPEG, PNG, GIF, BMP, TIFF를 포함한 광범위한 이미지 형식을 지원합니다. 이러한 형식의 이미지를 사용하여 테이블 셀에 추가할 수 있습니다.

#### 질문: 기존 PDF 문서의 표에 이미지를 추가할 수 있나요?

A: 네, Aspose.PDF for .NET을 사용하여 기존 PDF 문서의 표에 이미지를 추가할 수 있습니다. 기존 문서를 로드하고 튜토리얼에서 보여준 것과 동일한 단계에 따라 표에 이미지를 추가하기만 하면 됩니다.