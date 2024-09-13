---
title: PDF 파일에 숫자 스타일 적용
linktitle: PDF 파일에 숫자 스타일 적용
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 단계별 가이드를 통해 Aspose.PDF for .NET을 사용하여 PDF의 제목에 다양한 숫자 스타일(로마 숫자, 알파벳)을 적용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-headings/apply-number-style/
---
## 소개

PDF 문서에 아름답게 번호가 매겨진 목록을 추가해야 하는 경우가 있었나요? 법률 문서, 보고서 또는 프레젠테이션을 포맷하든 적절한 번호 매기기 스타일은 정보를 구성하는 데 필수적입니다. Aspose.PDF for .NET을 사용하면 PDF 파일의 제목에 다양한 번호 매기기 스타일을 적용하여 잘 구성되고 전문적인 문서를 만들 수 있습니다. 

## 필수 조건

코딩에 들어가기 전에 무엇이 필요한지 살펴보겠습니다.

1. .NET용 Aspose.PDF: 다음에서 최신 버전의 Aspose.PDF를 다운로드하세요.[여기](https://releases.aspose.com/pdf/net/).
2. 개발 환경: Visual Studio나 다른 .NET 호환 IDE가 있는지 확인하세요.
3. .NET Framework: .NET Framework 4.0 이상이 설치되어 있는지 확인하세요.
4.  라이센스 : 임시 라이센스를 사용할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/) 또는 탐색하세요[무료 체험](https://releases.aspose.com/) 옵션.

## 패키지 가져오기

시작하려면 프로젝트에 다음 네임스페이스를 가져왔는지 확인하세요.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 1단계: 문서 설정

새 PDF 문서를 만들고 페이지 설정을 구성하는 것으로 시작해 보겠습니다. 페이지 크기와 여백을 설정하여 콘텐츠의 레이아웃을 제어합니다.

설명: 이 단계에서는 일관된 서식을 위한 페이지 크기, 높이, 여백을 정의하는 등 PDF의 기본 구조를 설정합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// 페이지 크기와 여백 설정
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

이렇게 하면 문서의 페이지 크기가 8.5 x 11인치 페이지와 같아지고, 모든 변에 72포인트(또는 1인치)의 여백이 생깁니다.

## 2단계: PDF에 페이지 추가

다음으로, 나중에 번호 매기기 스타일을 적용할 PDF 문서에 새 페이지를 추가해 보겠습니다.

설명: 모든 PDF에는 페이지가 필요합니다! 이 단계는 PDF에 빈 페이지를 추가하고 여백을 문서 수준 설정과 일치하도록 설정합니다.

```csharp
// PDF 문서에 새 페이지 추가
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
```

## 3단계: 떠다니는 상자 만들기

FloatingBox를 사용하면 페이지의 흐름과 독립적으로 동작하는 상자 안에 콘텐츠(텍스트나 제목 등)를 배치할 수 있습니다. 이는 콘텐츠 레이아웃을 완벽하게 제어하고 싶을 때 유용합니다.

설명: 여기에서는 숫자 스타일이 적용될 제목을 담기 위해 FloatingBox를 설정하고 있습니다.

```csharp
// 구조화된 콘텐츠를 위한 FloatingBox 만들기
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

## 4단계: 로마 숫자로 첫 번째 제목 추가

이제 흥미로운 부분이 옵니다! 소문자 로마 숫자로 첫 번째 제목을 추가해 보겠습니다.

설명: 제목에 NumberingStyle.NumeralsRomanLowercase 스타일을 적용하면 번호가 로마 숫자(i, ii, iii 등)로 표시됩니다.

```csharp
// 로마 숫자로 첫 번째 제목을 만듭니다.
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
```

## 5단계: 두 번째 로마 숫자 제목 추가

데모 목적으로 두 번째 로마 숫자 제목을 추가해 보겠습니다. 하지만 이번에는 13부터 시작하겠습니다.

설명: StartNumber 속성을 사용하면 사용자 지정 번호에서 번호 매기기를 시작할 수 있습니다. 이 경우 13부터 시작합니다.

```csharp
// 로마 숫자 13으로 시작하는 두 번째 제목을 만듭니다.
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
```

## 6단계: 알파벳 번호가 있는 제목 추가

다양성을 위해 세 번째 제목을 추가해 보겠습니다. 하지만 이번에는 소문자로 알파벳 번호를 매기겠습니다(a, b, c 등).

설명: NumberingStyle을 LettersLowercase로 변경하면 제목에 알파벳 번호를 적용할 수 있습니다.

```csharp
// 알파벳 번호로 제목을 만듭니다.
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

## 7단계: PDF 저장

마지막으로 모든 제목과 숫자 스타일을 적용한 후 원하는 디렉토리에 PDF 파일을 저장해 보겠습니다.

설명: 이 단계에서는 모든 서식이 적용된 제목과 번호 매기기 스타일이 포함된 PDF 파일을 저장합니다.

```csharp
// PDF 문서 저장
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);
```

## 결론

이제 다 됐습니다! Aspose.PDF for .NET을 사용하여 PDF 파일의 제목에 번호 매기기 스타일(로마 숫자와 알파벳)을 성공적으로 적용했습니다. Aspose.PDF가 제공하는 유연성을 통해 페이지 레이아웃, 번호 매기기 스타일, 콘텐츠 위치를 제어할 수 있어 체계적이고 전문적인 PDF 문서를 만드는 데 강력한 도구 세트를 사용할 수 있습니다.

## 자주 묻는 질문

### 동일한 PDF 문서에 다른 숫자 스타일을 적용할 수 있나요?  
네, .NET용 Aspose.PDF를 사용하면 동일한 문서 내에서 로마 숫자, 아라비아 숫자, 알파벳 번호 매기기 등 다양한 번호 매기기 스타일을 혼합하여 사용할 수 있습니다.

### 제목의 시작 번호를 어떻게 사용자 지정할 수 있나요?  
 다음을 사용하여 모든 제목의 시작 번호를 설정할 수 있습니다.`StartNumber` 재산.

### 번호 매기기 순서를 재설정하는 방법이 있나요?  
예, 번호를 조정하여 재설정할 수 있습니다.`StartNumber` 각 제목에 대한 속성입니다.

### 제목에 번호 매기기 외에도 굵게나 기울임체 스타일을 적용할 수 있나요?  
 물론입니다! 글꼴, 크기, 굵게, 기울임체 등의 속성을 수정하여 제목 스타일을 사용자 지정할 수 있습니다.`TextState` 물체.

### Aspose.PDF에 대한 임시 라이선스를 받으려면 어떻게 해야 하나요?  
 임시면허는 다음에서 받을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/) 제한 없이 Aspose.PDF를 테스트하세요.