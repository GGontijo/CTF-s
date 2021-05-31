<h1 align="center">Eternal Loop</h1>
<p align="center">
<img src="https://avatars.githubusercontent.com/u/31746234?s=200&v=4" alt="HackTheBox"/> 
</p>
<h3 align="center">Hack The Box | Dificuldade: Fácil</h3>

<p>Eternal Loop foi um desafio simples, mas satisfatório.</p>
<p>Gastei mais tempo tentando fazer coisas novas do que seguindo o path que imaginei que seria, tempo este que foi recompensado com as coisas novas que aprendi.</p>

<p>Basicamente o desafio consiste em um arquivo .zip, e dentro deste arquivo possui dezenas de outros arquivos cujo nome é a senha do arquivo anterior.
</p>

![Screenshot from 2021-05-30 18-59-12](https://user-images.githubusercontent.com/38219914/120129686-65120d80-c192-11eb-8594-37a5baafcba4.png)

![Screenshot from 2021-05-30 19-00-17](https://user-images.githubusercontent.com/38219914/120129723-722efc80-c192-11eb-9716-81c8b72f9f85.png)

<p>Depois de extrair 5 arquivos usando essa técnica me dei conta do pradrão númerico, com isso já podíamos começar um algoritmo pra automatizar isso</p>

<p>Normalmente eu faria em python, mas como estou em ambiente linux aproveitei para fazer em bash e tentar aprender alguma coisa já que vou utilizar muito durante minha vida usando o pinguim</p>

<h3 align="left">Bruteforce.sh</h3>

<p>Basicamente o script final ficou com os seguintes passos:</p>

- Ler o nome do x.zip atual
- Listar os itens dentro do x.zip atual e extrair a senha
- Usar a senha para extrair o próximo x.zip
- Remover o x.zip anterior
- Repetir o ciclo até uma condição ser quebrada..

<p>A condição que defini foi justamente o padrão númerico, mesmo não tendo a certeza se o arquivo final teria um nome diferente eu optei por fazer desta forma pois foi a única que consegui pensar.</p>

<p>Depois de vários erros e correções, o código final e sua execução:</p>

![Screenshot from 2021-05-30 18-51-51](https://user-images.githubusercontent.com/38219914/120129048-4bbc9180-c191-11eb-856a-57782624044c.png)

![Screenshot from 2021-05-30 19-04-10](https://user-images.githubusercontent.com/38219914/120129950-0731f580-c193-11eb-8025-9a5fad40baf0.png)

<p>500 tentativas depois...</p>

![Screenshot from 2021-05-30 18-54-46](https://user-images.githubusercontent.com/38219914/120129308-b8379080-c191-11eb-9cfb-163f6a1a9c09.png)

<p>Show! o script funcionou</p>

![Screenshot from 2021-05-30 19-15-12](https://user-images.githubusercontent.com/38219914/120130654-b28f7a00-c194-11eb-8720-b5bae483cd2b.png)

<p>Ok, mas agora qual a senha do x.zip final??</p>

![Screenshot from 2021-05-30 19-18-36](https://user-images.githubusercontent.com/38219914/120130974-62fd7e00-c195-11eb-9697-96a39298ca16.png)

<p>Listando o conteúdo não consigo pensar em nada, tentei alguns hash's do nome do arquivo mas sem sucesso</p>

<p>Pensei em fazer outro script para bruteforce desse zip final, mas depois de algumas tentativas o unzip sai de execução o que forçaria um script mais complicado, então decidi pesquisar sobre outras formas de crackear a senha e cheguei ao fcrackzip</p>

![Screenshot from 2021-05-30 19-27-17](https://user-images.githubusercontent.com/38219914/120131344-40b83000-c196-11eb-928c-41c303c9492a.png)

<p>Passando a wordlist rockyou.txt (que já vem com o kali por padrão) e mais alguns parâmetros consegui a senha, easygame.</p>

![Screenshot from 2021-05-30 19-28-28](https://user-images.githubusercontent.com/38219914/120131552-a5738a80-c196-11eb-8a26-699799120180.png)

<h3 align="left">DoNotTouch (PT-br: NãoMeRéla)</h3>

<p>Bom, arquivo final se trata de um banco de dados (sei lá do que, mas envolve música):</p>

![Screenshot from 2021-05-30 19-32-32](https://user-images.githubusercontent.com/38219914/120131788-16b33d80-c197-11eb-8a73-e67bc05609d0.png)

![Screenshot from 2021-05-30 19-34-06](https://user-images.githubusercontent.com/38219914/120131937-6b56b880-c197-11eb-82c7-bf3697930d22.png)

<p>Como eu entendo muito pouco de SQL, resolvi procurar na mão. Depois de um tempinho usando o padrão de flag como filtro, encontrei a flag na tabela</p>

![Screenshot from 2021-05-30 19-39-50](https://user-images.githubusercontent.com/38219914/120132243-00f24800-c198-11eb-8fdd-c92f24acc02f.png)


<h2 align="left">HTB{z1p_and_unz1p_ma_bruddahs}</h2>




