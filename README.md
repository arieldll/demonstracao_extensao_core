Demonstração de extensão do core free5GC utilizando OpenAPI

Para começar, vamos instalar o OpenAPI. A instalação se baseou no seguinte link: https://openapi-generator.tech/docs/installation/

Começando... 

Primeiro passo: Instalar o OpenAPI CLI

```
$ sudo apt-get install curl
```

Verifique se o NodeJS está instalado em seu Ubuntu, através do comando: 
```
$ node --version
```

Se não tiver instalado, siga os comandos abaixo. Essa versão é a compatível com o Ubuntu 22.04. 

Baixe o script de instalação. Se seu Ubuntu é mais novo, por favor, atualize a string "setup_16.x" para a versão necessária: 
```
$ sudo curl -sL https://deb.nodesource.com/setup_16.x -o /tmp/nodesource_setup.sh
```

Agora execute o arquivo: 

```
$ sudo bash /tmp/nodesource_setup.sh
```

Agora é só instalar via apt

```
$ sudo apt-get install nodejs -y
```

Instalar o Java. Verifique se sua versão é compatível com a versão 18 do JDK ou se for superior, substitua a linha "18-jre" pela versão mais nova: 

```
$ sudo apt-get install -y openjdk-18-jre
```

Agora, vamos instalar o OpenAPI generator de forma global (parâmetro -g), que é o cliente que irá gerar os nossos arquivos da OpenAPI:
```
$ sudo npm install @openapitools/openapi-generator-cli -g
```

Setar a versão 5.3 do gerador. Esse passo é recomendado pelo site do OpenAPI:

```
$ openapi-generator-cli version-manager set 5.3.0
```

Agora, na linha abaixo, vamos gerar o nosso yaml baseado na linguagem de programação selecionada: 

```
$ npx @openapitools/openapi-generator-cli generate -i TSFunction.yaml -g (language: go) -o /tmp/test/ 
```

Caso o comando apresente problemas de validação de SPEC, adicione o parâmetro --skip-validate-spec

```
$ npx @openapitools/openapi-generator-cli generate -i TSFunction.yaml -g (language: go) -o /tmp/test/ --skip-validate-spec
```

Se tudo estiver correto, as classes serão geradas. Como esqueleto, verifique o arquivo nef.go deste repositório, como o exemplo de uma função que se registra à NRF no endereço http://127.0.0.10:8000