---
title: PDF 파일에서 열 텍스트 추출
linktitle: PDF 파일에서 열 텍스트 추출
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에서 텍스트 열을 추출하는 방법을 알아보세요. 이 가이드는 각 단계를 코드 예제와 설명으로 구분합니다.
type: docs
weight: 150
url: /ko/net/programming-with-text/extract-columns-text/
---
## 소개

PDF 파일을 사용하고 특정 열 형식의 텍스트를 추출해야 합니까? 송장, 보고서 또는 구조화된 문서를 처리하든 PDF에서 텍스트를 정확하게 추출하는 것은 까다로운 일이 될 수 있습니다. 여기서 Aspose.PDF for .NET이 프로세스를 간소화하기 위해 나섭니다. 이 튜토리얼에서는 PDF 파일에서 텍스트 열을 쉽게 추출하는 방법을 안내합니다. 

## 필수 조건

코드를 살펴보기 전에 먼저 꼭 필요한 사항을 살펴보겠습니다.

-  .NET용 Aspose.PDF: .NET용 Aspose.PDF의 최신 버전이 설치되어 있는지 확인하세요. 그렇지 않은 경우 다음을 수행할 수 있습니다.[여기서 다운로드하세요](https://releases.aspose.com/pdf/net/).
- 개발 환경: 코드 작업을 위해서는 Visual Studio나 다른 .NET 개발 환경이 필요합니다.
- PDF 문서: 텍스트 열이 포함된 샘플 PDF 문서를 준비해 두세요. 텍스트에서 텍스트를 추출할 예정이기 때문입니다.

 아직 .NET용 Aspose.PDF를 설치하지 않았다면 다음을 사용할 수 있습니다.[무료 체험](https://releases.aspose.com/) 또는[라이센스를 구매하다](https://purchase.aspose.com/buy) 전체 기능을 보려면 다음을 신청할 수도 있습니다.[임시 면허](https://purchase.aspose.com/temporary-license) 필요한 경우.

## 네임스페이스 가져오기

프로젝트에서 Aspose.PDF for .NET을 사용하려면 다음 네임스페이스를 가져와야 합니다.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## 단계별 가이드: PDF에서 텍스트 열 추출

이제 코드의 각 부분을 분석하여 작동 방식을 더 잘 이해해 보겠습니다. 단계별로 진행하면서 프로세스의 각 세그먼트를 설명하면서 따라가세요.

## 1단계: PDF 문서 로드

 첫 번째로 해야 할 일은 PDF 파일을 로드하는 것입니다.`Document`객체. 이것이 Aspose.PDF가 문서와 상호 작용하는 방식입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

 이 단계에서는 PDF 문서가 저장된 디렉토리를 정의합니다. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 로컬 PDF 파일에 대한 경로가 있습니다.`Document` 객체는 PDF를 메모리에 로드하여 추가 처리를 위해 접근할 수 있도록 합니다.

## 2단계: 텍스트 조각 흡수기 설정

 다음으로, 우리는 다음을 사용할 것입니다.`TextFragmentAbsorber` PDF 파일에서 모든 텍스트를 흡수하거나 캡처합니다. 이 흡수 클래스는 PDF의 특정 영역에서 텍스트 조각을 추출하도록 설계되어 텍스트 열을 추출하는 데 이상적입니다.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
```

여기서 우리는 인스턴스를 생성합니다`TextFragmentAbsorber` 그리고 PDF의 모든 페이지에 적용하세요`Accept()` . 그`TextFragmentCollection` 추출된 텍스트를 저장하고, 이 컬렉션에서 필요에 따라 텍스트를 조작하거나 추출할 수 있습니다.

## 3단계: 추출된 텍스트의 글꼴 크기 조정

텍스트 조각을 캡처한 후에는 특히 원래 텍스트가 너무 큰 경우 글꼴 크기를 줄이고 싶을 수 있습니다. 이 예에서는 글꼴 크기를 70% 줄입니다.

```csharp
foreach (TextFragment tf in tfc)
{
    // 글꼴 크기를 70% 줄이세요
    tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

이 코드는 각각을 반복합니다.`TextFragment` 컬렉션에서 글꼴 크기를 70% 줄입니다. 글꼴 크기를 조정하면 추출된 텍스트를 관리하기가 더 쉬워질 수 있으며, 특히 다른 목적으로 서식을 지정하는 경우 더욱 그렇습니다.

## 4단계: 문서를 메모리 스트림에 저장

 텍스트를 수정한 후 PDF를 저장합니다.`MemoryStream`이를 통해 디스크에 다시 쓰지 않고도 추가 처리를 위해 문서를 메모리에 보관할 수 있습니다.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
```

여기서 PDF를 메모리 스트림에 저장한 다음 문서를 다시 로드합니다. 이 방법은 대용량 파일을 작업하고 불필요한 디스크 작업을 피하고 싶을 때 유용합니다.

## 5단계: Text Absorber를 사용하여 모든 텍스트 추출

 이제 PDF를 준비했으니 텍스트를 추출할 차례입니다. 다음을 사용합니다.`TextAbsorber` 문서의 모든 텍스트를 가져옵니다.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
```

 이 단계에서는`TextAbsorber` PDF의 모든 텍스트를 흡수하고 추출된 텍스트는 다음에 저장됩니다.`extractedText` 문자열. 여기서 마법이 일어납니다. 텍스트 열이 이제 일반 텍스트 형식이 됩니다!

## 6단계: 추출된 텍스트를 파일에 저장

 마지막으로 추출된 텍스트를 저장합니다.`.txt` 쉽게 접근하고 추후 활용할 수 있도록 파일로 저장합니다.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

 이 코드는 추출된 텍스트를 새 텍스트로 작성합니다.`.txt` 파일을 저장하고 지정한 디렉토리에 저장합니다. 프로세스가 성공했음을 확인하는 메시지가 콘솔에 표시됩니다.

## 결론

이제 알았어요! Aspose.PDF for .NET을 사용하여 PDF 파일에서 텍스트 열을 추출하는 것은 생각보다 쉽습니다. 몇 줄의 코드만 있으면 PDF를 로드하고, 특정 텍스트를 추출하고, 서식을 조정하고, 결과를 텍스트 파일에 저장할 수 있습니다.

이 기술은 테이블, 보고서 또는 열로 구성된 모든 콘텐츠와 같은 구조화된 문서를 처리하는 데 매우 유용합니다. 데이터 추출을 자동화하거나 대량 문서를 처리해야 하는 경우 Aspose.PDF는 이를 효율적으로 수행할 수 있는 도구를 제공합니다.

## 자주 묻는 질문

### PDF의 특정 페이지에서 텍스트를 추출할 수 있나요?  
 네! 수정할 수 있습니다.`TextFragmentAbsorber` 특정 페이지를 타겟팅하려면 다음을 사용합니다.`pdfDocument.Pages[pageIndex].Accept(tfa);` 방법.

### 여러 열로 구성된 PDF에서 한 열에서만 텍스트를 추출하는 것이 가능할까요?  
 예, 하지만 다음을 사용하여 텍스트 조각의 좌표로 작업해야 합니다.`TextFragment.Rectangle` 문서의 특정 부분을 타겟으로 삼습니다.

### 텍스트 추출의 정확도를 어떻게 높일 수 있나요?  
 더 나은 정확성을 위해 PDF 구조가 잘 정의되어 있는지 확인하고 복잡한 레이아웃이 있는 문서는 피하십시오. 또한 다음을 미세 조정할 수 있습니다.`TextFragmentAbsorber` 글꼴 스타일, 크기 또는 지역에 따라 텍스트를 추출합니다.

### Aspose.PDF는 스캔한 문서에서 텍스트 추출을 지원합니까?  
네, 하지만 OCR(Optical Character Recognition) 기술을 사용해야 합니다. Aspose도 이를 위한 도구를 제공합니다.

### 수천 페이지가 넘는 대용량 PDF 파일을 어떻게 처리하나요?  
대용량 PDF의 경우, 메모리 사용량이 높아지는 것을 막기 위해 한 번에 몇 페이지에서 텍스트를 추출하여 문서를 청크로 처리하세요.