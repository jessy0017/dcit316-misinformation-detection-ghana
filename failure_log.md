# Failure Log

## 1. Misleadingly high accuracy
- **Problem:** The first baseline scored 98.68% accuracy, which looked too good.
- **Cause:** The `subject` column separates fake from real perfectly, and 99.2% of real
  articles contain "(Reuters)" against 0.04% of fake ones.
- **Fix:** Excluded `subject`, then trained a second baseline on text with the
  "(Reuters)" marker stripped. Accuracy fell only to 98.00%.
- **Lesson:** Check what a model has learned before trusting its score.

## 2. FileNotFoundError when loading the data
- **Problem:** `pd.read_csv('../data/raw/Fake.csv')` failed.
- **Cause:** The notebook was running from the repository root, so `../` pointed outside the repo.
- **Fix:** Printed `os.getcwd()` to see the real working directory, then corrected the path.
  The notebook later moved to `notebooks/`, where `../data/raw/` is correct.

## 3. Notebook saved in the wrong folder
- **Problem:** A "File Save Error: Failed to fetch" appeared and the notebook turned up in `src/`.
- **Cause:** The Jupyter server connection dropped during a save.
- **Fix:** Reopened it from `src/` and moved it with `git mv` into `notebooks/`.

## 4. NameError after the kernel restarted
- **Problem:** `name 'df' is not defined` and `name 'X_train_s_tfidf' is not defined`.
- **Cause:** The kernel restarted, so all variables were lost even though old outputs were still visible.
- **Fix:** Used Kernel > Restart Kernel and Run All Cells.

## 5. Git commands run in the wrong folder
- **Problem:** `fatal: not a git repository`.
- **Cause:** The terminal was in the parent folder, `Sem-Project`, not the repository.
- **Fix:** Ran `cd zunuo_dcit316-final-project` first.

## 6. Push failed after renaming the repository
- **Problem:** `remote: Repository not found`.
- **Cause:** The local remote URL pointed to the new name before the rename on GitHub was complete.
- **Fix:** Confirmed the name on GitHub, kept the remote URL matching it, and pushed again.

## 7. Notebook paste errors
- **Problem:** `IndentationError: unexpected indent` and `_IncompleteInputError`.
- **Cause:** A stray leading space, and a multi-line call that was cut off when pasted.
- **Fix:** Removed the space and pasted the call as a single line.

## 8. Find-and-replace damaged a code name
- **Problem:** Replacing "TFIDF" with "TF-IDF" in the paper changed `TfidfVectorizer` to "TF-IDFVectorizer".
- **Fix:** Restored `TfidfVectorizer` in Section 4.1.