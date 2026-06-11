# Governança de TI, Ética e Privacidade de Dados

## O Impacto da LGPD no Desenvolvimento de Software

### Conceitos e Fundamentos

#### O que é Governança de TI (COBIT/ITIL)?

Governança de TI é o conjunto de práticas, processos e políticas que garantem que a tecnologia esteja alinhada aos objetivos da organização, promovendo controle, segurança e eficiência.

* **COBIT:** framework voltado para governança, controle e gestão de riscos.
* **ITIL:** conjunto de boas práticas para gerenciamento e entrega de serviços de TI.

---

#### Princípios da LGPD para Desenvolvedores

A LGPD estabelece diretrizes para o tratamento de dados pessoais. Os principais princípios aplicados ao desenvolvimento de software são:

* Finalidade
* Necessidade
* Transparência
* Segurança
* Prevenção
* Responsabilização

---

#### O que é Privacy by Design?

É uma abordagem que incorpora a privacidade e a proteção de dados desde a fase de planejamento e desenvolvimento do sistema, reduzindo riscos e aumentando a conformidade com a LGPD.

---

#### O que são Dados Sensíveis?

São dados pessoais que podem gerar discriminação ou impactar significativamente a privacidade do indivíduo.

Exemplos:

* Dados de saúde
* Dados biométricos
* Opinião política

---

# Para Refletir

A MedAgenda é uma plataforma SaaS hospedada na AWS (IaaS) que gerencia consultas médicas. O sistema armazena o histórico clínico dos pacientes. Para economizar, a equipe de desenvolvimento utiliza o mesmo banco de dados de produção nos ambientes de testes locais. Um desenvolvedor baixou uma cópia do banco de dados para corrigir um erro em sua máquina pessoal, porém teve seu notebook furtado. O banco continha nomes, CPFs e diagnósticos de aproximadamente 10.000 pacientes.

---

# Respostas

## 1. Identificação

### Quais dados sensíveis foram expostos?

* Diagnósticos médicos.
* Histórico clínico dos pacientes.
* Nome dos pacientes.
* CPF dos pacientes.

### Quais princípios foram violados?

* Segurança.
* Prevenção.
* Necessidade.
* Responsabilização.
* Privacy by Design.

---

## 2. Mitigação Tecnológica

### Como Docker e ambientes isolados poderiam evitar o problema?

* Separando os ambientes de produção, testes e desenvolvimento.
* Evitando o acesso direto dos desenvolvedores ao banco de produção.
* Utilizando bancos de testes independentes em contêineres Docker.

### Como anonimização e mascaramento ajudariam?

* **Anonimização:** remove informações que identificam o paciente.
* **Mascaramento:** oculta dados como CPF, nome e demais informações pessoais.

Dessa forma, mesmo em caso de vazamento, os dados reais não seriam expostos.

---

## 3. Governança

### Qual política de acesso deveria ser implementada?

* Princípio do menor privilégio.
* Controle de acesso baseado em papéis (RBAC).
* Autenticação multifator (MFA).
* Monitoramento e registro de acessos por logs.
* Restrição de cópias e downloads de bases de produção para dispositivos pessoais.

Essas medidas reduzem os riscos de vazamento e ajudam a manter a conformidade com a LGPD.
