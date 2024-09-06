---
title: Achatar formulários em documento PDF
linktitle: Achatar formulários em documento PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Simplifique facilmente formulários em documentos PDF usando o Aspose.PDF para .NET.
type: docs
weight: 100
url: /pt/net/programming-with-forms/flatten-forms/
---
Neste tutorial, mostraremos como achatar formulários usando Aspose.PDF para .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo por esse processo.

## Etapa 1: Preparação

Primeiro, certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Carregar formulário PDF de origem

Carregue o formulário PDF de origem:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Etapa 3: achatar os formulários

Primeiro, verifique se há algum campo de formulário no documento. Se houver, itere por cada campo e aplique achatamento:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Etapa 4: Salve o documento atualizado

Salve o documento PDF atualizado:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Exemplo de código-fonte para Flatten Forms usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carregar formulário PDF de origem
Document doc = new Document(dataDir + "input.pdf");
// Achatar formulários
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Salvar o documento atualizado
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Conclusão

Neste tutorial, aprendemos como achatar formulários usando o Aspose.PDF para .NET. Seguindo essas etapas, você pode achatar formulários facilmente em seus documentos PDF, tornando campos não editáveis e mesclando anotações com o conteúdo do documento.

### Perguntas frequentes

#### P: O que significa "nivelar formulários" no Aspose.PDF para .NET?

R: Achatar formulários no Aspose.PDF para .NET se refere ao processo de tornar campos de formulário em um documento PDF não editáveis e mesclar anotações (como campos de formulário, anotações e assinaturas digitais) com o conteúdo do documento. Depois que os formulários são achatados, os usuários não podem modificar os campos do formulário, e a aparência visual dos campos do formulário se torna parte do conteúdo estático do documento PDF.

#### P: Posso reverter o processo de achatamento e tornar os campos do formulário editáveis novamente?

R: Não, uma vez que os campos do formulário são achatados, o processo é irreversível usando o Aspose.PDF para .NET. O achatamento mescla permanentemente a aparência dos campos do formulário com o conteúdo do PDF, e os elementos individuais dos campos do formulário não são mais acessíveis ou editáveis.

#### P: Quando devo nivelar formulários em um documento PDF?

R: O achatamento de formulários é útil quando você quer preservar a aparência visual dos campos de formulário e anotações em um documento PDF, ao mesmo tempo em que impede que os usuários modifiquem os dados. Isso é feito comumente quando você quer compartilhar um documento PDF com dados de formulário pré-preenchidos ou anotações que não devem ser alteradas pelos destinatários.

#### P: O nivelamento de formulários afetará outras anotações, como assinaturas digitais?

R: Sim, o achatamento de formulários mesclará todas as anotações, incluindo assinaturas digitais, com o conteúdo do PDF. Depois que os formulários forem achatados, todas as assinaturas digitais existentes se tornarão uma parte permanente do documento, e os usuários não poderão modificá-las ou removê-las.

#### P: Posso simplificar seletivamente campos específicos do formulário e deixar outros editáveis?

R: Sim, você pode achatar seletivamente campos de formulário específicos em um documento PDF enquanto deixa outros editáveis. Em vez de usar o código para achatar todos os campos de formulário, você pode escolher achatar apenas os campos de formulário desejados com base em seus nomes ou outros critérios.