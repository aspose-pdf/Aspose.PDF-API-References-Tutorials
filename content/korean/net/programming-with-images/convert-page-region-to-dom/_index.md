---
title: 페이지 영역을 DOM으로 변환
linktitle: 페이지 영역을 DOM으로 변환
second_title: .NET API 참조용 Aspose.PDF
description: Aspose.PDF for .NET을 사용하면 PDF 페이지의 특정 영역을 DOM(문서 개체 모델)으로 쉽게 변환할 수 있습니다.
type: docs
weight: 80
url: /ko/net/programming-with-images/convert-page-region-to-dom/
---
이 가이드는 .NET용 Aspose.PDF를 사용하여 페이지의 특정 영역을 DOM(문서 개체 모델)으로 변환하는 방법을 단계별로 안내합니다. 이미 환경을 설정했는지 확인하고 아래 단계를 따르세요.

## 1단계: 문서 디렉터리 정의

 시작하기 전에 문서에 대한 올바른 디렉토리를 설정했는지 확인하십시오. 바꾸다`"YOUR DOCUMENT DIRECTORY"` PDF 문서가 있는 디렉토리의 경로가 포함된 코드에

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 열기

이 단계에서는 다음을 사용하여 PDF 문서를 엽니다.`Document` Aspose.PDF의 클래스입니다. 사용`Document` 생성자를 선택하고 PDF 문서의 경로를 전달합니다.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## 3단계: 페이지 영역 직사각형 가져오기

 이 단계에서는 DOM으로 변환하려는 페이지의 특정 영역을 나타내는 직사각형을 정의합니다. 사용`Aspose.Pdf.Rectangle` 직사각형의 좌표를 정의하는 클래스입니다.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## 4단계: 페이지의 자르기 영역 정의

 사용`CropBox` 의 재산`Page` 페이지의 자르기 상자를 원하는 영역 직사각형으로 설정하는 개체입니다.

```csharp
document.Pages[1].CropBox = pageRect;
```

## 5단계: 잘린 PDF 문서를 스트림에 저장

 이 단계에서는 자른 PDF 문서를 다음을 사용하여 스트림에 저장합니다.`MemoryStream` 수업.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## 6단계: 자른 PDF 문서를 열고 이미지로 변환

 다음을 사용하여 잘린 PDF 문서를 엽니다.`Document` 클래스를 만들어 이미지로 변환합니다. 우리는 300dpi의 해상도를 사용하겠습니다.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## 7단계: 특정 페이지를 이미지로 변환

 다음을 사용하여 특정 페이지를 이미지로 변환합니다.`Process` 의 방법`pngDevice`물체. 이미지 출력 경로를 지정합니다.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### .NET용 Aspose.PDF를 사용하여 페이지 영역을 DOM으로 변환하기 위한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document document = new Document( dataDir + "AddImage.pdf");
// 특정 페이지 영역의 사각형 가져오기
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
// 원하는 페이지 영역의 직사각형에 따라 CropBox 값을 설정하십시오.
document.Pages[1].CropBox = pageRect;
// 자른 문서를 스트림에 저장
MemoryStream ms = new MemoryStream();
document.Save(ms);
// 자른 PDF 문서를 열고 이미지로 변환
document = new Document(ms);
// 해결 객체 생성
Resolution resolution = new Resolution(300);
// 지정된 속성을 사용하여 PNG 장치 생성
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
//특정 페이지를 변환하고 이미지를 스트리밍에 저장
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## 결론

축하합니다! .NET용 Aspose.PDF를 사용하여 페이지의 특정 영역을 DOM(문서 개체 모델)으로 성공적으로 변환했습니다. 결과 이미지는 지정된 디렉터리에 저장됩니다. 이제 프로젝트나 애플리케이션에서 이 이미지를 사용할 수 있습니다.

## FAQ

#### Q: Aspose.PDF for .NET을 사용하여 페이지의 특정 영역을 DOM(문서 개체 모델)으로 변환하는 목적은 무엇입니까?

답변: PDF 페이지의 특정 영역을 DOM(문서 개체 모델)으로 변환하면 PDF 문서 내 콘텐츠의 특정 섹션을 추출하고 조작하는 데 도움이 될 수 있습니다.

#### Q: .NET용 Aspose.PDF는 어떻게 특정 페이지 영역을 DOM으로 쉽게 변환합니까?

A: .NET용 Aspose.PDF는 원하는 페이지 영역을 정의하고, 자르기 영역을 설정하고, 자른 PDF 문서를 스트림에 저장하고, 지정된 페이지 영역을 이미지로 변환하는 단계별 프로세스를 제공합니다.

#### Q: 변환 프로세스를 시작하기 전에 문서 디렉터리를 정의하는 것이 왜 중요한가요?

답변: 문서 디렉터리를 지정하면 PDF 문서와 결과 이미지가 원하는 출력 경로에 올바르게 위치하게 됩니다.

####  Q: 어떻게 되나요?`Document` class in Aspose.PDF for .NET help in the conversion process?

 답:`Document` 클래스를 사용하면 PDF 문서를 열고, 조작하고, 저장할 수 있습니다. 이 경우 PDF 문서를 로드하고 잘린 버전을 만드는 데 사용됩니다.

####  Q: 이 프로그램의 목적은 무엇입니까?`Rectangle` class in the page region conversion process?

 답:`Rectangle` 클래스는 DOM으로 변환하려는 PDF 페이지의 특정 영역 좌표를 정의합니다. 자르기 영역을 정확하게 지정하는 데 도움이 됩니다.

#### Q: 변환 과정에서 페이지의 자르기 영역을 원하는 영역으로 어떻게 설정하나요?

 답:`CropBox` 의 재산`Page` 개체는 페이지의 자르기 영역을 특정 영역을 나타내는 정의된 직사각형으로 설정하는 데 사용됩니다.

#### Q: 변환 프로세스 중에 잘린 PDF 문서는 어떻게 스트림에 저장됩니까?

 A: 잘린 PDF 문서는 다음 폴더에 저장됩니다.`MemoryStream` PDF 콘텐츠를 효율적으로 조작할 수 있는 개체입니다.

####  Q: 어떤 역할을 하나요?`PngDevice` class play in the page region to DOM conversion process?

 답:`PngDevice` 클래스는 잘린 PDF 문서를 PNG와 같은 이미지 형식으로 변환하여 특정 페이지 영역을 시각화하는 데 도움이 됩니다.

#### Q: 변환 프로세스 중에 결과 이미지의 해상도나 기타 속성을 조정할 수 있습니까?

 A: 예. 구성을 통해 결과 이미지의 해상도와 기타 속성을 수정할 수 있습니다.`PngDevice` 페이지를 변환하기 전에 개체를 선택하세요.