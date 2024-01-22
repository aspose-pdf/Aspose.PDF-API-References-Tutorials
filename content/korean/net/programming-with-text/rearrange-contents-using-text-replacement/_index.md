---
title: 텍스트 교체를 사용하여 내용 재정렬
linktitle: 텍스트 교체를 사용하여 내용 재정렬
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF로 텍스트 교체를 사용하여 PDF 문서의 내용을 재정렬하는 방법을 알아보세요.
type: docs
weight: 270
url: /ko/net/programming-with-text/rearrange-contents-using-text-replacement/
---
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 텍스트 교체를 사용하여 PDF 문서의 내용을 재정렬하는 방법을 설명합니다. 제공된 C# 소스 코드를 사용하여 PDF를 로드하고, 특정 텍스트 조각을 검색하고, 텍스트를 바꾸고, 수정된 PDF를 저장하는 과정을 단계별로 살펴보겠습니다.

## 요구사항

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 라이브러리용 Aspose.PDF가 설치되었습니다.
- C# 프로그래밍에 대한 기본적인 이해.

## 1단계: 문서 디렉터리 설정

 먼저, PDF 파일이 있는 디렉터리의 경로를 설정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 변수를 PDF 파일 경로로 바꿉니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 소스 PDF 로드

 다음으로, 다음을 사용하여 소스 PDF 문서를 로드합니다.`Document` Aspose.PDF 라이브러리의 클래스입니다.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## 3단계: 텍스트 조각 검색 및 바꾸기

 우리는`TextFragmentAbsorber` 특정 텍스트 조각을 검색하려면 정규식을 사용하여 개체를 사용하세요. 그런 다음 텍스트 조각을 반복하고 글꼴, 크기, 색상을 사용자 정의하고 텍스트를 바꿉니다.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
doc.Pages.Accept(textFragmentAbsorber);

foreach(TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial");
     textFragment.TextState.FontSize = 12;
     textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
     textFragment.Text = "This is a Larger String for the Testing of this issue";
}
```

## 4단계: 수정된 PDF 저장

마지막으로 수정된 PDF 문서를 지정된 출력 파일에 저장합니다.

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### .NET용 Aspose.PDF를 사용하여 텍스트 교체를 사용하여 콘텐츠를 재정렬하기 위한 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// 소스 PDF 파일 로드
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	// 정규식을 사용하여 TextFragment Absorber 개체 만들기
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// 각 TextFragment 바꾸기
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// 대체되는 텍스트 조각의 글꼴 설정
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// 글꼴 크기 설정
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// 텍스트를 자리 표시자보다 큰 문자열로 바꿉니다.
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// 결과 PDF 저장
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리의 텍스트 대체를 사용하여 PDF 문서의 내용을 재정렬하는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 C# 코드를 실행하면 특정 텍스트 조각을 검색하고 모양을 사용자 정의하며 PDF 문서의 텍스트를 바꿀 수 있습니다.

### FAQ

#### Q: "텍스트 교체를 사용하여 내용 재정렬" 튜토리얼의 목적은 무엇입니까?

A: "텍스트 교체를 사용하여 내용 재정렬" 자습서에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 텍스트 교체를 수행하여 PDF 문서의 내용을 재정렬하는 방법을 보여줍니다. 이 자습서에서는 PDF 로드, 특정 텍스트 조각 검색, 텍스트 교체 및 수정된 PDF 저장에 도움이 되는 단계별 가이드와 C# 소스 코드를 제공합니다.

#### Q: PDF 문서의 내용을 재정렬하려는 이유는 무엇입니까?

답변: PDF 문서의 내용을 재정렬하는 것은 텍스트 업데이트, 레이아웃 재지정, 수정 등 다양한 목적에 유용할 수 있습니다. 이 기술을 사용하면 PDF의 구조와 모양을 유지하면서 PDF 내용을 동적으로 수정할 수 있습니다.

#### Q: 문서 디렉터리를 어떻게 설정합니까?

A: 문서 디렉토리를 설정하려면:

1.  바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 변수를 PDF 파일이 있는 디렉터리의 경로로 바꿉니다.

#### Q: PDF 문서에서 텍스트 교체를 어떻게 수행합니까?

 답변: 튜토리얼에서는 다음을 사용하여 PDF에서 특정 텍스트 조각을 검색하는 과정을 안내합니다.`TextFragmentAbsorber`수업. 텍스트 조각의 모양을 사용자 정의하고 해당 내용을 바꾸는 방법을 보여줍니다.

#### Q: 대체된 텍스트의 글꼴, 크기, 색상을 사용자 정의할 수 있나요?

 A: 예.`TextState` 의 속성`TextFragment` 물체. 이 튜토리얼에서는 텍스트의 글꼴, 글꼴 크기 및 전경색을 설정하는 방법에 대한 예를 제공합니다.

#### Q: 수정된 PDF 문서를 어떻게 저장합니까?

 A: 텍스트 교체를 수행하고 텍스트 조각을 사용자 정의한 후 다음을 사용하여 수정된 PDF 문서를 저장할 수 있습니다.`Save` 의 방법`Document` 수업. 원하는 출력 파일 경로를 인수로 제공하십시오.`Save` 방법.

#### Q: 이 튜토리얼에서 예상되는 결과는 무엇입니까?

A: 튜토리얼을 따르고 제공된 C# 코드를 실행하면 특정 텍스트 조각이 사양에 따라 바뀌고 사용자 정의된 수정된 PDF 문서가 생성됩니다.

#### Q: 텍스트 검색에 다른 정규식을 사용할 수 있습니까?

 A: 예, 다양한 정규식을 사용하여 PDF 문서에서 특정 텍스트 조각을 검색할 수 있습니다. 튜토리얼에 제공된 예는`TextFragmentAbsorber`특정 정규식을 사용하여 텍스트를 검색하고 바꾸는 개체입니다.

#### Q: 이 튜토리얼에는 유효한 Aspose 라이선스가 필요합니까?

A: 예, 이 튜토리얼이 올바르게 작동하려면 유효한 Aspose 라이선스가 필요합니다. Aspose 웹사이트에서 정식 라이선스를 구매하거나 30일 임시 라이선스를 얻을 수 있습니다.