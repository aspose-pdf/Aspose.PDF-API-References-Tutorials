---
title: PDF 파일에서 글꼴 바꾸기
linktitle: PDF 파일에서 글꼴 바꾸기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일의 글꼴을 바꾸는 방법을 알아보세요.
type: docs
weight: 340
url: /ko/net/programming-with-text/replace-fonts/
---
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일에서 특정 글꼴을 대체하는 방법을 설명합니다. PDF 문서를 로드하고, 텍스트 조각을 검색하고, 대체할 글꼴을 식별하고, 글꼴을 대체하고, 제공된 C# 소스 코드를 사용하여 수정된 PDF를 저장하는 단계별 프로세스를 살펴봅니다.

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 라이브러리용 Aspose.PDF가 설치되었습니다.
- C# 프로그래밍에 대한 기본적인 이해.

## 1단계: 문서 디렉토리 설정

 먼저 입력 PDF 파일이 있는 디렉토리 경로를 설정해야 합니다. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` PDF 파일 경로가 있는 변수입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: PDF 문서 로드

 다음으로, 다음을 사용하여 PDF 문서를 로드합니다.`Document` Aspose.PDF 라이브러리의 클래스입니다.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## 3단계: 글꼴 검색 및 바꾸기

 우리는 만듭니다`TextFragmentAbsorber` 객체를 선택하고 편집 옵션을 설정하여 사용하지 않는 글꼴을 제거합니다. 그런 다음 PDF 문서의 모든 페이지에 대한 흡수체를 수락하여 텍스트 조각을 검색합니다.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## 4단계: 글꼴 바꾸기

우리는 흡수체에 의해 식별된 모든 텍스트 조각을 탐색합니다. 텍스트 조각의 글꼴 이름이 대체할 원하는 글꼴과 일치하면 새 글꼴로 대체합니다.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## 5단계: 수정된 PDF 저장

마지막으로 수정된 PDF 문서를 지정된 출력 파일에 저장합니다.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### .NET용 Aspose.PDF를 사용하여 글꼴 바꾸기 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉토리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// 소스 PDF 파일 로드
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// 텍스트 조각을 검색하고 편집 옵션을 사용하지 않는 글꼴 제거로 설정합니다.
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// 모든 페이지에 대한 흡수체를 수용합니다.
	pdfDocument.Pages.Accept(absorber);
	// 모든 TextFragments를 탐색합니다.
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// 글꼴 이름이 ArialMT인 경우 글꼴 이름을 Arial로 바꾸세요.
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	// 업데이트된 문서 저장
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 특정 글꼴을 바꾸는 방법을 알아보았습니다. 단계별 가이드를 따르고 제공된 C# 코드를 실행하면 PDF 문서를 로드하고, 텍스트 조각을 검색하고, 특정 글꼴을 식별하여 바꾸고, 수정된 PDF를 저장할 수 있습니다.

### 자주 묻는 질문

#### 질문: "PDF 파일의 글꼴 바꾸기" 튜토리얼의 목적은 무엇인가요?

A: "PDF 파일에서 글꼴 바꾸기" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 특정 글꼴을 바꾸는 방법을 보여줍니다. PDF 문서를 로드하고, 텍스트 조각을 검색하고, 바꿀 글꼴을 식별하고, 글꼴을 바꾸고, 수정된 PDF를 저장하는 방법에 대한 단계별 가이드를 제공합니다.

#### 질문: PDF 문서의 글꼴을 왜 바꿔야 하나요?

A: PDF 문서의 글꼴을 바꾸는 것은 텍스트 모양을 표준화하거나 다양한 장치와 플랫폼에서 문서의 호환성을 개선하고자 할 때 필요할 수 있습니다. 일관된 타이포그래피와 서식을 보장할 수 있습니다.

#### 질문: 문서 디렉토리를 어떻게 설정하나요?

A: 문서 디렉토리를 설정하려면:

1.  바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 입력 PDF 파일이 있는 디렉토리의 경로를 포함하는 변수입니다.

#### 질문: PDF 문서에서 특정 글꼴을 바꾸려면 어떻게 해야 하나요?

A: 튜토리얼은 단계별로 과정을 안내합니다.

1.  PDF 문서를 로드하려면 다음을 사용합니다.`Document` 수업.
2.  생성하다`TextFragmentAbsorber` 객체를 선택하고 편집 옵션을 설정하여 사용하지 않는 글꼴을 제거합니다. 모든 페이지에 대한 흡수체를 수락하여 텍스트 조각을 검색합니다.
3. 식별된 텍스트 조각을 탐색합니다. 텍스트 조각의 글꼴 이름이 바꾸려는 글꼴과 일치하면 새 글꼴로 바꿉니다.

####  Q: 사용 목적은 무엇입니까?`TextFragmentAbsorber` with font replacement options?

 A: 그`TextFragmentAbsorber` 글꼴 교체 옵션을 사용하면 텍스트 조각을 찾고 동시에 사용하지 않는 글꼴을 제거할 수 있습니다. 이는 교체된 글꼴이 PDF에 추가 리소스로 추가되지 않도록 하는 데 중요합니다.

#### 질문: 바꿀 특정 글꼴을 어떻게 식별합니까?

A: 흡수체에서 식별한 텍스트 조각을 탐색하면 각 텍스트 조각의 글꼴 정보에 액세스할 수 있습니다. 글꼴 이름이 바꾸려는 글꼴과 일치하면 바꾸기를 수행할 수 있습니다.

#### 질문: 바꿀 글꼴이 텍스트 조각에서 발견되지 않으면 어떻게 되나요?

A: 대체할 글꼴이 텍스트 조각에서 발견되지 않으면 텍스트 조각의 글꼴은 변경되지 않습니다. 글꼴 이름이 일치하는 경우에만 대체가 발생합니다.

#### 질문: 이 튜토리얼에서 글꼴을 바꾸는 데 제한이 있나요?

A: 이 튜토리얼은 텍스트 조각에서 특정 글꼴을 대체하는 데 중점을 둡니다. 주석이나 양식 필드와 같이 다른 컨텍스트에서 글꼴을 대체해야 하는 경우 그에 따라 접근 방식을 확장해야 합니다.

#### 질문: 제공된 코드를 실행하면 예상되는 결과는 무엇입니까?

A: 튜토리얼을 따라 제공된 C# 코드를 실행하면 PDF 문서의 특정 글꼴을 대체하게 됩니다. 설정한 기준에 따라 식별된 글꼴은 지정한 새 글꼴로 대체됩니다.

#### 질문: 이 방법을 사용하면 PDF 문서 전체의 글꼴을 바꿀 수 있나요?

대답: 네, 모든 텍스트 조각을 탐색하고 글꼴 바꾸기 논리를 적용하여 전체 PDF 문서의 글꼴을 바꾸는 코드를 적용할 수 있습니다.