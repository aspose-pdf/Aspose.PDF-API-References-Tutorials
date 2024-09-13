---
title: PDF 파일의 바닥글에 있는 텍스트
linktitle: PDF 파일의 바닥글에 있는 텍스트
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일의 바닥글에 텍스트를 쉽게 추가하는 방법을 알아보세요. 원활한 통합을 위해 단계별 가이드가 포함되어 있습니다.
type: docs
weight: 180
url: /ko/net/programming-with-stamps-and-watermarks/text-in-footer/
---
## 소개

Aspose.PDF for .NET을 사용하여 PDF 파일의 바닥글에 사용자 정의 텍스트를 추가하려고 합니까? 당신은 올바른 곳에 있습니다! 페이지 번호, 날짜 또는 기타 사용자 정의 텍스트를 포함하든 이 튜토리얼은 전체 프로세스를 안내합니다. 강력한 PDF 조작 라이브러리인 Aspose.PDF를 사용하면 바닥글을 추가하는 것이 매우 쉽습니다. 이 문서에서는 PDF 파일의 모든 페이지의 바닥글에 텍스트를 추가하는 단계별 프로세스를 살펴보겠습니다. 빠르고 간단하며 .NET 애플리케이션에서 PDF 사용자 정의를 자동화하려는 사람들에게 완벽합니다.


## 필수 조건

코딩에 들어가기 전에 모든 것이 준비되었는지 확인해 보겠습니다.

-  .NET용 Aspose.PDF: .NET용 Aspose.PDF가 설치되어 있는지 확인하세요. 설치되어 있지 않으면 다음을 수행할 수 있습니다.[여기서 다운로드하세요](https://releases.aspose.com/pdf/net/).
- IDE: Visual Studio와 같은 개발 환경이 필요합니다.
- C#에 대한 기본 지식: C# 및 .NET에 대한 기본적인 이해가 필요합니다.
-  라이센스: Aspose.PDF를 평가 모드로 사용할 수 있지만 전체 기능을 사용하려면 다음을 고려하세요.[무료 체험](https://releases.aspose.com/) 또는 신청[임시 면허](https://purchase.aspose.com/temporary-license/).

## 패키지 가져오기

코딩 부분을 시작하기 전에 필요한 네임스페이스를 가져오세요. 이렇게 하면 Aspose.PDF 라이브러리의 클래스와 메서드가 프로젝트에서 사용 가능하게 됩니다.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

이제 준비가 되었으니, PDF 파일의 바닥글에 텍스트를 추가하는 과정을 쉽게 따라할 수 있는 단계로 나누어 보겠습니다.

## 1단계: 프로젝트 초기화 및 문서 디렉토리 설정

PDF 파일을 작업하기 전에 문서 디렉토리 경로를 지정해야 합니다. 여기가 PDF 파일이 있는 위치이며 수정된 파일이 저장되는 위치입니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 여기서 교체하세요`"YOUR DOCUMENT DIRECTORY"` 폴더의 실제 경로와 함께. 이 폴더는 원본 PDF 파일을 포함하고 수정된 파일의 출력 위치로도 사용됩니다.

## 2단계: PDF 문서 로드

 다음 단계는 PDF 파일을 프로젝트에 로드하는 것입니다.`Document` Aspose.PDF의 클래스를 사용하면 기존 PDF 문서를 열고 조작할 수 있습니다.

```csharp
// 문서 열기
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

 여기,`TextinFooter.pdf` 는 우리가 작업하는 파일입니다. 이것을 자신의 파일 이름으로 바꿀 수 있습니다.

## 3단계: 바닥글 텍스트 만들기

이제 각 페이지에 찍힐 바닥글 텍스트를 만들어 보겠습니다. 이것은 다음을 사용하여 수행됩니다.`TextStamp` 클래스. 정의한 텍스트는 모든 페이지의 바닥글로 사용됩니다.

```csharp
// 푸터 만들기
TextStamp textStamp = new TextStamp("Footer Text");
```

이 경우, "Footer Text"라는 간단한 푸터 텍스트를 만들었습니다. 자유롭게 자신의 메시지로 이것을 사용자 정의하세요. 원한다면 "Confidential" 또는 페이지 번호와 같은 것이 될 수 있습니다.

## 4단계: 바닥글 속성 설정

 푸터를 올바르게 배치하려면 여백, 정렬 및 위치 지정과 같은 일부 속성을 조정해야 합니다.`TextStamp` 클래스를 사용하면 바닥글 텍스트가 어디에 어떻게 표시되는지 완벽하게 제어할 수 있습니다.

```csharp
// 스탬프의 속성 설정
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

여기서는 하단 여백을 10단위로 설정하고, 텍스트를 수평으로 중앙에 정렬하고, 수직으로 페이지 하단에 배치했습니다. 특정 레이아웃 요구 사항에 따라 이러한 값을 조정할 수 있습니다.

## 5단계: 모든 페이지에 바닥글 적용

이제 재밌는 부분이 왔습니다. PDF의 모든 페이지에 푸터를 적용하는 것입니다. 문서의 모든 페이지를 반복하면서 각 페이지에 푸터 텍스트를 추가할 수 있습니다.

```csharp
// 모든 페이지에 바닥글 추가
foreach (Page page in pdfDocument.Pages)
{
    page.AddStamp(textStamp);
}
```

이 루프는 PDF 페이지 수에 관계없이 문서의 모든 페이지에 바닥글이 찍히도록 보장합니다.

## 6단계: 업데이트된 PDF 파일 저장

모든 페이지에 바닥글을 추가한 후 마지막 단계는 수정된 PDF 파일을 지정된 디렉토리에 저장하는 것입니다.

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
// 업데이트된 PDF 파일을 저장하세요
pdfDocument.Save(dataDir);
```

 우리는 새 이름으로 파일을 저장하고 있습니다.`TextinFooter_out.pdf`, 같은 디렉토리에 있습니다. 필요에 따라 이름을 자유롭게 바꾸세요.

## 7단계: 성공 확인

마지막으로 콘솔에 성공 메시지를 인쇄하여 사용자에게 PDF가 성공적으로 업데이트되었음을 알립니다.

```csharp
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);
```

그리고 그게 전부입니다! PDF의 모든 페이지의 바닥글에 텍스트를 성공적으로 추가했습니다.

## 결론

Aspose.PDF for .NET을 사용하여 PDF 문서에 푸터를 추가하는 것은 PDF 파일을 사용자 정의하는 간단하고 강력한 방법입니다. 몇 줄의 코드만 있으면 날짜, 제목 또는 페이지 번호와 같은 개인화된 텍스트를 문서의 모든 페이지에 추가할 수 있습니다. 이 가이드를 따르면 이제 .NET 애플리케이션에서 이 기능을 구현하는 지식을 갖추게 되었습니다.

## 자주 묻는 질문

### PDF의 각 페이지에 다른 바닥글을 추가할 수 있나요?  
 예, 다른 것을 지정하여 각 페이지에 고유한 바닥글을 추가할 수 있습니다.`TextStamp` 각 페이지에 대한 개체입니다.

### 바닥글 텍스트의 글꼴 스타일을 어떻게 변경합니까?  
 다음을 사용하여 텍스트를 사용자 정의할 수 있습니다.`TextStamp.TextState` 글꼴, 크기, 색상을 설정하는 속성입니다.

### 텍스트 대신 푸터에 이미지를 추가할 수 있나요?  
 네, 사용할 수 있습니다`ImageStamp` PDF 파일의 바닥글에 이미지를 추가합니다.

### 특정 페이지에만 바닥글을 추가할 수 있나요?  
 물론입니다! 특정 대상을 타겟팅하여 바닥글을 원하는 페이지 번호를 지정할 수 있습니다.`Page` 사물.

### PDF에서 기존 바닥글을 제거하려면 어떻게 해야 합니까?  
 기존 스탬프를 지울 수 있습니다.`Page.DeleteStampById` 방법 또는 사용`RemoveStamp` 모든 우표를 제거하세요.