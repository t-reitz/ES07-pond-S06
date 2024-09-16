# Proposta de Melhoria de Segurança em Sistemas Conversacionais (LLMs)

## Introdução

Sistemas conversacionais, especialmente aqueles baseados em Modelos de Linguagem de Grande Escala (LLMs ou Large Language Models), estão se tornando cada vez mais populares. No entanto, com essa popularidade, surgem inúmeros desafios significativos em termos de segurança. Segundo Zou et al. (2023), ataques adversariais podem manipular LLMs para gerar respostas inadequadas ou potencialmente prejudiciais, mesmo quando o modelo foi afinado para alinhar com valores humanos. Isso porque, existem maneiras de influenciar a LLM a produzir uma resposta maliciosa. Estes ataques exploram falhas na segurança do software, criando a necessidade de abordagens robustas de mitigação para proteger contra essas vulnerabilidades.

## Solução Proposta

### Módulos adaptados para maior segurança

1. **Módulo de Filtragem de Entrada**: Analisa as entradas dos usuários para detectar e flagrar possíveis técnicas maliciosas.
2. **Módulo de Detecção de Ataques Adversariais**: Utiliza modelos probabilísticos para identificar sufixos e prefixos adversariais anexados a consultas.
3. **Módulo de Alinhamento e Reinforcement Learning**: Realiza ajustes contínuos no modelo para melhorar a resistência contra novos ataques detectados, dessa forma, o modelo pode aprender com as técnicas flagradas no módulo de filtragem de entrada para se previnir contra essas técnicas no futuro.
4. **Monitoramento e Logging de Segurança**: Mantém logs detalhados de todas as interações e eventos de segurança para auditorias e resposta a incidentes, adicionando uma etapa de identificação dos usuários.
5. **Módulo de Resposta a Incidentes**: Automatiza a resposta a eventos de segurança detectados, incluindo bloqueio de entradas maliciosas e ajuste dos modelos.

## Conclusão

Melhorar a segurança de sistemas conversacionais baseados em LLMs requer um esforço multidisciplinar, tanto dos desenvolvedores que fine tunam esses modelos e também a capacidade do próprio modelo de se adaptar a técnicas maliciosas. Isso combina aprendizado de máquina, segurança de software e monitoramento contínuo. A proposta apresentada aqui fornece uma arquitetura escalável e resiliente para mitigar esses riscos de segurança que estão cada vez mais comuns. Porém, isso requer um investimento significativo em termos de desenvolvimento e recursos computacionais. Além disso, existe uma certa balança entre esses Módulos descritos acima e a qualidade da resposta dessas LLMs: isso porque esses módulos adicionais restringem de certa forma a resposta e isso impacta diretamente na qualidade da resposta. Por fim, essa balança deve ser muito bem ajustada (no fine tuning) para tanto produzir respostas de qualidade, e ainda bloquear intenções maliciosas; algo que não é uma tarefa fácil e requer muito esforço na etapa de testagem.

## Referências Bibliográficas

- ZOU, Andy; WANG, Zifan; CARLINI, Nicholas; NASR, Milad; KOLTER, J. Zico; FREDRIKSON, Matt. _Universal and Transferable Adversarial Attacks on Aligned Language Models_. arXiv preprint arXiv:2307.15043, 2023.
- GOODFELLOW, Ian; et al. _Explaining and Harnessing Adversarial Examples_. arXiv preprint arXiv:1412.6572, 2014.
- SCHNEIER, Bruce. _Applied Cryptography: Protocols, Algorithms, and Source Code in C_. John Wiley & Sons, 1996.
- ITPEDIA. Large Language Models (LLMs) in Cyber Security. Disponível em: https://pt.itpedia.nl/2024/05/25/large-language-models-llms-in-cyber-security/. Acesso em: 13 set. 2024.
