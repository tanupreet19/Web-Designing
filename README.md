# Web-Designing
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>YUMMY SNACKS | Premium Online Food Store</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
  <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>
  <style>
    html {
      scroll-behavior: smooth;
    }
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: #fff5db;
      margin: 0;
      padding: 0;
    }
    header {
      background: linear-gradient(90deg, #ff8c00, #ff4500);
      color: white;
      padding: 15px 30px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      position: sticky;
      top: 0;
      z-index: 10;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    }
    header h1 {
      margin: 0;
      font-size: 30px;
      font-weight: bold;
    }
    nav a {
      color: white;
      text-decoration: none;
      margin: 0 15px;
      font-weight: 600;
      transition: color 0.3s;
    }
    nav a:hover {
      color: #ffd700;
    }
    .hero {
      background: url('https://img.freepik.com/premium-photo/variation-different-unhealthy-snacks-crackers-sweet-salted-popcorn-tortillas-nuts-straws-bretsels_136595-3540.jpg') no-repeat center center/cover;
      color: white;
      text-align: center;
      font-size: 24px;
      padding: 120px 20px;
    }
    .hero h2 {
      font-size: 56px;
      margin-bottom: 10px;
    }
    .product {
      background: white;
      padding: 20px;
      border-radius: 16px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .product:hover {
      transform: translateY(-10px);
      box-shadow: 0 16px 32px rgba(0, 0, 0, 0.15);
    }
    .product img {
      width: 100%;
      height: 240px;
      object-fit: cover;
      border-radius: 12px;
    }
    footer {
      background: linear-gradient(90deg, #ff4500, #ff8c00);
      color: white;
      text-align: center;
      padding: 20px;
      margin-top: 40px;
    }
  </style>
</head>
<body>
  <header>
    <h1>🍔🍟 YUMMY SNACKS</h1>
    <nav>
      <a href="#home">Home</a>
      <a href="#foods">Products</a>
      <a href="#about">About</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <section id="home" class="hero">
    <h2>INDULGE IN DELICIOUS BITES</h2>
    <p>Treat yourself with the tastiest snacks around</p>
  </section>

  <section id="foods" class="container py-5">
    <h2 class="text-center mb-4">🍕 Trending Snacks</h2>
    <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4 g-4" id="productList"></div>
  </section>

  <script>
    const productList = document.getElementById("productList");

    const snacks = [
      { name: "Crunchy Chips", price: 149, image: "https://cdn.shopify.com/s/files/1/0258/6496/2125/files/mr-tortillas-crunchy-chips-variety-pack-478063.jpg?v=1718745288", delivery: "April 18" },
      { name: "Chocolate Bar", price: 199, image: "https://www.wonkachocolatebars.com/wp-content/uploads/2024/01/IMG_7623.jpg", delivery: "April 19" },
      { name: "Lays Classic", price: 120, image: "https://www.lays.com/sites/lays.com/files/2019-09/Classic.png", delivery: "April 20" },
      { name: "Fruit Snack Pack", price: 349, image: "https://s7.orientaltrading.com/is/image/OrientalTrading/k1420-b?$PDP_VIEWER_IMAGE$", delivery: "April 22" }
    ];

    function renderProducts(items) {
      productList.innerHTML = "";
      items.forEach((product, i) => {
        const col = document.createElement("div");
        col.className = "col";
        col.innerHTML = `
          <div class="product h-100">
            <img src="${product.image}" alt="${product.name}" />
            <h5 class="mt-3">${product.name}</h5>
            <p>Price: ₹${product.price}</p>
            <p>Delivery: ${product.delivery}</p>
            <div class="d-flex justify-content-between">
              <button class="btn btn-success">Add to Cart</button>
            </div>
          </div>
        `;
        productList.appendChild(col);
      });
    }


    renderProducts(snacks);
  </script>
</body>
</html>
