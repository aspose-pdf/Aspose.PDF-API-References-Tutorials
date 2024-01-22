---
title: 볼 때 페이지 지정
linktitle: 볼 때 페이지 지정
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF를 볼 때 페이지를 지정하는 방법을 알아보세요.
type: docs
weight: 110
url: /ko/net/programming-with-links-and-actions/specify-page-when-viewing/
---
이 단계별 가이드를 통해 .NET용 Aspose.PDF를 사용하여 PDF 파일을 볼 때 페이지를 지정하는 방법을 알아보세요.

## 1단계: 환경 설정

C# 프로젝트와 적절한 Aspose.PDF 참조를 사용하여 개발 환경을 설정했는지 확인하세요.

## 2단계: PDF 파일 로드

문서의 디렉터리 경로를 설정하고 다음 코드를 사용하여 PDF 파일을 업로드하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// PDF 파일 로드
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## 3단계: 대상 페이지 지정

다음 코드를 사용하여 대상 페이지 인스턴스를 가져옵니다.

```csharp
Page page2 = doc.Pages[2];
```

 인덱스를 조정할 수 있습니다.`[2]` 원하는 페이지를 선택하세요.

## 4단계: 확대/축소 설정 구성

대상 페이지 확대/축소 비율을 설정하는 변수를 만듭니다.

```csharp
double zoom = 1;
```

필요에 따라 확대/축소 값을 조정할 수 있습니다.

## 5단계: 탐색 작업 만들기

지정된 대상 페이지를 사용하여 탐색 작업의 인스턴스를 만듭니다.

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## 6단계: 목적지 설정

좌표와 확대/축소를 사용하여 대상 페이지로 이동할 대상을 설정합니다.

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## 7단계: 문서 열기 작업 구성

생성된 탐색 작업으로 문서 열기 작업을 설정합니다.

```csharp
doc. OpenAction = action;
```

## 8단계: 업데이트된 문서 저장

 다음을 사용하여 업데이트된 문서를 저장합니다.`Save` 방법:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 볼 때 페이지 지정의 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF 파일 로드
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// 문서의 두 번째 페이지 인스턴스 가져오기
Page page2 = doc.Pages[2];
// 대상 페이지의 확대/축소 비율을 설정하는 변수를 만듭니다.
double zoom = 1;
// GoToAction 인스턴스 생성
GoToAction action = new GoToAction(doc.Pages[2]);
// 2페이지로 이동
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// 문서 열기 동작 설정
doc.OpenAction = action;
// 업데이트된 문서 저장
doc.Save(dataDir + "goto2page_out.pdf");
```

## 결론

축하합니다! 이제 Aspose.PDF for .NET을 사용하여 PDF를 볼 때 페이지를 지정하는 방법을 알았습니다. 이 지식을 활용하여 PDF 문서의 사용자 보기 환경을 맞춤화하세요.

이제 이 가이드를 완료했으므로 이러한 개념을 자신의 프로젝트에 적용하고 .NET용 Aspose.PDF가 제공하는 기능을 더 자세히 살펴볼 수 있습니다.

### FAQ 

#### Q: PDF 파일을 볼 때 대상 페이지를 지정하는 목적은 무엇입니까?

A: 대상 페이지를 지정하면 파일을 열 때 표시되는 PDF 문서의 페이지를 제어할 수 있습니다. 이를 통해 관심 있는 특정 페이지로 사용자를 연결함으로써 사용자 경험을 향상시킬 수 있습니다.

#### Q: PDF 문서에서 대상 페이지를 지정하는 것이 어떻게 유용합니까?

A: 대상 페이지를 지정하는 것은 사용자가 페이지를 수동으로 탐색할 필요 없이 PDF 문서 내의 특정 섹션이나 콘텐츠를 안내하려는 경우 유용합니다.

#### Q: .NET용 Aspose.PDF는 보려는 대상 페이지 지정을 어떻게 용이하게 합니까?

답변: .NET용 Aspose.PDF는 대상 페이지, 확대/축소 수준 및 기타 표시 속성을 포함하여 PDF 문서의 초기 보기를 설정할 수 있는 API를 제공합니다.

#### Q: 어떤 페이지든 대상 페이지로 지정할 수 있나요?

A: 예, PDF 문서 내의 모든 페이지를 볼 대상 페이지로 지정할 수 있습니다. 적절한 색인을 사용하여 원하는 페이지를 선택하기만 하면 됩니다.

#### Q: 대상 페이지를 지정할 때 확대/축소 비율의 의미는 무엇입니까?

답변: 확대/축소 비율은 PDF 문서를 열 때 대상 페이지에 적용되는 확대 수준을 결정합니다. 뷰포트 내에 표시되는 콘텐츠의 양을 제어합니다.

#### Q: 대상 페이지별로 확대/축소 비율을 다르게 설정할 수 있나요?

A: 예, 별도의 생성을 통해 다양한 대상 페이지에 대해 서로 다른 확대/축소 비율을 설정할 수 있습니다.`GoToAction` 인스턴스를 생성하고 그에 따라 대상을 구성합니다.

#### Q: 대상 페이지 지정에 제한이 있나요?

A: 대상 페이지 지정은 PDF를 열 때 초기 보기를 제어하는 것으로 제한됩니다. PDF가 표시된 후에는 사용자 상호 작용이나 탐색에 영향을 주지 않습니다.

#### 질문: 이 기능을 사용하여 PDF 문서 내에서 프레젠테이션을 만들 수 있습니까?

A: 예, 이 기능을 사용하면 PDF 문서 내에서 프레젠테이션과 같은 경험을 만들어 사용자에게 다양한 섹션이나 주제를 안내할 수 있습니다.

#### Q: 페이지 레이아웃과 같은 초기 보기의 다른 측면을 사용자 정의할 수 있습니까?

A: 예, .NET용 Aspose.PDF는 페이지 레이아웃, 페이지 모드 등을 포함하여 초기 보기의 다른 측면을 사용자 정의하는 속성을 제공합니다.

#### Q: 지정된 대상 페이지와 확대/축소 비율이 의도한 대로 작동하는지 어떻게 테스트할 수 있나요?

A: 제공된 코드를 적용하여 대상 페이지와 확대/축소 비율을 지정한 후 수정된 PDF 파일을 열고 올바른 페이지와 확대/축소 수준으로 열리는지 확인하세요.