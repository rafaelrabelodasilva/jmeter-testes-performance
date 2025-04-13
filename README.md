# Apache JMeter v5.6.3 - Testes de Performance 📚

## O que é um teste de performance? 💡

Um teste de performance avalia a capacidade de um sistema em lidar com uma carga específica de usuários ou transações, garantindo que ele funcione de forma eficiente e confiável.

## Por que utilizar o JMeter? ✅

O JMeter é uma ferramenta poderosa e gratuita para realizar testes de performance. Ele suporta diversos protocolos, como HTTP, SOAP, REST, FTP, entre outros, e permite a criação de testes automatizados e relatórios detalhados.

---

## Sobre o Curso 🧑‍🎓

### Este projeto faz parte de um curso que ensina:

- **JMeter**:
  - Utilizar o JMeter.
  - Compreender a arquitetura do JMeter.
  - Aprender sobre os componentes do JMeter.
  - Criar scripts de testes automatizados.

- **Projeto 1 (eCommerce)**:
  - Criar planos de teste para seu cliente ou empresa.
  - Criar testes para:
    - Um usuário navegando na loja.
    - Um usuário buscando produtos.
    - Um usuário realizando uma compra.
    - Validação de ordem de compra.

- **Performance**:
  - Realizar testes de performance na prática.
  - Criar testes de performance de acordo com suas necessidades.

- **Webservices**:
  - Criar testes para arquitetura REST com métodos GET e POST.
  - Criar testes para arquitetura SOAP com HTTP POST.

- **Conceitos**:
  - Protocolo HTTP e Status Code.
  - Indicadores, volumetria e cenários de testes.
  - Defeitos de testes de performance.

---

## Instalação ⚙️

1. Certifique-se de que o **Java** está instalado na máquina.
2. Faça o download do zip do [Apache JMeter](https://jmeter.apache.org/) e extraia no disco `C:`.

---

## Execução do JMeter via Linha de Comando 🪄

### Passos:

Utilizarei como exemplo como está na minha máquina.

1. Acesse a raiz onde está o teste a ser executado:
   `"/c/projetos/udemy/jmeter/JMeter - Testes de performance/src/fluxo-ecomerce"`

2. Execute os comandos abaixo conforme necessário:

   - Para abrir a interface gráfica do JMeter:
     ```
     $ "C:\jmeter\bin\jmeter.bat"
     ```

   - Para abrir a interface gráfica com o plano de teste:
     ```
     $ "C:\jmeter\bin\jmeter.bat" -t ecomerce.jmx
     ```

   - Para executar o plano de teste sem interface gráfica:
     ```
     $ "C:\jmeter\bin\jmeter.bat" -n -t ecomerce.jmx
     ```

   - Para coletar os resultados do plano de teste e salvar no arquivo `resultado.jtl` (poderia ser `.csv` também):
     ```
     $ "C:\jmeter\bin\jmeter.bat" -n -t ecomerce.jmx -l resultado.jtl
     ```

   - Para gerar o relatório (dashboard) por linha de comando:
     ```
     $ "C:\jmeter\bin\jmeter.bat" -g resultado.jtl -o jmeterDash
     ```

     **Importante**: Se for gerar uma nova dashboard com o mesmo comando acima, é necessário deletar a pasta `jmeterDash` e o arquivo `resultado.jtl`, pois não é possível existir dois com o mesmo nome.

   - Para executar o plano de teste sem interface gráfica e, na sequência, gerar o relatório (dashboard):
     ```
     $ "C:\jmeter\bin\jmeter.bat" -n -t ecomerce.jmx -l resultado.jtl -e -o jmeterDash
     ```

---

## Mais sobre linhas de Comandos 🧙

### Sintaxe:

```
jmeter -n -t meu_teste.jmx
```

### Opções:

- `-n`: Essa opção diz para o JMeter ser executado apenas por linha de comando (sem a interface gráfica).
- `-t`: Seu script plano de teste (arquivo JMX).
- `-l`: Arquivo log de resultados do seu teste (arquivo JTL).
- `-j`: Arquivo log de execução do JMeter.
- `-r`: Opção para execução remota, usando os servidores especificados na propriedade `remote_hosts`.
- `-R`: Executa em um servidor específico.
- `-g`: Arquivo CSV para geração do dashboard.
- `-o`: Pasta de saída onde será gerado o dashboard. A pasta não pode existir ou deve estar vazia.
- `-H`: Proxy server hostname.
- `-P`: Proxy server porta.

### Exemplos:

1. Apenas executar o teste:
   ```
   jmeter -n -t meu_plano.jmx
   ```

2. Executar o teste e salvar o log de resultados:
   ```
   jmeter -n -t meu_plano.jmx -l resultado.jtl
   ```

3. Executar o teste e gerar a dashboard quando o teste finalizar:
   ```
   jmeter -n -t meu_plano.jmx -l resultado.jtl -e -o nomeMinhaDashboard
   ```

4. Apenas gerar a dashboard (é necessário ter o arquivo de resultado de testes):
   ```
   jmeter -g resultado.jtl -o nomeMinhaDashBoard
   ```

5. Executar um teste usando proxy:
   ```
   jmeter -n -t meu_plano.jmx -l resultado.jtl -H my.proxy.server -P 8080
   