---
title: PDF 파일에서 텍스트 조각을 사용하여 텍스트 회전
linktitle: PDF 파일에서 텍스트 조각을 사용하여 텍스트 회전
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일의 텍스트 조각을 사용하여 텍스트를 회전하는 방법을 알아보세요.
type: docs
weight: 390
url: /ko/net/programming-with-text/rotate-text-using-text-fragment/
---
이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 파일의 텍스트 조각을 사용하여 텍스트를 회전하는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

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
using Aspose.Pdf.Text.TextBuilder;
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

 여러개 생성`TextFragment` 객체를 지정하고, 텍스트와 속성을 설정하고, 페이지에서의 위치를 지정합니다.

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

원하는 대로 텍스트, 위치 및 기타 속성을 조정합니다.

## 6단계: TextBuilder를 만들고 텍스트 조각을 추가합니다.

 생성하다`TextBuilder` 객체를 사용하여`pdfPage` 그리고 PDF 페이지에 텍스트 조각을 추가합니다.

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## 7단계: PDF 문서 저장

 수정된 PDF 문서를 파일로 저장하려면 다음을 사용합니다.`Save` 방법:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 교체를 꼭 해주세요`"TextFragmentTests_Rotated1_out.pdf"` 원하는 출력 파일 이름을 입력합니다.

### .NET용 Aspose.PDF를 사용하여 텍스트 조각을 사용하여 텍스트 회전을 위한 샘플 소스 코드 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 객체 초기화
Document pdfDocument = new Document();
// 특정 페이지 가져오기
Page pdfPage = (Page)pdfDocument.Pages.Add();
// 텍스트 조각 만들기
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// 텍스트 속성 설정
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// 회전된 텍스트 조각 만들기
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// 텍스트 속성 설정
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// 회전된 텍스트 조각 만들기
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// 텍스트 속성 설정
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// TextBuilder 객체 생성
TextBuilder textBuilder = new TextBuilder(pdfPage);
// PDF 페이지에 텍스트 조각 추가
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// 문서 저장
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 문서에서 텍스트 조각을 사용하여 텍스트를 회전하는 방법을 성공적으로 배웠습니다. 이 튜토리얼은 문서 생성부터 수정된 버전 저장까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일에서 텍스트 회전을 조작할 수 있습니다.

### 자주 묻는 질문

#### 질문: "텍스트 조각을 사용하여 텍스트 회전" 튜토리얼의 목적은 무엇입니까?

A: "텍스트 조각을 사용하여 텍스트 회전" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서의 텍스트 조각을 사용하여 텍스트를 회전하는 과정을 안내합니다. 이 튜토리얼은 이 기능을 달성하기 위한 단계별 지침과 샘플 코드를 제공합니다.

#### 질문: "텍스트 조각을 사용하여 텍스트를 회전한다"는 것은 무엇을 의미합니까?

A: 텍스트 조각을 사용하여 텍스트를 회전한다는 것은 Aspose.PDF 라이브러리를 사용하여 PDF 문서 내의 개별 텍스트 조각에 회전을 적용하는 기능을 말합니다. 이 기술을 사용하면 PDF 콘텐츠 내에서 다양한 각도나 위치에서 텍스트의 방향을 제어할 수 있습니다.

#### 질문: PDF 문서의 텍스트 일부를 회전하고 싶은 이유는 무엇인가요?

답변: PDF 문서에서 텍스트 조각을 회전하면 특정 콘텐츠를 강조하거나, 예술적 디자인을 만들거나, 레이아웃과 가독성을 개선하는 등 다양한 목적으로 유용할 수 있습니다.

#### 질문: 튜토리얼 프로젝트를 어떻게 설정하나요?

A: 프로젝트를 설정하려면:

1. 선호하는 통합 개발 환경(IDE)에서 새로운 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.
3. C# 파일에 필요한 using 지침을 추가합니다.

#### 질문: 새로운 PDF 문서를 어떻게 만들 수 있나요?

 A: 새 PDF 문서를 만들려면 다음을 초기화하세요.`Document`Aspose.PDF 라이브러리의 객체입니다. 이 객체를 사용하여 PDF에 페이지와 콘텐츠를 추가할 수 있습니다.

#### 질문: 텍스트 조각을 사용하여 텍스트 조각을 회전하려면 어떻게 해야 하나요?

A: 텍스트 조각을 사용하여 텍스트 조각을 회전하려면:

1.  만들다`TextFragment` 사물.
2. 텍스트와 텍스트 조각의 속성을 설정합니다.
3. 페이지에서 텍스트 조각의 위치를 지정합니다.
4.  회전 각도를 설정하려면 다음을 사용하십시오.`TextState.Rotation` 텍스트 조각의 속성.
5.  생성하다`TextBuilder`객체를 만들고 텍스트 조각을 PDF 페이지에 추가합니다.

#### 질문: 다양한 텍스트 조각에 다른 회전 각도를 적용할 수 있나요?

 A: 네, 다양한 회전 각도를 적용할 수 있습니다.`TextFragment` 객체. 각 텍스트 조각은 다음을 사용하여 지정된 자체 회전 각도를 가질 수 있습니다.`TextState.Rotation` 재산.

#### 질문: 회전된 텍스트 조각이 있는 PDF 문서를 저장하려면 어떻게 해야 하나요?

 A: 회전된 텍스트 조각이 있는 PDF 문서를 저장하려면 다음을 사용하세요.`Save` 의 방법`Document` 객체를 선택하고 원하는 출력 파일 경로와 이름을 제공합니다.