# jackkeaveny.github.io

<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Jack Keaveny | Data Science Portfolio</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      max-width: 800px;
      margin: auto;
      padding: 30px;
    }
    .repo {
      border: 1px solid #ddd;
      padding: 15px;
      border-radius: 8px;
      margin-bottom: 15px;
    }
    a {
      color: #0366d6;
      text-decoration: none;
    }
    a:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>

<h1>Jack Keaveny</h1>
<p>Data Science & Machine Learning Portfolio</p>
<p>Below are all my public projects:</p>

<div id="repos"></div>

<script>
// Fetch all public repos from GitHub API
fetch("https://api.github.com/users/jackkeaveny/repos")
  .then(response => response.json())
  .then(data => {
    const container = document.getElementById("repos");
    data.forEach(repo => {
      const div = document.createElement("div");
      div.className = "repo";
      div.innerHTML = `
        <h3><a href="${repo.html_url}" target="_blank">${repo.name}</a></h3>
        <p>${repo.description || "No description provided."}</p>
      `;
      container.appendChild(div);
    });
  });
</script>

</body>
</html>
