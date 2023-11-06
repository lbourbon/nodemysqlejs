# nodemysqlejs

# CRIAR PROJETO USANDO NODE EXPRESS MYSQL BOOTSTRAP EJS

#Dentro da pasta do projeto no terminal
<code>
npm init    
</code>
#Após escolher nomes
<code>
npm install --save express sequelize mysql2 body-parser ejs
</code>


## Criar index.js
<code>
const express = require('express')
const app = express()
</code>

#View Engine
<code>
app.set('view engine', 'ejs')
</code>

#Static
<code>
app.use(express.static('public')) # criar pasta para arquivos estáticos "public"
</code>

#Body Parser
<code>
app.use(bodyParser.urlencoded({extended: false}))
app.use(bodyParser.json())
</code>

#Rotas
<code>
app.get('/', (req, res) => {
res.render("index")     # vai renderizar o arquivo index.ejs dentro da pasta "views"
})

app.listen(8080, () => {
console.log( "servidor rodando")
})</code>


## Criar pasta database/database.js e criar o banco de dados no mysql workbench

<code>
const Sequelize = require("sequelize")

const connection = new Sequelize('nomeDoBanco', 'root<usuário>', 'senha', {
  host: 'localhost',
  dialect: 'mysql'
})

module.exports = connection
</code>

#Acrescentar no index.js
#Database
<code>
const connection = require("./database/database")
connection.authenticate().then(() => {
  console.log("DB conectado com sucesso")
}).catch((error) => {
  console.log(error)
})
</code>

## Criar pasta Partials
arquivos header.js footer.js e outros componentes reutilizáveis
```html
<!DOCTYPE html>
<html lang='pt-br'>
<head>
    <meta charset='UTF-8'>
    <meta name='viewport' content='width=device-width, initial-scale=1.0'>
    <title>Home</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
    <link rel="stylesheet" href="/css/style.css">
</head>

  FOOTER:

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM" crossorigin="anonymous"></script>
</html>
```
## Obs: usando o bootstrap pelo CDN, precisa baixar o arquivo para o deploy?
