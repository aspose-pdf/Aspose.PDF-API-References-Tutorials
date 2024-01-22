---
title: PDF 문서의 그룹화된 확인란
linktitle: PDF 문서의 그룹화된 확인란
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서에 그룹화된 확인란을 쉽게 만들 수 있습니다.
type: docs
weight: 170
url: /ko/net/programming-with-forms/grouped-check-boxes/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 그룹화된 확인란을 만드는 방법을 보여줍니다. 이 프로세스를 안내하기 위해 C# 소스 코드를 단계별로 설명하겠습니다.

## 1단계: 준비

필요한 라이브러리를 가져왔는지 확인하고 문서 디렉터리 경로를 설정하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 개체 인스턴스화

Document 객체를 인스턴스화합니다.

```csharp
Document pdfDocument = new Document();
```

## 3단계: PDF 문서에 페이지 추가

PDF 문서에 페이지를 추가합니다.

```csharp
Page page = pdfDocument.Pages.Add();
```

## 4단계: RadioButtonField 개체 인스턴스화

페이지 번호를 인수로 사용하여 RadioButtonField 객체를 인스턴스화합니다.

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## 5단계: 라디오 버튼 옵션 추가

RadioButtonOptionField 객체를 사용하여 라디오 버튼 옵션을 추가하고 Rectangle 객체를 사용하여 해당 위치를 지정합니다.

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## 6단계: 라디오 버튼 옵션 사용자 정의

스타일, 테두리 및 모양을 설정하여 라디오 버튼 옵션을 사용자 정의합니다.

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## 7단계: 양식에 라디오 버튼 추가

문서 양식 개체에 라디오 버튼을 추가합니다.

```csharp
pdfDocument.Form.Add(radio);
```

## 8단계: 문서 저장

PDF 문서를 저장합니다.

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 그룹화된 확인란에 대한 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// 문서 객체 인스턴스화
	Document pdfDocument = new Document();
	// PDF 파일에 페이지 추가
	Page page = pdfDocument.Pages.Add();
	// 페이지 번호를 인수로 사용하여 RadioButtonField 객체를 인스턴스화합니다.
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// 첫 번째 라디오 버튼 옵션을 추가하고 Rectangle 객체를 사용하여 원점도 지정합니다.
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Document 객체의 양식 객체에 라디오 버튼 추가
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// PDF 문서 저장
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 그룹화된 확인란을 만드는 방법을 배웠습니다. 다음 단계를 따르면 사용자 정의 라디오 버튼 옵션을 쉽게 추가하고 Aspose.PDF를 사용하여 PDF 문서에 묶을 수 있습니다.

### FAQ

#### Q: PDF 문서의 그룹화된 확인란이란 무엇입니까?

답변: PDF 문서의 그룹화된 확인란은 함께 그룹화된 라디오 버튼 옵션 세트를 나타냅니다. 라디오 버튼을 사용하면 사용자는 상호 배타적인 선택 항목 그룹에서 하나의 옵션만 선택할 수 있습니다. 하나의 라디오 버튼을 선택하면 같은 그룹에 있는 다른 버튼은 자동으로 선택 취소됩니다. 이 그룹화 동작은 사용자에게 여러 옵션을 제공하지만 선택 항목을 하나만 선택하도록 제한하려는 경우에 유용합니다.

#### Q: .NET용 Aspose.PDF에서 그룹화된 확인란의 모양을 사용자 정의할 수 있습니까?

A: 예, .NET용 Aspose.PDF에서 그룹화된 확인란의 모양을 사용자 정의할 수 있습니다. API는 라디오 버튼 옵션의 스타일, 테두리 및 모양을 설정하는 다양한 옵션을 제공합니다. 각 옵션의 위치를 정의하고, 다양한 상자 스타일(예: 정사각형, 원, 십자형) 중에서 선택하고, 테두리 속성을 조정하여 원하는 시각적 표현을 얻을 수 있습니다.

#### Q: PDF 문서의 특정 페이지에 그룹화된 확인란을 어떻게 추가합니까?

A: PDF 문서의 특정 페이지에 그룹화된 확인란을 추가하려면`RadioButtonField` 원하는 페이지 번호를 인수로 사용하는 개체입니다. 그런 다음 생성`RadioButtonOptionField` 각 라디오 버튼 옵션을 나타내는 객체와`Rectangle` 물체. 마지막으로 다음 옵션을`RadioButtonField` 추가하기 전에 필요에 따라 모양을 맞춤설정하세요.`RadioButtonField` 문서양식으로.

#### 질문: 단일 PDF 문서에 여러 개의 확인란 그룹을 추가할 수 있습니까?

 A: 예, 단일 PDF 문서에 여러 개의 확인란 그룹을 추가할 수 있습니다. 각 그룹에는 고유한 그룹이 있어야 합니다.`RadioButtonField` 객체와`RadioButtonOptionField` 각 그룹 내의 개체는 해당 옵션에 대해 동일한 페이지와 고유한 이름을 공유해야 합니다. 이렇게 하면 각 그룹 내의 라디오 버튼이 올바르게 작동하고 선택 사항이 상호 배타적이게 됩니다.

#### Q: 모든 PDF 뷰어 및 응용 프로그램에서 그룹화된 확인란이 지원됩니까?

A: 예, 그룹화된 확인란은 모든 표준 호환 PDF 뷰어 및 응용 프로그램에서 지원됩니다. PDF 사양은 라디오 버튼과 해당 그룹화 동작을 정의하여 PDF 형식에서 보편적으로 인식되도록 합니다. 그러나 다양한 플랫폼에서 일관된 동작을 보장하려면 다양한 PDF 뷰어에서 기능을 테스트하는 것이 중요합니다.