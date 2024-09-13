---
title: PDF 파일에 음영 색상이 있는 텍스트 추가
linktitle: PDF 파일에 음영 색상이 있는 텍스트 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 음영 색상이 있는 텍스트를 추가하는 방법을 알아보세요.
type: docs
weight: 80
url: /ko/net/programming-with-text/add-text-with-shading-colors/
---
이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 파일에 음영 색상이 있는 텍스트를 추가하는 과정을 안내합니다. 제공된 C# 소스 코드는 필요한 단계를 보여줍니다.

## 요구 사항
시작하기 전에 다음 사항이 있는지 확인하세요.

- 컴퓨터에 Visual Studio나 다른 C# 컴파일러가 설치되어 있어야 합니다.
- .NET 라이브러리용 Aspose.PDF. 공식 Aspose 웹사이트에서 다운로드하거나 NuGet과 같은 패키지 관리자를 사용하여 설치할 수 있습니다.

## 1단계: 프로젝트 설정
1. 원하는 개발 환경에서 새로운 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필요한 네임스페이스 가져오기
음영 색상이 있는 텍스트를 추가하려는 코드 파일에서 다음 using 지시문을 파일 맨 위에 추가합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## 3단계: 문서 디렉토리 설정
 코드에서 다음 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 그리고 교체하다`"YOUR DOCUMENT DIRECTORY"` 문서가 저장된 디렉토리 경로를 포함합니다.

## 4단계: PDF 문서 로드
 기존 PDF 문서를 로드하려면 다음을 사용합니다.`Document` 생성자를 사용하고 문서 파일의 경로를 제공합니다.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // 코드는 여기에 입력하세요...
}
```

## 5단계: 수정할 텍스트 찾기
사용`TextFragmentAbsorber` 문서 내에서 원하는 텍스트를 찾습니다. 제공된 코드에서 "Lorem ipsum"이라는 텍스트를 찾습니다.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## 6단계: 텍스트의 음영 색상 설정
 새로운 것을 만드세요`Color` 패턴 색상 공간이 있는 객체를 선택하고 그래디언트 음영 색상을 지정합니다. 이 색상을 다음에 할당합니다.`ForegroundColor` 의 속성`TextState` 의`TextFragment` 물체.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## 7단계: 추가 텍스트 서식 적용(선택 사항)
 밑줄과 같은 추가 서식을 텍스트 조각에 적용하려면 속성을 수정해야 합니다.`TextState` 물체.

```csharp
textFragment.TextState.Underline = true;
```

## 8단계: 수정된 PDF 문서 저장
 수정된 PDF 문서를 다음을 사용하여 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 음영 색상으로 텍스트 추가를 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// 패턴 색상공간으로 새로운 색상 만들기
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## 결론
Aspose.PDF for .NET을 사용하여 PDF 문서에 음영 색상이 있는 텍스트를 성공적으로 추가했습니다. 결과 PDF 파일은 이제 지정된 출력 파일 경로에서 찾을 수 있습니다.

### 자주 묻는 질문

#### 질문: 이 튜토리얼의 주요 초점은 무엇입니까?

A: 이 튜토리얼은 Aspose.PDF for .NET 라이브러리를 사용하여 PDF 파일에 음영 색상이 있는 텍스트를 추가하는 과정을 안내합니다. 제공된 C# 소스 코드는 이를 달성하는 데 필요한 단계를 보여줍니다.

#### 질문: 이 튜토리얼에서는 어떤 네임스페이스를 가져와야 하나요?

A: 음영 색상이 있는 텍스트를 추가하려는 코드 파일에서 파일 시작 부분에 다음 네임스페이스를 가져옵니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### 질문: 문서 디렉토리를 어떻게 지정하나요?

 A: 코드에서 다음 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 그리고 교체하다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 포함합니다.

#### 질문: 기존 PDF 문서를 어떻게 로드하나요?

 A: 4단계에서는 다음을 사용하여 기존 PDF 문서를 로드합니다.`Document` 생성자와 문서 파일 경로 제공:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // 코드는 여기에 입력하세요...
}
```

#### 질문: PDF 문서에서 특정 텍스트를 찾아 수정하려면 어떻게 해야 하나요?

 A: 5단계에서는 다음을 사용합니다.`TextFragmentAbsorber` 문서 내에서 원하는 텍스트를 찾으려면. 그런 다음 속성을 수정할 수 있습니다.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### 질문: 텍스트에 음영 색상을 어떻게 설정할 수 있나요?

 A: 6단계에서는 새 것을 만듭니다.`Color` 패턴 색상 공간이 있는 객체를 선택하고 그래디언트 음영 색상을 지정합니다. 이 색상을 다음에 할당합니다.`ForegroundColor` 의 속성`TextState` 의`TextFragment` 물체:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### 질문: 수정된 텍스트에 추가적인 텍스트 서식을 적용할 수 있나요?

A: 예, 7단계에서 밑줄과 같은 추가 텍스트 서식을 적용할 수 있습니다.`TextState` 물체:

```csharp
textFragment.TextState.Underline = true;
```

#### 질문: 수정된 PDF 문서를 어떻게 저장하나요?

 A: 8단계에서는 수정된 PDF 문서를 다음을 사용하여 저장합니다.`Save` 의 방법`Document` 물체:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### 질문: 이 튜토리얼의 가장 중요한 점은 무엇인가요?

A: 이 튜토리얼을 따라하면 Aspose.PDF for .NET을 사용하여 음영 색상으로 텍스트를 추가하여 PDF 문서를 향상시키는 방법을 성공적으로 배웠습니다. 이는 PDF 파일 내의 특정 텍스트 콘텐츠를 강조하고 강조하는 데 특히 유용할 수 있습니다.