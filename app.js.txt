// app.js
const shops = [
    {name: 'Local Electronics', product: 'Washing Machine', price: '₹20,000'},
    {name: 'Tech World', product: 'Washing Machine', price: '₹19,500'},
    {name: 'Super Shop', product: 'Washing Machine', price: '₹21,000'}
];

function searchProduct() {
    const searchInput = document.getElementById('productSearch').value.toLowerCase();
    const resultsDiv = document.getElementById('results');
    resultsDiv.innerHTML = '';

    const filteredShops = shops.filter(shop => shop.product.toLowerCase() === searchInput);

    if (filteredShops.length > 0) {
        filteredShops.forEach(shop => {
            const shopItem = `
                <div class="shop-item">
                    <h3>${shop.name}</h3>
                    <p>Product: ${shop.product}</p>
                    <p>Price: ${shop.price}</p>
                </div>
            `;
            resultsDiv.innerHTML += shopItem;
        });
    } else {
        resultsDiv.innerHTML = '<p>No shops found for this product.</p>';
    }
}
