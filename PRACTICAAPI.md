---
attachments: [Clipboard_2023-12-02-16-48-11.png]
title: 'UNIDAD 3.1: Práctica de una API usando POKE API en Django'
created: '2023-12-02T22:35:17.771Z'
modified: '2023-12-02T22:48:11.724Z'
---

# UNIDAD 3.1: Práctica de una API usando POKE API en Django

Cuando ya se haya entendio lo que es y como funciona una API, vamos a realizar una práctica en Django con lo siguiente:

1. Primero vamos a crear una nueva carpeta en la ruta **ProgramacionRedes/mysite/webapp/layouts/** y dentro de esa carpeta de layouts/ vamos a crear un archivo llamada **layouts.html** y configuramos lo siguiente (esto va a servir para poder evitar escribir tanto código en un HTML y evitar problemas con cada línea de comando de nuestras páginas HTML):

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>
        {% block title %}{% endblock %}
    </title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">
  </head>
  <body>
    {% block content %}{% endblock %}
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL" crossorigin="anonymous"></script>
  </body>
</html>
```

2. Luego vamos a crear un archivo en templates/ y lo llamaremos **poke.html** y configuramos lo siguiente (esto es para poder mostrar tanto a todos los pokémons como un formulario de busqueda):

```html
{% extends "layouts/layouts.html" %}

{% block title %} poke-api.html {% endblock %}

{% block content %}
    <div class="container text-center">
      <div class="row align-items-center">
        <div class="col">
            <h1>
                Poke-Api
            </h1>
        </div>
      </div>
      <div class="row align-items-center">
        <div class="col" id="root">
        </div>
      </div>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
    {% load static %}
    <script src="{% static 'js/poke-api.js' %}">
    </script>
{% endblock %}
```

3. Por último configuramos el JS de la poke api de HTML mencionado anteriormente en la ruta **ProgramacionRedes/mysite/webapp/static/js/** y se llamará **poke-api.js** y configuramos lo siguiente (esto realiza las peticiones, las transforma en un JSON y trata de estructura todo de una forma concreta y válida):

```js
let root = document.getElementById("root");

const format_data = (json) => {
    
    let data = JSON.parse(JSON.stringify(json));

    console.log(data);

    search_pokemon();

    count_pokemon(data.count);

    table_content(data.results);

}

const send_input = () => {

    let value = document.getElementById("buscador_pokemon").value;

    const action = (data) => {

        let tipos = data.types.map( (types) => types.type.name );

        let stats = data.stats.map( (stats) => [stats.stat.name, stats.base_stat] );

        Swal.fire({
          title: data.name,
          html: `
            <p>
                Experiencia base: ${data.base_experience} <br/>
                Tipos: ${tipos} <br/>
                Peso: ${data.weight} <br/>
                <h5><b></n>Estádisticas:</b></h5>
                <code>
                    ${stats.map((element)=> `${element[0]}:${element[1]}<br/>`).join('')}
                </code>
            </p>
          `,
          imageUrl: data.sprites.front_default,
          confirmButtonText: 'Cerrar',
        });

    }

    fetch('https://pokeapi.co/api/v2/pokemon/'+value)
    .then( (response) => response.json() )
    .then( (json) => action(JSON.parse(JSON.stringify(json))) )
    .catch( () => alert("Tipo de pokemon no encontrado"));
}

const send_type_input = () => {

    let valor = document.getElementById("buscador_tipo_pokemon").value;

    let tabla = document.getElementsByClassName("table");

    tabla[0].remove();
    
    const action = (json) => {

        const data = json.pokemon.map((element)=>{
            return {
                'name': element.pokemon.name,
                'url': element.pokemon.url,
            }
        });

        table_content(data.slice(0, 21));
    }

    fetch('https://pokeapi.co/api/v2/type/'+valor)
    .then((response) => response.json())
    .then((json) => action(JSON.parse(JSON.stringify(json))) );

}

const search_pokemon = () => {

    root.innerHTML += `
        <div class="form-group mt-1">
            <input type="text" id="buscador_pokemon" class="input input-text" placeholder="Buscar pokemon">
            <button class="btn btn-primary btn-sm" onclick="send_input()">Búscar</button>
        </div>
        <div class="form-group mt-1">
             <select class="custom-select" id="buscador_tipo_pokemon">
                <option selected>Filtro por tipo</option>
                <option value="1">Normal</option>
                <option value="2">Lucha</option>
                <option value="3">Volador</option>
                <option value="4">Veneno</option>
                <option value="5">Tierra</option>
                <option value="6">Roca</option>
                <option value="7">Insecto</option>
                <option value="8">Fantasma</option>
                <option value="9">Metal</option>
                <option value="10">Fuego</option>
                <option value="11">Agua</option>
                <option value="12">Hierba</option>
                <option value="13">Electrico</option>
                <option value="14">Psicquico</option>
                <option value="15">Hielo</option>
                <option value="16">Dragon</option>
                <option value="17">Siniestro</option>
                <option value="18">Hada</option>
            </select>
            <button class="btn btn-primary btn-sm" onclick="send_type_input()">Búscar</button>
        </div>
    `;

}

const count_pokemon = (count) => {
    root.innerHTML += `<h2 id="count" count="${count}">Total de pokemon's: ${count}</h2>`;
}

const btn_click = (url) =>{

    const action = (data) => {

        let tipos = data.types.map( (types) => types.type.name );

        let stats = data.stats.map( (stats) => [stats.stat.name, stats.base_stat] );

        Swal.fire({
          title: data.name,
          html: `
            <p>
                Experiencia base: ${data.base_experience} <br/>
                Tipos: ${tipos} <br/>
                Peso: ${data.weight} <br/>
                <h5><b></n>Estádisticas:</b></h5>
                <code>
                    ${stats.map((element)=> `${element[0]}:${element[1]}<br/>`).join('')}
                </code>
            </p>
          `,
          imageUrl: data.sprites.front_default,
          confirmButtonText: 'Cerrar',
        });

    }

    fetch(url)
    .then( (response) => response.json() )
    .then( (json) => action(JSON.parse(JSON.stringify(json))) );

}

const table_content = (pokemons) => {

    root.innerHTML += `
        <table class="table">
          <thead class="thead-dark">
            <tr>
              <th scope="col">Nombre</th>
              <th scope="col">Imagen</th>
              <th scope="col">Información</th>
            </tr>
          </thead>
          <tbody id="tdata">
          </tbody>
        </table>
    `;

    let tdata = document.getElementById("tdata");

    const expresion_regular = /(\d+)/g;

    for (let i=0; i < pokemons.length; i++){


        let url = pokemons[i].url;

        let poke_imagen = url.match(expresion_regular)[1];

        tdata.innerHTML += `
            <tr>
                <td>
                    ${pokemons[i].name}
                </td>
                <td>
                    <img 
                        src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${poke_imagen}.png" 
                        alt="${pokemons[i].name}"
                    />
                </td>
                <td>
                    <button 
                        class="btn btn-secondary" 
                        data="${pokemons[i].url}"
                        onclick="btn_click('${pokemons[i].url}')"
                    >
                        Información de ${pokemons[i].name}
                    </button>
                </td>
            </tr>
        `;
    
    }

}

const data = () => {
    fetch("https://pokeapi.co/api/v2/pokemon/")
    .then((response) => response.json())
    .then((json) => format_data(json) );
}

data();
```

4. Al final vamos encendemos el servidor de nuestro Django y con esto tiene que funcionar el API (debe utilizar internet para este aspecto de trabajo)

---

# CAPTURAS DE FUNCIONAMIENTO

![](@attachment/Clipboard_2023-12-02-16-48-11.png)
