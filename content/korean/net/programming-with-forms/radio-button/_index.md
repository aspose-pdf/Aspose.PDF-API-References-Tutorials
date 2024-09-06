---
title: 라디오 버튼
linktitle: 라디오 버튼
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하면 PDF 문서에 라디오 버튼을 쉽게 추가할 수 있습니다.
type: docs
weight: 220
url: /ko/net/programming-with-forms/radio-button/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에 라디오 버튼을 추가하는 방법을 보여드리겠습니다. 이 과정을 안내하기 위해 C# 소스 코드를 단계별로 설명하겠습니다.

## 1단계: 준비

필요한 라이브러리를 가져왔는지 확인하고 문서 디렉토리 경로를 설정하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 개체 인스턴스화

새 PDF 문서를 만들려면 Document 객체를 인스턴스화하세요.

```csharp
Document pdfDocument = new Document();
```

## 3단계: 페이지 추가

PDF 문서에 페이지 추가:

```csharp
pdfDocument.Pages.Add();
```

## 4단계: RadioButtonField 객체 인스턴스화

페이지 번호를 인수로 지정하여 RadioButtonField 객체를 인스턴스화합니다.

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## 5단계: 라디오 버튼 옵션 추가

Rectangle 객체로 각 옵션의 좌표를 지정하여 RadioButtonField 객체에 라디오 버튼 옵션을 추가합니다.

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## 6단계: 양식에 라디오 버튼 추가

문서의 Form 개체에 라디오 버튼을 추가합니다.

```csharp
pdfDocument.Form.Add(radio);
```

## 7단계: PDF 문서 저장

생성된 PDF 문서를 저장합니다.

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용한 라디오 버튼의 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉토리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Document 객체 인스턴스화
	Document pdfDocument = new Document();
	// PDF 파일에 페이지 추가
	pdfDocument.Pages.Add();
	// 페이지 번호를 인수로 사용하여 RadioButtonField 객체를 인스턴스화합니다.
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// 첫 번째 라디오 버튼 옵션을 추가하고 Rectangle 객체를 사용하여 원점을 지정합니다.
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// 두 번째 라디오 버튼 옵션 추가
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Document 객체의 폼 객체에 라디오 버튼 추가
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// PDF 파일을 저장하세요
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에 라디오 버튼을 추가하는 방법을 알아보았습니다. 이러한 단계를 따르면 라디오 버튼을 쉽게 만들어 PDF 문서의 특정 페이지에 배치할 수 있습니다.


### 자주 묻는 질문

#### 질문: 라디오 버튼의 크기, 색상 등 모양을 사용자 지정할 수 있나요?

 A: 예, 라디오 버튼의 모양을 사용자 정의할 수 있습니다.`Rectangle` 객체의 좌표를 사용하여 크기와 위치를 정의합니다. Aspose.PDF for .NET을 사용하면 라디오 버튼의 모양을 필요에 맞게 조정할 수 있습니다.

#### 질문: 같은 페이지에 다양한 그룹의 라디오 버튼을 여러 개 추가할 수 있나요?

A: 네, 같은 페이지에 여러 개의 라디오 버튼을 다른 그룹으로 추가할 수 있습니다. 라디오 버튼 그룹은 각각 고유한 이름을 가질 수 있으며, 각 그룹 내에서 한 번에 하나의 옵션만 선택할 수 있습니다.

#### 질문: 라디오 버튼 옵션에 라벨이나 텍스트 설명을 추가하려면 어떻게 해야 하나요?

 A: 라디오 버튼 옵션에 레이블이나 텍스트 설명을 추가하려면 다음을 사용할 수 있습니다.`TextStamp`.NET용 Aspose.PDF 클래스를 사용하면 특정 좌표에 PDF 문서의 텍스트를 오버레이할 수 있습니다.

#### 질문: Aspose.PDF for .NET은 모든 버전의 .NET Framework와 호환됩니까?

답변: 네, Aspose.PDF for .NET은 .NET Core 및 .NET Standard를 포함한 모든 버전의 .NET Framework와 호환됩니다.

#### 질문: PDF 문서에서 라디오 버튼 옵션의 선택을 프로그래밍 방식으로 제어할 수 있나요?

 A: 예, 다음을 사용하여 라디오 버튼 옵션 선택을 프로그래밍 방식으로 제어할 수 있습니다.`IsSelected` 의 속성`RadioButtonOption` 클래스. 이 속성을 사용하면 특정 옵션을 선택된 것으로 설정할 수 있습니다.