---
title: PDF 파일에 텍스트 스탬프 추가
linktitle: PDF 파일에 텍스트 스탬프 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 텍스트 스탬프를 추가하는 방법을 단계별 가이드를 통해 알아보고 문서 프레젠테이션을 한 단계 업그레이드해 보세요.
type: docs
weight: 50
url: /ko/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
## 소개

오늘날의 디지털 시대에 PDF는 문서를 공유하고 전달하는 일반적인 형식입니다. 개발자이든, 콘텐츠 제작자이든, 아니면 PDF 파일을 개선하려는 사람이든, PDF를 프로그래밍 방식으로 조작하는 방법을 아는 것은 게임 체인저가 될 수 있습니다. 사용하고 싶을 수 있는 멋진 기능 중 하나는 PDF 파일에 텍스트 스탬프를 추가하는 기능입니다. 텍스트 스탬프를 추가하면 문서에 전문적인 느낌을 주거나 "샘플", "기밀" 또는 워터마크와 같은 중요한 정보를 전달할 수 있습니다.

## 필수 조건

코드로 넘어가기 전에 모든 것이 올바르게 설정되었는지 확인하기 위한 몇 가지 전제 조건이 있습니다. 필요한 것은 다음과 같습니다.

1.  .NET용 Aspose.PDF: 프로젝트에 Aspose.PDF 라이브러리가 설치되어 있는지 확인하세요. 아직 설치하지 않았다면 다음에서 다운로드할 수 있습니다.[Aspose 웹사이트](https://releases.aspose.com/pdf/net/).
2. Visual Studio 또는 호환 IDE: .NET 코드를 작성하고 실행하려면 개발 환경이 필요합니다. Visual Studio는 개발자들 사이에서 가장 일반적인 선택입니다.
3. C#에 대한 기본 지식: C#와 객체 지향 프로그래밍 원리에 익숙하면 예제를 더 잘 이해하는 데 도움이 됩니다.
4. 샘플 PDF 파일: 작업할 PDF 파일이 준비되어 있어야 합니다. 기본 PDF를 만들거나 기존 PDF를 사용하여 기능을 테스트할 수 있습니다.

이러한 전제 조건을 갖추면 이제 코딩으로 넘어갈 수 있습니다!

## 패키지 가져오기

이제 필요한 패키지를 임포트해 봅시다. 이 단계는 Aspose 라이브러리의 클래스와 메소드를 프로젝트에서 사용할 수 있게 하기 때문에 중요합니다.

### Aspose.PDF 어셈블리 가져오기

시작하려면 Aspose.PDF 네임스페이스를 가져와야 합니다. C# 파일의 맨 위에 다음 using 지시문을 추가합니다.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

이를 통해 PDF 문서를 만들고 조작하는 데 필수적인 수업을 수강할 수 있습니다.

이제 튜토리얼의 핵심으로 들어가겠습니다. 우리는 과정을 명확하고 간결한 단계로 나눌 것입니다. 각 단계는 PDF 파일에 텍스트 스탬프를 추가하는 코드를 안내합니다.

## 1단계: 문서 디렉토리 설정

먼저, PDF 문서가 저장된 디렉토리를 설정해야 합니다. 즉, 코드는 편집하려는 PDF 파일을 어디에서 찾을 수 있는지 알아야 합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 설명: 바꾸기`"YOUR DOCUMENT DIRECTORY"` PDF 파일이 있는 실제 경로와 함께 (`AddTextStamp.pdf`)이 저장됩니다. 이 경로는 나중에 수정된 PDF를 열고 저장하는 데 사용됩니다.

## 2단계: PDF 문서 열기

 다음으로, 다음을 사용하여 PDF 문서를 엽니다.`Document` Aspose.PDF 네임스페이스의 클래스입니다.

```csharp
// 문서 열기
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 설명: 여기서 우리는 인스턴스를 생성하고 있습니다.`Document` 클래스를 만들고 PDF 파일에 대한 경로를 전달합니다. 이렇게 하면 PDF가 로드되어 조작할 수 있습니다.

## 3단계: 텍스트 스탬프 만들기

이제 나중에 PDF 문서에 적용할 텍스트 스탬프를 만들어 보겠습니다.

```csharp
// 텍스트 스탬프 생성
TextStamp textStamp = new TextStamp("Sample Stamp");
```

 설명:`TextStamp` 객체는 표시하려는 텍스트로 생성됩니다. 이 경우, 우리는 스탬프의 텍스트로 "Sample Stamp"를 사용합니다.

## 4단계: 스탬프 속성 설정

스탬프를 사용자 지정하려면 배경색, 위치, 회전과 같은 다양한 속성을 설정할 수 있습니다. 지금 해보겠습니다.

```csharp
// 스탬프를 배경으로 할지 설정
textStamp.Background = true;

// 원점 설정
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// 스탬프 회전
textStamp.Rotate = Rotation.on90;
```

설명:
- 배경: 이것을 설정`true` 즉, 스탬프가 PDF 내용 뒤에 표시됩니다.
- XIndent & YIndent: 이 속성은 페이지에서 스탬프의 위치를 결정합니다. 이 예에서 스탬프는 페이지의 왼쪽과 위쪽 가장자리에서 100단위 떨어진 곳에 배치됩니다.
- 회전: 스탬프를 90도 회전합니다. 디자인 요구 사항에 따라 다양한 회전 옵션을 선택할 수 있습니다.

## 5단계: 텍스트 속성 사용자 지정

다음으로, 스탬프 내 텍스트의 모양을 사용자 지정하여 창의력을 발휘해 보겠습니다.

```csharp
// 텍스트 속성 설정
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(Color.Aqua);
```

설명:
- 글꼴: Arial 글꼴을 사용하여 굵게, 기울임체로 표시했습니다.
- 글꼴 크기: 14포인트로 설정되었습니다.
- ForegroundColor: RGB를 사용하여 텍스트 색상을 Aqua로 설정합니다. 브랜딩이나 디자인 요구 사항에 맞게 색상을 자유롭게 변경하세요!

## 6단계: PDF 페이지에 스탬프 추가

이제 PDF 문서의 특정 페이지에 스탬프를 추가할 시간입니다.

```csharp
// 특정 페이지에 스탬프 추가
pdfDocument.Pages[1].AddStamp(textStamp);
```

설명: 이 예에서 스탬프는 PDF의 첫 페이지에 추가됩니다(페이지는 1-인덱싱됨). 문서에 맞게 페이지 번호를 조정하세요.

## 7단계: 수정된 PDF 저장

마지막으로 새로 추가한 텍스트 스탬프로 문서를 저장해 보겠습니다.

```csharp
dataDir = dataDir + "AddTextStamp_out.pdf";

// 출력 문서 저장
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);
```

설명: 출력 파일에 대한 새 경로를 정의한 다음 수정된 문서를 저장합니다. 저장 후 경로가 콘솔에 인쇄되어 작업이 성공했음을 확인합니다.

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 파일에 텍스트 스탬프를 성공적으로 추가했습니다. 이 방법을 사용하면 문서에 효율적으로 주석을 달 수 있어 전문성과 사용성을 모두 향상시킬 수 있습니다. 워터마크, 서명 또는 간단한 메모를 추가하든 Aspose 라이브러리는 PDF를 쉽게 조작할 수 있는 강력한 도구를 제공합니다.

## 자주 묻는 질문

### PDF의 텍스트 스탬프란 무엇입니까?
텍스트 스탬프는 PDF 문서에 배치할 수 있는 텍스트가 포함된 그래픽 오버레이로, 종종 주석이나 워터마크에 사용됩니다.

### 스탬프를 이미지로 맞춤 설정할 수 있나요?
네, Aspose.PDF는 이미지 스탬프 추가도 지원하여 디자인의 유연성을 높입니다.

### Aspose.PDF에서 어떤 프로그래밍 언어를 사용할 수 있나요?
Aspose.PDF는 주로 .NET에 초점을 맞추고 있지만 Java 및 Python 등 다른 언어에 대한 버전도 제공됩니다.

### Aspose.PDF에 대한 임시 라이선스를 받으려면 어떻게 해야 하나요?
 임시 면허 신청은 다음 사이트를 방문하여 신청할 수 있습니다.[구매 링크](https://purchase.aspose.com/temporary-license/) 그들의 웹사이트에서.

### Aspose.PDF에 대한 지원은 어디에서 찾을 수 있나요?
 Aspose.PDF에 대한 지원은 다음에서 제공됩니다.[지원 포럼](https://forum.aspose.com/c/pdf/10).