---
title: PDF 파일에서 사용하지 않는 글꼴 제거
linktitle: PDF 파일에서 사용하지 않는 글꼴 제거
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에서 사용하지 않는 글꼴을 제거하는 방법을 알아보세요.
type: docs
weight: 300
url: /ko/net/programming-with-text/remove-unused-fonts/
---
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일에서 사용하지 않는 글꼴을 제거하는 방법을 설명합니다. PDF를 로드하고, 사용하지 않는 글꼴을 식별 및 제거하고, 제공된 C# 소스 코드를 사용하여 업데이트된 PDF를 저장하는 단계별 프로세스를 살펴보겠습니다.

## 요구사항

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 라이브러리용 Aspose.PDF가 설치되었습니다.
- C# 프로그래밍에 대한 기본적인 이해.

## 1단계: 문서 디렉터리 설정

 먼저, PDF 파일이 있는 디렉터리의 경로를 설정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 변수를 PDF 파일 경로로 바꿉니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 소스 PDF 로드

 다음으로, 다음을 사용하여 소스 PDF 문서를 로드합니다.`Document` Aspose.PDF 라이브러리의 클래스입니다.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## 3단계: 사용하지 않는 글꼴 식별 및 제거

 우리는`TextFragmentAbsorber` 이의를 제기하다`TextEditOptions` 매개변수가 다음으로 설정됨`TextEditOptions.FontReplace.RemoveUnusedFonts` . 이 옵션을 사용하면 PDF 문서에서 사용되지 않는 글꼴을 식별하고 제거할 수 있습니다. 그런 다음 모든 항목을 반복합니다.`TextFragments` 그리고 글꼴을 원하는 글꼴로 설정하세요.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## 4단계: 업데이트된 PDF 저장

마지막으로 업데이트된 PDF 문서를 지정된 출력 파일에 저장합니다.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### .NET용 Aspose.PDF를 사용하여 사용하지 않는 글꼴 제거에 대한 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// 소스 PDF 파일 로드
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// 모든 TextFragments를 반복합니다.
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// 업데이트된 문서 저장
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 사용하지 않는 글꼴을 제거하는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 C# 코드를 실행하면 PDF를 로드하고, 사용하지 않는 글꼴을 식별 및 제거하고, 업데이트된 PDF를 저장할 수 있습니다.

### FAQ

#### Q: "PDF 파일에서 사용하지 않는 글꼴 제거" 튜토리얼의 목적은 무엇입니까?

A: "PDF 파일에서 사용하지 않는 글꼴 제거" 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 사용하지 않는 글꼴을 제거하는 방법을 설명합니다. 이 튜토리얼은 PDF 로드, 사용하지 않는 글꼴 식별 및 제거, 업데이트된 PDF 저장 과정을 안내합니다.

#### 질문: PDF 문서에서 사용하지 않는 글꼴을 제거하려는 이유는 무엇입니까?

A: PDF 문서에서 사용하지 않는 글꼴을 제거하면 파일 크기를 줄이고 문서를 최적화하여 성능을 향상시킬 수 있습니다. 이는 문서 내용에 실제로 사용되지 않는 글꼴이 포함된 PDF를 처리할 때 특히 유용합니다.

#### Q: 문서 디렉터리를 어떻게 설정합니까?

A: 문서 디렉토리를 설정하려면:

1.  바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 변수를 PDF 파일이 있는 디렉터리의 경로로 바꿉니다.

#### Q: Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 사용하지 않는 글꼴을 어떻게 제거합니까?

A: 튜토리얼에서는 프로세스를 단계별로 안내합니다.

1.  다음을 사용하여 PDF 문서를 엽니다.`Document` 수업.
2.  만들기`TextFragmentAbsorber` 반대하다`TextEditOptions` 로 설정`FontReplace.RemoveUnusedFonts`.
3. PDF에서 사용되지 않는 글꼴을 식별하고 제거하려면 흡수체를 수락하십시오.
4.  모두 반복`TextFragments` 그리고 글꼴을 원하는 글꼴로 설정하세요.
5. 업데이트된 PDF 문서를 저장합니다.

####  Q: 이 프로그램의 목적은 무엇입니까?`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 답:`TextEditOptions.FontReplace.RemoveUnusedFonts` 매개변수는 다음을 지시합니다.`TextFragmentAbsorber` PDF 문서에서 사용하지 않는 글꼴을 식별하고 제거합니다.

#### Q: 사용하지 않는 글꼴을 내가 선택한 글꼴로 바꿀 수 있나요?

A: 예, 사용하지 않는 글꼴을 원하는 글꼴로 바꾸도록 코드를 수정할 수 있습니다. 제공된 샘플 코드에서는 "Arial, Bold" 글꼴이 대체 글꼴로 사용되었습니다.

####  Q: 어떻게 되나요?`TextFragmentAbsorber` work to remove unused fonts?

 답:`TextFragmentAbsorber` 으로 구성됩니다.`TextEditOptions.FontReplace.RemoveUnusedFonts` PDF의 텍스트 조각 내에서 사용되지 않는 글꼴을 식별하는 매개변수입니다. 흡수 후에는 다음을 통해 반복할 수 있습니다.`TextFragments` 글꼴을 원하는 대체 글꼴로 설정합니다.

#### Q: 제공된 코드를 실행하면 예상되는 결과는 무엇입니까?

A: 튜토리얼을 따르고 제공된 C# 코드를 실행하면 입력 PDF 문서에서 사용되지 않는 글꼴을 제거하고 업데이트된 버전을 출력 PDF 파일로 저장하게 됩니다.

#### Q: 특정 페이지나 영역에서만 글꼴을 제거하도록 코드를 수정할 수 있습니까?

답변: 제공된 코드는 전체 PDF 문서에서 사용되지 않는 글꼴을 제거하는 데 중점을 둡니다. 글꼴 제거를 위해 특정 페이지나 영역을 대상으로 지정하려면 접근 방식을 수정하고 더 복잡한 논리를 사용하여 해당 영역에서 사용되지 않는 글꼴을 식별해야 합니다.