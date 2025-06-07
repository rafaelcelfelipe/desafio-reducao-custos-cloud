# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS – Redução dos Custos em Farmácias com AWS

**Data de Início do Projeto:** 01/06/2025  
**Empresa:** Abstergo Industries  
**Responsável:** Rafael Celso Felipe  

---

## Introdução

Este relatório descreve a implementação de três serviços AWS no âmbito do desafio “Redução dos Custos em Farmácias com AWS”, conduzido por Rafael Felipe Celso Felipe na Abstergo Industries. O objetivo foi reduzir custos operacionais imediatos em uma rede de farmácias, mantendo escalabilidade, performance e compliance regulatório.

---

## Descrição do Projeto

O projeto foi dividido em três etapas, cada uma focada em um serviço AWS alinhado às necessidades específicas de uma farmácia:

### Etapa 1: AWS Lambda  
- **Foco:** execução serverless de lógica de negócio.  
- **Caso de uso em farmácias:**  
  - Acionamento de funções na venda de itens para atualizar estoque e emitir notificações (SMS/e-mail) sem necessidade de servidor 24/7.  
  - Gatilho em upload de receitas ou notas fiscais no S3 para processar OCR ou gerar cópias digitais automaticamente.  

### Etapa 2: Amazon S3 com Lifecycle Policies  
- **Foco:** armazenamento de objetos com tiering automático.  
- **Caso de uso em farmácias:**  
  - Armazenamento de imagens de receitas, notas fiscais e logs de transações em S3 Standard;  
  - Move para Standard-IA após 30 dias e Glacier após 90 dias, garantindo compliance (retenção mínima) e reduzindo em ~60 % o custo de armazenamento.  

### Etapa 3: EC2 Auto Scaling + Spot Instances  
- **Foco:** elasticidade de infraestrutura com economia de custos.  
- **Caso de uso em farmácias:**  
  - Processamento batch de vendas diárias e relatórios de performance histórica, escalando até 10 instâncias Spot durante picos;  
  - Mantém mínimo de 2 instâncias On-Demand para atender requisições críticas do ERP/PDV;  
  - Economia de até 70 % em computação.

---

## Conclusão

Com a adoção dessas três soluções, a Abstergo Industries obteria:

- **Computação mais econômica:** ~50 % de redução de custos via Lambda e Spot Instances.  
- **Armazenamento otimizado:** ~60 % de economia com S3 Lifecycle.  
- **Operação enxuta:** menos servidores de longa execução, menor overhead de manutenção.  
- **Escalabilidade sob demanda:** recursos alinhados à sazonalidade e horários de pico das farmácias.

Recomenda-se manter monitoramento contínuo pelo **AWS Cost Explorer** e **AWS Budgets**, além de avaliar:

- **Amazon RDS Aurora Serverless** para banco de dados relacional elástico.  
- **AWS Savings Plans** ou **Reserved Instances** para cargas previsíveis (PDV 24/7).  
- **AWS Compute Optimizer** para ajuste automático de tamanho de instâncias.  

---

**Assinatura do Responsável pelo Projeto:**  
Rafael Celso Felipe
