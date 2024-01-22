---
title: 테이블 셀에 이미지 추가
linktitle: 테이블 셀에 이미지 추가
second_title: .NET API 참조용 Aspose.PDF
description: PDF 문서의 이미지를 정밀하게 조작하기 위한 단계별 가이드인 Aspose.PDF for .NET을 사용하여 테이블 셀에 이미지를 추가하세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/add-image-in-a-table-cell/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 테이블 셀에 이미지를 추가하는 과정을 안내합니다. 제공된 C# 소스 코드는 이 기능을 구현하는 방법을 보여줍니다. 아래 설명된 단계를 따르면 이미지를 표 셀에 효과적으로 통합할 수 있습니다.

코드를 살펴보기 전에 .NET용 Aspose.PDF 라이브러리가 설치되어 있고 프로젝트에 참조되어 있는지 확인하세요.

## 1단계: 문서 설정

 시작하려면 새 인스턴스를 생성해야 합니다.`Document` Aspose.Pdf 네임스페이스의 클래스입니다. 이 클래스는 PDF 문서를 나타냅니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document 객체 인스턴스화
Document pdfDocument = new Document();
```

## 2단계: 페이지 만들기

다음으로 PDF 문서에 페이지를 추가해야 합니다. 페이지는 테이블과 기타 요소의 컨테이너 역할을 합니다.

```csharp
// PDF 문서에 페이지 만들기
Page sec1 = pdfDocument.Pages.Add();
```

## 3단계: 테이블 추가

 이 단계에서는 인스턴스를 생성하여 테이블을 생성합니다.`Table` Aspose.Pdf 네임스페이스의 클래스입니다.

```csharp
// 테이블 객체 인스턴스화
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## 4단계: 기본 셀 테두리 설정

 일관성을 보장하기 위해 다음을 사용하여 기본 셀 테두리를 설정할 수 있습니다.`DefaultCellBorder`테이블의 속성`BorderInfo` 물체.

```csharp
// BorderInfo 개체를 사용하여 기본 셀 테두리 설정
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## 5단계: 열 너비 설정

 테이블의 각 열 너비를 정의하기 위해 다음을 설정할 수 있습니다.`ColumnWidths` 재산. 공백으로 구분된 값이 포함된 문자열로 너비를 지정합니다.

```csharp
// 테이블의 열 너비로 설정
tab1.ColumnWidths = "100 100 120";
```

## 6단계: 표 셀에 이미지 추가

이제 테이블 셀에 이미지를 추가하는 흥미로운 부분이 나옵니다. 이를 위해 다음과 같은 하위 단계를 따릅니다.

## 6.1단계: 이미지 개체 생성

 인스턴스를 생성합니다.`Image` Aspose.Pdf 네임스페이스의 클래스입니다. 설정`File` 속성을 추가하려는 이미지 파일의 경로에 추가하세요.

```csharp
// 이미지 객체 생성
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## 6.2단계: 행 및 셀 생성

테이블에 이미지를 추가하려면 먼저 행과 필요한 셀을 만들어야 합니다.

```csharp
// 테이블에 행 만들기
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// 행에 텍스트 셀 추가
row1.Cells.Add("Sample text in cell");

// 이미지가 들어있는 셀을 추가하세요
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## 6.3단계: 테이블 셀에 이미지 추가

마지막으로 이미지를 셀 내의 단락으로 추가하여 표 셀에 이미지를 추가할 수 있습니다.

```csharp
// 테이블 셀에 이미지 추가
cell2.Paragraphs.Add(img);
```

## 6.4단계: 추가 셀 추가

이미지 셀을 추가한 후 필요한 경우 행에 더 많은 셀을 추가할 수 있습니다.

```csharp
//행에 다른 셀 추가
row1.Cells.Add("Previous cell with image");

// 세 번째 셀의 수직 정렬 조정
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## 7단계: 문서 저장

 마지막으로 다음을 사용하여 수정된 문서를 지정된 위치에 저장할 수 있습니다.`Save` 방법.

```csharp
// 문서 저장
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

축하해요! .NET용 Aspose.PDF를 사용하여 테이블 셀에 이미지를 추가하는 방법을 성공적으로 배웠습니다. 추가 사용자 정의 옵션을 자유롭게 탐색하고 이 기능을 프로젝트에 통합해 보세요.

### .NET용 Aspose.PDF를 사용하여 테이블 셀에 이미지를 추가하는 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document 객체 인스턴스화
Document pdfDocument = new Document();
// PDF 문서에 페이지 만들기
Page sec1 = pdfDocument.Pages.Add();
// 테이블 객체 인스턴스화
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// 원하는 페이지의 단락 모음에 표를 추가하세요.
sec1.Paragraphs.Add(tab1);
// BorderInfo 개체를 사용하여 기본 셀 테두리 설정
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// 테이블의 열 너비로 설정
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// 테이블에 행을 만든 다음 행에 셀을 만듭니다.
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// 이미지가 들어있는 셀을 추가하세요
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// 테이블 셀에 이미지 추가
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// 문서 저장
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 테이블 셀에 이미지를 추가하는 방법에 대한 단계별 가이드를 다루었습니다. 먼저 문서 설정, 페이지 생성, 표 추가부터 시작했습니다. 그런 다음 기본 셀 테두리와 열 너비를 설정합니다. 표 셀에 이미지를 추가하고 셀의 수직 정렬을 조정하는 방법을 시연했습니다. 마지막으로 수정된 문서를 저장했습니다. 다음 단계를 수행하면 표 셀의 이미지로 PDF 문서를 효율적으로 향상할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 동일한 테이블 내의 서로 다른 셀에 여러 이미지를 추가할 수 있습니까?

A: 예, Aspose.PDF for .NET을 사용하여 동일한 테이블 내의 서로 다른 셀에 여러 이미지를 추가할 수 있습니다. 테이블에 추가하려는 각 이미지에 대해 튜토리얼에서 설명한 것과 동일한 프로세스를 따르기만 하면 됩니다.

#### Q: 표 셀 내에서 이미지 크기와 위치를 사용자 정의할 수 있나요?

 A: 예, 속성을 조정하여 표 셀 내에서 이미지 크기와 위치를 사용자 정의할 수 있습니다.`Image`물체. 이미지 너비와 높이뿐만 아니라 셀 내 정렬도 설정할 수 있습니다.

#### Q: 동적인 행과 열 수를 포함하는 테이블에 이미지를 추가할 수 있습니까?

A: 예, 동적 행과 열 수를 사용하여 테이블에 이미지를 추가할 수 있습니다. .NET용 Aspose.PDF는 다양한 차원의 테이블을 생성하는 유연성을 제공합니다. 필요에 따라 행과 셀을 추가한 다음 그에 따라 특정 셀에 이미지를 추가할 수 있습니다.

#### Q: 표 셀에 이미지를 추가하기 위해 .NET용 Aspose.PDF에서는 어떤 이미지 형식을 지원합니까?

A: .NET용 Aspose.PDF는 JPEG, PNG, GIF, BMP 및 TIFF를 포함한 광범위한 이미지 형식을 지원합니다. 이러한 형식의 이미지를 사용하여 표 셀에 추가할 수 있습니다.

#### Q: 기존 PDF 문서의 표에 이미지를 추가할 수 있나요?

A: 예, .NET용 Aspose.PDF를 사용하여 기존 PDF 문서의 테이블에 이미지를 추가할 수 있습니다. 기존 문서를 로드하고 튜토리얼에서 설명한 것과 동일한 단계에 따라 테이블에 이미지를 추가하기만 하면 됩니다.