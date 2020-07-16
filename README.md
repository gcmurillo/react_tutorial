# Tutorial de React 
React es un *framework* para la creación de interfaces de usuario interactivas de forma sencilla. Es basado en componentes, los cuales manejan sus propios estados lo que permite crear interfaces más complejas, según tu necesidad. lógica de los componentes está escrita en JavaScript y no en plantillas, puedes pasar datos de forma sencilla a través de tu aplicación y mantener el estado fuera del DOM. 

Si quiere saber más sobre React, revise la documentación oficial. En este tutorial veremos un ejemplo de creación de componentes y filtrado de datos. Comencemos!

## Crear un nuevo proyecto de React.
Como requisito tiene que tener instalado `npm`. Ejecutamos el siguiente comando:
```bash
$ npm init react-app tutorial
```

Cuando se termine de crear el proyecto, tendrá la siguiente estructura.

![primero](https://github.com/gcmurillo/react_tutorial/blob/master/capturas/1.jpg)

Nuestro archivo principal es el `App.js`

```JS
import React from 'react';
import logo from './logo.svg';
import './App.css';

function App() {
  return (
      <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;
```

Ya lo modificaremos más adelante. Veamos qué nos muestra por defecto. Ejecutemos en el terminal:

```bash
$ npm start
```

En nuestro terminal

![segundo](https://github.com/gcmurillo/react_tutorial/blob/master/capturas/2.JPG)

En nuestro navegador

![tercero](https://github.com/gcmurillo/react_tutorial/blob/master/capturas/3.JPG)

Hemos levantado nuestra app localmente, pero queda más por resolver. 

Para el presente tutorial, vamos a cargar datos desde el API de Google Books, presentar libros y a realizar busquedas. En el tutorial usaremos componentes.

## Creando nuevos componentes

Como se menciona en la introduccion, React es un *framework* para *frontend* basado en componentes. Para crear un nuevo componente, creamos una nueva carpeta llamara *components* donde colocaremos los componentes. El primer componente que vamos a crear es **MiCard**, que será el que muestre la información de los libros individualmente. Vamos poco a poco.

*miCard.js*
```JS
import React, { Component } from 'react';

class MiCard extends Component {
    render() {
        return (
            <h1>Mi card</h1>
        )
    }
}

export default MiCard;
```

Esta es la declaración más sencilla de un componente. Nuestra nueva clase `MiCard` extiende de la clase `Component` propia de *React*. Ya veremos que significa aquello. Los componentes de *React* usan la funcion `render` para retornar lo que muestran en pantalla. Dentro de nuestros archivos *javascript* estaran nuestras vistas.

Vamos a colocar en el archivo *App.js* nuestro nuevo componente 

*App.js*
``` JS
function App() {
  return (
    <div className="App">
      <header className="App-header">
        <MiCard></MiCard>
      </header>
    </div>
  );
}
```

![cuarto](https://github.com/gcmurillo/react_tutorial/blob/master/capturas/4.JPG)
