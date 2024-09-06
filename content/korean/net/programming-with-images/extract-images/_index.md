---
title: PDF 파일에서 이미지 추출
linktitle: PDF 파일에서 이미지 추출
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에서 이미지를 쉽게 추출하세요.
type: docs
weight: 120
url: /ko/net/programming-with-images/extract-images/
---
이 가이드에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에서 이미지를 추출하는 방법을 단계별로 안내합니다. 이미 환경을 설정했는지 확인하고 아래 단계를 따르세요.

## 1단계: 문서 디렉토리 정의

시작하기 전에 문서에 대한 올바른 디렉토리를 설정했는지 확인하세요. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 코드에 PDF 문서가 있는 디렉토리 경로를 추가합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: PDF 문서 열기

 이 단계에서는 다음을 사용하여 PDF 문서를 엽니다.`Document` Aspose.PDF 클래스. 사용하세요`Document` 생성자를 사용하여 PDF 문서의 경로를 전달합니다.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## 3단계: 특정 이미지 추출

이 단계에서는 특정 페이지에서 특정 이미지를 추출합니다.`Images` 페이지 모음`s `Resources` 객체를 사용하여 원하는 이미지에 액세스합니다. 아래 예에서 우리는 첫 번째 페이지에서 인덱스 1의 이미지를 추출합니다.

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## 4단계: 추출된 이미지 저장

 추출된 이미지를 파일로 저장하려면 다음을 사용합니다.`Save` 의 방법`xImage` 객체. 출력 경로와 이미지 형식을 지정합니다(이 예에서는 JPEG 형식을 사용합니다).

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## 5단계: 업데이트된 PDF 파일 저장

 업데이트된 PDF 파일을 다음을 사용하여 저장합니다.`Save` 의 방법`pdfDocument` 객체. PDF 파일의 출력 경로를 지정하세요.

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 이미지 추출을 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
// 특정 이미지 추출
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
// 출력 이미지 저장
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
// 업데이트된 PDF 파일을 저장하세요
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF에서 이미지를 성공적으로 추출했습니다. 추출된 이미지는 지정된 디렉토리에 저장되고 업데이트된 PDF 파일도 저장됩니다. 이제 이러한 파일을 특정 요구 사항에 사용할 수 있습니다.

### PDF 파일에서 이미지 추출에 대한 FAQ

#### 질문: Aspose.PDF for .NET을 사용하여 PDF 파일에서 이미지를 추출해야 하는 이유는 무엇입니까?

답변: PDF 파일에서 이미지를 추출하면 보관, 다른 문서에서 이미지 재사용, 콘텐츠 분석 또는 이미지 처리 작업 수행 등 다양한 목적에 유용하게 사용할 수 있습니다.

#### 질문: Aspose.PDF for .NET은 어떻게 PDF 문서에서 이미지를 추출할 수 있게 하나요?

답변: .NET용 Aspose.PDF는 PDF 문서를 열고, 특정 이미지에 액세스하고, 다양한 형식을 사용하여 이미지 파일로 저장하는 단계별 프로세스를 제공합니다.

####  Q: 어떤 역할을 하나요?`Document` class in Aspose.PDF for .NET play in image extraction?

 A: 그`Document` 클래스는 PDF 문서를 로드하고 조작하는 데 사용됩니다. 이 맥락에서 이미지를 추출할 PDF 문서를 여는 데 도움이 됩니다.

#### 질문: PDF 페이지에서 추출하고 싶은 특정 이미지를 어떻게 지정합니까?

 A: 다음을 사용할 수 있습니다.`Images` 페이지의 컬렉션`Resources` 객체는 인덱스를 통해 원하는 이미지에 액세스합니다. 예를 들어,`pdfDocument.Pages[1].Resources.Images[1]` 첫 번째 페이지의 첫 번째 이미지에 접근합니다.

#### 질문: PDF 문서의 모든 페이지에서 이미지를 추출할 수 있나요?

대답: 네, 원하는 페이지 인덱스와 추출할 이미지 인덱스를 지정하면 PDF 문서의 모든 페이지에서 이미지를 추출할 수 있습니다.

#### 질문: 추출한 이미지는 어떤 이미지 형식으로 저장할 수 있나요?

 A: 추출된 이미지는 다양한 포맷으로 저장이 가능합니다.`ImageFormat` JPEG, PNG, BMP 등과 같은 열거형.

#### 질문: 추출된 이미지를 파일로 저장한 후 어떻게 사용할 수 있나요?

A: 추출된 이미지는 다른 이미지 파일과 마찬가지로 활용할 수 있습니다. 다른 문서나 프로젝트에 보거나, 편집하거나, 공유하거나 통합할 수 있습니다.

#### 질문: PDF에서 이미지를 추출하면 원본 PDF 문서의 레이아웃이나 내용에 영향을 미칩니까?

A: 아니요, PDF에서 이미지를 추출해도 원래 PDF 문서의 레이아웃이나 내용에는 영향을 미치지 않습니다. 추출된 이미지만 영향을 받습니다.

#### 질문: 단일 프로세스로 여러 페이지에서 여러 이미지를 추출할 수 있나요?

대답: 네, 다른 페이지 인덱스를 반복하여 여러 페이지에서 이미지를 추출하는 동일한 프로세스를 사용할 수 있습니다.