---
title: PDF 파일에서 보이지 않는 주석
linktitle: PDF 파일에서 보이지 않는 주석
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 보이지 않는 주석을 추가하는 방법을 알아보세요. 이 강력한 기능을 마스터하기 위한 단계별 가이드를 따르세요.
type: docs
weight: 100
url: /ko/net/annotations/invisibleannotation/
---
## 소개

PDF 파일에 보이지 않지만 효과적인 주석을 추가하고 싶었던 적이 있나요? 인쇄 목적으로 메모를 추가하거나 문서에 숨겨진 메시지를 남기고 싶을 때 보이지 않는 주석은 매우 유용할 수 있습니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 보이지 않는 주석을 만드는 과정을 안내합니다. 이 강력한 .NET 라이브러리를 사용하면 PDF 문서를 쉽게 조작할 수 있으며, 이 가이드를 마칠 때쯤이면 전문가처럼 PDF 파일에 보이지 않는 주석을 추가하는 기술을 터득하게 될 것입니다!

## 필수 조건

단계별로 들어가기 전에 먼저 필요한 모든 것이 있는지 확인해 보겠습니다.

- .NET용 Aspose.PDF: Aspose.PDF 라이브러리가 설치되어 있는지 확인하세요. 여기에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
- .NET 개발 환경: Visual Studio나 기타 선호하는 .NET 개발 환경이 설치되어 있어야 합니다.
- C#에 대한 기본 지식: C# 구문과 프로그래밍에 대한 이해가 필수적입니다.
-  유효한 라이센스 또는 무료 평가판: 라이센스가 없으면 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/) 또는 무료 체험판을 이용하세요.

## 패키지 가져오기

시작하려면 필요한 네임스페이스를 가져와야 합니다. 이러한 네임스페이스는 Aspose.PDF for .NET에서 PDF 문서로 작업하는 데 필요한 클래스와 메서드에 대한 액세스를 제공합니다.

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using System;
```

이제 필수 구성 요소를 살펴보았으니, PDF 문서에 보이지 않는 주석을 추가하는 과정을 관리하기 쉬운 단계로 나누어 보겠습니다.

## 1단계: 문서 디렉토리 설정

먼저, 입력 PDF 파일이 있는 문서 디렉토리 경로를 지정해야 합니다. 이 경로는 PDF 문서를 프로그램에 로드하는 데 사용됩니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 
 그만큼`dataDir`변수는 PDF 파일이 저장된 디렉토리 경로를 보유합니다. 다음을 반드시 바꾸십시오.`"YOUR DOCUMENT DIRECTORY"` 컴퓨터의 실제 경로와 일치합니다.

## 2단계: PDF 문서 로드

다음으로, PDF 문서를 우리 프로그램에 로드합니다. 이 문서는 우리가 보이지 않는 주석을 추가할 문서입니다.

```csharp
// 문서 열기
Document doc = new Document(dataDir + "input.pdf");
```
 
 여기서 우리는 다음을 사용합니다.`Document` Aspose.PDF 라이브러리의 클래스를 사용하여 PDF 파일을 엽니다.`input.pdf`. 이전 단계에서 지정한 디렉토리에 이 파일이 있는지 확인하세요.

## 3단계: 보이지 않는 주석 만들기

 이제 흥미로운 부분인 보이지 않는 주석을 만드는 단계가 시작됩니다. 우리는 다음을 사용할 것입니다.`FreeTextAnnotation` PDF 문서의 첫 페이지에 자유 텍스트 주석을 추가하는 클래스입니다.

```csharp
FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

-  우리는 새로운 것을 창조합니다`FreeTextAnnotation` 그리고 페이지를 지정하세요 (`doc.Pages[1]` ) 추가해야 할 곳입니다.`Rectangle` 클래스는 주석이 배치될 페이지의 영역을 정의합니다.
-  그만큼`DefaultAppearance` 클래스는 주석의 글꼴, 글꼴 크기, 색상을 설정하는 데 사용됩니다. 이 예에서 우리는 "Helvetica" 글꼴, 크기 16, 빨간색을 선택했습니다.
-  그만큼`Contents`속성은 주석의 텍스트를 보유하며 여기서는 다음과 같이 설정됩니다.`"ABCDEFG"`.
-  그만큼`Characteristics.Border` 속성은 주석의 테두리 색상을 정의하며, 역시 빨간색으로 설정됩니다.
-  그만큼`Flags` 속성에는 다음이 포함됩니다`AnnotationFlags.Print` 문서를 인쇄할 때 주석이 보이도록 하려면`AnnotationFlags.NoView` 일반적으로 볼 때는 보이지 않게 하세요.
-  마지막으로 PDF 문서의 첫 페이지에 주석을 추가합니다.`Annotations.Add` 방법.

## 4단계: 업데이트된 PDF 문서 저장

주석이 성공적으로 추가되면 다음 단계는 업데이트된 PDF 문서를 저장하는 것입니다.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
// 출력 파일 저장
doc.Save(dataDir);
```

 우리는 수정합니다`dataDir` 출력 파일 이름을 지정하는 변수`"InvisibleAnnotation_out.pdf"` . 그`Save` 그러면 이 방법은 보이지 않는 주석이 포함된 업데이트된 PDF 문서를 지정된 디렉토리에 저장합니다.

## 5단계: 프로세스 완료 확인

마지막으로, 프로세스가 성공적으로 완료되었다는 확인을 제공하는 것이 항상 좋은 관행입니다. 이 목적을 위해 간단한 콘솔 출력을 추가하겠습니다.

```csharp
Console.WriteLine("\nAnnotation invisible successfully.\nFile saved at " + dataDir);
```

이 줄은 콘솔에 확인 메시지를 출력하여, 보이지 않는 주석이 성공적으로 추가되었음을 알리고 저장된 파일의 위치를 나타냅니다.

## 결론

이제 아시죠! Aspose.PDF for .NET을 사용하여 PDF 파일에 보이지 않는 주석을 성공적으로 추가했습니다. 이 튜토리얼에서는 환경 설정부터 최종 문서 저장까지 각 단계를 안내해 드렸습니다. 숨겨진 메시지를 추가하든 인쇄 목적으로 주석을 추가하든 보이지 않는 주석은 Aspose.PDF for .NET을 사용하여 쉽게 구현할 수 있는 강력한 기능입니다. 즐거운 코딩 되세요!

## 자주 묻는 질문

### 주석을 다시 보이게 할 수 있나요?  
 네, 제거하면`AnnotationFlags.NoView` 플래그를 사용하면 일반 보기 중에 주석이 표시되도록 할 수 있습니다.

### Aspose.PDF를 사용하여 어떤 다른 유형의 주석을 추가할 수 있나요?  
Aspose.PDF는 텍스트, 링크, 강조 표시, 스탬프 주석 등 다양한 주석을 지원합니다.

### 주석을 추가한 후에 수정할 수 있나요?  
네, 주석이 문서에 추가된 후에도 주석의 속성을 수정할 수 있습니다.

### 동일한 문서에 여러 개의 주석을 추가하려면 어떻게 해야 하나요?  
추가하려는 각 주석에 대해 주석 생성 프로세스를 반복하기만 하면 됩니다. 각 주석은 동일하거나 다른 페이지에 추가할 수 있습니다.

### PDF 문서가 여러 페이지인 경우는 어떻게 되나요?  
 주석을 생성할 때 페이지 번호를 변경하여 지정할 수 있습니다.`doc.Pages[1]` 원하는 페이지 인덱스로 이동합니다.