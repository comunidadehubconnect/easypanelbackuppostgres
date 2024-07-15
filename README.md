<p align="center">
<img src="https://cwmkt.com.br/wp-content/uploads/2024/04/logo_github.png" width="240" />
<p align="center">Seja bem-vindo ao Guia de Instalação EasyPanel Postgres Backup 🚀</p>
</p>
  
<p align="center"> 
<a href="https://hubconnect.top" target="_blank">👉 Participe da Comunidade HubConnect 👈</a>
</p>

<hr />
<hr />

## Comando para Instalar EasyPanel

```bash
curl -sSL https://get.easypanel.io | sh
```

Adicione nome de Project

![48098522-0c485df00f5cadb0d329061c35fee46c](https://github.com/cwmkt/easypanelevotypebot/assets/91642837/b72c1359-91ca-4bf6-9fb1-32525ba5747b)

Clique na aba Templates

![image](https://github.com/user-attachments/assets/9d41ae87-dd7e-4003-a0a1-78f6a643065b)

Localize APP Minio, clique nele

![image](https://github.com/user-attachments/assets/eb5e2ae7-c1de-40f5-928a-08559470ab6a)

Crie suas credenciais depois botão CREATE

![image](https://github.com/user-attachments/assets/7e3ac114-bd94-48a5-80b3-eae4aa5da3bc)

Abaixo já temos credecial do Minio

![image](https://github.com/user-attachments/assets/15a24527-778a-494a-90ee-bf6820a7d801)

Agora precisamos acessa e criar Bucket chamado backup

![image](https://github.com/user-attachments/assets/7e081b24-630f-4f71-8da1-15ea3071ec0f)

![image](https://github.com/user-attachments/assets/3be40fb4-d10d-4e24-8ac2-8af68d42b4d6)

Deixe seu backup como publico 

![image](https://github.com/user-attachments/assets/49ca427b-40b0-46d9-9d34-197822f577fc)

Agora precisamos das credenciais

![image](https://github.com/user-attachments/assets/2e035ff6-b143-4ff3-8565-661a2798bb18)

![image](https://github.com/user-attachments/assets/bd8a5c24-7941-4f07-b267-59c764987183)

Copie suas credenciais para podemos usar mais pra frente


Agora vamos instalar Postgres Backup

Clique na aba Templates

![image](https://github.com/user-attachments/assets/9d41ae87-dd7e-4003-a0a1-78f6a643065b)

Localize APP POstgres Backup, clique nele

![image](https://github.com/user-attachments/assets/012b4825-f36d-4157-9934-dea3e9bf8b79)

Troque a parte de App Service Image para 

```bash
jnettome/postgres-backup-s3:15
```

Adicone as informações abaixo, nesse caso Minio vai ser nosso S3

![image](https://github.com/user-attachments/assets/41837e10-7857-45ca-a813-5f7e859a956b)

Execute a criação 

Agora vamos ajustar as variaveis 

Aba Environment Variables

```bash
POSTGRES_HOST=IPServer
POSTGRES_PORT=5432
POSTGRES_USER=postgres
POSTGRES_PASSWORD=senha
POSTGRES_DATABASE=banco dados
S3_ACCESS_KEY_ID=IDS3
S3_SECRET_ACCESS_KEY=KEYS3
S3_BUCKET=backup
S3_PREFIX=backup
S3_REGION=us-east-1
S3_ENDPOINT=https://urlS3
S3_S3V4=yes
SCHEDULE=0 0,8,16 * * *
```

Salve e mande fazer build novamente

Agora seu sistema vai rodar cron 3 vezes por dia fazendo backups de seu banco de dados e armazenando em nuvem

Pronto tudo Funcionando ✅😎

