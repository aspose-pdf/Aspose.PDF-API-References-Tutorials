---
title: PDF 파일의 텍스트에 도구 설명 추가
linktitle: PDF 파일의 텍스트에 도구 설명 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 텍스트에 도구 설명을 추가하는 방법을 알아보세요.
type: docs
weight: 90
url: /ko/net/programming-with-text/add-tooltip-to-text/
---
이 튜토리얼은 .NET용 Aspose.PDF를 사용하여 PDF 파일의 텍스트에 도구 설명을 추가하는 과정을 안내합니다. 제공된 C# 소스 코드는 필요한 단계를 보여줍니다.

## 요구사항
시작하기 전에 다음 사항이 있는지 확인하세요.

- 컴퓨터에 Visual Studio 또는 기타 C# 컴파일러가 설치되어 있습니다.
- .NET 라이브러리용 Aspose.PDF. 공식 Aspose 웹사이트에서 다운로드하거나 NuGet과 같은 패키지 관리자를 사용하여 설치할 수 있습니다.

## 1단계: 프로젝트 설정
1. 원하는 개발 환경에서 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필수 네임스페이스 가져오기
텍스트에 도구 설명을 추가하려는 코드 파일에서 파일 상단에 다음 using 지시문을 추가합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## 3단계: 문서 디렉터리 설정
 코드에서 다음과 같은 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 교체하고`"YOUR DOCUMENT DIRECTORY"` 문서가 저장된 디렉토리의 경로를 사용하세요.

## 4단계: 텍스트가 포함된 샘플 문서 만들기
 새로 만들기`Document` 개체를 선택하고 텍스트 조각이 포함된 페이지를 추가합니다. 제공된 코드에서는 두 개의 텍스트 조각이 해당 도구 설명 텍스트와 함께 문서에 추가됩니다.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## 5단계: 문서를 열고 텍스트 조각 찾기
 생성된 문서를 로드합니다.`Document` 생성자를 사용하여 툴팁이 필요한 텍스트 조각을 찾습니다.`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## 6단계: 텍스트 조각에 도구 설명 추가
 추출된 텍스트 조각을 반복하고 해당 위치에 보이지 않는 버튼을 만듭니다. 원하는 도구 설명 텍스트를`AlternateName` 의 재산`ButtonField`. 문서 양식에 버튼 필드를 추가합니다.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## 7단계: 긴 도구 설명이 포함된 추가 텍스트 조각에 대해 반복합니다.
긴 도구 설명이 있는 텍스트 조각에 대해 5단계와 6단계를 반복합니다. 그에 따라 검색 기준과 도구 설명 텍스트를 수정합니다.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## 8단계: 수정된 문서 저장
 다음을 사용하여 수정된 PDF 문서를 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
document. Save(outputFile);
```

### .NET용 Aspose.PDF를 사용하여 텍스트에 도구 설명 추가에 대한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// 텍스트가 포함된 샘플 문서 만들기
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// 텍스트가 포함된 문서 열기
Document document = new Document(outputFile);
// 정규식과 일치하는 모든 구문을 찾기 위해 TextAbsorber 개체를 만듭니다.
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// 문서 페이지의 흡수체를 수락합니다.
document.Pages.Accept(absorber);
// 추출된 텍스트 조각 가져오기
TextFragmentCollection textFragments = absorber.TextFragments;
// 조각을 통해 반복
foreach (TextFragment fragment in textFragments)
{
	// 텍스트 조각 위치에 보이지 않는 버튼 만들기
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// AlternateName 값은 뷰어 응용 프로그램에 의해 도구 설명으로 표시됩니다.
	field.AlternateName = "Tooltip for text.";
	// 문서에 버튼 필드 추가
	document.Form.Add(field);
}
// 다음은 매우 긴 툴팁의 샘플입니다.
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// 매우 긴 텍스트 설정
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// 문서 저장
document.Save(outputFile);
```

## 결론
.NET용 Aspose.PDF를 사용하여 PDF 문서의 텍스트에 도구 설명을 성공적으로 추가했습니다. 이제 결과 PDF 파일을 지정된 출력 파일 경로에서 찾을 수 있습니다.

## 자주 묻는 질문

#### Q: 이 튜토리얼의 초점은 무엇입니까?

A: 이 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일 내의 텍스트에 도구 설명을 추가하는 데 중점을 둡니다. 제공된 C# 소스 코드는 이를 달성하는 데 필요한 단계를 보여줍니다.

#### Q: 이 튜토리얼에서는 어떤 네임스페이스를 가져와야 합니까?

A: 텍스트에 도구 설명을 추가하려는 코드 파일에서 파일 시작 부분에 다음 네임스페이스를 가져옵니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### Q: 문서 디렉터리를 어떻게 지정합니까?

 A: 코드에서 다음 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 교체하고`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

#### Q: 텍스트가 포함된 샘플 문서를 만들려면 어떻게 해야 합니까?

 A: 4단계에서는 새`Document` 개체를 선택하고 텍스트 조각이 포함된 페이지를 추가합니다. 제공된 코드는 각각의 도구 설명 텍스트가 포함된 두 개의 텍스트 조각을 추가합니다.

#### Q: 문서를 열고 텍스트 조각을 찾으려면 어떻게 해야 합니까?

 A: 5단계에서는 생성된 문서를 로드합니다.`Document` 생성자를 사용하여 툴팁이 필요한 텍스트 조각을 찾습니다.`TextFragmentAbsorber`.

#### Q: 텍스트 조각에 도구 설명을 어떻게 추가합니까?

 A: 6단계에서는 추출된 텍스트 조각을 반복하여 해당 위치에 보이지 않는 버튼을 만듭니다. 도구 설명 텍스트가`AlternateName` 의 재산`ButtonField`문서 양식에 추가됩니다.

#### Q: 긴 도구 설명이 포함된 추가 텍스트 조각에 대한 프로세스를 어떻게 반복합니까?

A: 긴 도구 설명이 포함된 텍스트 조각의 경우 5단계와 6단계를 반복하십시오. 이에 따라 검색 기준과 도구 설명 텍스트를 수정하십시오.

#### Q: 수정된 문서를 어떻게 저장하나요?

 A: 8단계에서는 다음을 사용하여 수정된 PDF 문서를 저장합니다.`Save` 의 방법`Document` 물체.

#### Q: 이 튜토리얼의 주요 내용은 무엇입니까?

A: 이 튜토리얼을 따라 .NET용 Aspose.PDF를 사용하여 텍스트에 도구 설명을 추가하여 PDF 문서를 향상시키는 방법을 배웠습니다. 이는 독자가 PDF 콘텐츠와 상호 작용할 때 귀중한 추가 정보를 제공할 수 있습니다.