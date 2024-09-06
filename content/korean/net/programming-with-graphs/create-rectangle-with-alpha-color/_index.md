---
title: 알파 색상으로 사각형 만들기
linktitle: 알파 색상으로 사각형 만들기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 투명한 색상으로 사각형을 만드는 방법을 알아보세요. 투명도를 사용자 정의하는 단계별 가이드.
type: docs
weight: 60
url: /ko/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 알파 색상이 적용된 사각형을 만드는 방법을 C# 소스 코드를 단계별로 안내합니다.

시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본 지식이 있어야 합니다.

## 1단계: 문서 디렉토리 설정

제공된 소스 코드에서 결과 PDF 파일을 저장할 디렉토리를 지정해야 합니다. "dataDir" 변수를 원하는 디렉토리로 변경합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 개체 인스턴스화 및 페이지 추가

Document 클래스의 인스턴스를 생성하고 이 문서에 페이지를 추가합니다.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 3단계: 그래프 객체 및 사각형 만들기

지정된 차원의 Graph 객체와 특정 차원의 사각형을 생성합니다.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## 4단계: 사각형의 알파 색상 설정

System.Drawing.Color 클래스의 FromArgb 메서드를 사용하여 사각형의 알파 색상을 지정할 수 있습니다.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## 5단계: 그래프 개체에 사각형 추가

Graph 객체의 모양 컬렉션에 사각형을 추가합니다.

```csharp
canvas.Shapes.Add(rect);
```

## 6단계: 다른 알파 색상을 사용하여 두 번째 사각형 만들기

우리는 특정한 치수와 다른 알파 색상을 갖는 두 번째 사각형을 만듭니다.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## 7단계: 페이지에 그래프 개체 추가

Graph 객체를 Page 객체의 Paragraph 컬렉션에 추가합니다.

```csharp
page.Paragraphs.Add(canvas);
```

## 8단계: 결과 PDF 파일 저장

마지막으로, 지정된 디렉토리에 "CreateRectangleWithAlphaColor_out.pdf"라는 이름의 PDF 파일을 저장합니다.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 알파 색상으로 사각형 만들기 샘플 소스 코드 

```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 인스턴스화
Document doc = new Document();
// PDF 파일의 페이지 컬렉션에 페이지 추가
Aspose.Pdf.Page page = doc.Pages.Add();
// 그래프 인스턴스 생성
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// 특정 치수로 사각형 객체를 생성합니다.
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// 32비트 ARGB 값에서 System.Drawing.Color 구조의 그래프 채우기 색상 설정
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Graph 인스턴스의 shapes 컬렉션에 사각형 객체를 추가합니다.
canvas.Shapes.Add(rect);
// 두 번째 사각형 객체 생성
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// 페이지 객체의 문단 컬렉션에 그래프 인스턴스 추가
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// PDF 파일 저장
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 알파 색상이 있는 사각형을 만드는 방법을 설명했습니다. 이제 이 지식을 사용하여 PDF 파일에서 투명한 색상이 있는 기하학적 모양을 만들 수 있습니다.

## 자주 묻는 질문

#### 질문: 이 튜토리얼의 목적은 무엇인가요?

A: 이 튜토리얼은 Aspose.PDF for .NET을 사용하여 알파 색상이 있는 사각형을 만드는 과정을 안내합니다. PDF 파일에 투명한 색상이 있는 기하학적 모양을 추가하는 방법을 배우게 됩니다.

#### 질문: 시작하기 전에 어떤 전제 조건이 필요한가요?

A: 시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본적인 이해가 있는 것이 좋습니다.

#### 질문: PDF 파일을 저장할 디렉토리를 어떻게 지정합니까?

답변: 제공된 소스 코드에서 "dataDir" 변수를 수정하여 결과 PDF 파일을 저장할 디렉토리를 지정할 수 있습니다.

#### 질문: 그래프 객체와 사각형의 목적은 무엇인가요?

답변: 그래프 객체는 그리기 요소를 위한 컨테이너 역할을 하는 반면, 사각형은 PDF에 추가할 기하학적 모양을 나타냅니다.

#### 질문: 사각형에 알파 색상을 어떻게 설정할 수 있나요?

 A: 사각형의 알파 색상을 지정할 수 있습니다.`FillColor` 의 속성`GraphInfo` 객체와`Color.FromRgb` ARGB 값을 사용하는 방법.

#### 질문: 알파 색상이 다른 여러 개의 사각형을 만들 수 있나요?

대답: 네, 튜토리얼에서 보여준 것과 비슷한 단계를 따라가면 다양한 알파 색상을 사용해 여러 개의 사각형을 만들 수 있습니다.

#### 질문: 알파 색상으로 사각형을 만든 후 생성된 PDF 파일을 어떻게 저장합니까?

 A: 알파 색상으로 사각형을 만든 후에는 다음을 사용하여 결과 PDF 파일을 저장할 수 있습니다.`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` 제공된 소스 코드의 줄입니다.