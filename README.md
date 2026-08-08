# Aplicação dos Benchmarks de Otimização e Segurança na Quitandinha Online

1.Introdução dos Valores

 É necessário sempre ter em mente métricas de qualidade e eficiência de um projeto, os Benchmarks trem essa finalidade, podem ser categorizados em  pilares como: 
 
  **Otimização**
   **Segurança**
   **Custo**
   **Manutenção**
   **Confiabilidade**
   **Eficiência **
Iremos visar aplicar os conceitos fundamentais dos pilares de **Eficiência**, **Segurança**,**Otimização**
 
 **1. Benchmark de Segurança**

Definição estendida: avalia a capacidade do sistema de resistir a ataques, proteger dados sensíveis (login, endereço, dados de pagamento) e manter a integridade das informações contra acessos não autorizados. Isso inclui tanto vulnerabilidades no código da aplicação (falhas de programação que um invasor pode explorar) quanto na infraestrutura (servidor, banco de dados, configurações de rede). Para um e-commerce, segurança fraca não é só risco técnico — é risco de reputação e legal, já que envolve dados pessoais protegidos pela LGPD (Lei Geral de Proteção de Dados) e, se houver pagamento próprio, também normas de PCI-DSS.

Exemplo prático: rodar uma varredura com OWASP ZAP simulando um cliente tentando alterar a URL do pedido (ex: trocar pedido_id=101 por pedido_id=102) para ver se consegue acessar dados de outra pessoa. Se conseguir, é uma falha de controle de acesso — crítica, precisa ser corrigida antes de ir ao ar.

**2. Benchmark de Otimização**

Definição estendida: mede a velocidade e a fluidez da experiência do usuário durante a navegação — desde o momento em que ele clica no link até a página estar completamente carregada e interativa. Envolve fatores como tamanho de imagens, quantidade de scripts carregados, uso de cache do navegador, e a estrutura do código front-end (HTML/CSS/JS). Otimização ruim afeta diretamente a taxa de conversão: estudos mostram que cada segundo a mais de carregamento pode reduzir significativamente as vendas, especialmente em compras por impulso como as de uma quitandinha (o cliente decide rápido, e se a página trava, ele desiste).

Exemplo prático: rodar o Google PageSpeed Insights / Lighthouse na página de produtos (com fotos de frutas e verduras) e medir o LCP. Se estiver acima de 2,5s, o problema geralmente é imagem pesada sem compressão — a solução é converter para WebP e usar lazy loading.

**3. Benchmark de Eficiência**

Definição estendida: avalia quão bem o sistema utiliza os recursos computacionais (CPU, memória RAM, banco de dados, largura de banda) para entregar cada requisição do usuário. Diferente da otimização (que foca na percepção do cliente), a eficiência foca no "custo interno" de operar o sistema — ou seja, quantos usuários simultâneos o servidor aguenta antes de degradar, e quanto isso custa em infraestrutura (hospedagem, banco de dados na nuvem). Isso é essencial para planejar o crescimento: uma quitandinha que começa pequena mas quer expandir para vários bairros precisa saber se o sistema aguenta o aumento de pedidos sem precisar reescrever tudo do zero.

Exemplo prático: fazer um teste de carga (com ferramenta como k6 ou JMeter) simulando 100 usuários finalizando compra ao mesmo tempo, medindo o consumo de CPU/memória do servidor. Se o uso disparar demais com poucos usuários, indica que o código do checkout ou as queries do banco precisam ser otimizadas antes de escalar a operação.

Resumindo a diferença:

Benchmark	Pergunta que responde	Foco principal
Segurança	"O site está protegido contra invasões e vazamentos?"	Proteção de dados e integridade
Otimização	"O site é rápido para o cliente?"	Experiência do usuário
Eficiência	"O site usa bem os recursos do servidor pra sustentar o crescimento?"	Custo e escalabilidade


