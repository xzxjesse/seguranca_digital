# Terceiros

## O que é um terceiro?
Conteúdo de terceiros: algo **hospedado em uma origem compartilhada e pública**, que é amplamente usado por vários sites e é de autoria de alguém que não é o proprietário do site. 

> Do ponto de vista da privacidade, terceiro é qualquer pessoa que saiba algo sobre seus usuários, que não é você.

## Por que usamos recursos de terceiros?
São usados para **incluir funcionalidades no site** e podem ser recursos expostos aos usuários ou funções invisíveis do desenvolvedor.


## O que recursos de terceiros podem fazer?

- Acesso a informações
- Rastreamento entre sites: permitir que terceiros coletem um registro da atividade do usuário em vários sites, desde que todos usem um recurso do mesmo terceiro.
- Código de terceiros do lado do servidor: geralmente precisa fornecer os dados do usuário pelo desenvolvedor, o que significa que os dados a que ele é exposto estão mais sob seu controle. 
- Código de terceiro do lado do cliente: pode coletar alguns dados diretamente do usuário sem que esse processo de coleta seja mediado pelo desenvolvedor. 

> Um cookie é um pequeno arquivo de texto que um site armazena no dispositivo de um usuário quando ele visita o site. Esses arquivos contêm informações que podem ser acessadas pelo site posteriormente. 

## Por que você precisa ter cuidado com terceiros?
O conteúdo de terceiros pode gerar **problemas de desempenho, de segurança e de privacidade** porque está trazendo um serviço externo dentro do seu limite de confiança. 

## Exemplos de terceiros

- **Recurso entre sites:** É qualquer item do seu site que seja carregado de um site diferente e que não seja iframe ou script. Elas são carregadas por uma solicitação HTTP e essas solicitações incluem todos os cookies definidos anteriormente pelo outro site, o endereço IP do usuário solicitante e o URL da página atual como referenciador.

- **Iframe entre sites:** O iframe pode solicitar acesso adicional às APIs do navegador, além do triplo de cookies, endereço IP e referenciador, a forma queas APIs solicitam acesso são específicas do navegador

- **JavaScript entre sites:** O script em execução tem acesso total a tudo que os scripts próprios fazem, porem as permissões do navegador ainda gerenciam esses dados.

- **Bibliotecas de terceiros nas suas dependências:** O código incluso de um repositório do GitHub ou da biblioteca da linguagem de programação pode ler os mesmos dados que seu outro código pode ler.

## Conhecendo seus terceiros
É necessário saber quais são as **políticas e posições de privacidade, coleta de dados e experiência do usuário**. 

### Como auditar seus terceiros
- Executar uma auditoria não técnica: leitura e análise das Políticas de Privacidade dos fornecedores
- Realizar uma auditoria técnica: usar os recursos locais como parte do site na experiência de novo usuário

> Um arquivo HAR é um formato JSON padronizado de todas as solicitações de rede feitas por uma página.

## Práticas recomendadas ao integrar terceiros

- **Ao adicionar um botão de compartilhamento em mídia social:** Incorpore botões HTML diretamente ou adicionar links HTML simples.
- **Ao incorporar um vídeo:** Procure no código de incorporação opções que preservam a privacidade.
- **Ao incorporar scripts de análise:** Use sistemas de análise auto-hospedados ou verifique as opções de configuração do seu provedor de análise para limitar os dados coletados e reduzir a quantidade e a duração do armazenamento.

## Usar terceiros preservando a privacidade

### Política de referenciador
- **O que fazer:** Defina uma política de strict-origin-when-cross-origin ou noreferrer para impedir que outros sites recebam um cabeçalho Referer ao vinculá-los ou quando forem carregados como sub-recursos por uma página.
- **Por que isso protege a privacidade do usuário:** Fornecer um cabeçalho Referrer-Policy permite alterar isso, para que parte ou nenhum URL de referência seja transmitido.
    - Se não for possível definir cabeçalhos, você poderá definir uma política de referenciador para uma página HTML inteira usando um elemento meta em <head>: <meta name="referrer" content="same-origin">. 
    - Se você estiver preocupado com terceiros específicos, também poderá definir um atributo referrerpolicy em elementos individuais, como <script>, <a> ou <iframe>: <script src="https://thirdparty.example.com/data.js" referrerpolicy="no-referrer">

> URL do referenciador por padrão atualmente é transmitido a terceiros apenas como uma origem, o que preserva muito mais a privacidade do que antes, mas ainda fornece informações de alto nível a terceiros de sua escolha, como seu provedor de análise.

### Política de segurança de conteúdo

**CSP (Content-Security-Policy)**
> Determina de onde os recursos externos podem ser carregados. 
Ele é usado principalmente para fins de segurança, impedindo ataques de scripting em vários locais e injeção de script. No entanto, quando usado junto com auditorias regulares, ele também pode limitar para onde os terceiros escolhidos podem transmitir dados.

**Content-Security-Policy-Report-Only**
Com esse cabeçalho as solicitações que violarem a política fornecida não serão bloqueadas, mas um relatório JSON será enviado para um URL fornecido. Normalmente, isso é usado para testar uma política antes da implementação, mas uma ideia útil é usar isso como uma forma de conduzir uma "auditoria contínua".

- Isso faz parte da auditoria técnica, de maneira contínua. 

### Política de permissões

**Permissions-Policy ou Feature-Policy** 
> Restringe o acesso a recursos avançados do navegador. 

Essas restrições podem ser aplicadas a uma página de nível superior para evitar que os scripts carregados tentem usar esses recursos ou a páginas com subframes carregadas por meio de um iframe. Essa restrição de uso da API não está relacionada à impressão digital do navegador. Ela significa impedir que terceiros façam ações invasivas, como usar APIs avançadas, abrir janelas de permissões etc. Isso é definido pelo modelo de ameaças à privacidade de destino como "intrusão".

[Lista de recursos processados pelo cabeçalho Permissions-Policy](https://github.com/w3c/webappsec-permissions-policy/blob/main/features.md)

- **O que fazer:** Por padrão, os navegadores com suporte a Permissions-Policy não permitem recursos avançados em subframes, e você precisa tomar medidas para ativá-los. Por padrão, essa abordagem é particular. Se você achar que os subframes do seu site precisam dessas permissões, adicione-os seletivamente. No entanto, por padrão não há uma política de permissões aplicada à página principal. Portanto, os scripts (incluindo scripts de terceiros) que são carregados por ela não têm restrições de tentar usar esses recursos. Por isso, é útil aplicar uma Permissions-Policy restritiva a todas as páginas por padrão e adicionar gradualmente os recursos necessários.

## Entenda os recursos de privacidade integrados nos navegadores da Web

Além das proteções de "tempo de build" e "tempo de design", há também proteções de privacidade que ocorrem no **"tempo de execução"**, ou seja, recursos de privacidade implementados nos próprios navegadores para proteger os usuários. 

As abordagens dos navegadores sobre recursos de privacidade mudam com frequência, e é importante ficar atualizado. E as vezes, os modos de navegação anônima/privada implementam configurações diferentes do padrão do navegador (cookies de terceiros podem ser bloqueados por padrão nesses modos, por exemplo).

## Propostas de API

### Por que precisamos de novas APIs?
Embora os novos recursos e políticas de preservação da privacidade nos produtos de navegador ajudem a preservar a privacidade do usuário, eles também apresentam desafios. </br>

**Seria difícil e propenso a erros para os navegadores diferenciar os casos de uso e distinguir com segurança os usos que violam a privacidade dos outros. É por isso que a maioria dos principais navegadores bloqueou cookies de terceiros e técnicas de impressão digital ou pretendem fazer isso para proteger a privacidade do usuário.** </br>

À medida que os cookies de terceiros são descontinuados e as técnicas de impressão digital são mitigadas, os desenvolvedores precisam de APIs específicas que atendam aos casos de uso (que não desapareceram), mas sejam projetadas de maneira a preservar a privacidade. **O objetivo é projetar e criar APIs que não possam ser usadas para rastreamento entre sites.**

### Exemplos de propostas de API

Exemplos de propostas de API para substituir tecnologias criadas com **cookies de terceiros**:

- Casos de uso de identidade: FedCM

- Casos de uso de anúncios: Medição de cliques privados, Atribuição particular interoperável, Relatórios de atribuição, Topics, FLEDGE e PARAKEET.

Exemplos de propostas de API para substituir tecnologias baseadas no **rastreamento passivo**:

- Casos de uso de detecção de fraude: tokens de confiança.

Exemplo de outra proposta que outras APIs podem usar como base para **um futuro sem cookies de terceiros**:

- API Storage Access

**Global-Privacy-Control** </br>

É um cabeçalho que pretende comunicar a um site que o usuário não quer que os dados pessoais coletados sejam compartilhados com outros sites.

### Status das propostas de API
**A maioria dessas propostas de API ainda não foi implantada ou é implantada apenas sob sinalizações ou em ambientes limitados para experimentação.**

O melhor lugar para se manter atualizado sobre as novas APIs propostas é atualmente a [lista de propostas do Privacy Group](https://github.com/privacycg/proposals/issues).