---
title: "Población de los municipios de Canarias"
---

En este post se hace uso de los datos guardados en formato JSON en el directorio _data/csvjson_p9.json para mostrar una tabla con la población de los municipios de Canarias.

<table>
  <thead>
    <tr>
      <th>Nombre del municipio</th>
      <th>Población</th>
      <th>Tipo de municipio</th>
    </tr>
  </thead>
  <tbody>
    {% for municipio in site.data.csvjson_p9 %}
        <tr>
            <td>{{ municipio.etiqueta}}</td>
            <td>{{ municipio.poblacion}}</td>
            <td>{{ municipio.tipo_municipio}}</td>
        </tr>
    {% endfor %}
  </tbody>
</table>

> Fuente: [Datos obtenidos del Instituto Canario de Estadística](http://www.gobiernodecanarias.org/istac/)
