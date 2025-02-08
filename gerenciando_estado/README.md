Uma forma de manipular estados no react é com a utilização de `hooks` como o `useEffect`.

```jsx
import { useEffect } from 'react';

function Component () {
    useEffect(() => {
        /*
        códigos aqui dentro são execultados no momento
        em que o componenete é montado. (mount)
        */
       return () => {};  // função executada no momento em que o componente é desmontado (unmount)
    },
    []  // lista de dependencias usadas pela função
    )
}
```
1. primeiro o react executa o código dentro da função quando o componente é montado.

2. após cada re-renderização quando as dependencias mudam o react executa o metodo de `unmount` com o estado e props antigos e depois a função de `mount`com o novo estado e props.

3. por fim o react executa a função de `unmount` uma ultima vez removendo o componente da pagina.
