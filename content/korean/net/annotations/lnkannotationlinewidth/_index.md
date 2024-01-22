---
title: lnk 주석 줄 너비
linktitle: lnk 주석 줄 너비
second_title: .NET API 참조용 Aspose.PDF
description: 이 문서에서는 .NET용 Aspose.PDF를 사용하여 lnk 주석의 선 너비를 설정하는 단계별 가이드를 제공합니다.
type: docs
weight: 110
url: /ko/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF는 .NET 애플리케이션에서 PDF 파일 작업을 위해 강력하고 널리 사용되는 도구입니다. 페이지에 주석을 추가하는 기능을 포함하여 PDF 파일을 생성, 편집 및 조작하기 위한 다양한 기능을 제공합니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 링크 주석의 선 너비를 설정하는 방법을 설명합니다.

이러한 필수 구성 요소가 있으면 Visual Studio에서 새 콘솔 애플리케이션 프로젝트를 만듭니다. 그런 다음 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "NuGet 패키지 관리"를 선택한 다음 NuGet 패키지 관리자에서 "Aspose.PDF"를 검색하여 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가합니다.

PDF 문서에 lnk 주석을 추가하려면 다음 단계를 따르십시오.

##  1단계: 새로 만들기`Document` object.
```csharp
Document doc = new Document();
```
## 2단계: 문서에 새 페이지를 추가합니다.
```csharp
doc.Pages.Add();
```
##  3단계: 목록 만들기`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  4단계: 새로 만들기`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  5단계: 새로 만들기`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## 6단계: 잉크 제스처 목록에 제스처를 추가합니다.
```csharp
inkList.Add(gesture);
```
##  7단계: 새로 만들기`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## 8단계: 주석의 제목과 제목을 설정합니다.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## 9단계: 주석 색상을 설정합니다.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  10단계: 새로 만들기`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## 11단계: 페이지에 주석을 추가합니다.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## 12단계: 문서를 파일에 저장합니다.
```csharp
// 출력 파일 저장
doc.Save(dataDir);


```
### 이 예에서는 .NET용 Aspose.PDF를 사용한 lnk 주석 줄 너비를 보여줍니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// 출력 파일 저장
doc.Save(dataDir);
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 링크 주석의 선 너비를 설정하는 방법을 배웠습니다. .NET용 Aspose.PDF는 링크 주석을 생성하고 사용자 정의하는 기능을 포함하여 PDF 문서 작업을 위한 광범위한 도구와 기능을 제공합니다. 단계별 가이드를 따르고 제공된 C# 소스 코드를 사용하여 개발자는 PDF 문서에 대화형 링크를 쉽게 추가하여 응용 프로그램의 사용자 경험과 상호 작용성을 향상시킬 수 있습니다. Aspose.PDF for .NET은 .NET 개발자가 PDF 파일을 효율적이고 효과적으로 작업할 수 있도록 지원하는 다목적 라이브러리입니다.

### FAQ

#### Q: PDF 문서의 링크 주석이란 무엇입니까?

답변: PDF 문서의 링크 주석은 사용자를 동일한 문서 내의 다른 위치, 외부 웹 사이트 또는 다른 PDF 문서로 안내하는 하이퍼링크나 작업을 만들 수 있는 대화형 요소입니다.

#### Q: .NET용 Aspose.PDF를 사용하여 링크 주석의 선 너비를 어떻게 설정할 수 있습니까?

A: .NET용 Aspose.PDF를 사용하여 링크 주석의 선 너비를 설정하려면`InkAnnotation` 개체를 선택하고 선 너비 속성을 지정합니다.

#### Q: .NET용 Aspose.PDF에서 링크 주석에 대해 어떤 속성을 사용자 정의할 수 있습니까?

A: 위치, 크기, 색상, 테두리 속성(너비, 스타일, 대시 패턴 및 효과), 제목, 제목 및 가시성과 같은 Aspose.PDF for .NET에서 링크 주석의 다양한 속성을 사용자 정의할 수 있습니다.

#### Q: 여러 잉크 제스처가 포함된 링크 주석을 만들 수 있습니까?

 A: 예, 여러 잉크 제스처를 추가하여 여러 잉크 제스처가 포함된 링크 주석을 만들 수 있습니다.`Point` 배열을`InkAnnotation` 물체.

#### Q: PDF 문서의 특정 페이지에 링크 주석을 추가하려면 어떻게 해야 합니까?

 A: PDF 문서의 특정 페이지에 링크 주석을 추가하려면 PDF 문서를 생성할 때 페이지 번호를 지정해야 합니다.`InkAnnotation` 물체. 예를 들어,`new InkAnnotation(doc.Pages[1], ...)` 첫 번째 페이지에 링크 주석을 추가합니다.