---
title: 기본 글꼴 이름 설정
linktitle: 기본 글꼴 이름 설정
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF를 이미지로 렌더링할 때 기본 글꼴 이름을 설정하는 방법을 알아보세요. 이 가이드는 필수 조건, 단계별 지침 및 FAQ를 다룹니다.
type: docs
weight: 270
url: /ko/net/document-conversion/set-default-font-name/
---
## 소개

PDF 문서를 이미지로 렌더링하려고 했지만 글꼴이 제대로 보이지 않는 것을 발견한 적이 있습니까? 텍스트가 왜곡되어 보이거나 원래 글꼴이 지원되지 않는 것일 수 있습니다. 이때 기본 글꼴을 설정하면 문제가 해결될 수 있습니다! Aspose.PDF for .NET을 사용하면 PDF 렌더링을 위한 기본 글꼴을 쉽게 설정하여 문서가 선명하고 전문적으로 보이도록 할 수 있습니다. 이 튜토리얼에서는 PDF를 이미지로 렌더링할 때 기본 글꼴 이름을 설정하는 방법을 안내합니다. 이 가이드를 마치면 앞으로 닥칠 모든 PDF 렌더링 과제를 해결할 수 있는 기술을 갖추게 될 것입니다. 준비되셨나요? 시작해 볼까요!

## 필수 조건

코드로 들어가기 전에 먼저 준비해야 할 몇 가지 사항이 있습니다.

- .NET용 Aspose.PDF: 이 강력한 라이브러리는 PDF 문서를 조작하는 데 사용할 것입니다. 다음에서 다운로드할 수 있습니다.[Aspose 웹사이트](https://releases.aspose.com/pdf/net/).
- Visual Studio: 컴퓨터에 Visual Studio가 설치되어 있는지 확인하세요. 이것이 우리의 개발 환경이 될 것입니다.
- .NET Framework: .NET Framework가 설치되어 있는지 확인하세요. Aspose.PDF for .NET은 다양한 버전을 지원하므로 설명서를 확인하여 필요에 맞게 선택하세요.
- PDF 문서: 작업할 샘플 PDF 문서가 필요합니다. 없는 경우 간단한 PDF를 만들거나 온라인에서 샘플을 다운로드하세요.

모든 것을 설정했으면 이제 코딩을 시작할 준비가 되었습니다!

## 패키지 가져오기

코드로 들어가기 전에 필요한 패키지를 가져오는 것이 필수적입니다. 이렇게 하면 프로젝트에 필요한 모든 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using Aspose.Pdf.Devices;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

이러한 가져오기는 PDF 조작, 이미지 렌더링, 파일 스트림 작업을 처리하는 데 필요한 네임스페이스를 가져오기 때문에 매우 중요합니다.

## 1단계: 프로젝트 및 문서 경로 설정

우선, PDF 문서가 있는 디렉토리 경로를 설정해 보겠습니다. 이것은 PDF 파일을 조작하는 시작점이 될 것입니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 여기,`dataDir` PDF 문서가 있는 디렉토리입니다. 다음을 반드시 바꾸십시오.`"YOUR DOCUMENT DIRECTORY"` 문서의 실제 경로와 함께. 이것은 코드가 PDF 파일을 어디에서 가져올지 알아야 하기 때문에 필수적입니다.

## 2단계: PDF 문서 로드

이제 문서 경로가 있으니 다음 단계는 PDF 문서를 메모리에 로드하여 작업을 시작하는 것입니다.

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
```
 우리는 사용합니다`Document` Aspose.PDF 라이브러리의 클래스를 사용하여 PDF 파일을 로드합니다. 이 클래스는 PDF 문서에서 작업하기 위한 다양한 메서드와 속성을 제공합니다.`"input.pdf"` PDF의 실제 파일 이름으로 대체해야 합니다. 이 파일은 렌더링을 위한 입력으로 사용됩니다.

## 3단계: 출력을 위한 이미지 스트림 생성

문서가 로드되면 렌더링된 이미지를 저장할 스트림을 설정해야 합니다. 여기에 출력 이미지가 저장됩니다.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
```
 그만큼`FileStream`클래스는 렌더링된 이미지가 저장될 새 파일을 만드는 데 사용됩니다. 이 예에서 우리는 이미지를 다음과 같이 저장합니다.`"SetDefaultFontName.png"` . 그`FileMode.Create` 새로운 파일이 생성되는지, 아니면 기존 파일이 덮어쓰이는지 확인합니다.

## 4단계: 이미지 해상도 설정

PDF를 이미지로 렌더링하기 전에 해상도를 설정하는 것이 중요합니다. 이는 출력 이미지의 품질과 선명도를 결정합니다.

```csharp
Resolution resolution = new Resolution(300);
```
 그만큼`Resolution` 클래스는 출력 이미지의 해상도를 설정합니다. 여기서는 고품질 이미지의 표준인 300 DPI(인치당 도트 수)의 해상도를 선택했습니다. 이렇게 하면 PDF의 텍스트와 그래픽이 세부 사항을 잃지 않고 선명하게 렌더링됩니다.

## 5단계: PNG 장치 구성

다음으로, PDF를 PNG 이미지로 렌더링하는 장치를 구성해야 합니다.

```csharp
PngDevice pngDevice = new PngDevice(resolution);
```
 그만큼`PngDevice` 클래스는 PDF 문서를 PNG 이미지로 렌더링하는 역할을 합니다.`resolution` 이에 반대하는 경우 지정된 DPI로 이미지가 생성되도록 합니다.

## 6단계: 기본 글꼴 이름 설정

중요한 부분은 기본 글꼴 이름을 설정하는 것입니다. 이것은 PDF의 원래 글꼴을 사용할 수 없는 경우 대체 글꼴이 됩니다.

```csharp
RenderingOptions ro = new RenderingOptions();
ro.DefaultFontName = "Arial";
pngDevice.RenderingOptions = ro;
```
 우리는 인스턴스를 생성합니다`RenderingOptions` 그리고 그것을 설정`DefaultFontName` 재산에`"Arial"`. 즉, PDF의 원래 글꼴을 찾을 수 없는 경우 대신 Arial이 사용됩니다. 이 단계는 렌더링된 이미지에서 텍스트의 가독성과 모양을 유지하는 데 중요합니다.

## 7단계: PDF 페이지를 이미지로 렌더링

마지막으로 모든 것이 설정되었으므로 이제 PDF 문서의 첫 페이지를 이미지로 렌더링하고 앞서 생성한 파일 스트림을 사용하여 저장할 수 있습니다.

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```
 그만큼`Process` 의 방법`PngDevice` 클래스는 지정된 PDF 페이지(이 경우 첫 번째 페이지)를 이미지로 렌더링하는 데 사용됩니다. 그런 다음 출력이 저장됩니다.`imageStream`이 단계에서는 PDF 페이지를 지정된 해상도와 기본 글꼴을 사용하여 PNG 이미지로 변환합니다.

## 8단계: 파일 스트림 및 PDF 문서 닫기

이미지를 렌더링한 후에는 파일 스트림과 PDF 문서를 닫아 리소스를 확보하는 것이 중요합니다.

```csharp
imageStream.Close();
pdfDocument.Dispose();
```
닫기`imageStream` 파일이 제대로 저장되고 데이터가 손실되지 않도록 합니다.`pdfDocument` 메모리와 리소스를 확보하여 잠재적인 메모리 누수를 방지합니다.

## 결론

이제 다 됐습니다! 몇 줄의 코드만 있으면 Aspose.PDF for .NET을 사용하여 PDF를 이미지로 렌더링할 때 기본 글꼴 이름을 설정하는 방법을 배웠습니다. 이 기술은 특히 지원되지 않는 글꼴이 포함된 PDF를 처리할 때 매우 편리합니다. 기본 글꼴을 설정하면 렌더링된 이미지가 가독성과 전문적인 모양을 유지하도록 할 수 있습니다.

## 자주 묻는 질문

### 지정된 기본 글꼴이 시스템에 설치되어 있지 않으면 어떻게 되나요?
 기본 글꼴이 지정된 경우`RenderingOptions` 시스템에 설치되어 있지 않으면 Aspose.PDF는 시스템에서 정의한 대체 글꼴을 사용합니다.

### 기본 글꼴로 Arial 외의 다른 글꼴을 사용할 수 있나요?
물론입니다! 시스템에 설치된 모든 글꼴을 기본 글꼴로 설정할 수 있습니다.

### PDF의 여러 페이지를 한 번에 이미지로 렌더링할 수 있나요?
네, PDF 페이지를 반복하고 동일한 프로세스를 사용하여 각 페이지를 개별적으로 렌더링할 수 있습니다.

### 고해상도를 설정하면 PDF 렌더링 성능에 영향을 미칩니까?
네, 해상도가 높을수록 이미지 파일 크기가 커지고 렌더링 시간도 길어지지만, 이미지가 더 선명해집니다.

### PNG 외에 다른 이미지 형식으로 PDF를 렌더링할 수 있나요?
네, Aspose.PDF는 JPEG, BMP, TIFF 등 다양한 이미지 포맷으로의 렌더링을 지원합니다.