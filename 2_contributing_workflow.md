# Crash Course in Contributing to Scikit-learn:  Workflow

PR = Pull Request  
**Important Note:**  Please include **(#wimlds)** in your PR commit message so we can track them. 

---

## PART A:  Set-up work environment

#### Set up virtual environment
```bash
conda create -n sklearndev numpy scipy matplotlib pytest sphinx cython ipykernel
```
#### Activate virtual environment:  
```bash
source activate sklearndev
```
---

## PART B:  Set-up repository

### Fork repo:  https://github.com/scikit-learn/scikit-learn

### Set up local repo  
#### `git clone` your forked repo url.  

>my example
```bash
git clone https://github.com/reshamas/scikit-learn.git
```

#### `cd scikit-learn` into your folder

>my example
```bash
cd scikit-learn
```

#### Add `upstream` remote
```
git remote add upstream https://github.com/scikit-learn/scikit-learn.git
```

#### Check remotes are there using `git remote -v`

>my example
```bash
origin	https://github.com/reshamas/scikit-learn.git (fetch)
origin	https://github.com/reshamas/scikit-learn.git (push)
upstream	https://github.com/scikit-learn/scikit-learn.git (fetch)
upstream	https://github.com/scikit-learn/scikit-learn.git (push)
```

### Update local repo
```bash
git pull upstream master
```

### To fetch (someone else's) PR:
```bash
git fetch https://github.com/theirusername/reponame.git theirbranch:ourbranch
```


#### Build and run tests
```bash
pip install -e .
```
Note:  this will overwrite existing installations
Reference:  ["Editable" Installs](https://pip.pypa.io/en/stable/reference/pip_install/#examples)

---

## PART C:  Select issue
- Pick an issue to work on:  https://github.com/scikit-learn/scikit-learn/issues
- Comment on issue with:  *I'm working on this*

---

## PART D:  Fixing issue
- Explore and fix issue.  This will take the majority of time (!)
- Make updates to file `<file_name>`


---

## PART E:  Committing change 

#### Create feature branch

```bash
git checkout -b <feature_branch>
```

#### Commit changes to branch
Please include **(#wimlds)** in your PR so we can track them.  
 
```bash
git add <file_name>
git commit -m 'description for fix (#wimlds)'
```

---

## PART F:  Run tests

#### `flake8` formatting test
- `flake8` tests for formatting errors

```bash
flake8 <file_name>
```

#### `pytest sklearn` tests
- The [full test suite](http://scikit-learn.org/stable/developers/tips.html) takes fairly long to run
- Run tests  
```bash
pytest sklearn
```

### Create test file

#### Run tests on individual test files  
- Create test file under `tests` directory
- Run test file

```bash
pytest <test_file>
```

>example
```bash
pytest /Users/reshamashaikh/scikit-learn/sklearn/metrics/tests/test_classifier.py
pytest /Users/reshamashaikh/scikit-learn/sklearn/metrics/tests/test_mixture.py
```

---

## PART G:  Submit Pull Request
#### After all tests have passed, push update file(s) to feature branch
- `test_file` should be committed to feature branch as well

```bash
git add <test_file>
git commit -m 'description for test file'
git push origin <feature_branch>
```

#### Submit PR  
Do this on GitHub.

---

## Part H:  Regression Tests on GitHub
These tests happen automatically after a PR has been submitted.

<img src="images/reg_tests.png"  />
 
---

## Part I:  Next Steps
- Wait for reviews (be patient)
- Address review comments in the same branch
- Pushing to your fork will update the PR
- Reviewers will "approve" the PR or change title to [MRG + 1]
- You need **2 approvals for a merge**


---

## References
- [`flake8`](resouces.md)
