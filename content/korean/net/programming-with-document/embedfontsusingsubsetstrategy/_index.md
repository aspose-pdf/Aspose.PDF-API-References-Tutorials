---
title: Subset 전략을 사용하여 PDF 파일에 글꼴 포함
linktitle: Subset 전략으로 글꼴 임베드
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 Subset Strategy로 PDF 파일에 글꼴을 임베드하는 방법을 알아보세요. 필요한 문자만 임베드하여 PDF 크기를 최적화하세요.
type: docs
weight: 130
url: /ko/net/programming-with-document/embedfontsusingsubsetstrategy/
---
## 소개

디지털 시대에 PDF는 문서 공유의 필수 요소가 되었습니다. 보고서, 프레젠테이션 또는 전자책을 보내는 경우 글꼴이 올바르게 표시되는지 확인하는 것이 중요합니다. PDF를 열었는데 텍스트가 의도한 것과 다르게 보이는 경우가 있었나요? 이는 문서에 사용된 글꼴이 제대로 포함되지 않았을 때 종종 발생합니다. 바로 여기서 Aspose.PDF for .NET이 등장합니다! 이 튜토리얼에서는 하위 집합 전략을 사용하여 PDF 파일에 글꼴을 포함하는 방법을 살펴보고, 어디에서 보든 문서가 의도한 대로 표시되도록 합니다.

## 필수 조건

글꼴을 내장하는 것에 대한 세부적인 내용을 살펴보기 전에 몇 가지 준비해야 할 사항이 있습니다.

1.  .NET용 Aspose.PDF: Aspose.PDF 라이브러리가 설치되어 있는지 확인하세요. 여기에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
2. Visual Studio: .NET 코드를 작성하고 테스트할 수 있는 개발 환경입니다.
3. C#에 대한 기본 지식: C# 프로그래밍에 익숙하면 코드 조각을 더 잘 이해하는 데 도움이 됩니다.

## 패키지 가져오기

시작하려면 C# 프로젝트에서 필요한 패키지를 가져와야 합니다. 방법은 다음과 같습니다.

### 새 프로젝트 만들기

Visual Studio를 열고 새 C# 프로젝트를 만듭니다. 단순성을 위해 콘솔 애플리케이션을 선택할 수 있습니다.

### Aspose.PDF 참조 추가

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭합니다.
2. "NuGet 패키지 관리"를 선택하세요.
3. "Aspose.PDF"를 검색하여 최신 버전을 설치하세요.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

이제 모든 것이 설정되었으니 PDF 파일에 글꼴을 포함하는 과정을 단계별로 나누어 보겠습니다.

## 1단계: 문서 디렉토리 설정

우선, 우리는 문서가 어디에 저장되는지 정의해야 합니다. 이것은 우리가 이 디렉토리에서 읽고 쓸 것이기 때문에 중요합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` PDF 파일이 있는 실제 경로와 함께. 이는 다음과 같을 수 있습니다.`@"C:\Documents\"`.

## 2단계: PDF 문서 로드

다음으로, 수정하려는 PDF 문서를 로드합니다. 여기서 Aspose.PDF가 빛을 발하며, PDF 파일을 쉽게 조작할 수 있습니다.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 당신이 가지고 있는지 확인하십시오`input.pdf` 지정한 디렉토리에 있는 파일입니다. 이 파일은 우리가 수정할 파일입니다.

## 3단계: 모든 글꼴 하위 집합

이제 문제의 핵심인 글꼴 임베딩에 대해 알아보겠습니다. 모든 글꼴을 하위 집합으로 임베딩하는 것으로 시작하겠습니다. 즉, 문서에서 사용된 문자만 임베딩되므로 파일 크기를 상당히 줄일 수 있습니다.

```csharp
// SubsetAllFonts의 경우 모든 글꼴이 문서의 하위 집합으로 포함됩니다.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
```

 사용하여`SubsetAllFonts`문서에 사용된 모든 글꼴이 내장되도록 했지만, 실제로 사용되는 문자만 포함됩니다.

## 4단계: 내장된 글꼴만 하위 집합으로 지정

어떤 경우에는 문서에 이미 내장된 글꼴만 내장하고 싶을 수 있습니다. 이는 새 글꼴을 추가하지 않고 원래 모양을 유지하려는 경우에 유용합니다.

```csharp
//완전히 내장된 글꼴의 경우 글꼴 하위 집합이 포함되지만 문서에 내장되지 않은 글꼴은 영향을 받지 않습니다.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

이 코드 줄은 이미 내장된 글꼴만 하위 집합으로 지정하고 내장되지 않은 글꼴은 그대로 둡니다.

## 5단계: 수정된 문서 저장

마지막으로, 우리는 변경 사항을 저장해야 합니다. 여기서 우리는 수정된 문서를 디스크에 다시 씁니다.

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

 이렇게 하면 이름이 지정된 새 PDF 파일이 생성됩니다.`Output_out.pdf` 지정한 디렉토리에 내장된 글꼴이 포함되어 있습니다.

## 결론

이제 아시죠! Aspose.PDF for .NET을 사용하여 PDF 파일에 글꼴을 성공적으로 임베드했습니다. 이러한 단계를 따르면 어디에서 보든 문서가 의도한 대로 표시되도록 할 수 있습니다. 보고서, 프레젠테이션 또는 기타 유형의 문서를 공유하든 글꼴을 임베드하는 것은 전문성과 명확성을 유지하는 데 중요한 단계입니다.

## 자주 묻는 질문

### 글꼴 서브세팅이란 무엇인가요?
글꼴 서브세팅은 전체 글꼴을 포함하는 대신, 문서에 사용된 문자만 포함하는 프로세스로, 파일 크기를 줄이는 데 도움이 됩니다.

### PDF에 글꼴을 포함해야 하는 이유는 무엇입니까?
글꼴을 포함시키면 모든 기기에서 문서가 동일하게 표시되어 글꼴 대체 문제를 방지할 수 있습니다.

### Aspose.PDF를 무료로 사용할 수 있나요?
 네, Aspose는 구매하기 전에 라이브러리를 테스트하는 데 사용할 수 있는 무료 평가판을 제공합니다. 찾을 수 있습니다.[여기](https://releases.aspose.com/).

### 더 많은 문서는 어디에서 찾을 수 있나요?
 .NET용 Aspose.PDF에 대한 전체 문서에 액세스할 수 있습니다.[여기](https://reference.aspose.com/pdf/net/).

### 문제가 발생하면 어떻게 하나요?
 문제가 발생하면 Aspose 지원 포럼에서 도움을 요청할 수 있습니다.[여기](https://forum.aspose.com/c/pdf/10).