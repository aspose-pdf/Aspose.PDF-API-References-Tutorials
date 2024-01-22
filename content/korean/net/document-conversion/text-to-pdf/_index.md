---
title: 텍스트를 PDF로
linktitle: 텍스트를 PDF로
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 텍스트 파일을 PDF로 간단하고 효율적으로 변환합니다.
type: docs
weight: 300
url: /ko/net/document-conversion/text-to-pdf/
---
이 튜토리얼은 .NET용 Aspose.PDF를 사용하여 텍스트 파일을 PDF 파일로 변환하는 단계를 안내합니다. Aspose.PDF는 텍스트 서식과 프리젠테이션을 유지하면서 일반 텍스트를 PDF로 변환하는 간단하고 효과적인 솔루션을 제공합니다. 이 변환을 수행하려면 아래 단계를 따르십시오.

## 전제조건
시작하기 전에 다음 전제 조건을 충족하는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- 시스템에 설치된 .NET용 Aspose.PDF 라이브러리.
- Visual Studio와 같은 개발 환경.

## 1단계: 텍스트 파일 읽기
 첫 번째 단계는 다음을 사용하여 텍스트 파일의 내용을 읽는 것입니다.`StreamReader` 수업. 다음 코드를 사용하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 텍스트 파일 읽기
TextReader tr = new StreamReader(dataDir + "log.txt");
```

 꼭 교체하세요`"YOUR DOCUMENTS DIRECTORY"`텍스트 파일이 있는 실제 디렉터리를 사용합니다.

## 2단계: PDF 문서 만들기
 두 번째 단계는`Document` 최종 PDF 문서를 나타내는 개체입니다. 다음 코드를 사용하세요.

```csharp
// 문서 개체 만들기
Document doc = new Document();
```

## 3단계: 문서에 텍스트 추가
세 번째 단계는 PDF 문서의 페이지에 읽은 텍스트를 추가하는 것입니다. 다음 코드를 사용하세요.

```csharp
//문서에 새 페이지 추가
Page page = doc.Pages.Add();

// TextFragment 객체를 만들고 읽은 텍스트를 인수로 전달합니다.
TextFragment text = new TextFragment(tr.ReadToEnd());

// 페이지에 텍스트 단락 추가
page.Paragraphs.Add(text);
```

## 4단계: PDF 파일 저장
마지막으로 원하는 경로와 파일 이름을 지정하여 결과 PDF 파일을 저장합니다. 다음 코드를 사용하세요.

```csharp
// 결과 PDF 파일을 저장
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

결과 PDF 파일에 대해 원하는 경로와 파일 이름을 지정하십시오.

### .NET용 Aspose.PDF를 사용하여 텍스트를 PDF로 변환하는 예제 소스 코드

```csharp
try
{
	
	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// 소스 텍스트 파일 읽기
	TextReader tr = new StreamReader(dataDir + "log.txt");

	// 빈 생성자를 호출하여 Document 객체를 인스턴스화합니다.
	Document doc = new Document();

	// Document의 Pages 컬렉션에 새 페이지 추가
	Page page = doc.Pages.Add();

	// TextFragmet의 인스턴스를 만들고 판독기 개체의 텍스트를 해당 생성자에 인수로 전달합니다.
	TextFragment text = new TextFragment(tr.ReadToEnd());
	//Text.TextState.Font = FontRepository.FindFont("Arial 유니코드 MS");

	// 단락 컬렉션에 새 텍스트 단락을 추가하고 TextFragment 개체를 전달합니다.
	page.Paragraphs.Add(text);

	// 결과 PDF 파일 저장
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 텍스트 파일을 PDF 파일로 변환하는 방법을 배웠습니다. 위에 제공된 단계를 따르면 이 변환을 쉽게 수행할 수 있습니다. 이 방법을 사용하여 텍스트 파일을 PDF로 변환하고 Aspose.PDF의 유연성과 품질을 즐기세요.

### FAQ

#### Q: .NET용 Aspose.PDF이 무엇인가요?

A: .NET용 Aspose.PDF는 개발자가 C# 애플리케이션에서 PDF 문서 작업을 할 수 있게 해주는 강력한 라이브러리입니다. 일반 텍스트를 PDF로 변환하는 등 다양한 기능을 제공합니다.

#### Q: 텍스트 파일을 PDF로 변환하려는 이유는 무엇입니까?

A: 텍스트 파일을 PDF 형식으로 변환하면 문서 관리, 공유 및 배포가 더 쉬워집니다. PDF 파일은 다양한 장치와 운영 체제에서 일관된 형식을 제공합니다.

#### Q: Aspose.PDF for .NET을 사용하여 텍스트 파일을 로드하고 PDF로 변환하려면 어떻게 해야 합니까?

A: 텍스트 파일을 로드하려면 다음을 사용할 수 있습니다.`StreamReader` 파일의 내용을 읽는 클래스입니다. 그런 다음`Document` PDF 문서를 나타내는 개체입니다. 새 페이지와`TextFragment` 텍스트 파일의 텍스트를 포함합니다. 마지막으로 다음을 사용하여 결과 PDF를 저장합니다.`Save` 의 방법`Document` 물체.

#### Q: PDF의 텍스트 모양을 사용자 정의할 수 있습니까?

A: 예, .NET용 Aspose.PDF는 글꼴 스타일, 크기, 색상, 정렬 등 결과 PDF의 텍스트 모양을 사용자 정의할 수 있는 다양한 옵션을 제공합니다.

#### Q: 결과 PDF에 텍스트 서식이 유지됩니까?

A: 예, .NET용 Aspose.PDF는 텍스트를 PDF로 변환하는 동안 텍스트 서식과 레이아웃을 유지하여 원본 콘텐츠를 정확하게 표현합니다.