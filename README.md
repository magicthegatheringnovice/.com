<!DOCTYPE html>
<html>
<head>
	<title>MTG Card Collection Inventory</title>
</head>
<body>
	<h1>MTG Card Collection Inventory</h1>
	<form>
		<label for="cardName">Card Name:</label>
		<input type="text" id="cardName" name="cardName" placeholder="Enter card name...">
		<br>
		<label for="cardQuantity">Quantity:</label>
		<input type="number" id="cardQuantity" name="cardQuantity" min="1" max="4" value="1">
		<br>
		<label for="cardCondition">Condition:</label>
		<select id="cardCondition" name="cardCondition">
			<option value="Near Mint">Near Mint</option>
			<option value="Lightly Played">Lightly Played</option>
			<option value="Moderately Played">Moderately Played</option>
			<option value="Heavily Played">Heavily Played</option>
			<option value="Damaged">Damaged</option>
		</select>
		<br>
		<button type="button" onclick="addCard()">Add Card</button>
	</form>
	<table id="cardTable">
		<thead>
			<tr>
				<th>Card Name</th>
				<th>Quantity</th>
				<th>Condition</th>
			</tr>
		</thead>
		<tbody>
		</tbody>
	</table>
	<script>
		function addCard() {
			// Get form values
			var cardName = document.getElementById("cardName").value;
			var cardQuantity = document.getElementById("cardQuantity").value;
			var cardCondition = document.getElementById("cardCondition").value;

			// Create new table row
			var row = document.createElement("tr");

			// Create table cells
			var nameCell = document.createElement("td");
			var quantityCell = document.createElement("td");
			var conditionCell = document.createElement("td");

			// Add form values to table cells
			nameCell.innerHTML = cardName;
			quantityCell.innerHTML = cardQuantity;
			conditionCell.innerHTML = cardCondition;

			// Add table cells to table row
			row.appendChild(nameCell);
			row.appendChild(quantityCell);
			row.appendChild(conditionCell);

			// Add table row to table body
			document.getElementById("cardTable").getElementsByTagName("tbody")[0].appendChild(row);
		}
	</script>
</body>
</html>
