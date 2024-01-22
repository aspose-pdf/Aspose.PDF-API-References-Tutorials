---
title: PDF 양식 필드 좌표 가져오기
linktitle: PDF 양식 필드 좌표 가져오기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 PDF 양식 필드 좌표를 쉽게 얻을 수 있습니다.
type: docs
weight: 120
url: /ko/net/programming-with-forms/get-coordinates/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 양식 필드 좌표를 얻는 방법을 보여줍니다. 이 프로세스를 안내하기 위해 C# 소스 코드를 단계별로 설명하겠습니다.

## 1단계: 준비

필요한 라이브러리를 가져왔는지 확인하고 문서 디렉토리 경로를 설정하십시오.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 출력 문서 로드

출력 PDF 문서를 로드합니다.

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## 3단계: 추가된 필드 찾기

추가된 양식 필드를 찾습니다(이 예에서는 "Item1", "Item2" 및 "Item3" 필드를 사용함).

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## 4단계: 각 필드의 하위 항목 위치 표시

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

### .NET용 Aspose.PDF를 사용하여 좌표 가져오기의 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// 출력 문서 로드
	Document doc1 = new Document( dataDir + "input.pdf");
	// 추가된 필드 찾기
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// 그리고 각각에 대한 하위 항목의 위치를 표시합니다.
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

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 양식 필드 좌표를 얻는 방법을 배웠습니다. 다음 단계를 따르면 Aspose.PDF를 사용하여 PDF 문서에서 양식 필드의 하위 요소 좌표를 쉽게 검색할 수 있습니다.

### FAQ

#### Q: 이 방법을 사용하여 .NET용 Aspose.PDF에서 모든 유형의 양식 필드에 대한 좌표를 얻을 수 있습니까?

A: 예, 이 방법을 사용하여 .NET용 Aspose.PDF에서 다양한 유형의 양식 필드에 대한 좌표를 얻을 수 있습니다. 제공된 C# 소스 코드는 RadioButton 필드의 좌표를 가져오는 방법을 보여 주지만 TextBox, CheckBox, ListBox 등과 같은 다른 양식 필드 유형에도 동일한 접근 방식을 적용할 수 있습니다.

#### Q: 양식 필드 좌표를 수정하거나 조정하려면 어떻게 해야 합니까?

답변: 양식 필드 좌표는 PDF 문서의 좌표계를 기반으로 하며 원점(0,0)은 페이지의 왼쪽 하단에 있습니다. 양식 필드 좌표를 수정하거나 조정하려면`Rect` RadioButtonOptionField와 같은 해당 양식 필드 또는 해당 하위 항목의 속성입니다.

#### 질문: PDF 문서에 프로그래밍 방식으로 추가된 양식 필드의 좌표를 얻을 수 있습니까?

A: 예, PDF 문서에 프로그래밍 방식으로 추가된 양식 필드의 좌표를 얻을 수 있습니다. .NET용 Aspose.PDF를 사용하면 양식 필드를 동적으로 추가할 수 있으며, 추가한 후에는 이 튜토리얼에서 설명하는 접근 방식을 사용하여 해당 좌표를 검색할 수 있습니다.

#### Q: 양식 필드 좌표를 검색하는 목적은 무엇입니까?

A: PDF 문서 내의 양식 필드에 대해 특정 레이아웃 관련 작업이나 유효성 검사를 수행해야 할 때 양식 필드 좌표를 검색하는 것이 도움이 될 수 있습니다. 이를 통해 좌표를 기준으로 양식 필드를 정확하게 배치하고 정렬하여 문서에 올바르게 표시되고 원활한 사용자 경험을 제공할 수 있습니다.

#### Q: 양식 필드 좌표는 포인트로 표시되나요, 아니면 다른 단위로 표시되나요?

A: .NET용 Aspose.PDF의 양식 필드 좌표는 포인트로 표현됩니다. 1포인트는 1/72인치에 해당하므로 PDF 형식의 표준 측정 단위입니다.