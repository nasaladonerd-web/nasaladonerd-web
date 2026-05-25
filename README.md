# 🏢 Quem sou eu?

> **Civil Engineer**  & **Software Engineer**|

## ⚡ Projeto Ecossistema Synergie

O **Synergie** é um projeto de construção de um ecossistema de workspaces, concebidos sob o princípios de soberania tecnológica, automaçãos **fail-fast** e **isolamento** adequado. Dividido em duas frentes complementares, o ecossistema atende tanto à engenharia analítica de dados quanto à auditoria defensiva e ofensiva de infraestruturas críticas.

<table border="0" width="100%">
  <tr>
    <td width="50%" valign="top" style="border: none; padding-right: 15px;">
      <h3>🤖 Synergie Core (Open-Core)</h3>
      <p>Workspace de engenharia totalmente apoiado por assistentes inteligentes locais e orquestração multi-LLM independente da nuvem.</p>
      <ul>
        <li><b>IA 100% Local:</b> Modelos executados via Ollama/llama.cpp com logs agregados e dashboards dedicados.</li>
        <li><b>Ensemble de Modelos:</b> Orquestração inteligente com tomada de decisão baseada em voto conceitual mitigando alucinações.</li>
        <li><b>Governança Ativa:</b> Validação automática de schemas e metadados sob modo estrito e impeditivo <i>fail-fast</i>.</li>
      </ul>
      <br>
      <p>➔ <code>Foco: Produtividade, privacidade absoluta e conformidade corporativa.</code></p>
    </td>    
    <td width="50%" valign="top" style="border: none; padding-left: 15px;">
<h3>🛡️ Synergie Security Edition (Premium)</h3>
      <p>Ambiente isolado sob demanda para auditoria ofensiva e Pentesting profissional, estruturado sobre contêineres Kali Linux de alta confiabilidade.</p>
      <ul>
        <li><b>Isolamento Avançado:</b> Proteção de infraestrutura baseada em <code>userns-remap</code>, perfis AppArmor e filtros via Seccomp.</li>
        <li><b>Execução Imutável:</b> Contêiner operando com <code>rootfs</code> read-only, mitigação <code>--cap-drop=ALL</code> e limites estritos (4G RAM / 512 PIDs).</li>
        <li><b>Segregação de Redes:</b> Modos de rede customizados para Pentest interno (LAN via macvlan) ou alvos externos isolados do host.</li>
      </ul>
      <br>
      <p>➔ <code>Foco: Auditorias comerciais de segurança e laboratórios temporários de cybersecurity.</code></p>
    </td>
  </tr>
</table>

---

## 🛠️ Arquitetura de Isolamento e Segurança (Security Edition)

Para mitigar os riscos inerentes à execução de ferramentas hiper-agressivas de auditoria e exploração (como `nmap`, `metasploit-framework` e `hydra`), a infraestrutura do ecossistema opera sob o princípio de **Defesa em Profundidade**. O ambiente de execução do Kali Linux é envelopado por quatro camadas concêntricas de isolamento que blindam completamente o sistema hospedeiro (*Host*) contra qualquer vazamento de execução ou tentativa de elevação de privilégio:

### 🛡️ As 4 Camadas de Blindagem do Host

1. **Camada de Identidade (`userns-remap`):** O usuário `root` dentro do contêiner é mapeado para um usuário comum e sem privilégios no Host. Mesmo se um exploit quebrar o contêiner, o atacante ganha acesso ao seu computador real como um usuário totalmente inofensivo.
2. **Camada de Restrição do Kernel (`Seccomp` & `AppArmor`):** Filtros rígidos de chamadas de sistema (`Seccomp`) barram syscalls perigosas, enquanto o perfil do `AppArmor` confina os processos do contêiner, impedindo que acessem arquivos ou diretórios sensíveis do Host.
3. **Camada de Imutabilidade Estrita (`rootfs` read-only):** Todo o sistema de arquivos do Kali opera em modo somente-leitura. Malwares e payloads não conseguem se fixar ou modificar os binários do sistema, garantindo um ambiente estéril e livre de persistência maliciosa a cada execução.
4. **Camada de Contenção Física (Limites de Hardware):** Tetos rígidos de memória (4G RAM) e tabela de processos (`512 PIDs`) neutralizam ataques de Negação de Serviço (DoS) e scripts recursivos (como *Fork Bombs*), mantendo o Host perfeitamente estável.

<p align="center">
  <img src="https://raw.githubusercontent.com/nasaladonerd-web/nasaladonerd-web/main/kali_container_architecture.svg" alt="Synergie Pentest Architecture" width="100%" style="max-width:750px;">
</p>

## 🌐 Políticas de Segregação de Rede Dinâmica

O gerenciamento de conexões do workspace é projetado sob critérios rígidos de auditoria autorizada e contenção de tráfego, permitindo o chaveamento seguro entre dois modos de rede isolados, conforme o escopo e os termos de consentimento da homologação técnica:

- Modo --internal (Avaliação de Perímetro Interno / LAN): Utiliza drivers macvlan para associar um endereço IP dedicado da sub-rede local ao contêiner. Esta configuração é estritamente voltada para testes de conformidade, inventário de ativos e análise de vulnerabilidades em topologias internas (como switches, roteadores e servidores locais corporativos), operando com total transparência de tráfego para os sistemas de monitoramento da TI.

- Modo --external (Simulação de Vetores Externos / Cloud): Conecta o contêiner a uma interface de ponte (bridge) isolada, utilizando mascaramento de rede (NAT) e políticas restritivas no firewall iptables do Host. Este modo é desenhado para auditorias de aplicações hospedadas em nuvem pública (ambientes controlados ou de clientes homologados), garantindo tecnicamente que as ferramentas do contêiner fiquem completamente blindadas e incapazes de interagir, expor ou interferir com qualquer outro dispositivo da sua rede local.
    
## 📐 Engenharia, Soluções Técnológicas  & Consultorias.

A robustez e a rigidez aplicadas ao desenvolvimento do ecossistema de software originam-se diretamente das melhores práticas de gerenciamento de riscos e conformidades também existentes na engenharia tradicional. A unificação desses mundos garante a entrega de ativos de alta previsibilidade , rastreabilidade e segurança.

* **🏢 Consultoria em Engenharia Civil:** Cálculo estrutural, Gestão de projetos e Consultorias Técnicas.
* **⚖️ Conformidade e Normatização:** Mapeamento de processos operacionais e auditorias de segurança, ISOs e Normas técnicas.
* **📚 Gestão do Conhecimento:** Arquitetura de informação estratégica baseada na ontologia Cortex (PARA-like) estruturada para aprendizado contínuo de sistemas e equipes apoiados por Inteligencias Artificiais.

---

## ⚙️ Governança Automatizada do Workspace (Strict Fail-Fast Mode)

A integridade estrutural, a rastreabilidade e a confiabilidade de todos os artefatos (código, documentações técnicas e contratos) são asseguradas por uma esteira de governança automatizada. Operando sob a filosofia **Fail-Fast**, qualquer inconformidade bloqueia imediatamente o pipeline de integração local (Git Hooks) ou remoto (CI), impedindo a propagação de débitos técnicos.

### 🛠️ Pilares da Validação Estrita

* **🔴 Validação Terminológica Ubíqua (`check_vocabulary.py`):** Varredura estática de semântica que audita o repositório contra um dicionário poliglota próprio (atualmente na v0.4.0, cobrindo 66 conceitos fundamentais em PT-BR, EN e com infraestrutura pronta para expansão em FR). Isso garante a consistência terminológica absoluta entre os domínios de software e engenharia, eliminando ambiguidades conceituais.

* **🔴 Conformidade de Metadados e Esquemas (`validate_frontmatter.py`):**
  Auditoria rigorosa de cabeçalhos (Frontmatter YAML) contidos nos documentos Markdown. O validador utiliza a especificação internacional **JSON Schema Draft 2020-12** para impor tipagem estrita, campos obrigatórios de governança (como ciclo de vida, autoria e setor) e formatos canônicos, bloqueando dados corrompidos na origem.

* **🔴 Governança de Contratos de API (Linter Spectral):**
  Validação automatizada de especificações de interface orientadas a eventos e REST (OpenAPI e AsyncAPI) através do motor de regras customizado do Spectral. O processo garante que toda comunicação entre microsserviços do ecossistema respeite padrões estritos de segurança, design e compatibilidade retroativa, garantindo que as versões antigas do sistema não quebrem.

* **🔴 Histórico Imutável e Rastreabilidade (Linear Git History):**
  Aplicação de políticas corporativas estritas de versionamento para garantir uma trilha de auditoria limpa e auditável:
  * **Branches Protegidas:** Proibição de escrita direta na ramificação principal (`main`), tornando obrigatória a abertura de requisições de incorporação (Pull Requests).
  * **Conversation Resolution:** Bloqueio de merges caso haja revisões abertas ou apontamentos de segurança pendentes de marcação formal como resolvidos.
  * **Histórico estritamente Linear:** Enforcement de políticas que impedem commits de merge redundantes e vetam a utilização de `force-push` (reescrita de histórico), assegurando a total imutabilidade cronológica do código.

---

## 📬 Contatos & Parcerias

Se você busca uma infraestrutura soberana para IA local, quer acompanhar o desenvolvimento de outros projetos, estudos e contribuições ou necessita de consultoria em engenharia civil, para o desenvolvimento de soluções tecnológicas e governança de processos:

* 📧 **E-mail.:** `nasaladonerd@gmail.com`
* 🤖 **Código Aberto:** Explore a organização e controle estrutural do ecossistema no repositório `nasaladonerd-web/felipe`.
