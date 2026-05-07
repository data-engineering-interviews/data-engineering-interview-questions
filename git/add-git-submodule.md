# Add Git Submodule

> **Company:** EY | **Difficulty:** Medium

---

#### **Scenario**

You have a Git repository at `/home/interview/repo` where you need to include another repository as a dependency in your project.

#### **Task**

Add a Git submodule in the `vendor/utils` directory pointing to the external utils library at `file:///tmp/remote-repo/utils-lib.git`, commit the submodule configuration, and ensure the submodule is properly initialized with the `.gitmodules` file created and the submodule directory containing the external repository files.

#### **Example**

```
# Before (no submodule)

.git/  README.md

cat: .gitmodules: No such file or directory
```

```
# After (submodule added)

.git/  .gitmodules  README.md  vendor/

.gitmodules file now exists with submodule configuration

Submodule directory contains: helper.js  README.md
```

---
