---
title: PDF 페이지 크기 업데이트
linktitle: PDF 페이지 크기 업데이트
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 페이지 치수를 업데이트하는 단계별 가이드. 필요에 따라 치수를 확인하세요.
type: docs
weight: 150
url: /ko/net/programming-with-pdf-pages/update-dimensions/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서의 페이지 크기를 업데이트하는 단계별 프로세스를 안내합니다. 번들된 C# 소스 코드를 설명하고 이 기능을 이해하고 자신의 프로젝트에서 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼을 마치면 Aspose.PDF for .NET을 사용하여 PDF 문서의 페이지 크기를 변경하는 방법을 알게 됩니다.

## 필수 조건
시작하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식
- 개발 환경에 설치된 .NET용 Aspose.PDF

## 1단계: 문서 디렉토리 정의
먼저, 문서 디렉토리 경로를 설정해야 합니다. 편집한 PDF 문서를 저장할 위치입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: PDF 문서 열기
 그런 다음 기존 PDF 문서를 다음을 사용하여 열 수 있습니다.`Document` Aspose.PDF 클래스입니다. 올바른 문서 경로를 지정해야 합니다.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 3단계: 페이지 컬렉션 가져오기
 이제 다음을 사용하여 PDF 문서의 페이지 컬렉션에 액세스할 수 있습니다.`Pages` 의 속성`Document` 수업.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 4단계: 특정 페이지 가져오기
그런 다음 컬렉션의 페이지 인덱스를 사용하여 문서의 특정 페이지를 선택할 수 있습니다. 이 예에서는 두 번째 페이지(인덱스 1)를 사용합니다.

```csharp
Page pdfPage = pageCollection[1];
```

## 5단계: 새 페이지 크기 정의
 이제 다음을 사용하여 새 페이지 크기를 설정할 수 있습니다.`SetPageSize()` 의 방법`Page`객체. 이 예에서, 우리는 페이지 크기를 A4(11.7 x 8.3인치)로 설정하고 포인트로 변환합니다(1인치 = 72포인트).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## 6단계: 업데이트된 문서 저장
 마지막으로 업데이트된 PDF 문서를 다음을 사용하여 파일에 저장할 수 있습니다.`Save()` 의 방법`Document`클래스. 올바른 경로와 파일 이름을 지정해야 합니다.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 차원 업데이트를 위한 샘플 소스 코드 

```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// 페이지 컬렉션 가져오기
PageCollection pageCollection = pdfDocument.Pages;
// 특정 페이지 가져오기
Page pdfPage = pageCollection[1];
// 페이지 크기를 A4(11.7 x 8.3인치)로 설정하고 Aspose.Pdf에서는 1인치 = 72포인트로 설정합니다.
// 따라서 A4의 포인트 단위 치수는 (842.4, 597.6)이 됩니다.
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// 업데이트된 문서를 저장합니다
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## 결론
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서의 페이지 크기를 업데이트하는 방법을 알아보았습니다. 이 단계별 가이드를 따르면 필요에 따라 PDF 문서의 페이지 크기를 쉽게 변경할 수 있습니다. Aspose.PDF는 PDF 파일을 사용하고 페이지 크기를 변경하는 것을 포함한 다양한 조작을 수행하기 위한 강력하고 유연한 API를 제공합니다. 이러한 지식을 바탕으로 특정 요구 사항에 맞게 PDF 페이지의 크기를 제어하고 사용자 정의할 수 있습니다.

### PDF 페이지 크기 업데이트를 위한 FAQ

#### 질문: Aspose.PDF for .NET을 사용하여 PDF 문서의 특정 페이지의 크기를 업데이트하려면 어떻게 해야 합니까?

답변: Aspose.PDF for .NET을 사용하여 PDF 문서의 특정 페이지의 크기를 업데이트하려면 다음 단계를 따르세요.

1. 원본 PDF 파일이 있는 경로와 업데이트된 PDF 파일을 저장할 위치를 지정하여 문서 디렉토리를 설정합니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꿉니다.
2.  기존 PDF 문서를 열어 업데이트하려면 다음을 사용합니다.`Document` Aspose.PDF 클래스입니다. 원본 PDF 문서에 대한 올바른 경로를 지정해야 합니다.
3.  PDF 문서의 페이지 컬렉션에 액세스하려면 다음을 사용하세요.`Pages` 의 속성`Document` 수업.
4. 페이지 인덱스를 사용하여 페이지 컬렉션에서 업데이트하려는 특정 페이지를 선택합니다. 제공된 C# 소스 코드에서 두 번째 페이지(인덱스 1)를 사용하고 있습니다.
5.  새 페이지 크기를 정의하려면 다음을 사용합니다.`SetPageSize()` 의 방법`Page` 객체. 이 예에서 우리는 페이지 크기를 A4 크기(11.7 x 8.3인치)로 설정했고, 포인트로 변환했습니다(1인치 = 72포인트).
6.  업데이트된 PDF 문서를 파일에 저장하려면 다음을 사용합니다.`Save()` 의 방법`Document`클래스. 올바른 경로와 파일 이름을 지정해야 합니다.

#### 질문: PDF 문서의 여러 페이지의 크기를 동시에 업데이트할 수 있나요?

A: 네, 제공된 소스 코드를 수정하여 PDF 문서의 여러 페이지의 크기를 동시에 업데이트할 수 있습니다. 특정 페이지를 선택하는 대신(4단계에 표시된 대로) 페이지 컬렉션의 모든 페이지를 반복하고 각 페이지에 대해 원하는 페이지 크기를 설정할 수 있습니다.

#### 질문: Aspose.PDF for .NET을 사용할 때 페이지 크기를 인치에서 포인트로 변환하려면 어떻게 해야 합니까?

 A: Aspose.PDF for .NET에서 페이지 치수에 사용되는 측정 단위는 포인트이며, 1인치는 72포인트와 같습니다. 인치를 포인트로 변환하려면 다음 공식을 사용할 수 있습니다.`points = inches * 72`예를 들어, 11.7 x 8.3인치의 페이지 크기를 설정하려면 (11.7 * 72) 및 (8.3 * 72)로 해당 치수를 포인트로 계산할 수 있습니다.

#### 질문: 페이지의 크기를 업데이트하면 PDF 문서의 콘텐츠 레이아웃에 영향을 미칩니까?

A: 네, 페이지의 크기를 업데이트하면 해당 특정 페이지의 PDF 문서 콘텐츠 레이아웃에 영향을 미칩니다. 페이지 크기를 변경하면 페이지의 콘텐츠가 새 크기에 맞게 조정됩니다.

#### 질문: 업데이트한 후 변경 사항을 되돌리고 원래 페이지 크기로 복원하는 것이 가능합니까?

A: 네, 변경 사항을 되돌리고 원래 페이지 크기를 복원하려면 변경하기 전에 원래 PDF 문서의 사본을 보관하거나 변경 사항을 저장하지 않고 원래 PDF 문서를 다시 열 수 있습니다. 이렇게 하면 원래 크기가 보존됩니다.