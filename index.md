---
layout: home
title: Home
---

<p align="center">
  <img src="https://github.com/fahmiyufrizal.png" width="100" style="border-radius: 50%;" alt="Fahmi Yufrizal profile photo" />
</p>

Hi, I'm **Fahmi Yufrizal** 👋  
I'm a software engineer who enjoys building web apps, exploring clean architecture, and writing minimal, elegant code.

- 💻 Laravel, PHP, backend stuff
- ✍️ Writing about clean code, dev life, and tech
- 🔗 [github.com/fahmiyufrizal](https://github.com/fahmiyufrizal)

---

### 📝 Latest Posts
<!-- Blog posts are rendered automatically -->

---

### 📦 Repo

<div id="repo-list">
  Loading repositories...
</div>

<script>
  fetch("https://api.github.com/users/fahmiyufrizal/repos?sort=updated&per_page=5")
    .then(res => res.json())
    .then(repos => {
      const list = document.getElementById("repo-list");
      list.innerHTML = "<ul>" + repos.map(repo => `
        <li>
          <a href="${repo.html_url}" target="_blank">${repo.name}</a>
          <p style="margin: 4px 0; color: gray;">${repo.description || "No description"}</p>
        </li>
      `).join("") + "</ul>";
    })
    .catch(() => {
      document.getElementById("repo-list").innerText = "Failed to load repositories.";
    });
</script>
