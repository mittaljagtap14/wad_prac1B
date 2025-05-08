(B)
Write a JavaScript Program to get the user registration data and push to array/local storage with AJAX
POST method and data list in new page.

///////
users.html
//////

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Registered Users</title>

  <!-- Bootstrap CSS -->
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css">
</head>
<body class="container">
  <h2 class="text-center">Registered Users</h2>
  <table class="table table-bordered">
    <thead>
      <tr>
        <th>Name</th>
        <th>Email</th>
        <th>Password</th>
      </tr>
    </thead>
    <tbody id="userTable"></tbody>
  </table>

  <script>
    const users = JSON.parse(localStorage.getItem("users")) || [];
    const table = document.getElementById("userTable");

    users.forEach(user => {
      const row = `<tr>
        <td>${user.name}</td>
        <td>${user.email}</td>
        <td>${user.password}</td>
      </tr>`;
      table.innerHTML += row;
    });
  </script>
</body>
</html>

