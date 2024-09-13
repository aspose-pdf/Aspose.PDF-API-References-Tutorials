---
title: 브래들리 알고리즘
linktitle: 브래들리 알고리즘
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET에서 Bradley 알고리즘을 사용하여 PDF를 TIFF로 변환하는 방법을 알아보세요. 원활한 변환을 위한 단계별 가이드, 필수 조건 및 FAQ.
type: docs
weight: 30
url: /ko/net/programming-with-images/bradley-algorithm/
---
## 소개

PDF 파일을 다루는 것은 단순히 읽거나 편집하는 것 이상을 요구할 수 있습니다. 이미지로 변환해야 할 수도 있습니다. PDF를 TIFF 이미지로 변환하는 강력한 방법 중 하나는 Aspose.PDF for .NET 라이브러리를 통해 Bradley 알고리즘을 사용하는 것입니다. 이 방법은 문서 보관 및 기타 특수 사용 사례에 적합한 고품질 바이너리 이미지를 보장합니다.

이 튜토리얼은 Bradley Binarization Algorithm을 사용하여 PDF 페이지를 TIFF 이미지로 변환하는 자세하고 따라하기 쉬운 프로세스를 안내합니다. Aspose.PDF for .NET은 이 작업을 간소화하여 문서 워크플로를 자동화하고 간소화할 수 있는 기능을 제공합니다.

## 필수 조건

코드를 살펴보기 전에 먼저 따라야 할 모든 것이 있는지 확인해 보겠습니다.

-  .NET용 Aspose.PDF: 라이브러리가 필요합니다. 여기에서 다운로드하세요.[여기](https://releases.aspose.com/pdf/net/).
- Visual Studio(또는 C# IDE).
- C#에 대한 기본 지식.
-  유효한 면허증 또는[임시 면허](https://purchase.aspose.com/temporary-license/) Aspose에서.

## 패키지 가져오기

먼저, 프로젝트에 필요한 네임스페이스를 가져오세요. 이러한 라이브러리는 PDF 문서를 조작하고, TIFF 형식으로 변환하고, Bradley 이진화 알고리즘을 적용하는 도구를 제공합니다.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

순조롭게 따라갈 수 있도록 프로세스를 간단한 단계로 나누어 보겠습니다. 이 가이드를 마치면 Bradley 알고리즘을 사용하여 PDF 페이지를 바이너리 TIFF 이미지로 성공적으로 변환할 수 있습니다.

## 1단계: 문서 디렉토리 설정

첫 번째 단계는 PDF 문서가 있는 디렉토리 경로를 지정하는 것입니다. 또한 생성될 TIFF 이미지의 출력 경로도 정의합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // PDF 파일에 대한 경로
```

여기서는 원본 PDF와 변환된 TIFF 파일을 모두 저장합니다. 코드가 오류 없이 파일을 읽고 쓸 수 있도록 디렉토리가 제대로 설정되었는지 확인하세요.

## 2단계: PDF 문서 열기

이제 경로가 설정되었으므로 변환하려는 PDF 문서를 열 차례입니다. Aspose.PDF for .NET은 추가 처리를 위해 문서를 로드하는 것을 간단하게 만듭니다.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

 여기,`PageToTIFF.pdf` 샘플 파일입니다. 원하는 PDF 파일로 바꿀 수 있습니다. 이제 문서 객체는 추가 조작을 위해 PDF를 보관합니다.

## 3단계: 이미지에 대한 출력 경로 정의

다음으로, 표준 TIFF와 이진화된 버전을 모두 포함하여 생성된 TIFF 파일에 대한 출력 경로를 지정합니다.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

이러한 경로를 분리하면 표준 TIFF 변환을 위한 파일 하나와 Bradley 알고리즘을 적용한 이진화된 이미지용 파일 하나가 생깁니다.

## 4단계: 해결 객체 생성

PDF를 TIFF로 변환할 때 해상도는 이미지 품질을 결정하는 데 중요한 역할을 합니다. 우리의 목적상, 고품질 출력을 보장하기 위해 해상도를 300 DPI로 설정하겠습니다.

```csharp
Resolution resolution = new Resolution(300);
```

DPI가 높을수록 이미지 선명도가 높아지며, 특히 인쇄하거나 보관할 문서를 다룰 때 더욱 그렇습니다.

## 5단계: TIFF 설정 구성

다음으로, TIFF 이미지에 대한 설정을 구성해야 합니다. 여기서는 LZW 압축을 사용하고 색상 깊이를 1bpp(픽셀당 1비트)로 설정하여 이진 이미지를 얻습니다.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

깊이를 1bpp로 설정하여 이진 출력을 위한 이미지를 준비합니다. LZW 압축은 품질을 잃지 않고 파일 크기를 줄이는 효율성 때문에 선택되었습니다.

## 6단계: TIFF 장치 생성

이제 변환을 처리할 TIFF 장치를 만들어야 합니다. 이 장치는 이전에 정의된 해상도와 TIFF 설정을 사용합니다.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

TIFF 장치는 이 작업의 핵심입니다. PDF 문서를 가져와서 사전 정의된 설정에 따라 각 페이지를 TIFF 이미지로 변환합니다.

## 7단계: PDF 페이지를 TIFF로 변환

 PDF를 처리하고 첫 번째 페이지를 TIFF 이미지로 변환할 시간입니다.`Process` 이 방법을 사용하면 특정 페이지나 전체 문서를 변환할 수 있습니다. 이 예에서는 첫 번째 페이지를 변환합니다.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

이 방법이 완료되면 앞서 정의한 위치에 TIFF 이미지가 저장됩니다.

## 8단계: Bradley 이진화 알고리즘 적용

이제 마법이 등장합니다. Bradley 알고리즘입니다! 이 알고리즘은 회색조 TIFF 이미지를 이진 이미지로 변환하여 문서 인식 시스템에 최적화합니다.

```csharp
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
    using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
    {
        tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
    }
}
```

 BinarizeBradley 메서드는 두 개의 파일 스트림(입력 및 출력)과 임계값(여기서는)을 사용합니다.`0.1`) 이진화 수준을 결정합니다. 실행 후 완벽하게 이진화된 이미지를 사용할 준비가 됩니다.

## 9단계: 성공적인 전환 확인

마지막으로, 사용자에게 프로세스가 성공했음을 알리는 것이 좋습니다. 간단한 콘솔 출력으로 이를 수행할 수 있습니다.

```csharp
System.Console.WriteLine("Conversion using Bradley algorithm performed successfully!");
```

이것이 인쇄되면, PDF 페이지가 이진 TIFF 이미지로 성공적으로 변환되었다는 것을 알 수 있습니다!

## 결론

이제 PDF 페이지를 TIFF 이미지로 변환하고 Aspose.PDF for .NET을 사용하여 Bradley 이진화 알고리즘을 적용하는 방법을 배웠습니다. 이 프로세스는 문서 보관, 광학 문자 인식(OCR) 및 기타 전문 응용 프로그램에 필수적입니다. 고품질 해상도와 효율적인 압축을 통해 문서 이미지가 선명하고 크기가 관리하기 쉬운지 확인할 수 있습니다.

## 자주 묻는 질문

### 브래들리 알고리즘이란?
브래들리 알고리즘은 주변 환경에 따라 각 픽셀에 대한 적응적 임계값을 결정하여 회색조 이미지를 이진(흑백) 이미지로 변환하는 이진화 기술입니다.

### 이 방법을 사용하여 여러 개의 PDF 페이지를 TIFF로 변환할 수 있나요?
 네, 수정할 수 있습니다.`Process` 문서의 페이지를 순환하여 모든 페이지를 변환하는 방법입니다.

### PDF를 TIFF로 변환할 때 최적의 해상도는 무엇입니까?
고품질 이미지의 경우 일반적으로 300 DPI가 권장됩니다. 그러나 필요에 따라 이 값을 조정할 수 있습니다.

### 색상 심도에서 1bpp는 무엇을 의미합니까?
1bpp(픽셀당 1비트)는 이미지가 흑백임을 의미하며, 각 픽셀은 완전히 검은색이거나 완전히 흰색입니다.

### Bradley 알고리즘은 OCR에 적합합니까?
네, 브래들리 알고리즘은 스캔한 문서의 텍스트 대비를 향상시키기 때문에 OCR 사전 처리에 자주 사용됩니다.