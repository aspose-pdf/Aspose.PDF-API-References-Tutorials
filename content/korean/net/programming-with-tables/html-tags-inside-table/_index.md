---
title: PDF 파일의 테이블 내부 HTML 태그
linktitle: PDF 파일의 테이블 내부 HTML 태그
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 테이블 내에서 HTML 태그를 사용하는 방법을 알아보세요.
type: docs
weight: 100
url: /ko/net/programming-with-tables/html-tags-inside-table/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서의 테이블 내에서 HTML 태그를 사용하는 방법을 배우겠습니다. C#의 소스코드를 단계별로 설명하겠습니다. 이 튜토리얼이 끝나면 PDF 문서의 테이블에 HTML 콘텐츠를 삽입하는 방법을 알게 됩니다. 시작하자!

## 1단계: 환경 설정
.NET용 Aspose.PDF를 사용하여 C# 개발 환경을 구성했는지 확인하세요. 라이브러리에 참조를 추가하고 필요한 네임스페이스를 가져옵니다.

## 2단계: 테이블 데이터 생성
String 유형의 "데이터" 열을 포함하는 DataTable을 만듭니다. 그런 다음 HTML 콘텐츠를 사용하여 이 DataTable에 행을 추가합니다.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## 3단계: 문서 및 표 만들기
새 PDF 문서를 만들고 이 문서에 페이지를 추가합니다. 다음으로 Table 클래스의 인스턴스를 초기화하고 테이블 속성을 설정합니다.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## 4단계: 테이블로 데이터 가져오기
"ImportDataTable" 메서드를 사용하여 DataTable의 데이터를 테이블로 가져옵니다. DataTable의 행과 열 범위를 가져와야 함을 나타내기 위해 메서드 매개 변수를 지정합니다.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## 5단계: 문서에 표 추가
문서 페이지에 테이블을 추가합니다.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## 6단계: 문서 저장
HTML 콘텐츠가 포함된 테이블과 함께 PDF 문서를 저장합니다.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### .NET용 Aspose.PDF를 사용하는 HTML 태그 내부 테이블의 소스 코드 예

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// 테이블의 새 인스턴스를 초기화합니다.
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//테이블의 열 너비 설정
tableProvider.ColumnWidths = "400 50 ";
// 표 테두리 색상을 LightGray로 설정
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// 표 셀의 테두리 설정
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## 결론
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서의 테이블 내에서 HTML 태그를 사용하는 방법을 배웠습니다. 이 단계별 가이드를 사용하면 C#을 사용하여 PDF 문서의 표 셀에 HTML 콘텐츠를 삽입할 수 있습니다.

### PDF 파일의 테이블 내부 HTML 태그에 대한 FAQ

#### Q: 표 셀 내부에 다른 HTML 태그와 속성을 사용할 수 있습니까?

 A: 예, 다음과 같이 테이블 셀 내부에 다양한 HTML 태그와 속성을 사용할 수 있습니다.`<b>`, `<i>`, `<a>`그리고 더 많은. .NET용 Aspose.PDF는 표 셀 내의 콘텐츠 형식을 지정하는 데 사용할 수 있는 다양한 HTML 요소와 스타일을 지원합니다.

#### Q: 표 셀 내부의 HTML 콘텐츠에 CSS 스타일을 적용할 수 있습니까?

A: 예, 표 셀 내부의 HTML 콘텐츠에 CSS 스타일을 적용할 수 있습니다. .NET용 Aspose.PDF는 HTML 요소에 적용할 수 있는 기본 CSS 스타일을 지원합니다.

#### Q: 표 셀 안에 HTML 콘텐츠와 함께 이미지를 추가할 수 있나요?

 A: 예, 표 셀 내부에 HTML 콘텐츠와 함께 이미지를 추가할 수 있습니다. HTML을 사용할 수 있습니다`<img>` 로컬 파일이나 URL 등 다양한 소스의 이미지를 포함하는 태그입니다.

#### Q: 테이블에 대해 다른 열 너비를 어떻게 지정합니까?

 A: 다음을 사용하여 테이블의 열 너비를 다르게 지정할 수 있습니다.`ColumnWidths` 테이블의 속성입니다. 이 속성은 공백으로 구분된 값이 포함된 문자열을 사용하며, 여기서 각 값은 열 너비를 포인트 단위로 나타냅니다.

#### Q: HTML 콘텐츠가 포함된 셀 내부에 중첩된 표를 사용할 수 있습니까?

A: 예, HTML 콘텐츠가 포함된 셀 내부에 중첩된 테이블을 사용할 수 있습니다. 별도의 테이블 인스턴스를 생성하고 이를 셀 내부의 HTML 콘텐츠의 일부로 추가하여 중첩 효과를 얻을 수 있습니다.