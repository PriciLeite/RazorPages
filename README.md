# Breve histórico sobre as RazorPages:
## Acompanhe...

 As Razor Pages são estruturas de modelo de página baseada em diretório.
 É uma abordagem baseada em "Code-Behind" (Código por trás) onde a lógica de negócios é incluída em um arquivo .cshtml.cs.
 Esse modelo ajuda a manter a lógica da página coesa em um único arquivo, tornando a manutenção da aplicação mais fácil.
 No entanto, houve significativa evolução com a criação das Views com Model, que são as  tradicionais páginas de renderização em ASP.NET Core. 

 As Views passaram a contêr apenas o HTML e os elementos de design da página, enquanto a lógica de negócios é mantida em um arquivo separado, como um controlador. 
 Nesse modelo, as Views são simplesmente responsáveis por renderizar os dados fornecidos pelo controlador.

A principal diferença entre Razor Pages e Views com Model está na estrutura da aplicação. Enquanto as Razor Pages oferecem uma maneira de 
manter a lógica da página e a exibição em um único arquivo, Views com Model permitem que você separe a lógica de negócios e a exibição em arquivos diferentes.

Lembrando que, as páginas Razor são redenizadas do lado do servidor, portanto o tempo de retorno é maior em comparação ás rendezições do lado do cliente.

### Estrutura Razor Pages:
Pages/ <br/>
_ViewStart.cshtml  <br/>
_ViewImports.cshtml <br/>
Index.cshtml <br/>
Index.cshtml.cs <br/>
Privacy.cshtml <br/>
Privacy.cshtml.cs <br/>
... (outras páginas)

### Estrutura Views com Model:
Controllers/<br/>
HomeController.cs<br/>
Views/<br/>
Home/<br/>
Index.cshtml<br/>
Privacy.cshtml<br/>
... (outras Views)<br/>
Shared/<br/>
_Layout.cshtml<br/>
_ValidationScriptsPartial.cshtml<br/>
... (outras Views compartilhadas)

# Entendendo um pouco mais sobre a configuração do código do projeto...
## Acompanhe:
- Em Pages temos o arquivo Index.cshtml.cs, onde está contido a regra de négocio. 
- Ess arquivo Index.cshtml é chamado usando @Pages, a regra de negócio contido em Index.cshtml.cs.
- Em _ViewImports.cshtml estamos importanto todos os diretórios aos quais são necessários para direcionar Index.cshtml e _Layout.cshtml.
|> Que nesse caso, também foi criado um diretório Shared que contêm o arquivo _Layout.cshtml. Responsável por rendenizar a aplicação usando @RenderBody( ).
- Ainda em Shared temos as Partial View, Que por ter sido criada dentro de Shared pode ser usada por todas as Views, desde que na view chame, por exemplo, <partial name="Shared/NavMenuPartial" />.


