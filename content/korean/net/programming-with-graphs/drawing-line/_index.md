---
title: 선 그리기
linktitle: 선 그리기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서에 선을 그리는 방법을 알아보세요. 이 단계별 가이드는 문서 설정, 선 추가, 파일 저장을 다룹니다.
type: docs
weight: 80
url: /ko/net/programming-with-graphs/drawing-line/
---
## 소개

PDF 문서에 선을 그리는 것은 간단한 작업처럼 보일 수 있지만, 시각적 보조 자료, 다이어그램을 만들고 주요 영역을 강조하는 데 강력한 도구가 될 수 있습니다. 이 가이드에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에 선을 그리는 과정을 안내합니다. 이 튜토리얼에서는 환경 설정부터 선을 그린 PDF를 생성하는 코드 실행까지 모든 것을 다룹니다.

## 필수 조건

코드를 살펴보기 전에 몇 가지 필요한 것이 있습니다.

1.  .NET용 Aspose.PDF: .NET용 Aspose.PDF가 설치되어 있어야 합니다. 다음에서 다운로드할 수 있습니다.[Aspose 웹사이트](https://releases.aspose.com/pdf/net/).
2. .NET 개발 환경: .NET 애플리케이션을 위한 개발 환경이 설정되어 있는지 확인하세요. Visual Studio가 이에 적합한 선택입니다.
3. C#에 대한 기본 지식: C# 프로그래밍에 대한 지식은 이 튜토리얼의 코드 조각과 예제를 이해하는 데 도움이 됩니다.

## 패키지 가져오기

.NET용 Aspose.PDF를 사용하려면 관련 네임스페이스를 가져와야 합니다. C# 파일의 맨 위에 다음 using 지시문을 추가합니다.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

이러한 네임스페이스는 PDF 문서를 조작하고 도형을 그리는 데 필요한 클래스와 메서드에 대한 액세스를 제공합니다.

선을 그리는 과정을 일련의 단계로 나누어 보겠습니다. 각 단계는 코드의 특정 부분을 안내하여 원하는 결과를 얻는 방법을 이해하는 데 도움이 됩니다.

## 1단계: 문서 및 페이지 설정

첫 번째 단계는 새 PDF 문서를 만들고 페이지를 추가하는 것입니다. 이를 수행하는 방법은 다음과 같습니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 인스턴스 생성
Document pDoc = new Document();

// PDF 문서의 페이지 컬렉션에 페이지 추가
Page pg = pDoc.Pages.Add();
```

 여기,`dataDir` 출력 PDF가 저장되는 경로입니다.`Document` PDF를 처리하기 위한 주요 클래스이며,`Page` PDF 문서의 단일 페이지를 나타냅니다.

## 2단계: 페이지 여백 구성

줄이 가장자리에서 가장자리까지 확장되도록 하려면 페이지 여백을 0으로 설정해야 합니다.

```csharp
// 모든 면의 페이지 여백을 0으로 설정하세요
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

이렇게 하면 기본 여백이 제거되어 전체 페이지 캔버스에 그림을 그릴 수 있습니다.

## 3단계: 그래프 객체 생성

 다음으로, 다음을 생성합니다.`Graph` 페이지의 치수와 일치하는 개체입니다. 이 개체는 모양을 담는 용기 역할을 합니다.

```csharp
// 페이지 크기와 동일한 너비와 높이로 그래프 객체를 만듭니다.
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(pg.PageInfo.Width, pg.PageInfo.Height);
```

 그만큼`Graph` 객체를 사용하면 페이지에 모양을 추가하고 조작할 수 있습니다.

## 4단계: 첫 번째 선 그리기

이제 첫 번째 선을 그릴 시간입니다. 이 예에서는 페이지의 왼쪽 아래 모서리에서 오른쪽 위 모서리까지 선을 그립니다.

```csharp
// 페이지의 왼쪽 하단에서 오른쪽 상단 모서리까지 첫 번째 줄 객체를 만듭니다.
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });

// Graph 객체의 모양 컬렉션에 선 추가
graph.Shapes.Add(line);
```

 그만큼`Line` 클래스는 선의 시작점과 끝점에 대한 좌표를 취합니다. 여기서,`pg.Rect.LLX` 그리고`pg.Rect.URY` 각각 페이지의 왼쪽 아래와 오른쪽 위를 나타냅니다.

## 5단계: 두 번째 선 그리기

두 번째 선에서는 왼쪽 상단 모서리에서 오른쪽 하단 모서리까지 그립니다.

```csharp
// 페이지 왼쪽 상단 모서리에서 페이지 오른쪽 하단 모서리까지 선을 그립니다.
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });

// Graph 객체의 모양 컬렉션에 선 추가
graph.Shapes.Add(line2);
```

이 선은 반대 방향으로 대각선으로 페이지를 가로지릅니다.

## 6단계: 페이지에 그래프 추가

 선을 그었으므로 이제 다음을 추가해야 합니다.`Graph` 페이지의 문단 컬렉션에 대한 객체:

```csharp
// 페이지의 문단 컬렉션에 그래프 개체 추가
pg.Paragraphs.Add(graph);
```

 이 단계에서는 다음을 통합합니다.`Graph` PDF 페이지에 객체를 (줄을 넣어) 추가합니다.

## 7단계: 문서 저장

마지막으로 문서를 파일로 저장합니다.

```csharp
dataDir = dataDir + "DrawingLine_out.pdf";

// PDF 파일 저장
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);
```

 이렇게 하면 선이 그려진 PDF가 저장되고`Console.WriteLine` 이 진술은 작업이 성공적으로 이루어졌음을 확인합니다.

## 결론

Aspose.PDF for .NET을 사용하여 PDF 문서에 선을 그리는 것은 관리 가능한 단계로 나누면 간단한 프로세스입니다. 이 튜토리얼을 따라하면 PDF 문서를 설정하고, 문서를 가로지르는 선을 그리고, 최종 제품을 저장하는 방법을 배웠습니다. 다이어그램을 만들든, 텍스트를 강조하든, 단순히 PDF 조작을 실험하든, 이 가이드는 PDF에서 선을 작업하기 위한 견고한 기반을 제공합니다.

 질문이 있거나 추가 지원이 필요한 경우 언제든지 문의하십시오.[Aspose.PDF 문서](https://reference.aspose.com/pdf/net/) 또는 방문하세요[Aspose 지원 포럼](https://forum.aspose.com/c/pdf/10).

## 자주 묻는 질문

### 선 외에도 다양한 모양을 그릴 수 있나요?
 네, 사각형, 타원, 다각형 등 다양한 모양을 그릴 수 있습니다.`Aspose.Pdf.Drawing` 네임스페이스.

### 선의 색상과 두께는 어떻게 조절하나요?
 설정할 수 있습니다`Line` 사물`StrokeColor` 그리고`LineWidth` 선의 모양을 사용자 정의할 수 있는 속성입니다.

### 페이지의 특정 영역에 선을 그릴 수 있나요?
 물론입니다! 좌표만 조정하면 됩니다.`Line` 필요에 따라 선을 배치합니다.

### 줄과 함께 텍스트를 추가할 수 있나요?
 네, 다음을 만들어서 텍스트를 추가할 수 있습니다.`TextFragment` 객체를 배치하고`Paragraphs` 페이지의 컬렉션입니다.

### 새 PDF를 만드는 대신 기존 PDF에 줄을 추가하려면 어떻게 해야 하나요?
 기존 PDF를 로드하려면 다음을 사용하십시오.`Document` 그런 다음 비슷한 방법을 사용하여 기존 페이지에 줄을 추가합니다.