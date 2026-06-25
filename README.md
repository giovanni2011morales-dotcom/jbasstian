<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pedidos de Pastelería</title>

<style>
body{
    font-family: Arial, sans-serif;
    max-width: 800px;
    margin: 20px auto;
    padding: 20px;
}

input, select, button{
    width: 100%;
    padding: 8px;
    margin: 5px 0;
}

table{
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;
}

th, td{
    border: 1px solid #ccc;
    padding: 8px;
    text-align: center;
}

th{
    background: #f8b4c4;
}
</style>
</head>
<body>

<h2>Sistema de Pedidos de Pastelería</h2>

<input type="text" id="cliente" placeholder="Quién compró">

<input type="text" id="producto" placeholder="Producto">

<select id="zona">
    <option>Centro</option>
    <option>Norte</option>
    <option>Sur</option>
    <option>Este</option>
    <option>Oeste</option>
</select>

<input type="number" id="precio" placeholder="Precio">

<input type="text" id="pago" placeholder="Quién pagó">

<button onclick="agregarPedido()">Agregar Pedido</button>

<table>
    <thead>
        <tr>
            <th>Cliente</th>
            <th>Producto</th>
            <th>Zona</th>
            <th>Precio</th>
            <th>Pagó</th>
        </tr>
    </thead>
    <tbody id="tablaPedidos"></tbody>
</table>

<script>
function agregarPedido() {
    const cliente = document.getElementById("cliente").value;
    const producto = document.getElementById("producto").value;
    const zona = document.getElementById("zona").value;
    const precio = document.getElementById("precio").value;
    const pago = document.getElementById("pago").value;

    const fila = `
        <tr>
            <td>${cliente}</td>
            <td>${producto}</td>
            <td>${zona}</td>
            <td>$${precio}</td>
            <td>${pago}</td>
        </tr>
    `;

    document.getElementById("tablaPedidos").innerHTML += fila;

    document.getElementById("cliente").value = "";
    document.getElementById("producto").value = "";
    document.getElementById("precio").value = "";
    document.getElementById("pago").value = "";
}
</script>

</body>
</html>
