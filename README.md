# Segurança da Informação 🔐

## Aula 01 - Fundamentos da Segurança da Informação

### Pilares da Segurança da Informação (Tríade CIA)
A base da segurança da informação repousa sobre três princípios fundamentais, conhecidos como CIA:

- Confidencialidade: Garantir que a informação seja acessível apenas a pessoas autorizadas.

- Integridade: Manter a precisão e completude dos dados, prevenindo alterações não autorizadas.

- Disponibilidade: Assegurar que os sistemas e dados estejam acessíveis aos usuários sempre que necessário.

A violação de qualquer um desses pilares cria vulnerabilidades críticas.

### Por que a Segurança é Crucial?
A informação é um ativo valioso (dados, conversas, documentos) e sua perda ou vazamento pode causar danos financeiros e reputacionais graves para empresas e indivíduos. O volume massivo de dados trafegados na internet (ex.: milhões de mensagens por minuto) torna a proteção uma necessidade absoluta.

### O Equilíbrio Essencial
Um sistema eficaz deve encontrar o ponto ideal entre:

- Funcionalidade: O que o sistema faz.

- Usabilidade: A facilidade de uso.

- Segurança: A proteção dos dados.
  
A segurança não deve ser um obstáculo, mas uma aliada integrada que protege sem comprometer a experiência do usuário (ex.: usando autenticação multifator de forma inteligente).

### O que é Cibersegurança?
É a prática de proteger sistemas, redes e dados em ambientes digitais. Sua evolução acompanhou a tecnologia:

- Anos 80-90: Surgimento de antivírus e firewalls.

- Anos 2000: Adoção de políticas e normas (ex.: ISO 27001).

- 2010 em diante: Foco em segurança em nuvem (Cloud Security), BYOD (Bring Your Own Device) e frameworks como Zero Trust (confiança zero) e DevSecOps (integração da segurança no desenvolvimento de software).

### Tendências e Boas Práticas Modernas
- DevSecOps: Integrar controles de segurança em todas as etapas do ciclo de desenvolvimento de software.

- Zero Trust: Nunca confiar, sempre verificar. Conceder o mínimo privilégio necessário aos usuários.

- Conformidade Legal: Adequação à leis de proteção de dados como LGPD (Brasil) e GDPR (Europa).

- Segurança em IA: Novos desafios e camadas de proteção com o uso massivo de modelos de Inteligência Artificial.


---

### Pilares da Segurança da Informação - CIA

#### **1. Confidencialidade** 🔒
*   **O que é:** Garantia de que a informação só é acessível por pessoas ou sistemas autorizados.
*   **Exemplo Prático:** O acesso à sua conta bancária online é protegido por login, senha e, muitas vezes, um token (2FA). Sem essas credenciais, os dados (como seu saldo) devem permanecer inacessíveis.
*   **Riscos:** Quebras de confidencialidade permitem que invasores acessem dados sensíveis indevidamente, através de métodos como engenharia social ou manipulação de URLs.
*   **Como Garantir:**
    *   Utilizando autenticação robusta (senhas fortes).
    *   Implementando **Autenticação Multifator (MFA)** com tokens, biometria ou aplicativos autenticadores.
    *   Adotando o princípio de menor privilégio.

#### **2. Integridade** ✅
*   **O que é:** Garantia de que os dados estão completos, precisos e não foram alterados de forma não autorizada.
*   **Exemplo Prático:** Senhas nunca devem ser armazenadas em texto puro, mas sim como **hashes** (valores irreversíveis). Se um invasor modificar o hash no banco de dados, a integridade é violada e o acesso pode ser comprometido.
*   **Como Garantir:**
    *   Uso de funções de **hash** criptográficas (ex: SHA-256) para verificar a autenticidade de dados e arquivos.
    *   Verificação de hashes de arquivos baixados (ex: ISOs de sistemas operacionais) comparando o valor calculado com o fornecido pelo distribuidor.
    *   Uso de **assinaturas digitais** para verificar a autoria e a não alteração de documentos.

#### **3. Disponibilidade** ⏱️
*   **O que é:** Garantia de que os sistemas e dados estarão acessíveis para usuários autorizados quando necessário.
*   **Exemplo Prático:** Um ataque de **negação de serviço (DDoS)** que derruba um site é uma violação direta da disponibilidade.
*   **Como Garantir:**
    *   Implementação de redundância (servidores em cluster).
    *   Uso de **balanceadores de carga** para distribuir tráfego e evitar sobrecarga.
    *   Planos de recuperação de desastres (backups).

---

### **Conclusão**
A tríade **CIA** forma a base da segurança da informação:
*   Use **autenticação forte e MFA** para garantir a **Confidencialidade**.
*   Use **hashes e assinaturas** para garantir a **Integridade**.
*   Use **redundância e balanceamento** para garantir a **Disponibilidade**.

O equilíbrio entre esses três pilares é essencial para proteger ativos de informação contra ameaças e vulnerabilidades.

---

### Autenticidade, Não Repúdio e Auditoria (ANA)

#### **1. Autenticidade 🛡️**
*   **O que é:** Garantia de que uma informação ou ação é genuína e originada de uma fonte confiável e verificável.
*   **Como Garantir:**
    *   **Assinaturas Digitais:** Tecnologias como **DocuSign** provam que uma pessoa específica executou uma ação (ex: assinou um documento).
*   **Relação com a Integridade:** Se uma informação for modificada, ela perde sua autenticidade e confiabilidade.

#### **2. Não Repúdio (Non-Repudiation) 📝**
*   **O que é:** Princípio que impede um indivíduo de negar ter realizado uma ação. Fornece **prova irrefutável** da autoria de um evento.
*   **Como Garantir:**
    *   **Assinaturas Digitais:** Servem como uma prova de não repúdio.
    *   **Logs de Auditoria Robustos:** Registros detalhados que capturam "quem", "o quê", "quando" e "onde" de uma ação.

#### **3. Auditoria (Auditing) & Rastreabilidade 🔍**
*   **O que é:** A prática de **monitorar e registrar** eventos para criar um histórico de atividades. É a base para o não repúdio e a responsabilização.
*   **Por que é Crítica:** Sem logs, é impossível provar quem executou uma ação, investigar incidentes ou detectar comportamentos maliciosos.
*   **Exemplo Prático (API Flask):**
    Um log básico de uma API `127.0.0.1 - - [09/Jul/2025 23:30:33] "GET /api/hello HTTP/1.1" 200 -` é um começo, mas é insuficiente. Logs devem ser enriquecidos com:
    *   Identidade do usuário (não apenas IP).
    *   Ação específica realizada.
    *   Recursos acessados.
    *   Timestamp.
    *   Status da operação.

#### **4. Responsabilização (Accountability) 👤**
*   **O que é:** A consequência direta de uma auditoria eficaz. É a capacidade de **atribuir ações a um indivíduo** específico, tornando-o responsável por suas atividades no sistema.
*   **Objetivo:** Permite rastrear comportamentos, responder a incidentes e proteger contra negações fraudulentas de ações.


### Princípios-Chave

*   **A CIA não é suficiente:** Para segurança robusta, os pilares **Confidencialidade, Integridade e Disponibilidade** devem ser expandidos com **Autenticidade, Não Repúdio e Auditoria**.
*   **Logs são a prova:** A frase **"Sem log, não há prova"** é fundamental. Logs detalhados são a base para a auditoria e o não repúdio.
*   **Pense além dos erros:** Ao construir sistemas, não registre apenas falhas. **Registre todas as ações significativas** para permitir a rastreabilidade completa (accountability).
*   **A quebra desses princípios cria vulnerabilidades críticas,** pois impossibilita a investigação e a responsabilização, deixando sistemas expostos.



---

### Fundamentos do Zero Trust (Confiança Zero)

#### **🔐 Visão Geral**
O **Zero Trust** é um modelo de segurança moderno baseado em um princípio fundamental: **"Nunca confie, sempre verifique"**. Ele abandona o conceito tradicional de uma rede corporativa interna "confiável" e trata **todo usuário e dispositivo**, independente de sua localização (interno ou externo à rede), como uma potencial ameaça até que sua identidade e acesso sejam rigorosamente validados.

#### **🛡️ Princípios Centrais**
1.  **Verificação Contínua:** Toda tentativa de acesso a qualquer recurso deve ser autenticada, autorizada e criptografada. A confiança nunca é concedida permanentemente.
2.  **Privilégio Mínimo (Least Privilege):** Os usuários e dispositivos recebem **apenas as permissões estritamente necessárias** para realizar uma tarefa específica, limitando o potencial estrago de um acesso comprometido.
3.  **Segmentação de Rede:** A rede é dividida em micro-segmentos ou zonas de segurança. Isso impede que um invasor, após ganhar acesso a uma parte do sistema, se mova lateralmente por toda a infraestrutura.

#### **⚙️ Como é Implementado?**
A implementação do Zero Trust depende de verificações rigorosas e contextuais para cada solicitação de acesso. Essas verificações podem incluir:
*   **Autenticação Multifator (MFA)**
*   **Verificação da integridade e conformidade do dispositivo**
*   **Análise comportamental do usuário** (para detectar atividades anômalas)
*   **Avaliação de risco em tempo real** (com base no local, horário, sensibilidade do recurso, etc.)

As políticas de acesso são **dinâmicas**, podendo ser ajustadas automaticamente com base no contexto da solicitação.

#### **✅ Vantagens**
*   **Redução da Superfície de Ataque:** Ameaças internas e externas são tratadas com o mesmo ceticismo.
*   **Contenção de Brechas:** A segmentação limita o raio de explosão de uma potencial invasão.
*   **Maior Visibilidade e Controle:** Oferece um entendimento granular de quem está acessando o quê e quando.
*   **Suporte para Trabalho Remoto e BYOD:** É ideal para ambientes onde os recursos não estão mais confinados a um perímetro de rede físico.

#### **⚠️ Desafios**
*   **Complexidade de Implementação:** Integrar o modelo com sistemas legados pode ser desafiador.
*   **Mudança Cultural:** Exige uma mudança de mentalidade de "confiança interna" para "verificação constante".
*   **Investimento em Tecnologia e Treinamento:** Requer ferramentas robustas de identidade, monitoramento e análise, além de capacitação das equipes.

## Aula 02 -Ameaças Cibernéticas e seus impactos



### Vulnerabilidades vs. Ameaças em Segurança da Informação


### **🔓 VULNERABILIDADES (As Fraquezas)**

Vulnerabilidades são falhas ou brechas em sistemas, processos ou pessoas que podem ser exploradas. Elas são a "porta aberta" que permite um ataque.

#### **1. Vulnerabilidades Humanas (O Elo Mais Fraco)**
*   **Descrição:** Falta de treinamento ou conscientização dos usuários.
*   **Exemplo:** Um colaborador que clica em um link de **phishing** e divulga credenciais ou informações confidenciais.
*   **Mitigação:** Programas contínuos de **conscientização e treinamento** em segurança.

#### **2. Vulnerabilidades em Sistemas**
*   **Descrição:** Bugs ou falhas técnicas que podem ser explorados para ganhar acesso não autorizado ou causar danos.
*   **Exemplo:** Um botão quebrado é um *bug*; se ele permitir injetar código, torna-se uma *vulnerabilidade*.
*   **Mitigação:** Revisões de código, testes de penetração e práticas de desenvolvimento seguro (DevSecOps).

#### **3. Vulnerabilidades em Autenticação**
*   **Descrição:** Mecanismos fracos de verificação de identidade.
*   **Exemplos:**
    *   **Senhas Fracas:** Senhas curtas, simples ou reutilizadas.
    *   **Autenticação Própria:** Desenvolver um sistema de login próprio e potencialmente inseguro.
*   **Mitigação:**
    *   Implementar políticas de **senhas complexas** (ex.: 14+ caracteres, misturando maiúsculas, minúsculas, números e símbolos).
    *   Preferir usar **Single Sign-On (SSO)** com provedores confiáveis (Google, Microsoft) que suportam **Autenticação Multifator (MFA)**.

#### **4. Vulnerabilidades em Dependências (Softwares Desatualizados)**
*   **Descrição:** Uso de bibliotecas, frameworks ou softwares com versões antigas que contêm falhas de segurança conhecidas.
*   **Exemplo Crítico:** A vulnerabilidade **Log4Shell (Log4j)** em 2021, que permitia execução remota de código.
*   **Mitigação:**
    *   Gerenciamento constante de dependências (ex.: com `npm audit`, `snyk`).
    *   Implementar um processo de **atualização e patch management** contínuo para todos os componentes (servidores web, bancos de dados, serviços SMTP).

---

### **☠️ AMEAÇAS (Os Agentes de Ataque)**

Ameaças são os agentes ou eventos que exploram as vulnerabilidades para causar danos. Elas são "quem" ou "o quê" tenta atravessar a porta aberta.

#### **1. Malware (Software Malicioso)**
*   **Vírus:** Precisa de um arquivo hospedeiro para se espalhar.
*   **Worms:** Se espalham automaticamente pela rede, sem necessidade de um hospedeiro.
*   **Cavalo de Troia (Trojan):** Disfarça-se de software legítimo para enganar o usuário e instalar uma backdoor.
*   **Keylogger:** Captura tudo o que é digitado no teclado para roubar credenciais.

#### **2. Engenharia Social**
*   **Descrição:** Táticas psicológicas que manipulam pessoas para divulgar informações sensíveis ou realizar ações.
*   **Exemplo Principal:** **Phishing** (e-mails, mensagens) com links ou anexos maliciosos.
*   **Objetivo:** Extorsão, roubo de dados ou acesso inicial a um ambiente.

#### **3. Ataques de Negação de Serviço (DDoS)**
*   **Descrição:** Sobrecarregar um servidor ou rede com tráfego fraudulento, tornando-o indisponível para usuários legítimos.
*   **Como Funciona:** Geralmente realizado por uma **botnet** (rede de dispositivos infectados controlados por um atacante).

---

### **Relação Crucial**

*   Uma **Ameaça** explora uma **Vulnerabilidade** para materializar um **Risco**.
*   **Entender ambas é o primeiro passo para a prevenção:** Você não pode se defender de uma ameaça se não souber quais vulnerabilidades ela pode explorar.
*   A defesa eficaz requer um combate em duas frentes:
    1.  **Corrigir vulnerabilidades:** Atualizar sistemas, treinar pessoas e implementar autenticação forte.
    2.  **Monitorar e mitigar ameaças:** Usar ferramentas para detectar malware, filtrar phishing e absorver ataques DDoS.
