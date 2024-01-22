---
title: PDF 파일에서 확대/축소 비율 가져오기
linktitle: PDF 파일에서 확대/축소 비율 가져오기
second_title: .NET API 참조용 Aspose.PDF
description: 이 단계별 가이드를 통해 .NET용 Aspose.PDF를 사용하여 PDF 파일의 확대/축소 비율을 얻는 방법을 알아보세요.
type: docs
weight: 210
url: /ko/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET은 PDF 문서에 대해 다양한 작업을 수행할 수 있는 많은 기능을 제공하는 PDF 조작 라이브러리입니다. 이러한 기능 중 하나는 PDF 파일에서 확대/축소 비율을 가져오는 기능입니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 C# 소스 코드를 사용하여 PDF 파일의 확대/축소 비율을 얻는 방법을 설명합니다.


## 1단계: 새 Document 객체 인스턴스화

 .NET용 Aspose.PDF를 사용하여 PDF 파일의 확대/축소 비율을 얻는 첫 번째 단계는 새 파일을 인스턴스화하는 것입니다.`Document` 물체. 그만큼`Document` 객체는 파일이나 스트림에서 로드할 수 있는 PDF 문서를 나타냅니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 새 Document 객체 인스턴스화
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 위의 코드에서 우리는`Document` PDF 파일의 경로를 생성자에 전달하여 객체를 생성합니다.`Document` 수업. "YOUR DOCUMENT DIRECTORY"를 PDF 파일이 있는 디렉토리의 실제 경로로 바꿔야 합니다.

## 2단계: GoToAction 객체 생성

 다음 단계는`GoToAction` 물체. ㅏ`GoToAction`개체는 PDF 문서의 특정 대상으로 이동하는 작업을 나타냅니다. 우리의 경우에는 PDF 파일의 확대/축소 비율을 얻으려고 하므로 다음을 사용하겠습니다.`OpenAction` 의 재산`Document` 얻으려는 목적`GoToAction` 물체.

```csharp
// GoToAction 객체 생성
GoToAction action = doc.OpenAction as GoToAction;
```

 위의 코드에서 우리는`GoToAction` 캐스팅하여 이의를 제기합니다.`OpenAction` 의 재산`Document` 반대하다`GoToAction`.

## 3단계: PDF 파일의 확대/축소 비율 가져오기

 세 번째 단계는 PDF 파일의 확대/축소 비율을 얻는 것입니다. 다음에 액세스하여 PDF 파일의 확대/축소 비율을 얻을 수 있습니다.`Destination` 의 재산`GoToAction` 개체를 만든 다음 캐스팅합니다.`XYZExplicitDestination` . 그만큼`XYZExplicitDestination` 클래스는 이동할 좌표와 확대/축소 비율을 지정하는 PDF 문서의 대상을 나타냅니다.

```csharp
// PDF 파일의 확대/축소 비율 가져오기
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // 문서 확대/축소 값;
```

 위의 코드에서 우리는`Destination` 의 재산`GoToAction` 개체를 만든 다음 캐스팅하세요.`XYZExplicitDestination` . 그 후, 우리는`Zoom` 의 재산`XYZExplicitDestination` PDF 파일의 확대/축소 비율을 가져오는 개체입니다.

## 4단계: 확대/축소 비율 출력

 마지막 단계는 PDF 파일의 확대/축소 비율을 출력하는 것입니다. 우리는`System.Console.WriteLine`

```csharp
// PDF 파일의 확대/축소 비율 가져오기
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // 문서 확대/축소 값;
```        

### .NET용 Aspose.PDF를 사용하여 확대/축소 비율 가져오기에 대한 예제 소스 코드

다음은 .NET용 Aspose.PDF를 사용하여 확대/축소 비율 가져오기의 전체 예제 소스 코드입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 새 Document 객체 인스턴스화
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// GoToAction 객체 생성
GoToAction action = doc.OpenAction as GoToAction;

// PDF 파일의 확대/축소 비율 가져오기
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // 문서 확대/축소 값;
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일의 확대/축소 비율을 얻는 방법을 살펴보았습니다. 확대/축소 비율은 뷰어에서 열 때 초기 표시 크기를 결정하므로 PDF 문서의 중요한 측면입니다. 개발자는 확대/축소 비율에 액세스하고 이를 활용하여 최종 사용자의 보기 환경을 맞춤 설정할 수 있습니다. .NET용 Aspose.PDF는 PDF 문서에서 확대/축소 비율 및 기타 탐색 관련 정보를 검색할 수 있는 간단하고 효과적인 API를 제공하여 개발자가 기능이 풍부한 대화형 PDF 응용 프로그램을 구축할 수 있도록 지원합니다.

### PDF 파일의 확대/축소 비율 얻기에 대한 FAQ

#### Q: PDF 파일의 확대/축소 비율은 무엇입니까?

답변: PDF 파일의 확대/축소 비율은 문서를 볼 때 문서에 적용되는 확대 수준을 나타냅니다. 화면에 표시되는 PDF 파일의 초기 표시 크기를 결정합니다. 1.0의 확대/축소 비율은 실제 크기(100% 확대/축소)를 나타내고, 1.0보다 큰 확대/축소 비율은 확대를 나타내고, 1.0보다 작은 확대/축소 비율은 축소를 나타냅니다.

#### Q: 내 애플리케이션에서 확대/축소 비율 정보를 어떻게 사용할 수 있나요?

답변: 확대/축소 비율 정보를 사용하여 뷰어에서 PDF 문서를 열 때 PDF 문서의 초기 표시 크기를 사용자 정의할 수 있습니다. 예를 들어, PDF가 특정 크기로 표시되도록 하거나 전체 페이지를 뷰어 창에 맞추기 위해 특정 확대/축소 비율을 설정할 수 있습니다.

#### Q: .NET용 Aspose.PDF를 사용하여 프로그래밍 방식으로 PDF 문서의 확대/축소 비율을 수정할 수 있습니까?

 A: 예, .NET용 Aspose.PDF를 사용하여 프로그래밍 방식으로 PDF 문서의 확대/축소 비율을 수정할 수 있습니다. 다음과 같은 특정 작업에 대한 확대/축소 비율을 설정할 수 있습니다.`GoToAction` 또는`GoToRemoteAction`사용자가 링크나 책갈피와 상호 작용할 때 문서가 표시되는 방식을 제어합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서의 특정 위치로 이동하는 다른 방법이 있습니까?

 A: 예, Aspose.PDF for .NET은 PDF 문서의 특정 위치를 탐색할 수 있는 다양한 기능을 제공합니다. 사용하는 것 외에도`GoToAction` , 다음과 같은 다른 작업을 사용할 수 있습니다.`GoToURIAction` URL을 열려면`GoToEmbeddedAction` 포함된 파일을 탐색하고`GoToNamedAction` PDF 문서 내에서 명명된 대상으로 이동합니다.