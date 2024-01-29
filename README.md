# Repaso módulo 3 REACT

## Qué es React?
React es una libreía de JavaScript para construir interfaces de usuario. Es mantenido por Meta y es open-source.
La principal característica de React es que se basa en componentes, es decir, podemos crear componentes y reutilizarlos en nuestra aplicación.

## ⚛️ JSX
JSX es una extensión de JavaScript creada por Meta (facebook) para el uso con la biblioteca React. Sirve de preprocesador y transforma el código generado con React a JavaScript.

## 💻 Client Side Rendering vs Server Side Rendering
React es una librería que nos permite renderizar el contenido en el lado del cliente (Client Side Rendering). Esto quiere decir que el navegador es el encargado de pintar el contenido de la página. Por el contrario, en el Server Side Rendering, el servidor es el encargado de generar el HTML y enviarlo al navegador (tal y como vimos en el módulo 2 con HBS y Express).

## 👩‍👦 ¿Qué es un componente?
Un componente es una pieza de código que se encarga de una tarea en concreto. Por ejemplo, un componente puede ser un botón, un formulario, una barra de navegación, o incluso una página entera. Los componentes pueden tener hijos, y estos a su vez pueden tener otros hijos, formando una estructura de árbol.

## 📦 Functional components vs Class components
En React podemos crear componentes de dos formas: con funciones o con clases. La forma más moderna y recomendada es con funciones, ya que son más sencillas de escribir y de entender. 
### Functional component
```javascript
// Functional component
function MyComponent() {
  return <p>Hello, world!</p>;
}
export default MyComponent;
```
### Class component
```javascript

// Class component
class MyComponent extends React.Component {
    render() {
        return <p>Hello, world!</p>;
    }
}
export default MyComponent;
```

## 🙍➡️🙋‍♀️ Props
Las props son la forma de pasar datos de componente padre a componente hijo.
```javascript	
// Componente padre
<ChildComponent name="John" />

// Componente hijo
function ChildComponent(props) {
  return <p>Hello, {props.name}</p>;
}
```
El nombre que asignemos a la prop en el componente hijo, será el nombre que tendrá que tener en el componente padre. Accedemos a props como cualquier otro objeto (con dot notation). En el ejemplo anterior, props es un objeto que tiene una propiedad name, y accedemos a ella con ``props.name``.

## 🪝 Hooks
Son funciones que nos permiten usar el estado y otras características de React. Los hooks no funcionan dentro de clases, solo funcionan dentro de componentes funcionales.

## 🗽 Estado
Los estados en un componente son variables que se pueden modificar y que al hacerlo, React se encarga de renderizar el componente de nuevo con los nuevos valores.
Para crear un estado, usamos el hook ``useState``. Este hook nos devuelve un array con dos elementos: el valor del estado y una función para modificarlo. 
```javascript
const [count, setCount] = useState(0);
```
En el ejemplo anterior, ``count`` es el valor del estado y ``setCount`` es la función que nos permite modificarlo. Para modificar el estado, llamamos a la función ``setCount`` y le pasamos el nuevo valor.
```javascript
setCount(1);
```

El estado también tiene acceso al valor anterior, por lo que podemos hacer algo como esto:
```javascript
setCount((prevCount)=> prevCount + 1);
```
El argumento que recibe la función ``setCount`` es el valor anterior del estado.

## useEffect
Es un hook que nos permite ejecutar código cuando se monta, desmonta o actualiza un componente. Es decir, nos permite ejecutar código en ciertos momentos de la vida de un componente.
Es muy útil para hacer peticiones a una API, ya que podemos hacer la petición cuando se monta el componente y guardar los datos en el estado.

### Montar el componente

```javascript	
useEffect(() => {
    // Código que se ejecuta cuando se monta el componente
}, []);
```

### Desmontar el componente

```javascript   
useEffect(() => {
    // Código que se ejecuta cuando se monta el componente
    return () => {
        // Código que se ejecuta cuando se desmonta el componente
    }
}, []);
```

### Actualizar el componente según una variable de estado o prop

```javascript
useEffect(() => {
    // Código que se ejecuta cuando se monta el componente
    return () => {
        // Código que se ejecuta cuando se desmonta el componente
    }
}, [variableDeEstado, prop]);
```

