---
title: PDF 파일에서 플로팅 박스 콘텐츠에 대한 텍스트 정렬
linktitle: PDF 파일에서 플로팅 박스 콘텐츠에 대한 텍스트 정렬
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일의 떠 있는 상자 안에 텍스트를 정렬하는 방법을 알아보세요.
type: docs
weight: 520
url: /ko/net/programming-with-text/text-alignment-for-floating-box-contents/
---
이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 파일의 떠 있는 상자 안에 텍스트를 정렬하는 방법을 설명합니다. 제공된 C# 소스 코드는 단계별로 프로세스를 보여줍니다.

## 필수 조건

튜토리얼을 진행하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- .NET 라이브러리용 Aspose.PDF가 설치되었습니다. Aspose 웹사이트에서 얻을 수 있거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

## 1단계: 프로젝트 설정

선호하는 통합 개발 환경(IDE)에서 새 C# 프로젝트를 만들고 .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필요한 네임스페이스 가져오기

필요한 네임스페이스를 가져오려면 C# 파일의 시작 부분에 다음 using 지시문을 추가합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3단계: 문서 디렉토리 경로 설정

 다음을 사용하여 문서 디렉토리 경로를 설정하세요.`dataDir` 변하기 쉬운:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 포함합니다.

## 4단계: 새 문서 만들기

 새로운 것을 만드세요`Document` 물체:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## 5단계: 텍스트 조각으로 떠 있는 상자 만들기

 여러개 생성`FloatingBox` 수직 정렬과 수평 정렬이 다른 객체:

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

 텍스트와 스타일을 수정하세요`TextFragment` 원하는 대로 객체를 지정합니다.

## 6단계: PDF 문서 저장

수정된 PDF 문서를 저장합니다.

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 교체를 꼭 해주세요`"FloatingBox_alignment_review_out.pdf"` 원하는 출력 파일 이름을 입력합니다.

### .NET용 Aspose.PDF를 사용하여 떠 있는 상자 내용에 대한 텍스트 정렬을 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
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

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 문서의 떠 있는 상자 안에 텍스트를 정렬하는 방법을 성공적으로 배웠습니다. 이 튜토리얼은 프로젝트 설정부터 수정된 문서 저장까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일의 떠 있는 상자 안에 있는 텍스트 정렬을 사용자 지정할 수 있습니다.

### 자주 묻는 질문

#### 질문: "PDF 파일에서 떠 있는 상자 내용에 대한 텍스트 정렬" 튜토리얼의 목적은 무엇인가요?

A: "PDF 파일에서 플로팅 상자 내용에 대한 텍스트 정렬" 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 문서에서 플로팅 상자 내의 텍스트를 정렬하는 방법을 사용자에게 안내하는 것을 목표로 합니다. 이 튜토리얼은 프로세스를 보여주기 위한 단계별 지침과 C# 코드 샘플을 제공합니다.

#### 질문: 이 튜토리얼은 떠 있는 상자 안에서 텍스트를 정렬하는 데 어떻게 도움이 되나요?

A: 이 튜토리얼은 사용자가 Aspose.PDF for .NET을 사용하여 PDF 문서의 떠 있는 상자 안에 텍스트를 정렬하는 방법을 이해하는 데 도움이 됩니다. 제공된 단계와 코드 예제를 따르면 사용자는 떠 있는 상자 안에 있는 텍스트의 수직 및 수평 정렬을 사용자 지정할 수 있습니다.

#### 질문: 이 튜토리얼을 따르려면 어떤 전제 조건이 필요합니까?

A: 튜토리얼을 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있어야 합니다. 또한 Aspose.PDF for .NET 라이브러리를 설치해야 합니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

#### 질문: 이 튜토리얼을 따르려면 프로젝트를 어떻게 설정해야 하나요?

A: 시작하려면 선호하는 통합 개발 환경(IDE)에서 새 C# 프로젝트를 만들고 Aspose.PDF for .NET 라이브러리에 대한 참조를 추가합니다. 이렇게 하면 라이브러리의 기능을 활용하여 PDF 문서 작업과 떠 있는 상자 내에서 텍스트를 정렬할 수 있습니다.

#### 질문: 이 튜토리얼을 사용하면 모든 유형의 떠 있는 상자 내에서 텍스트를 정렬할 수 있나요?

A: 네, 이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 문서의 떠 있는 상자 안에 텍스트를 정렬하는 방법에 대한 지침을 제공합니다. 제공된 코드 샘플을 사용하여 떠 있는 상자 안에 있는 텍스트의 수직 및 수평 정렬을 사용자 지정할 수 있습니다.

#### 질문: 떠 있는 상자 안에서 텍스트 정렬을 어떻게 지정하나요?

 A: 튜토리얼에서는 생성 방법을 보여줍니다.`FloatingBox`객체와 설정`VerticalAlignment` 그리고`HorizontalAlignment` 포함된 텍스트의 정렬을 제어하는 속성입니다. 요구 사항에 따라 이러한 속성을 조정할 수 있습니다.

#### 질문: 떠 있는 상자의 모양을 어떻게 사용자 지정할 수 있나요?

 A: 테두리, 크기, 텍스트 내용과 같은 속성을 수정하여 떠 있는 상자의 모양을 사용자 정의할 수 있습니다. 이 튜토리얼은 떠 있는 상자를 만들고 스타일을 지정하는 방법을 보여주는 코드 샘플을 제공합니다.`FloatingBox` 사물.

#### 질문: 동일한 PDF 문서에 정렬이 다른 여러 개의 떠 있는 상자를 추가할 수 있나요?

 A: 네, 튜토리얼에서는 여러 개를 만드는 방법을 설명합니다.`FloatingBox` 수직 및 수평 정렬이 다른 객체를 동일한 PDF 문서에 추가합니다. 이를 통해 동일한 문서 내에서 다양한 정렬의 효과를 볼 수 있습니다.

#### 질문: 수정된 PDF 문서를 어떻게 저장하나요?

 A: 수정된 PDF 문서를 저장하려면 다음을 사용할 수 있습니다.`Save` 의 방법`Document` 객체. 이 튜토리얼은 결과 PDF 문서를 저장하는 방법을 보여주는 코드 샘플을 제공합니다.