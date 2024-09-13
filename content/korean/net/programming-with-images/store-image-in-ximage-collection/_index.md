---
title: XImage 컬렉션에 이미지 저장
linktitle: XImage 컬렉션에 이미지 저장
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 단계별 가이드를 통해 .NET용 Aspose.PDF를 사용하여 XImage 컬렉션에 이미지를 저장하는 방법을 알아보세요.
type: docs
weight: 290
url: /ko/net/programming-with-images/store-image-in-ximage-collection/
---
## 소개

오늘날의 디지털 시대에는 많은 애플리케이션에 문서를 프로그래밍 방식으로 처리하고 조작하는 것이 필수적입니다. Aspose.PDF for .NET은 개발자가 PDF 파일을 손쉽게 작업할 수 있도록 지원하여 워크플로를 개선하고 동적 콘텐츠를 만들 수 있도록 합니다. 이 가이드에서는 XImage 컬렉션에 이미지를 저장하는 프로세스를 자세히 살펴보겠습니다. 이 기능은 PDF에 직접 비주얼을 임베드할 수 있는 중요한 기능입니다. 멋진 콘텐츠를 만드는 여정을 시작할 준비가 되셨나요?

## 필수 조건

코드와 프로세스를 자세히 살펴보기 전에 몇 가지 사항이 준비되었는지 확인해야 합니다.

- .NET 환경: 컴퓨터에 .NET Framework가 설치되어 있어야 합니다. 프로젝트 요구 사항에 따라 적절한 버전을 선택하세요.
- .NET용 Aspose.PDF: Aspose.PDF 라이브러리가 있는지 확인하세요. 여기에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/) 또는 무료 체험판으로 시작하세요[여기](https://releases.aspose.com/).
- 이미지 파일: PDF에 저장하려는 이미지 파일(JPG 또는 PNG 등)도 필요합니다. 이 예에서는 "aspose-logo.jpg"라는 파일을 사용하겠습니다.
- C#에 대한 기본적인 이해: C# 프로그래밍에 익숙하면 원활하게 따라갈 수 있습니다.

## 패키지 가져오기

Aspose.PDF for .NET을 사용하려면 필요한 네임스페이스를 가져와야 합니다. 이 단계는 라이브러리에서 제공하는 모든 기능을 활용하기 위한 기반을 마련합니다.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Operators;
```

이러한 네임스페이스를 가져오면 Aspose.PDF에서 문서 생성, 이미지 처리 등 다양한 기능을 사용할 수 있습니다.

이를 관리하기 쉬운 단계로 나누어서 더 쉽게 따라할 수 있도록 하겠습니다.

## 1단계: 문서 디렉토리 설정

가장 먼저 해야 할 일은 무엇입니까? 문서를 어디에 저장할지 정의하세요. 문서 디렉토리 경로를 보관하는 변수를 설정해야 합니다. PDF가 저장되는 위치는 여기입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // 실제 문서 디렉토리로 바꾸세요.
```

## 2단계: 문서 초기화

이제 새로운 PDF 문서를 만들 시간입니다. 이 단계에서 PDF가 살아납니다. 

```csharp
Aspose.Pdf.Document document = new Document();
```

여기서는 캔버스 역할을 할 새로운 Document 객체를 인스턴스화하고 있습니다.

## 3단계: 새 페이지 추가

모든 걸작에는 캔버스가 필요하죠? 우리의 경우, 문서 내에서 작업할 페이지가 필요합니다.

```csharp
document.Pages.Add();
Page page = document.Pages[1]; // 첫 번째 페이지를 받으세요.
```

우리는 문서에 새 페이지를 추가하고 있습니다. 이제 이 페이지에서 작업하겠습니다.

## 4단계: 이미지 파일 로드

다음으로, 이미지를 프로그램에 로드해야 합니다. 이 단계는 책을 열어서 읽는 것과 매우 비슷합니다. 사용하기 전에 콘텐츠에 액세스해야 합니다.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open))
{
```

이 줄은 이미지 파일을 스트림으로 열어서 PDF에 이미지 파일을 조작하고 내장할 수 있게 해줍니다.

## 5단계: 페이지 리소스에 이미지 추가

이제 이미지를 준비했으니 페이지 리소스에 추가할 차례입니다. 기본적으로 PDF에 "안녕하세요, 기억해두셨으면 하는 멋진 이미지가 있어요!"라고 말하는 것입니다.

```csharp
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

 이 코드는 PDF에 이미지를 추가하고 이를 다음에 할당하는 힘든 작업을 수행합니다.`XImage` 나중에 참조할 수 있는 변수입니다.

## 6단계: 이미지 그리기 준비

이제 재밌는 부분이 나옵니다. 페이지에 이미지를 배치하는 것입니다. 이미지가 원하는 위치에 정확히 배치되도록 좌표를 설정해야 합니다.

```csharp
page.Contents.Add(new GSave());
```

이 줄은 나중에 복원하기 위해 그래픽 상태를 저장합니다. 아무것도 변경하기 전에 어떻게 설정되어 있는지 스냅샷을 찍는 것과 같습니다.

## 7단계: 이미지 위치 및 크기 정의

이제 이미지를 얼마나 크고 어디에 배치할지 정의하세요.

```csharp
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
```

이 코드 블록은 이미지가 들어갈 사각형의 크기를 설정하여 페이지에 이미지를 배치하는 데 필요한 공간을 제공합니다.

## 8단계: 변환 행렬 만들기 

이미지가 배치되는 방식을 제어하기 위해 변환 행렬을 정의합니다. 이는 이미지가 대상 좌표에 나타나는 방식을 제어합니다.

```csharp
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

여행을 떠나기 전에 지도를 그리는 것으로 생각해보세요. 이는 이미지가 페이지에 어떻게 표시될지 결정하는 데 도움이 됩니다.

## 9단계: 페이지에 이미지 배치

이제 PDF에 이미지를 어디에 넣을지 알려줄 차례입니다.

```csharp
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
```

여기서는 방금 설정한 매트릭스에 따라 이미지를 실제로 그리는 명령을 PDF의 콘텐츠 스트림에 추가합니다.

## 10단계: 문서 저장

마침내 우리는 걸작을 구할 수 있습니다! 이것은 당신의 모든 노고가 실질적인 결과물로 합쳐지는 순간입니다.

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Aspose.PDF에 제공된 파일 이름으로 문서를 저장하라고 했습니다. 이 코드를 실행하면 지정된 디렉토리에서 새로 만든 PDF 파일을 찾을 수 있으며, 내장된 이미지도 함께 제공됩니다.

## 결론

이제 아시겠죠! Aspose.PDF for .NET을 사용하여 XImage 컬렉션에 이미지를 포인트별로 저장하는 방법을 배웠습니다. 코드가 형성되고 유용한 것을 생성하는 것을 보는 것은 만족스럽지 않나요? 애플리케이션을 빌드하든 보고서를 자동화하려는 경우 이 가이드는 훌륭한 기초 자료가 됩니다. Aspose.PDF의 힘은 이 작업 외에도 여러 가지 작업을 도울 수 있으므로 계속 탐색하세요!

## 자주 묻는 질문

### Aspose.PDF의 이미지에는 어떤 파일 형식이 지원되나요?
Aspose.PDF는 JPG, PNG, BMP, GIF 등 다양한 이미지 형식을 지원합니다.

### PDF에 이미지 크기를 추가할 때 크기를 변경할 수 있나요?
네, 사각형에 정의된 좌표를 조정하면 PDF에 표시되는 이미지의 크기를 변경할 수 있습니다.

### Aspose.PDF를 사용하려면 라이선스가 필요합니까?
 Aspose는 무료 체험판과 다양한 구매 옵션을 제공합니다. 찾을 수 있습니다[여기](https://purchase.aspose.com/buy).

### 문제가 발생하면 어떻게 지원을 받을 수 있나요?
 Aspose 커뮤니티에서 도움을 받을 수 있습니다.[여기](https://forum.aspose.com/c/pdf/10).

### PDF에 추가된 이미지에 압축을 적용할 수 있는 방법이 있나요?
네, PDF에 이미지를 추가할 때 이미지 필터 유형을 지정하여 Flate와 같은 압축 방법을 사용할 수 있습니다.