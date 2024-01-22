---
title: XFA dinâmico para formulário Acro
linktitle: XFA dinâmico para formulário Acro
second_title: Referência da API Aspose.PDF para .NET
description: Converta facilmente formulários XFA To dinâmicos em formulários AcroForm padrão com Aspose.PDF para .NET.
type: docs
weight: 70
url: /pt/net/programming-with-forms/dynamic-xfa-to-acro-form/
---
Neste tutorial, mostraremos como converter um formulário XFA To dinâmico em um AcroForm usando Aspose.PDF para .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo neste processo.

## Etapa 1: Preparação

Primeiro, certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: carregar o formulário XFA dinâmico

Carregue o formulário XFA dinâmico:

```csharp
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
```

## Etapa 3: definir o tipo de formulário como AcroForm padrão

Defina o tipo de formulário como AcroForm padrão:

```csharp
document.Form.Type = FormType.Standard;
```

## Etapa 4: salve o PDF resultante

Salve o PDF resultante:

```csharp
dataDir = dataDir + "Standard_AcroForm_out.pdf";
document. Save(dataDir);
```

### Exemplo de código-fonte para Dynamic XFA To Acro Form usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carregar formulário XFA dinâmico
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
// Defina o tipo de campos do formulário como AcroForm padrão
document.Form.Type = FormType.Standard;
dataDir = dataDir + "Standard_AcroForm_out.pdf";
// Salve o PDF resultante
document.Save(dataDir);
Console.WriteLine("\nDynamic XFA form converted to standard AcroForm successfully.\nFile saved at " + dataDir);
```

## Conclusão

Neste tutorial, aprendemos como converter um formulário XFA To dinâmico em um formulário AcroForm padrão usando Aspose.PDF para .NET. Seguindo essas etapas, você pode converter facilmente seus formulários XFATo dinâmicos em AcroForms para uso mais comum.

### Perguntas frequentes

#### P: Qual é a diferença entre um formulário XFA dinâmico e um AcroForm padrão?

R: Um formulário XFA (XML Forms Architecture) dinâmico é um tipo de formulário PDF que usa dados baseados em XML para definir seu layout e comportamento. Os formulários XFA são frequentemente usados em formulários interativos e com uso intensivo de dados. Por outro lado, um AcroForm padrão é um tipo mais tradicional de formulário PDF que utiliza o próprio formato PDF para definir sua estrutura e aparência. AcroForms são amplamente suportados por visualizadores de PDF e podem ser mais compatíveis com vários aplicativos.

#### P: Por que eu desejaria converter um formulário XFA dinâmico em um AcroForm padrão?

R: A conversão de um formulário XFA dinâmico em um AcroForm padrão pode ser útil em cenários onde os formulários XFA não são totalmente suportados ou quando você deseja obter maior compatibilidade com diferentes visualizadores e aplicativos de PDF. Os AcroForms padrão geralmente são mais amplamente suportados em diferentes plataformas e dispositivos.

#### P: Posso modificar os campos do formulário após converter um formulário XFA dinâmico em um AcroForm padrão?

R: Sim, depois de converter um formulário XFA dinâmico em um AcroForm padrão, você pode modificar os campos do formulário conforme necessário usando Aspose.PDF para .NET. Você pode adicionar novos campos, alterar suas propriedades, definir valores de campos e realizar outras operações relacionadas ao formulário.

#### P: Há alguma limitação ou consideração ao converter formulários XFA dinâmicos em AcroForms padrão?

R: Sim, há algumas limitações a serem consideradas ao converter formulários XFA dinâmicos em AcroForms padrão. Os formulários XFA podem ter layouts complexos e dinâmicos, incluindo recursos como tabelas dinâmicas, seções repetidas e cálculos de formulário, que podem não ser totalmente preservados no processo de conversão. Além disso, algumas propriedades específicas de campos de formulário exclusivas dos formulários XFA podem não ser aplicáveis no AcroForms.

#### P: Posso converter um AcroForm padrão em um formulário XFA dinâmico usando Aspose.PDF para .NET?

R: Aspose.PDF para .NET atualmente oferece suporte à conversão de formulários XFA dinâmicos em AcroForms padrão, mas não oferece suporte à operação reversa de conversão de AcroForms padrão em formulários XFA dinâmicos. A conversão de AcroForms padrão em formulários XFA dinâmicos envolve transformações mais complexas e pode não ser totalmente suportada em todos os cenários.