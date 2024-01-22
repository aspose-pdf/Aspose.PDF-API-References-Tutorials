---
title: 라디오 버튼 캡션 설정
linktitle: 라디오 버튼 캡션 설정
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 형식의 라디오 버튼 캡션을 설정하는 방법을 알아보세요.
type: docs
weight: 280
url: /ko/net/programming-with-forms/set-radio-button-caption/
---
이 가이드에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 형식의 라디오 버튼 캡션을 정의하는 방법을 단계별로 설명합니다. 라디오 버튼 필드에 액세스하고, 새 라디오 버튼 옵션을 만들고, 버튼 캡션을 사용자 정의하는 방법을 보여드리겠습니다.

## 1단계: 문서 디렉터리 구성

 첫 번째 단계는 작업하려는 PDF 양식이 있는 문서 디렉터리를 구성하는 것입니다. 당신은 사용할 수 있습니다`dataDir` 디렉터리 경로를 지정하는 변수입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 꼭 교체하세요`"YOUR DOCUMENTS DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하세요.

## 2단계: 소스 PDF 양식 로드

 이 단계에서는 다음을 사용하여 소스 PDF 양식을 로드합니다.`Aspose.Pdf.Facades.Form` Aspose.PDF의 클래스입니다.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

양식이 포함된 PDF 파일이 지정된 문서 디렉토리에 있는지 확인하십시오.

## 3단계: 라디오 버튼 캡션 편집하기

양식 필드 이름을 반복하여 라디오 버튼 필드를 검색하겠습니다. 일치하는 필드가 발견되면 사용자 정의 캡션이 있는 새 라디오 버튼 옵션을 만들어 기존 필드에 추가합니다.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// TextParagraph 개체 만들기
TextParagraph par = new TextParagraph();
// 단락 위치 설정
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// 줄 바꿈 모드 지정
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// 단락에 새 TextFragment를 추가합니다.
par.AppendLine(updatedFragment);
// TextBuilder를 사용하여 TextParagraph 추가
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

필요에 따라 캡션 라디오 버튼과 기타 설정을 맞춤설정하세요.

## 4단계: 결과 PDF 저장

 이제 라디오 버튼 캡션 수정이 완료되었으므로 다음을 사용하여 결과 PDF를 저장할 수 있습니다.`Save` 의 방법`Document` 수업.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

결과 PDF의 전체 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.PDF를 사용하여 라디오 버튼 캡션 설정에 대한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 소스 PDF 양식 로드
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// TextParagraph 객체 생성
		TextParagraph par = new TextParagraph();
		// 단락 위치 설정
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// 단어 줄 바꿈 모드 지정
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// 단락에 새 TextFragment 추가
		par.AppendLine(updatedFragment);
		// TextBuilder를 사용하여 TextParagraph 추가
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## 결론

이 가이드에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 형식의 라디오 버튼 캡션을 설정하는 방법을 배웠습니다. 설명된 단계에 따라 라디오 버튼 옵션을 사용자 정의하고 필요에 따라 캡션을 변경할 수 있습니다. PDF 파일 조작 가능성을 확장하려면 .NET용 Aspose.PDF의 기능을 더 자세히 살펴보세요.

### FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 형식의 라디오 버튼 캡션을 설정할 수 있습니까?

A: 예, .NET용 Aspose.PDF를 사용하여 PDF 형식의 라디오 버튼 캡션을 설정할 수 있습니다. 제공된 샘플 소스 코드는 라디오 버튼 필드에 액세스하고, 사용자 정의 캡션이 있는 새 라디오 버튼 옵션을 만들고, 기존 필드를 업데이트하는 방법을 보여줍니다.

#### Q: 글꼴 크기, 색상 등 라디오 버튼 캡션의 모양을 어떻게 사용자 정의할 수 있나요?

 A: 라디오 버튼 캡션의 속성을 조정하여 라디오 버튼 캡션의 모양을 사용자 정의할 수 있습니다.`TextFragment` 캡션에 사용됩니다. 예를 들어 글꼴, 글꼴 크기, 색상, 줄 간격 및 기타 텍스트 서식 옵션을 설정할 수 있습니다.

#### Q: 단일 라디오 버튼 그룹에 캡션이 다른 여러 라디오 버튼 옵션을 추가할 수 있습니까?

A: 예, 단일 라디오 버튼 그룹에 캡션이 다른 여러 라디오 버튼 옵션을 추가할 수 있습니다. 각 옵션은 서로 다른 선택 사항을 나타내며 사용자는 그룹에서 하나의 옵션만 선택할 수 있습니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서의 다른 양식 필드를 수정할 수 있습니까?

A: 예, .NET용 Aspose.PDF는 텍스트 필드, 확인란, 드롭다운 목록 등과 같은 PDF 문서의 다양한 양식 필드를 조작할 수 있는 포괄적인 기능 세트를 제공합니다. 라이브러리를 사용하여 값을 설정하고, 모양을 수정하고, 양식 필드에 대화형 기능을 추가할 수 있습니다.

#### Q: .NET용 Aspose.PDF는 스캔한 문서 등 다른 소스에서 생성된 PDF 작업을 지원합니까?

A: 예, .NET용 Aspose.PDF는 스캔한 문서를 포함하여 다양한 소스에서 생성된 PDF 작업을 지원합니다. 라이브러리는 스캔한 PDF에서 텍스트를 추출하고 프로그래밍 방식으로 콘텐츠를 조작할 수 있는 OCR(광학 문자 인식) 기능을 제공합니다.