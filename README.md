const products = [
  { name: "Laptop", price: 1200 },
  { name: "Mouse", price: 25 },
  { name: "Keyboard", price: 45 }
];

// Function to create a "box" for each product
function printProductBox(product) {
  const blackBg = "\x1b[40m"; // black background
  const whiteText = "\x1b[37m"; // white text
  const reset = "\x1b[0m"; // reset styles

  // Box width
  const width = 25;

  // Function to pad text to center
  function padCenter(text) {
    const padding = Math.floor((width - text.length) / 2);
    return ' '.repeat(padding) + text + ' '.repeat(width - text.length - padding);
  }

  console.log(blackBg + whiteText);
  console.log('+' + '-'.repeat(width) + '+'); // top border
  console.log('|' + padCenter(`Product: ${product.name}`) + '|'); // product name
  console.log('|' + padCenter(`Price: $${product.price}`) + '|'); // price
  console.log('|' + padCenter('Buy Now') + '|'); // Buy Now
  console.log('+' + '-'.repeat(width) + '+'); // bottom border
  console.log(reset); // reset colors
}

// Call the function for each product
products.forEach(printProductBox);
