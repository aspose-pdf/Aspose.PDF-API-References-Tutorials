---
title: PDF 파일에서 글꼴 바꾸기
linktitle: PDF 파일에서 글꼴 바꾸기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일의 글꼴을 쉽게 교체하세요. 글꼴을 교체하기 위한 코드 예제가 있는 단계별 가이드.
type: docs
weight: 340
url: /ko/net/programming-with-text/replace-fonts/
---
## 소개

디지털 시대에 PDF는 비즈니스 보고서부터 개인 문서까지 어디에나 있습니다. 하지만 PDF에 사용된 글꼴이 요구 사항을 충족하지 못하면 어떻게 될까요? 일관성이 없거나 오래되었거나 브랜드와 맞지 않을 수 있습니다. Aspose.PDF for .NET을 사용하면 PDF 파일 내의 글꼴을 쉽게 바꿀 수 있습니다. 이 튜토리얼에서는 단계별로 이를 달성하는 방법을 살펴보고 PDF 파일에서 글꼴 관련 조정을 처리할 수 있도록 완벽하게 준비합니다.

## 필수 조건

Aspose.PDF for .NET을 사용하여 PDF의 글꼴을 바꾸는 과정으로 넘어가기 전에 몇 가지 준비해야 할 사항이 있습니다.

1.  Aspose.PDF for .NET 라이브러리: Aspose.PDF for .NET 라이브러리의 최신 버전을 다운로드하여 설치하세요. 다음에서 가져올 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
2. 개발 환경: Visual Studio와 같은 C# 개발 환경이 설정되어 있는지 확인하세요.
3.  유효한 라이센스: Aspose.PDF는 무료 평가판을 제공하지만 일부 고급 기능에는 라이센스가 필요할 수 있습니다.[임시 면허](https://purchase.aspose.com/temporary-license/) 또는[정식 라이센스를 구매하다](https://purchase.aspose.com/buy).
4. 기본 C# 지식: C# 프로그래밍과 외부 라이브러리 사용에 익숙해야 합니다.

## 네임스페이스 가져오기

글꼴을 바꾸기 전에 C# 프로젝트에서 다음 네임스페이스를 가져와야 합니다.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

이러한 네임스페이스는 PDF 파일을 로드하고 조작하고 저장하는 데 사용되는 클래스와 메서드에 액세스할 수 있게 해주므로 필수적입니다.

이제 PDF 파일에서 글꼴을 대체하는 단계를 분석해 보겠습니다. Arial,Bold라는 글꼴의 모든 인스턴스를 Arial로 대체하는 예를 들어보겠습니다. 방법은 다음과 같습니다.

## 1단계: 프로젝트 설정

PDF 파일을 조작하기 전에 새 프로젝트를 만들고 .NET용 Aspose.PDF 라이브러리를 설치해야 합니다.

1. 새 프로젝트 만들기: Visual Studio(또는 다른 IDE)를 열고 새 C# 콘솔 애플리케이션을 만듭니다.
2.  .NET용 Aspose.PDF 설치: NuGet 패키지 관리자에서 Aspose.PDF를 검색하여 프로젝트에 설치합니다. 또는 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/) 수동으로 참조하세요.

```bash
Install-Package Aspose.PDF
```

## 2단계: 소스 PDF 파일 로드

다음 단계는 글꼴을 대체하려는 PDF 파일을 로드하는 것입니다. 다음을 사용합니다.`Document` 이를 위해서는 수업이 필요합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

1. 경로 지정: PDF 파일이 있는 경로를 정의합니다.`dataDir`).
2.  PDF 로드: 사용`Document` PDF를 메모리에 로드하여 조작할 수 있도록 준비하는 클래스입니다.

## 3단계: 텍스트 조각 흡수기 설정

 특정 텍스트 조각에서 글꼴을 찾아 바꾸려면 다음을 사용합니다.`TextFragmentAbsorber` 클래스. 이 클래스를 사용하면 특정 텍스트 조각을 검색하고 글꼴 바꾸기와 같은 변경 사항을 적용할 수 있습니다.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

1.  TextFragmentAbsorber 생성: 초기화`TextFragmentAbsorber` ~와 함께`TextEditOptions` 사용하지 않는 글꼴을 제거하는 것도 포함됩니다.
2.  텍스트 흡수: 다음을 사용하여 문서의 모든 페이지에 흡수기를 적용합니다.`Accept` 방법.

## 4단계: 텍스트 조각 탐색

텍스트 조각을 흡수한 후에는 각 조각을 반복해서 살펴보고 글꼴을 확인해야 합니다. 글꼴이 Arial, Bold이면 Arial로 바꿉니다.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

1.  조각을 통한 루프: 사용`foreach` 각 텍스트 조각을 반복하기 위한 루프입니다.
2. 글꼴 확인: 각 텍스트 조각에 대해 글꼴이 Arial, Bold인지 확인하세요.
3.  글꼴 바꾸기: 조건이 충족되면 다음을 사용합니다.`FontRepository.FindFont` Arial,Bold를 Arial로 바꾸는 방법입니다.

## 5단계: 업데이트된 PDF 저장

글꼴 교체가 완료되면 업데이트된 PDF 파일을 저장합니다.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
```

1.  출력 경로 정의: 업데이트`dataDir` 새 파일 이름을 포함하는 변수(예:`ReplaceFonts_out.pdf`).
2.  PDF 저장: 사용`Save` 수정된 PDF 파일을 저장하는 방법.
3. 성공 메시지: PDF가 저장되었음을 나타내는 성공 메시지를 콘솔에 인쇄합니다.

## 6단계: 예외 처리

 프로그램이 충돌하지 않도록 하려면 코드를 다음과 같이 래핑하세요.`try-catch` PDF 파일 문제나 글꼴 누락 등 잠재적 오류를 처리하는 블록입니다.

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get a 30 day temporary license.");
}
```

1.  Try-Catch로 감싸기: 글꼴 교체 코드를 다음과 같이 넣으세요.`try` 차단하다.
2.  예외 포착:`catch` 블록하고 발생하는 모든 예외를 기록합니다.

## 결론

PDF 파일의 글꼴을 Aspose.PDF for .NET으로 바꾸는 것은 간단하면서도 강력합니다. 브랜딩을 업데이트하든 문서 전체에서 일관성을 유지하든 이 프로세스는 많은 시간을 절약할 수 있습니다. 위의 단계별 가이드를 따르면 이제 C#을 사용하여 PDF 파일 내의 글꼴을 효율적으로 바꿀 수 있는 도구가 있습니다.

## 자주 묻는 질문

### 하나의 PDF에서 여러 글꼴을 바꿀 수 있나요?
 네, 가능합니다. 수정하세요.`if` 루프에서 여러 글꼴 유형을 타겟으로 하는 조건.

### Aspose.PDF for .NET을 사용하려면 라이선스가 필요합니까?
 네, 일부 기능에는 라이센스가 필요합니다.[임시 면허](https://purchase.aspose.com/temporary-license/) 또는 다음에서 구매하세요[여기](https://purchase.aspose.com/buy).

### 내 시스템에 글꼴을 설치해야 합니까?
네, 원본을 바꾸려는 글꼴이 시스템에서 사용 가능해야 합니다.

### 암호화된 PDF의 글꼴을 바꿀 수 있나요?
 예, 하지만 먼저 다음을 사용하여 PDF를 암호 해독해야 합니다.`Document.Decrypt` 방법.

### 문제가 발생하면 어떻게 도움을 받을 수 있나요?
 당신은 확인할 수 있습니다[지원 포럼](https://forum.aspose.com/c/pdf/10) 도움이 필요하면.