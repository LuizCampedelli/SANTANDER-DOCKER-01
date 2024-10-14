# Docker simple deployment

docker buildx build -t meu_app_py -f flask.Dockerfile .

docker run -d -p 5000:5000 meu_app_py

docker stop <container id>

or

docker stop $(docker ps -q) >>> stop all containers

if you get any error in docker logs <container id>, add to requeirements: Werkzeug==2.0.3, to add WSGI libraries to the project

mandar para o docker
]
]docker login

docker tag <noe do meu app ou o que eu quiser> nome do meu usuario:versao da minha tag

docker tag meu_app_py vapeprosper/meu_app_py:v.1 >>> jeito correto de taggear

push: docker push vapeprosper/meu_app_py:v.1

docker push <nome do usuario no docker hub>/<nome do app>:<versao>

se fizer mudanças, faz o buldx de novo, fazer uma nova tag, versionando, e fazer um novo docker push dessa tag

para rodar:

docker run -d --name <nome do app> -p localport:dockerport <nome da imagem:versao da imagem>

exe: docker run -d --name banana -p 9000:5000 <bananaspli:v.1>

ARG:

docker buildx build -t image-args .

docker run image-args

Se o CMd náo for passado, o arg se encontrará dentro do argumento do container, podendo ser visto atraves do docker inspect <id do container>

            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
                "S3_BUCKET=arquivos"
