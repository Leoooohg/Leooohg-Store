<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tienda de Packs</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, sans-serif;
}

body{
    background:#111;
    color:white;
}

header{
    background:#1a1a1a;
    padding:20px;
    text-align:center;
    font-size:28px;
    font-weight:bold;
}

.container{
    max-width:1200px;
    margin:auto;
    padding:30px;
}

.page{
    display:none;
}

.active{
    display:block;
}

.card{
    background:#1f1f1f;
    border-radius:15px;
    overflow:hidden;
    max-width:400px;
    margin:auto;
    box-shadow:0 0 15px rgba(0,0,0,.5);
}

.card img{
    width:100%;
    height:250px;
    object-fit:cover;
}

.card-content{
    padding:20px;
    text-align:center;
}

button{
    background:#00c853;
    color:white;
    border:none;
    padding:12px 25px;
    border-radius:10px;
    cursor:pointer;
    font-size:16px;
    margin-top:10px;
}

button:hover{
    background:#00e676;
}

.back{
    background:#444;
}

.price{
    font-size:28px;
    color:#00e676;
    margin:15px 0;
}

ul{
    text-align:left;
    margin:20px auto;
    max-width:400px;
}

li{
    margin:10px 0;
}
</style>
</head>
<body>

<header>
🚗 Tienda de Packs
</header>

<div class="container">

    <!-- CATALOGO -->
    <div id="catalogo" class="page active">

        <h1 style="text-align:center;margin-bottom:30px;">
            Catálogo
        </h1>

        <div class="card">

            <img src="https://images.unsplash.com/photo-1492144534655-ae79c964c9d7?w=1200" alt="Auto">

            <div class="card-content">

                <h2>Pack Autos Premium</h2>

                <p>
                    Los mejores vehículos disponibles.
                </p>

                <button onclick="mostrarProducto()">
                    Ver Producto
                </button>

            </div>
        </div>

    </div>

    <!-- PRODUCTO -->
    <div id="producto" class="page">

        <h1 style="text-align:center;margin-bottom:20px;">
            Pack Autos Premium
        </h1>

        <ul>
            <li>BMW M3 Competition</li>
            <li>Audi RS7</li>
            <li>Lamborghini Huracán</li>
            <li>Ferrari SF90</li>
            <li>Porsche 911 Turbo S</li>
        </ul>

        <div style="text-align:center;">
            <div class="price">
                $9.990 CLP
            </div>

            <!-- CAMBIA EL LINK -->
            <a href="https://link.mercadopago.cl/TU-LINK" target="_blank">
                <button>
                    Comprar
                </button>
            </a>

            <br>

            <button class="back" onclick="volverCatalogo()">
                Volver
            </button>
        </div>

    </div>

</div>

<script>
function mostrarProducto(){
    document.getElementById("catalogo").classList.remove("active");
    document.getElementById("producto").classList.add("active");
}

function volverCatalogo(){
    document.getElementById("producto").classList.remove("active");
    document.getElementById("catalogo").classList.add("active");
}
</script>

</body>
</html>
