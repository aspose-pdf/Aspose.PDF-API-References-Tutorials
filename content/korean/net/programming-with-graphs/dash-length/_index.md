---
title: 대시 길이
linktitle: 대시 길이
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET으로 대시 길이를 설정하는 방법을 알아보세요. 대시 패턴을 사용자 정의하는 단계별 가이드.
type: docs
weight: 70
url: /ko/net/programming-with-graphs/dash-length/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 대시의 길이를 설정하는 방법을 단계별로 C# 소스 코드로 안내해 드리겠습니다.

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
Page page = doc.Pages.Add();
```

## 3단계: 그래프 개체 생성 및 페이지에 추가

지정된 차원의 Graph 객체를 생성하여 페이지의 문단 컬렉션에 추가합니다.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## 4단계: 라인 객체 생성 및 구성

지정된 좌표로 Line 객체를 생성하고 대시의 색상과 길이를 구성합니다.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## 5단계: 그래프 개체에 선 추가

Graph 객체의 shape 컬렉션에 선을 추가합니다.

```csharp
canvas.Shapes.Add(line);
```

## 6단계: 결과 PDF 파일 저장

마지막으로, 지정된 디렉토리에 "DashLength_out.pdf"라는 이름의 PDF 파일을 저장합니다.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### .NET용 Aspose.PDF를 사용한 Dash Length의 샘플 소스 코드 

```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 인스턴스화
Document doc = new Document();
// Document 객체의 pages 컬렉션에 페이지 추가
Page page = doc.Pages.Add();
// 특정 치수로 도면 객체를 생성합니다.
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// 페이지 인스턴스의 문단 컬렉션에 그리기 개체 추가
page.Paragraphs.Add(canvas);
// Line 객체 생성
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Line 객체에 대한 색상 설정
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// 라인 객체에 대한 대시 배열을 지정하세요
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Line 인스턴스에 대한 대시 단계 설정
line.GraphInfo.DashPhase = 1;
// 그리기 개체의 모양 컬렉션에 선 추가
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// PDF 문서 저장
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 대시 길이를 설정하는 방법을 설명했습니다. 이제 이 지식을 사용하여 PDF 파일에서 사용자 정의 대시 패턴이 있는 선을 만들 수 있습니다.

## 자주 묻는 질문

#### 질문: 이 튜토리얼의 목적은 무엇인가요?

A: 이 튜토리얼의 목적은 Aspose.PDF for .NET을 사용하여 선의 대시 길이를 설정하는 과정을 안내하는 것입니다. PDF 파일에서 사용자 정의 대시 패턴이 있는 선을 만드는 방법을 배우게 됩니다.

#### 질문: 시작하기 전에 어떤 전제 조건이 필요한가요?

A: 시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. C# 프로그래밍에 대한 기본적인 이해도 권장됩니다.

#### 질문: PDF 파일을 저장할 디렉토리를 어떻게 지정합니까?

답변: 제공된 소스 코드의 "dataDir" 변수를 수정하여 결과 PDF 파일을 저장할 디렉토리를 지정합니다.

#### 질문: 사용자 정의 대시 패턴이 있는 선을 어떻게 만들까요?

 A: 이 튜토리얼에서는 Line 객체를 생성하고 해당 객체의 색상, 대시 배열 및 대시 단계를 구성하는 방법을 보여줍니다.`GraphInfo` 객체. 원하는 대시 패턴을 얻으려면 이러한 설정을 수정하세요.

#### 질문: 선 색상을 사용자가 직접 설정할 수 있나요?

 A: 네, 선의 색상을 설정하여 사용자 정의할 수 있습니다.`Color` 의 속성`GraphInfo` Line과 연관된 객체입니다.

#### 질문: 대시 길이를 설정한 후 PDF 문서를 저장하려면 어떻게 해야 하나요?

 A: 원하는 대시 패턴으로 라인 객체를 구성한 후에는 다음을 사용하여 결과 PDF 문서를 저장할 수 있습니다.`doc.Save(dataDir + "DashLength_out.pdf");` 제공된 소스 코드의 줄입니다.