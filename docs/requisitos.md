# Requisitos

## Requisitos Funcionais (RF)

| Código | Requisito Funcional                                                                               |
| ------ | ------------------------------------------------------------------------------------------------- |
| RF01   | O sistema deve permitir login de usuários com diferentes perfis (RH, gestor, colaborador, admin). |
| RF02   | O sistema deve permitir o cadastro, edição e exclusão de usuários.                                |
| RF03   | O gestor deve poder criar e enviar avaliações para seus subordinados.                             |
| RF04   | O colaborador deve poder preencher sua autoavaliação.                                             |
| RF05   | O sistema deve armazenar as respostas das avaliações de forma segura e organizada.                |
| RF06   | O gestor e o RH devem poder visualizar o histórico de avaliações por colaborador.                 |
| RF07   | O sistema deve gerar relatórios individuais e por setor, com base nas avaliações.                 |
| RF08   | O RH deve poder gerar e visualizar a matriz 9-box com base nos critérios definidos.               |
| RF09   | O administrador deve poder definir, editar e excluir critérios de avaliação.                      |
| RF10   | O sistema deve exportar relatórios em PDF ou CSV.                                                 |
| RF11   | O sistema deve enviar notificações (e-mail ou painel) sobre avaliações pendentes.                 |


## Requisitos Não Funcionais (RNF)
| Código | Requisito Não Funcional                                                               |
| ------ | ------------------------------------------------------------------------------------- |
| RNF01  | O sistema deve estar disponível 99% do tempo (alta disponibilidade).                  |
| RNF02  | O tempo de resposta para gerar relatórios não deve ultrapassar 3 segundos.            |
| RNF03  | O sistema deve ser responsivo e funcionar bem em desktop, tablets e celulares.        |
| RNF04  | Os dados dos usuários e avaliações devem ser armazenados de forma criptografada.      |
| RNF05  | O sistema deve suportar pelo menos 1.000 usuários simultâneos.                        |
| RNF06  | O sistema deve seguir boas práticas de segurança (como autenticação JWT e HTTPS).     |
| RNF07  | A interface deve ser acessível conforme diretrizes WCAG (ex: contraste, teclado etc.) |
| RNF08  | O sistema deve permitir integração futura com ERPs e plataformas de RH.               |
| RNF09  | O sistema deve registrar logs de ações críticas (ex: login, edição de avaliação).     |
| RNF10  | O sistema deve estar documentado (manual de uso e documentação da API REST).          |
