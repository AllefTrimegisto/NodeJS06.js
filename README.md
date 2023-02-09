# NodeJS06.js

Faça um servidor web para responder requisições com diferentes status HTTP, os quais devem estar de acordo com os parâmetros enviados pelo placeholder nas requisições. Exemplo: a rota “/listar/50” vai retornar o HTTP 404; a rota /listar/10 vai retornar o HTTP 200 com alguma string.

const express = require('express');
const app = express();

app.get('/listar/:id', (req, res) => {
  const id = req.params.id;

  if (id === '50') {
    res.status(404).send('Not Found');
  } else if (id === '10') {
    res.status(200).send('OK');
  } else {
    res.status(400).send('Bad Request');
  }
});

const port = 8080;
app.listen(port, () => {
  console.log(`Server running at http://localhost:${port}`);
});

Nesse código, estamos criando uma rota GET com o placeholder :id. A variável id é recuperada a partir do objeto req.params. Em seguida, verificamos o valor de id e retornamos um status HTTP diferente com uma string correspondente. Se o valor de id for '50', retornamos o status 404 com a string 'Not Found'. Se for '10', retornamos o status 200 com a string 'OK'. Caso contrário, retornamos o status 400 com a string 'Bad Request'.

Por fim, iniciamos o servidor na porta 8080 usando o método listen e exibimos uma mensagem no console quando o servidor estiver funcionando.

Para rodar o código, você pode salvar o arquivo com uma extensão .js, abrir o terminal e navegar até o diretório onde o arquivo foi salvo. Em seguida, basta digitar o comando node nome_do_arquivo.js e acessar a rota no seu navegador.
