---
title: 하위 집합 전략을 사용하여 PDF 파일에 글꼴 포함
linktitle: 하위 집합 전략으로 글꼴 포함
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 하위 집합 전략을 사용하여 PDF 파일에 글꼴을 포함하는 방법을 알아보세요. 필요한 문자만 삽입하여 PDF 크기를 최적화하세요.
type: docs
weight: 130
url: /ko/net/programming-with-document/embedfontsusingsubsetstrategy/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 하위 집합 전략으로 PDF 파일에 글꼴을 포함하는 방법에 대해 설명합니다. .NET용 Aspose.PDF는 개발자가 프로그래밍 방식으로 PDF 문서를 생성, 편집 및 조작할 수 있는 강력한 라이브러리입니다. PDF 파일에 글꼴을 포함시키는 것은 필요한 글꼴이 해당 장치에 설치되어 있는지 여부에 관계없이 문서가 다른 장치에서 올바르게 표시되도록 하는 중요한 단계입니다.

## 1단계: 새 C# 콘솔 애플리케이션 만들기
시작하려면 Visual Studio에서 새 C# 콘솔 애플리케이션을 만듭니다. 원하는 대로 이름을 지정할 수 있습니다. 프로젝트가 생성되면 .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가해야 합니다.

## 2단계: Aspose.PDF 네임스페이스 가져오기
Aspose.PDF 네임스페이스를 가져오려면 C# 파일 상단에 다음 코드 줄을 추가하세요.

```csharp
using Aspose.Pdf;
```

## 3단계: 기존 PDF 파일 로드
기존 PDF 파일에 글꼴을 포함하려면 Document 클래스를 사용하여 해당 파일을 로드해야 합니다. 다음 코드는 기존 PDF 파일을 로드하는 방법을 보여줍니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 기존 PDF 파일 로드
Document doc = new Document(dataDir + "input.pdf");
```

## 4단계: 하위 집합 전략으로 글꼴 포함
.NET용 Aspose.PDF는 글꼴 포함을 위한 두 가지 전략인 SubsetAllFonts와 SubsetEmbeddedFontsOnly를 제공합니다.

SubsetAllFonts 전략은 문서의 모든 글꼴을 하위 집합으로 포함합니다. 하위 집합은 문서에 사용된 문자만 포함하는 글꼴의 일부입니다. 이 전략은 PDF 문서의 파일 크기를 줄이는 데 유용합니다.

SubsetEmbeddedFontsOnly 전략은 문서에 이미 포함된 글꼴의 하위 집합만 포함합니다. 글꼴이 포함되지 않은 경우 이 전략의 영향을 받지 않습니다.

다음 코드는 하위 집합 전략을 사용하여 PDF 파일에 글꼴을 포함하는 방법을 보여줍니다.

```csharp
// SubsetAllFonts의 경우 모든 글꼴이 문서에 하위 집합으로 포함됩니다.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// 완전히 포함된 글꼴에는 글꼴 하위 집합이 포함되지만 문서에 포함되지 않은 글꼴은 영향을 받지 않습니다.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## 5단계: PDF 문서 저장
하위 집합 전략을 사용하여 PDF 파일에 모든 글꼴을 포함시킨 후에는 문서를 저장해야 합니다. 다음 코드는 PDF 파일을 저장하는 방법을 보여줍니다.

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 하위 집합 전략으로 글꼴을 삽입하기 위한 예제 소스 코드입니다. 

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
// SubsetAllFonts의 경우 모든 글꼴이 문서에 하위 집합으로 포함됩니다.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
// 완전히 포함된 글꼴에는 글꼴 하위 집합이 포함되지만 문서에 포함되지 않은 글꼴은 영향을 받지 않습니다.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
doc.Save(dataDir + "Output_out.pdf");
```

## 결론
이 기사에서는 .NET용 Aspose.PDF를 사용하여 하위 집합 전략으로 PDF 파일에 글꼴을 포함하는 방법에 대해 논의했습니다. .NET용 Aspose.PDF는 다양한 전략으로 글꼴을 추가하고 포함하는 등 PDF 문서 작업을 위한 간단하고 사용하기 쉬운 API를 제공합니다. PDF 파일에 글꼴을 포함시키는 것은 문서가 다른 장치에서 올바르게 표시되도록 하는 중요한 단계이며, 하위 집합 전략은 PDF 문서의 파일 크기를 줄이는 데 유용한 기능입니다.

### 하위 집합 전략을 사용하여 PDF 파일에 글꼴을 포함하는 데 대한 FAQ

#### Q: PDF 파일에 글꼴을 포함하기 위한 하위 집합 전략은 무엇입니까?

A: PDF 파일에 글꼴을 포함하기 위한 하위 집합 전략은 문서에 사용된 문자를 포함하는 글꼴의 일부만 포함된다는 의미입니다. 이는 불필요한 글꼴 데이터를 제거하여 PDF 문서의 파일 크기를 줄이는 데 도움이 됩니다.

#### Q: SubsetAllFonts 전략과 SubsetEmbeddedFontsOnly 전략의 차이점은 무엇입니까?

 답:`SubsetAllFonts`전략은 문서의 모든 글꼴을 하위 집합으로 포함하지만`SubsetEmbeddedFontsOnly` 전략은 문서에 이미 포함된 글꼴의 하위 집합만 포함합니다. 후자 전략은 아직 포함되지 않은 글꼴에는 영향을 미치지 않습니다.

#### Q: 하위 집합 전략을 사용한 글꼴 포함이 중요한 이유는 무엇입니까?

A: 하위 집합 전략을 사용한 글꼴 포함은 PDF 파일에 텍스트를 올바르게 표시하는 데 필요한 글꼴 데이터가 포함되어 있는지 확인하는 동시에 문서에 사용된 문자만 포함하여 파일 크기를 더 작게 유지하는 데 중요합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 다양한 전략의 글꼴을 포함할 수 있습니까?

 A: 예, .NET용 Aspose.PDF는 다음을 포함하여 글꼴 포함을 위한 다양한 전략을 제공합니다.`SubsetAllFonts` 그리고`SubsetEmbeddedFontsOnly`. 요구 사항에 따라 적절한 전략을 선택할 수 있습니다.

#### Q: Aspose.PDF for .NET은 PDF 문서 작업을 위한 신뢰할 수 있는 라이브러리입니까?

A: 예, .NET용 Aspose.PDF는 PDF 문서 작업을 위한 안정적이고 강력한 라이브러리입니다. .NET 응용 프로그램에서 PDF 파일을 생성, 편집 및 조작하기 위한 광범위한 기능을 제공합니다.