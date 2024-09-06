---
title: 수평 및 수직 라디오 버튼
linktitle: 수평 및 수직 라디오 버튼
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하면 PDF 문서에 가로 및 세로 라디오 버튼을 쉽게 만들 수 있습니다.
type: docs
weight: 180
url: /ko/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 가로 및 세로로 배열된 라디오 버튼을 만드는 방법을 보여드리겠습니다. 이 과정을 안내하기 위해 C# 소스 코드를 단계별로 설명하겠습니다.

## 1단계: 준비

필요한 라이브러리를 가져왔는지 확인하고 문서 디렉토리 경로를 설정하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 로드

기존 PDF 문서를 로드합니다:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## 3단계: 라디오 버튼 옵션 사용자 정의

다음 속성을 설정하여 라디오 버튼 옵션을 사용자 정의하세요.

```csharp
formEditor. RadioGap = 4; // 두 개의 라디오 버튼 옵션 사이의 거리
formEditor. RadioHoriz = true; //라디오 버튼의 수평 레이아웃
formEditor.RadioButtonItemSize = 20; // 라디오 버튼의 크기
formEditor.Facade.BorderWidth = 1; // 라디오 버튼 테두리의 너비
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // 라디오 버튼 테두리 색상
```

## 4단계: 수평 라디오 버튼 추가

옵션과 필드 위치를 지정하여 수평으로 배열된 라디오 버튼을 추가합니다.

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## 5단계: 수직 라디오 버튼 추가

옵션과 필드 위치를 지정하여 수직으로 배열된 라디오 버튼을 추가합니다.

```csharp
formEditor. RadioHoriz = false; // 라디오 버튼의 수직 레이아웃
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## 6단계: 문서 저장

수정된 PDF 문서를 저장합니다.

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용한 수평 및 수직 라디오 버튼에 대한 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉토리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// 이전에 저장된 문서를 로드합니다
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap은 두 개의 라디오 버튼 옵션 사이의 거리입니다.
	formEditor.RadioGap = 4;
	// 수평 라디오 버튼 추가
	formEditor.RadioHoriz = true;
	// 라디오 버튼 항목의 크기인 RadioButtonItemSize입니다.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// 수직으로 배치된 다른 라디오 버튼 추가
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// PDF 문서 저장
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 가로 및 세로로 배열된 라디오 버튼을 만드는 방법을 배웠습니다. 이러한 단계를 따르면 라디오 버튼의 레이아웃을 쉽게 사용자 정의하고 Aspose.PDF를 사용하여 PDF 문서에 추가할 수 있습니다.

### 자주 묻는 질문

#### 질문: PDF 문서에서 수평 및 수직으로 배열된 라디오 버튼은 무엇입니까?

A: PDF 문서에서 가로 및 세로로 배열된 라디오 버튼은 라디오 버튼 옵션의 레이아웃 방향을 말합니다. 가로 레이아웃은 라디오 버튼 옵션을 나란히 배치하여 사용자가 왼쪽에서 오른쪽으로 선택할 수 있도록 합니다. 반면 세로 레이아웃은 라디오 버튼 옵션을 서로 위에 쌓아 사용자가 위에서 아래로 선택할 수 있도록 합니다.

#### 질문: .NET용 Aspose.PDF에서 라디오 버튼 옵션의 모양을 사용자 지정하려면 어떻게 해야 하나요?

A: Aspose.PDF for .NET에서 라디오 버튼 옵션의 모양을 사용자 정의하려면 여러 속성을 조정하면 됩니다. API는 두 라디오 버튼 옵션 사이의 거리를 설정하는 옵션을 제공합니다(`RadioGap`), 레이아웃 방향(`RadioHoriz`), 라디오 버튼 항목의 크기(`RadioButtonItemSize`), 라디오 버튼의 테두리 너비, 색상 등입니다.

#### 질문: 동일한 PDF 문서에 수평 및 수직 라디오 버튼을 모두 추가할 수 있나요?

A: 네, Aspose.PDF for .NET을 사용하여 동일한 PDF 문서에 가로 및 세로 라디오 버튼을 모두 추가할 수 있습니다. 튜토리얼에 제공된 샘플 소스 코드는 먼저 가로로 배열된 라디오 버튼을 추가한 다음 세로로 배열된 다른 라디오 버튼 세트를 동일한 PDF 문서에 추가하는 방법을 보여줍니다.

#### 질문: 각 라디오 버튼 그룹에 대해 다른 라디오 버튼 옵션을 설정할 수 있나요?

 A: 네, 각 라디오 버튼 그룹에 대해 다른 라디오 버튼 옵션을 설정할 수 있습니다. 각 그룹에는 고유한 옵션이 있어야 합니다.`RadioButtonField` 객체 및`RadioButtonOptionField` 각 그룹 내의 객체는 동일한 페이지와 옵션에 대한 고유한 이름을 공유해야 합니다. 이렇게 하면 각 그룹 내의 라디오 버튼이 올바르게 작동하고 선택 사항이 상호 배타적이 됩니다.

#### 질문: 라디오 버튼의 레이아웃과 모양 설정이 모든 PDF 뷰어와 애플리케이션에서 지원되나요?

A: 네, 라디오 버튼의 레이아웃 및 모양 설정은 모든 표준 호환 PDF 뷰어 및 애플리케이션에서 지원됩니다. PDF 사양은 라디오 버튼과 다양한 속성을 정의하여 PDF 형식에서 보편적으로 인식되도록 합니다. 그러나 다양한 플랫폼에서 일관된 렌더링을 보장하기 위해 다양한 PDF 뷰어에서 라디오 버튼의 모양과 동작을 테스트하는 것이 필수적입니다.