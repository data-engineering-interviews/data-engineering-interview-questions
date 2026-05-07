# Update Submodule to Latest Commit

> **Company:** GoDaddy | **Difficulty:** Medium

---

#### Scenario:

You have a Git repository at `/home/interview/repo` that contains a **submodule in the `vendor/utils` directory**. The submodule is pointing to an old commit, but **newer commits exist on the submodule's remote repository**.



#### Task:
Update the submodule to the latest commit on its default branch and commit this change in the parent repository.

#### **Example:**

```
# Before (submodule at old commit)
$ git submodule status
 a1b2c3d vendor/utils (v1.0.0)

$ cd vendor/utils && git log --oneline -1
a1b2c3d Add helper function
```
```
# After (submodule updated)
$ git submodule status
 e5f6g7h vendor/utils (v1.2.0)

$ cd vendor/utils && git log --oneline -1
e5f6g7h Add advanced features
```

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/terminal/update-submodule-to-latest-commit)
