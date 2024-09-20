---
title: PDF 문서에 반복 열 추가
linktitle: PDF 문서에 반복 열 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서에 반복되는 열을 추가하는 방법을 알아보세요. 예제와 코드가 포함된 단계별 가이드입니다. 개발자에게 완벽합니다.
type: docs
weight: 20
url: /ko/net/programming-with-tables/add-repeating-column/
---
## 소개

PDF 문서로 작업하고 반복되는 열을 추가해야 한다면, 당신은 올바른 곳에 있습니다! Aspose.PDF for .NET을 사용하면 PDF 내의 테이블과 콘텐츠를 쉽게 관리할 수 있습니다. 동적 보고서, 송장 또는 기타 구조화된 문서를 작성하든 반복되는 열은 데이터 구성에서 게임 체인저가 될 수 있습니다. PDF 문서에 반복되는 열을 추가하는 방법에 대한 단계별 가이드를 살펴보겠습니다.

## 필수 조건

코드로 넘어가기 전에 모든 것이 설정되어 있는지 확인해 보겠습니다.

- .NET용 Aspose.PDF: 프로젝트에 .NET용 Aspose.PDF 라이브러리가 설치되어 있어야 합니다.
- [.NET용 Aspose.PDF 다운로드](https://releases.aspose.com/pdf/net/)
- [무료 체험](https://releases.aspose.com/)
- 개발 환경: Visual Studio와 같은 .NET 호환 IDE가 설치되어 있는지 확인하세요.
- C#에 대한 기본적인 이해: 모든 내용을 나누어 설명하지만, C#에 대한 기본적인 이해가 있으면 원활하게 따라갈 수 있습니다.
  
 아직 .NET용 Aspose.PDF가 없다면 다음을 얻을 수 있습니다.[임시 면허](https://purchase.aspose.com/temporary-license/) 그 기능을 탐색해보세요.

## 패키지 가져오기

시작하려면 Aspose.PDF for .NET에서 필요한 네임스페이스를 가져와야 합니다. 방법은 다음과 같습니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

이러한 패키지는 PDF 문서를 다루고 표를 조작하는 데 필요한 필수 클래스와 메서드를 제공합니다.

이제 PDF 문서에 반복되는 열을 추가하기 위해 여러 단계로 프로세스를 나누어 보겠습니다. 따라하세요!

## 1단계: 문서 디렉토리 경로 설정

파일을 만들거나 조작하기 전에 생성된 PDF가 저장될 경로를 정의해야 합니다. C# 프로젝트에서 파일이 위치할 디렉토리 경로를 설정합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

 이 경로는 출력 PDF가 저장될 디렉토리를 가리킵니다. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 컴퓨터의 실제 경로와 일치합니다.

## 2단계: 새 PDF 문서 만들기

 시작하려면 새 인스턴스를 만듭니다.`Document` 객체. 이는 PDF 내의 모든 페이지와 콘텐츠의 컨테이너 역할을 합니다.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

 여기서 우리는 새로운 PDF 문서를 만들고 빈 페이지를 추가했습니다.`doc.Pages.Add()` 이 방법은 문서에 새 페이지를 삽입합니다.

## 3단계: 외부 테이블 인스턴스화

다음으로, 우리는 외부 테이블을 만듭니다. 이 테이블은 페이지의 전체 너비에 걸쳐 있으며 반복되는 열을 포함하는 테이블을 포함한 다른 테이블의 컨테이너 역할을 합니다.

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

 우리는 설정했습니다`ColumnWidths` 속성을 "100%"로 설정하면 표가 전체 페이지 너비에 걸쳐 늘어납니다.

## 4단계: 내부 테이블 만들기

 이제 반복되는 열이 있는 내부 테이블을 만들어 보겠습니다. 여기서 핵심 속성은 다음과 같습니다.`Broken` 이를 통해 동일한 페이지에서 표가 계속 이어지도록 할 수 있습니다.`ColumnAdjustment`콘텐츠에 맞게 열 너비를 자동으로 조정합니다.

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

이 안쪽 표는 바깥쪽 표 안에 중첩됩니다.

## 5단계: 페이지에 표 추가

이제 바깥쪽과 안쪽 표가 모두 준비되었으니 페이지에 추가해 보겠습니다. 이 단계는 표가 문서 구조에 포함되도록 합니다.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

 여기에 우리는 다음을 추가했습니다.`outerTable` 페이지로 이동한 다음 외부 테이블 내에서 중첩했습니다.`mytable` . 또한, 우리는 설정`RepeatingColumnsCount`데이터가 추가될 때 반복해야 하는 열의 수를 지정하여 5까지 지정합니다.

## 6단계: 헤더 행 추가

이제 테이블에 헤더를 추가할 시간입니다. 헤더 행은 데이터에 컨텍스트를 제공하고 열을 구조화하는 데 도움이 됩니다. 

```csharp
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");
```

이 코드 조각은 첫 번째 행(헤더로 사용)을 추가하고 "헤더 1", "헤더 2" 등과 같은 텍스트가 포함된 셀로 채웁니다.

## 7단계: 데이터 행 추가

마지막으로, 우리는 테이블에 데이터를 추가할 수 있습니다. 이 루프는 동적으로 행을 생성하고 셀을 콘텐츠로 채웁니다.

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
    Aspose.Pdf.Row row1 = mytable.Rows.Add();
    row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
```

루프는 6번 반복되며 행을 추가하고 각 셀에 해당 열 데이터(예: "col 1, 1", "col 2, 2" 등)를 채웁니다.

## 8단계: 문서 저장

모든 행과 열을 추가한 후 마지막 단계는 지정된 파일 경로에 문서를 저장하는 것입니다.

```csharp
doc.Save(outFile);
```

이제 문서가 반복되는 열로 저장되었습니다!

## 결론

이제 다 되었습니다! 이 간단한 단계를 통해 Aspose.PDF for .NET을 사용하여 반복되는 열이 있는 PDF 문서를 만들 수 있습니다. 중첩된 테이블의 유연성을 활용하여 PDF를 전문적이고 체계적으로 보이게 하는 복잡한 레이아웃을 구현할 수 있습니다. 다음 프로젝트에서 이 기능을 사용해 보고 Aspose.PDF의 모든 잠재력을 탐색하여 PDF 생성 요구 사항을 처리하세요.

## 자주 묻는 질문

### .NET용 Aspose.PDF란 무엇인가요?
.NET용 Aspose.PDF는 개발자가 프로그래밍 방식으로 PDF 문서를 만들고, 편집하고, 관리할 수 있는 강력한 라이브러리입니다.

### 반복되는 열의 수를 동적으로 조정할 수 있나요?
 예, 반복되는 열의 개수를 수정하여 변경할 수 있습니다.`RepeatingColumnsCount` 재산.

### .NET용 Aspose.PDF에 라이선스를 적용하려면 어떻게 해야 하나요?
 파일이나 스트림에서 라이센스를 적용하려면 다음을 따르세요.[선적 서류 비치](https://reference.aspose.com/pdf/net/).

### 표 셀에 이미지를 추가할 수 있나요?
네, .NET용 Aspose.PDF는 이미지를 포함한 다양한 유형의 콘텐츠를 표 셀에 추가하는 것을 지원합니다.

### 테이블 레이아웃을 더 세부적으로 사용자 지정할 수 있나요?
물론입니다! Aspose.PDF는 테두리, 패딩, 정렬 등을 포함하여 테이블 스타일을 사용자 정의하기 위한 광범위한 기능을 제공합니다.