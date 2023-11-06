# nodemysqlejs

# CRIAR PROJETO USANDO NODE EXPRESS MYSQL BOOTSTRAP EJS

#Dentro da pasta do projeto no terminal
<code>
npm init    
</code>
#Após escolher nomes:
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

#Rotas
<code>
app.get('/', (req, res) => {
res.send("Hello, world")
})

app.listen(8080, () => {
console.log( "servidor rodando")
})
</code>
