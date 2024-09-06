---
title: 페이지 영역을 DOM으로 변환
linktitle: 페이지 영역을 DOM으로 변환
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하면 PDF 페이지의 특정 영역을 DOM(문서 개체 모델)으로 쉽게 변환할 수 있습니다.
type: docs
weight: 80
url: /ko/net/programming-with-images/convert-page-region-to-dom/
---
이 가이드에서는 Aspose.PDF for .NET을 사용하여 페이지의 특정 영역을 문서 개체 모델(DOM)로 변환하는 방법을 단계별로 안내합니다. 이미 환경을 설정했는지 확인하고 아래 단계를 따르세요.

## 1단계: 문서 디렉토리 정의

시작하기 전에 문서에 대한 올바른 디렉토리를 설정했는지 확인하세요. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 코드에 PDF 문서가 있는 디렉토리 경로를 추가합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 열기

 이 단계에서는 다음을 사용하여 PDF 문서를 엽니다.`Document` Aspose.PDF 클래스. 사용하세요`Document` 생성자를 사용하여 PDF 문서의 경로를 전달합니다.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## 3단계: 페이지 영역 사각형 가져오기

 이 단계에서는 DOM으로 변환하려는 페이지의 특정 영역을 나타내는 사각형을 정의합니다.`Aspose.Pdf.Rectangle` 사각형의 좌표를 정의하는 클래스입니다.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## 4단계: 페이지의 자르기 영역 정의

 사용하세요`CropBox` 의 속성`Page` 페이지의 자르기 상자를 원하는 영역 사각형으로 설정합니다.

```csharp
document.Pages[1].CropBox = pageRect;
```

## 5단계: 잘라낸 PDF 문서를 스트림에 저장

 이 단계에서는 다음을 사용하여 잘린 PDF 문서를 스트림에 저장합니다.`MemoryStream` 수업.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## 6단계: 잘라낸 PDF 문서를 열고 이미지로 변환합니다.

 다음을 사용하여 잘린 PDF 문서를 엽니다.`Document`클래스를 사용하여 이미지로 변환합니다. 300 dpi의 해상도를 사용합니다.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## 7단계: 특정 페이지를 이미지로 변환

 특정 페이지를 이미지로 변환하려면 다음을 사용하세요.`Process` 의 방법`pngDevice` 객체. 이미지 출력 경로를 지정하세요.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### .NET용 Aspose.PDF를 사용하여 페이지 영역을 DOM으로 변환하기 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document document = new Document( dataDir + "AddImage.pdf");
// 특정 페이지 영역의 사각형 가져오기
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
// 원하는 페이지 영역의 사각형에 따라 CropBox 값을 설정합니다.
document.Pages[1].CropBox = pageRect;
// 잘라낸 문서를 스트림에 저장
MemoryStream ms = new MemoryStream();
document.Save(ms);
// 잘라낸 PDF 문서를 열고 이미지로 변환
document = new Document(ms);
// Resolution 객체 생성
Resolution resolution = new Resolution(300);
// 지정된 속성으로 PNG 장치 생성
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// 특정 페이지를 변환하고 이미지를 스트리밍으로 저장합니다.
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 페이지의 특정 영역을 문서 개체 모델(DOM)로 성공적으로 변환했습니다. 결과 이미지는 지정된 디렉토리에 저장됩니다. 이제 프로젝트나 애플리케이션에서 이 이미지를 사용할 수 있습니다.

## 자주 묻는 질문

#### 질문: Aspose.PDF for .NET을 사용하여 페이지의 특정 영역을 DOM(문서 개체 모델)으로 변환하는 목적은 무엇입니까?

답변: PDF 페이지의 특정 영역을 DOM(문서 개체 모델)으로 변환하면 PDF 문서 내에서 특정 콘텐츠 섹션을 추출하고 조작하는 데 도움이 될 수 있습니다.

#### 질문: .NET용 Aspose.PDF는 어떻게 특정 페이지 영역을 DOM으로 변환하나요?

답변: .NET용 Aspose.PDF는 원하는 페이지 영역을 정의하고, 자르기 영역을 설정하고, 자른 PDF 문서를 스트림으로 저장하고, 지정된 페이지 영역을 이미지로 변환하는 단계별 프로세스를 제공합니다.

#### 질문: 변환 과정을 시작하기 전에 문서 디렉토리를 정의하는 것이 중요한 이유는 무엇입니까?

답변: 문서 디렉토리를 지정하면 PDF 문서와 결과 이미지가 원하는 출력 경로에 올바르게 배치됩니다.

####  Q: 어떻게`Document` class in Aspose.PDF for .NET help in the conversion process?

 A: 그`Document` 클래스를 사용하면 PDF 문서를 열고, 조작하고, 저장할 수 있습니다. 이 경우 PDF 문서를 로드하고 잘린 버전을 만드는 데 사용됩니다.

####  Q: 목적은 무엇입니까?`Rectangle` class in the page region conversion process?

 A: 그`Rectangle`클래스는 DOM으로 변환하려는 PDF 페이지의 특정 영역의 좌표를 정의합니다. 자르기 영역을 정확하게 지정하는 데 도움이 됩니다.

#### 질문: 변환 과정에서 페이지의 자르기 영역을 원하는 영역으로 설정하려면 어떻게 해야 합니까?

 A: 그`CropBox` 의 속성`Page` 객체는 페이지의 자르기 영역을 특정 영역을 나타내는 정의된 사각형으로 설정하는 데 사용됩니다.

#### 질문: 변환 과정에서 잘린 PDF 문서는 어떻게 스트림에 저장되나요?

 A: 잘린 PDF 문서는 다음 위치에 저장됩니다.`MemoryStream` PDF 콘텐츠를 효율적으로 조작할 수 있는 객체입니다.

####  Q: 어떤 역할을 하나요?`PngDevice` class play in the page region to DOM conversion process?

 A: 그`PngDevice` 클래스는 잘린 PDF 문서를 PNG와 같은 이미지 형식으로 변환하는 데 도움이 되므로 특정 페이지 영역을 시각화할 수 있습니다.

#### 질문: 변환 과정에서 결과 이미지의 해상도나 다른 속성을 조정할 수 있나요?

 A: 예, 결과 이미지의 해상도 및 기타 속성을 구성하여 수정할 수 있습니다.`PngDevice` 페이지를 변환하기 전에 개체를 선택합니다.