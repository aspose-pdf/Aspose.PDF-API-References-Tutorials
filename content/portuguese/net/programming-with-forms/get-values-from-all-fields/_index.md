---
title: Obter valores de todos os campos no documento PDF
linktitle: Obter valores de todos os campos no documento PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Obtenha facilmente os valores de todos os campos de formulário em um documento PDF com Aspose.PDF para .NET.
type: docs
weight: 150
url: /pt/net/programming-with-forms/get-values-from-all-fields/
---
Neste tutorial, mostraremos como obter os valores de todos os campos de formulário em um documento PDF usando Aspose.PDF para .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo por esse processo.

## Etapa 1: Preparação

Certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Abra o documento

Abra o documento PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Etapa 3: Obtenha valores para todos os campos

Percorra todos os campos de formulário no documento e obtenha seus nomes e valores:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Código-fonte de exemplo para obter valores de todos os campos usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Obter valores de todos os campos
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Conclusão

Neste tutorial, aprendemos como obter os valores de todos os campos de formulário em um documento PDF usando Aspose.PDF para .NET. Seguindo essas etapas, você pode facilmente extrair os valores de todos os campos de formulário de seus documentos PDF usando Aspose.PDF.

### Perguntas frequentes

#### P: Posso modificar os valores dos campos de formulário ao recuperá-los usando o Aspose.PDF para .NET?

 R: Sim, você pode modificar os valores dos campos do formulário enquanto os recupera usando o Aspose.PDF para .NET. Depois de ter o`Field` objeto que representa um campo de formulário, você pode atualizá-lo`Value`propriedade com o valor desejado. Após fazer as alterações necessárias, você pode salvar o documento PDF atualizado para refletir as alterações.

#### P: Como posso filtrar e recuperar campos de formulário específicos com base em seus tipos (por exemplo, campos de texto, caixas de seleção)?

 R: Para recuperar campos de formulário específicos com base em seus tipos, você pode usar instruções condicionais ou consultas LINQ para filtrar os campos de interesse. Você pode verificar o tipo de cada campo de formulário usando o campo`FieldType` propriedade e, em seguida, recuperar os valores adequadamente.

#### P: O que acontece se o documento PDF não tiver campos de formulário?

 R: Se o documento PDF não contiver nenhum campo de formulário, o`pdfDocument.Form` property retornará uma coleção vazia. Nesses casos, o loop para recuperar valores não será executado e nenhum valor será exibido.

#### P: Posso extrair os valores dos campos do formulário em uma ordem específica ou classificá-los em ordem alfabética?

R: A ordem em que os campos do formulário são recuperados depende da estrutura subjacente do documento PDF. O Aspose.PDF for .NET retorna os campos do formulário na ordem em que foram adicionados ao documento. Se você quiser exibir ou processar os campos do formulário em uma ordem específica, você pode implementar uma lógica de classificação personalizada com base em seus requisitos.

#### P: Como posso lidar com documentos PDF criptografados com campos de formulário protegidos por senha?

 A: O Aspose.PDF para .NET fornece recursos para trabalhar com documentos PDF criptografados e campos de formulário protegidos por senha. Antes de carregar o documento, você pode definir a senha usando o`pdfDocument.Password` propriedade para acessar o documento PDF protegido e seus campos de formulário.