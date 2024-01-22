---
title: PDF 파일에 레이어 추가
linktitle: PDF 파일에 레이어 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에 레이어를 추가하는 방법을 알아보세요. 계층화된 PDF를 만들고 저장하기 위한 코드 튜토리얼이 포함된 단계별 가이드입니다.
type: docs
weight: 20
url: /ko/net/programming-with-document/addlayers/
---
PDF 파일에 레이어를 추가하기 위해 Aspose.PDF for .NET을 활용하겠습니다. 이 라이브러리를 사용하면 .NET 응용 프로그램에서 PDF 파일을 효과적으로 작업할 수 있습니다. .NET용 Aspose.PDF를 사용하여 레이어를 추가하려면 아래의 단계별 지침을 따르세요.

## 1단계: 새 PDF 문서 만들기

 새 인스턴스를 생성하여 시작합니다.`Document` .NET용 Aspose.PDF에서 제공하는 클래스입니다. 이는 레이어를 추가할 PDF 문서로 사용됩니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## 2단계: 문서에 페이지 추가

 다음으로,`Add` 의 방법`Pages` 의 컬렉션`Document` 수업.

```csharp
Page page = doc.Pages.Add();
```

## 3단계: 페이지에 레이어 생성 및 추가

 인스턴스를 생성합니다.`Layer` PDF 파일에 추가하려는 각 레이어에 대한 클래스입니다. 각 레이어의 고유 식별자와 이름을 지정합니다.

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

이 튜토리얼에서는 색상과 이름이 다른 세 개의 레이어를 페이지에 추가했습니다.

## 4단계: PDF 파일 저장

 다음을 사용하여 수정된 PDF 파일을 저장합니다.`Save` 의 방법`Document` 수업.

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

이 코드는 수정된 PDF 파일을 지정된 디렉토리에 저장합니다.

### .NET용 Aspose.PDF를 사용하여 PDF 페이지에 레이어를 추가하는 예제 소스 코드

```csharp            
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## 결론

이 기사에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일에 레이어를 추가하는 방법에 대한 단계별 가이드를 제공했습니다. 지침을 따르고 제공된 코드 튜토리얼을 활용하면 레이어를 PDF 문서에 쉽게 통합할 수 있습니다. 레이어를 사용하면 콘텐츠의 가시성을 구성하고 제어할 수 있어 사용자에게 보다 대화형이고 사용자 정의 가능한 환경을 제공할 수 있습니다.


### PDF 파일에 레이어 추가에 대한 FAQ

#### Q: .NET용 Aspose.PDF이 무엇인가요?

A: .NET용 Aspose.PDF는 개발자가 .NET 애플리케이션에서 PDF 파일을 효과적으로 작업할 수 있도록 지원하는 강력한 라이브러리입니다. PDF 문서 생성, 수정 및 조작을 위한 광범위한 기능을 제공합니다.

#### Q: PDF 레이어란 무엇입니까?

답변: OCG(선택적 콘텐츠 그룹)라고도 알려진 PDF 레이어를 사용하면 PDF 파일 내 특정 콘텐츠의 가시성과 모양을 제어할 수 있습니다. 콘텐츠를 구성하고 대화형 문서를 만드는 데 유용합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 파일에 여러 레이어를 추가할 수 있나요?

A: 예, .NET용 Aspose.PDF를 사용하여 PDF 파일에 여러 레이어를 추가할 수 있습니다. 튜토리얼에서 설명한 것처럼 각 레이어는 고유한 식별자와 이름을 가질 수 있습니다.

#### Q: 레이어의 모양을 어떻게 사용자 정의할 수 있나요?

A: 색상, 불투명도, 가시성 등 다양한 속성을 지정하여 레이어의 모양을 사용자 정의할 수 있습니다. .NET용 Aspose.PDF는 이를 달성하기 위한 다양한 옵션을 제공합니다.

#### Q: Aspose.PDF for .NET은 전문 프로젝트에 적합합니까?

A: 예, .NET용 Aspose.PDF는 전문 프로젝트에서 PDF 조작을 위해 안정적이고 널리 사용되는 라이브러리입니다. .NET 애플리케이션에서 PDF 파일 작업을 위한 광범위한 기능과 탁월한 성능을 제공합니다.