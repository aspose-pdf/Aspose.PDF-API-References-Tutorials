---
title: 그라데이션 채우기로 도면 추가
linktitle: 그라데이션 채우기로 도면 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 그라데이션 채우기가 있는 그림을 추가하는 방법을 알아보세요. 매력적인 PDF 문서를 만드는 단계별 튜토리얼입니다.
type: docs
weight: 20
url: /ko/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 그래픽 프로그래밍에 그라데이션 채우기가 포함된 그림을 추가하기 위해 다음 C# 소스 코드를 단계별로 안내합니다.

시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본 지식이 있어야 합니다.

## 1단계: 문서 디렉터리 설정

제공된 소스 코드에서 결과 PDF 파일을 저장할 디렉터리를 지정해야 합니다. "dataDir" 변수를 원하는 디렉터리로 변경합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 개체 인스턴스화 및 페이지 추가

Document 클래스의 인스턴스를 만들고 이 문서에 페이지를 추가합니다.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 3단계: 그래프 개체 생성 및 페이지에 추가

지정된 크기로 그래프 개체를 만들고 이를 페이지의 단락 컬렉션에 추가합니다.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## 4단계: 직사각형 개체 생성 및 차트에 추가

지정된 크기로 Rectangle 객체를 생성하고 이를 차트의 모양 컬렉션에 추가합니다.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## 5단계: 그라데이션 채우기 구성

GradientAxialShading 클래스를 사용하여 사각형의 그라데이션 채우기를 구성합니다.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

그러면 지점 (0, 0)에서 지점 (300, 300)까지 빨간색에서 파란색으로 그라데이션 채우기가 생성됩니다.

## 6단계: PDF 파일 저장

마지막으로 지정된 디렉토리에 "Add DrawingWithGradientFill_out.pdf"라는 이름으로 결과 PDF 파일을 저장합니다.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 그라데이션 채우기로 도면 추가에 대한 샘플 소스 코드 

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 그래픽 프로그래밍에 그라데이션 채우기가 포함된 그림을 추가하는 방법을 단계별로 설명했습니다. 이제 이 지식을 활용하여 맞춤형 디자인과 그라데이션 채우기가 포함된 매력적인 PDF 문서를 만들 수 있습니다.

### FAQ

#### Q: 이 튜토리얼의 목적은 무엇입니까?

A: 이 튜토리얼의 목적은 Aspose.PDF for .NET을 사용하여 그래픽 프로그래밍에 그라데이션 채우기가 포함된 그림을 추가하는 과정을 안내하는 것입니다.

#### Q: 시작하기 전에 어떤 전제 조건이 필요합니까?

A: 시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본적인 이해가 있는 것이 좋습니다.

#### Q: PDF 파일을 저장할 디렉터리를 어떻게 지정합니까?

A: 제공된 소스 코드에서 "dataDir" 변수의 값을 변경하여 결과 PDF 파일을 저장할 디렉터리를 나타낼 수 있습니다.

#### Q: 그래프 개체의 목적은 무엇입니까?

A: Graph 개체는 그리기 요소의 컨테이너 역할을 합니다. 지정된 크기로 생성되어 페이지의 단락 컬렉션에 추가됩니다.

#### Q: 도형에 그라데이션 채우기를 구성하려면 어떻게 해야 합니까?

A: 그라데이션 채우기를 구성하려면 GradientAxialShading 클래스를 사용하여 모양 GraphInfo의 FillColor 속성을 설정할 수 있습니다. 이를 통해 그라디언트의 시작 및 끝 지점과 전환할 색상을 정의할 수 있습니다.

#### Q: 그라데이션 채우기의 색상과 방향을 사용자 정의할 수 있나요?

A: 예, Color 객체를 조정하고 GradientAxialShading의 시작점과 끝점을 지정하여 그라데이션 채우기의 색상과 방향을 사용자 정의할 수 있습니다.

#### Q: 튜토리얼의 마지막 단계는 무엇입니까?

A: 마지막 단계에서는 결과 PDF 파일을 지정된 디렉터리에 "Add DrawingWithGradientFill_out.pdf"라는 이름으로 저장하는 작업이 포함됩니다.

#### Q: 사용 가능한 샘플 소스 코드가 있습니까?

A: 예, 튜토리얼에서는 설명된 단계를 구현하기 위한 참조로 사용할 수 있는 샘플 소스 코드를 제공합니다.

#### Q: 직사각형 외의 다른 도형에도 그라데이션 채우기를 적용할 수 있나요?

A: 예, 다른 모양에도 그라데이션 채우기를 적용할 수 있습니다. 이 프로세스에는 GradientAxialShading 클래스를 사용하여 모양 GraphInfo의 FillColor 속성을 구성하는 작업이 포함됩니다.