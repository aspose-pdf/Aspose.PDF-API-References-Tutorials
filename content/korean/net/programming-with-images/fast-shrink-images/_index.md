---
title: 빠른 축소 이미지
linktitle: 빠른 축소 이미지
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 이미지 크기를 빠르게 줄입니다.
type: docs
weight: 130
url: /ko/net/programming-with-images/fast-shrink-images/
---
이 가이드는 .NET용 Aspose.PDF를 사용하여 PDF 파일의 이미지 크기를 빠르게 줄이는 방법을 단계별로 안내합니다. 이미 환경을 설정했는지 확인하고 아래 단계를 따르세요.

## 1단계: 시간 초기화

시작하기 전에 압축 성능을 측정하기 위한 시간을 초기화하겠습니다. 시작 시간을 기록하려면 다음 코드를 추가하세요.

```csharp
var time = DateTime.Now.Ticks;
```

## 2단계: 문서 디렉터리 정의

 올바른 문서 디렉터리를 설정했는지 확인하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` PDF 문서가 있는 디렉토리의 경로가 포함된 코드에

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3단계: PDF 문서 열기

이 단계에서는 다음을 사용하여 PDF 문서를 엽니다.`Document` Aspose.PDF의 클래스입니다. 사용`Document` 생성자를 선택하고 PDF 문서의 경로를 전달합니다.

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## 4단계: 최적화 옵션 초기화

이 단계에서는 이미지 압축을 위한 최적화 옵션을 초기화합니다. 인스턴스 만들기`OptimizationOptions` 그리고 적절한 옵션을 설정하세요. 이 예에서는 이미지 압축을 활성화하고 이미지 품질을 75로 설정하며 빠른 압축 버전을 사용합니다.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## 5단계: PDF 문서 최적화

 이 단계에서는 앞서 정의한 최적화 옵션을 사용하여 PDF 문서를 최적화합니다. 를 불러`OptimizeResources` 의 방법`pdfDocument` 이의를 제기하고 최적화 옵션을 전달합니다.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## 6단계: 업데이트된 PDF 문서 저장

 다음을 사용하여 업데이트된 PDF 문서를 저장합니다.`Save` 의 방법`pdfDocument` 물체. PDF 파일의 출력 경로를 지정합니다.

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하는 빠른 축소 이미지의 샘플 소스 코드 
```csharp
// 초기화 시간
var time = DateTime.Now.Ticks;
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// 최적화 옵션 초기화
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// CompressImages 옵션 설정
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// ImageQuality 옵션 설정
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
// 이미지 압축 버전을 빠르게 설정하세요.
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
// OptimizationOptions를 사용하여 PDF 문서 최적화
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "FastShrinkImages_out.pdf";
// 업데이트된 문서 저장
pdfDocument.Save(dataDir);
Console.WriteLine("Ticks: {0}", DateTime.Now.Ticks - time);
Console.WriteLine("\nImage fast shrinked successfully.\nFile saved at " + dataDir);
```

## 결론

축하합니다! .NET용 Aspose.PDF를 사용하여 PDF의 이미지 크기를 빠르게 줄였습니다. 최적화된 PDF 파일이 지정된 디렉터리에 저장됩니다. 이제 보다 효율적인 저장 또는 공유 요구를 위해 축소된 이미지와 함께 이 PDF 파일을 사용할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 파일의 이미지 크기를 빠르게 줄이고 싶은 이유는 무엇입니까?

A: PDF 파일의 이미지 크기를 빠르게 줄이면 저장, 공유 또는 전송을 위해 파일을 최적화하는 데 도움이 되어 성능이 향상되고 리소스 소비가 줄어듭니다.

#### Q: PDF 문서에서 이미지 압축은 어떤 이점을 제공합니까?

A: PDF 문서의 이미지 압축은 허용 가능한 이미지 품질을 유지하면서 파일 크기를 최소화하는 데 도움이 되므로 로딩 시간이 빨라지고 저장 요구 사항이 줄어들며 데이터 전송 효율성이 향상됩니다.

#### Q: .NET용 Aspose.PDF는 어떻게 PDF 파일의 이미지 크기를 빠르게 줄일 수 있습니까?

A: .NET용 Aspose.PDF는 PDF 문서를 열고, 이미지 압축 옵션을 적용하고, 축소된 이미지 크기로 최적화된 PDF 파일을 저장하는 간소화된 프로세스를 제공합니다.

####  Q. 의의는 무엇인가요?`OptimizationOptions` class in fast image size reduction?

 답:`OptimizationOptions`클래스를 사용하면 이미지 압축 옵션을 포함한 다양한 최적화 설정을 정의하여 PDF 문서 내의 이미지 크기를 효과적으로 줄일 수 있습니다.

#### Q: 이미지 압축 설정을 사용자 정의하여 파일 크기와 이미지 품질 간의 균형을 제어할 수 있습니까?

A: 예, 이미지 품질, 압축 버전 등의 매개변수를 조정하여 파일 크기와 이미지 모양 간의 원하는 균형을 달성함으로써 이미지 압축 설정을 사용자 정의할 수 있습니다.

####  Q: 어떻게 되나요?`pdfDocument.OptimizeResources` method work to reduce image sizes?

 답:`OptimizeResources` 방법은 PDF 문서를 분석하고 이미지 압축 설정을 포함한 지정된 최적화 옵션을 적용하여 이미지 및 기타 리소스의 크기를 줄입니다.

#### Q: PDF 문서 내의 특정 페이지 범위에 빠른 이미지 크기 축소를 적용할 수 있습니까?

 답:`OptimizeResources` 방법은 전체 PDF 문서에 최적화 옵션을 적용합니다. 특정 페이지에 최적화를 적용하려면 최적화하기 전에 해당 페이지를 새 문서로 추출해야 합니다.

#### Q: 빠른 이미지 크기 축소가 도움이 될 수 있는 시나리오에는 어떤 것이 있습니까?

A: 빠른 이미지 크기 축소는 온라인 배포, 이메일 첨부, 보관을 위해 PDF 파일을 준비하거나 이미지가 많은 대용량 문서를 작업할 때 유용할 수 있습니다.

#### Q: 이미지 크기를 줄이면 PDF 문서에 있는 이미지의 시각적 품질에 영향을 미치나요?

A: 압축을 통해 이미지 크기를 줄이면 이미지 품질에 어느 정도 영향을 미칠 수 있습니다. 크기 감소와 허용 가능한 이미지 품질 간의 균형을 찾는 것이 중요합니다.

#### Q: 빠른 이미지 크기 축소 프로세스의 성능을 어떻게 측정할 수 있습니까?

 A: 다음을 사용하여 시작 시간을 기록하여 성능을 측정할 수 있습니다.`DateTime.Now.Ticks` 최적화 과정 이전에 방법을 사용하고 과정 이후에 경과된 시간을 계산합니다.