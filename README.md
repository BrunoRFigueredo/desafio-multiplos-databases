# desafio-multiplos-databases!

Base A e Base B - Utilizando um único micro-serviço para consumo e instância de postgres para realizar o consumo, a utilização do postgres foi para sanar a redundancia que havia entre os dois payloads (Endereço), já que os dois não precisam ser dados acessados em tempo real não é necessário utilizar um armazenamento em memória. Para consumo da IA através da base B creio que seria necessário um intermediário onde faria a exportação dos dados do postgres e disponibilizaria os mesmos.

Base C - Utilizando um micro-serviço e o banco de dados postgres, porém como esta base precisa de dados acessados em praticamente tempo real, é utilizado o redis que é um banco em memória, onde na primeira consulta possivelmente iria demorar um pouco mais por ter que buscar no postgres/jogar para o redis ou buscar na base e jogar pro postgres/redis, e a partir da segunda consulta o mesmo ia ser praticamente em tempo real, já que a mesma seria diretamente feita no redis.

Para consumo desses micro-serviços poderiam ser utilizados via API onde a autenticação poderia ser com JWT e relatórios emitidos em PDFs.

Segue abaixo o diagrama:


[Desafio drawio](https://user-images.githubusercontent.com/37082376/166008764-25f9a3cb-ca05-4a70-b78e-011a4360efac.png)


