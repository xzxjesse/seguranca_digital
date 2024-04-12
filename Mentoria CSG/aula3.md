# Cloud Security
## Definição
> "A computação em nuvem é a entrega de recursos de TI sob demanda por meio da Internet com definição de preço de pagamento conforme o uso. Em vez de comprar, ter e manter datacenters e servidores físicos, você pode acessar serviços de tecnologia, como capacidade computacional, armazenamento e banco de dados, conforme a necessidade, usando um provedor de nuvem." - Amazon Web Services(AWS)

## Contexto
Tirou a preocupação com datacenter, agora as empresas podem contratar a estrutura de outros e passam a se preocupar somente com as próprias vendas.

## Benefícios
- Foco no negócio
- Troca de despesas fixas por despesas variáveis
- Escalabilidade
- Custo de acordo com a capacidade usada
- Maior velocidade e agilidade
- Sem custo com administração e manutenção de data centers

> **Redundância:** manter uma ou mais cópias funcionais de dados, sistemas ou infraestruturas, de modo que, caso um componente falhe, outro possa assumir sua função sem interrupções, garantir a alta disponibilidade e confiabilidade de sistemas e serviços

## Problemática
- Vazamento de dados
- Construção de tecnologia insegura

## Medidas de segurança
A segurança na nuvem é uma responsabilidade compartilhada.

- Controle de Acesso:
    Autenticação forte
    Gerenciamento de identidade e acesso (IAM)
    Monitoramento de acesso
- Segurança de Rede:
    Firewalls de nuvem
    Segmentação de rede
    VPN (Virtual Private Network)
- Segurança de Dados:
    Criptografia
    Gerenciamento de chaves
    Backup e recuperação de desastres
- Segurança de Aplicativos:
    Desenvolvimento seguro
    Testes de penetração
    Monitoramento de segurança
- Conformidade:
    Avalie os requisitos de conformidade
    Auditoria e monitoramento
- Conscientização e treinamento
- Considerar um provedor de nuvem confiável
- Monitoramento e revisão

## Desafios
- Gerenciamento de Identidade e Acesso
- Proteção de dados
- Gerenciamento de conformidade
- Segurança de rede
- Gestão de incidentes e respostas e incidentes
- Gerenciamento de configuração
- Segurança de aplicações
- Riscos de terceiros

## Certificações e carreira
- Certificação especificas de produto:
    Fundational
    Professional
    Associate
    Specialty
- Certificação gerais

- Dicas de carreira:
    Compreensão dos conceitos básicos
    Familiarização com os principais provedores
    Cursos e certificações
    Participação em comunidades e fóruns
    Prática em ambientes de laboratório
    Acompanhamento de tendência e notícias

# Aplication Security

> "**Software** é um conjunto de programas de computador, bem como documentação e dados associados." - ISO/IEC

> "**Um programa, um aplicativo, ou um aplicação**, é um programa de computador projetado para realizar uma tarefa específica diferente daquela relacionada à operação do próprio computador, normalmente para ser usado pelos usuários finais." - Oxford Dictionary

## Metologia de desenvolvimento
1. Escopo e requisitos
2. Design
3. Build
4. Testes
5. Deploy
6. Operações

> "Segurança de aplicaçõe sinclui todas as tarefas que apresentam um ciclo de vida de desenvolvimento de software seguro para asequipes de desenvolvimento
seu objetivo é melhorar as praticas de segurança e, atraves disso, encontrar e corrigir, pre...

## Metodologia segura!!
1.

é necessario armazenar todas as informações do usuario?
como é guardada a senha? como é o acesso a elas?
erros seguidos de loging com erro, considerar tempo

> log: arquivo de texto

modelagem de ameaça
    artefato: documentação da arquitetura
    resultado: documentação com controles de segurança
sast
    artefato: codigo fonte mais recente da aplicação
    resultado: relatorio de vulnerabilidade
sca/osa
    artefato: conjunto de bibliotecas e framework utilizados
    resultado: relatorio de vulnerabilidades
dast
    artefato: versão de testes da aplicação
    resultado: relatorio de vulnerabilidades

comparativo de soluções
    slide

devops:
como habilitar o sec no devops:
devsecops e pipelines:
por onde começar:

security champions:
por onde começar:

correção de erros em codigo fonte anteriores:
- nao aceitar novas vulnerabilidades
- plano de correção com data de finalização

experiencia com mds
unb tv sem preocupação com segurança ou acessibilidade
- exemplos de testes de segurança ou onde acho esse conteudo e como executar
- pegar cada fase e adicionar segurança dentro dela, do inicio ao fim

certificação
https://www.eccouncil.org/train-certify/application-security/
https://wiki.owasp.org/index.php/OWASP_Internet_of_Things_Project#tab=IoT_Top_10
https://www.isc2.org/certifications/csslp (!)