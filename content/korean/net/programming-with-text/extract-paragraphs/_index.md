---
title: PDF 파일에서 단락 추출
linktitle: PDF 파일에서 단락 추출
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에서 단락을 추출하는 방법을 알아보세요.
type: docs
weight: 160
url: /ko/net/programming-with-text/extract-paragraphs/
---
이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 파일에서 단락을 추출하는 과정을 안내합니다. 제공된 C# 소스 코드는 필요한 단계를 보여줍니다.

## 요구사항
시작하기 전에 다음 사항이 있는지 확인하세요.

- 컴퓨터에 Visual Studio 또는 기타 C# 컴파일러가 설치되어 있습니다.
- .NET 라이브러리용 Aspose.PDF. 공식 Aspose 웹사이트에서 다운로드하거나 NuGet과 같은 패키지 관리자를 사용하여 설치할 수 있습니다.

## 1단계: 프로젝트 설정
1. 원하는 개발 환경에서 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필수 네임스페이스 가져오기
단락을 추출하려는 코드 파일에서 파일 상단에 다음 using 지시문을 추가합니다.

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## 3단계: 문서 디렉터리 설정
 코드에서 다음과 같은 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 교체하고`"YOUR DOCUMENT DIRECTORY"` 문서가 저장된 디렉토리의 경로를 사용하세요.

## 4단계: PDF 문서 열기
 다음을 사용하여 기존 PDF 문서를 엽니다.`Document`생성자를 생성하고 입력 PDF 파일에 대한 경로를 전달합니다.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 5단계: 단락 추출
 인스턴스화`ParagraphAbsorber` 수업을 듣고 그것을 사용`Visit` 문서에서 단락을 추출하는 방법.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## 6단계: 단락 반복
추출된 단락을 반복하여 텍스트 내용에 액세스합니다. 중첩된 루프를 사용하여 각 단락 내의 섹션과 줄을 탐색합니다.

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

### .NET용 Aspose.PDF를 사용하여 단락 추출을 위한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//기존 PDF 파일 열기
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
.NET용 Aspose.PDF를 사용하여 PDF 문서에서 단락을 성공적으로 추출했습니다. 추출된 단락이 콘솔 창에 표시되었습니다.

### FAQ

#### Q: 이 튜토리얼의 목적은 무엇입니까?

A: 이 튜토리얼의 목적은 .NET용 Aspose.PDF를 사용하여 PDF 파일에서 단락을 추출하는 과정을 안내하는 것입니다. 함께 제공되는 C# 소스 코드는 이 작업을 달성하기 위한 실제 단계를 제공합니다.

#### Q: 어떤 네임스페이스를 가져와야 합니까?

A: 단락을 추출하려는 코드 파일에서 파일 시작 부분에 다음 using 지시문을 포함합니다.

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### Q: 문서 디렉터리를 어떻게 지정합니까?

 A: 줄을 찾아보세요`string dataDir = "YOUR DOCUMENT DIRECTORY";` 코드에서 교체`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

#### Q: 기존 PDF 문서를 어떻게 열 수 있나요?

 A: 4단계에서는 다음을 사용하여 기존 PDF 문서를 엽니다.`Document` 생성자를 생성하고 입력 PDF 파일에 대한 경로를 제공합니다.

#### Q: 문서에서 단락을 어떻게 추출합니까?

 A: 5단계에서는`ParagraphAbsorber` 수업과 그 사용`Visit` PDF 문서에서 단락을 추출하는 방법.

#### Q: 추출된 단락을 어떻게 반복합니까?

A: 6단계에서는 추출된 단락을 반복하는 과정을 안내합니다. 중첩 루프는 각 단락 내의 섹션과 줄을 순회하여 궁극적으로 텍스트 내용에 액세스하고 표시하는 데 사용됩니다.

#### Q: 이 튜토리얼의 핵심 내용은 무엇입니까?

A: 이 튜토리얼을 따라 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 단락을 추출하는 방법을 배웠습니다. 추출된 단락이 콘솔 창에 표시되어 문서의 콘텐츠 구조에 대한 귀중한 통찰력을 제공합니다.