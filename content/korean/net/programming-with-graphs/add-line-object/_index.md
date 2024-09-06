---
title: PDF 파일에 라인 객체 추가
linktitle: PDF 파일에 라인 객체 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 사용자 정의 선 객체를 추가하는 방법을 알아보세요.
type: docs
weight: 30
url: /ko/net/programming-with-graphs/add-line-object/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 라인 객체를 추가하는 방법을 단계별로 설명하는 다음 C# 소스 코드를 안내합니다.

시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본 지식이 있어야 합니다.

## 1단계: 문서 디렉토리 설정

제공된 소스 코드에서 결과 PDF 파일을 저장할 디렉토리를 지정해야 합니다. "dataDir" 변수를 원하는 디렉토리로 변경합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 인스턴스 생성 및 페이지 추가

Document 클래스의 인스턴스를 생성하고 이 문서에 페이지를 추가합니다.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 3단계: 그래프 개체 생성 및 페이지에 추가

지정된 차원의 Graph 객체를 생성하여 페이지의 문단 컬렉션에 추가합니다.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## 4단계: 라인 객체 생성 및 차트에 추가

지정된 좌표로 Line 객체를 생성하여 차트의 모양 컬렉션에 추가합니다.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## 5단계: 라인 설정

우리는 대시 유형, 대시 단계 등의 선 속성을 지정할 수 있습니다.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## 6단계: PDF 파일 저장

마지막으로, 지정된 디렉토리에 "AddLineObject_out.pdf"라는 이름의 PDF 파일을 저장합니다.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 Add Line Object를 위한 샘플 소스 코드 

```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 인스턴스 생성
Document doc = new Document();
// PDF 파일의 페이지 컬렉션에 페이지 추가
Page page = doc.Pages.Add();
// 그래프 인스턴스 생성
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// 페이지 인스턴스의 문단 컬렉션에 그래프 객체 추가
page.Paragraphs.Add(graph);
// Rectangle 인스턴스 생성
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// 그래프 객체에 대한 채우기 색상 지정
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Graph 객체의 모양 컬렉션에 사각형 객체 추가
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// PDF 파일 저장
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 라인 객체를 추가하는 방법을 단계별로 설명했습니다. 이제 이 지식을 사용하여 애플리케이션에서 사용자 정의 라인이 있는 PDF 문서를 만들 수 있습니다.

### PDF 파일에 라인 객체를 추가하기 위한 FAQ

#### 질문: 이 튜토리얼의 목적은 무엇인가요?

답변: 이 튜토리얼은 Aspose.PDF for .NET을 사용하여 선 객체를 추가하여 PDF 문서를 향상시키는 과정을 안내합니다.

#### 질문: 시작하기 전에 어떤 전제 조건이 필요한가요?

A: 시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본적인 이해가 있는 것이 좋습니다.

#### 질문: PDF 파일을 저장할 디렉토리를 어떻게 지정합니까?

답변: 제공된 소스 코드에서 "dataDir" 변수를 수정하여 결과 PDF 파일을 저장할 디렉토리를 지정할 수 있습니다.

#### 질문: Graph 객체의 목적은 무엇인가요?

A: Graph 객체는 그리기 요소의 컨테이너 역할을 합니다. 지정된 치수로 생성되어 페이지의 문단 컬렉션에 추가됩니다.

#### 질문: PDF 문서에 선 객체를 추가하려면 어떻게 해야 하나요?

답변: 선 객체를 추가하려면 지정된 좌표로 Line 클래스의 인스턴스를 생성하고 그래프의 모양 컬렉션에 추가합니다.

#### 질문: 선의 모양을 사용자 지정할 수 있나요?

대답: 네, Line 객체의 GraphInfo 속성을 사용하여 대시 유형 및 대시 위상과 같은 속성을 설정하여 선의 모양을 사용자 정의할 수 있습니다.

#### 질문: 대시 배열과 대시 위상을 지정하는 목적은 무엇입니까?

대답: 대시 배열 및 대시 위상 속성을 사용하면 특정 패턴의 파선이나 점선을 만들 수 있습니다.

#### 질문: 선 객체를 추가한 후 PDF 파일을 어떻게 저장할 수 있나요?

 A: 라인 객체를 추가한 후에는 다음을 사용하여 결과 PDF 파일을 저장할 수 있습니다.`doc.Save(dataDir + "AddLineObject_out.pdf");` 제공된 소스 코드의 줄입니다.

#### 질문: 샘플 소스 코드가 있나요?

대답: 네, 튜토리얼에는 설명된 단계를 구현하는 데 참조할 수 있는 샘플 소스 코드가 포함되어 있습니다.