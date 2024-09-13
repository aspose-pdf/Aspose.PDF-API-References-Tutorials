---
title: TOC에서 페이지 번호 숨기기
linktitle: TOC에서 페이지 번호 숨기기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 목차에서 페이지 번호를 숨기는 방법을 알아보세요. 코드 예제가 있는 이 자세한 가이드를 따라 전문적인 PDF를 만드세요.
type: docs
weight: 220
url: /ko/net/programming-with-document/hidepagenumbersintoc/
---
## 소개

PDF로 작업할 때 목차(TOC)를 생성하고 페이지 번호를 숨겨서 매끈하게 유지하고 싶을 때가 있습니다. 페이지 번호 없이도 문서가 더 잘 흐르거나 미적인 선택일 수도 있습니다. 이유가 무엇이든 Aspose.PDF for .NET으로 작업하는 경우 이 튜토리얼은 TOC에서 페이지 번호를 숨기는 방법을 정확히 보여줍니다.

## 필수 조건

시작하기 전에, 몇 가지 준비해야 할 것이 있습니다. 간단한 체크리스트는 다음과 같습니다.

- Visual Studio 설치: 코딩을 하려면 Visual Studio의 실행 버전이 필요합니다.
- .NET용 Aspose.PDF 라이브러리: .NET용 Aspose.PDF 라이브러리를 설치했는지 확인하세요.
  -  다운로드 링크:[.NET용 Aspose.PDF](https://releases.aspose.com/pdf/net/)
- 임시 라이센스: 기능을 테스트해 보는 경우 임시 라이센스가 있으면 유용합니다.
  -  임시 라이센스:[여기서 받으세요](https://purchase.aspose.com/temporary-license/)

## 패키지 가져오기

코드로 넘어가기 전에 C# 프로젝트에서 다음 네임스페이스를 가져오는지 확인하세요. 이는 PDF 문서 작업과 목차(TOC) 생성에 필요한 클래스와 메서드를 제공합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

이제 환경이 준비되었고 패키지가 임포트되었으니 프로세스의 각 단계를 분석해 보겠습니다. 명확성을 보장하기 위해 코드의 모든 부분을 다루어 쉽게 따라갈 수 있도록 하겠습니다.

## 1단계: PDF 문서 초기화

가장 먼저 해야 할 일은 새 PDF 문서를 만들고 목차(TOC) 페이지를 추가하는 것입니다.


```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir: 출력 파일이 저장되는 디렉토리입니다.
- Document(): 새 PDF 문서를 초기화합니다.
- Pages.Add(): 나중에 TOC를 보관할 새 빈 페이지를 문서에 추가합니다.

## 2단계: TOC 정보 및 제목 설정

다음으로, TOC 정보를 정의하고 TOC 상단에 표시될 제목을 설정합니다.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo: 이 객체는 TOC에 대한 모든 정보를 보유합니다.
- TextFragment: TOC 제목의 텍스트를 나타냅니다. 여기서는 "목차"로 설정했습니다.
- 글꼴 스타일: TOC 제목의 크기를 20으로 설정하고 굵게 표시하여 스타일을 지정합니다.
- tocPage.TocInfo: TOC를 표시할 페이지에 TOC 정보를 할당합니다.

## 3단계: TOC에서 페이지 번호 숨기기

이제 재밌는 부분입니다! 여기서 TOC를 구성하여 페이지 번호를 숨깁니다.

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

-  IsShowPageNumbers: 이것은 페이지 번호를 숨기는 마법의 스위치입니다. 이것을 설정하세요`false`, 페이지 번호는 TOC에 나타나지 않습니다.
- FormatArrayLength: 이 값을 4로 설정하면 TOC 제목의 4개 수준에 대한 서식을 정의한다는 것을 나타냅니다.

## 4단계: TOC 형식 사용자 지정

TOC에 더 많은 스타일을 추가하기 위해 이제 다양한 수준의 제목에 대한 서식을 정의하겠습니다.

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray: 이 배열은 TOC 항목의 서식을 제어합니다. 각 인덱스는 다른 제목 수준을 나타냅니다.
- 여백 및 텍스트 스타일: 여백을 설정하고 각 제목 수준에 대해 굵게, 기울임꼴, 밑줄과 같은 글꼴 스타일을 적용합니다.

## 5단계: 문서에 제목 추가

마지막으로 TOC에 포함될 실제 제목을 추가해 보겠습니다.

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- 제목 및 텍스트 세그먼트: TOC에 나타날 제목을 나타냅니다. 각 레벨은 자체 제목을 갖습니다.
- IsAutoSequence: 제목에 자동으로 번호를 매깁니다.
- IsInList: 각 제목이 TOC에 나타나는지 확인합니다.

## 6단계: 문서 저장

모든 것이 설정되면 PDF 문서를 지정된 출력 파일로 저장합니다.

```csharp
doc.Save(outFile);
```

그리고 그게 전부입니다! 목차가 있는 PDF를 성공적으로 만들었고, 페이지 번호는 숨겨졌습니다!

## 결론

PDF에서 목차를 만들고 페이지 번호를 숨기는 것은 까다로울 수 있지만 Aspose.PDF for .NET을 사용하면 아주 간단합니다. 이 단계별 가이드를 따르면 TOC 형식을 사용자 지정하고, 페이지 번호를 숨기고, 제목에 다양한 스타일을 적용하는 방법을 배웠습니다. 이제 귀하의 정확한 요구 사항에 맞게 조정된 전문적인 PDF를 만들 수 있습니다.

## 자주 묻는 질문

### TOC에서 특정 제목의 페이지 번호를 표시할 수 있나요?
아니요, Aspose.PDF는 전체 TOC에 대한 페이지 번호를 숨기거나 표시합니다. 특정 항목에 대해 선택적으로 숨길 수는 없습니다.

### TOC에 더 많은 레벨을 추가할 수 있나요?
 네, 늘릴 수 있습니다.`FormatArrayLength` 더 많은 수준의 TOC 제목을 정의합니다.

### 모든 TOC 항목의 글꼴을 어떻게 변경할 수 있나요?
 글꼴을 수정하여 변경할 수 있습니다.`TextState.Font` 각 레벨의 속성`FormatArray`.

### TOC에 하이퍼링크를 삽입할 수 있나요?
 예, 다음을 사용하여 각 TOC 항목을 문서의 특정 섹션에 연결할 수 있습니다.`Heading.TocPage` 재산.

### Aspose.PDF를 사용하려면 라이선스가 필요한가요?
네, 프로덕션 사용에는 유효한 라이센스가 필요합니다. 임시 라이센스를 받을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/) 기능을 테스트합니다.