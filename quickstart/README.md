## Instalação
```sh
npm create vite@latest my-app --template react
cd my-app
npm install
npm run dev
```

## Componentes de Classes x Funcionais
```jsx
// componente funcional (Mais recente)
function App(){
    return (
        <div className="App">
            My App
        </div>
    )
}
export default App;
```

```jsx
// componente de classe (Mais comum em versões antigas)
export default class AppClass extends Component {
    constructor(props) {
        super(props);
        this.state = { counter: 0 };
        this.handleClick = this.handleClick.bind(this);
    }

    handleClick() {
        ...
    }

    render() {
        return (
            <div>
                ...
            </div>
        )
    }
}
```


## Componentes e props
- Os componentes são uma forma de padronizar e organizar o projeto em pequenas estruturas de código reutilizáveis.
- As `props` são argumentos que podem ser passados para os componentes.

```jsx
export default function Button(props) {
    const { labelText } = props;
    return (
        <button>{labelText}</button>
    )
}
```

## Ciclo de vida de um componente
Um componente react possui um ciclo de vida onde ele gerencia diversos estados de um componente, por exemplo: Criação do componente, Destruição, alteração de estado, etc.
