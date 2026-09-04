# Git Advanced Commands

## 1. Git Squash

بنستخدم `Squash` لما يكون عندنا كذا `commit` صغيرة وعايزين ندمجهم في `commit` واحدة علشان نخلي الـ history أنضف وأسهل في القراءة.

```text
A → B → C → D
      ↓
A → B → X
```

---

## 2. Git Merge

بنستخدم `Merge` علشان ندمج الـ changes اللي في branch مع branch تاني من غير ما نمسح الـ history بتاعهم.

```bash
git switch main
git merge feature
```

---

## 3. Git Rebase

بنستخدم `Rebase` علشان ننقل الـ commits بتاعت branch ونحطها فوق آخر نسخة من branch تاني ونخلي الـ history خط مستقيم.

```bash
git switch feature
git rebase main
```

```text
Before:
A → B → C → F → G
         \
          D → E

After:
A → B → C → F → G → D' → E'
```

---

## 4. Git Merge vs Rebase

الـ `Merge` بيحافظ على الـ history زي ما هو، لكن الـ `Rebase` بيعيد ترتيب الـ commits ويخلي الـ history أنضف.

---

## 5. Git Help

بنستخدم `Git Help` لما نكون عايزين نعرف شرح أو options أي command في Git.

```bash
git help commit
git help merge
```

---

## 6. Git Cherry-Pick

بنستخدم `Cherry-Pick` لما نكون عايزين ناخد `commit` معينة من branch ونطبقها على branch تاني.

```bash
git switch main
git cherry-pick <commit>
```

---

## 7. Git Clean

بنستخدم `Git Clean` علشان نمسح الملفات اللي Git مش متابعها `untracked files`.

```bash
git clean -n
git clean -f
```

---

## 8. Git Grep

بنستخدم `Git Grep` علشان ندور على كلمة أو جزء من كود جوه ملفات المشروع بسرعة.

```bash
git grep "Console"
```

---

## 9. Git Blame

بنستخدم `Git Blame` علشان نعرف مين عمل آخر تعديل على كل سطر في ملف وإمتى.

```bash
git blame Program.cs
```

---

## 10. Git Bisect

بنستخدم `Git Bisect` علشان نحدد الـ commit اللي دخلت الـ bug عن طريق البحث بين الـ commits.

```bash
git bisect start
git bisect bad
git bisect good <commit>
```

---

## 11. Git Shortlog

بنستخدم `Git Shortlog` علشان نطلع ملخص للـ commits ونشوف كل Developer عمل كام commit.

```bash
git shortlog
git shortlog -s
```

---

## 12. Git Prune

بنستخدم `Git Prune` علشان ننضف الـ Git repository من الـ objects اللي مبقاش ليها استخدام أو reference.

```bash
git prune
```

---

## 13. Git Worktree

بنستخدم `Git Worktree` علشان نشتغل على أكتر من branch في نفس الوقت من خلال فولدرات مختلفة.

```bash
git worktree add ../bug-fix bug-fix
```

---

## 14. Git Verify-Commit

بنستخدم `Git Verify-Commit` علشان نتأكد إن الـ commit متوقعة بتوقيع صحيح.

```bash
git verify-commit <commit>
```

---

## 15. Git Filter-Repo

بنستخدم `Git Filter-Repo` علشان نعدل أو ننضف الـ Git history زي حذف ملف حساس من كل الـ commits.

```bash
git filter-repo --path secret.txt --invert-paths
```