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

### 📦 Repo

<style>
  .repo-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1rem;
    margin-top: 1rem;
  }
  .repo-card {
    border: 1px solid #ccc;
    border-radius: 10px;
    padding: 1rem;
    background-color: rgba(255,255,255,0.05);
    transition: all 0.2s;
  }
  body[data-theme='dark'] .repo-card {
    border-color: #333;
    background-color: #1a1a1a;
  }
  .repo-card:hover {
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  }
</style>

<div id="repo-list" class="repo-grid">Loading repositories...</div>

<script>
  fetch("https://api.github.com/users/fahmiyufrizal/repos?sort=updated&per_page=6")
    .then(res => res.json())
    .then(repos => {
      const container = document.getElementById("repo-list");
      container.innerHTML = repos.map(repo => `
        <div class="repo-card">
          <strong><a href="${repo.html_url}" target="_blank">${repo.name}</a></strong>
          <p style="font-size: 0.85em; color: gray; margin: 0.5rem 0;">
            ${repo.description || "No description"}
          </p>
        </div>
      `).join("");
    })
    .catch(() => {
      document.getElementById("repo-list").innerText = "Failed to load repositories.";
    });
</script>
---
### 📝 Latest Posts
<!-- Blog posts are rendered automatically -->
---
