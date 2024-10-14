<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aplikasi Pengganti Excel</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Data Tabel</h1>
        <table id="dataTable">
            <thead>
                <tr>
                    <th>ID</th>
                    <th>Nama</th>
                    <th>Usia</th>
                    <th>Aksi</th>
                </tr>
            </thead>
            <tbody></tbody>
        </table>
        <button onclick="addRow()">Tambah Baris</button>
    </div>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
}

.container {
    width: 80%;
    margin: auto;
}

table {
    width: 100%;
    border-collapse: collapse;
    margin: 20px 0;
}

th, td {
    border: 1px solid #ddd;
    padding: 8px;
    text-align: left;
}

th {
    background-color: #f2f2f2;
}

button {
    margin: 10px 0;
    padding: 10px;
    background-color: #4CAF50;
    color: white;
    border: none;
    cursor: pointer;
}

button:hover {
    background-color: #45a049;
}
let idCounter = 1;

function addRow() {
    const tableBody = document.querySelector("#dataTable tbody");
    const newRow = document.createElement("tr");

    newRow.innerHTML = `
        <td>${idCounter}</td>
        <td contenteditable="true">Nama</td>
        <td contenteditable="true">Usia</td>
        <td><button onclick="deleteRow(this)">Hapus</button></td>
    `;

    tableBody.appendChild(newRow);
    idCounter++;
}

function deleteRow(button) {
    const row = button.parentElement.parentElement;
    row.parentElement.removeChild(row);
}


