# simulado-distribuidos-11-11

Questão 1. Qual é a função do semáforo no processamento dos pedidos?
O semáforo controla a quantidade de threads que podem executar simultaneamente uma parte do programa. Neste exercício, ele foi configurado para permitir no máximo dois pedidos em processamento ao mesmo tempo, evitando excesso de processamento simultâneo.

Questão 2. Por que é necessário sincronizar os dados entre o servidor principal e a réplica?
A sincronização é necessária para que a réplica receba as informações atualizadas do servidor principal. Isso evita diferenças nos dados dos servidores e garante maior consistência das informações, permitindo que a réplica seja utilizada caso o servidor principal fique indisponível.

Questão 3. O que significa tolerância a falhas e como ela aparece neste programa?
Tolerância a falhas é a capacidade de um sistema continuar funcionando mesmo quando um de seus componentes apresenta problemas. No programa, isso acontece quando o servidor principal fica offline e o sistema utiliza a réplica para consultar o estoque, mantendo o serviço disponível.

Questão 4. Para que serve o Lock no programa e como o controle de acesso aos recursos ajuda a prevenir problemas de concorrência?
O Lock serve para controlar o acesso aos recursos compartilhados entre as threads. Ele garante que apenas uma thread por vez execute a atualização do estoque e o registro dos pedidos, evitando condições de corrida, alterações simultâneas indevidas e inconsistências nos dados.

Questão 5. Considerando a sequência de eventos, a sincronização do estoque deve acontecer antes ou depois do processamento dos pedidos? Explique a relação de causalidade.
A sincronização deve acontecer depois do processamento dos pedidos, porque primeiro o servidor principal precisa atualizar o estoque com as vendas realizadas. Depois disso, a réplica recebe o valor atualizado. Essa sequência mantém a ordem correta dos acontecimentos e evita que a réplica fique com informações desatualizadas.
