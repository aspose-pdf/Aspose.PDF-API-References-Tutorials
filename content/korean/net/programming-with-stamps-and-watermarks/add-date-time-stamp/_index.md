---
title: PDF 파일에 날짜 시간 스탬프 추가
linktitle: PDF 파일에 날짜 시간 스탬프 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 단계별 가이드를 통해 Aspose.PDF for .NET을 사용하여 PDF 파일에 날짜 및 시간 스탬프를 추가하는 방법을 알아보세요. 문서 신뢰성을 강화하는 데 완벽합니다.
type: docs
weight: 10
url: /ko/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
## 소개

문서, 특히 PDF를 관리할 때 날짜 및 시간 스탬프를 추가하면 게임 체인저가 될 수 있습니다. 법률 문서, 프로젝트 보고서 또는 송장을 작업하든 타임스탬프는 신뢰성을 더할 뿐만 아니라 문서가 생성되거나 수정된 시점을 명확하게 기록합니다. 이 가이드에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일에 날짜 및 시간 스탬프를 추가하는 과정을 안내합니다. 

이 글은 간단하고 따라하기 쉬운 방식으로 작성되었으므로 프로그래밍이나 Aspose.PDF 라이브러리를 처음 접하더라도 자신감을 가지고 이 기능을 구현할 수 있을 것입니다. 시작해 볼까요!

## 필수 조건

시작하기 전에 꼭 갖춰야 할 몇 가지 전제 조건이 있습니다.

1. Visual Studio: 컴퓨터에 Visual Studio가 설치되어 있는지 확인하세요. 여기서 코드를 작성하고 실행합니다.
2. .NET용 Aspose.PDF: Aspose.PDF 라이브러리를 다운로드하여 설치해야 합니다. 최신 버전을 찾을 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
3. C#에 대한 기본 지식: C# 프로그래밍에 익숙하면 예제를 더 잘 이해하는 데 도움이 됩니다. 하지만 이제 막 시작하더라도 걱정하지 마세요. 모든 내용을 단계별로 설명해 드리겠습니다.
4.  PDF 파일: 샘플 PDF 파일을 준비하세요. 예를 들어, 우리는 다음과 같은 파일을 사용할 것입니다.`AddTextStamp.pdf`.

이러한 필수 구성 요소를 갖추면 PDF 파일에 날짜와 시간 스탬프를 추가할 준비가 된 것입니다!

## 패키지 가져오기

시작하려면 C# 프로젝트에서 필요한 네임스페이스를 가져와야 합니다. 방법은 다음과 같습니다.

### 새 프로젝트 만들기

1. Visual Studio 열기: Visual Studio 애플리케이션을 실행합니다.
2. 새 프로젝트 만들기: 시작 화면에서 "새 프로젝트 만들기"를 선택하세요.
3. 콘솔 앱 선택: 프로젝트 템플릿 목록에서 "콘솔 앱(.NET Framework)"을 선택합니다.
4.  프로젝트 이름 지정: 예를 들어 프로젝트 이름을 지정합니다.`PDFDateTimeStamp`.

### Aspose.PDF 참조 추가

1. 참조를 마우스 오른쪽 버튼으로 클릭합니다. 솔루션 탐색기에서 프로젝트의 "참조" 폴더를 마우스 오른쪽 버튼으로 클릭합니다.
2. "참조 추가"를 선택합니다. 상황에 맞는 메뉴에서 "참조 추가"를 선택합니다.
3. Aspose.PDF 찾아보기: Aspose.PDF를 다운로드한 위치로 이동하여 선택합니다. "확인"을 클릭하여 프로젝트에 추가합니다.

### 필요한 네임스페이스 가져오기

 당신의 맨 위에`Program.cs` 파일을 만들려면 다음 네임스페이스를 가져와야 합니다.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Annotations;
```

이제 모든 것이 설정되었으니 PDF 파일에 날짜와 시간 스탬프를 추가하는 과정을 명확하고 관리하기 쉬운 단계로 나누어 보겠습니다.

## 1단계: 문서 디렉토리 설정

먼저, PDF 파일이 있는 디렉토리를 지정해야 합니다. 이는 코드가 이 디렉토리에서 PDF를 찾기 때문에 중요합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // 실제 경로로 바꾸세요
```

 교체를 꼭 해주세요`YOUR DOCUMENT DIRECTORY` PDF 파일의 실제 경로를 포함합니다.

## 2단계: PDF 문서 열기

다음으로, 타임스탬프를 추가할 PDF 문서를 엽니다. 

```csharp
// 문서 열기
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 이 코드 줄은 다음을 초기화합니다.`Document` 클래스를 사용하여 PDF 파일을 로드합니다.`pdfDocument` 물체.

## 3단계: 날짜 시간 스탬프 만들기

이제 날짜와 시간 스탬프를 생성할 시간입니다. 특정 방식으로 표시되도록 형식을 지정합니다. 

```csharp
string annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
```

 여기,`DateTime.Now` 현재 날짜와 시간을 가져오고`ToString` 원하는 형식으로 변환합니다.

## 4단계: 텍스트 스탬프 만들기

날짜와 시간 문자열이 준비되면 이제 PDF에 추가될 텍스트 스탬프를 만들 수 있습니다.

```csharp
// 텍스트 스탬프 생성
TextStamp textStamp = new TextStamp(annotationText);
```

 이 줄은 새로운 인스턴스를 생성합니다.`TextStamp` 형식이 지정된 날짜와 시간 문자열을 사용합니다.

## 5단계: 스탬프 속성 설정

스탬프의 모양과 위치를 사용자 지정할 수 있습니다. 속성을 설정하는 방법은 다음과 같습니다.

```csharp
// 스탬프의 속성 설정
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

이 단계에서는 여백을 설정하고 스탬프를 PDF 페이지의 오른쪽 하단 모서리에 맞춥니다.

## 6단계: PDF에 스탬프 추가

이제 PDF 문서에 텍스트 스탬프를 추가할 시간입니다. 

```csharp
// 우표수집에 우표추가
pdfDocument.Pages[1].AddStamp(textStamp);
```

이 줄은 PDF의 첫 페이지에 스탬프를 추가합니다. 다른 페이지에 배치하려면 페이지 번호를 변경할 수 있습니다.

## 7단계: 자유 텍스트 주석 만들기(선택 사항)

스탬프에 주석을 추가하려면 다음을 생성할 수 있습니다.`FreeTextAnnotation` 다음과 같습니다:

```csharp
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;
```

이 선택 단계에서는 스탬프에 대한 추가 맥락이나 정보를 제공할 수 있는 자유 텍스트 주석이 생성됩니다.

## 8단계: 주석 테두리 구성

주석의 테두리를 사용자 지정하려면 다음과 같이 할 수 있습니다.

```csharp
Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

이 코드 조각은 테두리 너비를 0으로 설정하여 테두리를 보이지 않게 하고 PDF에 주석을 추가합니다.

## 9단계: PDF 문서 저장

마지막으로 수정된 PDF 문서를 저장해야 합니다. 

```csharp
dataDir = dataDir + "AddDateTimeStamp_out.pdf"; // 출력 파일 이름을 지정하세요
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);
```

이 줄은 타임스탬프가 추가된 PDF를 새 파일에 저장합니다. 지정한 디렉토리를 확인하여 출력을 볼 수 있습니다.

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 파일에 날짜 및 시간 스탬프를 성공적으로 추가했습니다. 이 간단하면서도 효과적인 기능은 문서를 향상시켜 더욱 전문적으로 만들고 언제 만들어졌거나 수정되었는지에 대한 명확한 기록을 제공할 수 있습니다. 

## 자주 묻는 질문

### 타임스탬프의 날짜 형식을 사용자 지정할 수 있나요?
 네, 수정할 수 있습니다.`ToString`원하는 대로 날짜 형식을 변경하는 방법입니다.

### Aspose.PDF는 무료로 사용할 수 있나요?
 Aspose.PDF는 무료 체험판을 제공하지만, 모든 기능을 사용하려면 라이선스를 구매해야 합니다. 임시 라이선스를 받을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).

### PDF에 여러 타임스탬프를 추가할 수 있나요?
 물론입니다! 여러 개를 만들 수 있습니다.`TextStamp` 인스턴스를 만들어 PDF의 다른 페이지나 위치에 추가합니다.

### Visual Studio가 없으면 어떻게 하나요?
C# IDE나 텍스트 편집기를 사용할 수 있지만 프로젝트를 실행하고 디버깅하려면 Visual Studio를 사용하는 것이 좋습니다.

### Aspose.PDF 사용에 대한 더 많은 예는 어디에서 볼 수 있나요?
 더 많은 예제와 튜토리얼을 탐색할 수 있습니다.[Aspose.PDF 문서](https://reference.aspose.com/pdf/net/).