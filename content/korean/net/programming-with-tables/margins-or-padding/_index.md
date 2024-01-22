---
title: 여백 또는 패딩
linktitle: 여백 또는 패딩
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 테이블에서 여백이나 패딩을 설정하는 방법을 알아보세요.
type: docs
weight: 140
url: /ko/net/programming-with-tables/margins-or-padding/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 테이블에 여백이나 패딩을 설정하는 단계별 프로세스를 안내합니다. C# 소스 코드에서 이 기능을 이해하고 구현하는 데 도움이 되는 설명과 코드 조각을 제공합니다.

## 1단계: 문서 및 페이지 설정
시작하려면 다음 코드를 사용하여 문서와 페이지를 설정해야 합니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 빈 생성자를 호출하여 Document 객체를 인스턴스화합니다.
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 2단계: 테이블 생성
다음으로 Aspose.Pdf.Table 클래스를 사용하여 테이블 개체를 만듭니다.

```csharp
// 테이블 객체 인스턴스화
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// 원하는 섹션의 단락 모음에 표를 추가합니다.
page.Paragraphs.Add(tab1);
```

## 3단계: 열 너비 및 기본 셀 테두리 설정
테이블의 열 너비와 기본 셀 테두리를 설정하려면 다음 코드를 사용하십시오.

```csharp
// 테이블의 열 너비 설정
tab1. ColumnWidths = "50 50 50";
// BorderInfo 개체를 사용하여 기본 셀 테두리 설정
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## 4단계: 표 테두리 및 셀 안쪽 여백 설정
테이블 테두리와 셀 패딩을 설정하려면 MarginInfo 개체를 만들고 해당 속성을 설정합니다.

```csharp
// MarginInfo 개체를 만들고 왼쪽, 아래쪽, 오른쪽 및 위쪽 여백을 설정합니다.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// MarginInfo 개체에 기본 셀 패딩을 설정합니다.
tab1. DefaultCellPadding = margin;

// 다른 사용자 정의된 BorderInfo 개체를 사용하여 표 테두리 설정
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## 5단계: 행 및 셀 추가
이제 테이블에 행과 셀을 추가해 보겠습니다. 새 행을 만들고 여기에 셀을 추가하겠습니다.

```csharp
// 테이블에 행을 만든 다음 행에 셀을 만듭니다.
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## 6단계: 셀에 텍스트 추가
셀에 텍스트를 추가하려면 TextFragment 객체를 만들어 원하는 셀에 추가합니다.

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## 7단계: PDF 저장
PDF 문서를 저장하려면 다음 코드를 사용하십시오.

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// PDF 저장
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### .NET용 Aspose.PDF를 사용하는 여백 또는 패딩의 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 빈 생성자를 호출하여 Document 개체를 인스턴스화합니다.
Document doc = new Document();
Page page = doc.Pages.Add();
// 테이블 객체 인스턴스화
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// 원하는 섹션의 단락 모음에 표를 추가합니다.
page.Paragraphs.Add(tab1);
// 테이블의 열 너비로 설정
tab1.ColumnWidths = "50 50 50";
// BorderInfo 개체를 사용하여 기본 셀 테두리 설정
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// 다른 사용자 정의된 BorderInfo 개체를 사용하여 테이블 테두리 설정
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// MarginInfo 개체를 만들고 왼쪽, 아래쪽, 오른쪽 및 위쪽 여백을 설정합니다.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// MarginInfo 개체에 기본 셀 패딩을 설정합니다.
tab1.DefaultCellPadding = margin;
// 테이블에 행을 만든 다음 행에 셀을 만듭니다.
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("셀 안에 배치할 큰 텍스트 문자열이 있는 col3");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// PDF 저장
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## 결론
축하해요! .NET용 Aspose.PDF를 사용하여 테이블에서 여백이나 패딩을 설정하는 방법을 성공적으로 배웠습니다. 이 지식은 문서 서식 기능을 향상시키고 테이블을 시각적으로 매력적으로 만드는 데 도움이 됩니다.

### FAQ

#### Q: 표의 개별 셀에 대해 서로 다른 여백이나 안쪽 여백을 설정할 수 있습니까?

A: 예, Aspose.PDF for .NET을 사용하여 테이블의 개별 셀에 대해 서로 다른 여백이나 패딩을 설정할 수 있습니다. 제공된 예에서는 다음을 사용하여 전체 테이블에 대한 기본 셀 패딩을 설정합니다.`DefaultCellPadding` 재산. 특정 셀에 대해 다른 패딩을 설정하려면`MarginInfo` 각 셀을 개별적으로 편집하고 여백을 수정합니다.

#### Q: 표의 테두리 색상이나 스타일을 어떻게 변경할 수 있나요?

 A: 표의 테두리 색상이나 스타일을 변경하려면`Color` 그리고`Width` 의 속성`BorderInfo` 물체. 주어진 예에서는 다음을 사용하여 테두리 색상을 검정색으로 설정하고 너비를 1F(1포인트)로 설정했습니다.`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. 요구 사항에 따라 색상과 너비를 조정할 수 있습니다.

#### Q: 표에 머리글이나 바닥글을 추가할 수 있나요?

A: 예, .NET용 Aspose.PDF를 사용하여 테이블에 머리글이나 바닥글을 추가할 수 있습니다. 머리글과 바닥글은 일반적으로 열 레이블, 표 제목, 요약 데이터 등의 추가 정보가 포함된 별도의 행입니다. 추가 행을 생성하고, 스타일을 다르게 지정하고, 표 콘텐츠 위나 아래에 추가할 수 있습니다.

#### Q: 표 셀 내에서 텍스트 정렬을 어떻게 조정합니까?

 A: 표 셀 내의 텍스트 정렬을 조정하려면`HorizontalAlignment` 그리고`VerticalAlignment` 의 속성`TextFragment` 물체. 예를 들어 텍스트를 가로로 가운데 정렬하려면 다음을 설정하면 됩니다.`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . 마찬가지로 설정할 수 있습니다.`mytext.VerticalAlignment` 수직 정렬을 제어합니다.

#### Q: 표 셀에 텍스트 대신 이미지를 추가할 수 있나요?

 A: 예, .NET용 Aspose.PDF를 사용하여 테이블 셀에 이미지를 추가할 수 있습니다. 생성하는 대신`TextFragment` 객체를 생성할 수 있습니다.`Image` 개체를 선택하고 이미지 파일을 로드한 후 다음을 사용하여 원하는 셀에 추가합니다.`cell.Paragraphs.Add(image);` 방법. 이를 통해 텍스트 내용과 함께 테이블에 이미지를 삽입할 수 있습니다.