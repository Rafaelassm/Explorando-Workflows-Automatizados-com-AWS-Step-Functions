# Explorando-Workflows-Automatizados-com-AWS-Step-Functions
Repositório organizado contendo anotações e insights adquiridos durante a aula  prática a fim de consolidar os conhecimentos em workflows automatizados com AWS Step Functions.

# 🌀 AWS Step Functions

O **AWS Step Functions** é um serviço **de orquestração sem servidor** que permite **criar fluxos de trabalho visuais** para coordenar e automatizar **serviços da AWS** e **microsserviços**.  

Agindo como um maestro, ele facilita a criação de aplicações **complexas e distribuídas**, oferecendo uma forma robusta de **gerenciar estados**, **controlar o fluxo lógico** e **recuperar erros**, sem a necessidade de codificação manual de orquestração.

---

## ⚙️ Como Funciona

A funcionalidade do Step Functions é baseada em **máquinas de estado**, que definem o fluxo de trabalho da aplicação.  
Essas máquinas são criadas usando a **Amazon States Language (ASL)** — um formato baseado em **JSON** ou **YAML**.  

A **criação e visualização** dos fluxos podem ser realizadas por meio de uma interface gráfica intuitiva no console da AWS, o **Workflow Studio**.

---

## 🌟 Benefícios

- ✅ **Orquestração visual e simplificada**  
- 🔁 **Tratamento automático de erros e resiliência**  
- 📊 **Gerenciamento de estado integrado**  
- 🤝 **Integração nativa com serviços da AWS**  
- ☁️ **Arquitetura totalmente sem servidor**

---

## 🚀 Casos de Uso

O Step Functions pode ser aplicado em diversos cenários para automatizar processos complexos, como:

- 📦 **Processamento de pedidos**  
- 🎬 **Processamento de dados e mídia**  
- 🧩 **Orquestração de microsserviços**  
- 🧠 **Automação de tarefas de TI**  
- 👥 **Fluxos de trabalho com intervenção humana**

---
## 🛠️ Criando e executando uma **Lambda** no AWS Step Functions — Passo a passo

### Passos rápidos
1. No console da AWS, pesquise por **Step Functions** e entre no serviço.  
2. Selecione **“Projeto de exemplo”** (Example projects).  
3. Escolha o projeto **Lambda → Processar arquivos no S3** (ou outro exemplo de Lambda desejado).  
4. Clique em **“Implantar e executar”** (Deploy and run).  
   - A implantação cria os recursos necessários (Lambda, roles, buckets, etc.) normalmente via **CloudFormation**.  
5. Acompanhe a criação dos recursos abrindo o stack gerado no **CloudFormation** (Console → CloudFormation → selecione o stack).  

### Visualizando e editando a máquina de estado
- Em **Step Functions**, abra a máquina de estado criada e clique em **“Editar máquina de estado”**.  
  - Ali você verá o **estado atual** da máquina e poderá editar a definição.  
- Na aba **Design** (Designer) é mostrada a visão *visual* do fluxo de trabalho — muito útil para entender e ajustar o fluxo.  
- Ao lado do **Design** há a aba que mostra o **código completo** (a definição da máquina em ASL — JSON/YAML). Você pode editar o ASL diretamente ou ajustar no Design.

### Executando o fluxo
1. Com a máquina de estado aberta, clique em **Executar** (Start execution).  
2. Informe o **JSON de entrada** (input) que a execução deve receber (por exemplo informações do arquivo S3 ou parâmetros necessários pela Lambda).  
3. Confirme e **inicie a execução**.  
4. A execução aparecerá em tempo real no console do Step Functions: cada estado mostrará sucesso, erro ou execução em progresso.

### Monitoramento e logs
- Para detalhes de logs da **Lambda**, abra o **CloudWatch Logs** (procure pelo grupo de logs da função Lambda).  
- O Step Functions também oferece histórico de execução com erros detalhados (tracebacks e causa).  
- Use métricas do CloudWatch (executions, failed, timed_out, etc.) para monitorar em produção.

### Permissões e atenção (boas práticas)
- Verifique o **role IAM** criado para o Step Functions / Lambda — ele deve ter permissão para acessar S3, CloudWatch e outras integrações necessárias.  
- Se o exemplo cria buckets S3 com dados de teste, revise políticas para evitar exposição pública.  
- Ao terminar os testes, **remova o stack do CloudFormation** para evitar custos (Delete stack).

---

## 📚 Projetos de Exemplo

Dentro do **AWS Step Functions**, é possível escolher e implementar **projetos de exemplo** diretamente no console, o que facilita o aprendizado e acelera o desenvolvimento de novos fluxos de trabalho.

---

## 🧩 Recursos Adicionais

- [Documentação Oficial da AWS Step Functions](https://docs.aws.amazon.com/step-functions/)    
- [Workflow Studio - AWS Console](https://aws.amazon.com/step-functions/)

## Todas as informações foram extraídas do curso Code Girls, e da internet

📅 **Última atualização:** 29 de Outubro de 2025
