---
title: Definir JavaScript
linktitle: Definir JavaScript
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como usar Aspose.PDF for .NET para definir JavaScript em campos de formulário em arquivos PDF.
type: docs
weight: 270
url: /pt/net/programming-with-forms/set-java-script/
---
Neste guia, explicaremos passo a passo como usar a biblioteca Aspose.PDF para .NET para definir JavaScript em um campo de formulário de um documento PDF. Mostraremos como configurar ações JavaScript para realizar operações específicas no campo de texto.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- Um ambiente de desenvolvimento .NET instalado em seu sistema.
- A biblioteca Aspose.PDF para .NET. Você pode baixá-lo no site oficial do Aspose.

## Passo 1: Configurando o diretório do documento

 O primeiro passo é configurar o diretório do documento onde está localizado o arquivo PDF no qual você deseja trabalhar. Você pode usar o`dataDir` variável para especificar o caminho do diretório.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Certifique-se de substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real para o diretório de documentos.

## Passo 2: Carregando o arquivo PDF de entrada

Nesta etapa, carregaremos o arquivo PDF de entrada usando o`Document` classe de Aspose.PDF.

```csharp
// Carregar arquivo PDF de entrada
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Certifique-se de que o arquivo PDF de entrada esteja presente no diretório de documentos especificado.

## Passo 3: Acessando o campo TextBox

 Para aplicar JavaScript a um campo de texto específico, primeiro precisamos acessar esse campo. Neste exemplo, assumimos que o campo de texto é denominado "textbox1". Use o`doc.Form["textbox1"]` método para obter o correspondente`TextBoxField` objeto.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Certifique-se de que o campo de texto especificado exista no arquivo PDF de entrada.

## Etapa 4: configurar ações JavaScript

 Agora que acessamos o campo de texto, podemos configurar as ações JavaScript associadas a este campo. Neste exemplo, usaremos duas ações:`OnModifyCharacter` e`OnFormat` . Essas ações serão definidas usando`JavascriptAction` objetos.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Certifique-se de personalizar as ações JavaScript de acordo com suas necessidades.

## Etapa 5: definir o valor do campo inicial

Antes de salvar o PDF resultante, podemos definir um valor inicial para o campo de texto. Neste exemplo, definiremos o valor “123” para o campo.

```csharp
field.Value = "123";
```

Personalize este valor de acordo com suas necessidades.

## Passo 6: Salvando o PDF resultante

 Agora que terminamos de configurar o campo de texto e as ações JavaScript, podemos salvar o PDF resultante usando o`Save` método do`Document` aula.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Salve o PDF resultante
doc.Save(dataDir);
```

Certifique-se de especificar o caminho completo e o nome do arquivo do PDF resultante.


### Exemplo de código-fonte para definir Java Script usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carregar arquivo PDF de entrada
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 dígitos após o ponto
// Sem separador
// Estilo Neg = menos
// Sem moeda
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Definir valor do campo inicial
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Salvar o PDF resultante
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Conclusão

Neste guia, aprendemos como usar a biblioteca Aspose.PDF para .NET para definir JavaScript em um campo de formulário de um documento PDF. Seguindo as etapas descritas, você pode personalizar ações JavaScript para realizar diversas operações em campos de texto. Sinta-se à vontade para explorar ainda mais os recursos do Aspose.PDF for .NET para expandir as possibilidades de manipulação de arquivos PDF.


### Perguntas frequentes

#### P: Posso usar Aspose.PDF for .NET para adicionar JavaScript a outros elementos de formulário, como caixas de seleção e botões de opção?

 R: Sim, Aspose.PDF for .NET permite adicionar JavaScript a vários elementos de formulário, incluindo caixas de seleção, botões de opção e listas suspensas. Você pode usar o`JavascriptAction` classe para definir ações JavaScript para diferentes elementos do formulário.

#### P: É possível validar a entrada do usuário usando JavaScript nos campos do formulário?

 R: Sim, você pode usar JavaScript para validar a entrada do usuário nos campos do formulário. Ao definir ações JavaScript como`OnBlur` ou`OnKeystroke` para um campo de formulário, é possível validar os dados inseridos e exibir mensagens de erro, se necessário.

#### P: Posso executar funções JavaScript complexas usando Aspose.PDF for .NET?

 R: Sim, você pode executar funções JavaScript complexas usando Aspose.PDF for .NET. Você tem a flexibilidade de definir funções JavaScript personalizadas e chamá-las dentro do`JavascriptAction`.

#### P: O Aspose.PDF for .NET oferece suporte a eventos JavaScript diferentes dos mencionados neste tutorial?

 R: Sim, Aspose.PDF for .NET oferece suporte a uma ampla variedade de eventos JavaScript, incluindo`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , e`OnMouseUp`, entre outros. Você pode usar esses eventos para acionar ações JavaScript com base nas interações do usuário.

#### P: Posso usar o Aspose.PDF for .NET para extrair código JavaScript de documentos PDF existentes?

 R: Aspose.PDF for .NET oferece a capacidade de extrair código JavaScript de documentos PDF existentes. Você pode usar o`JavascriptAction` class e outros métodos relevantes para acessar e analisar ações JavaScript em formato PDF.