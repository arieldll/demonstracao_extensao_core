# demonstracao_extensao_core
Demonstração de extensão do core utilizando OpenAPI

Para começar, vamos instalar o OpenAPI. A instalação se baseou no seguinte link: https://openapi-generator.tech/docs/installation/

Começando... 

Instalar o OpenAPI CLI

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
$ npx @openapitools/openapi-generator-cli generate -i petstore.yaml -g ruby -o /tmp/test/
```


