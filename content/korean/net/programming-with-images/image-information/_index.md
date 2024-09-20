---
title: PDF 파일의 이미지 정보
linktitle: PDF 파일의 이미지 정보
second_title: .NET API 참조를 위한 Aspose.PDF
description: 포괄적인 단계별 가이드를 통해 Aspose.PDF for .NET을 사용하여 PDF에서 이미지 정보를 추출하는 방법을 알아보세요.
type: docs
weight: 160
url: /ko/net/programming-with-images/image-information/
---
## 소개

PDF 파일은 요즘 어디에나 있습니다. 사실상 모든 전문 및 개인 문서가 어느 시점에서 이 형식으로 변환됩니다. 보고서, 브로셔 또는 전자책이든 이러한 파일을 프로그래밍 방식으로 상호 작용하는 방법을 이해하면 수많은 가능성이 제공됩니다. 일반적인 요구 사항 중 하나는 PDF 파일에서 이미지 정보를 추출하는 것입니다. 이 가이드에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에 포함된 이미지에 대한 중요한 세부 정보를 추출하는 방법을 살펴보겠습니다.

## 필수 조건

코딩의 핵심을 살펴보기 전에 꼭 갖춰야 할 몇 가지 전제 조건이 있습니다.

1. 개발 환경: .NET 개발 환경을 설정해야 합니다. 이는 Visual Studio 또는 기타 .NET 호환 IDE일 수 있습니다.
2.  Aspose.PDF 라이브러리: Aspose.PDF 라이브러리에 액세스할 수 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Aspose 웹사이트](https://releases.aspose.com/pdf/net/). 
3. 기본 C# 지식: C# 및 객체 지향 프로그래밍 개념에 익숙하다면 튜토리얼을 손쉽게 따라갈 수 있습니다.
4. PDF 문서: 코드를 테스트하기 위해 이미지가 포함된 샘플 PDF 문서를 준비해 두세요. 

## 패키지 가져오기

Aspose.PDF 라이브러리 사용을 시작하려면 필요한 네임스페이스를 C# 파일로 가져와야 합니다. 간단한 요약은 다음과 같습니다.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

이러한 네임스페이스는 PDF 파일을 조작하고 이미지 데이터를 추출하는 데 필요한 클래스와 메서드에 대한 액세스를 제공합니다.

이제 모든 것을 설정했으니, 이것을 관리 가능한 단계로 나눌 차례입니다. PDF 문서를 로드하고, 각 페이지를 살펴보고, 문서의 각 이미지의 크기와 해상도를 추출하는 C# 프로그램을 작성하겠습니다.

## 1단계: 문서 초기화

 이 단계에서는 PDF 파일의 경로를 사용하여 PDF 문서를 초기화합니다. 다음을 바꿔야 합니다.`"YOUR DOCUMENT DIRECTORY"` PDF 파일이 위치한 실제 경로를 포함합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 원본 PDF 파일을 로드합니다
Document doc = new Document(dataDir + "ImageInformation.pdf");
```
 우리는 만듭니다`Document` 지정된 디렉토리에서 PDF를 로드하는 객체입니다. 이를 통해 파일의 내용을 작업할 수 있습니다.

## 2단계: 기본 해상도 설정 및 데이터 구조 초기화

다음으로, 계산에 유용한 이미지의 기본 해상도를 설정합니다. 또한 이미지 이름을 보관할 배열과 그래픽 상태를 관리할 스택도 준비합니다.

```csharp
// 이미지의 기본 해상도를 정의합니다
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// 이미지 이름을 보관할 배열 목록 객체를 정의합니다.
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```
 그만큼`defaultResolution` 변수는 이미지의 해상도를 올바르게 계산하는 데 도움이 됩니다.`graphicsState`스택은 변환 연산자를 만났을 때 문서의 현재 그래픽 상태를 저장하는 수단으로 사용됩니다.

## 3단계: 페이지의 각 연산자 처리

이제 문서의 첫 페이지에 있는 모든 연산자를 반복합니다. 여기서 힘든 일이 일어납니다. 

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // 프로세스 운영자...
}
```
PDF 파일의 각 연산자는 렌더러에게 이미지를 포함한 그래픽 요소를 관리하는 방법을 알려주는 명령입니다.

## 4단계: GSave/GRestore 연산자 처리

루프 내부에서 그래픽 저장 및 복원 명령을 처리하여 그래픽 상태에서 변경된 사항을 추적합니다.

```csharp
if (opSaveState != null) 
{
    // 이전 상태 저장
    graphicsState.Push(((Matrix)graphicsState.Peek()).Clone());
} 
else if (opRestoreState != null) 
{
    // 이전 상태 복원
    graphicsState.Pop();
}
```
`GSave` 현재 그래픽 상태를 저장하는 동시에`GRestore` 마지막으로 저장된 상태를 복원하여 이미지를 처리할 때 모든 변환을 되돌릴 수 있습니다.

## 5단계: 변환 행렬 관리

다음으로, 이미지에 변환을 적용할 때 변환 행렬의 연결을 처리합니다.

```csharp
else if (opCtm != null) 
{
    Matrix cm = new Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);
    
    ((Matrix)graphicsState.Peek()).Multiply(cm);
    continue;
}
```
변환 행렬이 적용되면 그래픽 상태에 저장된 현재 행렬과 이를 곱하여 이미지에 적용된 크기 조정이나 이동을 추적할 수 있습니다.

## 6단계: 이미지 정보 추출

마지막으로, 이미지의 그리기 연산자를 처리하고 치수와 해상도와 같은 필요한 정보를 추출합니다.

```csharp
else if (opDo != null) 
{
    // 객체를 그리는 Do 연산자를 처리합니다.
    if (imageNames.Contains(opDo.Name)) 
    {
        Matrix lastCTM = (Matrix)graphicsState.Peek();
        XImage image = doc.Pages[1].Resources.Images[opDo.Name];
        double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
        double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
        double originalWidth = image.Width;
        double originalHeight = image.Height;
        
        double resHorizontal = originalWidth * defaultResolution / scaledWidth;
        double resVertical = originalHeight * defaultResolution / scaledHeight;
        
        // 정보를 출력하다
        Console.Out.WriteLine(string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
                         opDo.Name, scaledWidth, scaledHeight, resHorizontal, resVertical));
    }
}
```
여기서 우리는 연산자가 이미지를 그리는 것을 담당하는지 확인합니다. 그렇다면, 우리는 해당 XImage 객체를 얻고, 그 크기 조정된 치수와 해상도를 계산하고, 필요한 정보를 인쇄합니다.

## 결론

축하합니다! 방금 Aspose.PDF for .NET을 사용하여 PDF 파일에서 이미지 정보를 추출하는 방법에 대한 작동 예제를 만들었습니다. 이 기능은 보고, 데이터 추출 또는 사용자 지정 PDF 뷰어와 같은 다양한 애플리케이션을 위해 PDF 문서를 분석하거나 조작해야 하는 개발자에게 매우 유용할 수 있습니다. 


## 자주 묻는 질문

### Aspose.PDF 라이브러리란 무엇인가요?
Aspose.PDF 라이브러리는 .NET 애플리케이션에서 PDF 파일을 만들고, 조작하고, 변환하는 강력한 도구입니다.

### 도서관을 무료로 이용할 수 있나요?
 네, Aspose는 무료 체험판을 제공합니다. 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).

### 어떤 유형의 이미지 형식을 추출할 수 있나요?
라이브러리는 PDF에 포함되어 있는 JPEG, PNG, TIFF 등 다양한 이미지 형식을 지원합니다.

### Aspose는 상업적 목적으로 사용되나요?
 네, Aspose 제품을 상업적으로 사용할 수 있습니다. 라이선스에 대해서는 다음을 방문하세요.[구매 페이지](https://purchase.aspose.com/buy).

### Aspose에 대한 지원을 받으려면 어떻게 해야 하나요?
 지원 포럼에 접속할 수 있습니다[여기](https://forum.aspose.com/c/pdf/10).