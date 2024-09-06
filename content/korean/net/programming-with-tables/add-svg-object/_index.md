---
title: PDF 파일에 SVG 객체 추가
linktitle: PDF 파일에 SVG 객체 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 SVG 객체를 쉽게 추가할 수 있습니다.
type: docs
weight: 30
url: /ko/net/programming-with-tables/add-svg-object/
---
이 튜토리얼에서는 Aspose.PDF for .NET 라이브러리를 사용하여 PDF 파일에 SVG 객체를 추가하는 방법을 알아봅니다. SVG(Scalable Vector Graphics)는 품질을 잃지 않고 쉽게 확장할 수 있는 벡터 그래픽의 인기 있는 형식입니다. Aspose.PDF를 사용하면 SVG 객체를 프로그래밍 방식으로 PDF 문서에 추가할 수 있습니다.

## 요구 사항

시작하기 전에 다음 사항이 있는지 확인하세요.

- Visual Studio 설치됨
- .NET 라이브러리용 Aspose.PDF 설치됨

## 1단계: 환경 설정

먼저, Visual Studio에서 새 C# 프로젝트를 만들어 환경을 설정해 보겠습니다. Visual Studio를 열고 다음 단계를 따르세요.

1. "파일" > "새로 만들기" > "프로젝트"를 클릭하여 새 프로젝트를 만듭니다.
2. 설정에 따라 "콘솔 앱(.NET Framework)" 또는 "콘솔 앱(.NET Core)" 템플릿을 선택하세요.
3. 프로젝트에 적합한 이름과 위치를 선택한 후 "만들기"를 클릭하세요.

## 2단계: 문서 및 이미지 개체 만들기

이 단계에서는 PDF 문서와 SVG 이미지에 필요한 객체를 만듭니다. 프로젝트의 C# 파일을 열고 다음 코드를 추가합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instant Document 객체
Document doc = new Document();
// 이미지 인스턴스 생성
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## 3단계: 이미지 속성 설정

다음으로 SVG 이미지의 속성을 설정합니다. 파일 유형을 SVG로 지정하고, SVG 파일 경로와 이미지 크기를 지정합니다. 이전 단계 뒤에 다음 코드를 추가합니다.

```csharp
// 이미지 유형을 SVG로 설정
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// 소스 파일의 경로
img.File = dataDir + "SVGToPDF.svg";
// 이미지 인스턴스의 너비 설정
img. FixWidth = 50;
// 이미지 인스턴스의 높이 설정
img.FixHeight = 50;
```

## 4단계: 테이블 생성 및 구성

이제 테이블 객체를 만들고 열 너비를 설정해 보겠습니다. 각각 너비가 100인 두 개의 열이 있는 테이블을 만들 것입니다. 다음 코드를 추가합니다.

```csharp
// 인스턴스 테이블 생성
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// 테이블 셀의 너비 설정
table. ColumnWidths = "100 100";
```

## 5단계: 표에 셀 추가

이 단계에서는 테이블에 행과 셀을 추가합니다. 각 행은 테이블의 수평 행을 나타내며, 셀은 행에 추가됩니다. 다음 코드를 추가합니다.

```csharp
//행 객체를 생성하여 테이블 인스턴스에 추가합니다.
Aspose.Pdf.Row row = table.Rows.Add();
// 셀 객체를 생성하여 행 인스턴스에 추가합니다.
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## 6단계: 셀에 텍스트와 이미지 추가

다음으로, 테이블의 셀에 텍스트와 SVG 이미지를 추가해 보겠습니다. 첫 번째 셀에 "First cell"이라는 텍스트를 추가하고 두 번째 셀에 SVG 이미지를 추가합니다. 다음 코드를 추가합니다.

```csharp
// 셀 객체의 문단 컬렉션에 텍스트 조각을 추가합니다.
cell.Paragraphs.Add(new TextFragment("First cell"));
// 행 개체에 다른 셀 추가
cell = row. Cells. Add();
// 최근 추가된 셀 인스턴스의 문단 컬렉션에 SVG 이미지 추가
cell.Paragraphs.Add(img);
```

## 7단계: 문서에 페이지 만들기 및 추가

이제 페이지 객체를 만들어 문서에 추가해 보겠습니다. 테이블은 페이지의 paragraphs 컬렉션에 추가됩니다. 다음 코드를 추가합니다.

```csharp
// 페이지 객체를 생성하여 문서 인스턴스의 페이지 컬렉션에 추가합니다.
Page page = doc.Pages.Add();
// 페이지 객체의 문단 컬렉션에 표 추가
page.Paragraphs.Add(table);
```

## 8단계: PDF 파일 저장

마지막으로, PDF 파일을 지정된 위치에 저장합니다. 다음 코드를 추가합니다.

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// PDF 파일 저장
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### .NET용 Aspose.PDF를 사용하여 SVG 객체를 추가하는 예제 소스 코드

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document 객체 인스턴스화
Document doc = new Document();
// 이미지 인스턴스 생성
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// 이미지 유형을 SVG로 설정
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// 소스 파일의 경로
img.File = dataDir + "SVGToPDF.svg";
// 이미지 인스턴스의 너비 설정
img.FixWidth = 50;
// 이미지 인스턴스의 높이 설정
img.FixHeight = 50;
// 테이블 인스턴스 생성
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// 테이블 셀의 너비 설정
table.ColumnWidths = "100 100";
//행 객체를 생성하여 테이블 인스턴스에 추가합니다.
Aspose.Pdf.Row row = table.Rows.Add();
// 셀 객체를 생성하여 행 인스턴스에 추가합니다.
Aspose.Pdf.Cell cell = row.Cells.Add();
// 셀 객체의 문단 컬렉션에 텍스트 조각을 추가합니다.
cell.Paragraphs.Add(new TextFragment("First cell"));
// 행 개체에 다른 셀 추가
cell = row.Cells.Add();
// 최근 추가된 셀 인스턴스의 문단 컬렉션에 SVG 이미지 추가
cell.Paragraphs.Add(img);
// 페이지 객체를 생성하여 문서 인스턴스의 페이지 컬렉션에 추가합니다.
Page page = doc.Pages.Add();
// 페이지 객체의 문단 컬렉션에 표 추가
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// PDF 파일 저장
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET 라이브러리를 사용하여 SVG 객체를 PDF 파일에 추가하는 방법을 알아보았습니다. 문서 만들기, 환경 설정, 테이블 셀에 SVG 이미지 추가, PDF 파일 저장의 단계별 프로세스를 다루었습니다. 이제 SVG 객체를 프로그래밍 방식으로 PDF 문서에 통합할 수 있습니다.

### PDF 파일에 SVG 객체를 추가하기 위한 FAQ

#### 질문: PDF 문서에 SVG 객체를 여러 개 추가할 수 있나요?

 A: 네, PDF 문서에 여러 SVG 객체를 추가할 수 있습니다. 간단히 추가를 생성하고 구성하세요.`Aspose.Pdf.Image` 추가하려는 SVG 이미지마다 인스턴스를 만든 다음, 이를 PDF 문서의 원하는 표 셀이나 문단에 추가합니다.

#### 질문: 테이블 셀에서 SVG 이미지의 크기와 위치를 어떻게 조정할 수 있나요?

 A: 테이블 셀에서 SVG 이미지의 크기와 위치를 조정하려면 다음을 수정할 수 있습니다.`FixWidth` 그리고`FixHeight` 의 속성`Aspose.Pdf.Image`인스턴스. 다음과 같은 다른 속성을 사용할 수도 있습니다.`HorizontalAlignment` 그리고`VerticalAlignment` 테이블 셀의 위치를 제어합니다.

#### 질문: 같은 테이블 셀에 SVG 이미지와 함께 텍스트를 추가할 수 있나요?

 A: 네, 같은 테이블 셀에서 SVG 이미지 옆에 텍스트를 추가할 수 있습니다. 다음을 사용할 수 있습니다.`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` SVG 이미지와 함께 셀에 텍스트를 추가하는 방법입니다.

#### 질문: SVG 이미지에 하이퍼링크를 추가할 수 있나요?

 A: 예, SVG 이미지에 하이퍼링크를 추가할 수 있습니다.`Hyperlink` 의 속성`Aspose.Pdf.Image` 인스턴스. 이미지를 클릭할 수 있도록 하이퍼링크 URL이나 동작을 설정합니다.

#### 질문: Aspose.PDF for .NET은 .NET Core 3.1 이상 버전과 호환됩니까?

A: 네, Aspose.PDF for .NET은 .NET Core 3.1 이상 버전과 호환됩니다. .NET Framework와 .NET Core 애플리케이션에서 모두 사용할 수 있습니다.