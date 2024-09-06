---
title: lnk 주석 선 너비
linktitle: lnk 주석 선 너비
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF에서 잉크 주석 선 너비를 설정하는 방법을 알아보세요. 이 자세한 튜토리얼은 각 단계를 안내하여 고품질 출력을 보장합니다.
type: docs
weight: 110
url: /ko/net/annotations/lnkannotationlinewidth/
---
## 소개

PDF 문서로 작업할 때 주석을 추가하면 정보를 강조 표시하거나 파일에 대화형 요소를 추가하는 강력한 방법이 될 수 있습니다. 그러한 주석 중 하나는 PDF에 자유형 선을 그릴 수 있는 잉크 주석입니다. 하지만 이러한 선의 모양, 특히 선 너비를 사용자 지정해야 하는 경우는 어떨까요? 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 잉크 주석 선 너비를 설정하는 과정을 안내합니다.

## 필수 조건

코드를 살펴보기 전에 이 튜토리얼을 원활하게 따라갈 수 있도록 모든 것이 설정되어 있는지 확인해 보겠습니다.

1.  .NET용 Aspose.PDF: .NET용 Aspose.PDF 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[다운로드 페이지](https://releases.aspose.com/pdf/net/) 또는 Visual Studio의 NuGet 패키지 관리자를 통해 설치합니다.
2. 개발 환경: 이 튜토리얼에서는 Visual Studio와 같은 .NET 개발 환경에서 작업하고 있다고 가정합니다.
3. C#에 대한 기본 지식: C#에 대한 기본적인 이해는 코딩 단계를 따라가는 데 도움이 됩니다.
4. PDF 문서: 기존 PDF 문서를 사용하거나 이 튜토리얼을 위해 새 PDF 문서를 만드세요.

## 필요한 네임스페이스 가져오기

코딩을 시작하기 전에 프로젝트에 필요한 네임스페이스를 가져와야 합니다.

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

이러한 네임스페이스는 PDF 문서를 조작하고, 주석을 다루고, 그래픽 요소를 처리하는 데 필요한 클래스와 메서드를 제공합니다.

이제 전제 조건이 충족되었으므로 잉크 주석 선 너비를 설정하는 과정을 명확하고 관리하기 쉬운 단계로 나누어 보겠습니다.

## 1단계: PDF 문서 초기화

먼저, PDF 문서를 만들거나 열어야 합니다. 이 튜토리얼에서는 처음부터 새 PDF 문서를 만들겠습니다.

```csharp
// PDF 문서 초기화
string dataDir = "YOUR DOCUMENT DIRECTORY"; // 문서 디렉토리를 지정하세요
Document doc = new Document();
doc.Pages.Add(); // 문서에 빈 페이지 추가
```

 여기서 우리는 새로운 것을 초기화하고 있습니다`Document` 객체는 PDF 파일을 나타냅니다. 그런 다음 이 문서에 빈 페이지를 추가하여 작업합니다.

## 2단계: 잉크 주석 만들기

다음으로 잉크 주석 자체를 만들겠습니다. 여기에는 잉크 획을 구성하는 점을 정의하는 것이 포함됩니다.

```csharp
// 잉크 주석 만들기
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

 이 단계에서는 다음을 정의합니다.`LineInfo` 잉크 스트로크의 좌표, 가시성, 색상 및 초기 선 너비를 보유하는 객체입니다.`VerticeCoordinate` 배열에는 선의 각 지점의 X, Y 좌표가 포함됩니다.

## 3단계: 좌표를 점으로 변환

이제 이 좌표를 잉크 주석에서 사용할 수 있는 점으로 변환해야 합니다.

```csharp
// 좌표를 점으로 변환
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

 이 루프는 좌표 배열을 처리하여 각 좌표 쌍을 다음 좌표로 변환합니다.`Point` 그런 다음 객체가 추가됩니다.`inkList`.

## 4단계: PDF 페이지에 잉크 주석 추가

포인트가 준비되면 이제 잉크 주석을 만들어 PDF 페이지에 추가할 수 있습니다.

```csharp
// PDF 페이지에 잉크 주석 추가
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

 이 단계에서는 다음을 초기화합니다.`InkAnnotation`객체, 페이지, 경계 사각형, 그리고 포인트 목록을 지정합니다. 또한 주석의 주제, 제목, 색상을 설정합니다.

## 5단계: 주석 테두리 사용자 지정

주석의 모양을 더욱 세부적으로 사용자 지정하려면 테두리 속성을 수정합니다.

```csharp
// 주석 테두리 사용자 지정
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

 여기서 우리는 다음을 생성합니다.`Border` 주석에 대한 객체를 만들고, 너비, 효과, 대시 패턴, 스타일을 설정합니다. 이 단계는 주석이 PDF 페이지에서 시각적으로 돋보이도록 합니다.

## 6단계: PDF 문서 저장

마지막으로 필요한 모든 변경을 한 후에는 문서를 저장할 때입니다.

```csharp
// PDF 문서 저장
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

 이 코드는 지정된 디렉토리에 잉크 주석이 있는 수정된 PDF 문서를 저장합니다.`Console.WriteLine` 이 문장은 코드가 성공적으로 실행되었음을 확인합니다.

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 문서에서 잉크 주석을 성공적으로 만들고 사용자 지정했습니다. 이 튜토리얼에서는 문서 초기화부터 최종 파일 저장까지 전체 프로세스를 다루었습니다. 이러한 지식을 바탕으로 Aspose.PDF for .NET의 방대한 기능을 더 탐색하고 다른 유형의 주석이나 PDF 조작에 유사한 기술을 적용할 수 있습니다.

## 자주 묻는 질문

### 잉크 주석의 각 부분에 다른 색상을 사용할 수 있나요?  
 네, 여러 개를 만들 수 있습니다.`InkAnnotation` 다양한 색상의 객체를 선택하여 PDF의 같은 페이지나 다른 페이지에 추가합니다.

### 줄 너비를 동적으로 변경하려면 어떻게 해야 하나요?  
 조정할 수 있습니다`LineWidth` 의 속성`LineInfo` 좌표를 점으로 변환하기 전에 객체를 지정합니다.

### 잉크 주석을 투명하게 만들 수 있나요?  
 네, 수정할 수 있습니다.`Opacity` 의 속성`InkAnnotation` 투명하게 만들기 위해 반대합니다.

### 같은 페이지에 여러 개의 잉크 주석을 추가할 수 있나요?  
물론입니다! 프로세스를 반복하여 한 페이지에 원하는 만큼 많은 잉크 주석을 추가할 수 있습니다.

### PDF에서 잉크 주석을 제거하려면 어떻게 해야 하나요?  
 다음을 사용하여 주석을 제거할 수 있습니다.`doc.Pages[1].Annotations.Delete(a1)` 방법, 여기서`a1` 주석 객체입니다.