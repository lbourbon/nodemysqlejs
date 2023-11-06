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


## Criar database/databse.js

<code>
const Sequelize = require("sequelize")

const connection = new Sequelize('nomeDoBanco', 'root<usuário>', 'senha', {
  host: 'localhost',
  dialect: 'mysql'
})

module.exports = connection
</code>
