---
title: PDF 문서의 둥근 모서리 테이블
linktitle: PDF 문서의 둥근 모서리 테이블
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 둥근 모서리 테이블을 만드는 방법을 알아보세요.
type: docs
weight: 190
url: /ko/net/programming-with-tables/rounded-corner-table/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 둥근 모서리 테이블을 만드는 방법을 단계별로 안내합니다. 제공된 C# 소스 코드를 설명하고 이를 구현하는 방법을 보여 드리겠습니다.

## 1단계: 테이블 생성
먼저 다음 코드를 사용하여 테이블을 생성합니다.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## 2단계: 둥근 모서리 스타일 설정
다음으로 테이블의 둥근 모서리 스타일을 구성하겠습니다.

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## 3단계: 표 테두리 설정
테이블에 둥근 모서리 테두리를 제공하려면 BorderInfo 개체를 만들고 적절한 매개변수로 구성해야 합니다.

```csharp
// GraphInfo 객체를 생성하여 테두리 색상 설정
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// 빈 BorderInfo 개체 만들기
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// 둥근 테두리의 반경을 15로 설정합니다.
bInfo.RoundedBorderRadius = 15;

// 테이블에 테두리 정보 적용
tab1.Border = bInfo;
```

### .NET용 Aspose.PDF를 사용하는 둥근 모서리 테이블의 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// 빈 BorderInfo 개체 만들기
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// 테두리를 둥근 반경이 15인 더 둥근 테두리로 설정합니다.
bInfo.RoundedBorderRadius = 15;
// 테이블 모서리 스타일을 원형으로 설정합니다.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// 표 테두리 정보 설정
tab1.Border = bInfo;
```

## 결론
축하합니다! 이제 Aspose.PDF for .NET을 사용하여 PDF 문서에서 둥근 모서리 테이블을 만드는 방법을 배웠습니다. 이 단계별 가이드에서는 둥근 모서리 스타일과 표 테두리를 설정하는 방법을 보여주었습니다. 이제 이 지식을 자신의 프로젝트에 적용할 수 있습니다.

### PDF 문서의 둥근 모서리 테이블에 대한 FAQ

#### Q: 테이블의 둥근 모서리 반경을 사용자 정의할 수 있나요?

A: 예, 값을 수정하여 테이블의 둥근 모서리 반경을 사용자 정의할 수 있습니다.`bInfo.RoundedBorderRadius` 제공된 C# 소스 코드의 속성입니다. 원하는 둥근 모서리 모양을 얻으려면 원하는 반경 값(포인트 단위)을 설정하기만 하면 됩니다.

#### Q: 테이블 내의 개별 셀에 둥근 모서리를 적용할 수 있나요?

A: 아니요, 둥근 모서리 스타일은 테이블 전체에 전체적으로 적용됩니다. .NET용 Aspose.PDF는 현재 테이블 내의 개별 셀에 둥근 모서리를 적용하는 기본 지원을 제공하지 않습니다.

#### Q: 둥근 모서리 테두리의 색상을 변경할 수 있나요?

 A: 예, 값을 수정하여 둥근 모서리 테두리의 색상을 변경할 수 있습니다.`graph.Color` C# 소스 코드의 속성입니다. 다음과 같이 원하는 색상을 제공하기만 하면 됩니다.`Aspose.Pdf.Color.Red` 또는 기타 유효한 색상 표현.

#### 질문: 동일한 PDF 문서 내의 서로 다른 테이블에 서로 다른 모서리 스타일(예: 정사각형 및 둥근 모양)을 적용할 수 있습니까?

A: 예, 동일한 PDF 문서 내의 다양한 테이블에 다양한 모서리 스타일을 적용할 수 있습니다. 요구 사항에 따라 여러 테이블을 생성하고 모서리 스타일을 개별적으로 구성할 수 있습니다.

#### Q: 둥근 모서리 테두리의 두께를 조정할 수 있나요?

 A: 예, 둥근 모서리 테두리의 두께를 수정하여 조정할 수 있습니다.`BorderInfo` C# 소스 코드의 개체 속성. 예를 들어 다음을 설정할 수 있습니다.`bInfo.Width` 테두리의 두께를 조정하는 속성입니다.