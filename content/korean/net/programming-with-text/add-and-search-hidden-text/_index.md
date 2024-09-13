---
title: PDF 파일에 숨겨진 텍스트 추가 및 검색
linktitle: PDF 파일에 숨겨진 텍스트 추가 및 검색
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 숨겨진 텍스트를 추가하고 검색하는 단계별 가이드입니다.
type: docs
weight: 20
url: /ko/net/programming-with-text/add-and-search-hidden-text/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 숨겨진 텍스트를 추가하고 검색하는 방법을 안내해 드리겠습니다. 이 작업을 쉽게 수행하려면 다음 단계를 따르세요.

## 1. 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- Visual Studio 또는 다른 개발 환경이 설치 및 구성되어 있어야 합니다.
- C# 프로그래밍 언어에 대한 기본 지식.
- .NET용 Aspose.PDF 라이브러리가 설치되었습니다. Aspose 공식 웹사이트에서 다운로드할 수 있습니다.

## 2. 숨겨진 텍스트가 있는 PDF 문서 만들기

시작하려면 다음 코드를 사용하여 숨겨진 텍스트가 포함된 새 PDF 문서를 만드세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// 문서 만들기
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// 텍스트 속성 설정 - 보이지 않음
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

PDF 문서에 대한 원하는 경로와 파일 이름을 제공하세요.

## 3. 문서에서 텍스트 검색

다음으로, PDF 문서에서 숨겨진 텍스트를 검색합니다. 다음 코드를 사용합니다.

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
// 조각으로 무언가를 하세요
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

이렇게 하면 PDF 문서의 두 번째 페이지에 숨겨진 텍스트를 검색하여 관련 정보가 표시됩니다.

### .NET용 Aspose.PDF를 사용하여 숨겨진 텍스트 추가 및 검색을 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//숨겨진 텍스트가 있는 문서 만들기
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//텍스트 속성 설정 - 보이지 않음
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//문서에서 텍스트 검색
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//조각으로 무언가를 해보세요
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 문서에 숨겨진 텍스트를 성공적으로 추가하고 찾았습니다. 이제 이 방법을 자신의 프로젝트에 적용하여 PDF 파일에서 숨겨진 텍스트를 조작하고 검색할 수 있습니다.

### 자주 묻는 질문

#### 질문: .NET용 Aspose.PDF란 무엇인가요?

답변: .NET용 Aspose.PDF는 개발자가 .NET 애플리케이션 내에서 PDF 문서를 만들고, 조작하고, 변환할 수 있는 강력한 라이브러리입니다.

#### 질문: 숨겨진 텍스트를 워터마킹 목적으로 사용할 수 있나요?

A: 물론입니다! 숨겨진 텍스트는 PDF 문서에 워터마크를 찍는 효과적인 수단으로 사용할 수 있으며, 보안을 한층 더 강화할 수 있습니다.

#### 질문: PDF 문서에서 숨겨진 텍스트를 표시할 수 있나요?

대답: 네, PDF 문서 내에서 숨겨진 텍스트를 검색하여 찾아내는 과정은 이 튜토리얼에서 설명하는 기술을 사용하면 구현할 수 있습니다.

#### 질문: Aspose.PDF for .NET은 어떤 다른 기능을 제공하나요?

답변: Aspose.PDF for .NET은 숨겨진 텍스트 조작 외에도 PDF 생성, 변환, 암호화 등 다양한 기능을 제공합니다.