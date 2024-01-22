---
title: PDF 파일에서 확대/축소 비율 설정
linktitle: PDF 파일에서 확대/축소 비율 설정
second_title: .NET API 참조용 Aspose.PDF
description: 단계별 가이드를 통해 .NET용 Aspose.PDF를 사용하여 PDF 파일에서 확대/축소 비율을 설정하는 방법을 알아보세요.
type: docs
weight: 340
url: /ko/net/programming-with-document/setzoomfactor/
---
Aspose.PDF for .NET은 개발자가 .NET 애플리케이션에서 PDF 문서로 작업할 수 있도록 하는 강력한 API입니다. 그것이 제공하는 기능 중 하나는 PDF 문서의 확대/축소 비율을 설정하는 기능입니다. 이 단계별 가이드에서는 제공된 C# 소스 코드를 사용하여 PDF 문서의 확대/축소 비율을 설정하기 위해 .NET용 Aspose.PDF를 사용하는 방법을 설명합니다.

## 1단계: 문서 디렉터리 경로 설정

 첫 번째 단계는 PDF 문서가 있는 디렉토리의 경로를 설정하는 것입니다. 이는 다음을 설정하여 수행할 수 있습니다.`dataDir` 변수를 디렉터리 경로에 추가합니다. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

"YOUR DOCUMENT DIRECTORY"를 PDF 문서가 있는 실제 디렉토리 경로로 바꾸십시오.

## 2단계: 새 Document 개체 인스턴스화

 .NET용 Aspose.PDF를 사용하여 PDF 문서로 작업하려면 새 문서를 만들어야 합니다.`Document` 개체를 선택하고 PDF 파일을 해당 개체에 로드합니다. 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

 이 코드는 새로운`Document` 개체를 선택하고 다음에서 "SetZoomFactor.pdf"라는 PDF 파일을 로드합니다.`dataDir` 디렉토리를 그 안에 넣습니다.

## 3단계: 확대/축소 비율 설정

 일단`Document`개체가 생성되면 PDF 문서의 확대/축소 비율을 설정할 수 있습니다. 다음 코드에서는 확대/축소 비율을 50%로 설정했습니다.

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

 이 코드는 새 항목을 생성하여 확대/축소 비율을 50%로 설정합니다.`GoToAction` 객체를 전달하고`XYZExplicitDestination` 확대/축소 비율이 50%인 개체입니다. 그만큼`OpenAction` 의 재산`Document` 그런 다음 객체는 이것으로 설정됩니다`GoToAction` 물체.

## 4단계: PDF 문서 저장

 마지막으로 수정된 PDF 문서를 새 파일에 저장할 수 있습니다. 다음 코드에서는 PDF 문서를 "Zoomed_pdf_out.pdf"라는 새 파일에 저장합니다.`dataDir` 예배 규칙서.

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 확대/축소 비율 설정의 소스 코드 예

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 새 Document 객체 인스턴스화
Document doc = new Document(dataDir + "SetZoomFactor.pdf");

GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
dataDir = dataDir + "Zoomed_pdf_out.pdf";
// 문서 저장
doc.Save(dataDir);
```

## 결론

.NET용 Aspose.PDF는 C# 코드를 사용하여 PDF 문서의 확대/축소 비율을 설정하는 간단하고 효율적인 방법을 제공합니다. 위 단계를 수행하면 .NET 응용 프로그램에서 PDF 문서의 확대/축소 비율을 쉽게 수정할 수 있습니다.

### 자주 묻는 질문

#### Q: PDF 문서의 확대/축소 비율은 무엇이며 보기에 어떤 영향을 줍니까?

답변: PDF 문서의 확대/축소 비율은 문서를 볼 때 확대 수준을 결정합니다. 문서가 표시되는 배율을 지정하여 화면에 표시되는 콘텐츠의 크거나 작은 정도에 영향을 줍니다. 확대/축소 비율 1.0은 100% 확대/축소(실제 크기)를 나타내고, 1.0보다 큰 비율은 확대되고, 1.0보다 작은 비율은 축소됩니다.

#### Q: 동일한 PDF 문서 내의 여러 페이지에 대해 특정 확대/축소 비율을 설정할 수 있습니까?

 A: 예, .NET용 Aspose.PDF를 사용하면 동일한 PDF 문서 내의 여러 페이지에 대해 서로 다른 확대/축소 비율을 설정할 수 있습니다. 제공된 예제 소스 코드는`GoToAction` 물체. 필요에 따라 다른 페이지에 대해 다른 확대/축소 비율을 설정하도록 코드를 수정할 수 있습니다.

#### Q: 확대/축소 비율을 변경하면 PDF 문서 인쇄 및 저장에 어떤 영향을 줍니까?

A: .NET용 Aspose.PDF를 사용하여 확대/축소 비율을 변경해도 PDF 문서 자체의 실제 내용에는 영향을 미치지 않습니다. PDF 뷰어에서 문서를 열 때의 보기 환경에만 영향을 미칩니다. 프로그래밍 방식으로 설정된 확대/축소 비율은 인쇄된 출력이나 저장된 PDF 파일에 영향을 주지 않습니다.