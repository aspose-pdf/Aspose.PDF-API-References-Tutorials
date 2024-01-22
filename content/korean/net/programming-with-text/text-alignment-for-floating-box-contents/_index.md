---
title: PDF 파일의 부동 상자 내용에 대한 텍스트 정렬
linktitle: PDF 파일의 부동 상자 내용에 대한 텍스트 정렬
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 부동 상자 내에서 텍스트를 정렬하는 방법을 알아보세요.
type: docs
weight: 520
url: /ko/net/programming-with-text/text-alignment-for-floating-box-contents/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일의 부동 상자 내에서 텍스트를 정렬하는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

## 전제조건

튜토리얼을 진행하기 전에 다음 사항을 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- .NET 라이브러리용 Aspose.PDF가 설치되었습니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

## 1단계: 프로젝트 설정

선호하는 IDE(통합 개발 환경)에서 새 C# 프로젝트를 생성하고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하는 것으로 시작하세요.

## 2단계: 필요한 네임스페이스 가져오기

필수 네임스페이스를 가져오려면 C# 파일 시작 부분에 다음 using 지시문을 추가하세요.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3단계: 문서 디렉터리 경로 설정

 다음을 사용하여 문서 디렉토리의 경로를 설정하십시오.`dataDir` 변하기 쉬운:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

## 4단계: 새 문서 만들기

 새로 만들기`Document` 물체:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## 5단계: 텍스트 조각으로 부동 상자 만들기

 여러 개 만들기`FloatingBox` 수직 정렬과 수평 정렬이 다른 객체:

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);

Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);

Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

 텍스트와 스타일을 수정합니다.`TextFragment` 원하는대로 개체.

## 6단계: PDF 문서 저장

수정된 PDF 문서를 저장합니다.

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 꼭 교체하세요`"FloatingBox_alignment_review_out.pdf"` 원하는 출력 파일 이름으로.

### .NET용 Aspose.PDF를 사용하여 부동 상자 내용의 텍스트 정렬을 위한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

## 결론

축하해요! .NET용 Aspose.PDF를 사용하여 PDF 문서의 부동 상자 내에서 텍스트를 정렬하는 방법을 성공적으로 배웠습니다. 이 튜토리얼에서는 프로젝트 설정부터 수정된 문서 저장까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일의 부동 상자 내 텍스트 정렬을 사용자 지정할 수 있습니다.

### FAQ

#### Q: "PDF 파일의 부동 상자 내용에 대한 텍스트 정렬" 튜토리얼의 목적은 무엇입니까?

A: "PDF 파일의 부동 상자 내용에 대한 텍스트 정렬" 튜토리얼의 목적은 .NET용 Aspose.PDF를 사용하여 PDF 문서의 부동 상자 내에서 텍스트를 정렬하는 방법을 사용자에게 안내하는 것입니다. 이 자습서에서는 프로세스를 보여주기 위한 단계별 지침과 C# 코드 샘플을 제공합니다.

#### Q: 이 튜토리얼은 부동 상자 내에서 텍스트를 정렬하는 데 어떻게 도움이 됩니까?

A: 이 튜토리얼은 사용자가 .NET용 Aspose.PDF를 활용하여 PDF 문서의 부동 상자 내에서 텍스트를 정렬하는 방법을 이해하는 데 도움이 됩니다. 제공된 단계와 코드 예제에 따라 사용자는 부동 상자 내 텍스트의 수직 및 수평 정렬을 사용자 정의할 수 있습니다.

#### Q: 이 튜토리얼을 따르려면 어떤 전제 조건이 필요합니까?

A: 자습서를 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있어야 합니다. 또한 .NET용 Aspose.PDF 라이브러리가 설치되어 있어야 합니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

#### Q: 이 튜토리얼을 따르려면 프로젝트를 어떻게 설정해야 합니까?

A: 시작하려면 선호하는 IDE(통합 개발 환경)에서 새 C# 프로젝트를 만들고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하세요. 이를 통해 PDF 문서 작업 및 부동 상자 내에서 텍스트 정렬을 위한 라이브러리 기능을 활용할 수 있습니다.

#### Q: 이 튜토리얼을 사용하여 모든 유형의 부동 상자 내에서 텍스트를 정렬할 수 있습니까?

A: 예, 이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서의 부동 상자 내에서 텍스트를 정렬하는 방법에 대한 지침을 제공합니다. 제공된 코드 샘플을 사용하여 부동 상자 내 텍스트의 수직 및 수평 정렬을 사용자 정의할 수 있습니다.

#### Q: 부동 상자 내에서 텍스트 정렬을 어떻게 지정합니까?

 A: 튜토리얼에서는 다음을 생성하는 방법을 보여줍니다.`FloatingBox`개체를 설정하고`VerticalAlignment` 그리고`HorizontalAlignment` 포함된 텍스트의 정렬을 제어하는 속성입니다. 요구 사항에 따라 이러한 속성을 조정할 수 있습니다.

#### Q: 떠다니는 상자의 모양을 어떻게 사용자 정의할 수 있나요?

 A: 테두리, 크기, 텍스트 내용 등의 속성을 수정하여 부동 상자의 모양을 사용자 정의할 수 있습니다. 이 튜토리얼에서는 다음을 생성하고 스타일을 지정하는 방법을 보여주는 코드 샘플을 제공합니다.`FloatingBox` 사물.

#### 질문: 동일한 PDF 문서에 정렬이 다른 여러 개의 부동 상자를 추가할 수 있습니까?

 A: 예, 튜토리얼에서는 여러 항목을 생성하는 방법을 보여줍니다.`FloatingBox` 수직 및 수평 정렬이 다른 개체를 동일한 PDF 문서에 추가합니다. 이를 통해 동일한 문서 내에서 다양한 정렬의 효과를 확인할 수 있습니다.

#### Q: 수정된 PDF 문서를 어떻게 저장합니까?

 A: 수정된 PDF 문서를 저장하려면`Save` 의 방법`Document` 물체. 이 튜토리얼에서는 결과 PDF 문서를 저장하는 방법을 보여주는 코드 샘플을 제공합니다.