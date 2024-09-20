---
title: 텍스트 검색 및 하이퍼링크 추가
linktitle: 텍스트 검색 및 하이퍼링크 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: 단계별 튜토리얼을 통해 Aspose.PDF for .NET을 사용하여 PDF에서 텍스트를 검색하고 하이퍼링크를 추가하는 방법을 알아보세요.
type: docs
weight: 450
url: /ko/net/programming-with-text/search-text-and-add-hyperlink/
---
## 소개

PDF를 조작할 뿐만 아니라 하이퍼링크를 삽입하여 PDF를 향상시킬 방법을 찾고 계신가요? 글쎄요, 당신은 올바른 곳에 있습니다! 강력한 Aspose.PDF for .NET 라이브러리를 사용하면 PDF 문서에서 텍스트 패턴을 검색하고 원활하게 하이퍼링크를 추가할 수 있습니다. 링크를 클릭하기만 하면 정보를 전달할 뿐만 아니라 독자를 관련 리소스에 연결하는 문서가 있다고 상상해보세요. 멋진 것처럼 들리죠? 이 튜토리얼에서는 정규 표현식을 사용하여 텍스트를 검색하고 PDF 내에 하이퍼링크를 추가하는 방법을 단계별로 안내합니다. 노련한 개발자이든 방금 시작한 개발자이든 이 프로세스는 간단하고 보람이 있다는 것을 알게 될 것입니다.

## 필수 조건

세부적인 내용을 살펴보기 전에 따라야 할 모든 것이 있는지 확인해 보겠습니다. 편리한 체크리스트가 있습니다.

- .NET Framework: 컴퓨터에 .NET Framework가 설치되어 있어야 합니다(버전 4.0 이상).
- .NET 라이브러리용 Aspose.PDF: 프로젝트에 Aspose.PDF 라이브러리를 다운로드하고 참조를 추가하는 것을 잊지 마세요. 찾을 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
- IDE: 코드를 작성하고 실행하려면 Visual Studio와 같은 통합 개발 환경(IDE)이 필요합니다.
- 샘플 PDF 파일: 코드를 테스트할 수 있는 샘플 PDF 파일을 가져오세요. 간단한 PDF를 만들거나 기존 문서 중 하나를 사용할 수 있습니다.

이 목록에 있는 모든 것을 완료했다면, 이제 시작할 준비가 되었습니다!

## 패키지 가져오기

여정의 첫 번째 단계는 필요한 패키지를 가져오는 것입니다. 여기서 우리는 프로젝트에 어떤 도구를 사용할지 알려줍니다. 다음은 이를 수행하는 방법입니다.

C# 파일에서 맨 위에 다음 네임스페이스를 포함시켜 시작합니다.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

이러한 네임스페이스를 가져오면 프로그램이 Aspose.PDF가 제공하는 모든 멋진 기능에 액세스할 수 있습니다.

이제 모든 준비가 끝났으니, 행동에 나설 시간입니다. 일련의 단계로 진행해 보겠습니다. 주의 깊게 따라오세요!

### 1단계: 문서 디렉토리 설정

먼저 PDF 파일이 저장된 위치를 지정해야 합니다. 수정`dataDir` 변수는 문서 디렉토리를 가리킵니다. 방법은 다음과 같습니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 교체를 꼭 해주세요`"YOUR DOCUMENT DIRECTORY"` 문서의 실제 경로를 포함합니다.

### 2단계: TextFragmentAbsorber 만들기

 다음으로, 링크하려는 텍스트를 찾을 도구가 필요합니다.`TextFragmentAbsorber`이 작은 친구는 PDF에서 특정 텍스트 패턴을 검색하는 데 도움이 됩니다.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

여기서 우리는 특정 패턴을 찾고 있습니다. 4자리 숫자, 대시, 그 뒤에 또 다른 4자리 숫자(전화번호나 연도와 같음)가 이어지는 패턴입니다.

### 3단계: 정규 표현식 검색 활성화

 우리는 이미 텍스트 패턴을 찾기 위해 정규 표현식을 사용하고 있지만 다음을 확인해야 합니다.`absorber` 활성화되어 있다는 것을 알고 있습니다. 이것은 제대로 검색하는 데 중요합니다.

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

### 4단계: PdfContentEditor 초기화

 이제 흡수 장치가 준비되었으므로 다음이 필요합니다.`PdfContentEditor` PDF 파일을 작업하기 위해. 이 클래스를 사용하면 PDF에 바인딩하고 조작할 수 있습니다.

```csharp
PdfContentEditor editor = new PdfContentEditor();
```

### 5단계: 소스 PDF 파일 바인딩

컨텐츠 편집기가 준비되었으니, 이제 작업하려는 실제 PDF 파일에 바인딩할 차례입니다.

```csharp
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 교체를 꼭 해주세요`"SearchRegularExpressionPage.pdf"` PDF 파일의 이름을 입력합니다.

### 6단계: 페이지에 대한 흡수체 수락

우리는 편집자에게 문서의 특정 페이지를 검색하고 싶다는 것을 알려야 합니다. 이 경우, 페이지 1로 가보겠습니다.

```csharp
editor.Document.Pages[1].Accept(absorber);
```

### 7단계: 텍스트 조각을 반복할 준비

이제 우리는 흡수체가 찾은 모든 텍스트 조각을 반복할 준비가 되었습니다. 우리는 그들의 모양을 조정하고 하이퍼링크를 설정할 것입니다.

```csharp
int[] dashArray = { };
String[] LEArray = { };
Color blue = Color.Blue;
```

여기서는 하이퍼링크의 색상 등 몇 가지 매개변수를 설정합니다.

### 8단계: 각 텍스트 조각을 반복합니다.

검색과 일치하는 모든 텍스트 조각에 대해 색상을 변경하고 하이퍼링크를 만듭니다. 다음과 같습니다.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    Rectangle rect = new Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
    
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, 파란색, actionName);
    editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
        (float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
```

### 9단계: 편집된 PDF 저장

거의 다 됐습니다! 이제 새 PDF 파일에 변경 사항을 저장할 시간입니다.

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
```

### 10단계: 편집기 닫기

마지막으로, 리소스를 공개하려면 문서를 닫는 것을 잊지 마세요!

```csharp
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

이제 검색 결과에 따라 동적으로 생성된 하이퍼링크가 있는 PDF를 만들었습니다. 얼마나 멋진가요?

## 결론

이제 다 봤습니다! 이 단계를 따르면 Aspose.PDF for .NET 라이브러리를 사용하여 PDF를 검색하고 하이퍼링크를 추가하는 방법을 배웠습니다. 특히 상호 작용이 필요한 문서로 작업하는 경우, 이는 가능성의 세계를 열어줄 수 있습니다. 관련 리소스, 참조 웹사이트 또는 내부 페이지에 링크를 추가하는 것을 상상해보세요. 단 몇 줄의 코드만으로 가능합니다!
## 자주 묻는 질문

### .NET용 Aspose.PDF란 무엇인가요?  
.NET용 Aspose.PDF는 개발자가 .NET 애플리케이션에서 PDF 문서를 만들고, 조작하고, 관리할 수 있는 라이브러리입니다.

### .NET용 Aspose.PDF를 어떻게 다운로드할 수 있나요?  
 라이브러리를 다운로드 할 수 있습니다[여기](https://releases.aspose.com/pdf/net/).

### Aspose.PDF를 무료로 사용해 볼 수 있나요?  
 물론입니다! 무료 체험판을 받으실 수 있습니다[여기](https://releases.aspose.com/).

### Aspose 제품에 대한 지원이 제공되나요?  
 네, 지원과 커뮤니티 토론을 찾을 수 있습니다.[여기](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF에 대한 임시 라이선스를 어떻게 얻을 수 있나요?  
 임시 면허를 요청할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).