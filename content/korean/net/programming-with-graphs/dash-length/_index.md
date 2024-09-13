---
title: 대시 길이
linktitle: 대시 길이
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF에서 라인 대시 패턴을 사용자 지정하는 방법을 단계별 가이드로 알아보세요. 문서에 스타일을 추가하는 데 완벽합니다.
type: docs
weight: 70
url: /ko/net/programming-with-graphs/dash-length/
---
## 소개

다양한 대시 패턴으로 선을 사용자 지정하여 PDF 문서에 창의성을 더하고 싶으신가요? Aspose.PDF for .NET을 사용하면 문서의 필요에 맞게 선 스타일을 쉽게 수정할 수 있습니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서의 선 대시 길이를 조정하는 방법을 살펴보겠습니다. 대시 선이나 점선 패턴을 목표로 하든 이 가이드는 원하는 결과를 얻는 데 필요한 도구와 단계를 제공합니다.

## 필수 조건

튜토리얼을 시작하기 전에 꼭 필요한 몇 가지가 있습니다.

1. .NET용 Aspose.PDF: .NET용 Aspose.PDF가 설치되어 있는지 확인하세요. 아직 설치하지 않았다면 다음에서 다운로드할 수 있습니다.[.NET용 Aspose.PDF](https://releases.aspose.com/pdf/net/).
2. C#에 대한 기본 지식: 이 튜토리얼은 여러분이 C# 프로그래밍에 대한 기본적인 이해가 있다고 가정합니다. C#을 처음 접한다면, 먼저 기본 사항을 되짚어보는 것이 좋습니다.
3. Visual Studio: 모든 IDE를 사용할 수 있지만, 이 가이드에서는 C# 코드를 작성하고 실행하려면 Visual Studio를 사용한다고 가정합니다.
4.  Aspose 계정: 추가 리소스 및 지원을 받으려면 Aspose에 계정이 있는지 확인하세요.[무료 체험](https://releases.aspose.com/) 또는 라이센스를 구매하세요[여기](https://purchase.aspose.com/buy).

## 패키지 가져오기

Aspose.PDF for .NET으로 작업을 시작하려면 관련 네임스페이스를 가져와야 합니다. 방법은 다음과 같습니다.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

이러한 네임스페이스에는 PDF 문서, 도면, 선 작업에 필요한 클래스와 메서드가 포함되어 있습니다.

## 1단계: 프로젝트 설정

코딩을 시작하기 전에 Visual Studio에서 새 C# 프로젝트를 설정합니다. NuGet을 통해 또는 DLL을 수동으로 참조하여 Aspose.PDF for .NET 라이브러리를 프로젝트에 추가합니다. 

## 2단계: 문서 초기화

새 PDF 문서를 만들고 페이지를 추가하여 시작합니다. 이것은 당신이 선을 그릴 캔버스입니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 인스턴스화
Document doc = new Document();

// Document 객체의 pages 컬렉션에 페이지 추가
Page page = doc.Pages.Add();
```

 여기서 우리는 다음을 생성합니다.`Document` 객체를 추가하고 새 객체를 추가합니다.`Page` 그것에. 이것은 당신의 선을 그리는 기초를 마련합니다.

## 3단계: 그리기 개체 만들기

 다음으로, 다음을 생성합니다.`Graph` 그릴 영역을 나타내는 객체입니다. 요구 사항에 따라 치수를 정의합니다.

```csharp
// 특정 치수로 도면 객체를 생성합니다.
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);

// 페이지 인스턴스의 문단 컬렉션에 그리기 개체 추가
page.Paragraphs.Add(canvas);
```

 그만큼`Graph` 객체는 드로잉 요소의 컨테이너 역할을 합니다. 여기서는 너비가 100단위이고 높이는 400단위로 설정되었습니다.

## 4단계: 라인 정의

 이제 생성할 시간입니다.`Line`객체. 선의 시작점과 끝점을 지정하고 스타일을 사용자 정의합니다.

```csharp
// Line 객체 생성
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
```

이 선은 좌표 (100, 100)에서 시작하여 (200, 100)에서 끝납니다. 이러한 좌표를 조정하여 특정 요구 사항에 맞출 수 있습니다.

## 5단계: 선 스타일 사용자 지정

선의 색상과 대시 패턴을 설정합니다. 여기서 선을 돋보이게 만들 수 있습니다.

```csharp
// Line 객체에 대한 색상 설정
line.GraphInfo.Color = Aspose.Pdf.Color.Red;

// 라인 객체에 대한 대시 배열을 지정하세요
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };

// Line 인스턴스에 대한 대시 단계 설정
line.GraphInfo.DashPhase = 1;
```

- `line.GraphInfo.Color`: 선의 색상을 설정합니다. 이 경우에는 빨간색입니다.
- `line.GraphInfo.DashArray` : 대시 패턴을 정의합니다. 여기서,`{ 0, 1, 0 }` 점선 패턴을 나타냅니다.
- `line.GraphInfo.DashPhase`: 대시 패턴의 시작점을 조정합니다.

## 6단계: 도면에 선 추가

 선 스타일을 지정한 후 다음을 추가합니다.`Graph` 물체.

```csharp
// 그리기 개체의 모양 컬렉션에 선 추가
canvas.Shapes.Add(line);
```

이렇게 하면 선이 그림 캔버스에 통합됩니다.

## 7단계: 문서 저장

마지막으로 문서를 지정된 경로에 저장합니다. 여기가 PDF 파일이 생성되는 곳입니다.

```csharp
dataDir = dataDir + "DashLength_out.pdf";

// PDF 문서 저장
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);
```

이 코드 줄은 PDF 문서를 저장하고 파일이 저장된 위치를 나타내는 확인 메시지를 제공합니다.

## 결론

PDF 문서의 선 스타일을 사용자 지정하면 보고서, 프레젠테이션 및 기타 문서에 전문적인 느낌을 더할 수 있습니다. 이 튜토리얼을 따라 Aspose.PDF for .NET을 사용하여 선의 대시 길이를 조정하는 방법을 배웠습니다. 간단한 대시 선이나 더 복잡한 패턴을 만들든 Aspose.PDF는 문서를 돋보이게 하는 데 필요한 유연성을 제공합니다. 다양한 대시 패턴과 색상을 실험하여 필요에 가장 적합한 스타일을 찾으세요.

## 자주 묻는 질문

### .NET용 Aspose.PDF를 어떻게 설치하나요?
 Visual Studio에서 NuGet을 통해 설치하거나 다음에서 다운로드할 수 있습니다.[Aspose의 웹사이트](https://releases.aspose.com/pdf/net/).

### Aspose.PDF for .NET을 무료로 사용할 수 있나요?
 예, Aspose에서는 다음을 제공합니다.[무료 체험](https://releases.aspose.com/) 라이선스를 구매하기 전에 기능을 테스트해 볼 수 있습니다.

### PDF의 줄에 대해 어떤 다른 사용자 정의를 할 수 있나요?
 선 두께, 색상 및 대시 패턴을 조정할 수 있습니다.[선적 서류 비치](https://reference.aspose.com/pdf/net/) 자세한 내용은.

### 문제가 발생하면 어떻게 지원을 받을 수 있나요?
 다음을 통해 지원에 액세스할 수 있습니다.[애스포지 포럼](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF for .NET 라이선스는 어디에서 구매할 수 있나요?
라이센스를 구매할 수 있습니다[여기](https://purchase.aspose.com/buy).