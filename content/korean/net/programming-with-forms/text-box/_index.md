---
title: 텍스트 상자
linktitle: 텍스트 상자
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 텍스트 필드를 만드는 방법을 알아보세요.
type: docs
weight: 290
url: /ko/net/programming-with-forms/text-box/
---
이 가이드에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에 텍스트 필드를 만드는 방법을 단계별로 설명합니다. 문서를 열고, 텍스트 필드를 만들고, 해당 속성을 사용자 정의하고, 편집된 PDF를 저장하는 방법을 보여 드리겠습니다.

## 1단계: 문서 디렉터리 구성

 첫 번째 단계는 작업하려는 PDF 파일이 있는 문서 디렉터리를 구성하는 것입니다. 당신은 사용할 수 있습니다`dataDir` 디렉터리 경로를 지정하는 변수입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 꼭 교체하세요`"YOUR DOCUMENTS DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하세요.

## 2단계: PDF 문서 열기

이 단계에서는 다음을 사용하여 PDF 문서를 엽니다.`Document` Aspose.PDF의 클래스입니다.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

PDF 파일이 지정된 문서 디렉토리에 있는지 확인하십시오.

## 3단계: 텍스트 필드 만들기

 다음을 사용하여 텍스트 필드를 만듭니다.`TextBoxField` 수업. 다음을 사용하여 위치 좌표와 필드 크기를 지정할 수 있습니다.`Rectangle` 수업.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

필요에 따라 좌표, 크기, 부분 이름 및 텍스트 필드 값을 사용자 정의합니다.

## 4단계: 텍스트 필드 속성 사용자 정의

이 단계에서는 테두리, 색상 등과 같은 텍스트 필드 속성을 사용자 정의합니다.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

원하는 대로 텍스트 필드 속성을 사용자 정의합니다.

## 5단계: 문서에 필드 추가

이제 텍스트 필드를 만들고 구성했으므로 PDF 문서에 추가할 수 있습니다.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## 6단계: 수정된 PDF 저장

 마지막으로 다음을 사용하여 수정된 PDF를 저장할 수 있습니다.`Save` 의 방법`Document` 수업.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

편집된 PDF의 전체 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.PDF를 사용하는 텍스트 상자의 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// 필드 만들기
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
//TextBoxField.Border = 새 테두리(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// 문서에 필드 추가
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// 수정된 PDF 저장
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## 결론

이 가이드에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에 텍스트 필드를 만드는 방법을 배웠습니다. 설명된 단계에 따라 텍스트 필드의 속성을 사용자 정의하고 필요에 따라 문서에 추가할 수 있습니다. PDF 파일 조작 가능성을 확장하려면 .NET용 Aspose.PDF의 기능을 더 자세히 살펴보세요.

### FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 단일 PDF 문서에 여러 텍스트 필드를 만들 수 있습니까?

A: 예, .NET용 Aspose.PDF를 사용하여 단일 PDF 문서에 여러 텍스트 필드를 만들 수 있습니다. 문서에서 원하는 각 위치에 대해 텍스트 필드를 만들고 사용자 정의하는 과정을 반복하기만 하면 됩니다.

#### Q: 글꼴 크기, 색상 등 텍스트 필드의 모양을 어떻게 사용자 정의할 수 있나요?

답변: 글꼴 크기, 글꼴 스타일, 색상, 테두리 스타일, 배경색 등과 같은 속성을 조정하여 텍스트 필드의 모양을 사용자 정의할 수 있습니다. 제공된 샘플 소스 코드에서는 테두리 너비, 테두리 대시 패턴 및 텍스트 색상이 사용자 정의됩니다.

#### Q: 생성된 텍스트 필드에서 사용자가 입력한 텍스트를 추출할 수 있나요?

A: 예, 생성된 텍스트 필드에서 사용자가 입력한 텍스트를 추출할 수 있습니다. 사용자가 PDF 문서의 텍스트 필드를 채운 후 .NET용 Aspose.PDF를 사용하여 프로그래밍 방식으로 필드 값을 검색할 수 있습니다.

#### 질문: 새 문서를 만들지 않고도 기존 PDF 문서에 텍스트 필드를 추가할 수 있습니까?

A: 예, 새 PDF 문서를 만들지 않고도 기존 PDF 문서에 텍스트 필드를 추가할 수 있습니다. .NET용 Aspose.PDF는 텍스트 필드, 확인란 및 기타 양식 요소 추가를 포함하여 기존 PDF 문서를 수정하는 기능을 제공합니다.

#### Q: .NET용 Aspose.PDF는 확인란 및 라디오 버튼과 같은 다른 유형의 양식 필드를 지원합니까?

A: 예, .NET용 Aspose.PDF는 체크박스, 라디오 버튼, 드롭다운 목록 등을 포함한 다양한 유형의 양식 필드를 지원합니다. 라이브러리를 사용하여 PDF 문서의 다양한 유형의 양식 요소로 작업할 수 있습니다.