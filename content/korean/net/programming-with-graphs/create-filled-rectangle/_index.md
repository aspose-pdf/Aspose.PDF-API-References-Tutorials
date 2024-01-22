---
title: 채워진 직사각형 만들기
linktitle: 채워진 직사각형 만들기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF로 채워진 직사각형을 만드는 방법을 알아보세요. 채우기 색상을 사용자 정의하는 단계별 안내입니다.
type: docs
weight: 50
url: /ko/net/programming-with-graphs/create-filled-rectangle/
---
이 튜토리얼에서는 다음 C# 소스 코드를 단계별로 안내하여 .NET용 Aspose.PDF를 사용하여 채워진 사각형을 만듭니다.

시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본 지식이 있어야 합니다.

## 1단계: 문서 디렉터리 설정

제공된 소스 코드에서 결과 PDF 파일을 저장할 디렉터리를 지정해야 합니다. "dataDir" 변수를 원하는 디렉터리로 변경합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 인스턴스 만들기 및 페이지 추가

Document 클래스의 인스턴스를 만들고 이 문서에 페이지를 추가합니다.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 3단계: 그래프 개체 생성 및 페이지에 추가

지정된 크기로 그래프 개체를 만들고 이를 페이지의 단락 컬렉션에 추가합니다.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## 4단계: 직사각형 개체 생성 및 차트에 추가

지정된 크기로 Rectangle 개체를 만들고 이를 차트의 모양 컬렉션에 추가합니다.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## 5단계: 채우기 색상 설정

GraphInfo 개체의 FillColor 속성을 사용하여 사각형의 채우기 색상을 지정할 수 있습니다.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## 6단계: 결과 PDF 파일 저장

마지막으로 지정된 디렉터리에 "CreateFilledRectangle_out.pdf"라는 이름으로 결과 PDF 파일을 저장합니다.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 채워진 직사각형 만들기의 샘플 소스 코드 

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 인스턴스 생성
Document doc = new Document();
// PDF 파일의 페이지 모음에 페이지 추가
Page page = doc.Pages.Add();
// 그래프 인스턴스 만들기
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// 페이지 인스턴스의 단락 컬렉션에 그래프 개체 추가
page.Paragraphs.Add(graph);
// Rectangle 인스턴스 생성
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// 그래프 개체의 채우기 색상 지정
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Graph 개체의 모양 컬렉션에 사각형 개체 추가
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF 파일 저장
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 채워진 사각형을 만드는 방법을 설명했습니다. 이제 이 지식을 사용하여 PDF 파일에서 사용자 정의 채우기 색상으로 기하학적 모양을 만들 수 있습니다.

## FAQ

#### Q: 이 튜토리얼의 목적은 무엇입니까?

A: 이 튜토리얼의 목적은 .NET용 Aspose.PDF를 사용하여 채워진 사각형을 만드는 과정을 안내하고 채우기 색상이 있는 사용자 정의 기하학적 모양을 PDF 파일에 추가할 수 있도록 하는 것입니다.

#### Q: 시작하기 전에 어떤 전제 조건이 필요합니까?

A: 시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본적인 이해가 있는 것이 좋습니다.

#### Q: PDF 파일을 저장할 디렉터리를 어떻게 지정합니까?

A: 제공된 소스 코드에서 "dataDir" 변수를 수정하여 결과 PDF 파일을 저장할 디렉터리를 나타낼 수 있습니다.

#### Q: 그래프 개체의 목적은 무엇입니까?

A: Graph 개체는 그리기 요소의 컨테이너 역할을 합니다. 지정된 크기로 생성되어 페이지의 단락 컬렉션에 추가됩니다.

#### 질문: PDF 문서에 채워진 사각형을 어떻게 추가할 수 있나요?

A: 채워진 사각형을 추가하려면 지정된 크기와 채우기 색상을 사용하여 Rectangle 클래스의 인스턴스를 만들고 이를 그래프의 모양 컬렉션에 추가하세요.

#### Q: 직사각형의 크기와 채우기 색상을 사용자 정의할 수 있습니까?

 A: 예.`Aspose.Pdf.Drawing.Rectangle` 생성자를 생성하고 FillColor 속성을 설정합니다.

#### Q: 채워진 직사각형을 만든 후 결과 PDF 파일을 어떻게 저장합니까?

 A: 채워진 직사각형을 만든 후 다음을 사용하여 결과 PDF 파일을 저장할 수 있습니다.`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` 제공된 소스 코드의 한 줄.