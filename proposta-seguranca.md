# Proposta de Melhoria de Segurança em Sistemas Conversacionais (LLMs)

## Introdução

&emsp;Sistemas conversacionais, especialmente aqueles baseados em Modelos de Linguagem de Grande Escala (LLMs ou Large Language Models), estão se tornando cada vez mais populares. No entanto, com essa popularidade, surgem inúmeros desafios significativos em termos de segurança. Segundo Zou et al. (2023), ataques adversariais podem manipular LLMs para gerar respostas inadequadas ou potencialmente prejudiciais, mesmo quando o modelo foi afinado para alinhar com valores humanos. Isso porque, existem maneiras de influenciar a LLM a produzir uma resposta maliciosa. Estes ataques exploram falhas na segurança do software, criando a necessidade de abordagens robustas de mitigação para proteger contra essas vulnerabilidades.

## Principais Problemas Relacionados a LLMs

1. **Injeção de Prompt Adversarial**: Um dos ataques mais comuns é a manipulação de prompts para induzir o modelo a gerar respostas prejudiciais ou ofensivas. Esses ataques são complexos de detectar e podem violar regras de segurança. O **Módulo de Filtragem de Entrada** e o **Módulo de Detecção de Ataques Adversariais** são cruciais para identificar e neutralizar entradas suspeitas antes do processamento.
2. **Evasão de Políticas de Alinhamento**: Técnicas de "jailbreaking" permitem que usuários contornem as regras de segurança e obtenham respostas proibidas, comprometendo o alinhamento ético do modelo. O **Módulo de Alinhamento e Reinforcement Learning** é necessário para ajustar o modelo e reforçar regras de segurança sem sacrificar a qualidade das respostas.
3. **Evasão de Detecção**: Invasores podem desenvolver métodos para escapar dos mecanismos de detecção, como logs de segurança e módulos de filtragem. Modificando padrões de ataque, conseguem evadir detecções convencionais. O **Monitoramento e Logging de Segurança** é vital para analisar interações, identificar novos padrões de ataque e registrar atividades para auditoria.
4. **Respostas Automatizadas Adversárias**: O **Módulo de Resposta a Incidentes** pode ser manipulado para gerar respostas automatizadas adversas, criando reações indesejadas ou incorretas do modelo. É crucial projetar respostas a incidentes que diferenciem entre ataques genuínos e falsos positivos.
5. **Impacto na Qualidade das Respostas**: Módulos de segurança rigorosos podem afetar a qualidade das respostas do LLM. Apesar da prioridade na segurança, deve-se equilibrar entre respostas naturais e restrições, garantindo que o sistema seja eficaz e atraente. O ajuste fino deve otimizar a segurança sem comprometer a usabilidade.

&emsp;Os módulos citados nesses principais problemas estão na próxima secção (Módulos adaptados para maior segurança), onde uma breve descrição de cada parte da solução proposta foi incluida para melhorar a segurança em geral de sistemas convesacionais.

## Solução Proposta

### Módulos adaptados para maior segurança

1. **Módulo de Filtragem de Entrada**: Analisa as entradas dos usuários para detectar e flagrar possíveis técnicas maliciosas.
2. **Módulo de Detecção de Ataques Adversariais**: Utiliza modelos probabilísticos para identificar sufixos e prefixos adversariais anexados a consultas.
3. **Módulo de Alinhamento e Reinforcement Learning**: Realiza ajustes contínuos no modelo para melhorar a resistência contra novos ataques detectados, dessa forma, o modelo pode aprender com as técnicas flagradas no módulo de filtragem de entrada para se previnir contra essas técnicas no futuro.
4. **Monitoramento e Logging de Segurança**: Mantém logs detalhados de todas as interações e eventos de segurança para auditorias e resposta a incidentes, adicionando uma etapa de identificação dos usuários.
5. **Módulo de Resposta a Incidentes**: Automatiza a resposta a eventos de segurança detectados, incluindo bloqueio de entradas maliciosas e ajuste dos modelos.

## Conclusão

&emsp;Melhorar a segurança de sistemas conversacionais baseados em LLMs requer um esforço multidisciplinar, tanto dos desenvolvedores que fine tunam esses modelos mas também a capacidade do próprio modelo de se adaptar a identificar técnicas maliciosas. Isso combina aprendizado de máquina, segurança de software e monitoramento contínuo. A proposta apresentada tem como objetivo mitigar esses riscos de segurança que estão cada vez mais comuns. Porém, isso requer um investimento significativo em termos de desenvolvimento e recursos computacionais. Além disso, existe uma certa balança entre esses Módulos descritos acima e a qualidade da resposta dessas LLMs: isso porque esses módulos adicionais restringem de certa forma a resposta e isso impacta diretamente na qualidade da resposta. Por fim, essa balança deve ser muito bem ajustada para tanto produzir respostas relevantes e de qualidade, e ainda bloquear intenções maliciosas; algo que não é uma tarefa fácil e requer muito esforço na etapa de testagem.

## Referências Bibliográficas

- ZOU, Andy; WANG, Zifan; CARLINI, Nicholas; NASR, Milad; KOLTER, J. Zico; FREDRIKSON, Matt. Universal and Transferable Adversarial Attacks on Aligned Language Models, 20 Dec 2023. Disponível em: https://arxiv.org/abs/2307.15043. Acesso em: 11 set. 2024.
- ITPEDIA. Large Language Models (LLMs) in Cyber Security. Disponível em: https://pt.itpedia.nl/2024/05/25/large-language-models-llms-in-cyber-security/. Acesso em: 13 set. 2024.
- GENETEC. As implicações de modelos de linguagem grandes na segurança física. Disponível em: https://www.genetec.com/br/blog/cybersecurity/as-implicacoes-de-modelos-de-linguagem-grandes-na-seguranca-fisica. Acesso em: 13 set. 2024.
- BRIGHTSEC. Exploring the Risks of Using Large Language Models. 2023. Disponível em: https://brightsec.com/wp-content/uploads/2023/11/Exploring-the-Risks-of-Using-Large-Language-Models-Final.pdf. Acesso em: 14 set. 2024.
