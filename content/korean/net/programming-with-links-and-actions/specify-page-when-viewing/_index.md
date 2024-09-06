---
title: 보기 시 페이지 지정
linktitle: 보기 시 페이지 지정
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF를 볼 때 페이지를 지정하는 방법을 알아보세요.
type: docs
weight: 110
url: /ko/net/programming-with-links-and-actions/specify-page-when-viewing/
---
이 단계별 가이드를 통해 Aspose.PDF for .NET을 사용하여 PDF 파일을 볼 때 페이지를 지정하는 방법을 알아보세요.

## 1단계: 환경 설정

C# 프로젝트와 적절한 Aspose.PDF 참조로 개발 환경을 설정했는지 확인하세요.

## 2단계: PDF 파일 로딩

다음 코드를 사용하여 문서의 디렉토리 경로를 설정하고 PDF 파일을 업로드하세요.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// PDF 파일을 로드합니다
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## 3단계: 대상 페이지 지정

다음 코드를 사용하여 대상 페이지 인스턴스를 가져옵니다.

```csharp
Page page2 = doc.Pages[2];
```

 인덱스를 조정할 수 있습니다`[2]` 원하는 페이지를 선택하세요.

## 4단계: 확대/축소 설정 구성

대상 페이지 확대/축소 비율을 설정하기 위한 변수를 만듭니다.

```csharp
double zoom = 1;
```

사용자의 필요에 맞게 줌 값을 조절할 수 있습니다.

## 5단계: 탐색 작업 만들기

지정된 대상 페이지를 사용하여 탐색 작업의 인스턴스를 만듭니다.

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## 6단계: 목적지 설정

좌표와 확대/축소를 사용하여 대상 페이지로 이동할 목적지를 설정합니다.

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## 7단계: 문서 열기 동작 구성

생성된 탐색 동작으로 문서 열기 동작을 설정합니다.

```csharp
doc. OpenAction = action;
```

## 8단계: 업데이트된 문서 저장

 업데이트된 문서를 저장하려면 다음을 사용합니다.`Save` 방법:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 볼 때 페이지 지정을 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF 파일을 로드합니다
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// 문서의 두 번째 페이지 인스턴스를 가져옵니다.
Page page2 = doc.Pages[2];
// 대상 페이지의 확대/축소 비율을 설정하기 위한 변수를 생성합니다.
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

축하합니다! 이제 Aspose.PDF for .NET을 사용하여 PDF를 볼 때 페이지를 지정하는 방법을 알게 되었습니다. 이 지식을 사용하여 PDF 문서에서 사용자 보기 환경을 사용자 지정하세요.

이제 이 가이드를 완료했으니, 이러한 개념을 여러분의 프로젝트에 적용하고 .NET용 Aspose.PDF가 제공하는 기능을 더욱 자세히 탐색해 볼 수 있습니다.

### 자주 묻는 질문 

#### 질문: PDF 파일을 볼 때 대상 페이지를 지정하는 목적은 무엇입니까?

A: 대상 페이지를 지정하면 파일을 열 때 PDF 문서의 어느 페이지가 표시되는지 제어할 수 있습니다. 이를 통해 관심 있는 특정 페이지로 안내하여 사용자 경험을 향상시킬 수 있습니다.

#### 질문: PDF 문서에서 대상 페이지를 지정하는 것이 어떻게 유용할 수 있나요?

답변: PDF 문서 내에서 사용자가 페이지를 직접 탐색하지 않고도 특정 섹션이나 콘텐츠로 이동할 수 있도록 안내하려는 경우 대상 페이지를 지정하는 것이 유용합니다.

#### 질문: .NET용 Aspose.PDF는 어떻게 대상 페이지를 지정하여 볼 수 있게 하나요?

답변: .NET용 Aspose.PDF는 대상 페이지, 확대/축소 수준, 기타 표시 속성을 포함하여 PDF 문서의 초기 보기를 설정할 수 있는 API를 제공합니다.

#### 질문: 어떤 페이지든 대상 페이지로 지정할 수 있나요?

A: 네, PDF 문서 내의 모든 페이지를 볼 대상 페이지로 지정할 수 있습니다. 적절한 인덱스를 사용하여 원하는 페이지를 선택하기만 하면 됩니다.

#### 질문: 대상 페이지를 지정할 때 확대/축소 비율은 어떤 의미가 있나요?

A: 확대/축소 계수는 PDF 문서를 열 때 대상 페이지에 적용되는 확대 수준을 결정합니다. 뷰포트 내에 표시되는 콘텐츠 양을 제어합니다.

#### 질문: 다른 대상 페이지에 대해 다른 확대/축소 비율을 설정할 수 있나요?

A: 예, 별도의 확대/축소 요소를 생성하여 다른 대상 페이지에 대해 다른 확대/축소 요소를 설정할 수 있습니다.`GoToAction` 인스턴스를 생성하고 그에 따라 대상지를 구성합니다.

#### 질문: 대상 페이지를 지정하는 데 제한이 있나요?

A: 대상 페이지 지정은 PDF가 열릴 때 초기 뷰를 제어하는 데 국한됩니다. PDF가 표시된 후에는 사용자 상호 작용이나 탐색에 영향을 미치지 않습니다.

#### 질문: 이 기능을 사용하여 PDF 문서 내에서 프레젠테이션을 만들 수 있나요?

대답: 네, 이 기능을 사용하면 PDF 문서 내에서 프레젠테이션과 같은 경험을 만들어 사용자를 다양한 섹션이나 주제로 안내할 수 있습니다.

#### 질문: 페이지 레이아웃 등 초기 보기의 다른 측면을 사용자 지정할 수 있나요?

대답: 네, .NET용 Aspose.PDF는 페이지 레이아웃, 페이지 모드 등 초기 보기의 다른 측면을 사용자 정의할 수 있는 속성을 제공합니다.

#### 질문: 지정된 대상 페이지와 확대/축소 비율이 의도한 대로 작동하는지 어떻게 테스트할 수 있나요?

답변: 제공된 코드를 적용하여 대상 페이지와 확대/축소 비율을 지정한 후, 수정된 PDF 파일을 열어 올바른 페이지와 확대/축소 수준으로 열리는지 확인합니다.