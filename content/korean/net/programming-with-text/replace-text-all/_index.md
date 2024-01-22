---
title: PDF 파일의 텍스트 모두 바꾸기
linktitle: PDF 파일의 텍스트 모두 바꾸기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 모든 텍스트를 바꾸는 방법을 알아보세요.
type: docs
weight: 350
url: /ko/net/programming-with-text/replace-text-all/
---
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일의 모든 텍스트를 바꾸는 방법을 설명합니다. 필요한 C# 소스 코드와 함께 단계별 가이드를 제공합니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 라이브러리용 Aspose.PDF가 설치되었습니다.
- C# 프로그래밍에 대한 기본 이해.

## 1단계: 문서 디렉터리 설정

 입력 PDF 파일이 있는 디렉터리로 경로를 설정합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 변수를 PDF 파일 경로로 바꿉니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: PDF 문서 로드

 다음을 사용하여 PDF 문서를 로드합니다.`Document` Aspose.PDF 라이브러리의 클래스입니다.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## 3단계: 텍스트 검색 및 바꾸기

 만들기`TextFragmentAbsorber` 입력된 검색 문구의 모든 인스턴스를 찾는 개체입니다. PDF 문서의 모든 페이지에 대해 흡수체를 적용하여 텍스트 조각을 추출합니다.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 4단계: 텍스트 바꾸기

추출된 텍스트 조각을 반복하고 필요에 따라 텍스트를 바꿉니다. 텍스트와 글꼴, 글꼴 크기, 전경색, 배경색 등 기타 속성을 업데이트합니다.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "TEXT";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## 5단계: 수정된 PDF 저장

수정된 PDF 문서를 지정된 출력 파일에 저장합니다.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### .NET용 Aspose.PDF를 사용하여 텍스트 모두 바꾸기의 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
// 입력된 검색 문구의 모든 인스턴스를 찾기 위해 TextAbsorber 개체를 만듭니다.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// 모든 페이지에 대한 흡수체를 수락합니다.
pdfDocument.Pages.Accept(textFragmentAbsorber);
// 추출된 텍스트 조각 가져오기
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// 조각을 통해 반복
foreach (TextFragment textFragment in textFragmentCollection)
{
	// 텍스트 및 기타 속성 업데이트
	textFragment.Text = "TEXT";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextAll_out.pdf";
// 결과 PDF 문서를 저장합니다.
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서의 모든 텍스트를 바꾸는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 C# 코드를 실행하면 PDF 문서를 로드하고, 원하는 텍스트를 검색하여 바꾸고, 수정된 PDF를 저장할 수 있습니다.

### FAQ

#### Q: "PDF 파일의 텍스트 모두 바꾸기" 튜토리얼의 목적은 무엇입니까?

A: "PDF 파일에서 텍스트 모두 바꾸기" 튜토리얼의 목적은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 특정 텍스트의 모든 인스턴스를 바꾸는 과정을 안내하는 것입니다. 샘플 C# 코드와 함께 단계별 가이드를 제공합니다.

#### Q: PDF 문서의 모든 텍스트 인스턴스를 바꾸려는 이유는 무엇입니까?

A: 문서 전체의 내용을 업데이트하거나 표준화해야 하는 경우 PDF 문서에서 특정 텍스트의 모든 인스턴스를 바꾸는 것이 필요할 수 있습니다. 이 프로세스는 문서 내용과 형식의 일관성을 보장하는 데 특히 유용할 수 있습니다.

#### Q: 문서 디렉터리를 어떻게 설정합니까?

A: 문서 디렉토리를 설정하려면:

1.  바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 변수를 입력 PDF 파일이 있는 디렉터리의 경로로 바꿉니다.

#### Q: PDF 문서의 모든 텍스트 인스턴스를 어떻게 바꾸나요?

A: 튜토리얼에서는 다음 단계를 안내합니다.

1.  다음을 사용하여 PDF 문서를 로드합니다.`Document` 수업.
2.  만들기`TextFragmentAbsorber` 입력된 검색 문구의 모든 인스턴스를 찾는 개체입니다. PDF 문서의 모든 페이지에 대해 흡수체를 적용하여 텍스트 조각을 추출합니다.
3. 추출된 텍스트 조각을 반복하고 텍스트를 바꿉니다. 필요에 따라 글꼴, 글꼴 크기, 전경색, 배경색과 같은 기타 속성을 업데이트합니다.
4. 수정된 PDF 문서를 저장합니다.

#### Q: 대소문자 구분 검색을 기반으로 텍스트를 바꿀 수 있습니까?

 A: 예, 변경할 수 있습니다.`TextFragmentAbsorber` 대소문자를 구분하여 검색하려면 텍스트를 검색하세요. 검색하려는 정확한 텍스트를 제공하기만 하면 흡수체가 그에 따라 일치시켜 줍니다.

#### Q: 텍스트 교체 시 글꼴 교체는 선택 사항인가요?

A: 예, 글꼴 교체는 선택 사항입니다. 새 글꼴을 지정하지 않으면 텍스트는 원본 텍스트 조각의 글꼴을 유지합니다.

#### Q: PDF 문서의 특정 섹션에서 텍스트를 바꾸려면 어떻게 해야 합니까?

A: 텍스트 조각의 위치에 따라 조건문을 포함하도록 텍스트 조각을 통해 루프를 조정할 수 있습니다. 이렇게 하면 PDF의 특정 섹션에서만 텍스트를 바꾸도록 선택할 수 있습니다.

#### Q: 제공된 코드를 실행하면 예상되는 결과는 무엇입니까?

A: 튜토리얼을 따르고 제공된 C# 코드를 실행하면 PDF 문서에서 지정된 텍스트의 모든 인스턴스를 바꿀 수 있습니다. 대체된 텍스트에는 글꼴, 글꼴 크기, 전경색, 배경색 등 사용자가 지정한 속성이 적용됩니다.

#### Q: 이 접근 방식을 사용하여 이미지나 주석과 같은 텍스트가 아닌 요소를 바꿀 수 있습니까?

A: 아니요. 이 튜토리얼은 특히 PDF 문서의 텍스트 교체에 중점을 둡니다. 텍스트가 아닌 요소를 교체해야 하는 경우 다른 절차를 따르거나 다른 Aspose.PDF 기능을 사용해야 합니다.