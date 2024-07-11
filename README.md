# Stock-Material-Blending
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Material Stock Table</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 20px;
        }
        table, th, td {
            border: 1px solid black;
        }
        th, td {
            padding: 8px;
            text-align: left;
        }
        th {
            background-color: #f2f2f2;
        }
        .add-button, .remove-button {
            padding: 10px 15px;
            margin-top: 10px;
            cursor: pointer;
        }
    </style>
</head>
<body>

<h1>Material Stock Table</h1>

<table id="stockTable">
    <thead>
        <tr>
            <th>Material Name</th>
            <th>Quantity</th>
            <th>Unit</th>
            <th>Action</th>
        </tr>
    </thead>
    <tbody>
        <!-- Rows will be added here dynamically -->
    </tbody>
</table>

<button class="add-button" onclick="addRow()">Add Row</button>

<script>
    function addRow() {
        var table = document.getElementById("stockTable").getElementsByTagName('tbody')[0];
        var newRow = table.insertRow();
        
        var cell1 = newRow.insertCell(0);
        var cell2 = newRow.insertCell(1);
        var cell3 = newRow.insertCell(2);
        var cell4 = newRow.insertCell(3);

        cell1.innerHTML = '<input type="text" placeholder="Material Name">';
        cell2.innerHTML = '<input type="number" placeholder="Quantity">';
        cell3.innerHTML = '<input type="text" placeholder="Unit">';
        cell4.innerHTML = '<button class="remove-button" onclick="removeRow(this)">Remove</button>';
    }

    function removeRow(button) {
        var row = button.parentNode.parentNode;
        row.parentNode.removeChild(row);
    }
</script>

</body>
</html>
