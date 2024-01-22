---
title: Obtenha o fator de zoom no arquivo PDF
linktitle: Obtenha o fator de zoom no arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como usar Aspose.PDF for .NET para obter o fator de zoom em um arquivo PDF com este guia passo a passo.
type: docs
weight: 210
url: /pt/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET é uma biblioteca de manipulação de PDF que oferece muitos recursos para realizar diversas operações em documentos PDF. Um desses recursos é a capacidade de obter o fator de zoom no arquivo PDF. Neste tutorial, explicaremos como usar Aspose.PDF for .NET para obter o fator de zoom no arquivo PDF usando código-fonte C#.


## Etapa 1: instanciar o novo objeto Document

 O primeiro passo para obter o fator de zoom de um arquivo PDF usando Aspose.PDF for .NET é instanciar um novo`Document` objeto. O`Document` objeto representa um documento PDF que pode ser carregado de um arquivo ou fluxo.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar novo objeto Document
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 No código acima, criamos um`Document` objeto passando o caminho do arquivo PDF para o construtor do`Document` aula. Você precisa substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real do diretório onde seu arquivo PDF está localizado.

## Etapa 2: criar o objeto GoToAction

 O próximo passo é criar um`GoToAction` objeto. A`GoToAction`objeto representa uma ação que vai para um destino específico em um documento PDF. No nosso caso, queremos obter o fator de zoom do arquivo PDF, então usaremos o`OpenAction` propriedade do`Document` objeto para obter o`GoToAction` objeto.

```csharp
// Criar objeto GoToAction
GoToAction action = doc.OpenAction as GoToAction;
```

 No código acima, criamos um`GoToAction` objeto lançando o`OpenAction` propriedade do`Document` opor-se a`GoToAction`.

## Passo 3: Obtenha o fator de zoom do arquivo PDF

 A terceira etapa é obter o fator de zoom do arquivo PDF. Podemos obter o fator de zoom do arquivo PDF acessando o`Destination` propriedade do`GoToAction` objeto e, em seguida, lançando-o para`XYZExplicitDestination` . O`XYZExplicitDestination` class representa um destino em um documento PDF que especifica as coordenadas e o fator de zoom para onde ir.

```csharp
// Obtenha o fator de zoom do arquivo PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valor de zoom do documento;
```

 No código acima, acessamos o`Destination` propriedade do`GoToAction` objeto e, em seguida, lance-o para`XYZExplicitDestination` . Depois disso, acessamos o`Zoom` propriedade do`XYZExplicitDestination` objeto para obter o fator de zoom do arquivo PDF.

## Etapa 4: produza o fator de zoom

 A etapa final é gerar o fator de zoom do arquivo PDF. Podemos usar o`System.Console.WriteLine`

```csharp
// Obtenha o fator de zoom do arquivo PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valor de zoom do documento;
```        

### Exemplo de código-fonte para obter fator de zoom usando Aspose.PDF para .NET

Aqui está o exemplo de código-fonte completo para obter fator de zoom usando Aspose.PDF para .NET:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar novo objeto Document
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// Criar objeto GoToAction
GoToAction action = doc.OpenAction as GoToAction;

// Obtenha o fator de zoom do arquivo PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valor de zoom do documento;
```

## Conclusão

Neste tutorial, exploramos como usar Aspose.PDF for .NET para obter o fator de zoom de um arquivo PDF. O fator de zoom é um aspecto crucial de um documento PDF, pois determina o tamanho inicial de exibição quando aberto em um visualizador. Ao acessar e utilizar o fator de zoom, os desenvolvedores podem personalizar a experiência de visualização dos usuários finais. Aspose.PDF for .NET fornece uma API simples e eficaz para recuperar o fator de zoom e outras informações relacionadas à navegação de um documento PDF, capacitando os desenvolvedores a criar aplicativos PDF interativos e ricos em recursos.

### Perguntas frequentes para obter fator de zoom em arquivo PDF

#### P: Qual é o fator de zoom em um arquivo PDF?

R: O fator de zoom em um arquivo PDF refere-se ao nível de ampliação aplicado ao documento quando ele é visualizado. Determina o tamanho inicial de exibição do arquivo PDF na tela. Um fator de zoom de 1,0 representa o tamanho real (zoom de 100%), enquanto um fator de zoom maior que 1,0 representa uma ampliação e um fator de zoom menor que 1,0 representa uma redução.

#### P: Como posso usar as informações do fator de zoom em meu aplicativo?

R: Você pode usar as informações do fator de zoom para personalizar o tamanho de exibição inicial de um documento PDF quando ele é aberto em um visualizador. Por exemplo, você pode definir um fator de zoom específico para garantir que o PDF seja exibido em um tamanho específico ou ajuste a página inteira à janela do visualizador.

#### P: Posso modificar o fator de zoom de um documento PDF programaticamente usando Aspose.PDF for .NET?

 R: Sim, você pode modificar o fator de zoom de um documento PDF programaticamente usando Aspose.PDF for .NET. Você pode definir o fator de zoom para ações específicas, como`GoToAction` ou`GoToRemoteAction`para controlar como o documento é exibido quando o usuário interage com links ou marcadores.

#### P: Existem outras maneiras de navegar para locais específicos em um documento PDF usando Aspose.PDF for .NET?

 R: Sim, o Aspose.PDF for .NET oferece vários recursos para navegar para locais específicos em um documento PDF. Além de usar`GoToAction` , você pode usar outras ações como`GoToURIAction` para abrir um URL,`GoToEmbeddedAction` para navegar até arquivos incorporados e`GoToNamedAction` para ir para destinos nomeados no documento PDF.