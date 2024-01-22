---
title: PDF 파일에 글꼴 포함
linktitle: PDF 파일에 글꼴 포함
second_title: .NET API 참조용 Aspose.PDF
description: 이 단계별 가이드를 통해 .NET용 Aspose.PDF를 사용하여 PDF 파일에 글꼴을 포함하는 방법을 알아보세요. 문서가 모든 장치에서 올바르게 표시되는지 확인하십시오.
type: docs
weight: 120
url: /ko/net/programming-with-document/embedfont/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 글꼴을 포함하는 방법에 대해 설명합니다. .NET용 Aspose.PDF는 개발자가 프로그래밍 방식으로 PDF 문서를 생성, 편집 및 조작할 수 있는 강력한 라이브러리입니다. 이 라이브러리는 텍스트, 이미지, 표 등을 추가하는 등 PDF 문서 작업에 필요한 다양한 기능을 제공합니다. PDF 파일에 글꼴을 포함시키는 것은 필요한 글꼴이 해당 장치에 설치되어 있는지 여부에 관계없이 PDF 파일이 다른 장치에서 올바르게 표시되는지 확인하려는 개발자의 일반적인 요구 사항입니다.

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

## 4단계: 모든 페이지를 반복합니다.
PDF 파일을 로드한 후에는 문서의 모든 페이지를 반복해야 합니다. 각 페이지마다 사용된 글꼴이 있는지 확인하고, 그렇다면 해당 글꼴을 삽입해야 합니다. 다음 코드는 PDF 파일의 모든 페이지를 반복하고 글꼴을 포함하는 방법을 보여줍니다.

```csharp
foreach (Page page in doc.Pages)
{
    if (page.Resources.Fonts != null)
    {
        foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
        {
            // 글꼴이 이미 포함되어 있는지 확인
            if (!pageFont.IsEmbedded)
                pageFont.IsEmbedded = true;
        }
    }

    // 양식 개체 확인
    foreach (XForm form in page.Resources.Forms)
    {
        if (form.Resources.Fonts != null)
        {
            foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
            {
                // 글꼴이 포함되어 있는지 확인
                if (!formFont.IsEmbedded)
                    formFont.IsEmbedded = true;
            }
        }
    }
}
```

## 5단계: PDF 문서 저장
PDF 파일에 모든 글꼴을 포함시킨 후에는 문서를 저장해야 합니다. 다음 코드는 PDF 파일을 저장하는 방법을 보여줍니다.

```csharp
dataDir = dataDir + "EmbedFont_out.pdf";
// PDF 문서 저장
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```

### .NET용 Aspose.PDF를 사용하는 Embed Font의 예제 소스 코드

다음은 .NET용 Aspose.PDF를 사용하여 글꼴을 포함하는 전체 소스 코드입니다.


```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 기존 PDF 파일 로드
Document doc = new Document(dataDir + "input.pdf");

// 모든 페이지를 반복
foreach (Page page in doc.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// 글꼴이 이미 포함되어 있는지 확인
			if (!pageFont.IsEmbedded)
				pageFont.IsEmbedded = true;
		}
	}

	// 양식 개체 확인
	foreach (XForm form in page.Resources.Forms)
	{
		if (form.Resources.Fonts != null)
		{
			foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
			{
				// 글꼴이 포함되어 있는지 확인
				if (!formFont.IsEmbedded)
					formFont.IsEmbedded = true;
			}
		}
	}
}
dataDir = dataDir + "EmbedFont_out.pdf";
// PDF 문서 저장
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```


## 결론 PDF 파일에 글꼴 포함
이 기사에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 글꼴을 포함하는 방법에 대해 설명했습니다. .NET용 Aspose.PDF는 글꼴 추가 및 포함을 포함하여 PDF 문서 작업을 위한 간단하고 사용하기 쉬운 API를 제공합니다. PDF 파일에 글꼴을 포함시키는 것은 필요한 글꼴이 해당 장치에 설치되어 있는지 여부에 관계없이 문서가 다른 장치에서 올바르게 표시되도록 하는 중요한 단계입니다.

### FAQ

#### Q: PDF 파일에 글꼴을 포함하는 것이 중요한 이유는 무엇입니까?

A: 문서가 다양한 장치 및 시스템에서 올바르게 표시되도록 하려면 PDF 파일에 글꼴을 포함시키는 것이 필수적입니다. 글꼴이 포함되면 PDF 파일의 일부가 되므로 보기 장치에 설치된 외부 글꼴에 대한 종속성이 제거됩니다.

#### Q: PDF 파일에 사용된 모든 글꼴을 포함할 수 있나요?

A: 예, PDF 파일에 사용된 모든 글꼴을 포함할 수 있습니다. .NET용 Aspose.PDF는 PDF 파일에 사용된 모든 글꼴을 반복하고 이를 포함하여 다양한 장치에서 정확한 렌더링을 보장하는 간단한 접근 방식을 제공합니다.

#### Q: .NET용 Aspose.PDF는 다른 글꼴 형식과 호환됩니까?

A: 예, .NET용 Aspose.PDF는 TrueType, OpenType, Type 1 및 CFF 글꼴을 포함한 다양한 글꼴 형식을 지원합니다. 형식에 관계없이 PDF 파일에 글꼴을 포함할 수 있습니다.

#### Q: 글꼴을 포함하면 PDF 문서의 파일 크기가 늘어나나요?

A: 예, PDF 문서에 글꼴을 포함하면 글꼴 데이터가 PDF 파일 자체에 포함되므로 파일 크기가 커질 수 있습니다. 그러나 이렇게 하면 보기 장치의 글꼴 사용 가능 여부에 관계없이 문서의 모양이 일관되게 유지됩니다.

#### Q: 글꼴 포함 프로세스를 사용자 정의할 수 있습니까?

A: 예, .NET용 Aspose.PDF를 사용하면 글꼴 포함 프로세스를 사용자 정의할 수 있습니다. 포함할 글꼴을 선택하거나, 특정 글꼴을 제외하거나, 글꼴의 특정 하위 집합만 포함하여 파일 크기를 최적화할 수 있습니다.