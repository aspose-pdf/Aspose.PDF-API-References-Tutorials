---
title: Definir Java Script
linktitle: Definir Java Script
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a usar o Aspose.PDF para .NET para definir JavaScript em campos de formulário em arquivos PDF.
type: docs
weight: 270
url: /pt/net/programming-with-forms/set-java-script/
---
Neste guia, vamos explicar passo a passo como usar a biblioteca Aspose.PDF para .NET para definir JavaScript em um campo de formulário de um documento PDF. Mostraremos como configurar ações JavaScript para executar operações específicas no campo de texto.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- Um ambiente de desenvolvimento .NET instalado no seu sistema.
- A biblioteca Aspose.PDF para .NET. Você pode baixá-la do site oficial do Aspose.

## Etapa 1: Configurando o diretório de documentos

 O primeiro passo é configurar o diretório do documento onde o arquivo PDF no qual você deseja trabalhar está localizado. Você pode usar o`dataDir` variável para especificar o caminho do diretório.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Certifique-se de substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real para o diretório dos seus documentos.

## Etapa 2: Carregando o arquivo PDF de entrada

 Nesta etapa, carregaremos o arquivo PDF de entrada usando o`Document` classe de Aspose.PDF.

```csharp
// Carregar arquivo PDF de entrada
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Certifique-se de que o arquivo PDF de entrada esteja presente no diretório de documentos especificado.

## Etapa 3: Acessando o campo TextBox

 Para aplicar JavaScript a um campo de texto específico, primeiro precisamos acessar esse campo. Neste exemplo, assumimos que o campo de texto é chamado de "textbox1". Use o`doc.Form["textbox1"]` método para obter o correspondente`TextBoxField` objeto.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Certifique-se de que o campo de texto especificado exista no arquivo PDF de entrada.

## Etapa 4: Configurar ações JavaScript

 Agora que acessamos o campo de texto, podemos configurar as ações JavaScript associadas a esse campo. Neste exemplo, usaremos duas ações:`OnModifyCharacter` e`OnFormat` . Essas ações serão definidas usando`JavascriptAction` objetos.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Certifique-se de personalizar as ações do JavaScript de acordo com suas necessidades.

## Etapa 5: Definindo o valor do campo inicial

Antes de salvar o PDF resultante, podemos definir um valor inicial para o campo de texto. Neste exemplo, definiremos o valor "123" para o campo.

```csharp
field.Value = "123";
```

Personalize este valor de acordo com suas necessidades.

## Etapa 6: Salvando o PDF resultante

 Agora que terminamos de configurar o campo de texto e as ações JavaScript, podemos salvar o PDF resultante usando o`Save` método do`Document` aula.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Salvar PDF resultante
doc.Save(dataDir);
```

Certifique-se de especificar o caminho completo e o nome do arquivo para o PDF resultante.


### Exemplo de código-fonte para Set Java Script usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carregar arquivo PDF de entrada
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 dígitos depois do ponto
// Sem separador
// Estilo Neg = menos
// Nenhuma moeda
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Definir valor de campo inicial
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Salvar PDF resultante
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Conclusão

Neste guia, aprendemos como usar a biblioteca Aspose.PDF para .NET para definir JavaScript em um campo de formulário de um documento PDF. Seguindo as etapas descritas, você pode personalizar ações JavaScript para executar várias operações em campos de texto. Sinta-se à vontade para explorar mais os recursos do Aspose.PDF para .NET para expandir as possibilidades de manipulação de arquivos PDF.


### Perguntas frequentes

#### P: Posso usar o Aspose.PDF para .NET para adicionar JavaScript a outros elementos de formulário, como caixas de seleção e botões de opção?

 R: Sim, o Aspose.PDF para .NET permite que você adicione JavaScript a vários elementos de formulário, incluindo caixas de seleção, botões de opção e listas suspensas. Você pode usar o`JavascriptAction` classe para definir ações JavaScript para diferentes elementos de formulário.

#### P: É possível validar a entrada do usuário usando JavaScript em campos de formulário?

 R: Sim, você pode usar JavaScript para validar a entrada do usuário em campos de formulário. Ao definir ações JavaScript como`OnBlur` ou`OnKeystroke` para um campo de formulário, você pode validar os dados inseridos e exibir mensagens de erro, se necessário.

#### P: Posso executar funções JavaScript complexas usando Aspose.PDF para .NET?

 R: Sim, você pode executar funções JavaScript complexas usando Aspose.PDF para .NET. Você tem a flexibilidade de definir funções JavaScript personalizadas e chamá-las dentro do`JavascriptAction`.

#### P: O Aspose.PDF para .NET oferece suporte a eventos JavaScript além dos mencionados neste tutorial?

 R: Sim, o Aspose.PDF para .NET oferece suporte a uma ampla variedade de eventos JavaScript, incluindo`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , e`OnMouseUp`, entre outros. Você pode usar esses eventos para disparar ações JavaScript com base nas interações do usuário.

#### P: Posso usar o Aspose.PDF para .NET para extrair código JavaScript de documentos PDF existentes?

 A: Aspose.PDF para .NET fornece a capacidade de extrair código JavaScript de documentos PDF existentes. Você pode usar o`JavascriptAction` classe e outros métodos relevantes para acessar e analisar ações JavaScript em um formulário PDF.