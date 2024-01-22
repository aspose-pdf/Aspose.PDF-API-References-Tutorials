---
title: PDF 페이지 크기 업데이트
linktitle: PDF 페이지 크기 업데이트
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 페이지 크기를 업데이트하는 단계별 가이드입니다. 필요에 따라 치수를 확인하십시오.
type: docs
weight: 150
url: /ko/net/programming-with-pdf-pages/update-dimensions/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서의 페이지 크기를 업데이트하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 Aspose.PDF for .NET을 사용하여 PDF 문서의 페이지 크기를 변경하는 방법을 알게 됩니다.

## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식
- 개발 환경에 설치된 .NET용 Aspose.PDF

## 1단계: 문서 디렉터리 정의
먼저 문서 디렉터리의 경로를 설정해야 합니다. 편집한 PDF 문서를 저장하려는 위치입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: PDF 문서 열기
 그런 다음 다음을 사용하여 기존 PDF 문서를 열 수 있습니다.`Document` Aspose.PDF의 클래스입니다. 올바른 문서 경로를 지정하십시오.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 3단계: 페이지 컬렉션 가져오기
 이제 다음을 사용하여 PDF 문서의 페이지 컬렉션에 액세스할 수 있습니다.`Pages` 의 재산`Document` 수업.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 4단계: 특정 페이지 가져오기
그런 다음 컬렉션에 있는 페이지의 색인을 사용하여 문서의 특정 페이지를 선택할 수 있습니다. 이 예에서는 두 번째 페이지(인덱스 1)를 사용하고 있습니다.

```csharp
Page pdfPage = pageCollection[1];
```

## 5단계: 새 페이지 차원 정의
 이제 다음을 사용하여 새 페이지 크기를 설정할 수 있습니다.`SetPageSize()` 의 방법`Page`물체. 이 예에서는 페이지 크기를 A4(11.7 x 8.3인치)로 설정하고 포인트(1인치 = 72포인트)로 변환합니다.

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## 6단계: 업데이트된 문서 저장
 마지막으로 다음을 사용하여 업데이트된 PDF 문서를 파일로 저장할 수 있습니다.`Save()` 의 방법`Document`수업. 올바른 경로와 파일 이름을 지정하십시오.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하는 Update Dimensions의 샘플 소스 코드 

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// 페이지 컬렉션 가져오기
PageCollection pageCollection = pdfDocument.Pages;
// 특정 페이지 가져오기
Page pdfPage = pageCollection[1];
// 페이지 크기를 A4(11.7 x 8.3인치)로 설정하고 Aspose.Pdf에서는 1인치 = 72포인트로 설정합니다.
// 따라서 A4 크기(포인트)는 (842.4, 597.6)입니다.
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// 업데이트된 문서 저장
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서의 페이지 크기를 업데이트하는 방법을 배웠습니다. 이 단계별 가이드를 따르면 필요에 따라 PDF 문서의 페이지 크기를 쉽게 변경할 수 있습니다. Aspose.PDF는 PDF 파일 작업 및 페이지 크기 변경을 포함한 다양한 조작을 수행하기 위한 강력하고 유연한 API를 제공합니다. 이러한 지식을 바탕으로 특정 요구 사항에 맞게 PDF 페이지의 크기를 제어하고 사용자 정의할 수 있습니다.

### PDF 페이지 크기 업데이트에 대한 FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 특정 페이지의 크기를 어떻게 업데이트할 수 있습니까?

A: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 특정 페이지의 크기를 업데이트하려면 다음 단계를 따르세요.

1. 원본 PDF 파일이 있는 경로와 업데이트된 PDF 파일을 저장할 위치를 지정하여 문서 디렉터리를 설정하세요. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.
2.  업데이트할 기존 PDF 문서를 엽니다.`Document` Aspose.PDF의 클래스입니다. 원본 PDF 문서의 올바른 경로를 지정하십시오.
3.  다음을 사용하여 PDF 문서의 페이지 컬렉션에 액세스합니다.`Pages` 의 재산`Document` 수업.
4. 페이지 색인을 사용하여 페이지 컬렉션에서 업데이트하려는 특정 페이지를 선택합니다. 제공된 C# 소스 코드에서는 두 번째 페이지(인덱스 1)를 사용하고 있습니다.
5.  다음을 사용하여 새 페이지 크기를 정의합니다.`SetPageSize()` 의 방법`Page` 물체. 예제에서는 페이지 크기를 A4 크기(11.7 x 8.3인치)로 설정하고 포인트(1인치 = 72포인트)로 변환했습니다.
6.  다음을 사용하여 업데이트된 PDF 문서를 파일로 저장합니다.`Save()` 의 방법`Document`수업. 올바른 경로와 파일 이름을 지정하십시오.

#### Q: PDF 문서에서 여러 페이지의 크기를 동시에 업데이트할 수 있습니까?

A: 예, 제공된 소스 코드를 수정하여 PDF 문서의 여러 페이지 크기를 동시에 업데이트할 수 있습니다. 특정 페이지를 선택하는 대신(4단계 참조) 페이지 컬렉션의 모든 페이지를 반복하여 각 페이지에 대해 원하는 페이지 크기를 설정할 수 있습니다.

#### Q: .NET용 Aspose.PDF를 사용할 때 페이지 치수를 인치에서 포인트로 어떻게 변환합니까?

 A: .NET용 Aspose.PDF에서 페이지 크기에 사용되는 측정 단위는 포인트입니다. 여기서 1인치는 72포인트에 해당합니다. 인치를 포인트로 변환하려면 다음 공식을 사용할 수 있습니다.`points = inches * 72`. 예를 들어, 페이지 크기를 11.7 x 8.3인치로 설정하려면 해당 치수를 (11.7 * 72) 및 (8.3 * 72)로 포인트 단위로 계산할 수 있습니다.

#### 질문: 페이지 크기를 업데이트하면 PDF 문서의 내용 레이아웃에 영향을 미치나요?

A: 예, 페이지 크기를 업데이트하면 해당 페이지의 PDF 문서 내용 레이아웃에 영향을 미칩니다. 페이지 크기를 변경하면 페이지의 콘텐츠가 새 크기에 맞게 조정됩니다.

#### Q: 업데이트 후 변경 사항을 되돌리고 원래 페이지 크기를 복원할 수 있습니까?

A: 예, 변경 사항을 되돌리고 원래 페이지 크기를 복원하려면 변경하기 전에 원본 PDF 문서의 복사본을 보관하거나 변경 사항을 저장하지 않고 원본 PDF 문서를 다시 열 수 있습니다. 이렇게 하면 원래 치수가 유지됩니다.