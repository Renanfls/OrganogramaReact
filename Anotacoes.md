# **Base do React**

## **No terminal**

`npx create-react-app organo`

**organo** É o nome do projeto

npm - Utilizado para rodar coisas locais
npx - Roda um script de forma remota

#

## **Subindo a aplicação**

`npm start`

A pasta `public` é utilizada para imagens estaticas

#

# **Componentes**

**Forma mais comum**
<code>

    import './'

    const NomeDoComponente = () => {

    }

    export default NomeDoComponente
<code>

**Outra forma**

<code>

    function NomeDoComponente() {
        return (

        )
    }

    export default NomeDoComponente
<code>

#

- O JSX parece um HTML mas não é
- JSX é como o react lê uma tag img por exemplo e transforma em elementos no DOM

<code>

    function Banner() {
        // JSX
        return (
            <img src="/imagens/banner.png" alt=""/>
        )
    }

    export default Banner
</code>

# 

## **Atribuindo class em JSX**

Não utilizamos apenas `class` pois é uma palavra reservada do JS, para atribuir classes utlizamos `className`

<code>

    // JSX
    return (
        <header className="banner">
            <img src="/imagens/banner.png" alt=""/>
        </header>
    )
</code>

#

Componentes React começam com letra maiuscula

#

# **Parâmetros de componentes**

### **Arquivo `index.js`**
<code>

    const CampoTexto = (props) => {
        return (
            <div className="campo-texto">
                <label>{props.label}</label>
                <input placeholder={props.placeholder}/>
            </div>
        )
    }
</code>

Parâmetro `props` muito utilizado por devs. e significa **propriedades**

### **Arquivo `App.js`**

<code>

    function App() {
        return (
            <div className="App">
            <Banner /> 
            <CampoTexto label="Nome" placeholder="Digite seu nome"/>
            <CampoTexto label="Cargo" placeholder="Digite seu cargo"/>
            <CampoTexto label="Imagem" placeholder="Digite o endereço da imagem"/>
            </div>
        );
    }
</code>

O arquivo `App.js` passa os valores explicitos em seus determinados parâmetros 

#

# **Interpolação de Strigs em JS**

Utilizamos a Interpolação `` (Crases)

**Concatenação**

Utilizamos `` `${}` ``

<code>

    <input placeholder={`${props.placeholder}...`}/>
</code>

#

## **Atalho VSCode**

CTRL + Espaço (Localiza e importa o documento caso o componente seja realocado para outro arquivo)

#

# **Componentes Funcionais**

#### **Componente funcional:**

<code>

    function BoasVindas(props) {
        return <h1>Olá, {props.nome}</h1>;
    }
</code>

#### **O mesmo componente, baseado em classes, seria:**

<code>

    class BoasVindas extends React.Component {
        render() {
            return <h1>Olá, {this.props.nome}</h1>;
        }
    }
</code>

#

**Single Page Application (SPA)**

Uma aplicação que roda em uma unica página

#

# **Iterando uma lista com React**

Para iterar em React usamos o `map()` um método do JS que itera e renderiza, diferente do `forEach()` que apenas itera.

O `map()` percorre o array, executa alguma função e retorna um novo array transformado.

**Forma Longa**
<code>

    {props.itens.map(item => {
        return <option>{item}</option>
    })}
<code>

**Forma Reduzida**
<code>

    {props.itens.map(item => <option>{item}</option>)}
<code>

#

**Data Binding**

Termo usado quando se Linka um valor do input com uma variavel, se a variavel muda, o input muda e vice versa

#

## **Recebendo Propriedades atraves do filho**

`children` -> crianças(filhos)

<code>

    <button className="botao">{props.children}</button>
</code>

Dessa forma o componente recebe como paramentro tudo que esta entre <Botao></Botao>

Assim tambem podemos colocar imagens como se tivesse na estrutura de um HTML

<code>

    <Botao>
        Criar Card
    </Botao>
</code>