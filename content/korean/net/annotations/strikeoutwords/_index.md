---
title: 단어 취소
linktitle: 단어 취소
second_title: .NET API 참조용 Aspose.PDF
description: 이 문서에서는 단계별 가이드 및 설명을 포함하여 .NET용 Aspose.PDF의 Strike Out Words 기능을 사용하는 방법에 대한 단계별 가이드를 제공합니다.
type: docs
weight: 150
url: /ko/net/annotations/strikeoutwords/
---
Aspose.PDF for .NET은 PDF 파일을 생성, 수정, 변환하는 다양한 기능을 제공하는 PDF 문서 조작 및 처리 라이브러리입니다. Aspose.PDF가 제공하는 유용한 기능 중 하나는 C# 소스 코드를 사용하여 PDF 문서에서 단어나 구문을 취소하는 기능입니다. 이 기사에서는 .NET용 Aspose.PDF를 사용하여 단어를 취소하는 방법에 대한 단계별 가이드를 제공합니다.

## 1단계: PDF 문서 로드
첫 번째 단계는 수정하려는 PDF 문서를 로드하는 것입니다. 이 튜토리얼에서는 "YOUR DOCUMENT DIRECTORY" 폴더에서 "input.pdf"라는 PDF 문서를 로드합니다. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## 2단계: 텍스트 조각 검색
PDF 문서에서 특정 단어나 문구를 취소하려면 먼저 해당 단어나 문구를 검색해야 합니다. Aspose.PDF는 PDF 문서에서 특정 텍스트 조각을 검색하는 데 사용할 수 있는 TextFragmentAbsorber 클래스를 제공합니다.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

위 코드에서는 PDF 문서에서 텍스트 조각 "Estoque"를 검색하고 있습니다. 이를 수정하여 취소하려는 다른 단어나 문구를 검색할 수 있습니다.

## 3단계: 텍스트 조각 제거
텍스트 조각을 찾은 후 다음 단계는 이를 제거하는 것입니다. Aspose.PDF는 텍스트 조각에 대한 취소선 주석을 만드는 데 사용할 수 있는 StrikeOutAnnotation 클래스를 제공합니다. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

위 코드에서는 찾은 각 텍스트 조각에 대해 취소선 주석을 생성합니다. 취소선 주석의 불투명도, 테두리 및 색상도 설정하고 있습니다.

## 4단계: 수정된 PDF 문서 저장
텍스트 조각을 제거한 후 수정된 문서를 저장합니다.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 단어 취소에 대한 예제 소스 코드


```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document document = new Document(dataDir + "input.pdf");

// 특정 텍스트 조각을 검색하려면 TextFragment Absorber 인스턴스를 생성하세요.
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// PDF 문서의 페이지를 반복합니다.
for (int i = 1; i <= document.Pages.Count; i++)
{
	// PDF 문서의 첫 페이지 가져오기
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// 흡수된 텍스트 모음 만들기
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//위 컬렉션을 반복합니다.
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// TextFragment 객체의 직사각형 크기 가져오기
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// StrikeOut Annotation 인스턴스 인스턴스화
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// 주석의 불투명도 설정
	strikeOut.Opacity = .80f;
	// 주석 인스턴스의 테두리 설정
	strikeOut.Border = new Border(strikeOut);
	// 주석 색상 설정
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// TextFragment의 주석 컬렉션에 주석 추가
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 특정 단어를 취소하는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 C# 소스 코드를 사용하면 쉽게 PDF 문서를 로드하고, 특정 텍스트 조각을 검색하고, 취소선 주석을 만들어 해당 단어를 시각적으로 표시하고 취소할 수 있습니다. .NET용 Aspose.PDF는 PDF 문서를 프로그래밍 방식으로 조작하는 간단하고 효과적인 방법을 제공하므로 .NET 응용 프로그램에서 PDF 파일을 작업하는 개발자에게 유용한 도구입니다.

### FAQ

#### Q: .NET용 Aspose.PDF이 무엇인가요?

A: .NET용 Aspose.PDF는 개발자가 .NET 애플리케이션에서 프로그래밍 방식으로 PDF 문서를 생성, 편집 및 조작할 수 있는 강력한 라이브러리입니다. 텍스트 추출, 주석 처리, 양식 채우기 등을 포함하여 PDF 파일 작업에 필요한 다양한 기능을 제공합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 특정 단어를 취소할 수 있습니까?

A: 예, Aspose.PDF for .NET은 PDF 문서에서 특정 텍스트 조각을 검색한 다음 취소선 주석을 생성하여 해당 단어를 시각적으로 표시하고 취소하는 기능을 제공합니다.

#### Q: PDF 문서에서 취소할 텍스트를 어떻게 지정합니까?

 A: 취소할 텍스트를 지정하려면`TextFragmentAbsorber` .NET용 Aspose.PDF에서 제공하는 클래스입니다. 원하는 기준에 따라 PDF 문서에서 특정 텍스트 조각을 검색할 수 있습니다.

#### Q: 취소선 주석의 모양을 사용자 정의할 수 있습니까?

A: 예, 불투명도, 테두리 스타일, 색상 등 취소선 주석의 다양한 속성을 사용자 정의할 수 있습니다. 이를 통해 취소선 주석의 모양을 특정 요구 사항에 맞게 조정할 수 있습니다.