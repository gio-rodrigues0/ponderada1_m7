# Explicação da Ponderada 1

## Construção do currículo

Resolvi fazer um currículo em html simples sendo servido por um servidor em python com o FastAPI.

Obtendo então os três arquivos: index.html, styles.css e main.py.

O processo foi iniciado com a criação de uma env para a instalação dos frameworks necessários e a criação do arquivo requirements.txt para anotar tais frameworks.

## Construção do Dockerfile

No arquivo Dockerfile foram escritos todos os processos que devem ser realizados para rodar a aplicação, obtendo os seguintes passos:

- Seleção da imagem pertencente ao Python3, como não há versão definida, a imagem mais recente é selecionada.
- Criação do diretório "code" no conteiner.
- Cópia do arquivo requirements.txt dentro do diretório criado.
- Intalação de todas as dependências demarcadas no arquivo requirements.txt
- Cópia dos demais arquivos do diretório.
- Exposição da porta 3000.
- O arquivo responsável pelo servidor é rodado.

## Criação da imagem

Para a criação de uma imagem nós usamos o comando:

```
docker build -t ponderada1:latest .
```
O ponto significa que o Dockerfile que será buildado é o que estiver naquele diretório.

Depois de buildado, é possível iniciar a imagem com o seguinte comando:

```
docker run -dp 3000:3000 ponderada1
```

A primeira porta definida é aquela do seu computador enquanto a segunda será a do container.

## Hospedando a imagem no DockerHub

Para subir a imagem no DockerHub é preciso, em primeiro lugar, criar um diretório por meio da web.

Depois, uma tag é adicionada a imagem por meio de:

```
docker tag ponderada1:latest giovanna0/ponderada1:latest
```

Sendo "ponderada1" o nome da imagem, "latest" sendo a sua tag e "giovanna0/ponderada1" o nome do repositório.

E então, enviar a imagem para o repositório com o comando:

```
docker push giovanna0/ponderada1:latest
```

Logo, a imagem que possuir tag "latest" que esteja relacionada ao repositório demarcado será enviada.