---
title: 알파 색상으로 직사각형 만들기
linktitle: 알파 색상으로 직사각형 만들기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 투명한 색상으로 직사각형을 만드는 방법을 알아보세요. 투명도를 사용자 정의하기 위한 단계별 가이드입니다.
type: docs
weight: 60
url: /ko/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 알파 색상이 포함된 사각형을 만드는 다음 C# 소스 코드를 단계별로 안내합니다.

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
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 3단계: 그래프 개체 및 사각형 만들기

지정된 치수를 가진 Graph 개체와 특정 치수를 가진 직사각형을 만듭니다.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## 4단계: 직사각형의 알파 색상 설정

System.드로잉.Color 클래스의 FromArgb 메서드를 사용하여 사각형의 알파 색상을 지정할 수 있습니다.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## 5단계: 그래프 개체에 직사각형 추가

Graph 개체의 모양 컬렉션에 사각형을 추가합니다.

```csharp
canvas.Shapes.Add(rect);
```

## 6단계: 다른 알파 색상을 사용하여 두 번째 직사각형 만들기

특정 치수와 다른 알파 색상을 사용하여 두 번째 직사각형을 만듭니다.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## 7단계: 페이지에 그래프 개체 추가

Graph 개체를 Page 개체의 Paragraph 컬렉션에 추가합니다.

```csharp
page.Paragraphs.Add(canvas);
```

## 8단계: 결과 PDF 파일 저장

마지막으로 지정된 디렉터리에 "CreateRectangleWithAlphaColor_out.pdf"라는 이름으로 결과 PDF 파일을 저장합니다.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 알파 색상으로 직사각형 만들기에 대한 샘플 소스 코드 

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 인스턴스 인스턴스화
Document doc = new Document();
// PDF 파일의 페이지 모음에 페이지 추가
Aspose.Pdf.Page page = doc.Pages.Add();
// 그래프 인스턴스 만들기
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// 특정 치수의 직사각형 객체 생성
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//32비트 ARGB 값의 System. Drawing.Color 구조에서 그래프 채우기 색상 설정
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Graph 인스턴스의 모양 컬렉션에 사각형 개체 추가
canvas.Shapes.Add(rect);
// 두 번째 직사각형 객체 만들기
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// 페이지 개체의 단락 컬렉션에 그래프 인스턴스 추가
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// PDF 파일 저장
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 알파 색상으로 직사각형을 만드는 방법을 설명했습니다. 이제 이 지식을 사용하여 PDF 파일에서 투명한 색상으로 기하학적 모양을 만들 수 있습니다.

## FAQ

#### Q: 이 튜토리얼의 목적은 무엇입니까?

A: 이 튜토리얼의 목표는 .NET용 Aspose.PDF를 사용하여 알파 색상으로 직사각형을 만드는 과정을 안내하는 것입니다. PDF 파일에 투명한 색상의 기하학적 모양을 추가하는 방법을 배우게 됩니다.

#### Q: 시작하기 전에 어떤 전제 조건이 필요합니까?

A: 시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본적인 이해가 있는 것이 좋습니다.

#### Q: PDF 파일을 저장할 디렉터리를 어떻게 지정합니까?

A: 제공된 소스 코드에서 "dataDir" 변수를 수정하여 결과 PDF 파일을 저장할 디렉터리를 나타낼 수 있습니다.

#### Q: Graph 개체와 Rectangle의 용도는 무엇인가요?

A: 그래프 개체는 그리기 요소의 컨테이너 역할을 하는 반면 직사각형은 PDF에 추가할 기하학적 모양을 나타냅니다.

#### Q: 직사각형의 알파 색상을 어떻게 설정합니까?

A: 다음을 사용하여 직사각형의 알파 색상을 지정할 수 있습니다.`FillColor` 의 재산`GraphInfo` 객체와`Color.FromRgb` ARGB 값을 사용하는 메서드입니다.

#### Q: 서로 다른 알파 색상을 사용하여 여러 개의 직사각형을 만들 수 있습니까?

A: 예, 튜토리얼에 설명된 것과 유사한 단계를 수행하여 다양한 알파 색상으로 여러 개의 직사각형을 만들 수 있습니다.

#### Q: 알파 색상으로 직사각형을 만든 후 결과 PDF 파일을 어떻게 저장합니까?

 A: 알파 색상으로 직사각형을 만든 후 다음을 사용하여 결과 PDF 파일을 저장할 수 있습니다.`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` 제공된 소스 코드의 한 줄.