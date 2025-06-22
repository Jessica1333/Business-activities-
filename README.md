# Business-activities-
Business activities of people living with disabilities 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Business Activities Summary</title>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<link href="https://cdnjs.cloudflare.com/ajax/libs/tailwindcss/2.2.19/tailwind.min.css" rel="stylesheet">
</head>
<body class="bg-gray-50 p-8">
<h1 class="text-3xl font-bold mb-6 text-center">Business Activities of Persons with Disabilities</h1>

<!-- Table -->
<table class="min-w-full bg-white shadow-md rounded mb-8">
<thead class="bg-blue-100">
<tr>
<th class="p-3 border">Name</th>
<th class="p-3 border">Business</th>
<th class="p-3 border">Income (GHS/Day)</th>
<th class="p-3 border">Challenges</th>
<th class="p-3 border">Support</th>
<th class="p-3 border">Aspiration</th>
</tr>
</thead>
<tbody id="businessTable" class="bg-white"></tbody>
</table>

<!-- Chart -->
<h2 class="text-xl font-semibold mb-4">Income per Person (GHS per day)</h2>
<canvas id="incomeChart" width="400" height="200"></canvas>

<script>
const data = [
    { "name": "Eunice Darko", "business": "Fruit Selling", "income_per_day": 20, "challenges": "Mobility, unstable profit", "support": "GHS1,500 (Social Welfare)", "aspiration": "Expand business into a shop" },
    { "name": "Leticia Ofosuaa", "business": "Tea & Bread", "income_per_day": 20, "challenges": "Mobility, financing", "support": "GHS1,500 (Social Welfare)", "aspiration": "Sell more food items" },
    { "name": "Afua Gyekyebea", "business": "Water", "income_per_day": 5, "challenges": "Low profit, health issues", "support": "Fridge (Social Welfare)", "aspiration": "Own a shop" },
    { "name": "Patricia Anim", "business": "Water", "income_per_day": 5, "challenges": "Weakness, discrimination", "support": "Fridge (Social Welfare)", "aspiration": "Own a container shop" }
];

// Populate the table
const tableBody = document.getElementById('businessTable');
data.forEach(row => {
    const tr = document.createElement('tr');
    tr.innerHTML = `
        <td class="p-3 border">${row.name}</td>
        <td class="p-3 border">${row.business}</td>
        <td class="p-3 border">${row.income_per_day}</td>
        <td class="p-3 border">${row.challenges}</td>
        <td class="p-3 border">${row.support}</td>
        <td class="p-3 border">${row.aspiration}</td>
    `;
    tableBody.appendChild(tr);
});

// Render the chart
new Chart(document.getElementById('incomeChart').getContext('2d'), {
    type: 'bar',
    data: {
        labels: data.map(d => d.name),
        datasets: [{
            label: 'Income per Day (GHS)',
            data: data.map(d => d.income_per_day),
            backgroundColor: ['#3B82F6','#10B981','#F59E0B','#EF4444'],
        }]
    }
});
</script>
</body>
</html>
