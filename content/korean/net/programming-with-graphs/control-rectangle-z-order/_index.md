---
title: PDF 파일의 직사각형 Z 순서 제어
linktitle: PDF 파일의 직사각형 Z 순서 제어
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에서 직사각형의 Z 순서를 제어하는 방법을 알아보세요.
type: docs
weight: 40
url: /ko/net/programming-with-graphs/control-rectangle-z-order/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 직사각형의 Z 순서를 제어하기 위해 다음 C# 소스 코드를 단계별로 안내합니다.

시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본 지식이 있어야 합니다.

## 1단계: 문서 디렉터리 설정

제공된 소스 코드에서 결과 PDF 파일을 저장할 디렉터리를 지정해야 합니다. "dataDir" 변수를 원하는 디렉터리로 변경합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 개체 인스턴스화 및 페이지 추가

Document 클래스의 인스턴스를 만들고 이 문서에 페이지를 추가합니다.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## 3단계: 페이지 크기 설정

SetPageSize 메서드를 사용하여 PDF 페이지 크기를 설정합니다.

```csharp
page1.SetPageSize(375, 300);
```

## 4단계: 페이지 여백 설정

PageInfo 개체의 속성을 사용하여 페이지 여백을 구성할 수 있습니다.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## 5단계: 지정된 Z 순서로 직사각형 추가

다양한 색상과 지정된 Z 순서로 페이지에 직사각형을 생성하고 추가합니다.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## 6단계: 결과 PDF 파일 저장

마지막으로 지정된 디렉터리에 "ControlRectangleZOrder_out.pdf"라는 이름으로 결과 PDF 파일을 저장합니다.

```csharp
doc1.Save(dataDir);
```
### .NET용 Aspose.PDF를 사용하는 Control Rectangle Z Order의 샘플 소스 코드 

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 클래스 객체 인스턴스화
Document doc1 = new Document();
/// PDF 파일의 페이지 모음에 페이지 추가
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// PDF 페이지 크기 설정
page1.SetPageSize(375, 300);
// 페이지 개체의 왼쪽 여백을 0으로 설정
page1.PageInfo.Margin.Left = 0;
// 페이지 개체의 위쪽 여백을 0으로 설정
page1.PageInfo.Margin.Top = 0;
// 색상을 빨간색으로, Z 순서를 0으로, 특정 치수를 사용하여 새 직사각형을 만듭니다.
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// 색상을 파란색으로, Z 순서를 0으로, 특정 치수를 사용하여 새 직사각형을 만듭니다.
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
//색상을 녹색으로, Z 순서를 0으로, 특정 치수를 사용하여 새 직사각형을 만듭니다.
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// 결과 PDF 파일 저장
doc1.Save(dataDir);

```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 직사각형의 Z 순서를 제어하는 방법을 설명했습니다. 이제 이 지식을 사용하여 PDF 파일의 직사각형을 정밀하게 정렬하고 계층화할 수 있습니다.

### FAQ의 제어 사각형 z 순서(PDF 파일)

#### Q: 이 튜토리얼의 목적은 무엇입니까?

A: 이 튜토리얼의 목표는 .NET용 Aspose.PDF를 사용하여 직사각형의 Z 순서를 제어하는 과정을 안내하여 PDF 파일에서 직사각형을 배열하고 레이어링할 수 있도록 하는 것입니다.

#### Q: 시작하기 전에 어떤 전제 조건이 필요합니까?

A: 시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본적인 이해가 있는 것이 좋습니다.

#### Q: PDF 파일을 저장할 디렉터리를 어떻게 지정합니까?

A: 제공된 소스 코드에서 "dataDir" 변수를 수정하여 결과 PDF 파일을 저장할 디렉터리를 나타낼 수 있습니다.

#### Q: 페이지 크기와 여백을 설정하는 목적은 무엇입니까?

A: 페이지 크기와 여백을 설정하면 PDF 페이지의 레이아웃을 구성하는 데 도움이 되며 사각형을 정렬할 수 있는 캔버스가 제공됩니다.

#### Q: 지정된 Z 순서로 직사각형을 어떻게 추가합니까?

 A: 다음을 사용하여 페이지에 직사각형을 만들고 추가할 수 있습니다.`AddRectangle` 메서드를 사용하여 각 직사각형의 위치, 치수, 색상 및 Z 순서를 지정합니다.

#### Q: Z 순서란 무엇이며, 왜 중요한가요?

A: Z 순서는 페이지에 개체가 쌓이는 순서를 결정합니다. Z 순서 값이 높은 개체는 Z 순서 값이 낮은 개체 위에 배치되어 가시성 및 레이어링에 영향을 미칩니다.

#### Q: 직사각형의 색상과 크기를 사용자 정의할 수 있나요?

 A: 예.`AddRectangle` 방법.

#### Q: 직사각형을 정렬한 후 결과 PDF 파일을 어떻게 저장합니까?

 A: 직사각형을 정렬한 후 다음을 사용하여 결과 PDF 파일을 저장할 수 있습니다.`doc1.Save(dataDir);` 제공된 소스 코드의 한 줄.