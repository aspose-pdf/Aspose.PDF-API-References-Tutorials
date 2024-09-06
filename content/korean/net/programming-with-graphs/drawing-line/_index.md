---
title: 선 그리기
linktitle: 선 그리기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 페이지에 선을 그리는 방법을 알아보세요. 사용자 지정 선을 만드는 단계별 가이드.
type: docs
weight: 80
url: /ko/net/programming-with-graphs/drawing-line/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 선을 그리는 방법을 단계별로 C# 소스 코드로 안내해 드리겠습니다.

시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본 지식이 있어야 합니다.

## 1단계: 문서 디렉토리 설정

제공된 소스 코드에서 결과 PDF 파일을 저장할 디렉토리를 지정해야 합니다. "dataDir" 변수를 원하는 디렉토리로 변경합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 인스턴스 생성 및 페이지 추가

Document 클래스의 인스턴스를 생성하고 이 문서에 페이지를 추가합니다.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## 3단계: 페이지 여백 설정

우리는 모든 면의 페이지 여백을 0으로 설정했습니다.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## 4단계: 그래프 객체 및 첫 번째 줄 만들기

페이지 크기와 같은 크기의 Graph 객체를 생성하고 페이지의 왼쪽 아래 모서리에서 오른쪽 위 모서리까지 첫 번째 선을 그립니다.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## 5단계: 두 번째 선 그리기

두 번째 선을 페이지의 왼쪽 상단 모서리에서 오른쪽 하단 모서리까지 그립니다.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## 6단계: 페이지에 그래프 개체 추가

Graph 객체를 페이지의 문단 컬렉션에 추가합니다.

```csharp
pg.Paragraphs.Add(graph);
```

## 7단계: 결과 PDF 파일 저장

마지막으로, 지정된 디렉토리에 "DrawingLine_out.pdf"라는 이름의 PDF 파일을 저장합니다.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 선을 그리기 위한 샘플 소스 코드 

```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 인스턴스 생성
Document pDoc = new Document();
// PDF 문서의 페이지 컬렉션에 페이지 추가
Page pg = pDoc.Pages.Add();
// 모든 면의 페이지 여백을 0으로 설정하세요
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// 페이지 크기와 동일한 너비와 높이로 그래프 객체를 만듭니다.
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// 페이지의 왼쪽 하단에서 오른쪽 상단 모서리까지 첫 번째 줄 객체를 만듭니다.
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Graph 객체의 모양 컬렉션에 선 추가
graph.Shapes.Add(line);
// 페이지 왼쪽 상단 모서리에서 페이지 오른쪽 하단 모서리까지 선을 그립니다.
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Graph 객체의 모양 컬렉션에 선 추가
graph.Shapes.Add(line2);
// 페이지의 문단 컬렉션에 그래프 개체 추가
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// PDF 파일 저장
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 선을 그리는 방법을 설명했습니다. 이제 이 지식을 사용하여 PDF 파일에서 사용자 정의 선이 있는 기하학적 모양을 만들 수 있습니다.

### 자주 묻는 질문

#### 질문: 이 튜토리얼의 목적은 무엇인가요?

A: 이 튜토리얼의 목적은 Aspose.PDF for .NET을 사용하여 선을 그리는 과정을 안내하는 것입니다. PDF 페이지에서 선을 만들고 모양을 사용자 지정하는 방법을 배우게 됩니다.

#### 질문: 시작하기 전에 어떤 전제 조건이 필요한가요?

A: 시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. C# 프로그래밍에 대한 기본 지식도 권장됩니다.

#### 질문: PDF 파일을 저장할 디렉토리를 어떻게 지정합니까?

답변: 제공된 소스 코드의 "dataDir" 변수를 수정하여 결과 PDF 파일을 저장할 디렉토리를 지정합니다.

#### 질문: PDF 페이지에 선을 어떻게 만듭니까?

A: 이 튜토리얼에서는 페이지의 치수로 Graph 객체를 생성한 다음 Line 객체를 추가하는 방법을 보여줍니다. Line 객체의 좌표와 속성을 수정하여 원하는 선을 만듭니다.

#### 질문: 선의 모양을 사용자 지정할 수 있나요?

A: 네, Line 객체의 속성을 수정하여 선의 모양을 사용자 지정할 수 있습니다. 여기에는 좌표, 색상, 두께 및 기타 그래픽 속성을 변경하는 것이 포함됩니다.

#### 질문: 선을 그린 후 PDF 문서를 어떻게 저장합니까?

 A: 페이지에 Line 개체와 함께 Graph 개체를 추가한 후에는 다음을 사용하여 결과 PDF 문서를 저장할 수 있습니다.`pDoc.Save(dataDir + "DrawingLine_out.pdf");` 제공된 소스 코드의 줄입니다.

#### 질문: 다양한 각도와 방향으로 선을 그릴 수 있나요?

대답: 네, 그래프 내 선 객체의 좌표와 속성을 조정하여 다양한 각도와 방향으로 선을 그릴 수 있습니다.