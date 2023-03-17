# pegar-resultado-do-cookie-com-fetch-
pegar resultado do cookie com fetch
```
// Define a função para extrair o valor do cookie
function extrairValorDoCookie(result, nomeDoCookie) {
  // Extrai todos os cookies da resposta do fetch
  const cookies = result.headers.get('Set-Cookie');
  // Usa a biblioteca js-cookie para obter o valor do cookie desejado
  const valorDoCookie = Cookies.get(nomeDoCookie, cookies);
  // Retorna o valor do cookie
  return valorDoCookie;
}

// Faz a solicitação fetch e armazena a resposta em uma variável
const resultadoFetch = fetch('https://exemplo.com').then(response => {
  // Retorna a resposta como um objeto JavaScript
  return response.json();
}).then(data => {
  // Usa a função "extrairValorDoCookie" para obter o valor do cookie desejado
  const valorEspecifico = extrairValorDoCookie(data, 'nome-do-cookie');
  // Faça algo com o valor do cookie retornado
});
```
