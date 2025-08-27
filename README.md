# GitHub API Integration – Collaborator Lister

This is a companion script to my blog post where I shared my journey of writing a real-world shell script that talks directly to the GitHub API.

> **Goal:**
> List all users who have **read access** to a given GitHub repository.

This may look like a small script, but it reflects a common DevOps & developer use case: checking repo permissions quickly without clicking around GitHub’s UI.

---

## What This Script Does

* ✅ Accepts repository owner and repository name as input
* ✅ Connects to GitHub’s API using your username & personal access token
* ✅ Fetches all collaborators for the repository
* ✅ Filters and displays only users with **read (pull) access**
* ✅ Provides clear messages if no collaborators are found

---

## Example Usage

```bash
./list-users.sh REPO_OWNER REPO_NAME
```

For example:

```bash
./list-users.sh octocat hello-world
```

---

## Sample Output

```
Listing users with read access to octocat/hello-world...
Users with read access to octocat/hello-world:
alice
bob
```

Or, if no users are found:

```
No users with read access found for octocat/hello-world.
```

---

## Prerequisites

Before running the script, make sure you have:

* ✅ **curl** installed (to send API requests)
* ✅ **jq** installed (to parse JSON responses)
* ✅ A **GitHub username** and a **Personal Access Token** (PAT) with `repo` scope
* ✅ The username and token exported as environment variables:

```bash
export username="your-github-username"
export token="your-personal-access-token"
```

---

## Script Overview

Here’s how the script works under the hood:

1. **Takes two arguments** – the repository owner and repository name (`$1` and `$2`)
2. **Builds the API endpoint** – e.g., `repos/OWNER/REPO/collaborators`
3. **Uses curl** to make an authenticated request to GitHub’s API
4. **Parses the JSON** using `jq` to extract only collaborators with read access
5. **Prints results** in a clean, beginner-friendly format

---

## File Permissions

Make the script executable:

```bash
chmod +x list-users.sh
```

---

## Why This Matters

This project is about more than just querying GitHub. It’s about:

* Understanding how APIs work (step into “behind the scenes” of GitHub 🚪)
* Combining Bash + curl + jq to solve real-world problems
* Writing scripts that are reusable, simple, and reliable
* Building confidence in DevOps habits — automation, clarity, and structure

Even a small script like this can save you time and make you feel comfortable working with APIs.

---

## 📘 Blog Post

Want the full breakdown — explained line by line for beginners?

👉 [Read the full blog here](#) *(replace with your Hashnode/Medium link)*

---

Thanks for stopping by!
— *Arnab*

---

