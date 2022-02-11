< -------- Banco de Dados -------- >

#Criar Banco de Dados
sudo docker-compose up -d

#Parar Banco de Dados
sudo docker-compose down -v

#Ativar Banco de Dados
sudo docker-compose -f docker-compose.yml up --build

#Listar containers ativos
sudo docker containers ps

#Listar containers
sudo docker containers ls -a

#Acessar Bancos de dados
sudo docker-compose exec db psql -U postgres -c '\l'

< ----------- Volumes ----------- >

#Acessar Banco de Dados e seus dados pelos Volumes
sudo docker-compose exec db psql -U postgres -f /scripts/check.sql


< ----------- Frontend ----------- >

#Subir o HTML para uma porta
sudo docker-compose logs -f -t

#Verificar se foi para o banco de dados
sudo docker-compose exec db psql -U postgres -d email_sender -c 'select * from emails'

< ---------- Isntâncias ---------- >

#Instalar multiplas instancias
sudo docker-compose up -d --scale worker=3




