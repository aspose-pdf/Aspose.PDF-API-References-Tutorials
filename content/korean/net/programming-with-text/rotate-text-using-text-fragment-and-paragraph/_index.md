---
title: 텍스트 조각과 단락을 사용하여 텍스트 회전
linktitle: 텍스트 조각과 단락을 사용하여 텍스트 회전
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 텍스트 조각과 단락을 사용하여 텍스트를 회전하는 방법을 알아보세요.
type: docs
weight: 400
url: /ko/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 텍스트 조각과 단락을 사용하여 텍스트를 회전하는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

## 전제조건

튜토리얼을 진행하기 전에 다음 사항을 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- .NET 라이브러리용 Aspose.PDF가 설치되었습니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

## 1단계: 프로젝트 설정

선호하는 IDE(통합 개발 환경)에서 새 C# 프로젝트를 생성하고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하는 것으로 시작하세요.

## 2단계: 필요한 네임스페이스 가져오기

필수 네임스페이스를 가져오려면 C# 파일 시작 부분에 다음 using 지시문을 추가하세요.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3단계: PDF 문서 만들기

 초기화`Document` 새 PDF 문서를 만들기 위한 개체:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 꼭 교체하세요`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

## 4단계: 페이지 추가

 다음을 사용하여 문서에서 특정 페이지를 가져옵니다.`Pages.Add()` 방법:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## 5단계: 텍스트 조각 만들기

 여러 개 만들기`TextFragment` 객체의 텍스트와 속성을 설정하고 회전 각도를 지정합니다.

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

원하는 대로 텍스트, 회전 각도 및 기타 속성을 조정합니다.

## 6단계: 페이지에 텍스트 조각 추가

 생성된 텍스트 조각을 페이지에 추가하여 페이지에 추가합니다.`Paragraphs` 수집:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## 7단계: PDF 문서 저장

 다음을 사용하여 수정된 PDF 문서를 파일로 저장합니다.`Save` 방법:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 꼭 교체하세요`"TextFragmentTests_Rotated3_out.pdf"` 원하는 출력 파일 이름으로.

### .NET용 Aspose.PDF를 사용하여 텍스트 조각 및 단락을 사용하여 텍스트 회전에 대한 샘플 소스 코드 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 객체 초기화
Document pdfDocument = new Document();
// 특정 페이지 가져오기
Page pdfPage = (Page)pdfDocument.Pages.Add();
// 텍스트 조각 만들기
TextFragment textFragment1 = new TextFragment("main text");
// 텍스트 속성 설정
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// 텍스트 조각 만들기
TextFragment textFragment2 = new TextFragment("rotated text");
// 텍스트 속성 설정
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// 회전 설정
textFragment2.TextState.Rotation = 315;
// 텍스트 조각 만들기
TextFragment textFragment3 = new TextFragment("rotated text");
// 텍스트 속성 설정
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// 회전 설정
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// 문서 저장
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## 결론

축하해요! .NET용 Aspose.PDF를 사용하여 PDF 문서에서 텍스트 조각과 단락을 사용하여 텍스트를 회전하는 방법을 성공적으로 배웠습니다. 이 튜토리얼에서는 문서 작성부터 수정된 버전 저장까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일의 텍스트 회전을 조작할 수 있습니다.

### FAQ

#### Q: "텍스트 조각 및 단락을 사용하여 텍스트 회전" 튜토리얼의 목적은 무엇입니까?

A: "텍스트 조각 및 단락을 사용하여 텍스트 회전" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서 내의 텍스트 조각과 단락을 모두 사용하여 텍스트를 회전하는 프로세스를 안내하는 것을 목표로 합니다. 튜토리얼에서는 이 기능을 구현하기 위한 단계별 지침과 샘플 코드를 제공합니다.

#### Q: 이 튜토리얼은 이전 텍스트 회전 튜토리얼과 어떻게 다릅니까?

답변: 이 튜토리얼에서는 텍스트 조각과 단락을 결합하여 PDF 문서 내에서 텍스트 회전을 구현합니다. 텍스트 조각을 개별적으로 회전한 다음 페이지의`Paragraphs` 보다 포괄적인 텍스트 회전 효과를 얻기 위한 컬렉션입니다.

#### Q: 텍스트 회전에 텍스트 조각과 단락을 사용하면 어떤 이점이 있나요?

A: 텍스트 조각과 단락을 함께 사용하면 텍스트 회전에 더 많은 유연성이 제공됩니다. 텍스트 조각을 사용하면 개별 회전 및 서식 설정이 가능하고, 단락은 페이지 내에서 텍스트 조각을 정렬하고 배치하기 위한 구조를 제공합니다.

#### Q: 동일한 단락 내의 서로 다른 텍스트 조각에 서로 다른 회전 각도를 적용할 수 있습니까?

 A: 예, 서로 다른 회전 각도를 적용할 수 있습니다.`TextFragment` 같은 단락 내의 개체. 각 텍스트 조각은 다음을 사용하여 지정된 자체 회전 각도를 가질 수 있습니다.`TextState.Rotation` 재산.

#### Q: 이 방법을 사용하여 복잡한 텍스트 회전 효과를 얻을 수 있습니까?

A: 예, 다양한 회전 각도로 텍스트 조각을 결합하고 단락 내에서 정렬하면 복잡하고 사용자 정의된 텍스트 회전 효과를 얻을 수 있어 PDF 문서의 시각적 매력을 향상시킬 수 있습니다.

#### Q: 텍스트 조각과 단락을 사용하여 텍스트를 회전하려면 어떤 단계가 필요합니까?

답변: 단계에는 다음이 포함됩니다.

1. 새 C# 프로젝트를 생성하고 .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가하여 프로젝트를 설정합니다.
2. PDF 문서를 만들고 페이지를 추가합니다.
3. 텍스트 조각 만들기, 속성 설정 및 회전 각도 지정.
4.  다음을 사용하여 페이지에 텍스트 조각 추가`Paragraphs` 수집.
5. 수정된 PDF 문서를 저장합니다.

#### Q: 전체 단락에 회전을 적용할 수 있나요?

 A: 예, 다음을 설정하여 전체 단락에 회전을 적용할 수 있습니다.`TextState.Rotation` 단락 자체의 속성입니다. 그러면 해당 단락 내의 모든 텍스트 조각이 회전됩니다.