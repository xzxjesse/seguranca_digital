# Use apenas os dados necessários
Não manter dados sensíveis sobre os usuários.

## Abordagens:
> Transparência gera confiança.

### Não colete-o.
A maneira mais óbvia de não comprometer os dados dos seus usuários é não coletá-los. 

- Em 2021, um estudo descobriu que **uma em cada quatro vendas abandonadas ocorre porque o site exigia que o usuário criasse uma conta**. Possibilitar a conclusão de uma compra sem se inscrever oferece melhores opções aos usuários e também significa que você não tem muitos dados para proteger.

### "Fuzz" seus dados
É importante coletar dados para fornecer alguns serviços e tomar decisões de negócios sensatas e por isso é essencial criar uma relação de confiança. 

As decisões tomadas de maneira agregada (ou seja, que afetam muitos usuários de uma vez) são tomadas sobre **dados agregados** (ou seja, sobre propriedades coletivas dos dados).

- Às vezes é útil conhecer as informações demográficas do seu público e para isso é possível mudar sua mensagem ou abordagem, o que não significa que você precisa coletar o dado exata de cada usuário do serviço. O que você procura com frequência são **tendências e propriedades gerais**. Isso os reúne em dois "buckets": nesse grupo e não nesse grupo. 

Solicitar dados extremamente granulares, pessoais e personalizados pode deixar as pessoas desconfortáveis e reduzir a confiança do usuário em sua organização, além de aumentar o risco.

### Métodos de resposta aleatórios
Significa que os dados são coletados com um **grau ajustável de imprecisão**, envolve ampliar as respostas do usuário. 

### Privacidade diferencial
É um método que usa técnicas matemáticas para alterar o armazenamento de dados para que as propriedades agregadas dos dados ainda estejam presentes, mas não é possível saber se um indivíduo específico forneceu dados ou se foram fornecidos. 

Nessas abordagens e em outras ainda é necessário **ter e seguir políticas claras** para confirmar que você não as está usando antes da agregação ou para que você está usando esses dados.

### Retenção
> colete e remova dados depois que eles forem usados

- **Ciclo de vida dos dados**: eles são coletados, usados para ajudar você a tomar decisões de negócios e, em algum momento, precisam ser removidos. 

- **Princípio da revogabilidade**: "A interface precisa permitir que o usuário revogue facilmente as autoridades concedidas pelo usuário sempre que possível a revogação. Os usuários precisam ter a opção de revogar esse consentimento e, assim, reduzir o acesso das autoridades aos recursos se possível.

> Os usuários "precisam de uma "saída de emergência" claramente marcada para sair da ação indesejada sem ter que passar por um processo estendido, oferecer aos usuários a capacidade de escapar sem ter que passar pelos obstáculos, "promove uma sensação de liberdade e confiança". 

### O que fazer
É útil permitir que os usuários **excluam contas** e que **limpem regularmente os dados temporários** e armazenados localmente ao sair com o cabeçalho Clear-Site-Data.

**Cabeçalho Clear-Site-Data** para remover alguns ou todos os dados do usuário armazenados no lado do cliente, quando razoável. 

```bash
<div>
    <label for="email">Email address*</label>
    <input id="email" type="email" name="email" required aria-describedby="whyemail">
    <a href="#whyemail">Why do we need this?</a>
    <aside id="whyemail">We need this information as a unique identifier for you, and if you forget your password we can send you a reminder. We will use your email address to send you regular updates on the service if you choose, and will delete your email address from any mailing lists if you delete your account.</aside>
</div>
```
> Usar o cabeçalho Clear-Site-Data provavelmente será mais fácil do que excluir individualmente todos os recursos criados, porque ele não exige que o código JavaScript seja executado no cliente (e é a única maneira oficial de limpar o cache do navegador), mas não é compatível com todos os navegadores.

### Explique para o que você precisa dos dados
A importância da confiança no relacionamento dos usuários com seu serviço aumenta a **longevidade do usuário e a vantagem competitiva**. 

De modo que é importante ter **transparência dos processos**, e uma boa maneira de ser transparente é explicar **para que** você quer dados e **o que será feito** com esses dados e **quando e como remover eles**. Isso pode ser feito na Política de Privacidade ou ao fazer perguntas sobre a criação da conta.

Passar por esse processo com tudo o que você coletar sobre um usuário também pode ajudar em processos e discussões internos. **Se você estiver relutante em anotar publicamente o que quer fazer com os dados do usuário porque ele não vai gostar da explicação, isso pode ser um sinal de que vale a pena repensar a coleta de dados.**

- **muito invasiva:** "usaremos isso para rastrear onde você visita a cada hora" 
- **ampla demais:** "não sabemos para o que vamos usar isso ainda, mas queremos que isso seja feito caso pensemos em algo para isso"
- **muito evasiva:** "vamos usar isso para fins internos não divulgados"