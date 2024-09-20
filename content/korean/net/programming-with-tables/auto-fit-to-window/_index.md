---
title: 창에 자동 맞춤
linktitle: 창에 자동 맞춤
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 자세한 단계별 가이드에서 Aspose.PDF for .NET을 사용하여 테이블을 창에 자동으로 맞추는 방법을 알아보세요. PDF에서 세련되고 잘 맞는 테이블을 만드는 데 적합합니다.
type: docs
weight: 50
url: /ko/net/programming-with-tables/auto-fit-to-window/
---
## 소개

PDF로 작업할 때 표를 다루는 것이 일반적이며, 이러한 표를 페이지 너비에 완벽하게 맞춰야 할 때가 있습니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 표를 창에 자동으로 맞추는 방법을 살펴보겠습니다. 이렇게 하면 표가 세련되고 정리되어 보이며, 넘치거나 열이 고르지 않은 것과 같은 문제가 발생하지 않습니다. 배울 준비가 되셨나요? 시작해 볼까요!

## 필수 조건

단계별 가이드를 살펴보기 전에 몇 가지 필요한 사항이 있습니다.

1. 프로젝트에 Aspose.PDF for .NET이 설치되어 있습니다. 아직 설치하지 않았다면 다음을 수행할 수 있습니다.[여기서 다운로드하세요](https://releases.aspose.com/pdf/net/) 또는 탐색하다[무료 체험판](https://releases.aspose.com/).
2. .NET 프로그래밍에 대한 기본적인 이해.
3. 시스템에 Visual Studio 또는 .NET을 지원하는 IDE가 설치되어 있어야 합니다.

>  PS Aspose.PDF를 제한 없이 사용하려면 라이센스가 필요하다는 것을 잊지 마세요. 하나를 구매하거나[여기](https://purchase.aspose.com/buy) 또는 얻을[임시 면허](https://purchase.aspose.com/temporary-license/) 모든 기능을 사용해보세요.

## 패키지 가져오기

코드를 살펴보기 전에 필요한 네임스페이스를 가져와야 합니다.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

이제 모든 준비가 끝났으니 Aspose.PDF for .NET을 사용하여 표를 창에 자동으로 맞추는 방법을 이해하기 쉽게 간단하고 이해하기 쉬운 단계로 나누어 보겠습니다.

## 1단계: 문서 개체 초기화

먼저 PDF 문서를 만들어야 합니다. 이 문서를 페이지와 표를 추가할 빈 시트라고 생각하세요.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 빈 생성자를 호출하여 Pdf 객체를 인스턴스화합니다.
Document doc = new Document();
```
  
 여기서 우리는 다음을 사용하여 새 문서를 만듭니다.`Document` Aspose.PDF에서 클래스입니다.`dataDir` 작업이 완료된 후 PDF가 저장되는 위치입니다.

## 2단계: 문서에 페이지 추가

PDF 문서에는 페이지가 필요하죠? 하나 추가해 봅시다.

```csharp
// Pdf 객체에 섹션(페이지)을 만듭니다.
Page sec1 = doc.Pages.Add();
```
  
 우리는 다음을 사용하여 문서에 새 페이지를 추가했습니다.`Pages.Add()` 방법. 이것은 테이블을 놓을 문서에 새 시트를 추가하는 것으로 생각할 수 있습니다.

## 3단계: 테이블 생성 및 구성

이제 표를 만들고 창에 맞게 조정해야 할 때입니다.

```csharp
// 테이블 객체 인스턴스화
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// 원하는 섹션의 문단 모음에 표를 추가합니다.
sec1.Paragraphs.Add(tab1);
```
  
 새로운 것을 초기화했습니다`Table` 객체를 만들고 페이지의 문단 컬렉션에 추가했습니다. 각 PDF 페이지는 다른 문단을 가질 수 있으며, 여기서는 표를 문단으로 취급합니다.

## 4단계: 열 너비 정의 및 창에 자동 맞춤

다음으로, 열 너비를 설정하고 테이블이 창에 맞게 조정되는지 확인합니다.

```csharp
// 표의 열 너비 설정
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```
  
 우리는 테이블에 고정된 열 너비를 설정했지만 또한 추가했습니다.`ColumnAdjustment.AutoFitToWindow`이를 통해 테이블의 크기가 사용 가능한 창에 맞게 조정됩니다.

## 5단계: 표와 셀의 테두리 및 여백 설정

테두리 없는 표는 종종 읽을 수 없습니다. 테두리와 여백을 정의하여 깔끔하게 보이도록 합시다.

```csharp
// BorderInfo 객체를 사용하여 기본 셀 테두리 설정
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// 다른 사용자 지정 BorderInfo 개체를 사용하여 테이블 테두리 설정
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

// MarginInfo 객체를 생성하고 왼쪽, 아래쪽, 오른쪽, 위쪽 여백을 설정합니다.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// MarginInfo 개체에 기본 셀 패딩을 설정합니다.
tab1.DefaultCellPadding = margin;
```
  
 테두리는 다음을 사용하여 표와 셀에 추가됩니다.`BorderInfo` 클래스에서 두께를 정의합니다. 여백은 셀에 패딩 공간을 제공하기 위해 설정됩니다.

## 6단계: 표에 행과 셀 추가

내용이 없는 표? 안 돼! 행과 셀을 추가해 보자.

```csharp
//표에 행을 만든 다음 행에 셀을 만듭니다.
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```
  
우리는 두 개의 행을 만들고 각 행에 세 개의 셀을 추가합니다. 여기서 실제 데이터(문자열에서 더 복잡한 요소까지 무엇이든 될 수 있음)를 입력하게 됩니다.

## 7단계: 문서 저장

모든 것이 설정되면 새로 만든 PDF 문서를 저장하고 싶을 겁니다.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
// 테이블 객체를 포함하는 업데이트된 문서를 저장합니다.
doc.Save(dataDir);
```
  
 그만큼`doc.Save()` 이 방법은 PDF를 지정된 디렉토리에 저장합니다. 이 경우 문서는 다음과 같이 저장됩니다.`AutoFitToWindow_out.pdf` 정의된 디렉토리에 있습니다.

## 결론

이제 다 되었습니다! Aspose.PDF for .NET을 사용하여 창에 자동으로 맞는 테이블을 만들었습니다. 이렇게 하면 테이블이 전문적이고 잘 맞는 것처럼 보일 뿐만 아니라 다양한 데이터 크기로 작업할 때 유연성도 제공됩니다. 보고서, 송장 또는 테이블이 필요한 문서를 만들 때 이 방법은 깔끔하고 읽기 쉬운 레이아웃을 유지하는 좋은 방법입니다.

## 자주 묻는 질문

### 더 많은 행을 동적으로 추가할 수 있나요?  
 예, 다음을 사용하여 행을 계속 추가할 수 있습니다.`tab1.Rows.Add()` 콘텐츠에 따라 동적으로 결정되는 방법입니다.

### 표를 자동으로 맞추고 싶지 않으면 어떻게 조정합니까?  
 수동으로 설정할 수 있습니다`ColumnWidths` 사용하지 않고`ColumnAdjustment.AutoFitToWindow` 고정된 테이블 너비를 유지합니다.

### 셀 안에 이미지나 다른 콘텐츠를 추가할 수 있나요?  
네, Aspose.PDF를 사용하면 셀 안에 이미지, 텍스트, 심지어 다른 표도 추가할 수 있습니다!

### 더 복잡한 표 스타일이 필요한 경우에는 어떻게 해야 하나요?  
배경색, 텍스트 정렬, 글꼴 설정 등의 속성을 사용하여 표와 셀 스타일을 더욱 세부적으로 사용자 지정할 수 있습니다.

### 이 표를 PDF 이외의 다른 형식으로 내보낼 수 있나요?  
물론입니다! Aspose.PDF는 HTML, DOCX 등 다양한 형식으로 내보내기를 지원합니다.