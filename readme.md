<h1>API de Tienda de Joyas</h1>
<p>Esta es una API para gestionar joyas en una tienda. Permite realizar operaciones como obtener todas las joyas con paginación y ordenamiento, así como filtrar joyas por diferentes criterios.</p>

<h2>Requisitos</h2>
<ul>
    <li>Node.js</li>
    <li>npm </li>
    <li>Express.js</li>
</ul>


<h2>Endpoints</h2>

<h3>Obtener Todas las Joyas</h3>
<p><strong>GET</strong> <code>/api/joyas</code></p>
<p>Obtiene una lista de todas las joyas con soporte para paginación y ordenamiento.</p>



<h4>Ejemplo de Consulta:</h4>
<pre><code>curl "http://localhost:3000/api/joyas?limits=3&page=2&order_by=precio_DESC"</code></pre>

<h4>Respuesta Ejemplo:</h4>
<pre><code>{
"totalJoyas": 15,
"joyas": [
{ "id": 4, "nombre": "Anillo de plata", "categoria": "anillos", "metal": "plata", "precio": 200, "stock": 10 },
{ "id": 8, "nombre": "Collar de oro", "categoria": "collares", "metal": "oro", "precio": 500, "stock": 5 }
],
"links": {
"self": "/api/joyas?limits=3&page=2&order_by=precio_DESC",
"next": "/api/joyas?limits=3&page=3&order_by=precio_DESC"
}
}</code></pre>

<h3>Filtrar Joyas</h3>
<p><strong>GET</strong> <code>/api/joyas/filtros</code></p>
<p>Obtiene una lista de joyas filtradas según los criterios proporcionados.</p>


<h4>Ejemplo de Consulta:</h4>
<pre><code>curl "http://localhost:3000/api/joyas/filtros?precio_min=100&precio_max=300&categoria=anillos"</code></pre>

<h4>Respuesta Ejemplo:</h4>
<pre><code>[
{ "id": 2, "nombre": "Anillo de oro", "categoria": "anillos", "metal": "oro", "precio": 250, "stock": 7 },
{ "id": 5, "nombre": "Anillo de plata con diamante", "categoria": "anillos", "metal": "plata", "precio": 150, "stock": 3 }
]</code></pre>

<h2>Manejo de Errores</h2>
<ul>
    <li><strong>500 Internal Server Error</strong>: Ocurre cuando hay un error en el servidor.</li>
    <li><strong>404 Not Found</strong>: Ocurre cuando la ruta solicitada no existe.</li>
</ul>


</body>
</html>