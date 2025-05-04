<meta name='viewport' content='width=device-width, initial-scale=1'/><!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>TIF-till</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f8f9fa;
      margin: 0;
    }
    .navbar {
      background-color: #28a745;
      color: white;
      padding: 15px 20px;
      font-size: 24px;
      font-weight: bold;
      box-shadow: 0 2px 4px rgba(0,0,0,0.1);
      text-align: center; /* Center navbar title */
    }
    .container {
      padding: 20px;
      max-width: 800px;
      margin: 0 auto;
    }
    .module {
      display: none;
      background: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
      margin-bottom: 20px; /* Space between modules if they were all visible */
    }
    .active {
      display: block;
    }
    .btn, .back-button {
      width: 100%;
      margin: 10px 0;
      padding: 15px;
      font-size: 16px;
      background-color: #28a745;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: background-color 0.3s;
      box-sizing: border-box; /* Include padding and border in width */
    }
    .btn:hover, .back-button:hover {
      background-color: #218838;
    }
    .btn:disabled, .back-button:disabled {
        background-color: #999;
        cursor: not-allowed;
    }
    .back-button {
      background-color: #6c757d;
    }
    .back-button:hover {
       background-color: #5a6268;
    }
     .clear-cart {
       background-color: #dc3545;
     }
     .clear-cart:hover {
       background-color: #c82333;
     }

    input, select {
      width: 100%;
      padding: 10px;
      margin: 8px 0;
      border: 1px solid #ddd;
      border-radius: 4px;
      box-sizing: border-box;
    }
     label {
         display: block; /* Labels on their own line */
         margin-bottom: 5px;
         font-weight: bold;
         color: #555;
     }
    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 15px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      background-color: #fff;
    }
    th, td {
      border: 1px solid #ddd;
      padding: 12px;
      text-align: left;
      word-wrap: break-word; /* Ensure content wraps */
    }
    th {
      background-color: #28a745;
      color: white;
      font-weight: bold;
    }
    tr:nth-child(even) {
      background-color: #f2f2f2;
    }
     tr:hover {
         background-color: #e9e9e9;
     }

    #receipt {
      white-space: pre-wrap; /* Use pre-wrap to allow wrapping */
      font-family: Consolas, Monaco, 'Andale Mono', 'Ubuntu Mono', monospace;
      background: #fff;
      padding: 20px;
      border: 1px solid #ccc;
      margin-top: 20px;
      border-radius: 4px;
      overflow-x: auto; /* Add scroll for very wide receipts */
      box-shadow: 0 2px 5px rgba(0,0,0,0.05);
    }
    #stockInfo {
      font-weight: bold;
      margin-bottom: 15px;
      color: #555; /* Default color */
    }
     .low-stock {
         color: #dc3545 !important; /* Red for low stock */
     }
     .ok-stock {
         color: #28a745 !important; /* Green for ok stock */
     }

    #cart {
      list-style-type: none;
      padding: 0;
    }
    #cart li {
      padding: 8px;
      border-bottom: 1px solid #eee;
      background-color: #f8f9fa;
      margin-bottom: 4px;
      border-radius: 4px;
    }
    .status-message {
      padding: 10px;
      margin: 10px 0;
      border-radius: 4px;
      display: none; /* Hidden by default */
      text-align: center;
      font-weight: bold;
    }
    .success {
      background-color: #d4edda;
      color: #155724;
      border: 1px solid #c3e6cb;
    }
    .error {
      background-color: #f8d7da;
      color: #721c24;
      border: 1px solid #f5c6cb;
    }
     .info {
         background-color: #e9ecef;
         color: #333;
         border: 1px solid #dee2e6;
     }
     .warning { /* Added warning style */
         background-color: #fff3cd;
         color: #856404;
         border: 1px solid #ffeeba;
     }


    .loader {
      display: none;
      border: 4px solid #f3f3f3;
      border-top: 4px solid #28a745;
      border-radius: 50%;
      width: 20px;
      height: 20px;
      animation: spin 1s linear infinite; /* Faster spin */
      margin: 20px auto; /* Center loader */
    }
    @keyframes spin {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }
    h2 {
      color: #28a745;
      border-bottom: 2px solid #eee;
      padding-bottom: 10px;
      margin-top: 0; /* Adjusted margin */
    }
     h3, h4 {
         color: #555;
         margin-top: 15px;
         margin-bottom: 10px;
     }
    .report-controls {
      display: flex;
      flex-wrap: wrap; /* Allow items to wrap on small screens */
      gap: 10px;
      margin-bottom: 15px;
      align-items: center; /* Vertically align items */
    }
    .report-controls label {
        margin-bottom: 0; /* Remove bottom margin in flex container */
        font-weight: normal;
    }
     .report-controls input[type="date"] {
         flex-grow: 1; /* Allow date inputs to grow */
         min-width: 120px; /* Minimum width for date inputs */
         width: auto; /* Override 100% width */
     }
     .report-controls button {
         width: auto; /* Override 100% width */
         padding: 10px 15px;
         margin: 0; /* Remove margin */
     }

    .clear-cart {
      background-color: #dc3545;
    }
    .clear-cart:hover {
       background-color: #c82333;
     }


     #add-product-form {
       display: none; /* Hidden by default */
       margin-top: 20px;
       background: #f8f9fa;
       padding: 15px;
       border-radius: 5px;
       box-shadow: inset 0 1px 3px rgba(0,0,0,0.1); /* Inner shadow */
     }
      #add-product-form input,
      #add-product-form select {
          margin-bottom: 10px; /* Space between inputs in form */
      }
      #add-product-form button {
          width: auto; /* Allow buttons in form to size to content */
          padding: 10px 15px;
          margin-right: 10px; /* Space between form buttons */
      }
      #add-product-form button:last-child {
          margin-right: 0;
      }

     /* Style for enabled features - removing disabled state */
     .enabled-feature {
         opacity: 1;
         cursor: pointer;
     }
     .enabled-feature .btn {
         pointer-events: auto; /* Enable click events */
     }


     #inventoryTableBody td:last-child button {
         width: auto;
         padding: 5px 10px;
         margin: 0;
         font-size: 0.9em;
     }
      #inventoryTableBody td {
          vertical-align: middle; /* Vertically center table cell content */
      }
       #inventoryTableBody th:last-child,
       #inventoryTableBody td:last-child {
           text-align: center; /* Center align actions column */
       }

     #salesTableBody th:last-child,
     #salesTableBody td:last-child {
        text-align: right; /* Align totals to the right in reports */
     }
     #salesTableBody th:nth-last-child(2),
     #salesTableBody td:nth-last-child(2) {
        text-align: right; /* Align unit price to the right in reports */
     }
     #salesTableBody th:nth-last-child(3),
     #salesTableBody td:nth-last-child(3) {
        text-align: center; /* Center align quantity */
     }


     #sales-summary {
         margin-top: 20px;
         padding: 15px;
         background: #e9ecef;
         border-radius: 5px;
         border: 1px solid #dee2e6;
     }
     #sales-summary p {
         margin-top: 0;
         margin-bottom: 8px;
     }
     #sales-summary ul {
         padding-left: 20px;
         margin-top: 8px;
     }

     /* Adjust for smaller screens */
     @media (max-width: 600px) {
         .container {
             padding: 10px;
         }
         .navbar {
             font-size: 20px;
             padding: 10px 15px;
         }
         .report-controls {
             flex-direction: column; /* Stack report controls */
             gap: 5px;
         }
          .report-controls input[type="date"], .report-controls button {
              width: 100%; /* Full width stacked */
              margin: 0;
          }
          th, td {
              padding: 8px;
              font-size: 0.9em;
          }
          /* Optional: Make inventory table responsive by stacking cells if needed
             (More complex JS/CSS required) */
     }
  </style>
</head>
<body>
<div class="navbar">TIF-till</div>
<div class="container">
  <div id="home" class="active module">
    <h2>Main Menu</h2>
    <button class="btn" id="cash-register-btn">Cash Register</button>
    <button class="btn" id="inventory-btn">Inventory Management</button>
    <button class="btn" id="reports-btn">Sales Reports</button>
  </div>

  <div id="cash" class="module">
    <h2>Cash Register</h2>
     <div id="status-message" class="status-message"></div>

    <label for="product">Select Product:</label>
    <select id="product">
      <option value="">Loading products...</option> </select>

    <h4 id="stockInfo">Stock: ---</h4> <label for="quantity">Quantity:</label>
    <input type="number" id="quantity" value="1" min="1">

    <button class="btn" id="add-to-cart-btn">Add to Cart</button>

    <h3>Current Cart</h3>
    <ul id="cart"></ul>
    <h4>Total: $<span id="total">0.00</span></h4>

    <div class="loader" id="cart-loader"></div>

    <button class="btn" id="complete-transaction-btn">Complete Sale</button>
    <button class="btn clear-cart" id="clear-cart-btn">Clear Cart</button>

    <div id="receipt"></div>
    <button class="btn" id="download-btn" style="display:none;">Download Receipt PDF</button>

    <button class="back-button" id="cash-back-btn">Back to Home</button>
  </div>

  <div id="inventory" class="module">
    <h2>Inventory Management</h2>
    <div id="inventory-status" class="status-message"></div>
    <div class="loader" id="inventory-loader"></div>

    <button class="btn" id="add-product-btn">Add New Product</button>
    <div id="add-product-form">
        <h3>Add New Product</h3>
         <input type="text" id="new-product-name" placeholder="Product Name" required>
          <select id="new-product-category" required>
              <option value="">-- Select Category --</option>
              <option value="Cosmetics">Cosmetics</option>
              <option value="Jewellery">Jewellery</option>
              <option value="Hair">Hair</option>
              <option value="Nail Products">Nail Products</option>
              <option value="Other">Other</option>
          </select>
         <input type="number" id="new-product-price" placeholder="Price" step="0.01" min="0" required>
         <input type="number" id="new-product-stock" placeholder="Initial Stock" min="0" required>
         <input type="number" id="new-product-reorder" placeholder="Reorder Level" min="0" required>
         <button class="btn" id="save-product-btn">Save Product</button>
         <button class="back-button" id="cancel-add-product-btn">Cancel</button>
     </div>


    <table>
      <thead>
        <tr>
          <th>Product</th>
           <th>Category</th>
          <th>Stock</th>
          <th>Price</th>
           <th>Reorder</th>
          <th>Last Updated</th>
          <th>Actions</th> </tr>
      </thead>
      <tbody id="inventoryTableBody">
        <tr><td colspan="7" style="text-align:center;">Loading inventory...</td></tr>
      </tbody>
    </table>

    <button class="btn" id="refresh-inventory-btn">Refresh Inventory</button>
    <button class="back-button" id="inventory-back-btn">Back to Home</button>
  </div>

  <div id="reports" class="module">
    <h2>Sales Reports</h2>
    <div class="report-controls">
      <label for="start-date">From:</label>
      <input type="date" id="start-date">
      <label for="end-date">To:</label>
      <input type="date" id="end-date">
      <button class="btn" id="generate-report-btn">Generate Report</button>
    </div>

    <div class="loader" id="report-loader"></div>
    <div id="report-status" class="status-message"></div>

    <table>
      <thead>
        <tr>
          <th>Date</th>
           <th>Time</th>
          <th>Product</th>
           <th>Category</th>
          <th>Quantity</th>
          <th>Unit Price</th>
          <th>Line Total</th>
        </tr>
      </thead>
      <tbody id="salesTableBody">
        <tr><td colspan="7" style="text-align:center;">Select a date range and click "Generate Report".</td></tr>
      </tbody>
    </table>

    <h3>Summary</h3>
    <div id="sales-summary">
      <p>Generate a report to see the summary.</p>
    </div>

    <button class="back-button" id="reports-back-btn">Back to Home</button>
  </div>
</div>

<script>
  // --- Constants and Global Variables ---
  // URL for your Google Apps Script deployed as a Web App
  // This Apps Script now includes doGet and an updated doPost to handle different actions.
  // Replace with your actual deployed script URL
  const API_URL = "https://script.google.com/macros/s/AKfycbwucWKA65PsJF40oHTsavGLWTDeeecchnZfR7L-pnN6wGPFA5RKiqvrMvZB3LH3Z4QA1g/exec";
  const BUSINESS_NAME = "TIF-till";
  const BUSINESS_ADDRESS = "123 Main St, City"; // Placeholder for receipt
  const BUSINESS_PHONE = "(555) 123-4567"; // Placeholder for receipt

  // Internal state storage (in memory for the current session)
  // Data will be loaded from and synced to the Apps Script API.
  let products = []; // Array of { id, name, category, price, stock, reorder, lastUpdated }
  let cartItems = []; // Array of { id, name, category, price, quantity, lineTotal }

  let total = 0; // Total of current cart

  // --- Initialization ---
  window.onload = function() {
    console.log("Window loaded. Setting up event listeners and initializing UI.");
    setupEventListeners();

    // Set default dates for reports (last 7 days)
    const endDateInput = document.getElementById('end-date');
    const startDateInput = document.getElementById('start-date');
    const today = new Date();
    const lastWeek = new Date(today);
    lastWeek.setDate(lastWeek.getDate() - 7);

    if(endDateInput) endDateInput.value = today.toISOString().split('T')[0];
    if(startDateInput) startDateInput.value = lastWeek.toISOString().split('T')[0];

     // Start by showing the home module
     showModule('home');
     // Initial product load will happen when entering the Cash module.
     // Inventory fetch will happen when entering the Inventory module.
  };

  // --- Event Listeners Setup ---
  function setupEventListeners() {
    console.log("Setting up event listeners.");
    // Navigation buttons
    document.getElementById('cash-register-btn').addEventListener('click', () => showModule('cash'));
    document.getElementById('inventory-btn').addEventListener('click', () => showModule('inventory'));
    document.getElementById('reports-btn').addEventListener('click', () => showModule('reports'));

    // Cash Register module buttons and input change
    const productSelect = document.getElementById('product');
    if(productSelect) productSelect.addEventListener('change', updateStockInfo);

    const addToCartBtn = document.getElementById('add-to-cart-btn');
    if(addToCartBtn) addToCartBtn.addEventListener('click', addToCart);

    const completeTransactionBtn = document.getElementById('complete-transaction-btn');
    if(completeTransactionBtn) completeTransactionBtn.addEventListener('click', completeTransaction);

    const clearCartBtn = document.getElementById('clear-cart-btn');
    if(clearCartBtn) clearCartBtn.addEventListener('click', clearCart);

    const downloadBtn = document.getElementById('download-btn');
    if(downloadBtn) downloadBtn.addEventListener('click', downloadPDF);

    const cashBackBtn = document.getElementById('cash-back-btn');
    if(cashBackBtn) cashBackBtn.addEventListener('click', () => showModule('home'));

    // Inventory module buttons and form
    const addProductBtn = document.getElementById('add-product-btn');
    if(addProductBtn) addProductBtn.addEventListener('click', showAddProductForm);

    const saveProductBtn = document.getElementById('save-product-btn');
    if(saveProductBtn) saveProductBtn.addEventListener('click', addNewProduct);
     // Save Product button in the form is initially disabled until form is valid.
     if(saveProductBtn) saveProductBtn.disabled = true;


    const cancelAddProductBtn = document.getElementById('cancel-add-product-btn');
    if(cancelAddProductBtn) cancelAddProductBtn.addEventListener('click', hideAddProductForm);

    const refreshInventoryBtn = document.getElementById('refresh-inventory-btn');
    if(refreshInventoryBtn) refreshInventoryBtn.addEventListener('click', fetchInventoryData);

    const inventoryBackBtn = document.getElementById('inventory-back-btn');
    if(inventoryBackBtn) inventoryBackBtn.addEventListener('click', () => showModule('home'));

    // Reports module buttons
    const generateReportBtn = document.getElementById('generate-report-btn');
    if(generateReportBtn) generateReportBtn.addEventListener('click', generateReport);

    const reportsBackBtn = document.getElementById('reports-back-btn');
    if(reportsBackBtn) reportsBackBtn.addEventListener('click', () => showModule('home'));
  }

  // --- API Communication ---

  // safeFetch function - Handles communication with the Google Apps Script API
  // Expects and validates standard JSON responses for both GET and POST.
  // Assumes Apps Script returns { success: true, data: {...} } for GET data,
  // and { success: true, message: "...", id: "...", ...} for successful POST actions.
  // Assumes Apps Script returns { success: false, message: "...", error: "..." } for API-side errors.
  async function safeFetch(url, options = {}) {
      console.log(`Attempting fetch: ${url}`, options.method || 'GET', options.body ? JSON.parse(options.body) : ''); // Log method and body
    try {
        // Ensure headers for JSON are set, especially for POST
        if (!options.headers) options.headers = {};
        // Setting Content-Type is important for the server to parse the body
        options.headers["Content-Type"] = "application/json";

        // Perform the fetch request
        const response = await fetch(url, options);

        // Check for HTTP errors (404, 500, etc.)
        if (!response.ok) {
             // Attempt to read error body if available and response is not successfully OK
            const errorBody = await response.text().catch(() => "N/A (could not read body)");
            const errorText = `HTTP error! status: ${response.status}. Body: ${errorBody.substring(0, 200)}`; // Limit body length in log
            console.error('Fetch failed (HTTP Error):', errorText, response);
            throw new Error(errorText);
        }

        // Try to parse response as JSON for both GET and POST on success
        // Assumes the Apps Script consistently returns JSON on successful HTTP status
        try {
            const data = await response.json();
            console.log('Fetch successful, API Response Data:', data);

            // Check for a server-side 'success' status within the JSON data
            // Assumes Apps Script returns { success: true, ... } on successful operations and { success: false, message: "..." } on logical errors
            if (data && data.success === false) {
                 const apiErrorMessage = data.message || 'API reported unknown error';
                 console.error('Fetch successful HTTP status, but API reported server-side error:', apiErrorMessage, data);
                 throw new Error('API reported error: ' + apiErrorMessage);
            }

            // For GET, we expect the data 
