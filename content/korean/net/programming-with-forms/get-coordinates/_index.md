---
title: PDF 양식 필드 좌표 가져오기
linktitle: PDF 양식 필드 좌표 가져오기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하면 PDF 문서에서 PDF 양식 필드 좌표를 쉽게 얻을 수 있습니다.
type: docs
weight: 120
url: /ko/net/programming-with-forms/get-coordinates/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 양식 필드 좌표를 가져오는 방법을 보여드리겠습니다. 이 과정을 안내하기 위해 C# 소스 코드를 단계별로 설명하겠습니다.

## 1단계: 준비

필요한 라이브러리를 가져왔는지 확인하고 문서 디렉토리 경로를 설정하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 출력 문서 로드

출력 PDF 문서를 로드합니다:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## 3단계: 추가된 필드 찾기

추가된 양식 필드를 찾으세요(이 예에서는 "Item1", "Item2", "Item3" 필드를 사용하고 있습니다).

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## 4단계: 각 필드에 대한 하위 항목 위치 표시

각 필드의 옵션을 순환하고 각 하위 항목의 좌표를 확인하세요.

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### .NET용 Aspose.PDF를 사용하여 좌표 가져오기 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉토리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// 출력 문서 로드
	Document doc1 = new Document( dataDir + "input.pdf");
	// 추가된 필드 찾기
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// 그리고 각 항목의 하위 항목 위치를 보여줍니다.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 폼 필드 좌표를 가져오는 방법을 배웠습니다. 이러한 단계를 따르면 Aspose.PDF를 사용하여 PDF 문서에서 폼 필드 하위 요소의 좌표를 쉽게 검색할 수 있습니다.

### 자주 묻는 질문

#### 질문: 이 방법을 사용하면 .NET용 Aspose.PDF의 모든 유형의 양식 필드에 대한 좌표를 얻을 수 있나요?

A: 네, 이 방법을 사용하면 .NET용 Aspose.PDF에서 다양한 유형의 폼 필드에 대한 좌표를 얻을 수 있습니다. 제공된 C# 소스 코드는 RadioButton 필드에 대한 좌표를 얻는 방법을 보여주지만, TextBox, CheckBox, ListBox 등과 같은 다른 폼 필드 유형에도 동일한 접근 방식을 적용할 수 있습니다.

#### 질문: 양식 필드 좌표를 수정하거나 조정하려면 어떻게 해야 하나요?

A: 양식 필드 좌표는 PDF 문서의 좌표계를 기반으로 하며, 원점(0,0)은 페이지의 왼쪽 하단 모서리에 있습니다. 양식 필드 좌표를 수정하거나 조정하려면 다음을 업데이트할 수 있습니다.`Rect` 각 양식 필드나 하위 항목의 속성(예: RadioButtonOptionField)

#### 질문: PDF 문서에 프로그래밍 방식으로 추가된 양식 필드의 좌표를 얻을 수 있나요?

A: 네, PDF 문서에 프로그래밍 방식으로 추가된 폼 필드의 좌표를 얻을 수 있습니다. Aspose.PDF for .NET을 사용하면 폼 필드를 동적으로 추가할 수 있으며, 추가한 후에는 이 튜토리얼에서 설명한 접근 방식을 사용하여 좌표를 검색할 수 있습니다.

#### 질문: 양식 필드 좌표를 검색하는 목적은 무엇입니까?

A: PDF 문서 내의 양식 필드에 대한 특정 레이아웃 관련 작업이나 검증을 수행해야 할 때 양식 필드 좌표를 검색하는 것이 도움이 될 수 있습니다. 이를 통해 좌표를 기준으로 양식 필드를 정확하게 배치하고 정렬하여 문서에 올바르게 표시되고 원활한 사용자 경험을 제공할 수 있습니다.

#### 질문: 양식 필드 좌표는 포인트로 표현되나요, 아니면 다른 단위로 표현되나요?

A: Aspose.PDF for .NET의 폼 필드 좌표는 포인트로 표현됩니다. 1포인트는 1/72인치와 동일하므로 PDF 형식의 표준 측정 단위가 됩니다.