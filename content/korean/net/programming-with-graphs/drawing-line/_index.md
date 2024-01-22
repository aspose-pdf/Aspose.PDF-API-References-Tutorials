---
title: 선 그리기
linktitle: 선 그리기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 페이지에 선을 그리는 방법을 알아보세요. 맞춤형 선을 만드는 방법을 단계별로 안내합니다.
type: docs
weight: 80
url: /ko/net/programming-with-graphs/drawing-line/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 선을 그리는 다음 C# 소스 코드를 단계별로 안내합니다.

시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본 지식이 있어야 합니다.

## 1단계: 문서 디렉터리 설정

제공된 소스 코드에서 결과 PDF 파일을 저장할 디렉터리를 지정해야 합니다. "dataDir" 변수를 원하는 디렉터리로 변경합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 인스턴스 만들기 및 페이지 추가

Document 클래스의 인스턴스를 만들고 이 문서에 페이지를 추가합니다.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## 3단계: 페이지 여백 설정

모든 면에서 페이지 여백을 0으로 설정했습니다.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## 4단계: 그래프 개체 및 첫 번째 선 만들기

페이지의 크기와 동일한 크기의 그래프 개체를 만들고 페이지의 왼쪽 하단에서 오른쪽 상단으로 이어지는 첫 번째 선을 그립니다.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## 5단계: 두 번째 선 그리기

페이지의 왼쪽 상단에서 오른쪽 하단으로 가는 두 번째 선을 그립니다.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## 6단계: 페이지에 그래프 개체 추가

페이지의 단락 컬렉션에 Graph 개체를 추가합니다.

```csharp
pg.Paragraphs.Add(graph);
```

## 7단계: 결과 PDF 파일 저장

마지막으로 지정된 디렉토리에 " DrawingLine_out.pdf"라는 이름으로 결과 PDF 파일을 저장합니다.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### .NET용 Aspose.PDF를 사용하는 Drawing Line의 샘플 소스 코드 

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 인스턴스 생성
Document pDoc = new Document();
// PDF 문서의 페이지 모음에 페이지 추가
Page pg = pDoc.Pages.Add();
// 모든 측면의 페이지 여백을 0으로 설정
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// 너비와 높이가 페이지 크기와 동일한 그래프 개체 만들기
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// 페이지의 왼쪽 아래부터 오른쪽 위 모서리까지 시작하여 첫 번째 줄 개체를 만듭니다.
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Graph 개체의 모양 컬렉션에 선 추가
graph.Shapes.Add(line);
// 페이지의 왼쪽 상단 모서리에서 페이지의 오른쪽 하단 모서리까지 선을 그립니다.
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Graph 개체의 모양 컬렉션에 선 추가
graph.Shapes.Add(line2);
// 페이지의 단락 컬렉션에 그래프 개체 추가
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// PDF 파일 저장
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## 결론

이번 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 선을 그리는 방법을 설명했습니다. 이제 이 지식을 사용하여 PDF 파일에서 사용자 정의 선이 있는 기하학적 모양을 만들 수 있습니다.

### FAQ

#### Q: 이 튜토리얼의 목적은 무엇입니까?

A: 이 튜토리얼의 목적은 .NET용 Aspose.PDF를 사용하여 선을 그리는 과정을 안내하는 것입니다. PDF 페이지에 선을 만들고 모양을 사용자 정의하는 방법을 배우게 됩니다.

#### Q: 시작하기 전에 어떤 전제 조건이 필요합니까?

A: 시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. C# 프로그래밍에 대한 기본 지식도 권장됩니다.

#### Q: PDF 파일을 저장할 디렉터리를 어떻게 지정합니까?

A: 제공된 소스 코드에서 "dataDir" 변수를 수정하여 결과 PDF 파일을 저장할 디렉터리를 나타냅니다.

#### Q: PDF 페이지에 줄을 어떻게 만듭니까?

A: 튜토리얼에서는 페이지 크기로 그래프 개체를 만든 다음 여기에 선 개체를 추가하는 방법을 보여줍니다. Line 객체의 좌표와 속성을 수정하여 원하는 선을 만듭니다.

#### Q: 선의 모양을 사용자 정의할 수 있나요?

A: 예, Line 개체의 속성을 수정하여 선의 모양을 사용자 정의할 수 있습니다. 여기에는 좌표, 색상, 두께 및 기타 그래픽 속성 변경이 포함됩니다.

#### Q: 선을 그린 후 PDF 문서를 어떻게 저장합니까?

A: 선 개체가 포함된 그래프 개체를 페이지에 추가한 후 다음을 사용하여 결과 PDF 문서를 저장할 수 있습니다.`pDoc.Save(dataDir + "DrawingLine_out.pdf");` 제공된 소스 코드의 한 줄.

#### Q: 다양한 각도와 방향으로 선을 그릴 수 있나요?

A: 예, 그래프 내 Line 개체의 좌표와 속성을 조정하여 다양한 각도와 방향으로 선을 그릴 수 있습니다.