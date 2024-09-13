---
title: PDF 파일에서 문단 추출
linktitle: PDF 파일에서 문단 추출
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에서 문단을 추출하는 방법을 알아보세요.
type: docs
weight: 160
url: /ko/net/programming-with-text/extract-paragraphs/
---
이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 파일에서 문단을 추출하는 과정을 안내합니다. 제공된 C# 소스 코드는 필요한 단계를 보여줍니다.

## 요구 사항
시작하기 전에 다음 사항이 있는지 확인하세요.

- 컴퓨터에 Visual Studio나 다른 C# 컴파일러가 설치되어 있어야 합니다.
- .NET 라이브러리용 Aspose.PDF. 공식 Aspose 웹사이트에서 다운로드하거나 NuGet과 같은 패키지 관리자를 사용하여 설치할 수 있습니다.

## 1단계: 프로젝트 설정
1. 원하는 개발 환경에서 새로운 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필요한 네임스페이스 가져오기
문단을 추출하려는 코드 파일에서 파일 맨 위에 다음 using 지침을 추가합니다.

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## 3단계: 문서 디렉토리 설정
 코드에서 다음 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 그리고 교체하다`"YOUR DOCUMENT DIRECTORY"` 문서가 저장된 디렉토리 경로를 포함합니다.

## 4단계: PDF 문서 열기
 기존 PDF 문서를 열려면 다음을 사용하세요.`Document`생성자를 사용하고 입력 PDF 파일의 경로를 전달합니다.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 5단계: 문단 추출
 인스턴스화`ParagraphAbsorber` 클래스를 사용하고 사용합니다`Visit` 문서에서 문단을 추출하는 방법.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## 6단계: 문단 반복
추출된 문단을 반복하여 텍스트 내용에 접근합니다. 중첩된 루프를 사용하여 각 문단 내의 섹션과 줄을 탐색합니다.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### .NET용 Aspose.PDF를 사용하여 문단 추출을 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 기존 PDF 파일 열기
Document doc = new Document(dataDir + "input.pdf");
// ParagraphAbsorber 인스턴스화
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## 결론
Aspose.PDF for .NET을 사용하여 PDF 문서에서 문단을 성공적으로 추출했습니다. 추출된 문단이 콘솔 창에 표시되었습니다.

### 자주 묻는 질문

#### 질문: 이 튜토리얼의 목적은 무엇인가요?

A: 이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 파일에서 문단을 추출하는 과정을 안내합니다. 첨부된 C# 소스 코드는 이 작업을 달성하기 위한 실용적인 단계를 제공합니다.

#### 질문: 어떤 네임스페이스를 가져와야 합니까?

A: 문단을 추출하려는 코드 파일에서 파일 시작 부분에 다음 using 지침을 포함합니다.

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### 질문: 문서 디렉토리를 어떻게 지정하나요?

 A: 라인을 찾으세요`string dataDir = "YOUR DOCUMENT DIRECTORY";` 코드에서 교체`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 포함합니다.

#### 질문: 기존 PDF 문서를 어떻게 열 수 있나요?

 A: 4단계에서는 다음을 사용하여 기존 PDF 문서를 엽니다.`Document` 생성자를 사용하고 입력 PDF 파일에 대한 경로를 제공합니다.

#### 질문: 문서에서 문단을 추출하려면 어떻게 해야 하나요?

 A: 5단계에는 인스턴스를 만드는 것이 포함됩니다.`ParagraphAbsorber` 클래스와 그것을 사용하는`Visit` PDF 문서에서 문단을 추출하는 방법.

#### 질문: 추출된 문단을 반복하려면 어떻게 해야 하나요?

A: 6단계에서는 추출된 문단을 반복하는 방법을 안내합니다. 중첩된 루프는 각 문단 내의 섹션과 줄을 순회하는 데 사용되며, 궁극적으로 텍스트 콘텐츠에 액세스하여 표시합니다.

#### 질문: 이 튜토리얼의 주요 내용은 무엇인가요?

A: 이 튜토리얼을 따라하면 Aspose.PDF for .NET을 사용하여 PDF 문서에서 문단을 추출하는 방법을 배웠습니다. 추출된 문단은 콘솔 창에 표시되어 문서의 콘텐츠 구조에 대한 귀중한 통찰력을 제공합니다.