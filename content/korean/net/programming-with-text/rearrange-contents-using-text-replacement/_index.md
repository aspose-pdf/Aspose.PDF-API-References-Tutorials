---
title: 텍스트 교체를 사용하여 콘텐츠 재정렬
linktitle: 텍스트 교체를 사용하여 콘텐츠 재정렬
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 텍스트 교체를 사용하여 PDF 문서의 내용을 재정렬하는 방법을 알아보세요.
type: docs
weight: 270
url: /ko/net/programming-with-text/rearrange-contents-using-text-replacement/
---
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 텍스트 대체를 사용하여 PDF 문서의 내용을 재정렬하는 방법을 설명합니다. PDF를 로드하고, 특정 텍스트 조각을 검색하고, 텍스트를 대체하고, 제공된 C# 소스 코드를 사용하여 수정된 PDF를 저장하는 단계별 프로세스를 살펴보겠습니다.

## 요구 사항

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 라이브러리용 Aspose.PDF가 설치되었습니다.
- C# 프로그래밍에 대한 기본적인 이해.

## 1단계: 문서 디렉토리 설정

 먼저 PDF 파일이 있는 디렉토리 경로를 설정해야 합니다. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` PDF 파일 경로가 있는 변수입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 소스 PDF 로드

 다음으로, 다음을 사용하여 소스 PDF 문서를 로드합니다.`Document` Aspose.PDF 라이브러리의 클래스입니다.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## 3단계: 텍스트 조각 검색 및 바꾸기

 우리는 만듭니다`TextFragmentAbsorber` 정규 표현식을 사용하여 특정 텍스트 조각을 검색하는 객체입니다. 그런 다음 텍스트 조각을 반복하고 글꼴, 크기, 색상을 사용자 지정하고 텍스트를 바꿉니다.

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

### .NET용 Aspose.PDF를 사용하여 텍스트 교체를 사용하여 콘텐츠 재정렬하기 위한 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉토리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// 소스 PDF 파일 로드
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	// 정규 표현식을 사용하여 TextFragment Absorber 객체를 만듭니다.
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// 각 TextFragment를 교체하세요
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// 교체되는 텍스트 조각의 글꼴 설정
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// 글꼴 크기 설정
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// 플레이스홀더보다 큰 문자열로 텍스트를 바꾸세요
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

이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 텍스트 대체를 사용하여 PDF 문서의 내용을 재정렬하는 방법을 알아보았습니다. 단계별 가이드를 따르고 제공된 C# 코드를 실행하면 특정 텍스트 조각을 검색하고 모양을 사용자 지정하고 PDF 문서의 텍스트를 대체할 수 있습니다.

### 자주 묻는 질문

#### 질문: "텍스트 교체를 사용하여 내용 재정렬" 튜토리얼의 목적은 무엇입니까?

A: "텍스트 대체를 사용하여 내용 재정렬" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 텍스트 대체를 수행하여 PDF 문서의 내용을 재정렬하는 방법을 보여줍니다. 이 튜토리얼은 PDF를 로드하고, 특정 텍스트 조각을 검색하고, 텍스트를 대체하고, 수정된 PDF를 저장하는 데 도움이 되는 단계별 가이드와 C# 소스 코드를 제공합니다.

#### 질문: PDF 문서의 내용을 재정렬하고 싶은 이유는 무엇인가요?

A: PDF 문서의 내용을 재정렬하는 것은 텍스트 업데이트, 레이아웃 재포맷 또는 수정과 같은 다양한 목적에 유용할 수 있습니다. 이 기술을 사용하면 구조와 모양을 유지하면서 PDF의 내용을 동적으로 수정할 수 있습니다.

#### 질문: 문서 디렉토리를 어떻게 설정하나요?

A: 문서 디렉토리를 설정하려면:

1.  바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` PDF 파일이 있는 디렉토리 경로를 포함하는 변수입니다.

#### 질문: PDF 문서에서 텍스트를 바꾸려면 어떻게 해야 하나요?

 A: 이 튜토리얼은 PDF에서 특정 텍스트 조각을 검색하는 과정을 안내합니다.`TextFragmentAbsorber`클래스. 텍스트 조각의 모양을 사용자 지정하고 해당 내용을 대체하는 방법을 보여줍니다.

#### 질문: 바뀐 텍스트의 글꼴, 크기, 색상을 사용자 지정할 수 있나요?

 A: 예, 교체된 텍스트의 글꼴, 크기 및 색상을 수정하여 사용자 정의할 수 있습니다.`TextState` 의 속성`TextFragment` 객체. 이 튜토리얼은 텍스트의 글꼴, 글꼴 크기 및 전경색을 설정하는 방법의 예를 제공합니다.

#### 질문: 수정된 PDF 문서를 어떻게 저장하나요?

 A: 텍스트 교체를 수행하고 텍스트 조각을 사용자 지정한 후 수정된 PDF 문서를 다음을 사용하여 저장할 수 있습니다.`Save` 의 방법`Document` 클래스. 원하는 출력 파일 경로를 인수로 제공합니다.`Save` 방법.

#### 질문: 이 튜토리얼을 통해 기대되는 결과는 무엇인가요?

답변: 튜토리얼을 따라 제공된 C# 코드를 실행하면 특정 텍스트 조각이 대체되고 귀하의 사양에 맞게 사용자 정의된 수정된 PDF 문서가 생성됩니다.

#### 질문: 텍스트 검색에 다른 정규 표현식을 사용할 수 있나요?

 A: 네, PDF 문서에서 특정 텍스트 조각을 검색하기 위해 다양한 정규 표현식을 사용할 수 있습니다. 튜토리얼에서 제공하는 예는 다음을 만드는 방법을 보여줍니다.`TextFragmentAbsorber`텍스트를 검색하고 바꾸기 위한 특정 정규 표현식을 가진 객체입니다.

#### 질문: 이 튜토리얼을 사용하려면 유효한 Aspose 라이선스가 필요합니까?

A: 네, 이 튜토리얼이 제대로 작동하려면 유효한 Aspose 라이선스가 필요합니다. Aspose 웹사이트에서 전체 라이선스를 구매하거나 30일 임시 라이선스를 얻을 수 있습니다.