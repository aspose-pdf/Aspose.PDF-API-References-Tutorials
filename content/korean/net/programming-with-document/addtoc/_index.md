---
title: PDF 파일에 목차 추가
linktitle: PDF 파일에 목차 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF에 목차를 추가하는 방법을 알아보세요. 이 단계별 가이드는 프로세스를 간소화하고 문서 내에서 쉽게 탐색할 수 있도록 보장합니다.
type: docs
weight: 40
url: /ko/net/programming-with-document/addtoc/
---
## 소개

긴 PDF를 끝없이 스크롤하면서 잘 정리된 목차가 있었으면 좋겠다고 생각한 적이 있나요? 글쎄요, 오늘은 당신의 행운의 날입니다! 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 목차를 추가하는 방법을 알아봅니다. 복잡한 보고서, 전자책 또는 사업 제안서를 작업하든 목차는 문서를 전문적이고 탐색하기 쉬운 걸작으로 바꿀 수 있습니다.

## 필수 조건

코드로 넘어가기 전에 먼저 필요한 모든 것이 있는지 확인해 보겠습니다.

1. .NET용 Aspose.PDF: Aspose.PDF 라이브러리를 다운로드하여 설치했는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
   
2. 개발 환경: Visual Studio와 같은 .NET 개발 환경이 컴퓨터에 설치되어 있는지 확인하세요.

3.  라이센스: 라이센스가 없는 경우 무료 체험판을 받거나 임시 라이센스를 요청할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).

## 패키지 가져오기

시작하려면 코드 파일의 시작 부분에서 필요한 네임스페이스를 가져오세요. 방법은 다음과 같습니다.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

이러한 네임스페이스를 사용하면 PDF 관련 기능에 액세스하고 문서 내의 텍스트 요소를 조작할 수 있습니다.

이 작업을 한 입 크기의 단계로 나누어 보겠습니다. 각 단계는 PDF 문서에 TOC를 만들고 삽입하는 과정을 안내합니다.

## 1단계: PDF 문서 로드

가장 먼저 해야 할 일은 TOC를 추가하려는 기존 PDF 파일을 로드하는 것입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

 이 단계에서는 문서 디렉토리 경로를 지정하고 다음을 사용하여 PDF를 로드합니다.`Document` 객체입니다. 반드시 교체하세요.`"YOUR DOCUMENT DIRECTORY"` 파일의 실제 경로를 포함합니다.

## 2단계: TOC에 대한 새 페이지 삽입

다음으로, PDF 문서의 시작 부분에 새 페이지를 삽입합니다. 이 페이지는 목차를 호스팅합니다.

```csharp
Page tocPage = doc.Pages.Insert(1);
```

TOC 페이지를 시작 부분에 삽입함으로써 독자가 PDF에서 가장 먼저 보는 부분으로 표시되도록 합니다.

## 3단계: TOC 정보 개체 만들기

이제 TOC 정보를 나타낼 객체를 만들어 보겠습니다. 또한 TOC에 제목을 추가하여 눈에 띄게 만들겠습니다.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

여기에서는 TOC의 제목을 "목차"로 설정하고 글꼴 크기를 늘리고, 강조를 위해 굵게 표시했습니다.

## 4단계: TOC 요소 정의

이 단계에서는 TOC에 표시될 요소(또는 제목)를 정의합니다. 이러한 요소는 독자가 문서의 특정 섹션으로 이동하는 데 도움이 됩니다.

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
```

우리는 PDF의 다양한 페이지에 해당하는 TOC 항목으로 사용될 문자열 배열을 생성했습니다.

## 5단계: TOC 제목 만들기

이제 가장 중요한 단계, 즉 TOC에 제목을 추가하고 이를 해당 페이지에 연결하는 단계입니다.

```csharp
for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;
    segment2.Text = titles[i];

    tocPage.Paragraphs.Add(heading2);
}
```

무슨 일이 일어나고 있는지 알려드리겠습니다.
- 제목: 우리는 만듭니다`Heading` 객체를 추가하고`TextSegment` 그것에.
- 도착 페이지: 각 제목이 링크될 페이지를 설정합니다.
- 상단 위치: 제목이 가리키는 페이지의 위치를 지정합니다.
- 텍스트: 각 제목은 앞서 만든 배열에서 해당 제목을 가져옵니다.

이 루프는 TOC의 처음 두 요소에 대한 제목을 만들고 이를 해당 페이지에 연결합니다.

## 6단계: TOC를 포함한 PDF 저장

마지막으로 TOC 요소를 모두 추가한 후에는 업데이트된 PDF를 저장할 때입니다.

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
```

이제 파일이 PDF에 TOC가 추가되어 저장됩니다. 축하합니다. 목차를 성공적으로 추가했습니다!

## 7단계: 확인 메시지

사용자에게 프로세스가 완료되었음을 알리기 위해 콘솔에 간단한 메시지를 표시합니다.

```csharp
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## 결론

이제 다 알게 되셨죠! Aspose.PDF for .NET을 사용하면 PDF에 목차를 추가하는 것이 쉬울 뿐만 아니라 사용자 정의도 가능합니다. 간단한 탐색 링크나 복잡한 구조를 만들어야 하든 이 도구가 해결해 드립니다. 그러니 다음에 긴 PDF를 작업할 때는 전문적인 터치를 위해 목차를 추가하는 것을 잊지 마세요!

## 자주 묻는 질문

### Aspose.PDF에서 TOC의 모양을 사용자 정의할 수 있나요?  
네, TOC의 모양을 글꼴 스타일, 크기, 정렬 등 원하는 대로 사용자 지정할 수 있습니다.

### TOC에 부제목을 추가하려면 어떻게 해야 하나요?  
 하위 제목을 추가하려면 다음을 조정하세요.`Heading` 수준(예:`Heading(2)`)을 사용하여 계층적 TOC를 만듭니다.

### 문서가 변경되면 TOC를 자동으로 업데이트할 수 있나요?  
아니요, TOC는 자동으로 업데이트되지 않습니다. 문서 구조가 변경되면 다시 만들어야 합니다.

### TOC 항목을 외부 문서에 연결할 수 있나요?  
네, 하이퍼링크를 사용하여 TOC 항목을 외부 PDF나 URL에 연결할 수 있습니다.

### Aspose.PDF는 다단계 목차를 지원합니까?  
네, Aspose.PDF는 하위 섹션이 있는 복잡한 문서에 대해 다단계 TOC를 지원합니다.