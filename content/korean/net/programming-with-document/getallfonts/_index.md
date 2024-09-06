---
title: PDF 파일에 모든 글꼴 가져오기
linktitle: PDF 파일에 모든 글꼴 가져오기
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 단계별 가이드와 예제 코드를 통해 Aspose.PDF for .NET을 사용하여 PDF 파일에서 사용된 모든 글꼴을 프로그래밍 방식으로 가져오는 방법을 알아보세요.
type: docs
weight: 160
url: /ko/net/programming-with-document/getallfonts/
---
Aspose.PDF for .NET은 개발자가 PDF 파일을 프로그래밍 방식으로 작업할 수 있도록 하는 강력한 라이브러리입니다. 제공하는 기능 중 하나는 PDF 파일에서 사용된 모든 글꼴을 가져오는 기능입니다. 이는 PDF 파일의 글꼴을 프로그래밍 방식으로 분석하거나 조작해야 하는 경우 유용할 수 있습니다.

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에 사용된 모든 글꼴을 가져오는 방법을 설명합니다. 이를 수행하는 방법에 대한 단계별 가이드와 예제 소스 코드를 제공합니다.

## 1단계: 새 C# 콘솔 애플리케이션 만들기
시작하려면 Visual Studio에서 새 C# 콘솔 애플리케이션을 만듭니다. 원하는 이름을 지정할 수 있습니다. 프로젝트가 생성되면 .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가해야 합니다.

## 2단계: Aspose.PDF 네임스페이스 가져오기
C# 파일의 맨 위에 다음 코드 줄을 추가하여 Aspose.PDF 네임스페이스를 가져옵니다.

```csharp
using Aspose.Pdf;
```

## 3단계: PDF 문서 로드
글꼴을 가져오려는 PDF 문서를 로드합니다.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 4단계: 모든 글꼴 가져오기
PDF 문서에 사용된 모든 글꼴을 가져옵니다.

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## 5단계: 모든 글꼴 인쇄
PDF 문서에 사용된 모든 글꼴을 인쇄합니다.

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### .NET용 Aspose.PDF를 사용하여 모든 글꼴 가져오기에 대한 예제 소스 코드
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## 결론
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 사용된 모든 글꼴을 가져오는 방법을 설명했습니다. PDF 문서에서 사용된 모든 글꼴을 가져오는 것은 PDF 문서의 글꼴을 프로그래밍 방식으로 분석하거나 조작해야 하는 경우 유용할 수 있습니다. Aspose.PDF for .NET은 PDF 문서에서 사용된 모든 글꼴을 가져오는 것을 포함하여 PDF 문서 작업을 위한 간단하고 사용하기 쉬운 API를 제공합니다.

### 자주 묻는 질문

#### 질문: PDF 문서에 사용된 모든 글꼴을 가져와야 하는 이유는 무엇인가요?

답변: PDF 문서에 사용된 모든 글꼴을 가져오는 것은 글꼴 교체나 글꼴 사용자 정의와 같이 다양한 목적으로 글꼴을 프로그래밍 방식으로 분석하거나 조작해야 하는 경우 유용할 수 있습니다.

#### 질문: Aspose.PDF for .NET을 사용하여 PDF 문서에 사용된 모든 글꼴을 어떻게 가져올 수 있습니까?

 A: Aspose.PDF for .NET을 호출하여 PDF 문서에 사용된 모든 글꼴을 가져올 수 있습니다.`GetAllFonts` 의 방법`FontUtilities` 클래스. 이 메서드는 배열을 반환합니다.`Aspose.Pdf.Text.Font` PDF 문서에 사용된 글꼴을 나타내는 개체입니다.

#### 질문: 특정 기준에 따라 글꼴을 필터링할 수 있나요?

A: 네, Aspose.PDF for .NET을 사용하여 특정 기준에 따라 글꼴을 필터링할 수 있습니다. 모든 글꼴을 가져온 후, 글꼴을 프로그래밍 방식으로 분석하고 필요에 따라 필터링 논리를 적용할 수 있습니다.

#### 질문: Aspose.PDF for .NET은 다양한 글꼴 형식과 호환됩니까?

A: 네, Aspose.PDF for .NET은 TrueType, OpenType, Type 1 글꼴을 포함한 다양한 글꼴 형식과 호환됩니다. 다양한 글꼴 형식으로 작업하고 PDF 문서 조작 중에 처리할 수 있습니다.