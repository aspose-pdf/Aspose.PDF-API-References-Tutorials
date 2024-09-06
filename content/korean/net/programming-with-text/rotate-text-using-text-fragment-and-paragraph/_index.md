---
title: 텍스트 조각과 문단을 사용하여 텍스트 회전
linktitle: 텍스트 조각과 문단을 사용하여 텍스트 회전
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서의 텍스트 조각과 문단을 사용하여 텍스트를 회전하는 방법을 알아보세요.
type: docs
weight: 400
url: /ko/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
이 튜토리얼은 Aspose.PDF for .NET을 사용하여 텍스트 조각과 문단을 사용하여 텍스트를 회전하는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

## 필수 조건

튜토리얼을 진행하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- .NET 라이브러리용 Aspose.PDF가 설치되었습니다. Aspose 웹사이트에서 얻을 수 있거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

## 1단계: 프로젝트 설정

선호하는 통합 개발 환경(IDE)에서 새 C# 프로젝트를 만들고 .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필요한 네임스페이스 가져오기

필요한 네임스페이스를 가져오려면 C# 파일의 시작 부분에 다음 using 지시문을 추가합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3단계: PDF 문서 만들기

 초기화`Document` 새 PDF 문서를 만드는 객체:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 교체를 꼭 해주세요`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 포함합니다.

## 4단계: 페이지 추가

 문서에서 특정 페이지를 가져오려면 다음을 사용합니다.`Pages.Add()` 방법:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## 5단계: 텍스트 조각 만들기

 여러개 생성`TextFragment` 객체를 설정하고, 텍스트와 속성을 설정하고, 회전 각도를 지정합니다.

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

 생성된 텍스트 조각을 페이지에 추가하여 추가합니다.`Paragraphs` 수집:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## 7단계: PDF 문서 저장

 수정된 PDF 문서를 파일로 저장하려면 다음을 사용합니다.`Save` 방법:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 교체를 꼭 해주세요`"TextFragmentTests_Rotated3_out.pdf"` 원하는 출력 파일 이름을 입력합니다.

### .NET용 Aspose.PDF를 사용하여 텍스트 조각과 단락을 사용하여 텍스트 회전을 위한 샘플 소스 코드 
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

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 문서에서 텍스트 조각과 문단을 사용하여 텍스트를 회전하는 방법을 성공적으로 배웠습니다. 이 튜토리얼은 문서 생성부터 수정된 버전 저장까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일에서 텍스트 회전을 조작할 수 있습니다.

### 자주 묻는 질문

#### 질문: "텍스트 조각과 문단을 사용하여 텍스트 회전" 튜토리얼의 목적은 무엇입니까?

A: "텍스트 조각과 문단을 사용하여 텍스트 회전" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서 내에서 텍스트 조각과 문단을 모두 사용하여 텍스트를 회전하는 과정을 안내합니다. 이 튜토리얼은 이 기능을 달성하기 위한 단계별 지침과 샘플 코드를 제공합니다.

#### 질문: 이 튜토리얼은 이전 텍스트 회전 튜토리얼과 어떻게 다릅니까?

A: 이 튜토리얼은 PDF 문서 내에서 텍스트 회전을 달성하기 위해 텍스트 조각과 문단을 사용하는 것을 결합합니다. 텍스트 조각을 개별적으로 회전한 다음 페이지의`Paragraphs` 보다 포괄적인 텍스트 회전 효과를 얻기 위한 컬렉션입니다.

#### 질문: 텍스트 회전에 텍스트 조각과 문단을 사용하면 어떤 이점이 있나요?

A: 텍스트 조각과 문단을 함께 사용하면 텍스트 회전에 더 많은 유연성이 있습니다. 텍스트 조각은 개별 회전 및 서식 설정을 가능하게 하는 반면, 문단은 페이지 내에서 텍스트 조각을 배열하고 배치하기 위한 구조를 제공합니다.

#### 질문: 같은 문단 내의 다른 텍스트 조각에 다른 회전 각도를 적용할 수 있나요?

 A: 네, 다양한 회전 각도를 적용할 수 있습니다.`TextFragment` 동일한 문단 내의 객체. 각 텍스트 조각은 다음을 사용하여 지정된 고유한 회전 각도를 가질 수 있습니다.`TextState.Rotation` 재산.

#### 질문: 이 방법을 사용해 복잡한 텍스트 회전 효과를 낼 수 있나요?

대답: 네, 다양한 회전 각도를 가진 텍스트 조각을 결합하고 문단 내에 배열함으로써 복잡하고 사용자 정의된 텍스트 회전 효과를 얻을 수 있으며, PDF 문서의 시각적 매력을 향상시킬 수 있습니다.

#### 질문: 텍스트 조각과 문단을 사용하여 텍스트를 회전하는 데는 어떤 단계가 포함됩니까?

A: 단계는 다음과 같습니다.

1. 새 C# 프로젝트를 만들고 .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가하여 프로젝트를 설정합니다.
2. PDF 문서를 만들고 페이지를 추가합니다.
3. 텍스트 조각을 만들고, 속성을 설정하고, 회전 각도를 지정합니다.
4.  페이지에 텍스트 조각 추가`Paragraphs` 수집.
5. 수정된 PDF 문서를 저장합니다.

#### 질문: 문단 전체에 회전을 적용할 수 있나요?

 A: 예, 전체 문단에 회전을 적용할 수 있습니다.`TextState.Rotation` 문단 자체의 속성입니다. 이렇게 하면 해당 문단 내의 모든 텍스트 조각이 회전합니다.