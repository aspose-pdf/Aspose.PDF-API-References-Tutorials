---
title: PDF 파일에서 사용하지 않는 글꼴 제거
linktitle: PDF 파일에서 사용하지 않는 글꼴 제거
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에서 사용하지 않는 글꼴을 손쉽게 제거하는 방법을 알아보세요. 성능을 개선하고 파일 크기를 줄이세요.
type: docs
weight: 300
url: /ko/net/programming-with-text/remove-unused-fonts/
---
## 소개

안녕하세요! 불필요한 공간을 차지하는 글꼴로 가득 찬 부풀려진 PDF 파일에 지치셨나요? 여러분만 그런 것은 아닙니다! PDF에서 글꼴 사용을 관리하는 것은 번거로울 수 있습니다. 특히 문서를 깔끔하고 효율적으로 만들고 싶을 때 더욱 그렇습니다. 다행히도 Aspose.PDF for .NET을 사용하면 PDF 파일에서 사용하지 않는 글꼴을 쉽게 제거하여 성능을 향상시키고 파일 크기를 줄일 수 있습니다. 이 튜토리얼에서는 PDF 파일 관리를 간소화할 수 있도록 단계별로 프로세스를 안내해 드리겠습니다.

## 필수 조건

시작하기에 앞서, 이 튜토리얼을 최대한 활용하기 위해 다음 사항이 설정되어 있는지 확인하세요.

1. Visual Studio 설치됨: .NET 코드를 실행하려면 개발 환경이 필요합니다. Visual Studio(모든 버전)는 좋은 선택입니다.
2.  .NET용 Aspose.PDF: 이 라이브러리가 설치되어 있는지 확인하세요. 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
3. C#에 대한 기본적인 이해: 이 예제에서는 C#를 사용하므로 해당 언어에 대한 지식이 필요합니다.
4. PDF 파일: 샘플 PDF 파일을 준비하세요. 직접 만들거나 기존 PDF를 사용할 수 있습니다. 이름이 지정되었는지 확인하세요.`ReplaceTextPage.pdf` 문서 디렉토리에 저장됩니다.
5.  유효한 라이센스: 무료 평가판을 사용할 수 있지만 완전한 기능을 위해서는 유효한 라이센스를 권장합니다. 임시 라이센스가 필요한 경우 다음을 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).

## 패키지 가져오기

이제 필수 구성 요소가 준비되었으니, 필요한 패키지를 C# 프로젝트로 임포트해 보겠습니다. 필요한 것은 다음과 같습니다.

Aspose.PDF 네임스페이스: PDF 파일을 처리하는 데 필요한 모든 기본 기능을 제공합니다.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

이를 가져오려면 위의 줄을 C# 파일 맨 위에 추가하세요. 이렇게 하면 PDF 문서를 조작하는 데 사용할 클래스와 메서드에 액세스할 수 있습니다.

## 1단계: 프로젝트 환경 설정

먼저 해야 할 일! Visual Studio에서 새 콘솔 애플리케이션을 만들어야 합니다. 다음 단계를 따르세요.

- Visual Studio를 엽니다.
- 파일 > 새로 만들기 > 프로젝트를 클릭합니다.
-  콘솔 앱(.NET Framework)을 선택하고 이름을 지정합니다(예:`PdfFontCleaner`).
- 만들기를 클릭합니다.

이제 작업할 새로운 프로젝트가 생겼습니다!

## 2단계: Aspose.PDF 라이브러리 추가

다음으로, Aspose.PDF 라이브러리를 프로젝트에 추가합니다. NuGet을 통해 이를 수행할 수 있습니다.

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭합니다.
2. NuGet 패키지 관리를 선택합니다.
3.  검색`Aspose.PDF` 설치하세요.

## 3단계: PDF 문서 로드

처리하려는 문서를 로드해 보겠습니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY/"; // 이것을 경로로 업데이트하세요
// 소스 PDF 파일 로드
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

 바꾸다`"YOUR DOCUMENT DIRECTORY/"` PDF 파일이 저장된 실제 경로와 함께. 이 단계는 Aspose가 PDF 문서에 액세스할 수 있도록 하기 때문에 중요합니다. 

## 4단계: 텍스트 조각 흡수기 설정

다음으로, PDF에서 사용되지 않는 글꼴을 식별하고 제거하는 데 도움이 되는 프로세서를 설정합니다. 이를 수행하는 코드는 다음과 같습니다.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorber);
```

 이 코드 줄은 다음을 생성합니다.`TextFragmentAbsorber` 사용되지 않는 글꼴을 제거하도록 구성된 개체입니다. 호출하여`doc.Pages.Accept(absorber)`, Aspose에게 문서의 모든 페이지를 검토하여 텍스트 조각을 식별하라고 말하고 있습니다.

## 5단계: 텍스트 조각을 반복하고 글꼴 바꾸기

텍스트 조각을 식별한 후에는 이를 반복하고 사용하지 않는 글꼴을 대체할 차례입니다. 다음 코드를 추가합니다.

```csharp
//모든 TextFragments를 반복합니다.
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

 이 루프에서는 각각의 글꼴을 변경합니다.`TextFragment` "Arial, Bold"로 변경합니다. 필요에 맞는 글꼴을 선택할 수 있습니다. 여기서 진짜 마법이 일어나는데, PDF가 깨끗하고 잘 정의된 글꼴로 남게 되기 때문입니다.

## 6단계: 업데이트된 문서 저장

이제 필요한 변경을 마쳤으니 업데이트된 PDF를 저장해 보겠습니다! 다음 코드를 추가합니다.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
// 업데이트된 문서 저장
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
```

 여기서 우리는 새로운 파일을 생성합니다`RemoveUnusedFonts_out.pdf` 동일한 디렉토리에 있습니다. 이렇게 하면 원본 PDF의 백업을 받을 수 있고, 간소화된 버전을 계속 제공할 수 있습니다.

## 7단계: 예외 처리

마지막으로, 오류 처리를 내장하는 것은 항상 좋은 생각입니다. 코드를 래핑하는 간단한 try-catch 블록은 다음과 같습니다.

```csharp
try
{
    // ... (이전 코드)
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30-day temporary license from https://purchase.aspose.com.");
}
```

이렇게 하면 프로세스 중에 발생하는 모든 예외를 포착하고 사용자 친화적인 오류 메시지를 제공합니다. 사용자에게 유효한 Aspose 라이선스가 필요한 것과 같은 요구 사항을 알리는 것이 필수적입니다.

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 파일에서 사용하지 않는 글꼴을 제거하는 방법을 성공적으로 배웠습니다. 위에 설명된 단계를 따르면 PDF 파일을 더 간결하고 깔끔하게 만들어 더 효율적이고 사용자 친화적으로 만들 수 있습니다. Aspose.PDF의 다른 기능을 탐색하여 문서 처리 기능을 더욱 향상시키는 것을 잊지 마세요!

## 자주 묻는 질문

### 이 작업에 Aspose.PDF 무료 버전을 사용할 수 있나요?
네, 무료 평가판을 사용하실 수 있지만, 최적의 성능을 위해 전체 라이선스를 구매하시는 것이 좋습니다.

### 대체할 수 있는 글꼴이 없다면 해당 글꼴은 어떻게 되나요?
대체 글꼴이 없으면 텍스트가 올바르게 표시되지 않을 수 있으므로 일반적으로 사용되는 글꼴을 선택하세요.

### 임시 면허는 어떻게 받을 수 있나요?
 임시 라이센스를 요청할 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).

### 사용하지 않는 글꼴을 제거하면 문서의 모양에 영향을 미칩니까?
제거된 글꼴과 텍스트 조각이 어떻게 바뀌는지에 따라 달라질 수 있지만 테스트를 권장합니다.

### 사용하지 않는 글꼴을 제거하는 다른 방법이 있나요?
이런 목적에는 Aspose.PDF for .NET이 매우 효율적이지만 다른 라이브러리나 도구가 비슷한 기능을 제공할 수도 있습니다.