---
title: 문서 만들기
linktitle: 문서 만들기
second_title: .NET API 참조용 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 라디오 버튼이 있는 문서를 쉽게 만들 수 있습니다.
type: docs
weight: 40
url: /ko/net/programming-with-forms/create-doc/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 라디오 버튼이 있는 문서를 만드는 방법을 보여줍니다. 이 프로세스를 안내하기 위해 C# 소스 코드를 단계별로 설명하겠습니다.

##1단계: 준비

먼저, 필요한 라이브러리를 가져왔는지 확인하고 문서 디렉터리 경로를 설정하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 새 문서 만들기

PDF 문서를 보관할 새 Document 개체를 만듭니다.

```csharp
Document doc = new Document();
```

## 3단계: 페이지 추가

문서에 새 페이지를 추가합니다.

```csharp
Page page = doc.Pages.Add();
```

## 4단계: 라디오 버튼 필드 추가

라디오 버튼 필드를 생성하고 위치와 크기를 설정합니다.

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## 5단계: 라디오 버튼 옵션 추가

라디오 버튼 필드에 원하는 옵션을 추가합니다. 필요에 따라 각 옵션의 좌표와 크기를 설정할 수 있습니다.

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## 6단계: 양식에 라디오 버튼 필드 추가

문서 양식 필드 컬렉션에 라디오 버튼 필드를 추가합니다.

```csharp
doc.Form.Add(field);
```

## 7단계: 문서 저장

PDF 문서를 저장합니다.

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 문서 만들기의 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// 새 문서 만들기
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// 라디오 버튼 필드 추가
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// 라디오 버튼 옵션을 추가합니다. 이 옵션은 위치되어 있습니다.
	// 가로도 세로도 아닙니다.
	// 좌표(심지어 크기까지)를 설정할 수 있습니다.
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// PDF 문서 저장
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 라디오 버튼이 있는 문서를 만드는 방법을 배웠습니다. 다음 단계를 따르면 Aspose.PDF를 사용하여 PDF 문서에 라디오 버튼을 쉽게 추가할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 문서의 라디오 버튼 모양을 사용자 정의할 수 있나요?

A: 예, .NET용 Aspose.PDF를 사용하여 문서의 라디오 버튼 모양을 사용자 정의할 수 있습니다. 크기, 색상, 테두리 스타일 등과 같은 속성을 설정하여 라디오 버튼의 모양을 사용자 정의할 수 있습니다.

#### Q: 상호 배타적인 옵션이 있는 라디오 버튼 그룹을 추가하려면 어떻게 해야 합니까?

A: 상호 배타적인 옵션을 생성하려면 동일한 이름을 가진 여러 개의 라디오 버튼 필드를 추가할 수 있습니다. 이렇게 하면 하나의 옵션을 선택할 때 동일한 이름을 가진 다른 옵션이 자동으로 선택 취소됩니다.

#### Q: 라디오 버튼에 대해 기본 선택 옵션을 설정할 수 있습니까?

A: 예, .NET용 Aspose.PDF를 사용하여 라디오 버튼에 대해 기본 선택 옵션을 설정할 수 있습니다. 당신은 사용할 수 있습니다`Selected` 의 재산`RadioButtonOptionField` 옵션을 기본적으로 선택된 것으로 표시하는 개체입니다.

#### Q: 라디오 버튼에 이벤트 핸들러를 추가할 수 있나요?

 A: 예, .NET용 Aspose.PDF를 사용하여 라디오 버튼에 이벤트 핸들러를 추가할 수 있습니다. 다음과 같은 JavaScript 작업을 연결할 수 있습니다.`OnValueChanged`, 사용자가 옵션을 선택할 때 특정 작업을 수행하는 라디오 버튼입니다.

#### Q: 사용자가 선택한 후 라디오 버튼 그룹에서 선택한 옵션을 검색하려면 어떻게 해야 합니까?

 A: .NET용 Aspose.PDF를 사용하여 라디오 버튼 그룹에서 선택한 옵션을 검색할 수 있습니다. 사용자가 선택한 후에는 다음 항목에 액세스할 수 있습니다.`Selected` 의 재산`RadioButtonOptionField` 어떤 옵션이 선택되었는지 확인하는 개체입니다.