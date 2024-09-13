---
title: 글꼴 임베드 해제 및 PDF 파일 최적화
linktitle: 글꼴 임베드 해제 및 PDF 파일 최적화
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 단계별 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 글꼴을 포함하고 있는 항목을 해제하고 PDF 파일을 최적화하는 방법을 알아봅니다.
type: docs
weight: 370
url: /ko/net/programming-with-document/unembedfonts/
---
## 소개

디지털 시대에 PDF는 어디에나 있습니다. 보고서, 프레젠테이션 또는 전자책을 공유하든, Portable Document Format(PDF)은 문서의 무결성을 유지하기 위한 최고의 선택입니다. 그러나 더 많은 PDF를 만들고 공유함에 따라 파일 크기가 커져 보내거나 저장하기가 번거로울 수 있습니다. 여기서 Aspose.PDF for .NET이 등장하여 PDF 파일을 최적화하는 강력한 도구를 제공합니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 글꼴을 임베드 해제하고 PDF 파일을 최적화하는 방법을 살펴보겠습니다.

## 필수 조건

본론으로 들어가기 전에 시작하는 데 필요한 모든 것이 있는지 확인해 보겠습니다.

1. Visual Studio: 컴퓨터에 Visual Studio가 설치되어 있는지 확인하세요. .NET 코드를 작성하고 실행하는 데 사용할 IDE입니다.
2.  .NET용 Aspose.PDF: Aspose.PDF 라이브러리를 다운로드하여 설치해야 합니다. 다음에서 가져올 수 있습니다.[다운로드 링크](https://releases.aspose.com/pdf/net/).
3. C#에 대한 기본 지식: C# 프로그래밍에 대한 지식은 우리가 사용할 코드 조각을 이해하는 데 도움이 될 것입니다.
4.  PDF 파일: 최적화하려는 PDF 파일을 준비하세요. 어떤 PDF라도 사용할 수 있지만, 데모를 위해 PDF 파일이라고 부르겠습니다.`OptimizeDocument.pdf`.

## 패키지 가져오기

시작하려면 C# 프로젝트에서 필요한 패키지를 가져와야 합니다. 방법은 다음과 같습니다.

1. Visual Studio에서 프로젝트를 엽니다.
2. Aspose.PDF에 대한 참조를 추가하려면 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "NuGet 패키지 관리"를 선택한 다음 다음을 검색합니다.`Aspose.PDF`. 패키지를 설치합니다.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

이제 모든 것이 설정되었으니 최적화 과정을 관리 가능한 단계로 나누어 보겠습니다.

## 1단계: 문서 디렉토리 설정

먼저, 문서 디렉토리 경로를 정의해야 합니다. 여기에 PDF 파일이 저장됩니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` PDF 파일이 있는 실제 경로와 함께. 이것은 프로그램이 최적화하려는 PDF를 어디에서 찾을지 알아야 하기 때문에 중요합니다.

## 2단계: PDF 문서 열기

이제 디렉토리를 설정했으니 최적화하려는 PDF 문서를 열 차례입니다. 이를 위한 코드는 다음과 같습니다.

```csharp
// 문서 열기
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 이 코드 줄은 새로운 것을 생성합니다.`Document` 개체, PDF 파일을 나타냅니다. 파일 이름이 디렉토리에 있는 파일 이름과 일치하는지 확인하세요.

## 3단계: 최적화 옵션 설정

다음으로, 최적화 옵션을 지정해야 합니다. 이 경우, 글꼴을 언임베드하고 싶습니다. 이를 설정하는 방법은 다음과 같습니다.

```csharp
// UnembedFonts 옵션 설정
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    UnembedFonts = true
};
```

 설정하여`UnembedFonts` 에게`true`, Aspose.PDF에 글꼴을 언임베딩하여 PDF를 최적화하도록 지시하고 있습니다. 이렇게 하면 특히 PDF에 많은 임베디드 글꼴이 포함되어 있는 경우 파일 크기를 상당히 줄일 수 있습니다.

## 4단계: PDF 문서 최적화

옵션을 설정했으니 이제 PDF 문서를 최적화할 차례입니다. 이를 위한 코드는 다음과 같습니다.

```csharp
Console.WriteLine("Start");
// OptimizationOptions를 사용하여 PDF 문서 최적화
pdfDocument.OptimizeResources(optimizeOptions);
```

이 코드 조각은 다음을 호출합니다.`OptimizeResources` 방법에 대한`pdfDocument` 객체, 이전에 정의한 최적화 옵션을 적용합니다. 콘솔에 최적화 프로세스가 시작되었다는 메시지가 표시됩니다.

## 5단계: 업데이트된 문서 저장

PDF를 최적화한 후에는 업데이트된 문서를 저장해야 합니다. 방법은 다음과 같습니다.

```csharp
// 업데이트된 문서 저장
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
```

 이 코드는 최적화된 PDF를 다음과 같이 저장합니다.`OptimizeDocument_out.pdf` 같은 디렉토리에 있습니다. 원한다면 다른 이름을 선택할 수 있지만, 비슷하게 유지하면 원본과 최적화된 버전을 식별하는 데 도움이 됩니다.

## 6단계: 파일 크기 비교

마지막으로, 얼마나 많은 공간을 절약했는지 확인하는 것이 좋습니다. 원본 파일 크기와 최적화된 파일 크기를 비교하는 방법은 다음과 같습니다.

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

이 코드는 원본과 최적화된 PDF의 파일 크기를 검색하여 콘솔에 인쇄합니다. 파일 크기를 얼마나 줄였는지 보는 것은 만족스러운 순간입니다!

## 결론

이제 아시겠죠! Aspose.PDF for .NET을 사용하여 성공적으로 글꼴을 언임베디드하고 PDF 파일을 최적화했습니다. 이 프로세스는 파일 크기를 줄이는 데 도움이 될 뿐만 아니라 PDF 문서의 성능도 향상시킵니다. 이메일을 통해 파일을 공유하든 클라우드에 저장하든, 더 작은 파일 크기는 큰 차이를 만들어낼 수 있습니다.

## 자주 묻는 질문

### .NET용 Aspose.PDF란 무엇인가요?
.NET용 Aspose.PDF는 개발자가 PDF 문서를 프로그래밍 방식으로 만들고, 조작하고, 최적화할 수 있는 강력한 라이브러리입니다.

### Aspose.PDF를 무료로 사용할 수 있나요?
 네, Aspose는 무료 체험판을 제공합니다. 여기에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).

### Aspose.PDF에 대한 지원은 어떻게 받을 수 있나요?
 다음을 통해 지원을 받을 수 있습니다.[Aspose 포럼](https://forum.aspose.com/c/pdf/10).

### PDF에서 어떤 유형의 최적화를 수행할 수 있나요?
글꼴 포함을 해제하고, 이미지를 압축하고, 사용하지 않는 객체를 제거하는 등 다양한 작업을 수행하여 PDF 파일을 최적화할 수 있습니다.

### .NET용 Aspose.PDF를 어디서 구매할 수 있나요?
 라이센스는 다음에서 구매할 수 있습니다.[Aspose 구매 페이지](https://purchase.aspose.com/buy).