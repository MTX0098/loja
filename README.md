# loja
um site de loja de roupas online
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Loja de Vestuário</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
            padding: 20px;
        }
        header {
            background-color: #4CAF50;
            color: white;
            padding: 10px 0;
            text-align: center;
        }
        .product {
            background-color: white;
            padding: 15px;
            margin: 10px;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            display: inline-block;
            width: 200px;
            text-align: center;
        }
        .cart {
            margin-top: 20px;
        }
    </style>
</head>
<body>

<header>
    <h1>Loja de Vestuário</h1>
</header>

<div class="products">
    <div class="product">
        <h2>Camiseta</h2>
        <p>Preço: R$ 49,90</p>
        <button onclick="addToCart('Camiseta', 49.90)">Adicionar ao Carrinho</button>
    </div>
    <div class="product">
        <h2>Calça Jeans</h2>
        <p>Preço: R$ 99,90</p>
        <button onclick="addToCart('Calça Jeans', 99.90)">Adicionar ao Carrinho</button>
    </div>
    <div class="product">
        <h2>Jaqueta</h2>
        <p>Preço: R$ 199,90</p>
        <button onclick="addToCart('Jaqueta', 199.90)">Adicionar ao Carrinho</button>
    </div>
</div>

<div class="cart">
    <h2>Carrinho</h2>
    <ul id="cart-items"></ul>
    <p id="total-price">Total: R$ 0,00</p>
</div>

<script>
    let cart = [];
    let total = 0;

    function addToCart(product, price) {
        cart.push({ product, price });
        total += price;
        updateCart();
    }

    function updateCart() {
        const cartItems = document.getElementById('cart-items');
        cartItems.innerHTML = ''; // Limpa a lista atual
        cart.forEach(item => {
            const li = document.createElement('li');
            li.textContent = `${item.product} - R$ ${item.price.toFixed(2)}`;
            cartItems.appendChild(li);
        });
        document.getElementById('total-price').textContent = `Total: R$ ${total.toFixed(2)}`;
    }
</script>

</body>
</html>
